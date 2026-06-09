# Microsoft.Crm.ServiceBus.AuthClientBehaviorStrategy::.ctor

- ea: `0x3a20`
- end: `0x3a2e`
- name: `Microsoft.Crm.ServiceBus.AuthClientBehaviorStrategy::.ctor`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x3a50`

## pseudocode

```c

```

## disassembly

```asm
0x3a20  ldarg.0
0x3a21  call     instance void [mscorlib]System.Object::.ctor()
0x3a26  ldarg.0
0x3a27  ldarg.1
0x3a28  stfld    class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.AuthClientBehaviorStrategy::endpointInfo
0x3a2d  ret
```
