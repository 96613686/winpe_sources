# Microsoft.Crm.CrmLive.Provisioning.DropXdbDatabaseExecutor::TaskCancelledBuildRetry

- ea: `0x13be0`
- end: `0x13c95`
- name: `Microsoft.Crm.CrmLive.Provisioning.DropXdbDatabaseExecutor::TaskCancelledBuildRetry`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x13850`

## callees

- `0x137f0`
- `0x13800`
- `0x13810`
- `0x13be0`

## string_xrefs

- `0x13be5`: `TaskCanceledExceptionMaxRetryCount`
- `0x13c0e`: `SpartanTaskRetryDurationInSeconds`

## pseudocode

```c

```

## disassembly

```asm
0x13be0  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x13be5  ldstr    aTaskcanceledex// "TaskCanceledExceptionMaxRetryCount"
0x13bea  ldc.i4.0
0x13beb  callvirt T0x2B000069
0x13bf0  stloc.3
0x13bf1  ldloca.s 3
0x13bf3  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x13bf8  brtrue.s loc_13C01
0x13bfa  ldc.i4   0x12C
0x13bff  br.s     loc_13C08
0x13c01  ldloca.s 3
0x13c03  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x13c08  stloc.0
0x13c09  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x13c0e  ldstr    aSpartantaskret// "SpartanTaskRetryDurationInSeconds"
0x13c13  ldc.i4.0
0x13c14  callvirt T0x2B000069
0x13c19  stloc.3
0x13c1a  ldloca.s 3
0x13c1c  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x13c21  brtrue.s loc_13C2A
0x13c23  ldc.i4   0x12C
0x13c28  br.s     loc_13C31
0x13c2a  ldloca.s 3
0x13c2c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x13c31  stloc.1
0x13c32  ldarg.3
0x13c33  callvirt instance int32 Microsoft.Crm.CrmLive.Provisioning.DropXdbDatabaseRuntimeData::get_TaskCancelledRetryCount()
0x13c38  ldc.i4.1
0x13c39  add
0x13c3a  ldc.i4.s 0x3C
0x13c3c  mul
0x13c3d  ldloc.1
0x13c3e  bgt.s    loc_13C43
0x13c40  ldloc.1
0x13c41  br.s     loc_13C4E
0x13c43  ldarg.3
0x13c44  callvirt instance int32 Microsoft.Crm.CrmLive.Provisioning.DropXdbDatabaseRuntimeData::get_TaskCancelledRetryCount()
0x13c49  ldc.i4.1
0x13c4a  add
0x13c4b  ldc.i4.s 0x3C
0x13c4d  mul
0x13c4e  stloc.2
0x13c4f  ldarg.3
0x13c50  dup
0x13c51  callvirt instance int32 Microsoft.Crm.CrmLive.Provisioning.DropXdbDatabaseRuntimeData::get_TaskCancelledRetryCount()
0x13c56  stloc.s  4
0x13c58  ldloc.s  4
0x13c5a  ldc.i4.1
0x13c5b  add
0x13c5c  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.DropXdbDatabaseRuntimeData::set_TaskCancelledRetryCount(int32 value)
0x13c61  ldarg.2
0x13c62  ldarg.1
0x13c63  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x13c68  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x13c6d  ldarg.3
0x13c6e  call     T0x2B00006B
0x13c73  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager::UpdateQueueItemRuntimeData(valuetype [mscorlib]System.Guid, string)
0x13c78  ldc.i4.0
0x13c79  ldarg.0
0x13c7a  ldnull
0x13c7b  ldarg.1
0x13c7c  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x13c81  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_RetryCount()
0x13c86  ldloc.2
0x13c87  ldloc.0
0x13c88  ldarg.3
0x13c89  callvirt instance int32 Microsoft.Crm.CrmLive.Provisioning.DropXdbDatabaseRuntimeData::get_SpartanRetryCount()
0x13c8e  add
0x13c8f  call     class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::BuildRetry(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string, class [mscorlib]System.Exception, int32, int32, int32)
0x13c94  ret
```
