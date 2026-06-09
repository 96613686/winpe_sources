# Microsoft.Crm.Tools.Admin.CrmOrganizationActionManager::GetCrmOrganizationActionsForUpdate

- ea: `0xa6b0`
- end: `0xa710`
- name: `Microsoft.Crm.Tools.Admin.CrmOrganizationActionManager::GetCrmOrganizationActionsForUpdate`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0xd960`

## callees

- `0x8600`
- `0x8610`
- `0x9870`
- `0xa6b0`
- `0xad10`
- `0xadc0`
- `0xfe80`

## pseudocode

```c

```

## disassembly

```asm
0xa6b0  ldarg.1
0xa6b1  callvirt instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0xa6b6  callvirt instance bool Microsoft.Crm.Tools.Admin.OrganizationInfo::get_IsXrmOrg()
0xa6bb  brtrue.s loc_A70E
0xa6bd  ldarg.1
0xa6be  callvirt instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0xa6c3  callvirt instance bool Microsoft.Crm.Tools.Admin.OrganizationInfo::get_IsXrmOrg()
0xa6c8  stloc.0
0xa6c9  ldarg.1
0xa6ca  callvirt instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0xa6cf  ldc.i4.0
0xa6d0  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_IsXrmOrg(bool value)
0xa6d5  ldarg.0
0xa6d6  ldarg.1
0xa6d7  ldc.i4.s 0x19
0xa6d9  newobj   instance void Microsoft.Crm.Tools.Admin.InstallCrmSystemConvertedSolutionsAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xa6de  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xa6e3  ldarg.0
0xa6e4  ldarg.1
0xa6e5  ldc.i4.5
0xa6e6  newobj   instance void Microsoft.Crm.Tools.Admin.InstallOtherCRMSolutionsAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xa6eb  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xa6f0  ldarg.0
0xa6f1  ldarg.1
0xa6f2  ldc.i4.s 0xF
0xa6f4  ldc.i4.0
0xa6f5  newobj   instance void Microsoft.Crm.Tools.Admin.InstallDatabaseUpdatesAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting, [opt] bool isXrm)
0xa6fa  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xa6ff  leave.s  loc_A70E
0xa701  ldarg.1
0xa702  callvirt instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0xa707  ldloc.0
0xa708  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_IsXrmOrg(bool value)
0xa70d  endfinally
0xa70e  ldarg.0
0xa70f  ret
```
