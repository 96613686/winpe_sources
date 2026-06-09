# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContextFactory::CreateCachedData

- ea: `0x780`
- end: `0x7de`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContextFactory::CreateCachedData`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x4c0`
- `0x500`
- `0x780`

## string_xrefs

- `0x781`: `Microsoft.Xrm.DataProvider.Json.Generated.`

## pseudocode

```c

```

## disassembly

```asm
0x780  nop
0x781  ldstr    aMicrosoftXrmDa_1// "Microsoft.Xrm.DataProvider.Json.Generat"...
0x786  ldarg.2
0x787  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase::get_MetadataId()
0x78c  stloc.s  4
0x78e  ldloca.s 4
0x790  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x795  stloc.s  5
0x797  ldloca.s 5
0x799  ldstr    aN// "N"
0x79e  call     instance string [mscorlib]System.Guid::ToString(string)
0x7a3  call     string [mscorlib]System.String::Concat(string, string)
0x7a8  stloc.0
0x7a9  ldc.i4.1
0x7aa  stloc.1
0x7ab  ldloc.0
0x7ac  ldloc.1
0x7ad  call     class [mscorlib]System.Reflection.Emit.ModuleBuilder [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.CodeGen.ModuleBuilderFactory::Create(string, int32)
0x7b2  stloc.2
0x7b3  ldloc.2
0x7b4  call     class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.CodeGen.ClassTypeFactory Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterClassTypeFactoryFactory::Create(class [mscorlib]System.Reflection.Emit.ModuleBuilder moduleBuilder)
0x7b9  stloc.3
0x7ba  ldloc.3
0x7bb  ldc.i4.1
0x7bc  newarr   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata
0x7c1  dup
0x7c2  ldc.i4.0
0x7c3  ldarg.2
0x7c4  stelem.ref
0x7c5  callvirt instance void [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.CodeGen.ClassTypeFactory::Create(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata>)
0x7ca  nop
0x7cb  ldloc.2
0x7cc  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Module::get_Assembly()
0x7d1  ldarg.1
0x7d2  newobj   instance void Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterContext::.ctor(class [mscorlib]System.Reflection.Assembly entityTypes, int32 hash)
0x7d7  stloc.s  6
0x7d9  br.s     loc_7DB
0x7db  ldloc.s  6
0x7dd  ret
```
