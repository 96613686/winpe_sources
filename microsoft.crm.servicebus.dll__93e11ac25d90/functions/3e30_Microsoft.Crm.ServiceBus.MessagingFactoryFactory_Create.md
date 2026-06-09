# Microsoft.Crm.ServiceBus.MessagingFactoryFactory::Create

- ea: `0x3e30`
- end: `0x3e38`
- name: `Microsoft.Crm.ServiceBus.MessagingFactoryFactory::Create`
- size: `8`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x4e40`

## callees

- `0x4890`

## pseudocode

```c

```

## disassembly

```asm
0x3e30  ldarg.0
0x3e31  ldarg.1
0x3e32  newobj   instance void Microsoft.Crm.ServiceBus.ServiceBusMessagingFactory::.ctor(class [System]System.Uri namespaceUri, class [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.MessagingFactorySettings settings)
0x3e37  ret
```
