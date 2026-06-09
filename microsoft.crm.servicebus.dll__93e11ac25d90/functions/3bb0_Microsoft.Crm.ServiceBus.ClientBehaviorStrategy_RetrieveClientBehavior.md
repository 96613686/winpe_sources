# Microsoft.Crm.ServiceBus.ClientBehaviorStrategy::RetrieveClientBehavior

- ea: `0x3bb0`
- end: `0x3bbc`
- name: `Microsoft.Crm.ServiceBus.ClientBehaviorStrategy::RetrieveClientBehavior`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x3b70`

## pseudocode

```c

```

## disassembly

```asm
0x3bb0  ldarg.0
0x3bb1  ldfld    class Microsoft.Crm.ServiceBus.IClientBehaviorStrategy Microsoft.Crm.ServiceBus.ClientBehaviorStrategy::selectedStrategy
0x3bb6  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior> Microsoft.Crm.ServiceBus.IClientBehaviorStrategy::RetrieveClientBehavior()
0x3bbb  ret
```
