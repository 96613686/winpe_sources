# Microsoft.Crm.CrmLive.Provisioning.OrganizationDeleteExecutor::Execute

- ea: `0x22bb0`
- end: `0x22d69`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDeleteExecutor::Execute`
- size: `441`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x187c0`
- `0x1bb50`
- `0x22bb0`
- `0x22d70`
- `0x2f0f0`

## string_xrefs

- `0x22ce1`: `CrmScaleGroupProvisioningService`
- `0x22d17`: `CrmScaleGroupProvisioningService`
- `0x22bef`: `Organization records does not exist in the Geo database for organizaiton {0} , delete operation completed.`

## pseudocode

```c

```

## disassembly

```asm
0x22bb0  ldnull
0x22bb1  stloc.0
0x22bb2  ldarg.1
0x22bb3  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x22bb8  stloc.1
0x22bb9  ldloc.1
0x22bba  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x22bbf  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDeleteInfo [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDeleteInfo::Deserialize(string)
0x22bc4  stloc.0
0x22bc5  ldloc.1
0x22bc6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x22bcb  call     void Microsoft.Crm.CrmLive.Provisioning.TracingListener::SetOrganizationId(valuetype [mscorlib]System.Guid organizationId)
0x22bd0  ldstr    aOrganizationDe_0// "Organization Details"
0x22bd5  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.CrmLiveContext::.ctor(string)
0x22bda  stloc.3
0x22bdb  ldarg.1
0x22bdc  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x22be1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x22be6  ldloc.3
0x22be7  call     bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::DoesOrganizationExist(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.CrmLiveContext)
0x22bec  brtrue.s loc_22C15
0x22bee  ldc.i4.4
0x22bef  ldstr    aOrganizationRe_0// "Organization records does not exist in "...
0x22bf4  ldarg.1
0x22bf5  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x22bfa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x22bff  box      [mscorlib]System.Guid
0x22c04  call     string [mscorlib]System.String::Format(string, object)
0x22c09  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x22c0e  stloc.s  4
0x22c10  leave    loc_22D66
0x22c15  leave.s  loc_22C21
0x22c17  ldloc.3
0x22c18  brfalse.s loc_22C20
0x22c1a  ldloc.3
0x22c1b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22c20  endfinally
0x22c21  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::.ctor()
0x22c26  stloc.2
0x22c27  ldloc.2
0x22c28  ldloc.1
0x22c29  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x22c2e  callvirt instance bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::IsOsdpOrganization(valuetype [mscorlib]System.Guid)
0x22c33  brfalse.s loc_22C77
0x22c35  ldloc.2
0x22c36  ldloc.1
0x22c37  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x22c3c  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::RetrieveOrganizationContextId(valuetype [mscorlib]System.Guid)
0x22c41  stloc.s  5
0x22c43  call     class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient::ConnectLivePlatformService()
0x22c48  stloc.s  6
0x22c4a  ldloc.s  6
0x22c4c  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.LivePlatformService [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient::get_LivePlatformService()
0x22c51  ldloc.0
0x22c52  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDeleteInfo::get_OrganizationId()
0x22c57  ldloca.s 5
0x22c59  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x22c5e  ldloc.0
0x22c5f  callvirt instance bool [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDeleteInfo::get_DeleteForSandboxInstanceReprovision()
0x22c64  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.LivePlatformService::OnOrganizationPreDelete(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, bool)
0x22c69  leave.s  loc_22C77
0x22c6b  ldloc.s  6
0x22c6d  brfalse.s loc_22C76
0x22c6f  ldloc.s  6
0x22c71  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22c76  endfinally
0x22c77  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.Organization::.ctor()
0x22c7c  ldloc.0
0x22c7d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDeleteInfo::get_OrganizationId()
0x22c82  ldloc.0
0x22c83  callvirt instance bool [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDeleteInfo::get_DeleteDatabase()
0x22c88  ldloc.0
0x22c89  callvirt instance bool [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDeleteInfo::get_DeleteForSandboxInstanceReprovision()
0x22c8e  ldloc.0
0x22c8f  callvirt instance bool [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDeleteInfo::get_IsCduPrevalidation()
0x22c94  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.Organization::Delete(valuetype [mscorlib]System.Guid organizationId, bool deleteDatabase, bool deleteForSandboxInstanceReprovision, bool IsCduPrevalidation)
0x22c99  leave    loc_22D5A
0x22c9e  stloc.s  7
0x22ca0  ldarg.1
0x22ca1  ldloc.0
0x22ca2  ldloc.s  7
0x22ca4  call     class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult Microsoft.Crm.CrmLive.Provisioning.OrganizationDeleteExecutor::BuildTaskResult(class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask task, class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDeleteInfo info, class [mscorlib]System.Exception ex)
0x22ca9  stloc.s  4
0x22cab  leave    loc_22D66
0x22cb0  stloc.s  8
0x22cb2  ldarg.1
0x22cb3  ldloc.0
0x22cb4  ldloc.s  8
0x22cb6  call     class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult Microsoft.Crm.CrmLive.Provisioning.OrganizationDeleteExecutor::BuildTaskResult(class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask task, class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDeleteInfo info, class [mscorlib]System.Exception ex)
0x22cbb  stloc.s  4
0x22cbd  leave    loc_22D66
0x22cc2  stloc.s  9
0x22cc4  ldarg.1
0x22cc5  ldloc.0
0x22cc6  ldloc.s  9
0x22cc8  call     class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult Microsoft.Crm.CrmLive.Provisioning.OrganizationDeleteExecutor::BuildTaskResult(class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask task, class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDeleteInfo info, class [mscorlib]System.Exception ex)
0x22ccd  stloc.s  4
0x22ccf  leave    loc_22D66
0x22cd4  pop
0x22cd5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0x22cda  stloc.s  0xA
0x22cdc  ldloc.0
0x22cdd  brtrue.s loc_22D15
0x22cdf  ldloc.s  0xA
0x22ce1  ldstr    aCrmscalegroupp// "CrmScaleGroupProvisioningService"
0x22ce6  ldc.i4.1
0x22ce7  ldc.i4   0xC0004622
0x22cec  conv.u8
0x22ced  ldc.i4.2
0x22cee  newarr   [mscorlib]System.Object
0x22cf3  dup
0x22cf4  ldc.i4.0
0x22cf5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x22cfa  box      [mscorlib]System.Guid
0x22cff  stelem.ref
0x22d00  dup
0x22d01  ldc.i4.1
0x22d02  ldloc.1
0x22d03  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x22d08  box      [mscorlib]System.Guid
0x22d0d  stelem.ref
0x22d0e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x22d13  br.s     loc_22D4A
0x22d15  ldloc.s  0xA
0x22d17  ldstr    aCrmscalegroupp// "CrmScaleGroupProvisioningService"
0x22d1c  ldc.i4.1
0x22d1d  ldc.i4   0xC0004622
0x22d22  conv.u8
0x22d23  ldc.i4.2
0x22d24  newarr   [mscorlib]System.Object
0x22d29  dup
0x22d2a  ldc.i4.0
0x22d2b  ldloc.0
0x22d2c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDeleteInfo::get_OrganizationId()
0x22d31  box      [mscorlib]System.Guid
0x22d36  stelem.ref
0x22d37  dup
0x22d38  ldc.i4.1
0x22d39  ldloc.1
0x22d3a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x22d3f  box      [mscorlib]System.Guid
0x22d44  stelem.ref
0x22d45  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x22d4a  leave.s  loc_22D58
0x22d4c  ldloc.s  0xA
0x22d4e  brfalse.s loc_22D57
0x22d50  ldloc.s  0xA
0x22d52  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22d57  endfinally
0x22d58  rethrow
0x22d5a  ldc.i4.4
0x22d5b  ldstr    aSuccess// "success"
0x22d60  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x22d65  ret
0x22d66  ldloc.s  4
0x22d68  ret
```
