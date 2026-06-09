# Microsoft.Crm.ServiceBus.ServiceBusClientBase::.ctor

- ea: `0x4420`
- end: `0x4439`
- name: `Microsoft.Crm.ServiceBus.ServiceBusClientBase::.ctor`
- size: `25`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x4a90`
- `0x4c70`
- `0x4e20`
- `0x5550`

## callees

- `0x46a0`
- `0x46d0`

## pseudocode

```c

```

## disassembly

```asm
0x4420  ldarg.0
0x4421  call     instance void [mscorlib]System.Object::.ctor()
0x4426  ldarg.0
0x4427  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x442c  call     instance void Microsoft.Crm.ServiceBus.ServiceBusClientBase::set_Id(valuetype [mscorlib]System.Guid value)
0x4431  ldarg.0
0x4432  ldc.i4.0
0x4433  call     instance void Microsoft.Crm.ServiceBus.ServiceBusClientBase::set_Status(valuetype Microsoft.Crm.ServiceBus.ClientStatus value)
0x4438  ret
```
