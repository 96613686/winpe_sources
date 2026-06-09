# Microsoft.Crm.CrmLive.Provisioning.SyncSubscribedPlanAction::SyncObject

- ea: `0xf540`
- end: `0xf6d0`
- name: `Microsoft.Crm.CrmLive.Provisioning.SyncSubscribedPlanAction::SyncObject`
- size: `400`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2b770`

## callees

- `0x1ac0`
- `0x1d80`
- `0x1dd0`
- `0xf540`
- `0xf6d0`
- `0xf760`
- `0xf840`
- `0xf970`
- `0x1c360`
- `0x1c3b0`
- `0x2f310`
- `0x2f330`
- `0x2f3b0`
- `0x2f510`
- `0x2f750`
- `0x2f8c0`

## string_xrefs

- `0xf575`: `Deserialized SubscribedPlan object is null`
- `0xf662`: `ConfigSettingManagement`

## pseudocode

```c

```

## disassembly

```asm
0xf540  ldarg.1
0xf541  ldstr    aItem// "item"
0xf546  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xf54b  ldarg.2
0xf54c  ldstr    aRecord// "record"
0xf551  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xf556  call     T0x2B000036
0xf55b  ldarg.1
0xf55c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0xf561  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProviderFactory::GetProvider(valuetype [mscorlib]System.Guid)
0xf566  ldarg.2
0xf567  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObject [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider::ConvertToDirectoryObject(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag)
0xf56c  isinst   [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.SubscribedPlan
0xf571  stloc.0
0xf572  ldloc.0
0xf573  brtrue.s loc_F580
0xf575  ldstr    aDeserializedSu// "Deserialized SubscribedPlan object is n"...
0xf57a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xf57f  throw
0xf580  ldarg.0
0xf581  ldarg.1
0xf582  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0xf587  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncSubscribedPlanAction::_orgId
0xf58c  ldarg.0
0xf58d  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncSubscribedPlanAction::_orgId
0xf592  call     class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.AssignedAndSubscribedPlans [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.CompanyState::GetPreviousAssignedAndSubscribedPlans(valuetype [mscorlib]System.Guid)
0xf597  stloc.1
0xf598  ldloc.1
0xf599  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.SubscribedPlan> [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.AssignedAndSubscribedPlans::get_SubscribedPlans()
0xf59e  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.SubscribedPlan, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.MicrosoftOnline.SimpleSubscribedPlan> <>c::<>9__0_0
0xf5a3  dup
0xf5a4  brtrue.s loc_F5BD
0xf5a6  pop
0xf5a7  ldsfld   class <>c <>c::<>9
0xf5ac  ldftn    instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.MicrosoftOnline.SimpleSubscribedPlan <>c::<SyncObject>b__0_0(class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.SubscribedPlan s)
0xf5b2  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.SubscribedPlan, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.MicrosoftOnline.SimpleSubscribedPlan>::.ctor(object, native int)
0xf5b7  dup
0xf5b8  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.SubscribedPlan, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.MicrosoftOnline.SimpleSubscribedPlan> <>c::<>9__0_0
0xf5bd  call     T0x2B000009
0xf5c2  call     bool Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.Action.SyncData.SubscribedPlanUtility::IsTrialSubscription(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.MicrosoftOnline.SimpleSubscribedPlan> subscribedPlans)
0xf5c7  stloc.2
0xf5c8  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.SyncData.SubscribedPlanHandler.PostSyncActionSet::.ctor()
0xf5cd  stloc.3
0xf5ce  ldarg.0
0xf5cf  ldarg.0
0xf5d0  call     instance int32 Microsoft.Crm.CrmLive.Provisioning.SyncSubscribedPlanAction::GetOldStorageDueToUserLicenses()
0xf5d5  stfld    int32 Microsoft.Crm.CrmLive.Provisioning.SyncSubscribedPlanAction::_previousStorageDueToUserLicenses
0xf5da  ldarg.0
0xf5db  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncSubscribedPlanAction::_orgId
0xf5e0  ldarg.1
0xf5e1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0xf5e6  newobj   instance void Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.Action.SyncData.SubscribedPlanLogger::.ctor(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid queueItemId)
0xf5eb  stloc.s  4
0xf5ed  ldarg.0
0xf5ee  ldloc.0
0xf5ef  call     instance class Microsoft.Crm.CrmLive.Provisioning.SyncData.SubscribedPlanHandler.ISubscribedPlanHandler Microsoft.Crm.CrmLive.Provisioning.SyncSubscribedPlanAction::GetHandler(class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.SubscribedPlan subscribedPlan)
0xf5f4  ldarg.1
0xf5f5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0xf5fa  ldloc.0
0xf5fb  ldloc.1
0xf5fc  ldloc.s  4
0xf5fe  callvirt instance class Microsoft.Crm.CrmLive.Provisioning.SyncData.SubscribedPlanHandler.PostSyncActionSet Microsoft.Crm.CrmLive.Provisioning.SyncData.SubscribedPlanHandler.ISubscribedPlanHandler::Sync(valuetype [mscorlib]System.Guid orgId, class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.SubscribedPlan plan, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.AssignedAndSubscribedPlans previousAssignedAndSubscribedPlans, class Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.Action.SyncData.ISubscribedPlanLogger logger)
0xf603  stloc.3
0xf604  ldloc.1
0xf605  ldloc.0
0xf606  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.AssignedAndSubscribedPlans::UpdateSubscribedPlan(class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.SubscribedPlan)
0xf60b  ldarg.0
0xf60c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncSubscribedPlanAction::_orgId
0xf611  ldloc.1
0xf612  call     void Microsoft.Crm.CrmLive.Provisioning.SyncData.SubscribedPlanHandler.SubscribedPlanHelpers::WritePreviousAssignedAndSubscribedPlansToDatabase(valuetype [mscorlib]System.Guid orgId, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.AssignedAndSubscribedPlans previousAssignedAndSubscribedPlans)
0xf617  ldarg.1
0xf618  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0xf61d  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::GetOrganizationType(valuetype [mscorlib]System.Guid)
0xf622  stloc.s  5
0xf624  ldloc.s  5
0xf626  ldc.i4.7
0xf627  beq.s    loc_F65A
0xf629  ldloc.s  5
0xf62b  ldc.i4.s 0xA
0xf62d  beq.s    loc_F65A
0xf62f  ldloc.s  5
0xf631  ldc.i4.s 0xB
0xf633  beq.s    loc_F65A
0xf635  ldloc.3
0xf636  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.SyncData.SubscribedPlanHandler.PostSyncActionSet::get_RecalculateStorage()
0xf63b  brfalse.s loc_F65A
0xf63d  ldarg.0
0xf63e  ldloc.1
0xf63f  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.SubscribedPlan> [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.AssignedAndSubscribedPlans::get_SubscribedPlans()
0xf644  ldarg.0
0xf645  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncSubscribedPlanAction::_orgId
0xf64a  ldloc.0
0xf64b  callvirt instance string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObject::get_ContextId()
0xf650  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xf655  call     instance void Microsoft.Crm.CrmLive.Provisioning.SyncSubscribedPlanAction::RecalculateTotalStorageFromSubscribedPlans(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.SubscribedPlan> subscribedPlans, valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid contextId)
0xf65a  ldloc.0
0xf65b  call     bool Microsoft.Crm.CrmLive.Provisioning.SyncData.SubscribedPlanHandler.SubscribedPlanHelpers::IsPaidSubscribedPlan(class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.SubscribedPlan subscribedPlan)
0xf660  brfalse.s loc_F6C8
0xf662  ldstr    aConfigsettingm// "ConfigSettingManagement"
0xf667  call     bool [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClientHelper::IsGeoFeatureEnabled(string)
0xf66c  brfalse.s loc_F694
0xf66e  ldarg.0
0xf66f  call     T0x2B00005B
0xf674  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Configuration.CloudConfig.ICloudConfigApi Microsoft.Crm.CrmLive.Provisioning.SyncSubscribedPlanAction::_proxy
0xf679  ldarg.0
0xf67a  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Configuration.CloudConfig.ICloudConfigApi Microsoft.Crm.CrmLive.Provisioning.SyncSubscribedPlanAction::_proxy
0xf67f  ldloc.0
0xf680  callvirt instance string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObject::get_ContextId()
0xf685  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xf68a  ldstr    aTrial// "Trial"
0xf68f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Configuration.CloudConfig.ICloudConfigApi::DeleteProvisioningTag(valuetype [mscorlib]System.Guid, string)
0xf694  ldloc.0
0xf695  callvirt instance string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObject::get_ContextId()
0xf69a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xf69f  ldarg.0
0xf6a0  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncSubscribedPlanAction::_orgId
0xf6a5  call     void Microsoft.Crm.CrmLive.Provisioning.SyncData.SubscribedPlanHandler.SubscribedPlanHelpers::SetContextIsTrialToFalse(valuetype [mscorlib]System.Guid contextId, valuetype [mscorlib]System.Guid orgId)
0xf6aa  ldloc.2
0xf6ab  brfalse.s loc_F6C8
0xf6ad  call     class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::NewService()
0xf6b2  ldarg.1
0xf6b3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0xf6b8  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::GetDirectoryObjectIds(valuetype [mscorlib]System.Guid organizationId)
0xf6bd  stloc.s  6
0xf6bf  ldarg.0
0xf6c0  ldloc.s  6
0xf6c2  ldarg.1
0xf6c3  call     instance void Microsoft.Crm.CrmLive.Provisioning.SyncSubscribedPlanAction::ScheduleUserSync(class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid> objectsToSync, class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem parentQueueItem)
0xf6c8  ldloc.s  4
0xf6ca  callvirt instance void Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.Action.SyncData.SubscribedPlanLogger::CommitLog()
0xf6cf  ret
```
