# Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::.ctor

- ea: `0x5de20`
- end: `0x5de93`
- name: `Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::.ctor`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x5de10`
- `0x5de20`

## string_xrefs

- `0x5de2c`: `locatorCacheSettingAccessor`
- `0x5de43`: `locatorCacheAdapter`
- `0x5de5a`: `persistentCacheAccessor`
- `0x5de70`: `locatorCacheDataProvider`

## pseudocode

```c

```

## disassembly

```asm
0x5de20  ldarg.0
0x5de21  call     instance void [mscorlib]System.Object::.ctor()
0x5de26  ldarg.0
0x5de27  ldarg.3
0x5de28  dup
0x5de29  brtrue.s loc_5DE37
0x5de2b  pop
0x5de2c  ldstr    aLocatorcachese_0// "locatorCacheSettingAccessor"
0x5de31  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5de36  throw
0x5de37  stfld    class Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.ILocatorCacheSettingAccessor Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::_locatorCacheSettingAccessor
0x5de3c  ldarg.0
0x5de3d  ldarg.s  5
0x5de3f  dup
0x5de40  brtrue.s loc_5DE4E
0x5de42  pop
0x5de43  ldstr    aLocatorcachead// "locatorCacheAdapter"
0x5de48  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5de4d  throw
0x5de4e  stfld    class Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.ILocatorCacheAdapter Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::_volatileCacheAdapter
0x5de53  ldarg.0
0x5de54  ldarg.s  4
0x5de56  dup
0x5de57  brtrue.s loc_5DE65
0x5de59  pop
0x5de5a  ldstr    aPersistentcach// "persistentCacheAccessor"
0x5de5f  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5de64  throw
0x5de65  stfld    class Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.IPersistentLocatorCacheAdapter Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::_persistentCacheAdapter
0x5de6a  ldarg.0
0x5de6b  ldarg.2
0x5de6c  dup
0x5de6d  brtrue.s loc_5DE7B
0x5de6f  pop
0x5de70  ldstr    aLocatorcacheda_0// "locatorCacheDataProvider"
0x5de75  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5de7a  throw
0x5de7b  stfld    class Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Providers.ILocatorCacheDataProvider Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::_locatorCacheDataProvider
0x5de80  ldarg.1
0x5de81  call     void Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::set_ServiceIdentifier(string value)
0x5de86  ldarg.0
0x5de87  ldc.i4.0
0x5de88  newobj   instance void [mscorlib]System.Threading.ManualResetEvent::.ctor(bool)
0x5de8d  stfld    class [mscorlib]System.Threading.ManualResetEvent Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::_writeToCacheEvent
0x5de92  ret
```
