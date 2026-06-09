# Microsoft.Crm.Tools.Admin.BusinessProvisioningActionManager::GetActionsForCreate

- ea: `0xd290`
- end: `0xd3bd`
- name: `Microsoft.Crm.Tools.Admin.BusinessProvisioningActionManager::GetActionsForCreate`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x12200`

## callees

- `0x6540`
- `0x72a0`
- `0x8600`
- `0x8610`
- `0x9870`
- `0xa670`
- `0xd290`
- `0xd3c0`
- `0xdaa0`
- `0xdae0`
- `0xdbc0`
- `0xdbe0`
- `0xdc50`
- `0xdd40`
- `0xe940`
- `0xe990`
- `0xfe80`
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
0xd290  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationActionCollection::.ctor()
0xd295  stloc.0
0xd296  ldloc.0
0xd297  ldarg.0
0xd298  ldc.i4.0
0xd299  newobj   instance void Microsoft.Crm.Tools.Admin.DisableSharedCacheAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd29e  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd2a3  ldloc.0
0xd2a4  ldarg.0
0xd2a5  ldc.i4.0
0xd2a6  ldc.i4.1
0xd2a7  newobj   instance void Microsoft.Crm.Tools.Admin.DisableLabelCacheSharingAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting, [opt] bool isCreate)
0xd2ac  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd2b1  ldarg.0
0xd2b2  callvirt instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0xd2b7  callvirt instance bool Microsoft.Crm.Tools.Admin.OrganizationInfo::get_IsXrmOrg()
0xd2bc  stloc.1
0xd2bd  ldarg.0
0xd2be  callvirt instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0xd2c3  ldc.i4.1
0xd2c4  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_IsXrmOrg(bool value)
0xd2c9  ldloc.0
0xd2ca  ldarg.0
0xd2cb  call     class Microsoft.Crm.Tools.Admin.OrganizationActionCollection Microsoft.Crm.Tools.Admin.BusinessProvisioningActionManager::GetActionsForCreateInternal(class Microsoft.Crm.Tools.Admin.OrganizationActionCollection businessProvisioningActions, class Microsoft.Crm.Tools.Admin.OrganizationOperation operation)
0xd2d0  stloc.0
0xd2d1  ldloc.0
0xd2d2  ldarg.0
0xd2d3  ldc.i4.3
0xd2d4  ldc.i4.1
0xd2d5  newobj   instance void Microsoft.Crm.Tools.Admin.InstallDatabaseUpdatesAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting, [opt] bool isXrm)
0xd2da  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd2df  ldloc.0
0xd2e0  ldarg.0
0xd2e1  ldc.i4.0
0xd2e2  newobj   instance void Microsoft.Crm.Tools.Admin.DisableSharedCacheAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd2e7  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd2ec  ldloc.0
0xd2ed  ldarg.0
0xd2ee  ldc.i4.0
0xd2ef  ldc.i4.1
0xd2f0  newobj   instance void Microsoft.Crm.Tools.Admin.DisableLabelCacheSharingAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting, [opt] bool isCreate)
0xd2f5  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd2fa  ldloc.0
0xd2fb  ldarg.0
0xd2fc  ldc.i4.5
0xd2fd  newobj   instance void Microsoft.Crm.Tools.Admin.InstallPlatformSolutionsAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd302  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd307  ldloc.0
0xd308  ldarg.0
0xd309  ldc.i4.1
0xd30a  newobj   instance void Microsoft.Crm.Tools.Admin.CreateCustomControlDefaultConfigAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd30f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd314  ldloc.0
0xd315  ldarg.0
0xd316  ldc.i4.5
0xd317  newobj   instance void Microsoft.Crm.Tools.Admin.InstallXrmSystemConvertedSolutionsAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd31c  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd321  ldloc.0
0xd322  ldarg.0
0xd323  ldc.i4.5
0xd324  newobj   instance void Microsoft.Crm.Tools.Admin.InstallOtherXrmSolutionsAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd329  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd32e  leave.s  loc_D33D
0xd330  ldarg.0
0xd331  callvirt instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0xd336  ldloc.1
0xd337  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_IsXrmOrg(bool value)
0xd33c  endfinally
0xd33d  ldloc.0
0xd33e  ldarg.0
0xd33f  call     class Microsoft.Crm.Tools.Admin.OrganizationActionCollection Microsoft.Crm.Tools.Admin.CrmOrganizationActionManager::GetCrmOrganizationActions(class Microsoft.Crm.Tools.Admin.OrganizationActionCollection actions, class Microsoft.Crm.Tools.Admin.OrganizationOperation operation)
0xd344  stloc.0
0xd345  ldloc.0
0xd346  ldarg.0
0xd347  ldc.i4.1
0xd348  ldc.i4.0
0xd349  newobj   instance void Microsoft.Crm.Tools.Admin.SetOrganizationStateAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState stateToSet, int32 nominalProgressWeighting)
0xd34e  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd353  ldloc.0
0xd354  ldarg.0
0xd355  ldc.i4.1
0xd356  newobj   instance void Microsoft.Crm.Tools.Admin.AddOutOfBoxDupDetectionRulesAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd35b  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd360  ldloc.0
0xd361  ldarg.0
0xd362  ldc.i4.2
0xd363  newobj   instance void Microsoft.Crm.Tools.Admin.PublishDuplicateRuleAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd368  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd36d  ldloc.0
0xd36e  ldarg.0
0xd36f  ldc.i4.5
0xd370  newobj   instance void Microsoft.Crm.Tools.Admin.InstallRibbonClientMetadataAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd375  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd37a  ldloc.0
0xd37b  ldarg.0
0xd37c  ldc.i4.0
0xd37d  newobj   instance void Microsoft.Crm.Tools.Admin.EnableSharedCacheAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd382  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd387  ldloc.0
0xd388  ldarg.0
0xd389  ldc.i4.0
0xd38a  newobj   instance void Microsoft.Crm.Tools.Admin.EnableLabelCacheSharingAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd38f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd394  ldloc.0
0xd395  ldarg.0
0xd396  ldc.i4.2
0xd397  ldc.i4.0
0xd398  newobj   instance void Microsoft.Crm.Tools.Admin.SetOrganizationStateAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState stateToSet, int32 nominalProgressWeighting)
0xd39d  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd3a2  ldarg.0
0xd3a3  callvirt instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0xd3a8  call     bool Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::UseMultiTenantPackageDeployer(class Microsoft.Crm.Tools.Admin.OrganizationInfo organizationInfo)
0xd3ad  brfalse.s loc_D3BB
0xd3af  ldloc.0
0xd3b0  ldarg.0
0xd3b1  newobj   instance void Microsoft.Crm.Tools.Admin.FlushOrgMetadataCacheInMTPDAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operationBase)
0xd3b6  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd3bb  ldloc.0
0xd3bc  ret
```
