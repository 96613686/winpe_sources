# Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::ScheduleSyncLocatorCache

- ea: `0x5e110`
- end: `0x5e293`
- name: `Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::ScheduleSyncLocatorCache`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x5e3a0`

## callees

- `0x1eaa0`
- `0x1f510`
- `0x5db20`
- `0x5dd10`
- `0x5dd30`
- `0x5dd50`
- `0x5de00`
- `0x5e110`
- `0x5e2a0`

## string_xrefs

- `0x5e17b`: `LocatorCacheSyncEnabled`
- `0x5e173`: `LocatorCacheSyncManager`
- `0x5e257`: `LocatorCacheSyncManager`
- `0x5e166`: `{0}: Registry Key '{1}' is set to '{2}'. Starting synchronization tasks...`
- `0x5e1a5`: `Unexpected exception while syncing locator cache: {0}.`
- `0x5e24a`: `{0}: Waiting until next schedule cache refresh on '{1}' (UTC)`

## pseudocode

```c

```

## disassembly

```asm
0x5e110  br       loc_5E286
0x5e115  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0x5e11a  stloc.0
0x5e11b  ldloc.0
0x5e11c  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x5e121  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x5e126  stloc.1
0x5e127  ldloc.1
0x5e128  ldsfld   string Microsoft.Crm.CustomPropertyConstants::CrmServiceName
0x5e12d  call     string Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::get_ServiceIdentifier()
0x5e132  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x5e137  ldc.i4.1
0x5e138  stloc.2
0x5e139  ldarg.0
0x5e13a  ldfld    class Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.ILocatorCacheSettingAccessor Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::_locatorCacheSettingAccessor
0x5e13f  callvirt instance class Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettings Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.ILocatorCacheSettingAccessor::get_Settings()
0x5e144  callvirt instance bool Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettings::get_Enabled()
0x5e149  stloc.s  5
0x5e14b  ldloc.1
0x5e14c  ldsfld   string Microsoft.Crm.CustomPropertyConstants::IsCacheSyncEnabled
0x5e151  ldloca.s 5
0x5e153  call     instance string [mscorlib]System.Boolean::ToString()
0x5e158  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x5e15d  ldloc.s  5
0x5e15f  brfalse.s loc_5E196
0x5e161  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::Logger
0x5e166  ldstr    a0RegistryKey1I// "{0}: Registry Key '{1}' is set to '{2}'"...
0x5e16b  ldc.i4.3
0x5e16c  newarr   [mscorlib]System.Object
0x5e171  dup
0x5e172  ldc.i4.0
0x5e173  ldstr    aLocatorcachesy_4// "LocatorCacheSyncManager"
0x5e178  stelem.ref
0x5e179  dup
0x5e17a  ldc.i4.1
0x5e17b  ldstr    aLocatorcachesy_3// "LocatorCacheSyncEnabled"
0x5e180  stelem.ref
0x5e181  dup
0x5e182  ldc.i4.2
0x5e183  ldloc.s  5
0x5e185  box      [mscorlib]System.Boolean
0x5e18a  stelem.ref
0x5e18b  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogInformation(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x5e190  ldarg.0
0x5e191  call     instance void Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::RefreshCacheValues()
0x5e196  leave.s  loc_5E1D4
0x5e198  stloc.s  6
0x5e19a  ldc.i4.0
0x5e19b  stloc.2
0x5e19c  ldloc.s  6
0x5e19e  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x5e1a3  ldc.i4.s 0x14
0x5e1a5  ldstr    aUnexpectedExce_2// "Unexpected exception while syncing loca"...
0x5e1aa  ldc.i4.1
0x5e1ab  newarr   [mscorlib]System.Object
0x5e1b0  dup
0x5e1b1  ldc.i4.0
0x5e1b2  ldloc.s  6
0x5e1b4  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5e1b9  stelem.ref
0x5e1ba  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x5e1bf  leave.s  loc_5E1D4
0x5e1c1  ldloc.0
0x5e1c2  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x5e1c7  ldarg.0
0x5e1c8  ldfld    class [mscorlib]System.Threading.ManualResetEvent Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::_writeToCacheEvent
0x5e1cd  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Set()
0x5e1d2  pop
0x5e1d3  endfinally
0x5e1d4  ldloc.2
0x5e1d5  brfalse.s loc_5E1EF
0x5e1d7  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::Logger
0x5e1dc  ldsfld   string Microsoft.Crm.CustomMetricNames::LocatorCacheSyncSuccess
0x5e1e1  ldloc.1
0x5e1e2  ldloc.0
0x5e1e3  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x5e1e8  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryExtensions::LogMetric(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>, int64)
0x5e1ed  br.s     loc_5E205
0x5e1ef  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::Logger
0x5e1f4  ldsfld   string Microsoft.Crm.CustomMetricNames::LocatorCacheSyncFailure
0x5e1f9  ldloc.1
0x5e1fa  ldloc.0
0x5e1fb  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x5e200  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryExtensions::LogMetric(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>, int64)
0x5e205  ldarg.0
0x5e206  ldfld    class Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.ILocatorCacheSettingAccessor Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::_locatorCacheSettingAccessor
0x5e20b  callvirt instance class Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettings Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.ILocatorCacheSettingAccessor::get_Settings()
0x5e210  callvirt instance int32 Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettings::get_MaxJittererWaitInSec()
0x5e215  stloc.3
0x5e216  ldarg.0
0x5e217  ldfld    class Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.ILocatorCacheSettingAccessor Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::_locatorCacheSettingAccessor
0x5e21c  callvirt instance class Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettings Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.ILocatorCacheSettingAccessor::get_Settings()
0x5e221  callvirt instance int32 Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettings::get_RefreshIntervalInSec()
0x5e226  conv.r8
0x5e227  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x5e22c  ldsfld   class [mscorlib]System.Random Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::Jitterer
0x5e231  ldc.i4.0
0x5e232  ldloc.3
0x5e233  callvirt instance int32 [mscorlib]System.Random::Next(int32, int32)
0x5e238  conv.r8
0x5e239  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x5e23e  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::op_Addition(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x5e243  stloc.s  4
0x5e245  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::Logger
0x5e24a  ldstr    a0WaitingUntilN// "{0}: Waiting until next schedule cache "...
0x5e24f  ldc.i4.2
0x5e250  newarr   [mscorlib]System.Object
0x5e255  dup
0x5e256  ldc.i4.0
0x5e257  ldstr    aLocatorcachesy_4// "LocatorCacheSyncManager"
0x5e25c  stelem.ref
0x5e25d  dup
0x5e25e  ldc.i4.1
0x5e25f  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x5e264  ldloc.s  4
0x5e266  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x5e26b  box      [mscorlib]System.DateTime
0x5e270  stelem.ref
0x5e271  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogInformation(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x5e276  ldarga.s 1
0x5e278  call     instance class [mscorlib]System.Threading.WaitHandle [mscorlib]System.Threading.CancellationToken::get_WaitHandle()
0x5e27d  ldloc.s  4
0x5e27f  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne(valuetype [mscorlib]System.TimeSpan)
0x5e284  brtrue.s loc_5E292
0x5e286  ldarga.s 1
0x5e288  call     instance bool [mscorlib]System.Threading.CancellationToken::get_IsCancellationRequested()
0x5e28d  brfalse  loc_5E115
0x5e292  ret
```
