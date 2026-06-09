# Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.FileCacheAdapter::ReadAll

- ea: `0x5e9b0`
- end: `0x5ea85`
- name: `Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.FileCacheAdapter::ReadAll`
- size: `213`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x5e880`
- `0x5e9b0`

## string_xrefs

- `0x5ea04`: `Exception while deserializing to cache file located at '{0}': {1}`
- `0x5ea31`: `Security exception while attempting to access the cache file located at '{0}': {1}`
- `0x5ea5c`: `Could not find locator cache file {0}`

## pseudocode

```c

```

## disassembly

```asm
0x5e9b0  ldsfld   object Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.FileCacheAdapter::FileLock
0x5e9b5  stloc.0
0x5e9b6  ldc.i4.0
0x5e9b7  stloc.1
0x5e9b8  ldloc.0
0x5e9b9  ldloca.s 1
0x5e9bb  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x5e9c0  ldarg.0
0x5e9c1  call     instance string Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.FileCacheAdapter::get_CacheFilePath()
0x5e9c6  call     bool [mscorlib]System.IO.File::Exists(string)
0x5e9cb  brfalse  loc_5EA56
0x5e9d0  ldarg.0
0x5e9d1  call     instance string Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.FileCacheAdapter::get_CacheFilePath()
0x5e9d6  call     class [mscorlib]System.IO.FileStream [mscorlib]System.IO.File::OpenRead(string)
0x5e9db  stloc.2
0x5e9dc  newobj   instance void [mscorlib]System.Runtime.Serialization.Formatters.Binary.BinaryFormatter::.ctor()
0x5e9e1  ldloc.2
0x5e9e2  callvirt instance object [mscorlib]System.Runtime.Serialization.Formatters.Binary.BinaryFormatter::Deserialize(class [mscorlib]System.IO.Stream)
0x5e9e7  castclass Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.ILocatorCacheEntryCollection
0x5e9ec  stloc.3
0x5e9ed  leave    loc_5EA83
0x5e9f2  ldloc.2
0x5e9f3  brfalse.s loc_5E9FB
0x5e9f5  ldloc.2
0x5e9f6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5e9fb  endfinally
0x5e9fc  stloc.s  4
0x5e9fe  ldarg.0
0x5e9ff  ldfld    class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.FileCacheAdapter::_logger
0x5ea04  ldstr    aExceptionWhile_1// "Exception while deserializing to cache "...
0x5ea09  ldc.i4.2
0x5ea0a  newarr   [mscorlib]System.Object
0x5ea0f  dup
0x5ea10  ldc.i4.0
0x5ea11  ldarg.0
0x5ea12  call     instance string Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.FileCacheAdapter::get_CacheFilePath()
0x5ea17  stelem.ref
0x5ea18  dup
0x5ea19  ldc.i4.1
0x5ea1a  ldloc.s  4
0x5ea1c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5ea21  stelem.ref
0x5ea22  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogError(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x5ea27  leave.s  loc_5EA75
0x5ea29  stloc.s  5
0x5ea2b  ldarg.0
0x5ea2c  ldfld    class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.FileCacheAdapter::_logger
0x5ea31  ldstr    aSecurityExcept// "Security exception while attempting to "...
0x5ea36  ldc.i4.2
0x5ea37  newarr   [mscorlib]System.Object
0x5ea3c  dup
0x5ea3d  ldc.i4.0
0x5ea3e  ldarg.0
0x5ea3f  call     instance string Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.FileCacheAdapter::get_CacheFilePath()
0x5ea44  stelem.ref
0x5ea45  dup
0x5ea46  ldc.i4.1
0x5ea47  ldloc.s  5
0x5ea49  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5ea4e  stelem.ref
0x5ea4f  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogError(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x5ea54  leave.s  loc_5EA75
0x5ea56  ldarg.0
0x5ea57  ldfld    class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.FileCacheAdapter::_logger
0x5ea5c  ldstr    aCouldNotFindLo// "Could not find locator cache file {0}"
0x5ea61  ldc.i4.1
0x5ea62  newarr   [mscorlib]System.Object
0x5ea67  dup
0x5ea68  ldc.i4.0
0x5ea69  ldarg.0
0x5ea6a  call     instance string Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.Adapters.FileCacheAdapter::get_CacheFilePath()
0x5ea6f  stelem.ref
0x5ea70  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogWarning(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x5ea75  ldnull
0x5ea76  stloc.3
0x5ea77  leave.s  loc_5EA83
0x5ea79  ldloc.1
0x5ea7a  brfalse.s loc_5EA82
0x5ea7c  ldloc.0
0x5ea7d  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x5ea82  endfinally
0x5ea83  ldloc.3
0x5ea84  ret
```
