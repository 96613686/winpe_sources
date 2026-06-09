# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterClassTypeFactoryFactory::Create

- ea: `0x4c0`
- end: `0x4d3`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterClassTypeFactoryFactory::Create`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x780`

## callees

- `0x4c0`

## pseudocode

```c

```

## disassembly

```asm
0x4c0  nop
0x4c1  ldarg.0
0x4c2  newobj   instance void [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.DefaultTypeMapFactory::.ctor()
0x4c7  newobj   instance void [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.CodeGen.ClassTypeFactory::.ctor(class [mscorlib]System.Reflection.Emit.ModuleBuilder, class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.ITypeMapFactory)
0x4cc  stloc.0
0x4cd  ldloc.0
0x4ce  stloc.1
0x4cf  br.s     loc_4D1
0x4d1  ldloc.1
0x4d2  ret
```
