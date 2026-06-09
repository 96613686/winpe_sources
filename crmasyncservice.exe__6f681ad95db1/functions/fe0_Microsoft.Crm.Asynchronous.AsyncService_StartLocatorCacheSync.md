# Microsoft.Crm.Asynchronous.AsyncService::StartLocatorCacheSync

- ea: `0xfe0`
- end: `0x103c`
- name: `Microsoft.Crm.Asynchronous.AsyncService::StartLocatorCacheSync`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xe20`

## string_xrefs

- `0xfe5`: `AsyncServiceLocatorCacheSync`

## pseudocode

```c

```

## disassembly

```asm
0xfe0  call     class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILoggerFactory [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmLoggerFactory::get_LoggerFactory()
0xfe5  ldstr    aAsyncservicelo// "AsyncServiceLocatorCacheSync"
0xfea  callvirt instance class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILoggerFactory::CreateLogger(string)
0xfef  stloc.0
0xff0  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xff5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Providers.ConfigDbLocatorCacheDataProvider::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService)
0xffa  stloc.1
0xffb  ldarg.0
0xffc  call     instance string [System.ServiceProcess]System.ServiceProcess.ServiceBase::get_ServiceName()
0x1001  ldloc.0
0x1002  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.FileCacheAdapter::.ctor(string, class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger)
0x1007  stloc.2
0x1008  ldarg.0
0x1009  call     instance string [System.ServiceProcess]System.ServiceProcess.ServiceBase::get_ServiceName()
0x100e  ldarg.0
0x100f  call     instance string [System.ServiceProcess]System.ServiceProcess.ServiceBase::get_ServiceName()
0x1014  call     class [Microsoft.Crm.Core]Microsoft.Crm.IRegistryDataProvider [Microsoft.Crm.Core]Microsoft.Crm.RegistryDataProvider::get_Instance()
0x1019  ldloc.0
0x101a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettingAccessor::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IRegistryDataProvider, class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger)
0x101f  stloc.3
0x1020  ldloc.2
0x1021  stloc.s  4
0x1023  ldloc.1
0x1024  ldloc.3
0x1025  ldloc.s  4
0x1027  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x102c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.ILocatorCacheAdapter [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Cache()
0x1031  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Providers.ILocatorCacheDataProvider, class [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.ILocatorCacheSettingAccessor, class [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.IPersistentLocatorCacheAdapter, class [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.ILocatorCacheAdapter)
0x1036  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::StartAndWait()
0x103b  ret
```
