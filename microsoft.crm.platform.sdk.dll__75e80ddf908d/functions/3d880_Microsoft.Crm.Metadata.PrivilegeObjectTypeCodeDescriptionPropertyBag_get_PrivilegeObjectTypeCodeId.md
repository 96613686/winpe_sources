# Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescriptionPropertyBag::get_PrivilegeObjectTypeCodeId

- ea: `0x3d880`
- end: `0x3d8ae`
- name: `Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescriptionPropertyBag::get_PrivilegeObjectTypeCodeId`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x3d880`
- `0x6fd40`
- `0x6fe70`

## string_xrefs

- `0x3d886`: `privilegeobjecttypecodeid`
- `0x3d89e`: `privilegeobjecttypecodeid`

## pseudocode

```c

```

## disassembly

```asm
0x3d880  ldarg.0
0x3d881  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescriptionPropertyBag::_privilegeObjectTypeCodeData
0x3d886  ldstr    aPrivilegeobjec_3// "privilegeobjecttypecodeid"
0x3d88b  callvirt instance bool Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string propertyName)
0x3d890  brfalse.s loc_3D898
0x3d892  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3d897  ret
0x3d898  ldarg.0
0x3d899  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDescriptionPropertyBag::_privilegeObjectTypeCodeData
0x3d89e  ldstr    aPrivilegeobjec_3// "privilegeobjecttypecodeid"
0x3d8a3  callvirt instance object Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string propertyName)
0x3d8a8  unbox.any [mscorlib]System.Guid
0x3d8ad  ret
```
