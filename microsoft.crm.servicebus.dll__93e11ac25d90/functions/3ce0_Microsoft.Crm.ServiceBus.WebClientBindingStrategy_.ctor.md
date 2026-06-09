# Microsoft.Crm.ServiceBus.WebClientBindingStrategy::.ctor

- ea: `0x3ce0`
- end: `0x3cfa`
- name: `Microsoft.Crm.ServiceBus.WebClientBindingStrategy::.ctor`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3bf0`

## callees

- `0x1470`

## pseudocode

```c

```

## disassembly

```asm
0x3ce0  ldarg.0
0x3ce1  call     instance void [mscorlib]System.Object::.ctor()
0x3ce6  ldarg.0
0x3ce7  ldc.i4.1
0x3ce8  stfld    valuetype [Microsoft.ServiceBus]Microsoft.ServiceBus.EndToEndWebHttpSecurityMode Microsoft.Crm.ServiceBus.WebClientBindingStrategy::securityMode
0x3ced  ldarg.0
0x3cee  ldarg.1
0x3cef  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_OrganizationId()
0x3cf4  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.WebClientBindingStrategy::orgId
0x3cf9  ret
```
