# Microsoft.Crm.CrmPluginAssemblyMetadata::GetPluginTypeMetadata_0

- ea: `0x1e4a0`
- end: `0x1e4ec`
- name: `Microsoft.Crm.CrmPluginAssemblyMetadata::GetPluginTypeMetadata_0`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1e4f0`

## callees

- `0x1e4a0`
- `0x1f250`
- `0x1f290`

## string_xrefs

- `0x1e4c9`: `GetPluginTypeMetadata/TypeName`

## pseudocode

```c

```

## disassembly

```asm
0x1e4a0  ldnull
0x1e4a1  stloc.0
0x1e4a2  ldarg.0
0x1e4a3  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<unsigned int32, class Microsoft.Crm.CrmPluginTypeMetadata> Microsoft.Crm.CrmPluginAssemblyMetadata::_processedTypes
0x1e4a8  ldarg.1
0x1e4a9  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<unsigned int32, class Microsoft.Crm.CrmPluginTypeMetadata>::ContainsKey(var<u1>)
0x1e4ae  brfalse.s loc_1E4D5
0x1e4b0  ldarg.0
0x1e4b1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<unsigned int32, class Microsoft.Crm.CrmPluginTypeMetadata> Microsoft.Crm.CrmPluginAssemblyMetadata::_processedTypes
0x1e4b6  ldarg.1
0x1e4b7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<unsigned int32, class Microsoft.Crm.CrmPluginTypeMetadata>::get_Item(void)
0x1e4bc  stloc.0
0x1e4bd  ldloc.0
0x1e4be  callvirt instance string Microsoft.Crm.CrmPluginTypeMetadata::get_TypeName()
0x1e4c3  ldarg.2
0x1e4c4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e4c9  ldstr    aGetplugintypem// "GetPluginTypeMetadata/TypeName"
0x1e4ce  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1e4d3  ldloc.0
0x1e4d4  ret
0x1e4d5  ldarg.1
0x1e4d6  ldarg.2
0x1e4d7  newobj   instance void Microsoft.Crm.CrmPluginTypeMetadata::.ctor(unsigned int32 typeDef, string typeName)
0x1e4dc  stloc.0
0x1e4dd  ldarg.0
0x1e4de  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<unsigned int32, class Microsoft.Crm.CrmPluginTypeMetadata> Microsoft.Crm.CrmPluginAssemblyMetadata::_processedTypes
0x1e4e3  ldarg.1
0x1e4e4  ldloc.0
0x1e4e5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<unsigned int32, class Microsoft.Crm.CrmPluginTypeMetadata>::Add(var<u1>, !!T0)
0x1e4ea  ldloc.0
0x1e4eb  ret
```
