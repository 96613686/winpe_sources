# Microsoft.Crm.CrmLive.Provisioning.InvitationUpdateExecutor::Execute

- ea: `0x222a0`
- end: `0x22378`
- name: `Microsoft.Crm.CrmLive.Provisioning.InvitationUpdateExecutor::Execute`
- size: `216`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1c0f0`
- `0x1c3b0`
- `0x222a0`

## string_xrefs

- `0x222b1`: `task.QueueItem`
- `0x222df`: `Parameter 'task' of unexpected type`
- `0x222c6`: `task.QueueItem.ItemData`

## pseudocode

```c

```

## disassembly

```asm
0x222a0  ldarg.1
0x222a1  ldstr    aTask// "task"
0x222a6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x222ab  ldarg.1
0x222ac  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x222b1  ldstr    aTaskQueueitem// "task.QueueItem"
0x222b6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x222bb  ldarg.1
0x222bc  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x222c1  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x222c6  ldstr    aTaskQueueitemI// "task.QueueItem.ItemData"
0x222cb  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x222d0  ldarg.1
0x222d1  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x222d6  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemType()
0x222db  ldc.i4.s 9
0x222dd  ceq
0x222df  ldstr    aParameterTaskO// "Parameter 'task' of unexpected type"
0x222e4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x222e9  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x222ee  stloc.0
0x222ef  ldarg.1
0x222f0  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x222f5  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x222fa  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.SystemUserInvitationUpdateInfo [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.SystemUserInvitationUpdateInfo::Deserialize(string)
0x222ff  stloc.1
0x22300  ldloc.1
0x22301  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.SystemUserInvitationUpdateInfo::get_OrganizationId()
0x22306  stloc.0
0x22307  call     class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::NewService()
0x2230c  ldloc.1
0x2230d  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::UpdateSystemUser(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.SystemUserInvitationUpdateInfo inviteUpdateInfo)
0x22312  leave.s  loc_2236E
0x22314  stloc.2
0x22315  ldloc.2
0x22316  ldloc.0
0x22317  ldc.i4.s 0xA
0x22319  ldstr    aExceptionUpdat// "Exception updating invitation status co"...
0x2231e  ldc.i4.1
0x2231f  newarr   [mscorlib]System.Object
0x22324  dup
0x22325  ldc.i4.0
0x22326  ldloc.2
0x22327  callvirt instance string [mscorlib]System.Object::ToString()
0x2232c  stelem.ref
0x2232d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x22332  ldloc.2
0x22333  isinst   [System.Data]System.Data.SqlClient.SqlException
0x22338  ldloc.2
0x22339  isinst   class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>
0x2233e  stloc.3
0x2233f  brtrue.s loc_22356
0x22341  ldloc.3
0x22342  brfalse.s loc_2236C
0x22344  ldloc.3
0x22345  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x2234a  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x2234f  ldc.i4   0x80044150
0x22354  bne.un.s loc_2236C
0x22356  ldnull
0x22357  ldloc.2
0x22358  ldarg.1
0x22359  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2235e  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_RetryCount()
0x22363  call     class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::BuildRetry(string, class [mscorlib]System.Exception, int32)
0x22368  stloc.s  4
0x2236a  leave.s  loc_22375
0x2236c  rethrow
0x2236e  ldc.i4.4
0x2236f  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus)
0x22374  ret
0x22375  ldloc.s  4
0x22377  ret
```
