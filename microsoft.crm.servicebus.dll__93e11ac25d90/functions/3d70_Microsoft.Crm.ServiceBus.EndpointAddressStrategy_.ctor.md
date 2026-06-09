# Microsoft.Crm.ServiceBus.EndpointAddressStrategy::.ctor

- ea: `0x3d70`
- end: `0x3d88`
- name: `Microsoft.Crm.ServiceBus.EndpointAddressStrategy::.ctor`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x4540`

## callees

- `0x1630`
- `0x3db0`

## pseudocode

```c

```

## disassembly

```asm
0x3d70  ldarg.0
0x3d71  call     instance void [mscorlib]System.Object::.ctor()
0x3d76  ldarg.0
0x3d77  ldarg.1
0x3d78  callvirt instance class [System]System.Uri Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_Address()
0x3d7d  newobj   instance void Microsoft.Crm.ServiceBus.DefaultEndpointAddress::.ctor(class [System]System.Uri serviceUri)
0x3d82  stfld    class Microsoft.Crm.ServiceBus.IEndpointAddressStrategy Microsoft.Crm.ServiceBus.EndpointAddressStrategy::selectedStrategy
0x3d87  ret
```
