# Microsoft.Crm.ServiceBus.RouterService::RetrievePrivilegeUserGroupId

- ea: `0x4340`
- end: `0x4382`
- name: `Microsoft.Crm.ServiceBus.RouterService::RetrievePrivilegeUserGroupId`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x42f0`
- `0x4390`

## callees

- `0x4340`

## string_xrefs

- `0x434d`: `PrivilegeUserGroupId`
- `0x435a`: `PrivilegeUserGroupId`
- `0x4367`: `PrivilegeUserGroupId`

## pseudocode

```c

```

## disassembly

```asm
0x4340  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::.ctor()
0x4345  ldc.i4.1
0x4346  newarr   [mscorlib]System.String
0x434b  dup
0x434c  ldc.i4.0
0x434d  ldstr    aPrivilegeuserg// "PrivilegeUserGroupId"
0x4352  stelem.ref
0x4353  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::Retrieve(string[])
0x4358  stloc.0
0x4359  ldloc.0
0x435a  ldstr    aPrivilegeuserg// "PrivilegeUserGroupId"
0x435f  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x4364  brfalse.s loc_4377
0x4366  ldloc.0
0x4367  ldstr    aPrivilegeuserg// "PrivilegeUserGroupId"
0x436c  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x4371  unbox.any [mscorlib]System.Guid
0x4376  ret
0x4377  ldstr    aCouldNotFindPr// "Could not find Priv user group id."
0x437c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x4381  throw
```
