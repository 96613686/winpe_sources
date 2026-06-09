# Microsoft.Crm.ServiceBus.ClientBehaviorStrategy::.ctor

- ea: `0x3b90`
- end: `0x3ba3`
- name: `Microsoft.Crm.ServiceBus.ClientBehaviorStrategy::.ctor`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x4560`

## callees

- `0x3a50`

## pseudocode

```c

```

## disassembly

```asm
0x3b90  ldarg.0
0x3b91  call     instance void [mscorlib]System.Object::.ctor()
0x3b96  ldarg.0
0x3b97  ldarg.1
0x3b98  newobj   instance void Microsoft.Crm.ServiceBus.TokenClientBehaviorStrategy::.ctor(class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation endpointInfo)
0x3b9d  stfld    class Microsoft.Crm.ServiceBus.IClientBehaviorStrategy Microsoft.Crm.ServiceBus.ClientBehaviorStrategy::selectedStrategy
0x3ba2  ret
```
