# <>c__DisplayClass5_0::<Get>b__0

- ea: `0x1cc0`
- end: `0x1d3d`
- name: `<>c__DisplayClass5_0::<Get>b__0`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1670`
- `0x1cc0`

## string_xrefs

- `0x1cc1`: `Creating cache entry for data source '`

## pseudocode

```c

```

## disassembly

```asm
0x1cc0  nop
0x1cc1  ldstr    aCreatingCacheE// "Creating cache entry for data source '"
0x1cc6  ldarg.0
0x1cc7  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata <>c__DisplayClass5_0::metadata
0x1ccc  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_ExternalName()
0x1cd1  ldstr    aMetadataId// "', metadata ID "
0x1cd6  ldarg.0
0x1cd7  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata <>c__DisplayClass5_0::metadata
0x1cdc  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase::get_MetadataId()
0x1ce1  stloc.1
0x1ce2  ldloca.s 1
0x1ce4  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x1ce9  stloc.2
0x1cea  ldloca.s 2
0x1cec  ldstr    aN// "N"
0x1cf1  call     instance string [mscorlib]System.Guid::ToString(string)
0x1cf6  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x1cfb  stloc.0
0x1cfc  ldarg.0
0x1cfd  ldfld    class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger <>c__DisplayClass5_0::logger
0x1d02  ldloc.0
0x1d03  ldc.i4.0
0x1d04  newarr   [mscorlib]System.Object
0x1d09  call     void [Microsoft.Xrm.Log]Microsoft.Xrm.Log.LoggerExtension::Debug(class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger, string, object[])
0x1d0e  nop
0x1d0f  ldarg.1
0x1d10  ldarg.0
0x1d11  ldfld    class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContextCache <>c__DisplayClass5_0::<>4__this
0x1d16  ldfld    class [Microsoft.Extensions.Caching.Abstractions]Microsoft.Extensions.Caching.Memory.MemoryCacheEntryOptions Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContextCache::cacheEntryOptions
0x1d1b  call     class [Microsoft.Extensions.Caching.Abstractions]Microsoft.Extensions.Caching.Memory.ICacheEntry [Microsoft.Extensions.Caching.Abstractions]Microsoft.Extensions.Caching.Memory.CacheEntryExtensions::SetOptions(class [Microsoft.Extensions.Caching.Abstractions]Microsoft.Extensions.Caching.Memory.ICacheEntry, class [Microsoft.Extensions.Caching.Abstractions]Microsoft.Extensions.Caching.Memory.MemoryCacheEntryOptions)
0x1d20  pop
0x1d21  ldarg.0
0x1d22  ldfld    class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.Interfaces.IJsonConverterContextFactory <>c__DisplayClass5_0::contextFactory
0x1d27  ldarg.0
0x1d28  ldfld    int32 <>c__DisplayClass5_0::hashCode
0x1d2d  ldarg.0
0x1d2e  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata <>c__DisplayClass5_0::metadata
0x1d33  callvirt instance class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContext Microsoft.Xrm.DataProvider.JsonConverter.Plugins.Interfaces.IJsonConverterContextFactory::CreateCachedData(int32 hashCode, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata metadata)
0x1d38  stloc.3
0x1d39  br.s     loc_1D3B
0x1d3b  ldloc.3
0x1d3c  ret
```
