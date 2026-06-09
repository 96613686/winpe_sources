# Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettingAccessor::.ctor

- ea: `0x5db40`
- end: `0x5db7d`
- name: `Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettingAccessor::.ctor`
- size: `61`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x31e0`
- `0x69d0`

## callees

- `0x1be80`
- `0x1beb0`

## string_xrefs

- `0x5db52`: `registryDataProvider`
- `0x5db47`: `serviceIdentifier`

## pseudocode

```c

```

## disassembly

```asm
0x5db40  ldarg.0
0x5db41  call     instance void [mscorlib]System.Object::.ctor()
0x5db46  ldarg.1
0x5db47  ldstr    aServiceidentif// "serviceIdentifier"
0x5db4c  call     void Microsoft.Crm.Exceptions::ThrowIfEmpty(string value, string parameterName)
0x5db51  ldarg.2
0x5db52  ldstr    aRegistrydatapr// "registryDataProvider"
0x5db57  call     void Microsoft.Crm.Exceptions::ThrowIfNull(object parameter, string name)
0x5db5c  ldarg.3
0x5db5d  ldstr    aLogger// "logger"
0x5db62  call     void Microsoft.Crm.Exceptions::ThrowIfNull(object parameter, string name)
0x5db67  ldarg.0
0x5db68  ldarg.2
0x5db69  stfld    class Microsoft.Crm.IRegistryDataProvider Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettingAccessor::_registryDataProvider
0x5db6e  ldarg.0
0x5db6f  ldarg.1
0x5db70  stfld    string Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettingAccessor::_serviceIdentifier
0x5db75  ldarg.0
0x5db76  ldarg.3
0x5db77  stfld    class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettingAccessor::_logger
0x5db7c  ret
```
