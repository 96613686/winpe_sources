# Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::.ctor

- ea: `0x19c0`
- end: `0x19ce`
- name: `Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::.ctor`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x10`

## callees

- `0x1bc0`

## pseudocode

```c

```

## disassembly

```asm
0x19c0  ldarg.0
0x19c1  call     instance void [mscorlib]System.Object::.ctor()
0x19c6  ldarg.0
0x19c7  ldc.i4.0
0x19c8  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_ValidateOnly(bool value)
0x19cd  ret
```
