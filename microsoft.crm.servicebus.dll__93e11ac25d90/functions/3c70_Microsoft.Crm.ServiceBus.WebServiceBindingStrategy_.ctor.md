# Microsoft.Crm.ServiceBus.WebServiceBindingStrategy::.ctor

- ea: `0x3c70`
- end: `0x3c8a`
- name: `Microsoft.Crm.ServiceBus.WebServiceBindingStrategy::.ctor`
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
0x3c70  ldarg.0
0x3c71  call     instance void [mscorlib]System.Object::.ctor()
0x3c76  ldarg.0
0x3c77  ldc.i4.1
0x3c78  stfld    valuetype [Microsoft.ServiceBus]Microsoft.ServiceBus.EndToEndSecurityMode Microsoft.Crm.ServiceBus.WebServiceBindingStrategy::securityMode
0x3c7d  ldarg.0
0x3c7e  ldarg.1
0x3c7f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_OrganizationId()
0x3c84  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.WebServiceBindingStrategy::orgId
0x3c89  ret
```
