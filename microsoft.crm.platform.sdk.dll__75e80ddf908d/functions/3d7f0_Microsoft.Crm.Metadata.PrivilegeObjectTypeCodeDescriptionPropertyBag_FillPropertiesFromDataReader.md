# Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescriptionPropertyBag::FillPropertiesFromDataReader

- ea: `0x3d7f0`
- end: `0x3d877`
- name: `Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescriptionPropertyBag::FillPropertiesFromDataReader`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x3d2a0`
- `0x3d550`
- `0x3d570`
- `0x3d7f0`

## string_xrefs

- `0x3d840`: `ComponentState`
- `0x3d858`: `ComponentState`

## pseudocode

```c

```

## disassembly

```asm
0x3d7f0  ldarg.0
0x3d7f1  ldarg.1
0x3d7f2  ldarg.2
0x3d7f3  call     instance void Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescription::FillPropertiesFromDataReader(class [System.Data]System.Data.IDataReader reader, [opt] class Microsoft.Crm.Metadata.MetadataForMetadata metadataForMetadata)
0x3d7f8  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x3d7fd  stloc.0
0x3d7fe  ldc.i4.0
0x3d7ff  stloc.1
0x3d800  br.s     loc_3D813
0x3d802  ldloc.0
0x3d803  ldarg.1
0x3d804  ldloc.1
0x3d805  callvirt instance string [System.Data]System.Data.IDataRecord::GetName(int32)
0x3d80a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3d80f  ldloc.1
0x3d810  ldc.i4.1
0x3d811  add
0x3d812  stloc.1
0x3d813  ldloc.1
0x3d814  ldarg.1
0x3d815  callvirt instance int32 [System.Data]System.Data.IDataRecord::get_FieldCount()
0x3d81a  blt.s    loc_3D802
0x3d81c  ldloc.0
0x3d81d  ldstr    aSolutionid// "SolutionId"
0x3d822  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x3d827  brfalse.s loc_3D83F
0x3d829  ldarg.0
0x3d82a  ldarg.1
0x3d82b  ldstr    aSolutionid// "SolutionId"
0x3d830  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3d835  unbox.any [mscorlib]System.Guid
0x3d83a  callvirt instance void Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescription::set_SolutionId(valuetype [mscorlib]System.Guid value)
0x3d83f  ldloc.0
0x3d840  ldstr    aComponentstate_0// "ComponentState"
0x3d845  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x3d84a  brfalse.s loc_3D876
0x3d84c  ldarg.0
0x3d84d  ldtoken  Microsoft.Crm.Platform.ComponentState
0x3d852  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d857  ldarg.1
0x3d858  ldstr    aComponentstate_0// "ComponentState"
0x3d85d  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3d862  callvirt instance string [mscorlib]System.Object::ToString()
0x3d867  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x3d86c  unbox.any Microsoft.Crm.Platform.ComponentState
0x3d871  callvirt instance void Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescription::set_ComponentState(valuetype Microsoft.Crm.Platform.ComponentState value)
0x3d876  ret
```
