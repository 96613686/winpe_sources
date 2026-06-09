# Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::TryPopulateCacheFromPersistentStore

- ea: `0x5df20`
- end: `0x5dfa9`
- name: `Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::TryPopulateCacheFromPersistentStore`
- size: `137`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x5dfb0`
- `0x5e2a0`

## callees

- `0x5df20`
- `0x5e310`
- `0x5eae0`

## string_xrefs

- `0x5df50`: `LocatorCacheSyncManager`
- `0x5df43`: `{0}: Wrote values to cache type '{1}'`
- `0x5df72`: `No cache items found in persistent store.`
- `0x5df8a`: `Non-terminal failure while retrieving cache values from persistent store: {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x5df20  ldarg.0
0x5df21  call     instance class Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.ILocatorCacheEntryCollection Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::GetCacheItemsFromPersistentStore()
0x5df26  stloc.0
0x5df27  ldloc.0
0x5df28  brfalse.s loc_5DF6D
0x5df2a  ldloc.0
0x5df2b  call     T0x2B000107
0x5df30  brfalse.s loc_5DF6D
0x5df32  ldarg.0
0x5df33  ldfld    class Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.ILocatorCacheAdapter Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::_volatileCacheAdapter
0x5df38  ldloc.0
0x5df39  callvirt instance void Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.ILocatorCacheAdapter::WriteToCache(class Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.ILocatorCacheEntryCollection cacheItems)
0x5df3e  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::Logger
0x5df43  ldstr    a0WroteValuesTo// "{0}: Wrote values to cache type '{1}'"
0x5df48  ldc.i4.2
0x5df49  newarr   [mscorlib]System.Object
0x5df4e  dup
0x5df4f  ldc.i4.0
0x5df50  ldstr    aLocatorcachesy_4// "LocatorCacheSyncManager"
0x5df55  stelem.ref
0x5df56  dup
0x5df57  ldc.i4.1
0x5df58  ldarg.0
0x5df59  ldfld    class Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.IPersistentLocatorCacheAdapter Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::_persistentCacheAdapter
0x5df5e  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x5df63  stelem.ref
0x5df64  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogInformation(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x5df69  ldc.i4.1
0x5df6a  stloc.1
0x5df6b  leave.s  loc_5DFA7
0x5df6d  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::Logger
0x5df72  ldstr    aNoCacheItemsFo// "No cache items found in persistent stor"...
0x5df77  ldc.i4.0
0x5df78  newarr   [mscorlib]System.Object
0x5df7d  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogInformation(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x5df82  leave.s  loc_5DFA5
0x5df84  stloc.2
0x5df85  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::Logger
0x5df8a  ldstr    aNonTerminalFai// "Non-terminal failure while retrieving c"...
0x5df8f  ldc.i4.1
0x5df90  newarr   [mscorlib]System.Object
0x5df95  dup
0x5df96  ldc.i4.0
0x5df97  ldloc.2
0x5df98  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5df9d  stelem.ref
0x5df9e  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogError(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x5dfa3  leave.s  loc_5DFA5
0x5dfa5  ldc.i4.0
0x5dfa6  ret
0x5dfa7  ldloc.1
0x5dfa8  ret
```
