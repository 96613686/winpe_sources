# Microsoft.Crm.Asynchronous.AsyncService::get_ServiceBehavior

- ea: `0x18c0`
- end: `0x18c7`
- name: `Microsoft.Crm.Asynchronous.AsyncService::get_ServiceBehavior`
- size: `7`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x51d0`

## pseudocode

```c

```

## disassembly

```asm
0x18c0  ldarg.0
0x18c1  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceBehavior Microsoft.Crm.Asynchronous.AsyncServiceBehaviorFactory::CreateBehaviors(class Microsoft.Crm.Asynchronous.AsyncService service)
0x18c6  ret
```
