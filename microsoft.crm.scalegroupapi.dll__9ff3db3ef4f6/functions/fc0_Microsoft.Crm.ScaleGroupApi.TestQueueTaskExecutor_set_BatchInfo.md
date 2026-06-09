# Microsoft.Crm.ScaleGroupApi.TestQueueTaskExecutor::set_BatchInfo

- ea: `0xfc0`
- end: `0xfc8`
- name: `Microsoft.Crm.ScaleGroupApi.TestQueueTaskExecutor::set_BatchInfo`
- size: `8`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1010`

## pseudocode

```c

```

## disassembly

```asm
0xfc0  ldarg.0
0xfc1  ldarg.1
0xfc2  stfld    class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.UserProvisioningBatchInfo Microsoft.Crm.ScaleGroupApi.TestQueueTaskExecutor::<BatchInfo>k__BackingField
0xfc7  ret
```
