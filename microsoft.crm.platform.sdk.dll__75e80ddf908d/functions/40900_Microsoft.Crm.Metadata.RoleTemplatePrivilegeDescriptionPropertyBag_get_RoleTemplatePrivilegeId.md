# Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescriptionPropertyBag::get_RoleTemplatePrivilegeId

- ea: `0x40900`
- end: `0x4092e`
- name: `Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescriptionPropertyBag::get_RoleTemplatePrivilegeId`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x40900`
- `0x6fd40`
- `0x6fe70`

## string_xrefs

- `0x40906`: `roletemplateprivilegeid`
- `0x4091e`: `roletemplateprivilegeid`

## pseudocode

```c

```

## disassembly

```asm
0x40900  ldarg.0
0x40901  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescriptionPropertyBag::_roleTemplatePrivilegeData
0x40906  ldstr    aRoletemplatepr_4// "roletemplateprivilegeid"
0x4090b  callvirt instance bool Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string propertyName)
0x40910  brfalse.s loc_40918
0x40912  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x40917  ret
0x40918  ldarg.0
0x40919  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.RoleTemplatePrivilegeDescriptionPropertyBag::_roleTemplatePrivilegeData
0x4091e  ldstr    aRoletemplatepr_4// "roletemplateprivilegeid"
0x40923  callvirt instance object Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string propertyName)
0x40928  unbox.any [mscorlib]System.Guid
0x4092d  ret
```
