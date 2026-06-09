# Microsoft.Crm.CrmLive.Provisioning.OrganizationMoveAttachExecutor::Execute

- ea: `0x23840`
- end: `0x239c7`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationMoveAttachExecutor::Execute`
- size: `391`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x191d0`
- `0x1a3b0`
- `0x1a3e0`
- `0x1a500`
- `0x1bb50`
- `0x23840`

## string_xrefs

- `0x2387d`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\TaskExecutor\OrganizationMoveAttachExecutor.cs`
- `0x238b3`: `Org move attach operation`

## pseudocode

```c

```

## disassembly

```asm
0x23840  ldarg.1
0x23841  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x23846  stloc.0
0x23847  ldloc.0
0x23848  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemRuntimeData()
0x2384d  call     class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::Deserialize(string)
0x23852  stloc.1
0x23853  ldloc.0
0x23854  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x23859  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationMoveInfo [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationMoveInfo::Deserialize(string)
0x2385e  stloc.2
0x2385f  ldloc.1
0x23860  ldloc.2
0x23861  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationMoveInfo::get_TargetState()
0x23866  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::set_TargetState(valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState)
0x2386b  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x23870  ldloc.2
0x23871  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationMoveInfo::get_OrganizationId()
0x23876  ldc.i4.s 0x1E
0x23878  ldstr    aExecute// "Execute"
0x2387d  ldstr    aDDbsShDccm2110_36// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x23882  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationState(valuetype [mscorlib]System.Guid, int32, string, string)
0x23887  ldloc.2
0x23888  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationMoveInfo::get_OrganizationId()
0x2388d  ldstr    aOrganization// "Organization"
0x23892  ldstr    aAttach// "Attach"
0x23897  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.PerformanceAuditHistoryService::CreateStartEntry(valuetype [mscorlib]System.Guid, string, string)
0x2389c  ldc.i4.1
0x2389d  bne.un.s loc_238CB
0x2389f  call     class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient::ConnectLivePlatformService()
0x238a4  stloc.s  4
0x238a6  ldloc.s  4
0x238a8  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.LivePlatformService [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient::get_LivePlatformService()
0x238ad  ldloc.2
0x238ae  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationMoveInfo::get_OrganizationId()
0x238b3  ldstr    aOrgMoveAttachO// "Org move attach operation"
0x238b8  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.LivePlatformService::DisableOrganizationIgnoreBreakMirror(valuetype [mscorlib]System.Guid, string)
0x238bd  leave.s  loc_238CB
0x238bf  ldloc.s  4
0x238c1  brfalse.s loc_238CA
0x238c3  ldloc.s  4
0x238c5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x238ca  endfinally
0x238cb  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.Organization::.ctor()
0x238d0  stloc.3
0x238d1  ldloc.2
0x238d2  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationMoveInfo::get_TargetPrimarySqlServer()
0x238d7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x238dc  brfalse.s loc_23903
0x238de  ldloc.2
0x238df  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationMoveInfo::get_TargetSecondarySqlServer()
0x238e4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x238e9  brfalse.s loc_23903
0x238eb  ldloc.1
0x238ec  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_New()
0x238f1  ldnull
0x238f2  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::set_PrimaryServer(string)
0x238f7  ldloc.1
0x238f8  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_New()
0x238fd  ldnull
0x238fe  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::set_SecondaryServer(string)
0x23903  ldloc.3
0x23904  ldloc.1
0x23905  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.Organization::Attach(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData moveData)
0x2390a  ldloc.3
0x2390b  ldloc.2
0x2390c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationMoveInfo::get_OrganizationId()
0x23911  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.Organization::UpdateSecurityGroups(valuetype [mscorlib]System.Guid organizationId)
0x23916  ldloc.2
0x23917  callvirt instance bool [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationMoveInfo::get_DisableWorkflow()
0x2391c  brfalse.s loc_2392A
0x2391e  ldloc.3
0x2391f  ldloc.2
0x23920  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationMoveInfo::get_OrganizationId()
0x23925  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.Organization::DisableWorkflow(valuetype [mscorlib]System.Guid organizationId)
0x2392a  ldloc.2
0x2392b  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationMoveInfo::get_AdminToKeepAdmin()
0x23930  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x23935  brtrue.s loc_23949
0x23937  ldloc.3
0x23938  ldloc.2
0x23939  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationMoveInfo::get_OrganizationId()
0x2393e  ldloc.2
0x2393f  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationMoveInfo::get_AdminToKeepAdmin()
0x23944  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.Organization::DisableAllUsersExcept(valuetype [mscorlib]System.Guid organizationId, string adminUserToKeep)
0x23949  ldloc.1
0x2394a  callvirt instance valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveContext [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_Context()
0x2394f  ldc.i4.1
0x23950  beq.s    loc_23983
0x23952  ldloc.1
0x23953  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_TargetState()
0x23958  ldc.i4.1
0x23959  bne.un.s loc_23983
0x2395b  call     class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient::ConnectLivePlatformService()
0x23960  stloc.s  5
0x23962  ldloc.s  5
0x23964  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.LivePlatformService [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient::get_LivePlatformService()
0x23969  ldloc.1
0x2396a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x2396f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.LivePlatformService::EnableOrganization(valuetype [mscorlib]System.Guid)
0x23974  pop
0x23975  leave.s  loc_23983
0x23977  ldloc.s  5
0x23979  brfalse.s loc_23982
0x2397b  ldloc.s  5
0x2397d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x23982  endfinally
0x23983  leave.s  loc_239A6
0x23985  pop
0x23986  ldloc.1
0x23987  ldc.i4.0
0x23988  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::set_IsDatabasePrepared(bool)
0x2398d  rethrow
0x2398f  newobj   instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager::.ctor()
0x23994  ldloc.0
0x23995  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x2399a  ldloc.1
0x2399b  call     string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::Serialize(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData)
0x239a0  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager::UpdateQueueItemRuntimeData(valuetype [mscorlib]System.Guid, string)
0x239a5  endfinally
0x239a6  ldloc.2
0x239a7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationMoveInfo::get_OrganizationId()
0x239ac  ldstr    aOrganization// "Organization"
0x239b1  ldstr    aAttach// "Attach"
0x239b6  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.PerformanceAuditHistoryService::CreateEndEntry(valuetype [mscorlib]System.Guid, string, string)
0x239bb  ldc.i4.4
0x239bc  ldstr    aSuccess// "success"
0x239c1  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x239c6  ret
```
