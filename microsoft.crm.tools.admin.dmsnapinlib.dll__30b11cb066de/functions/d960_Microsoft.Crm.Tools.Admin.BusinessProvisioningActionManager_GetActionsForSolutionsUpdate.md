# Microsoft.Crm.Tools.Admin.BusinessProvisioningActionManager::GetActionsForSolutionsUpdate

- ea: `0xd960`
- end: `0xd9ee`
- name: `Microsoft.Crm.Tools.Admin.BusinessProvisioningActionManager::GetActionsForSolutionsUpdate`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0xd8c0`

## callees

- `0x6540`
- `0x8600`
- `0x8610`
- `0x9870`
- `0xa6b0`
- `0xd960`
- `0xdae0`
- `0x102b0`
- `0x102d0`
- `0x102f0`
- `0x10310`
- `0x10390`

## pseudocode

```c

```

## disassembly

```asm
0xd960  ldarg.1
0xd961  callvirt instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0xd966  callvirt instance bool Microsoft.Crm.Tools.Admin.OrganizationInfo::get_IsXrmOrg()
0xd96b  stloc.0
0xd96c  ldarg.1
0xd96d  callvirt instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0xd972  ldc.i4.1
0xd973  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_IsXrmOrg(bool value)
0xd978  ldarg.0
0xd979  ldarg.1
0xd97a  ldc.i4.4
0xd97b  newobj   instance void Microsoft.Crm.Tools.Admin.InstallPlatformSolutionsAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd980  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd985  ldarg.0
0xd986  ldarg.1
0xd987  ldc.i4.1
0xd988  newobj   instance void Microsoft.Crm.Tools.Admin.CreateCustomControlDefaultConfigAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd98d  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd992  ldarg.0
0xd993  ldarg.1
0xd994  ldc.i4.s 0xF
0xd996  newobj   instance void Microsoft.Crm.Tools.Admin.InstallXrmSystemConvertedSolutionsAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd99b  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd9a0  ldarg.0
0xd9a1  ldarg.1
0xd9a2  ldc.i4.s 0xA
0xd9a4  newobj   instance void Microsoft.Crm.Tools.Admin.InstallOtherXrmSolutionsAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd9a9  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd9ae  leave.s  loc_D9BD
0xd9b0  ldarg.1
0xd9b1  callvirt instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0xd9b6  ldloc.0
0xd9b7  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_IsXrmOrg(bool value)
0xd9bc  endfinally
0xd9bd  ldarg.0
0xd9be  ldarg.1
0xd9bf  call     class Microsoft.Crm.Tools.Admin.OrganizationActionCollection Microsoft.Crm.Tools.Admin.CrmOrganizationActionManager::GetCrmOrganizationActionsForUpdate(class Microsoft.Crm.Tools.Admin.OrganizationActionCollection actions, class Microsoft.Crm.Tools.Admin.OrganizationOperation operation)
0xd9c4  starg.s  0
0xd9c6  ldarg.0
0xd9c7  ldarg.1
0xd9c8  ldc.i4.5
0xd9c9  newobj   instance void Microsoft.Crm.Tools.Admin.InstallRibbonClientMetadataAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd9ce  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd9d3  ldarg.1
0xd9d4  callvirt instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0xd9d9  call     bool Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::UseMultiTenantPackageDeployer(class Microsoft.Crm.Tools.Admin.OrganizationInfo organizationInfo)
0xd9de  brfalse.s loc_D9EC
0xd9e0  ldarg.0
0xd9e1  ldarg.1
0xd9e2  newobj   instance void Microsoft.Crm.Tools.Admin.FlushOrgMetadataCacheInMTPDAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operationBase)
0xd9e7  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd9ec  ldarg.0
0xd9ed  ret
```
