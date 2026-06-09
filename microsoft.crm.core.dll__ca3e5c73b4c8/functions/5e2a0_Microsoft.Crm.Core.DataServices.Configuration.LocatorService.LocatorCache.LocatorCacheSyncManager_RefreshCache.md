# Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::RefreshCacheValues

- ea: `0x5e2a0`
- end: `0x5e303`
- name: `Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::RefreshCacheValues`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x5e110`

## callees

- `0x1eaa0`
- `0x1f510`
- `0x5df20`
- `0x5e2a0`
- `0x5e3d0`
- `0x5eae0`

## string_xrefs

- `0x5e2b2`: `LocatorCacheSyncManager`
- `0x5e2a5`: `{0}: Running cache refresh...`
- `0x5e2e0`: `Error while retrieving config values for Locator Cache Items: {0}\n Attempting to read from persistent cache...`

## pseudocode

```c

```

## disassembly

```asm
0x5e2a0  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::Logger
0x5e2a5  ldstr    a0RunningCacheR// "{0}: Running cache refresh..."
0x5e2aa  ldc.i4.1
0x5e2ab  newarr   [mscorlib]System.Object
0x5e2b0  dup
0x5e2b1  ldc.i4.0
0x5e2b2  ldstr    aLocatorcachesy_4// "LocatorCacheSyncManager"
0x5e2b7  stelem.ref
0x5e2b8  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogInformation(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x5e2bd  ldarg.0
0x5e2be  ldfld    class Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Providers.ILocatorCacheDataProvider Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::_locatorCacheDataProvider
0x5e2c3  callvirt instance class Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.ILocatorCacheEntryCollection Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Providers.ILocatorCacheDataProvider::RetrieveCacheItems()
0x5e2c8  stloc.0
0x5e2c9  ldarg.0
0x5e2ca  ldfld    class Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.IPersistentLocatorCacheAdapter Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::_persistentCacheAdapter
0x5e2cf  ldloc.0
0x5e2d0  callvirt instance void Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.ILocatorCacheAdapter::WriteToCache(class Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.ILocatorCacheEntryCollection cacheItems)
0x5e2d5  leave.s  loc_5E2FB
0x5e2d7  stloc.1
0x5e2d8  ldloc.1
0x5e2d9  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x5e2de  ldc.i4.s 0x14
0x5e2e0  ldstr    aErrorWhileRetr// "Error while retrieving config values fo"...
0x5e2e5  ldc.i4.1
0x5e2e6  newarr   [mscorlib]System.Object
0x5e2eb  dup
0x5e2ec  ldc.i4.0
0x5e2ed  ldloc.1
0x5e2ee  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5e2f3  stelem.ref
0x5e2f4  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x5e2f9  leave.s  loc_5E2FB
0x5e2fb  ldarg.0
0x5e2fc  call     instance bool Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::TryPopulateCacheFromPersistentStore()
0x5e301  pop
0x5e302  ret
```
