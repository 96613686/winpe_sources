# Microsoft.Crm.ServiceBus.ClientBindingStrategy::RetrieveClientBinding

- ea: `0x3c50`
- end: `0x3c5c`
- name: `Microsoft.Crm.ServiceBus.ClientBindingStrategy::RetrieveClientBinding`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x3bd0`

## pseudocode

```c

```

## disassembly

```asm
0x3c50  ldarg.0
0x3c51  ldfld    class Microsoft.Crm.ServiceBus.IClientBindingStrategy Microsoft.Crm.ServiceBus.ClientBindingStrategy::selectedStrategy
0x3c56  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.Binding Microsoft.Crm.ServiceBus.IClientBindingStrategy::RetrieveClientBinding()
0x3c5b  ret
```
