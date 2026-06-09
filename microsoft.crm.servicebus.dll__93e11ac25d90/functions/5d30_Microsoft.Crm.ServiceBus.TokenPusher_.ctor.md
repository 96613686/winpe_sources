# Microsoft.Crm.ServiceBus.TokenPusher::.ctor

- ea: `0x5d30`
- end: `0x5d45`
- name: `Microsoft.Crm.ServiceBus.TokenPusher::.ctor`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3a60`

## callees

- `0x5d20`

## pseudocode

```c

```

## disassembly

```asm
0x5d30  ldarg.0
0x5d31  call     instance void [mscorlib]System.Object::.ctor()
0x5d36  ldarg.0
0x5d37  ldarg.1
0x5d38  stfld    class Microsoft.Crm.ServiceBus.TokenProvider Microsoft.Crm.ServiceBus.TokenPusher::_provider
0x5d3d  ldarg.0
0x5d3e  ldarg.2
0x5d3f  call     instance void Microsoft.Crm.ServiceBus.TokenPusher::set_ForServiceBusScope(bool value)
0x5d44  ret
```
