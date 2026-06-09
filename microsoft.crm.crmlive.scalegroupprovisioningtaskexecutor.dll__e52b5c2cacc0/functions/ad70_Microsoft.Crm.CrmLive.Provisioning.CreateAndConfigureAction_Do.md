# Microsoft.Crm.CrmLive.Provisioning.CreateAndConfigureAction::Do

- ea: `0xad70`
- end: `0xb01e`
- name: `Microsoft.Crm.CrmLive.Provisioning.CreateAndConfigureAction::Do`
- size: `686`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0xad50`
- `0xad70`
- `0xb4f0`
- `0x24dc0`

## string_xrefs

- `0xad93`: `CreateAndConfigureAction`

## pseudocode

```c

```

## disassembly

```asm
0xad70  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.AdminContext::.ctor()
0xad75  stloc.1
0xad76  ldarg.0
0xad77  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xad7c  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_ScaleGroupName()
0xad81  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::RetrieveScaleGroupIdFromName(string)
0xad86  stloc.0
0xad87  leave.s  loc_AD93
0xad89  ldloc.1
0xad8a  brfalse.s loc_AD92
0xad8c  ldloc.1
0xad8d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xad92  endfinally
0xad93  ldstr    aCreateandconfi// "CreateAndConfigureAction"
0xad98  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.CrmLiveContext::.ctor(string)
0xad9d  stloc.2
0xad9e  ldc.i4   0x10000
0xada3  newobj   instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient::.ctor(valuetype [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.CrmLiveConnections)
0xada8  stloc.3
0xada9  newobj   instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOrganizationRequest::.ctor()
0xadae  stloc.s  4
0xadb0  ldloc.s  4
0xadb2  ldarg.0
0xadb3  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xadb8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_OrganizationId()
0xadbd  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOrganizationRequest::set_OrganizationId(valuetype [mscorlib]System.Guid)
0xadc2  ldloc.s  4
0xadc4  ldarg.0
0xadc5  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xadca  callvirt instance int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_BaseLanguageCode()
0xadcf  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOrganizationRequest::set_BaseLanguageCode(int32)
0xadd4  ldloc.s  4
0xadd6  ldarg.0
0xadd7  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xaddc  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_InitialUserPuid()
0xade1  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOrganizationRequest::set_Puid(string)
0xade6  ldloc.s  4
0xade8  ldarg.0
0xade9  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xadee  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_InitialUserFirstName()
0xadf3  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOrganizationRequest::set_FirstName(string)
0xadf8  ldloc.s  4
0xadfa  ldarg.0
0xadfb  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xae00  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_InitialUserLastName()
0xae05  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOrganizationRequest::set_LastName(string)
0xae0a  ldloc.s  4
0xae0c  ldarg.0
0xae0d  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xae12  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_InitialUserLiveId()
0xae17  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOrganizationRequest::set_EmailAddress(string)
0xae1c  ldloc.s  4
0xae1e  ldsfld   string [mscorlib]System.String::Empty
0xae23  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOrganizationRequest::set_Version(string)
0xae28  ldloc.s  4
0xae2a  ldsfld   string [mscorlib]System.String::Empty
0xae2f  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOrganizationRequest::set_Category(string)
0xae34  ldloc.s  4
0xae36  ldarg.0
0xae37  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xae3c  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_UniqueName()
0xae41  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOrganizationRequest::set_UniqueName(string)
0xae46  ldloc.s  4
0xae48  ldarg.0
0xae49  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xae4e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_DatacenterId()
0xae53  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOrganizationRequest::set_DatacenterId(valuetype [mscorlib]System.Guid)
0xae58  ldloc.s  4
0xae5a  ldloc.0
0xae5b  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOrganizationRequest::set_ScaleGroupId(valuetype [mscorlib]System.Guid)
0xae60  ldloc.s  4
0xae62  ldarg.0
0xae63  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.CreateAndConfigureAction::get_QueueItemId()
0xae68  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOrganizationRequest::set_ParentQueueItemId(valuetype [mscorlib]System.Guid)
0xae6d  ldloc.3
0xae6e  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.LivePlatformService [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient::get_LivePlatformService()
0xae73  ldloc.s  4
0xae75  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ServiceResponseMessage [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.LivePlatformService::Execute(class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ServiceRequestMessage)
0xae7a  pop
0xae7b  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager::NewManager()
0xae80  dup
0xae81  ldarg.0
0xae82  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.CreateAndConfigureAction::get_QueueItemId()
0xae87  ldc.i4.2
0xae88  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager::TryPeekChildByType(valuetype [mscorlib]System.Guid, int32)
0xae8d  stloc.s  5
0xae8f  ldloc.s  5
0xae91  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0xae96  ldc.r8   30.0
0xae9f  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0xaea4  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreSubscriptionExecutor::WaitForQueueItem(valuetype [mscorlib]System.Guid queueItemId, valuetype [mscorlib]System.TimeSpan timeToWait)
0xaea9  ldc.i4.4
0xaeaa  beq.s    loc_AEB7
0xaeac  ldstr    aCouldNotProvis// "Could not provision organization"
0xaeb1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xaeb6  throw
0xaeb7  newobj   instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.OrganizationConfigurationData::.ctor()
0xaebc  stloc.s  6
0xaebe  ldloc.s  6
0xaec0  ldc.i4.1
0xaec1  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.OrganizationConfigurationData::set_IsRestore(bool)
0xaec6  ldloc.s  6
0xaec8  ldarg.0
0xaec9  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xaece  callvirt instance int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_BaseLanguageCode()
0xaed3  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.OrganizationConfigurationData::set_BaseLanguageCode(int32)
0xaed8  ldloc.s  6
0xaeda  ldarg.0
0xaedb  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xaee0  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_FriendlyName()
0xaee5  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.OrganizationConfigurationData::set_FriendlyName(string)
0xaeea  ldloc.s  6
0xaeec  ldarg.0
0xaeed  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xaef2  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_Locale()
0xaef7  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.OrganizationConfigurationData::set_Locale(string)
0xaefc  ldloc.s  6
0xaefe  ldarg.0
0xaeff  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xaf04  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_OrganizationId()
0xaf09  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.OrganizationConfigurationData::set_OrgId(valuetype [mscorlib]System.Guid)
0xaf0e  ldloc.s  6
0xaf10  ldarg.0
0xaf11  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xaf16  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_CompanySize()
0xaf1b  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.OrganizationConfigurationData::set_CompanySize(string)
0xaf20  ldloc.s  6
0xaf22  ldarg.0
0xaf23  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xaf28  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_UrlName()
0xaf2d  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.OrganizationConfigurationData::set_OrgDomainName(string)
0xaf32  ldloc.s  6
0xaf34  ldarg.0
0xaf35  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xaf3a  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_AccountId()
0xaf3f  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.OrganizationConfigurationData::set_AccountId(string)
0xaf44  ldloc.s  6
0xaf46  ldarg.0
0xaf47  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xaf4c  callvirt instance bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_OptInEmail()
0xaf51  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.OrganizationConfigurationData::set_OptInEmail(bool)
0xaf56  ldloc.s  6
0xaf58  ldarg.0
0xaf59  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xaf5e  callvirt instance bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_OptInPhone()
0xaf63  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.OrganizationConfigurationData::set_OptInPhone(bool)
0xaf68  ldloc.s  6
0xaf6a  ldarg.0
0xaf6b  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xaf70  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_PostalCode()
0xaf75  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.OrganizationConfigurationData::set_PostalCode(string)
0xaf7a  ldloc.s  6
0xaf7c  ldarg.0
0xaf7d  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xaf82  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_StateProvince()
0xaf87  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.OrganizationConfigurationData::set_StateProvince(string)
0xaf8c  ldloc.s  6
0xaf8e  ldarg.0
0xaf8f  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xaf94  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_Phone()
0xaf99  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.OrganizationConfigurationData::set_Phone(string)
0xaf9e  ldloc.s  6
0xafa0  ldstr    a0_0// "0"
0xafa5  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.OrganizationConfigurationData::set_InboundTrackingCode(string)
0xafaa  ldloc.s  6
0xafac  ldstr    a0_0// "0"
0xafb1  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.OrganizationConfigurationData::set_OutboundTrackingCode(string)
0xafb6  newobj   instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ConfigureOrganizationRequest::.ctor()
0xafbb  stloc.s  7
0xafbd  ldloc.s  7
0xafbf  ldloc.s  6
0xafc1  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ConfigureOrganizationRequest::set_ConfigurationData(class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.OrganizationConfigurationData)
0xafc6  ldloc.s  7
0xafc8  ldstr    aNotused// "NotUsed"
0xafcd  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ConfigureOrganizationRequest::set_Version(string)
0xafd2  ldloc.3
0xafd3  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.LivePlatformService [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient::get_LivePlatformService()
0xafd8  ldloc.s  7
0xafda  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ServiceResponseMessage [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.LivePlatformService::Execute(class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ServiceRequestMessage)
0xafdf  pop
0xafe0  ldloc.s  5
0xafe2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0xafe7  ldc.i4.s 0x14
0xafe9  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager::TryPeekChildByType(valuetype [mscorlib]System.Guid, int32)
0xafee  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0xaff3  ldc.r8   30.0
0xaffc  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0xb001  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus Microsoft.Crm.CrmLive.Provisioning.OrganizationRestoreSubscriptionExecutor::WaitForQueueItem(valuetype [mscorlib]System.Guid queueItemId, valuetype [mscorlib]System.TimeSpan timeToWait)
0xb006  pop
0xb007  leave.s  loc_B01D
0xb009  ldloc.3
0xb00a  brfalse.s loc_B012
0xb00c  ldloc.3
0xb00d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb012  endfinally
0xb013  ldloc.2
0xb014  brfalse.s loc_B01C
0xb016  ldloc.2
0xb017  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb01c  endfinally
0xb01d  ret
```
