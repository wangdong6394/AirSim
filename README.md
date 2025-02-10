## 解决官方版本的airsim在UE5.2中使用时，项目打包存在的问题。
   Solve the problem of project packaging when using the official version of AirSim in UE5.2
### 1.编译报错
  如果报错信息涉及FObjectProperty的Cast<>强制类型转换，修改SimModeBase.c文件的232行为以下内容：
  #if ENGINE_MINOR_VERSION > 24
        FObjectProperty* sun_prop = CastFieldChecked<FObjectProperty>(p);
#else
        FObjectProperty* sun_prop = CastField<FObjectProperty>(p);
#endif
