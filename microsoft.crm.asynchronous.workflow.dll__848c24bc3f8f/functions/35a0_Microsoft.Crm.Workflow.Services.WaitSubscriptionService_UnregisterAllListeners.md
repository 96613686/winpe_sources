# Microsoft.Crm.Workflow.Services.WaitSubscriptionService::UnregisterAllListeners

- ea: `0x35a0`
- end: `0x35a8`
- name: `Microsoft.Crm.Workflow.Services.WaitSubscriptionService::UnregisterAllListeners`
- size: `8`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x740`

## callees

- `0x35b0`

## pseudocode

```c

```

## disassembly

```asm
0x35a0  ldarg.0
0x35a1  ldc.i4.0
0x35a2  call     instance void Microsoft.Crm.Workflow.Services.WaitSubscriptionService::UnregisterAllListeners(bool ignoreErrors)
0x35a7  ret
```
