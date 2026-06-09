# Microsoft.Crm.CrmLive.Provisioning.OsdpCompanyStateChanger::Enable

- ea: `0xeb00`
- end: `0xebfe`
- name: `Microsoft.Crm.CrmLive.Provisioning.OsdpCompanyStateChanger::Enable`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xeab0`

## callees

- `0xeb00`

## string_xrefs

- `0xeb20`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\SyncData\OsdpCompanyStateChanger.cs`
- `0xeb3d`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\SyncData\OsdpCompanyStateChanger.cs`

## pseudocode

```c

```

## disassembly

```asm
0xeb00  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0xeb05  ldarg.0
0xeb06  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.OsdpCompanyStateChanger::_organizationId
0xeb0b  ldc.i4.1
0xeb0c  newarr   [mscorlib]System.String
0xeb11  dup
0xeb12  ldc.i4.0
0xeb13  ldstr    aStatechangerea// "StateChangeReason"
0xeb18  stelem.ref
0xeb19  ldc.i4.s 0x48
0xeb1b  ldstr    aEnable// "Enable"
0xeb20  ldstr    aDDbsShDccm2110_19// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0xeb25  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganization(valuetype [mscorlib]System.Guid, string[], int32, string, string)
0xeb2a  stloc.0
0xeb2b  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0xeb30  ldarg.0
0xeb31  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.OsdpCompanyStateChanger::_organizationId
0xeb36  ldc.i4.s 0x49
0xeb38  ldstr    aEnable// "Enable"
0xeb3d  ldstr    aDDbsShDccm2110_19// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0xeb42  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationState(valuetype [mscorlib]System.Guid, int32, string, string)
0xeb47  stloc.1
0xeb48  ldloca.s 1
0xeb4a  ldc.i4.0
0xeb4b  box      [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState
0xeb50  constrained. [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState
0xeb56  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xeb5b  brfalse.s loc_EB8C
0xeb5d  ldloc.0
0xeb5e  brfalse.s loc_EB8C
0xeb60  ldloc.0
0xeb61  ldstr    aStatechangerea// "StateChangeReason"
0xeb66  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xeb6b  brfalse.s loc_EB8C
0xeb6d  ldarg.0
0xeb6e  ldfld    string Microsoft.Crm.CrmLive.Provisioning.OsdpCompanyStateChanger::_disabledByMicrosoftOnline
0xeb73  ldloc.0
0xeb74  ldstr    aStatechangerea// "StateChangeReason"
0xeb79  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xeb7e  castclass [mscorlib]System.String
0xeb83  ldc.i4.5
0xeb84  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xeb89  brtrue.s loc_EB8C
0xeb8b  ret
0xeb8c  ldsfld   class [mscorlib]System.Action`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.CrmLive.Provisioning.OsdpCompanyStateChanger::_performBackup
0xeb91  ldarg.0
0xeb92  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.OsdpCompanyStateChanger::_organizationId
0xeb97  callvirt instance void class [mscorlib]System.Action`1<valuetype [mscorlib]System.Guid>::Invoke(var<u1>)
0xeb9c  call     class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient::ConnectLivePlatformService()
0xeba1  stloc.2
0xeba2  newobj   instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.EnableOrganizationRequest::.ctor()
0xeba7  stloc.3
0xeba8  ldloc.3
0xeba9  ldarg.0
0xebaa  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.OsdpCompanyStateChanger::_organizationId
0xebaf  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.EnableOrganizationRequest::set_OrganizationId(valuetype [mscorlib]System.Guid)
0xebb4  ldloc.2
0xebb5  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.LivePlatformService [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient::get_LivePlatformService()
0xebba  ldloc.3
0xebbb  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ServiceResponseMessage [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.LivePlatformService::Execute(class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ServiceRequestMessage)
0xebc0  pop
0xebc1  leave.s  loc_EBCD
0xebc3  ldloc.2
0xebc4  brfalse.s loc_EBCC
0xebc6  ldloc.2
0xebc7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xebcc  endfinally
0xebcd  ldarg.0
0xebce  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService Microsoft.Crm.CrmLive.Provisioning.OsdpCompanyStateChanger::_lifecycleService
0xebd3  ldc.i4.7
0xebd4  ldarg.0
0xebd5  ldfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleStatus Microsoft.Crm.CrmLive.Provisioning.OsdpCompanyStateChanger::_currentLifecycleStatus
0xebda  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0xebdf  ldarg.0
0xebe0  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.OsdpCompanyStateChanger::_organizationId
0xebe5  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::GetOrganizationName(valuetype [mscorlib]System.Guid)
0xebea  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::SwitchOrganizationLifecycleStatus(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleStatus, valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleStatus, string)
0xebef  ldarg.0
0xebf0  ldc.i4.7
0xebf1  stfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleStatus Microsoft.Crm.CrmLive.Provisioning.OsdpCompanyStateChanger::_currentLifecycleStatus
0xebf6  ldarg.0
0xebf7  ldc.i4.1
0xebf8  stfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.ServiceInstanceStatus Microsoft.Crm.CrmLive.Provisioning.OsdpCompanyStateChanger::_newStatus
0xebfd  ret
```
