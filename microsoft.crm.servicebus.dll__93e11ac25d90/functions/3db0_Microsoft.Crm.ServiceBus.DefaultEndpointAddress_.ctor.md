# Microsoft.Crm.ServiceBus.DefaultEndpointAddress::.ctor

- ea: `0x3db0`
- end: `0x3dbe`
- name: `Microsoft.Crm.ServiceBus.DefaultEndpointAddress::.ctor`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x3d70`

## pseudocode

```c

```

## disassembly

```asm
0x3db0  ldarg.0
0x3db1  call     instance void [mscorlib]System.Object::.ctor()
0x3db6  ldarg.0
0x3db7  ldarg.1
0x3db8  stfld    class [System]System.Uri Microsoft.Crm.ServiceBus.DefaultEndpointAddress::serviceUri
0x3dbd  ret
```
