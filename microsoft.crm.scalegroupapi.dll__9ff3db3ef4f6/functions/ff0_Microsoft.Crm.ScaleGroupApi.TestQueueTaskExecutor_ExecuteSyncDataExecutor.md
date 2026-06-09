# Microsoft.Crm.ScaleGroupApi.TestQueueTaskExecutor::ExecuteSyncDataExecutor

- ea: `0xff0`
- end: `0x1008`
- name: `Microsoft.Crm.ScaleGroupApi.TestQueueTaskExecutor::ExecuteSyncDataExecutor`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xf80`
- `0xfd0`

## pseudocode

```c

```

## disassembly

```asm
0xff0  ldarg.0
0xff1  ldc.i4.1
0xff2  call     instance void Microsoft.Crm.ScaleGroupApi.TestQueueTaskExecutor::set_ExecuteSyncDataExecutorInvoked(bool value)
0xff7  ldarg.0
0xff8  call     instance class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult Microsoft.Crm.ScaleGroupApi.TestQueueTaskExecutor::get_TaskResultToReturn()
0xffd  ldsfld   string [mscorlib]System.String::Empty
0x1002  call     T0x2B00000C
0x1007  ret
```
