# Microsoft.Crm.Metadata.PrivilegeDescriptionPropertyBag::FillPropertiesFromDataReader

- ea: `0x3cb90`
- end: `0x3cc17`
- name: `Microsoft.Crm.Metadata.PrivilegeDescriptionPropertyBag::FillPropertiesFromDataReader`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x3bf10`
- `0x3c7a0`
- `0x3c7c0`
- `0x3cb90`

## string_xrefs

- `0x3cbe0`: `ComponentState`
- `0x3cbf8`: `ComponentState`

## pseudocode

```c

```

## disassembly

```asm
0x3cb90  ldarg.0
0x3cb91  ldarg.1
0x3cb92  ldarg.2
0x3cb93  call     instance void Microsoft.Crm.Metadata.PrivilegeDescription::FillPropertiesFromDataReader(class [System.Data]System.Data.IDataReader reader, [opt] class Microsoft.Crm.Metadata.MetadataForMetadata metadataForMetadata)
0x3cb98  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x3cb9d  stloc.0
0x3cb9e  ldc.i4.0
0x3cb9f  stloc.1
0x3cba0  br.s     loc_3CBB3
0x3cba2  ldloc.0
0x3cba3  ldarg.1
0x3cba4  ldloc.1
0x3cba5  callvirt instance string [System.Data]System.Data.IDataRecord::GetName(int32)
0x3cbaa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3cbaf  ldloc.1
0x3cbb0  ldc.i4.1
0x3cbb1  add
0x3cbb2  stloc.1
0x3cbb3  ldloc.1
0x3cbb4  ldarg.1
0x3cbb5  callvirt instance int32 [System.Data]System.Data.IDataRecord::get_FieldCount()
0x3cbba  blt.s    loc_3CBA2
0x3cbbc  ldloc.0
0x3cbbd  ldstr    aSolutionid// "SolutionId"
0x3cbc2  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x3cbc7  brfalse.s loc_3CBDF
0x3cbc9  ldarg.0
0x3cbca  ldarg.1
0x3cbcb  ldstr    aSolutionid// "SolutionId"
0x3cbd0  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3cbd5  unbox.any [mscorlib]System.Guid
0x3cbda  callvirt instance void Microsoft.Crm.Metadata.PrivilegeDescription::set_SolutionId(valuetype [mscorlib]System.Guid value)
0x3cbdf  ldloc.0
0x3cbe0  ldstr    aComponentstate_0// "ComponentState"
0x3cbe5  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x3cbea  brfalse.s loc_3CC16
0x3cbec  ldarg.0
0x3cbed  ldtoken  Microsoft.Crm.Platform.ComponentState
0x3cbf2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3cbf7  ldarg.1
0x3cbf8  ldstr    aComponentstate_0// "ComponentState"
0x3cbfd  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3cc02  callvirt instance string [mscorlib]System.Object::ToString()
0x3cc07  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x3cc0c  unbox.any Microsoft.Crm.Platform.ComponentState
0x3cc11  callvirt instance void Microsoft.Crm.Metadata.PrivilegeDescription::set_ComponentState(valuetype Microsoft.Crm.Platform.ComponentState value)
0x3cc16  ret
```
