# Microsoft.Crm.CrmLive.Provisioning.ScaleGroupUpdateExecutor::MoveToNextStageAndSetTaskDependency

- ea: `0x28d00`
- end: `0x28d7a`
- name: `Microsoft.Crm.CrmLive.Provisioning.ScaleGroupUpdateExecutor::MoveToNextStageAndSetTaskDependency`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x28c50`

## callees

- `0x28a70`
- `0x28e10`

## string_xrefs

- `0x28d0b`: `Implementation assumes child item will be provided to set task dependency`
- `0x28d15`: `Setting next stage:  {0}: ChildTaskId: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x28d00  ldarg.2
0x28d01  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x28d06  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x28d0b  ldstr    aImplementation// "Implementation assumes child item will "...
0x28d10  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x28d15  ldstr    aSettingNextSta// "Setting next stage:  {0}: ChildTaskId: "...
0x28d1a  ldc.i4.2
0x28d1b  newarr   [mscorlib]System.Object
0x28d20  dup
0x28d21  ldc.i4.0
0x28d22  ldarga.s 1
0x28d24  constrained. Microsoft.Crm.CrmLive.Provisioning.ScaleGroupUpdateStage
0x28d2a  callvirt instance string [mscorlib]System.Object::ToString()
0x28d2f  stelem.ref
0x28d30  dup
0x28d31  ldc.i4.1
0x28d32  ldarga.s 2
0x28d34  constrained. [mscorlib]System.Guid
0x28d3a  callvirt instance string [mscorlib]System.Object::ToString()
0x28d3f  stelem.ref
0x28d40  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x28d45  ldarg.0
0x28d46  call     instance class Microsoft.Crm.CrmLive.Provisioning.ScaleGroupUpdateRuntimeData Microsoft.Crm.CrmLive.Provisioning.ScaleGroupUpdateExecutor::get_RuntimeData()
0x28d4b  ldarg.1
0x28d4c  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ScaleGroupUpdateRuntimeData::set_Stage(valuetype Microsoft.Crm.CrmLive.Provisioning.ScaleGroupUpdateStage value)
0x28d51  ldarg.0
0x28d52  ldfld    class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager Microsoft.Crm.CrmLive.Provisioning.ScaleGroupUpdateExecutor::_queueManager
0x28d57  ldarg.0
0x28d58  ldfld    class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem Microsoft.Crm.CrmLive.Provisioning.ScaleGroupUpdateExecutor::_queueItem
0x28d5d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x28d62  ldarg.0
0x28d63  call     instance class Microsoft.Crm.CrmLive.Provisioning.ScaleGroupUpdateRuntimeData Microsoft.Crm.CrmLive.Provisioning.ScaleGroupUpdateExecutor::get_RuntimeData()
0x28d68  call     T0x2B0000BF
0x28d6d  ldarg.2
0x28d6e  box      [mscorlib]System.Guid
0x28d73  ldnull
0x28d74  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager::UpdateQueueItem(valuetype [mscorlib]System.Guid, string, object, string)
0x28d79  ret
```
