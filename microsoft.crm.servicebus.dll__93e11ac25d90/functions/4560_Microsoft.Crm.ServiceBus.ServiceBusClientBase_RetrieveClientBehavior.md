# Microsoft.Crm.ServiceBus.ServiceBusClientBase::RetrieveClientBehavior

- ea: `0x4560`
- end: `0x456c`
- name: `Microsoft.Crm.ServiceBus.ServiceBusClientBase::RetrieveClientBehavior`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x4500`

## callees

- `0x3b70`
- `0x3b90`

## pseudocode

```c

```

## disassembly

```asm
0x4560  ldarg.1
0x4561  newobj   instance void Microsoft.Crm.ServiceBus.ClientBehaviorStrategy::.ctor(class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation endpointInfo)
0x4566  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior> Microsoft.Crm.ServiceBus.IClientBehaviorStrategy::RetrieveClientBehavior()
0x456b  ret
```
