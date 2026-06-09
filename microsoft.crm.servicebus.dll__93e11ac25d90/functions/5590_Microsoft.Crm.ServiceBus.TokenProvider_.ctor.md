# Microsoft.Crm.ServiceBus.TokenProvider::.ctor

- ea: `0x5590`
- end: `0x559e`
- name: `Microsoft.Crm.ServiceBus.TokenProvider::.ctor`
- size: `14`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3a60`
- `0x3ac0`
- `0x42e0`
- `0x4450`

## callees

- `0x5580`

## pseudocode

```c

```

## disassembly

```asm
0x5590  ldarg.0
0x5591  call     instance void [mscorlib]System.Object::.ctor()
0x5596  ldarg.0
0x5597  ldarg.1
0x5598  call     instance void Microsoft.Crm.ServiceBus.TokenProvider::set_EndpointInfo(class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation value)
0x559d  ret
```
