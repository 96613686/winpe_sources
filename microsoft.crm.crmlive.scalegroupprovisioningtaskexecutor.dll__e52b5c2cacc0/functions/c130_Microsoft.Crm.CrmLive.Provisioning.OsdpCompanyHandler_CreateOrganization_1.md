# Microsoft.Crm.CrmLive.Provisioning.OsdpCompanyHandler::CreateOrganization_1

- ea: `0xc130`
- end: `0xc345`
- name: `Microsoft.Crm.CrmLive.Provisioning.OsdpCompanyHandler::CreateOrganization_1`
- size: `533`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xc0d0`
- `0xc0e0`

## callees

- `0xc130`
- `0xc350`
- `0xc3a0`
- `0xc920`
- `0x18250`

## string_xrefs

- `0xc2de`: `CrmScaleGroupProvisioningService`

## pseudocode

```c

```

## disassembly

```asm
0xc130  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xc135  stloc.0
0xc136  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xc13b  stloc.1
0xc13c  ldarg.s  4
0xc13e  ldarg.2
0xc13f  callvirt instance string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObject::get_ContextId()
0xc144  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xc149  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider::GetInitialUserForCompany(valuetype [mscorlib]System.Guid)
0xc14e  stloc.2
0xc14f  ldloc.2
0xc150  brfalse  loc_C327
0xc155  ldloca.s 3
0xc157  ldarg.2
0xc158  callvirt instance string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObject::get_ContextId()
0xc15d  call     instance void [mscorlib]System.Guid::.ctor(string)
0xc162  ldloc.2
0xc163  ldarg.1
0xc164  ldarg.s  4
0xc166  call     string Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUtility::ExtractPuidFromUser(class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User user, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider directoryProvider)
0xc16b  stloc.s  4
0xc16d  ldarg.2
0xc16e  call     class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.MicrosoftOnline.OsdpLanguageSettings [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.MicrosoftOnline.OsdpUtility::GetLanguageSettingsForCompany(class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.Company)
0xc173  stloc.s  5
0xc175  ldloc.s  5
0xc177  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.MicrosoftOnline.OsdpLanguageSettings::get_PreferredLanguage()
0xc17c  ldarg.1
0xc17d  call     int32 [Microsoft.Crm]Microsoft.Crm.LanguageUtility::PreferredLanguageToLcid(string, valuetype [mscorlib]System.Guid)
0xc182  stloc.s  6
0xc184  ldarg.s  4
0xc186  ldloc.2
0xc187  ldstr    aGivenname// "GivenName"
0xc18c  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider::RetrieveStringPropertyValue(class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObject, string)
0xc191  stloc.s  7
0xc193  ldarg.s  4
0xc195  ldloc.2
0xc196  ldstr    aSn// "Sn"
0xc19b  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider::RetrieveStringPropertyValue(class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObject, string)
0xc1a0  stloc.s  8
0xc1a2  ldc.i4   0x10000
0xc1a7  newobj   instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient::.ctor(valuetype [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.CrmLiveConnections)
0xc1ac  stloc.s  9
0xc1ae  newobj   instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOsdpOrganizationRequest::.ctor()
0xc1b3  stloc.s  0xA
0xc1b5  ldloc.s  0xA
0xc1b7  ldarg.1
0xc1b8  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOsdpOrganizationRequest::set_OrganizationId(valuetype [mscorlib]System.Guid)
0xc1bd  ldloc.s  0xA
0xc1bf  ldloc.3
0xc1c0  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOsdpOrganizationRequest::set_ContextId(valuetype [mscorlib]System.Guid)
0xc1c5  ldloc.s  0xA
0xc1c7  ldloc.s  6
0xc1c9  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOsdpOrganizationRequest::set_BaseLanguageCode(int32)
0xc1ce  ldloc.s  0xA
0xc1d0  ldloc.s  4
0xc1d2  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOsdpOrganizationRequest::set_Puid(string)
0xc1d7  ldloc.s  0xA
0xc1d9  ldloc.s  7
0xc1db  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOsdpOrganizationRequest::set_FirstName(string)
0xc1e0  ldloc.s  0xA
0xc1e2  ldloc.s  8
0xc1e4  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOsdpOrganizationRequest::set_LastName(string)
0xc1e9  ldloc.s  0xA
0xc1eb  ldarg.s  4
0xc1ed  ldloc.2
0xc1ee  ldstr    aUserprincipaln// "UserPrincipalName"
0xc1f3  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider::RetrieveStringPropertyValue(class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObject, string)
0xc1f8  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOsdpOrganizationRequest::set_UserPrincipalName(string)
0xc1fd  ldloc.s  0xA
0xc1ff  ldloc.2
0xc200  callvirt instance string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObject::get_ObjectId()
0xc205  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xc20a  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOsdpOrganizationRequest::set_InitialUserObjectId(valuetype [mscorlib]System.Guid)
0xc20f  ldloc.s  0xA
0xc211  ldloc.2
0xc212  ldarg.s  4
0xc214  ldarg.1
0xc215  call     bool Microsoft.Crm.CrmLive.Provisioning.OsdpCompanyHandler::IsUserLicensedInOsdp(class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User user, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider directoryProvider, valuetype [mscorlib]System.Guid organizationId)
0xc21a  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0xc21f  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOsdpOrganizationRequest::set_IsInitialUserLicensed(valuetype [mscorlib]System.Nullable`1<bool>)
0xc224  ldloc.s  0xA
0xc226  ldarg.s  4
0xc228  ldarg.2
0xc229  ldstr    aTechnicalnotif// "TechnicalNotificationMail"
0xc22e  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider::RetrieveStringPropertyValue(class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObject, string)
0xc233  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOsdpOrganizationRequest::set_EmailAddress(string)
0xc238  ldarg.0
0xc239  brfalse.s loc_C248
0xc23b  ldloc.s  0xA
0xc23d  ldarg.0
0xc23e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ScaleGroupId()
0xc243  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOsdpOrganizationRequest::set_ScaleGroupId(valuetype [mscorlib]System.Guid)
0xc248  ldloc.s  0xA
0xc24a  ldarg.s  4
0xc24c  ldarg.2
0xc24d  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider::GetOffice365DomainName(class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObject)
0xc252  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOsdpOrganizationRequest::set_RequestedUniqueName(string)
0xc257  ldloc.s  0xA
0xc259  ldloc.s  0xA
0xc25b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOsdpOrganizationRequest::get_ContextId()
0xc260  ldarg.s  4
0xc262  ldarg.2
0xc263  ldstr    aDisplayname// "DisplayName"
0xc268  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider::RetrieveStringPropertyValue(class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObject, string)
0xc26d  call     string Microsoft.Crm.CrmLive.Provisioning.OsdpCompanyHandler::RetrieveUniqueFriendlyNameForContext(valuetype [mscorlib]System.Guid contextId, string baseFriendlyName)
0xc272  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOsdpOrganizationRequest::set_FriendlyName(string)
0xc277  ldloc.s  0xA
0xc279  ldloc.s  5
0xc27b  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.MicrosoftOnline.OsdpLanguageSettings::get_CountryCode()
0xc280  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOsdpOrganizationRequest::set_CountryCode(string)
0xc285  ldloc.s  0xA
0xc287  ldloc.s  5
0xc289  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.MicrosoftOnline.OsdpLanguageSettings::get_PreferredLanguage()
0xc28e  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOsdpOrganizationRequest::set_PreferredLanguage(string)
0xc293  ldloc.s  0xA
0xc295  ldarg.3
0xc296  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0xc29b  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOsdpOrganizationRequest::set_OrganizationType(valuetype [mscorlib]System.Nullable`1<int32>)
0xc2a0  ldloc.s  9
0xc2a2  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.LivePlatformService [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient::get_LivePlatformService()
0xc2a7  ldloc.s  0xA
0xc2a9  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ServiceResponseMessage [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.LivePlatformService::Execute(class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ServiceRequestMessage)
0xc2ae  castclass [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOsdpOrganizationResponse
0xc2b3  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOsdpOrgResult [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOsdpOrganizationResponse::get_Result()
0xc2b8  stloc.s  0xB
0xc2ba  ldloc.s  0xB
0xc2bc  callvirt instance valuetype [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOsdpOrgResultCode [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOsdpOrgResult::get_Result()
0xc2c1  brtrue.s loc_C2D5
0xc2c3  ldloc.s  0xB
0xc2c5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOsdpOrgResult::get_QueueItemId()
0xc2ca  stloc.0
0xc2cb  ldloc.s  0xB
0xc2cd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOsdpOrgResult::get_DatacenterId()
0xc2d2  stloc.1
0xc2d3  leave.s  loc_C33D
0xc2d5  call     class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::NewEventLog()
0xc2da  stloc.s  0xC
0xc2dc  ldloc.s  0xC
0xc2de  ldstr    aCrmscalegroupp// "CrmScaleGroupProvisioningService"
0xc2e3  ldc.i4.2
0xc2e4  ldc.i4   0xC000464D
0xc2e9  conv.u8
0xc2ea  ldc.i4.2
0xc2eb  newarr   [mscorlib]System.Object
0xc2f0  dup
0xc2f1  ldc.i4.0
0xc2f2  ldarg.1
0xc2f3  box      [mscorlib]System.Guid
0xc2f8  stelem.ref
0xc2f9  dup
0xc2fa  ldc.i4.1
0xc2fb  ldloc.s  0xB
0xc2fd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisionOsdpOrgResult::get_QueueItemId()
0xc302  box      [mscorlib]System.Guid
0xc307  stelem.ref
0xc308  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0xc30d  leave.s  loc_C33D
0xc30f  ldloc.s  0xC
0xc311  brfalse.s loc_C31A
0xc313  ldloc.s  0xC
0xc315  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc31a  endfinally
0xc31b  ldloc.s  9
0xc31d  brfalse.s loc_C326
0xc31f  ldloc.s  9
0xc321  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc326  endfinally
0xc327  ldstr    aNoUserFoundFor// "No user found for this org to provision"
0xc32c  ldarg.2
0xc32d  callvirt instance string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObject::get_ContextId()
0xc332  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xc337  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.CrmOsdpInitialUserNotFoundException::.ctor(string message, valuetype [mscorlib]System.Guid contextId)
0xc33c  throw
0xc33d  ldloc.0
0xc33e  ldloc.1
0xc33f  call     T0x2B00003B
0xc344  ret
```
