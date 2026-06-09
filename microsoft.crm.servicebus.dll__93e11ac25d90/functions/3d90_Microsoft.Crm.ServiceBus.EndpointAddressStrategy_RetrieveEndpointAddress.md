# Microsoft.Crm.ServiceBus.EndpointAddressStrategy::RetrieveEndpointAddress

- ea: `0x3d90`
- end: `0x3d9c`
- name: `Microsoft.Crm.ServiceBus.EndpointAddressStrategy::RetrieveEndpointAddress`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x3d50`

## pseudocode

```c

```

## disassembly

```asm
0x3d90  ldarg.0
0x3d91  ldfld    class Microsoft.Crm.ServiceBus.IEndpointAddressStrategy Microsoft.Crm.ServiceBus.EndpointAddressStrategy::selectedStrategy
0x3d96  callvirt instance class [System.ServiceModel]System.ServiceModel.EndpointAddress Microsoft.Crm.ServiceBus.IEndpointAddressStrategy::RetrieveEndpointAddress()
0x3d9b  ret
```
