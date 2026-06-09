# Microsoft.Crm.ServiceBus.ServiceBusClientBase::get_EndpointBehaviors

- ea: `0x4690`
- end: `0x4697`
- name: `Microsoft.Crm.ServiceBus.ServiceBusClientBase::get_EndpointBehaviors`
- size: `7`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x4570`
- `0x4980`
- `0x4b50`
- `0x4d10`

## pseudocode

```c

```

## disassembly

```asm
0x4690  ldarg.0
0x4691  ldfld    class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior> Microsoft.Crm.ServiceBus.ServiceBusClientBase::endpointBehaviors
0x4696  ret
```
