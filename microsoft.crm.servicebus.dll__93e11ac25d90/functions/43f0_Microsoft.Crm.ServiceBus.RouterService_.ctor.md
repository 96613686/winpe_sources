# Microsoft.Crm.ServiceBus.RouterService::.ctor

- ea: `0x43f0`
- end: `0x4402`
- name: `Microsoft.Crm.ServiceBus.RouterService::.ctor`
- size: `18`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x420`
- `0x430`

## pseudocode

```c

```

## disassembly

```asm
0x43f0  ldarg.0
0x43f1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x43f6  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.RouterService::_privUserGroupId
0x43fb  ldarg.0
0x43fc  call     instance void [mscorlib]System.Object::.ctor()
0x4401  ret
```
