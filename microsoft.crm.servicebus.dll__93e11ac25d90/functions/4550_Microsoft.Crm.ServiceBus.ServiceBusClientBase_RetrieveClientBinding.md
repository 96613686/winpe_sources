# Microsoft.Crm.ServiceBus.ServiceBusClientBase::RetrieveClientBinding

- ea: `0x4550`
- end: `0x455c`
- name: `Microsoft.Crm.ServiceBus.ServiceBusClientBase::RetrieveClientBinding`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x4500`

## callees

- `0x3bd0`
- `0x3bf0`

## pseudocode

```c

```

## disassembly

```asm
0x4550  ldarg.1
0x4551  newobj   instance void Microsoft.Crm.ServiceBus.ClientBindingStrategy::.ctor(class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation endpointInfo)
0x4556  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.Binding Microsoft.Crm.ServiceBus.IClientBindingStrategy::RetrieveClientBinding()
0x455b  ret
```
