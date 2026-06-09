# Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.FileCacheAdapter::.ctor

- ea: `0x5e890`
- end: `0x5e8ec`
- name: `Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.FileCacheAdapter::.ctor`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1be80`
- `0x1beb0`
- `0x5e890`

## string_xrefs

- `0x5e897`: `serviceIdentifier`
- `0x5e8b1`: `Cache`
- `0x5e8d1`: `locator.cache`

## pseudocode

```c

```

## disassembly

```asm
0x5e890  ldarg.0
0x5e891  call     instance void [mscorlib]System.Object::.ctor()
0x5e896  ldarg.1
0x5e897  ldstr    aServiceidentif// "serviceIdentifier"
0x5e89c  call     void Microsoft.Crm.Exceptions::ThrowIfEmpty(string value, string parameterName)
0x5e8a1  ldarg.2
0x5e8a2  ldstr    aLogger// "logger"
0x5e8a7  call     void Microsoft.Crm.Exceptions::ThrowIfNull(object parameter, string name)
0x5e8ac  call     string [mscorlib]System.IO.Path::GetTempPath()
0x5e8b1  ldstr    aCache_0// "Cache"
0x5e8b6  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x5e8bb  ldarg.1
0x5e8bc  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x5e8c1  stloc.0
0x5e8c2  ldloc.0
0x5e8c3  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x5e8c8  brtrue.s loc_5E8D1
0x5e8ca  ldloc.0
0x5e8cb  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x5e8d0  pop
0x5e8d1  ldstr    aLocatorCache// "locator.cache"
0x5e8d6  stloc.1
0x5e8d7  ldarg.0
0x5e8d8  ldloc.0
0x5e8d9  ldloc.1
0x5e8da  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x5e8df  stfld    string Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.FileCacheAdapter::<CacheFilePath>k__BackingField
0x5e8e4  ldarg.0
0x5e8e5  ldarg.2
0x5e8e6  stfld    class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.FileCacheAdapter::_logger
0x5e8eb  ret
```
