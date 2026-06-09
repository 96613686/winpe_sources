# Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescriptionPropertyBag::get_PrivilegeId

- ea: `0x3d8d0`
- end: `0x3d8fe`
- name: `Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescriptionPropertyBag::get_PrivilegeId`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x3d8d0`
- `0x6fd40`
- `0x6fe70`

## string_xrefs

- `0x3d8d6`: `privilegeid`
- `0x3d8ee`: `privilegeid`

## pseudocode

```c

```

## disassembly

```asm
0x3d8d0  ldarg.0
0x3d8d1  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescriptionPropertyBag::_privilegeObjectTypeCodeData
0x3d8d6  ldstr    aPrivilegeid_1// "privilegeid"
0x3d8db  callvirt instance bool Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string propertyName)
0x3d8e0  brfalse.s loc_3D8E8
0x3d8e2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3d8e7  ret
0x3d8e8  ldarg.0
0x3d8e9  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescriptionPropertyBag::_privilegeObjectTypeCodeData
0x3d8ee  ldstr    aPrivilegeid_1// "privilegeid"
0x3d8f3  callvirt instance object Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string propertyName)
0x3d8f8  unbox.any [mscorlib]System.Guid
0x3d8fd  ret
```
