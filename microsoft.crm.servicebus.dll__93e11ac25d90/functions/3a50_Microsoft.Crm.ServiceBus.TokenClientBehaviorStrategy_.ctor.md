# Microsoft.Crm.ServiceBus.TokenClientBehaviorStrategy::.ctor

- ea: `0x3a50`
- end: `0x3a58`
- name: `Microsoft.Crm.ServiceBus.TokenClientBehaviorStrategy::.ctor`
- size: `8`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3b90`

## callees

- `0x3a20`

## pseudocode

```c

```

## disassembly

```asm
0x3a50  ldarg.0
0x3a51  ldarg.1
0x3a52  call     instance void Microsoft.Crm.ServiceBus.AuthClientBehaviorStrategy::.ctor(class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation endpointInfo)
0x3a57  ret
```
