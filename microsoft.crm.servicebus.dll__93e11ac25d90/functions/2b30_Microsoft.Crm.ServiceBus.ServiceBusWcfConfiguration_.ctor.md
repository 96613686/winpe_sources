# Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::.ctor

- ea: `0x2b30`
- end: `0x2b51`
- name: `Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::.ctor`
- size: `33`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x230`
- `0x3c90`
- `0x3d00`
- `0x3e60`

## pseudocode

```c

```

## disassembly

```asm
0x2b30  ldarg.0
0x2b31  call     instance void [mscorlib]System.Object::.ctor()
0x2b36  ldarg.0
0x2b37  ldarga.s 1
0x2b39  constrained. Microsoft.Crm.ServiceBus.ServiceBusPropertyPrefix
0x2b3f  callvirt instance string [mscorlib]System.Object::ToString()
0x2b44  stfld    string Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_propertyPrefix
0x2b49  ldarg.0
0x2b4a  ldarg.2
0x2b4b  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_orgId
0x2b50  ret
```
