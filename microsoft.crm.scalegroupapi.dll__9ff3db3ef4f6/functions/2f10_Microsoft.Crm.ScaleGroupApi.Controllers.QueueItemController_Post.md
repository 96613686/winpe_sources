# Microsoft.Crm.ScaleGroupApi.Controllers.QueueItemController::Post

- ea: `0x2f10`
- end: `0x3047`
- name: `Microsoft.Crm.ScaleGroupApi.Controllers.QueueItemController::Post`
- size: `311`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x1620`
- `0x1630`
- `0x1640`
- `0x1660`
- `0x1680`
- `0x2f10`
- `0x3070`

## string_xrefs

- `0x2f19`: `Only queue item type 2 (CreateOrganization) is supported`
- `0x2fd5`: `Task did not complete successfully : `

## pseudocode

```c

```

## disassembly

```asm
0x2f10  ldarg.1
0x2f11  callvirt instance int32 Microsoft.Crm.ScaleGroupApi.Models.SGQueueItem::get_ItemType()
0x2f16  ldc.i4.2
0x2f17  beq.s    loc_2F24
0x2f19  ldstr    aOnlyQueueItemT// "Only queue item type 2 (CreateOrganizat"...
0x2f1e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x2f23  throw
0x2f24  ldarg.1
0x2f25  callvirt instance string Microsoft.Crm.ScaleGroupApi.Models.SGQueueItem::get_ItemData()
0x2f2a  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfo [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfo::Deserialize(string)
0x2f2f  stloc.0
0x2f30  ldloc.0
0x2f31  callvirt instance bool [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfo::get_AssociatePlaceholder()
0x2f36  brtrue.s loc_2F43
0x2f38  ldstr    aOnlyAssociatep// "Only AssociatePlaceholder requests are "...
0x2f3d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x2f42  throw
0x2f43  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::.ctor()
0x2f48  ldarg.1
0x2f49  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGQueueItem::get_OrganizationId()
0x2f4e  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::RetrieveOrganizationContextId(valuetype [mscorlib]System.Guid)
0x2f53  stloc.1
0x2f54  ldstr    aAssociateplace// "AssociatePlaceholderSynchronously"
0x2f59  ldloc.1
0x2f5a  call     bool [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClientHelper::IsGeoFeatureEnabledForContext(string, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x2f5f  brtrue.s loc_2F68
0x2f61  ldarg.1
0x2f62  call     class Microsoft.Crm.ScaleGroupApi.Models.SGQueueItem Microsoft.Crm.ScaleGroupApi.Controllers.QueueItemController::CreateTask(class Microsoft.Crm.ScaleGroupApi.Models.SGQueueItem value)
0x2f67  ret
0x2f68  nop
0x2f69  newobj   instance void [Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupTaskExecutorFactory::.ctor()
0x2f6e  ldarg.1
0x2f6f  callvirt instance int32 Microsoft.Crm.ScaleGroupApi.Models.SGQueueItem::get_ItemType()
0x2f74  ldarg.1
0x2f75  callvirt instance string Microsoft.Crm.ScaleGroupApi.Models.SGQueueItem::get_ItemData()
0x2f7a  newobj   instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem::.ctor(valuetype [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemType, string)
0x2f7f  stloc.2
0x2f80  ldloc.2
0x2f81  ldarg.1
0x2f82  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGQueueItem::get_OrganizationId()
0x2f87  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_OrganizationId(valuetype [mscorlib]System.Guid)
0x2f8c  ldloc.2
0x2f8d  ldarg.1
0x2f8e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGQueueItem::get_QueueItemId()
0x2f93  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_QueueItemId(valuetype [mscorlib]System.Guid)
0x2f98  ldloc.2
0x2f99  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::.ctor(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem)
0x2f9e  stloc.3
0x2f9f  ldloc.3
0x2fa0  callvirt instance class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.ITaskExecutor [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.TaskExecutorFactory::CreateTaskExecutor(class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.ITask)
0x2fa5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x2faa  stloc.s  4
0x2fac  ldloc.3
0x2fad  callvirt instance class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.ITaskExecutor::Execute(class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.ITask)
0x2fb2  stloc.s  5
0x2fb4  call     class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTelemetryEvents [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTelemetryEvents::get_Instance()
0x2fb9  ldstr    aAssociateplace// "AssociatePlaceholderSynchronously"
0x2fbe  ldloc.2
0x2fbf  ldloc.s  4
0x2fc1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x2fc6  callvirt instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTelemetryEvents::OperationCompleted(string, class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken)
0x2fcb  ldloc.s  5
0x2fcd  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::get_Status()
0x2fd2  ldc.i4.4
0x2fd3  beq.s    loc_2FEC
0x2fd5  ldstr    aTaskDidNotComp// "Task did not complete successfully : "
0x2fda  ldloc.s  5
0x2fdc  callvirt instance string [mscorlib]System.Object::ToString()
0x2fe1  call     string [mscorlib]System.String::Concat(string, string)
0x2fe6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x2feb  throw
0x2fec  ldarg.1
0x2fed  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2ff2  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGQueueItem::set_QueueItemId(valuetype [mscorlib]System.Guid value)
0x2ff7  ldarg.1
0x2ff8  stloc.s  6
0x2ffa  leave.s  loc_3044
0x2ffc  stloc.s  7
0x2ffe  call     class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.AuditHistory::NewService()
0x3003  ldarg.1
0x3004  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGQueueItem::get_OrganizationId()
0x3009  ldstr    aOrganization_0// "Organization"
0x300e  ldstr    aAssociateplace_0// "AssociatePlaceholderInSgApi"
0x3013  ldstr    aFailed// "Failed : "
0x3018  ldloc.s  7
0x301a  callvirt instance string [mscorlib]System.Object::ToString()
0x301f  call     string [mscorlib]System.String::Concat(string, string)
0x3024  ldc.i4.0
0x3025  ldarg.1
0x3026  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGQueueItem::get_OrganizationId()
0x302b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory::CreateCompletedEntry(valuetype [mscorlib]System.Guid, string, string, string, bool, valuetype [mscorlib]System.Guid)
0x3030  ldloc.0
0x3031  callvirt instance bool [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfo::get_PerformSingleAttemptOnly()
0x3036  brfalse.s loc_303A
0x3038  rethrow
0x303a  ldarg.1
0x303b  call     class Microsoft.Crm.ScaleGroupApi.Models.SGQueueItem Microsoft.Crm.ScaleGroupApi.Controllers.QueueItemController::CreateTask(class Microsoft.Crm.ScaleGroupApi.Models.SGQueueItem value)
0x3040  stloc.s  6
0x3042  leave.s  loc_3044
0x3044  ldloc.s  6
0x3046  ret
```
