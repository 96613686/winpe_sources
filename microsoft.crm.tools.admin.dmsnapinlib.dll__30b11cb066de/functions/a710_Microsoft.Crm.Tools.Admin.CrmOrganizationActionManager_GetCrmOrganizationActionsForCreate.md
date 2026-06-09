# Microsoft.Crm.Tools.Admin.CrmOrganizationActionManager::GetCrmOrganizationActionsForCreate

- ea: `0xa710`
- end: `0xa77c`
- name: `Microsoft.Crm.Tools.Admin.CrmOrganizationActionManager::GetCrmOrganizationActionsForCreate`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0xa670`

## callees

- `0x8600`
- `0x8610`
- `0x9870`
- `0xa710`
- `0xad10`
- `0xadc0`
- `0xade0`
- `0xec00`
- `0xfe80`

## pseudocode

```c

```

## disassembly

```asm
0xa710  ldarg.1
0xa711  callvirt instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0xa716  callvirt instance bool Microsoft.Crm.Tools.Admin.OrganizationInfo::get_IsXrmOrg()
0xa71b  stloc.0
0xa71c  ldarg.1
0xa71d  callvirt instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0xa722  ldc.i4.0
0xa723  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_IsXrmOrg(bool value)
0xa728  ldarg.0
0xa729  ldarg.1
0xa72a  ldc.i4.s 0xA
0xa72c  newobj   instance void Microsoft.Crm.Tools.Admin.InstallCrmSystemConvertedSolutionsAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xa731  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xa736  ldarg.0
0xa737  ldarg.1
0xa738  ldc.i4.1
0xa739  newobj   instance void Microsoft.Crm.Tools.Admin.PopulateValuesForMigrationSupport::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xa73e  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xa743  ldarg.0
0xa744  ldarg.1
0xa745  ldc.i4.2
0xa746  newobj   instance void Microsoft.Crm.Tools.Admin.SetOutOfBoxDocumentTemplatesAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xa74b  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xa750  ldarg.0
0xa751  ldarg.1
0xa752  ldc.i4.5
0xa753  newobj   instance void Microsoft.Crm.Tools.Admin.InstallOtherCRMSolutionsAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xa758  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xa75d  ldarg.0
0xa75e  ldarg.1
0xa75f  ldc.i4.3
0xa760  ldc.i4.0
0xa761  newobj   instance void Microsoft.Crm.Tools.Admin.InstallDatabaseUpdatesAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting, [opt] bool isXrm)
0xa766  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xa76b  leave.s  loc_A77A
0xa76d  ldarg.1
0xa76e  callvirt instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0xa773  ldloc.0
0xa774  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_IsXrmOrg(bool value)
0xa779  endfinally
0xa77a  ldarg.0
0xa77b  ret
```
