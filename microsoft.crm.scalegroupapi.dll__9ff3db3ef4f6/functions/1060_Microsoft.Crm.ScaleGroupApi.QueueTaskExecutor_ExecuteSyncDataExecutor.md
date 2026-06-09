# Microsoft.Crm.ScaleGroupApi.QueueTaskExecutor::ExecuteSyncDataExecutor

- ea: `0x1060`
- end: `0x107b`
- name: `Microsoft.Crm.ScaleGroupApi.QueueTaskExecutor::ExecuteSyncDataExecutor`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1060  newobj   instance void [Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor]Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::.ctor()
0x1065  ldarg.3
0x1066  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::.ctor(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem)
0x106b  callvirt instance class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult [Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor]Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::ExecuteSyncDataExecutor(class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask)
0x1070  ldsfld   string [mscorlib]System.String::Empty
0x1075  call     T0x2B00000C
0x107a  ret
```
