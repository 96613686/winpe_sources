# Microsoft.Crm.LocatorCache::RemoveAll

- ea: `0x3610`
- end: `0x36aa`
- name: `Microsoft.Crm.LocatorCache::RemoveAll`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3760`

## callees

- `0x3610`
- `0x3c70`
- `0x3cc0`
- `0x5db20`
- `0x5dd90`
- `0x5de00`

## string_xrefs

- `0x3670`: `CrmConfigDb`
- `0x367b`: `CrmConfigDb`
- `0x3680`: `CrmConfigDb`

## pseudocode

```c

```

## disassembly

```asm
0x3610  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0x3615  stloc.0
0x3616  ldloc.0
0x3617  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x361c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x3621  stloc.1
0x3622  ldloc.1
0x3623  ldsfld   string Microsoft.Crm.CustomPropertyConstants::CrmServiceName
0x3628  call     string Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::get_ServiceIdentifier()
0x362d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x3632  ldloc.1
0x3633  ldsfld   string Microsoft.Crm.CustomPropertyConstants::LocatorCacheFlushType
0x3638  ldc.i4.0
0x3639  stloc.2
0x363a  ldloca.s 2
0x363c  constrained. Microsoft.Crm.LocatorCacheFlushType
0x3642  callvirt instance string [mscorlib]System.Object::ToString()
0x3647  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x364c  ldarg.0
0x364d  ldfld    class Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.ILocatorCacheSettingAccessor Microsoft.Crm.LocatorCache::_locatorCacheSettingAccessor
0x3652  callvirt instance class Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettings Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.ILocatorCacheSettingAccessor::get_Settings()
0x3657  callvirt instance bool Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettings::get_CacheFlushEnabled()
0x365c  stloc.3
0x365d  ldloc.1
0x365e  ldsfld   string Microsoft.Crm.CustomPropertyConstants::LocatorCacheFlushEnabled
0x3663  ldloca.s 3
0x3665  call     instance string [mscorlib]System.Boolean::ToString()
0x366a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x366f  ldarg.0
0x3670  ldstr    aCrmconfigdb// "CrmConfigDb"
0x3675  call     instance void Microsoft.Crm.LocatorCache::RemoveFromCache(string key)
0x367a  ldarg.0
0x367b  ldstr    aCrmconfigdb// "CrmConfigDb"
0x3680  ldstr    aCrmconfigdb// "CrmConfigDb"
0x3685  ldsfld   class [System.Runtime.Caching]System.Runtime.Caching.CacheItemPolicy Microsoft.Crm.LocatorCache::NotRemovablePolicy
0x368a  ldnull
0x368b  call     instance void Microsoft.Crm.LocatorCache::InsertIntoCache(string key, object value, class [System.Runtime.Caching]System.Runtime.Caching.CacheItemPolicy cacheItemPolicy, [opt] string[] dependencies)
0x3690  leave.s  loc_36A9
0x3692  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.LocatorCache::Logger
0x3697  ldsfld   string Microsoft.Crm.CustomMetricNames::LocatorCacheRemoveEntry
0x369c  ldloc.1
0x369d  ldloc.0
0x369e  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x36a3  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryExtensions::LogMetric(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>, int64)
0x36a8  endfinally
0x36a9  ret
```
