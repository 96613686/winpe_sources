# Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeExecutor::Execute

- ea: `0x25630`
- end: `0x256dd`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeExecutor::Execute`
- size: `173`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x3e0`
- `0x256e0`
- `0x32f50`

## string_xrefs

- `0x2564e`: `task.QueueItem`
- `0x2567b`: `Parameter 'task' of unexpected type`
- `0x25663`: `task.QueueItem.ItemData`

## pseudocode

```c

```

## disassembly

```asm
0x25630  newobj   instance void <>c__DisplayClass5_0::.ctor()
0x25635  stloc.0
0x25636  ldloc.0
0x25637  ldarg.0
0x25638  stfld    class Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeExecutor <>c__DisplayClass5_0::<>4__this
0x2563d  ldarg.1
0x2563e  ldstr    aTask// "task"
0x25643  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x25648  ldarg.1
0x25649  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2564e  ldstr    aTaskQueueitem// "task.QueueItem"
0x25653  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x25658  ldarg.1
0x25659  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2565e  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x25663  ldstr    aTaskQueueitemI// "task.QueueItem.ItemData"
0x25668  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x2566d  ldarg.1
0x2566e  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x25673  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemType()
0x25678  ldc.i4.6
0x25679  ceq
0x2567b  ldstr    aParameterTaskO// "Parameter 'task' of unexpected type"
0x25680  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x25685  ldarg.1
0x25686  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x2568b  stloc.1
0x2568c  ldloc.0
0x2568d  ldloc.1
0x2568e  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x25693  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeInfo [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeInfo::Deserialize(string)
0x25698  stfld    class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeInfo <>c__DisplayClass5_0::upgradeInfo
0x2569d  ldarg.0
0x2569e  ldloc.0
0x2569f  ldfld    class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeInfo <>c__DisplayClass5_0::upgradeInfo
0x256a4  call     instance int32 Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeExecutor::GetTimeLimit(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpgradeInfo upgradeInfo)
0x256a9  conv.r8
0x256aa  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x256af  stloc.2
0x256b0  ldloc.0
0x256b1  ldnull
0x256b2  stfld    class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult <>c__DisplayClass5_0::result
0x256b7  ldarg.0
0x256b8  ldloc.0
0x256b9  ldftn    instance void <>c__DisplayClass5_0::<Execute>b__0()
0x256bf  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x256c4  ldloc.2
0x256c5  ldloc.1
0x256c6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x256cb  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x256d0  ldc.i4.0
0x256d1  call     void Microsoft.Crm.CrmLive.TaskExecutorBaseExtensions::ExecuteActionWithTimeLimit(class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.TaskExecutorBase taskExecutorBase, class [mscorlib]System.Action taskAction, valuetype [mscorlib]System.TimeSpan timeLimit, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> queueItemId, [opt] bool attemptCallStackRetrieval)
0x256d6  ldloc.0
0x256d7  ldfld    class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult <>c__DisplayClass5_0::result
0x256dc  ret
```
