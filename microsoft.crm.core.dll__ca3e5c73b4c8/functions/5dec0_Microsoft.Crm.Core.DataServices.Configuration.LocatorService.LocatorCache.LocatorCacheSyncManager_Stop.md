# Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::Stop

- ea: `0x5dec0`
- end: `0x5def7`
- name: `Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::Stop`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x5df00`

## string_xrefs

- `0x5dede`: `{0}: Cache synchronization job stopped.`
- `0x5deeb`: `LocatorCacheSyncManager`

## pseudocode

```c

```

## disassembly

```asm
0x5dec0  ldarg.0
0x5dec1  ldc.i4.0
0x5dec2  stfld    bool Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::_isExecuting
0x5dec7  ldarg.0
0x5dec8  ldfld    class [mscorlib]System.Threading.ManualResetEvent Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::_writeToCacheEvent
0x5decd  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Reset()
0x5ded2  pop
0x5ded3  ldarg.0
0x5ded4  call     instance void Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::Dispose()
0x5ded9  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::Logger
0x5dede  ldstr    a0CacheSynchron// "{0}: Cache synchronization job stopped."
0x5dee3  ldc.i4.1
0x5dee4  newarr   [mscorlib]System.Object
0x5dee9  dup
0x5deea  ldc.i4.0
0x5deeb  ldstr    aLocatorcachesy_4// "LocatorCacheSyncManager"
0x5def0  stelem.ref
0x5def1  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogInformation(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x5def6  ret
```
