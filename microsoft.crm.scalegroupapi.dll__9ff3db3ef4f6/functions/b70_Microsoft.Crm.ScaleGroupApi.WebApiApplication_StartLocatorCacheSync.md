# Microsoft.Crm.ScaleGroupApi.WebApiApplication::StartLocatorCacheSync

- ea: `0xb70`
- end: `0xbc1`
- name: `Microsoft.Crm.ScaleGroupApi.WebApiApplication::StartLocatorCacheSync`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xa70`

## string_xrefs

- `0xb70`: `SGAPICacheSyncProcess`

## pseudocode

```c

```

## disassembly

```asm
0xb70  ldstr    aSgapicachesync// "SGAPICacheSyncProcess"
0xb75  call     class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILoggerFactory [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmLoggerFactory::get_LoggerFactory()
0xb7a  ldstr    aSgapi// "SGAPI"
0xb7f  callvirt instance class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILoggerFactory::CreateLogger(string)
0xb84  stloc.0
0xb85  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xb8a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Providers.ConfigDbLocatorCacheDataProvider::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService)
0xb8f  stloc.1
0xb90  dup
0xb91  ldloc.0
0xb92  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.FileCacheAdapter::.ctor(string, class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger)
0xb97  stloc.2
0xb98  dup
0xb99  call     class [Microsoft.Crm.Core]Microsoft.Crm.IRegistryDataProvider [Microsoft.Crm.Core]Microsoft.Crm.RegistryDataProvider::get_Instance()
0xb9e  ldloc.0
0xb9f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettingAccessor::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IRegistryDataProvider, class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger)
0xba4  stloc.3
0xba5  ldloc.2
0xba6  stloc.s  4
0xba8  ldloc.1
0xba9  ldloc.3
0xbaa  ldloc.s  4
0xbac  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xbb1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.ILocatorCacheAdapter [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Cache()
0xbb6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Providers.ILocatorCacheDataProvider, class [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.ILocatorCacheSettingAccessor, class [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.IPersistentLocatorCacheAdapter, class [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.ILocatorCacheAdapter)
0xbbb  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::StartAndWait()
0xbc0  ret
```
