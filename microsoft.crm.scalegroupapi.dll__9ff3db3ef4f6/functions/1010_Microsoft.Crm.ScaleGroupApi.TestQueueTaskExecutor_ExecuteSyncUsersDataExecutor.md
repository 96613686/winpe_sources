# Microsoft.Crm.ScaleGroupApi.TestQueueTaskExecutor::ExecuteSyncUsersDataExecutor

- ea: `0x1010`
- end: `0x1039`
- name: `Microsoft.Crm.ScaleGroupApi.TestQueueTaskExecutor::ExecuteSyncUsersDataExecutor`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xfa0`
- `0xfc0`
- `0xfd0`

## pseudocode

```c

```

## disassembly

```asm
0x1010  ldarg.0
0x1011  ldarg.3
0x1012  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x1017  call     T0x2B00000D
0x101c  call     instance void Microsoft.Crm.ScaleGroupApi.TestQueueTaskExecutor::set_BatchInfo(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.UserProvisioningBatchInfo value)
0x1021  ldarg.0
0x1022  ldc.i4.1
0x1023  call     instance void Microsoft.Crm.ScaleGroupApi.TestQueueTaskExecutor::set_ExecuteSyncUsersDataExecutorInvoked(bool value)
0x1028  ldarg.0
0x1029  call     instance class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult Microsoft.Crm.ScaleGroupApi.TestQueueTaskExecutor::get_TaskResultToReturn()
0x102e  ldsfld   string [mscorlib]System.String::Empty
0x1033  call     T0x2B00000C
0x1038  ret
```
