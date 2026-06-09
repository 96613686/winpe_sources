# Microsoft.Crm.Metadata.DynamicMetadataCacheDataProvider::TryGetRoleTemplatePrivilege_0

- ea: `0x1da40`
- end: `0x1da64`
- name: `Microsoft.Crm.Metadata.DynamicMetadataCacheDataProvider::TryGetRoleTemplatePrivilege_0`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1a010`
- `0x1d210`

## string_xrefs

- `0x1da4c`: `privilegeId`
- `0x1da41`: `roleTemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x1da40  ldarg.1
0x1da41  ldstr    aRoletemplateid// "roleTemplateId"
0x1da46  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1da4b  ldarg.2
0x1da4c  ldstr    aPrivilegeid// "privilegeId"
0x1da51  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1da56  ldarg.0
0x1da57  call     instance class Microsoft.Crm.Metadata.IDynamicMetadataContainer Microsoft.Crm.Metadata.DynamicMetadataDataSizeCollectable::get_Container()
0x1da5c  ldarg.1
0x1da5d  ldarg.2
0x1da5e  callvirt instance class Microsoft.Crm.Metadata.RoleTemplatePrivilege Microsoft.Crm.Metadata.IDynamicMetadataContainer::TryGetRoleTemplatePrivilege(valuetype [mscorlib]System.Guid roleTemplateId, valuetype [mscorlib]System.Guid privilegeId)
0x1da63  ret
```
