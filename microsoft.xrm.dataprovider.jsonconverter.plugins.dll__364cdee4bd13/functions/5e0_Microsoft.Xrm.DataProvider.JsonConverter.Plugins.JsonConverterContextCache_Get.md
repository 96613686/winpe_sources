# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContextCache::Get

- ea: `0x5e0`
- end: `0x682`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContextCache::Get`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x520`
- `0x5e0`
- `0x690`
- `0x1cb0`

## pseudocode

```c

```

## disassembly

```asm
0x5e0  newobj   instance void <>c__DisplayClass5_0::.ctor()
0x5e5  stloc.0
0x5e6  ldloc.0
0x5e7  ldarg.1
0x5e8  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata <>c__DisplayClass5_0::metadata
0x5ed  ldloc.0
0x5ee  ldarg.3
0x5ef  stfld    class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger <>c__DisplayClass5_0::logger
0x5f4  ldloc.0
0x5f5  ldarg.0
0x5f6  stfld    class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContextCache <>c__DisplayClass5_0::<>4__this
0x5fb  ldloc.0
0x5fc  ldarg.2
0x5fd  stfld    class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.Interfaces.IJsonConverterContextFactory <>c__DisplayClass5_0::contextFactory
0x602  nop
0x603  ldloc.0
0x604  ldloc.0
0x605  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata <>c__DisplayClass5_0::metadata
0x60a  call     int32 [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.TypeHashUtil::HashEntityMetadata(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata)
0x60f  stfld    int32 <>c__DisplayClass5_0::hashCode
0x614  ldarg.0
0x615  ldfld    class [Microsoft.Extensions.Caching.Memory]Microsoft.Extensions.Caching.Memory.MemoryCache Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContextCache::memCache
0x61a  ldloc.0
0x61b  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata <>c__DisplayClass5_0::metadata
0x620  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase::get_MetadataId()
0x625  stloc.2
0x626  ldloca.s 2
0x628  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x62d  box      [mscorlib]System.Guid
0x632  ldloc.0
0x633  ldftn    instance class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContext <>c__DisplayClass5_0::<Get>b__0(class [Microsoft.Extensions.Caching.Abstractions]Microsoft.Extensions.Caching.Memory.ICacheEntry entry)
0x639  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Extensions.Caching.Abstractions]Microsoft.Extensions.Caching.Memory.ICacheEntry, class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContext>::.ctor(object, native int)
0x63e  call     T0x2B000006
0x643  stloc.1
0x644  ldloc.1
0x645  callvirt instance int32 Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContext::get_MetadataHash()
0x64a  ldloc.0
0x64b  ldfld    int32 <>c__DisplayClass5_0::hashCode
0x650  ceq
0x652  stloc.3
0x653  ldloc.3
0x654  brfalse.s loc_65C
0x656  nop
0x657  ldloc.1
0x658  stloc.s  4
0x65a  br.s     loc_67F
0x65c  nop
0x65d  ldarg.0
0x65e  ldloc.0
0x65f  ldfld    int32 <>c__DisplayClass5_0::hashCode
0x664  ldloc.0
0x665  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata <>c__DisplayClass5_0::metadata
0x66a  ldloc.0
0x66b  ldfld    class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.Interfaces.IJsonConverterContextFactory <>c__DisplayClass5_0::contextFactory
0x670  ldloc.0
0x671  ldfld    class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger <>c__DisplayClass5_0::logger
0x676  call     instance class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContext Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContextCache::SetUpdatedCacheValue(int32 hashCode, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata metadata, class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.Interfaces.IJsonConverterContextFactory contextFactory, class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger logger)
0x67b  stloc.s  4
0x67d  br.s     loc_67F
0x67f  ldloc.s  4
0x681  ret
```
