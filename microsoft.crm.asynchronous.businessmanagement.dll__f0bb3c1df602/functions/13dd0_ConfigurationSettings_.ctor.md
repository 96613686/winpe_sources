# ConfigurationSettings::.ctor

- ea: `0x13dd0`
- end: `0x13ed3`
- name: `ConfigurationSettings::.ctor`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x5d50`

## pseudocode

```c

```

## disassembly

```asm
0x13dd0  ldarg.0
0x13dd1  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x13dd6  stfld    valuetype [mscorlib]System.DateTime ConfigurationSettings::startDateTime
0x13ddb  ldarg.0
0x13ddc  ldc.i4.5
0x13ddd  stfld    int32 ConfigurationSettings::maxRetryCount
0x13de2  ldarg.0
0x13de3  ldc.i4   0x1F4
0x13de8  stfld    int32 ConfigurationSettings::maxExchangeBatchSize
0x13ded  ldarg.0
0x13dee  ldc.i4.s 0x14
0x13df0  stfld    int32 ConfigurationSettings::maxRunTimeInMinutes
0x13df5  ldarg.0
0x13df6  ldc.i4.s 0x1C
0x13df8  stfld    int32 ConfigurationSettings::numberOfDaysToSync
0x13dfd  ldarg.0
0x13dfe  call     instance void [mscorlib]System.Object::.ctor()
0x13e03  ldarg.0
0x13e04  ldc.i4.0
0x13e05  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x13e0a  ldstr    aResourcebookin_3// "ResourceBookingSyncMaxRetryCount"
0x13e0f  ldarg.0
0x13e10  ldfld    int32 ConfigurationSettings::maxRetryCount
0x13e15  callvirt T0x2B00001C
0x13e1a  call     int32 [mscorlib]System.Math::Max(int32, int32)
0x13e1f  stfld    int32 ConfigurationSettings::maxRetryCount
0x13e24  ldarg.0
0x13e25  ldc.i4.1
0x13e26  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x13e2b  ldstr    aResourcebookin_4// "ResourceBookingSyncMaxExchangeBatchSize"
0x13e30  ldarg.0
0x13e31  ldfld    int32 ConfigurationSettings::maxExchangeBatchSize
0x13e36  callvirt T0x2B00001C
0x13e3b  call     int32 [mscorlib]System.Math::Max(int32, int32)
0x13e40  stfld    int32 ConfigurationSettings::maxExchangeBatchSize
0x13e45  ldarg.0
0x13e46  ldc.i4.1
0x13e47  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x13e4c  ldstr    aResourcebookin_5// "ResourceBookingSyncMaxRunTimeInMinutes"
0x13e51  ldarg.0
0x13e52  ldfld    int32 ConfigurationSettings::maxRunTimeInMinutes
0x13e57  callvirt T0x2B00001C
0x13e5c  call     int32 [mscorlib]System.Math::Max(int32, int32)
0x13e61  stfld    int32 ConfigurationSettings::maxRunTimeInMinutes
0x13e66  ldarg.0
0x13e67  ldc.i4.1
0x13e68  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x13e6d  ldstr    aResourcebookin_6// "ResourceBookingSyncNumberOfDaysToSync"
0x13e72  ldarg.0
0x13e73  ldfld    int32 ConfigurationSettings::numberOfDaysToSync
0x13e78  callvirt T0x2B00001C
0x13e7d  call     int32 [mscorlib]System.Math::Max(int32, int32)
0x13e82  stfld    int32 ConfigurationSettings::numberOfDaysToSync
0x13e87  ldarg.0
0x13e88  ldarg.0
0x13e89  ldflda   valuetype [mscorlib]System.DateTime ConfigurationSettings::startDateTime
0x13e8e  ldc.r8   -24.0
0x13e97  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddHours(float64)
0x13e9c  stfld    valuetype [mscorlib]System.DateTime ConfigurationSettings::lowerBoundDateTime
0x13ea1  ldarg.0
0x13ea2  ldarg.0
0x13ea3  ldflda   valuetype [mscorlib]System.DateTime ConfigurationSettings::startDateTime
0x13ea8  ldarg.0
0x13ea9  ldfld    int32 ConfigurationSettings::numberOfDaysToSync
0x13eae  conv.r8
0x13eaf  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x13eb4  stfld    valuetype [mscorlib]System.DateTime ConfigurationSettings::upperBoundDateTime
0x13eb9  ldarg.0
0x13eba  ldarg.0
0x13ebb  ldflda   valuetype [mscorlib]System.DateTime ConfigurationSettings::startDateTime
0x13ec0  ldarg.0
0x13ec1  ldfld    int32 ConfigurationSettings::numberOfDaysToSync
0x13ec6  neg
0x13ec7  conv.r8
0x13ec8  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x13ecd  stfld    valuetype [mscorlib]System.DateTime ConfigurationSettings::upperBoundDateTimeForCleanupIdMapping
0x13ed2  ret
```
