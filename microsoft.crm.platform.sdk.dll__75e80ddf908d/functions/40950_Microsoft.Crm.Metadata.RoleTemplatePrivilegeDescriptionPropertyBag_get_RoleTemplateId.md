# Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescriptionPropertyBag::get_RoleTemplateId

- ea: `0x40950`
- end: `0x4097e`
- name: `Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescriptionPropertyBag::get_RoleTemplateId`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x40950`
- `0x6fd40`
- `0x6fe70`

## string_xrefs

- `0x40956`: `roletemplateid`
- `0x4096e`: `roletemplateid`

## pseudocode

```c

```

## disassembly

```asm
0x40950  ldarg.0
0x40951  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescriptionPropertyBag::_roleTemplatePrivilegeData
0x40956  ldstr    aRoletemplateid_1// "roletemplateid"
0x4095b  callvirt instance bool Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string propertyName)
0x40960  brfalse.s loc_40968
0x40962  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x40967  ret
0x40968  ldarg.0
0x40969  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescriptionPropertyBag::_roleTemplatePrivilegeData
0x4096e  ldstr    aRoletemplateid_1// "roletemplateid"
0x40973  callvirt instance object Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string propertyName)
0x40978  unbox.any [mscorlib]System.Guid
0x4097d  ret
```
