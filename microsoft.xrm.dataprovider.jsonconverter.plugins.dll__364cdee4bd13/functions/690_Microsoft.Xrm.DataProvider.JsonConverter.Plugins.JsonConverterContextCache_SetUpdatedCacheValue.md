# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContextCache::SetUpdatedCacheValue

- ea: `0x690`
- end: `0x75c`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContextCache::SetUpdatedCacheValue`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x5e0`

## callees

- `0x520`
- `0x530`
- `0x690`
- `0x1670`

## string_xrefs

- `0x6f6`: `Creating new cache entry because metadata is outdated. Assembly name: `

## pseudocode

```c

```

## disassembly

```asm
0x690  nop
0x691  ldsfld   object Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContextCache::CacheLock
0x696  stloc.0
0x697  ldc.i4.0
0x698  stloc.1
0x699  ldloc.0
0x69a  ldloca.s 1
0x69c  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x6a1  nop
0x6a2  nop
0x6a3  ldarg.0
0x6a4  ldfld    class [Microsoft.Extensions.Caching.Memory]Microsoft.Extensions.Caching.Memory.MemoryCache Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContextCache::memCache
0x6a9  ldarg.2
0x6aa  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase::get_MetadataId()
0x6af  stloc.3
0x6b0  ldloca.s 3
0x6b2  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x6b7  box      [mscorlib]System.Guid
0x6bc  call     T0x2B000007
0x6c1  stloc.2
0x6c2  ldloc.2
0x6c3  brfalse.s loc_6D0
0x6c5  ldloc.2
0x6c6  callvirt instance int32 Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContext::get_MetadataHash()
0x6cb  ldarg.1
0x6cc  ceq
0x6ce  br.s     loc_6D1
0x6d0  ldc.i4.0
0x6d1  stloc.s  4
0x6d3  ldloc.s  4
0x6d5  brfalse.s loc_6DD
0x6d7  nop
0x6d8  ldloc.2
0x6d9  stloc.s  5
0x6db  leave.s  loc_759
0x6dd  ldloc.2
0x6de  brfalse.s loc_6EE
0x6e0  ldloc.2
0x6e1  callvirt instance class [mscorlib]System.Reflection.Assembly Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContext::get_EntityTypes()
0x6e6  ldnull
0x6e7  call     bool [mscorlib]System.Reflection.Assembly::op_Inequality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0x6ec  br.s     loc_6EF
0x6ee  ldc.i4.0
0x6ef  stloc.s  6
0x6f1  ldloc.s  6
0x6f3  brfalse.s loc_71E
0x6f5  nop
0x6f6  ldstr    aCreatingNewCac// "Creating new cache entry because metada"...
0x6fb  ldloc.2
0x6fc  callvirt instance class [mscorlib]System.Reflection.Assembly Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContext::get_EntityTypes()
0x701  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x706  call     string [mscorlib]System.String::Concat(string, string)
0x70b  stloc.s  7
0x70d  ldarg.s  4
0x70f  ldloc.s  7
0x711  ldc.i4.0
0x712  newarr   [mscorlib]System.Object
0x717  call     void [Microsoft.Xrm.Log]Microsoft.Xrm.Log.LoggerExtension::Debug(class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger, string, object[])
0x71c  nop
0x71d  nop
0x71e  ldarg.0
0x71f  ldfld    class [Microsoft.Extensions.Caching.Memory]Microsoft.Extensions.Caching.Memory.MemoryCache Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContextCache::memCache
0x724  ldarg.2
0x725  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase::get_MetadataId()
0x72a  stloc.3
0x72b  ldloca.s 3
0x72d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x732  box      [mscorlib]System.Guid
0x737  ldarg.3
0x738  ldarg.1
0x739  ldarg.2
0x73a  callvirt instance class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContext Microsoft.Xrm.DataProvider.JsonConverter.Plugins.Interfaces.IJsonConverterContextFactory::CreateCachedData(int32 hashCode, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata metadata)
0x73f  ldarg.0
0x740  ldfld    class [Microsoft.Extensions.Caching.Abstractions]Microsoft.Extensions.Caching.Memory.MemoryCacheEntryOptions Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContextCache::cacheEntryOptions
0x745  call     T0x2B000008
0x74a  stloc.s  5
0x74c  leave.s  loc_759
0x74e  ldloc.1
0x74f  brfalse.s loc_758
0x751  ldloc.0
0x752  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x757  nop
0x758  endfinally
0x759  ldloc.s  5
0x75b  ret
```
