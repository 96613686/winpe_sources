# Microsoft.Crm.LocatorCache::.ctor_0

- ea: `0x31e0`
- end: `0x332d`
- name: `Microsoft.Crm.LocatorCache::.ctor_0`
- size: `333`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x31d0`
- `0x69d0`

## callees

- `0x31e0`
- `0x3bc0`
- `0x3c70`
- `0x13af0`
- `0x13e10`
- `0x17d50`
- `0x1ee00`
- `0x1ee10`
- `0x346c0`
- `0x5db40`

## string_xrefs

- `0x32dd`: `MSCRMLocatorService`
- `0x32f4`: `CrmConfigDb`
- `0x32f9`: `CrmConfigDb`
- `0x330a`: `LocatorCache`

## pseudocode

```c

```

## disassembly

```asm
0x31e0  ldarg.0
0x31e1  call     instance void [mscorlib]System.Object::.ctor()
0x31e6  call     bool Microsoft.Crm.CrmTrace::get_TraceDisabled()
0x31eb  stloc.0
0x31ec  ldloc.0
0x31ed  brtrue.s loc_31F5
0x31ef  ldloc.0
0x31f0  ldc.i4.0
0x31f1  ceq
0x31f3  br.s     loc_31F6
0x31f5  ldloc.0
0x31f6  call     void Microsoft.Crm.CrmTrace::set_TraceDisabled(bool value)
0x31fb  ldarg.0
0x31fc  ldftn    instance void Microsoft.Crm.LocatorCache::NotificationHandler(class Microsoft.Crm.NotificationEventArgs args)
0x3202  newobj   instance void Microsoft.Crm.NotificationEventHandler::.ctor(object object, native int method)
0x3207  stloc.1
0x3208  ldc.i4.s 0x16
0x320a  ldloc.1
0x320b  call     void Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype Microsoft.Crm.NotificationEventType eventId, class Microsoft.Crm.NotificationEventHandler eventHandler)
0x3210  ldc.i4.s 0x17
0x3212  ldloc.1
0x3213  call     void Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype Microsoft.Crm.NotificationEventType eventId, class Microsoft.Crm.NotificationEventHandler eventHandler)
0x3218  ldc.i4.s 0x18
0x321a  ldloc.1
0x321b  call     void Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype Microsoft.Crm.NotificationEventType eventId, class Microsoft.Crm.NotificationEventHandler eventHandler)
0x3220  ldc.i4.s 0x19
0x3222  ldloc.1
0x3223  call     void Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype Microsoft.Crm.NotificationEventType eventId, class Microsoft.Crm.NotificationEventHandler eventHandler)
0x3228  ldc.i4.s 0x1D
0x322a  ldloc.1
0x322b  call     void Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype Microsoft.Crm.NotificationEventType eventId, class Microsoft.Crm.NotificationEventHandler eventHandler)
0x3230  ldc.i4.s 0x1E
0x3232  ldloc.1
0x3233  call     void Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype Microsoft.Crm.NotificationEventType eventId, class Microsoft.Crm.NotificationEventHandler eventHandler)
0x3238  ldc.i4.s 0x1F
0x323a  ldloc.1
0x323b  call     void Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype Microsoft.Crm.NotificationEventType eventId, class Microsoft.Crm.NotificationEventHandler eventHandler)
0x3240  ldc.i4.s 0x20
0x3242  ldloc.1
0x3243  call     void Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype Microsoft.Crm.NotificationEventType eventId, class Microsoft.Crm.NotificationEventHandler eventHandler)
0x3248  ldc.i4.s 0x1A
0x324a  ldloc.1
0x324b  call     void Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype Microsoft.Crm.NotificationEventType eventId, class Microsoft.Crm.NotificationEventHandler eventHandler)
0x3250  ldc.i4.0
0x3251  ldloc.1
0x3252  call     void Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype Microsoft.Crm.NotificationEventType eventId, class Microsoft.Crm.NotificationEventHandler eventHandler)
0x3257  ldc.i4.s 0x26
0x3259  ldloc.1
0x325a  call     void Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype Microsoft.Crm.NotificationEventType eventId, class Microsoft.Crm.NotificationEventHandler eventHandler)
0x325f  ldc.i4.s 0x29
0x3261  ldloc.1
0x3262  call     void Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype Microsoft.Crm.NotificationEventType eventId, class Microsoft.Crm.NotificationEventHandler eventHandler)
0x3267  ldc.i4.2
0x3268  ldloc.1
0x3269  call     void Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype Microsoft.Crm.NotificationEventType eventId, class Microsoft.Crm.NotificationEventHandler eventHandler)
0x326e  ldc.i4.s 0x35
0x3270  ldloc.1
0x3271  call     void Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype Microsoft.Crm.NotificationEventType eventId, class Microsoft.Crm.NotificationEventHandler eventHandler)
0x3276  ldc.i4.s 0x36
0x3278  ldloc.1
0x3279  call     void Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype Microsoft.Crm.NotificationEventType eventId, class Microsoft.Crm.NotificationEventHandler eventHandler)
0x327e  ldc.i4.s 0x37
0x3280  ldloc.1
0x3281  call     void Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype Microsoft.Crm.NotificationEventType eventId, class Microsoft.Crm.NotificationEventHandler eventHandler)
0x3286  ldc.i4.s 0x38
0x3288  ldloc.1
0x3289  call     void Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype Microsoft.Crm.NotificationEventType eventId, class Microsoft.Crm.NotificationEventHandler eventHandler)
0x328e  ldc.i4.s 0x39
0x3290  ldloc.1
0x3291  call     void Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype Microsoft.Crm.NotificationEventType eventId, class Microsoft.Crm.NotificationEventHandler eventHandler)
0x3296  ldc.i4.s 0x3A
0x3298  ldloc.1
0x3299  call     void Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype Microsoft.Crm.NotificationEventType eventId, class Microsoft.Crm.NotificationEventHandler eventHandler)
0x329e  ldc.i4.s 0x43
0x32a0  ldloc.1
0x32a1  call     void Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype Microsoft.Crm.NotificationEventType eventId, class Microsoft.Crm.NotificationEventHandler eventHandler)
0x32a6  ldc.i4.s 0x45
0x32a8  ldloc.1
0x32a9  call     void Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype Microsoft.Crm.NotificationEventType eventId, class Microsoft.Crm.NotificationEventHandler eventHandler)
0x32ae  ldc.i4.s 0x62
0x32b0  ldloc.1
0x32b1  call     void Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype Microsoft.Crm.NotificationEventType eventId, class Microsoft.Crm.NotificationEventHandler eventHandler)
0x32b6  ldc.i4.s 0x6C
0x32b8  ldloc.1
0x32b9  call     void Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype Microsoft.Crm.NotificationEventType eventId, class Microsoft.Crm.NotificationEventHandler eventHandler)
0x32be  ldc.i4   0x84
0x32c3  ldloc.1
0x32c4  call     void Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype Microsoft.Crm.NotificationEventType eventId, class Microsoft.Crm.NotificationEventHandler eventHandler)
0x32c9  ldarg.0
0x32ca  ldarg.1
0x32cb  stfld    valuetype Microsoft.Crm.LocatorServiceContext Microsoft.Crm.LocatorCache::_locatorServiceContext
0x32d0  ldarg.0
0x32d1  call     instance void Microsoft.Crm.LocatorCache::CreatePerformanceCounters()
0x32d6  newobj   instance void [System]System.Diagnostics.EventLog::.ctor()
0x32db  stloc.2
0x32dc  ldloc.2
0x32dd  ldstr    aMscrmlocatorse// "MSCRMLocatorService"
0x32e2  callvirt instance void [System]System.Diagnostics.EventLog::set_Source(string)
0x32e7  ldarg.0
0x32e8  ldloc.2
0x32e9  newobj   instance void Microsoft.Crm.CrmEventLog::.ctor(class [System]System.Diagnostics.EventLog eventLog)
0x32ee  stfld    class Microsoft.Crm.CrmEventLog Microsoft.Crm.LocatorCache::_eventLog
0x32f3  ldarg.0
0x32f4  ldstr    aCrmconfigdb// "CrmConfigDb"
0x32f9  ldstr    aCrmconfigdb// "CrmConfigDb"
0x32fe  ldsfld   class [System.Runtime.Caching]System.Runtime.Caching.CacheItemPolicy Microsoft.Crm.LocatorCache::NotRemovablePolicy
0x3303  ldnull
0x3304  call     instance void Microsoft.Crm.LocatorCache::InsertIntoCache(string key, object value, class [System.Runtime.Caching]System.Runtime.Caching.CacheItemPolicy cacheItemPolicy, [opt] string[] dependencies)
0x3309  ldarg.0
0x330a  ldstr    aLocatorcache// "LocatorCache"
0x330f  call     class Microsoft.Crm.IRegistryDataProvider Microsoft.Crm.RegistryDataProvider::get_Instance()
0x3314  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.LocatorCache::Logger
0x3319  newobj   instance void Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettingAccessor::.ctor(string serviceIdentifier, class Microsoft.Crm.IRegistryDataProvider registryDataProvider, class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger logger)
0x331e  stfld    class Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.ILocatorCacheSettingAccessor Microsoft.Crm.LocatorCache::_locatorCacheSettingAccessor
0x3323  leave.s  loc_332C
0x3325  ldloc.0
0x3326  call     void Microsoft.Crm.CrmTrace::set_TraceDisabled(bool value)
0x332b  endfinally
0x332c  ret
```
