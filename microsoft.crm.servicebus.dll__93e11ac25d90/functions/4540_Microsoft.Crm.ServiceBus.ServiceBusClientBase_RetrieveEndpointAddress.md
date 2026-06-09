# Microsoft.Crm.ServiceBus.ServiceBusClientBase::RetrieveEndpointAddress

- ea: `0x4540`
- end: `0x454c`
- name: `Microsoft.Crm.ServiceBus.ServiceBusClientBase::RetrieveEndpointAddress`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x4500`

## callees

- `0x3d50`
- `0x3d70`

## pseudocode

```c

```

## disassembly

```asm
0x4540  ldarg.1
0x4541  newobj   instance void Microsoft.Crm.ServiceBus.EndpointAddressStrategy::.ctor(class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation endpointInfo)
0x4546  callvirt instance class [System.ServiceModel]System.ServiceModel.EndpointAddress Microsoft.Crm.ServiceBus.IEndpointAddressStrategy::RetrieveEndpointAddress()
0x454b  ret
```
