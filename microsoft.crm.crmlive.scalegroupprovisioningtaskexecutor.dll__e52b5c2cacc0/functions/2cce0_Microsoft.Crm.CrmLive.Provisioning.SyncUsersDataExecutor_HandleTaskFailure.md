# Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutor::HandleTaskFailure

- ea: `0x2cce0`
- end: `0x2ce52`
- name: `Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutor::HandleTaskFailure`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x2bd10`

## callees

- `0x2cca0`
- `0x2cce0`
- `0x2cec0`
- `0x2ecd0`
- `0x2edb0`
- `0x2edf0`
- `0x339c0`

## string_xrefs

- `0x2cd3f`: `HandleTaskFailure`
- `0x2cdef`: `HandleTaskFailure`

## pseudocode

```c

```

## disassembly

```asm
0x2cce0  newobj   instance void <>c__DisplayClass21_0::.ctor()
0x2cce5  stloc.0
0x2cce6  ldloc.0
0x2cce7  ldarg.s  4
0x2cce9  stfld    class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass21_0::usersNotYetSynced
0x2ccee  ldarg.0
0x2ccef  call     valuetype Microsoft.Crm.CrmLive.Provisioning.SyncUserErrorResponse Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutor::GetErrorResponse(class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask task)
0x2ccf4  stloc.1
0x2ccf5  ldloc.1
0x2ccf6  ldc.i4.1
0x2ccf7  bne.un.s loc_2CD12
0x2ccf9  ldarg.3
0x2ccfa  ldloc.0
0x2ccfb  ldftn    instance bool <>c__DisplayClass21_0::<HandleTaskFailure>b__0(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser x)
0x2cd01  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser, bool>::.ctor(object, native int)
0x2cd06  call     T0x2B0000D2
0x2cd0b  call     T0x2B0000D3
0x2cd10  starg.s  3
0x2cd12  ldarg.s  5
0x2cd14  brfalse.s loc_2CD22
0x2cd16  ldloc.1
0x2cd17  ldc.i4.2
0x2cd18  beq.s    loc_2CD22
0x2cd1a  ldarg.3
0x2cd1b  call     T0x2B00005D
0x2cd20  brtrue.s loc_2CD98
0x2cd22  call     class Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource::get_Instance()
0x2cd27  ldarg.0
0x2cd28  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2cd2d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x2cd32  ldarg.0
0x2cd33  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2cd38  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x2cd3d  ldarg.1
0x2cd3e  ldarg.2
0x2cd3f  ldstr    aHandletaskfail// "HandleTaskFailure"
0x2cd44  ldarga.s 6
0x2cd46  constrained. Microsoft.Crm.CrmLive.Provisioning.UserProvisioningRequestSource
0x2cd4c  callvirt instance string [mscorlib]System.Object::ToString()
0x2cd51  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource::FailureNoRetry(valuetype [mscorlib]System.Guid queueItemId, valuetype [mscorlib]System.Guid organizationId, int32 errorCount, int32 totalUsers, string context, string provisioningRequestSource)
0x2cd56  ldc.i4.s 0xB
0x2cd58  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2cd5d  ldstr    aQueueitemid0Ha_0// "QueueItemId {0} has failed to provision"...
0x2cd62  ldc.i4.3
0x2cd63  newarr   [mscorlib]System.Object
0x2cd68  dup
0x2cd69  ldc.i4.0
0x2cd6a  ldarg.0
0x2cd6b  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2cd70  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x2cd75  box      [mscorlib]System.Guid
0x2cd7a  stelem.ref
0x2cd7b  dup
0x2cd7c  ldc.i4.1
0x2cd7d  ldarg.1
0x2cd7e  box      [mscorlib]System.Int32
0x2cd83  stelem.ref
0x2cd84  dup
0x2cd85  ldc.i4.2
0x2cd86  ldarg.2
0x2cd87  box      [mscorlib]System.Int32
0x2cd8c  stelem.ref
0x2cd8d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2cd92  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x2cd97  ret
0x2cd98  ldarg.0
0x2cd99  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2cd9e  ldloc.1
0x2cd9f  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutor::BuildQueueItemForFastRetry(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem oldItem, valuetype Microsoft.Crm.CrmLive.Provisioning.SyncUserErrorResponse errorResponse)
0x2cda4  stloc.2
0x2cda5  newobj   instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.UserProvisioningBatchInfo::.ctor()
0x2cdaa  stloc.3
0x2cdab  ldloc.3
0x2cdac  ldarg.3
0x2cdad  call     T0x2B0000C6
0x2cdb2  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.UserProvisioningBatchInfo::set_Users(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser[])
0x2cdb7  ldloc.2
0x2cdb8  ldloc.3
0x2cdb9  call     T0x2B00004E
0x2cdbe  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_ItemData(string)
0x2cdc3  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemRequest [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemRequest::NewRequest()
0x2cdc8  ldloc.2
0x2cdc9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemRequest::CreateReady(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase)
0x2cdce  stloc.s  4
0x2cdd0  call     class Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource::get_Instance()
0x2cdd5  ldarg.0
0x2cdd6  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2cddb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x2cde0  ldarg.0
0x2cde1  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2cde6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x2cdeb  ldarg.1
0x2cdec  ldarg.2
0x2cded  ldloc.s  4
0x2cdef  ldstr    aHandletaskfail// "HandleTaskFailure"
0x2cdf4  ldarga.s 6
0x2cdf6  constrained. Microsoft.Crm.CrmLive.Provisioning.UserProvisioningRequestSource
0x2cdfc  callvirt instance string [mscorlib]System.Object::ToString()
0x2ce01  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource::FailureWithRetry(valuetype [mscorlib]System.Guid queueItemId, valuetype [mscorlib]System.Guid organizationId, int32 errorCount, int32 totalUsers, valuetype [mscorlib]System.Guid newItem, string context, string provisioningRequestSource)
0x2ce06  ldc.i4.s 0xB
0x2ce08  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2ce0d  ldstr    aQueueitemid0Ha_1// "QueueItemId {0} has failed to provision"...
0x2ce12  ldc.i4.4
0x2ce13  newarr   [mscorlib]System.Object
0x2ce18  dup
0x2ce19  ldc.i4.0
0x2ce1a  ldarg.0
0x2ce1b  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2ce20  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x2ce25  box      [mscorlib]System.Guid
0x2ce2a  stelem.ref
0x2ce2b  dup
0x2ce2c  ldc.i4.1
0x2ce2d  ldarg.1
0x2ce2e  box      [mscorlib]System.Int32
0x2ce33  stelem.ref
0x2ce34  dup
0x2ce35  ldc.i4.2
0x2ce36  ldarg.2
0x2ce37  box      [mscorlib]System.Int32
0x2ce3c  stelem.ref
0x2ce3d  dup
0x2ce3e  ldc.i4.3
0x2ce3f  ldloc.s  4
0x2ce41  box      [mscorlib]System.Guid
0x2ce46  stelem.ref
0x2ce47  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2ce4c  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x2ce51  ret
```
