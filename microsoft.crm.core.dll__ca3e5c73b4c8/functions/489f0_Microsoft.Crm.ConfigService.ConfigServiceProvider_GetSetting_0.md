# Microsoft.Crm.ConfigService.ConfigServiceProvider::GetSetting_0

- ea: `0x489f0`
- end: `0x48b7c`
- name: `Microsoft.Crm.ConfigService.ConfigServiceProvider::GetSetting_0`
- size: `396`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x489e0`

## callees

- `0x1a7f0`
- `0x48850`
- `0x489f0`
- `0x48c00`
- `0x48c30`
- `0x48f30`
- `0x49150`
- `0x491f0`
- `0x49360`

## string_xrefs

- `0x48aa7`: `Authentication exception in retrieving config {0}: {1}`
- `0x48b0e`: `Exception in retrieving config {0}: {1}`
- `0x48b42`: `Config service call failed`

## pseudocode

```c

```

## disassembly

```asm
0x489f0  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x489f5  stloc.0
0x489f6  ldarg.0
0x489f7  ldarg.1
0x489f8  ldarg.2
0x489f9  ldarg.3
0x489fa  call     instance string Microsoft.Crm.ConfigService.ConfigServiceProvider::GetCacheKey(string key, string tableName, string primaryKey)
0x489ff  stloc.1
0x48a00  ldsfld   class [System.Runtime.Caching]System.Runtime.Caching.MemoryCache Microsoft.Crm.ConfigService.ConfigServiceProvider::_configCache
0x48a05  ldloc.1
0x48a06  ldnull
0x48a07  callvirt instance bool [System.Runtime.Caching]System.Runtime.Caching.ObjectCache::Contains(string, string)
0x48a0c  brfalse.s loc_48A36
0x48a0e  ldloc.0
0x48a0f  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x48a14  call     class Microsoft.Crm.ConfigService.Telemetry.IMetrics Microsoft.Crm.ConfigService.Telemetry.Metrics::get_Instance()
0x48a19  ldloc.0
0x48a1a  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x48a1f  callvirt instance void Microsoft.Crm.ConfigService.Telemetry.IMetrics::ReportGetSettingsLatency(int64 latency)
0x48a24  ldsfld   class [System.Runtime.Caching]System.Runtime.Caching.MemoryCache Microsoft.Crm.ConfigService.ConfigServiceProvider::_configCache
0x48a29  ldloc.1
0x48a2a  ldnull
0x48a2b  callvirt instance object [System.Runtime.Caching]System.Runtime.Caching.ObjectCache::Get(string, string)
0x48a30  callvirt instance string [mscorlib]System.Object::ToString()
0x48a35  ret
0x48a36  ldnull
0x48a37  stloc.2
0x48a38  ldarg.2
0x48a39  call     string Microsoft.Crm.ConfigService.ConfigClientUtility::GetScopeName(string tableName)
0x48a3e  stloc.3
0x48a3f  ldnull
0x48a40  stloc.s  4
0x48a42  ldloc.3
0x48a43  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x48a48  brtrue.s loc_48A60
0x48a4a  ldloc.3
0x48a4b  ldarg.3
0x48a4c  newobj   instance void [Microsoft.Crm.ConfigClient.ReadOnly]Microsoft.Crm.ConfigClient.Models.Scope::.ctor(string, string)
0x48a51  stloc.s  5
0x48a53  ldc.i4.1
0x48a54  newarr   [Microsoft.Crm.ConfigClient.ReadOnly]Microsoft.Crm.ConfigClient.Models.Scope
0x48a59  dup
0x48a5a  ldc.i4.0
0x48a5b  ldloc.s  5
0x48a5d  stelem.ref
0x48a5e  stloc.s  4
0x48a60  nop
0x48a61  ldloc.s  4
0x48a63  brtrue.s loc_48A76
0x48a65  ldarg.0
0x48a66  ldfld    class [Microsoft.Crm.ConfigService.Adapter]Microsoft.Crm.ConfigService.Adapter.IConfigServiceAdapter Microsoft.Crm.ConfigService.ConfigServiceProvider::_configServiceAdapter
0x48a6b  ldarg.1
0x48a6c  ldarg.s  4
0x48a6e  callvirt instance string [Microsoft.Crm.ConfigService.Adapter]Microsoft.Crm.ConfigService.Adapter.IConfigServiceAdapter::GetSetting(string, string)
0x48a73  stloc.2
0x48a74  br.s     loc_48A89
0x48a76  ldarg.0
0x48a77  ldfld    class [Microsoft.Crm.ConfigService.Adapter]Microsoft.Crm.ConfigService.Adapter.IConfigServiceAdapter Microsoft.Crm.ConfigService.ConfigServiceProvider::_configServiceAdapter
0x48a7c  ldloc.s  4
0x48a7e  ldarg.1
0x48a7f  ldarg.s  5
0x48a81  ldarg.s  4
0x48a83  callvirt instance string [Microsoft.Crm.ConfigService.Adapter]Microsoft.Crm.ConfigService.Adapter.IConfigServiceAdapter::GetSetting(class [Microsoft.Crm.ConfigClient.ReadOnly]Microsoft.Crm.ConfigClient.Models.Scope[], string, bool, string)
0x48a88  stloc.2
0x48a89  ldloc.2
0x48a8a  brfalse.s loc_48A93
0x48a8c  ldloc.1
0x48a8d  ldloc.2
0x48a8e  call     void Microsoft.Crm.ConfigService.ConfigServiceProvider::InsertIntoCache(string cacheKey, string response)
0x48a93  ldloc.2
0x48a94  stloc.s  6
0x48a96  leave    loc_48B79
0x48a9b  stloc.s  7
0x48a9d  call     class Microsoft.Crm.ConfigService.Telemetry.IEvents Microsoft.Crm.ConfigService.Telemetry.Events::get_Instance()
0x48aa2  ldstr    aUnauthorizedex// "UnauthorizedException"
0x48aa7  ldstr    aAuthentication_2// "Authentication exception in retrieving "...
0x48aac  ldarg.1
0x48aad  ldloc.s  7
0x48aaf  call     string [mscorlib]System.String::Format(string, object, object)
0x48ab4  ldstr    aGetsetting// "GetSetting"
0x48ab9  ldc.i4.4
0x48aba  newarr   [mscorlib]System.Object
0x48abf  dup
0x48ac0  ldc.i4.0
0x48ac1  ldarg.2
0x48ac2  stelem.ref
0x48ac3  dup
0x48ac4  ldc.i4.1
0x48ac5  ldarg.3
0x48ac6  stelem.ref
0x48ac7  dup
0x48ac8  ldc.i4.2
0x48ac9  ldarg.s  4
0x48acb  stelem.ref
0x48acc  dup
0x48acd  ldc.i4.3
0x48ace  ldarg.s  5
0x48ad0  box      [mscorlib]System.Boolean
0x48ad5  stelem.ref
0x48ad6  callvirt instance void Microsoft.Crm.ConfigService.Telemetry.IEvents::LogError(string type, string message, string functionName, object[] parameterList)
0x48adb  ldstr    aAuthentication_3// "Authentication failure"
0x48ae0  ldc.i4   0x80040277
0x48ae5  ldc.i4.1
0x48ae6  newarr   [mscorlib]System.Object
0x48aeb  dup
0x48aec  ldc.i4.0
0x48aed  ldloc.s  7
0x48aef  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x48af4  stelem.ref
0x48af5  newobj   instance void Microsoft.Crm.CrmException::.ctor(string formattedErrorMessage, int32 errorCode, object[] arguments)
0x48afa  throw
0x48afb  stloc.s  8
0x48afd  call     class Microsoft.Crm.ConfigService.Telemetry.IEvents Microsoft.Crm.ConfigService.Telemetry.Events::get_Instance()
0x48b02  ldloc.s  8
0x48b04  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x48b09  callvirt instance string [mscorlib]System.Object::ToString()
0x48b0e  ldstr    aExceptionInRet// "Exception in retrieving config {0}: {1}"
0x48b13  ldarg.1
0x48b14  ldloc.s  8
0x48b16  call     string [mscorlib]System.String::Format(string, object, object)
0x48b1b  ldstr    aGetsetting// "GetSetting"
0x48b20  ldc.i4.4
0x48b21  newarr   [mscorlib]System.Object
0x48b26  dup
0x48b27  ldc.i4.0
0x48b28  ldarg.2
0x48b29  stelem.ref
0x48b2a  dup
0x48b2b  ldc.i4.1
0x48b2c  ldarg.3
0x48b2d  stelem.ref
0x48b2e  dup
0x48b2f  ldc.i4.2
0x48b30  ldarg.s  4
0x48b32  stelem.ref
0x48b33  dup
0x48b34  ldc.i4.3
0x48b35  ldarg.s  5
0x48b37  box      [mscorlib]System.Boolean
0x48b3c  stelem.ref
0x48b3d  callvirt instance void Microsoft.Crm.ConfigService.Telemetry.IEvents::LogError(string type, string message, string functionName, object[] parameterList)
0x48b42  ldstr    aConfigServiceC// "Config service call failed"
0x48b47  ldc.i4   0x80040216
0x48b4c  ldc.i4.1
0x48b4d  newarr   [mscorlib]System.Object
0x48b52  dup
0x48b53  ldc.i4.0
0x48b54  ldloc.s  8
0x48b56  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x48b5b  stelem.ref
0x48b5c  newobj   instance void Microsoft.Crm.CrmException::.ctor(string formattedErrorMessage, int32 errorCode, object[] arguments)
0x48b61  throw
0x48b62  ldloc.0
0x48b63  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x48b68  call     class Microsoft.Crm.ConfigService.Telemetry.IMetrics Microsoft.Crm.ConfigService.Telemetry.Metrics::get_Instance()
0x48b6d  ldloc.0
0x48b6e  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x48b73  callvirt instance void Microsoft.Crm.ConfigService.Telemetry.IMetrics::ReportGetSettingsLatency(int64 latency)
0x48b78  endfinally
0x48b79  ldloc.s  6
0x48b7b  ret
```
