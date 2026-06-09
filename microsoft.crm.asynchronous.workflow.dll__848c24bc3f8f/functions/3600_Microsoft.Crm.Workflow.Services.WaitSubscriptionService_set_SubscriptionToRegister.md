# Microsoft.Crm.Workflow.Services.WaitSubscriptionService::set_SubscriptionToRegister

- ea: `0x3600`
- end: `0x3608`
- name: `Microsoft.Crm.Workflow.Services.WaitSubscriptionService::set_SubscriptionToRegister`
- size: `8`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x3450`

## pseudocode

```c

```

## disassembly

```asm
0x3600  ldarg.0
0x3601  ldarg.1
0x3602  stfld    class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WaitSubscription Microsoft.Crm.Workflow.Services.WaitSubscriptionService::_subscriptionToRegister
0x3607  ret
```
