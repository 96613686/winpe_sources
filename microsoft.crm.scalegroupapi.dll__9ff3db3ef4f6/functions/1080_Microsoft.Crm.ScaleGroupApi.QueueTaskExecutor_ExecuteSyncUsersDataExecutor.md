# Microsoft.Crm.ScaleGroupApi.QueueTaskExecutor::ExecuteSyncUsersDataExecutor

- ea: `0x1080`
- end: `0x10a4`
- name: `Microsoft.Crm.ScaleGroupApi.QueueTaskExecutor::ExecuteSyncUsersDataExecutor`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1080  newobj   instance void [Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor]Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutor::.ctor()
0x1085  ldarg.3
0x1086  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::.ctor(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem)
0x108b  ldc.i4.0
0x108c  callvirt instance class [Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor]Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutionResult [Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor]Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutor::ExecuteSyncUsersDataExecutor(class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask, bool)
0x1091  stloc.0
0x1092  ldloc.0
0x1093  callvirt instance class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult [Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor]Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutionResult::get_Result()
0x1098  ldloc.0
0x1099  callvirt instance string [Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor]Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutionResult::get_TaskLog()
0x109e  call     T0x2B00000C
0x10a3  ret
```
