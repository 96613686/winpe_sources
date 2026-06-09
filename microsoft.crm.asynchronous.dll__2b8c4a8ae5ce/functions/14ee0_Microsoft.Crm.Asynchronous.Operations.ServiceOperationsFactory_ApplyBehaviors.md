# Microsoft.Crm.Asynchronous.Operations.ServiceOperationsFactory::ApplyBehaviors

- ea: `0x14ee0`
- end: `0x14ef6`
- name: `Microsoft.Crm.Asynchronous.Operations.ServiceOperationsFactory::ApplyBehaviors`
- size: `22`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14e00`
- `0x14e20`
- `0x14e40`
- `0x14e60`
- `0x14e80`
- `0x14ea0`
- `0x14ec0`

## callees

- `0x14d70`
- `0x14ee0`
- `0x14f20`

## pseudocode

```c

```

## disassembly

```asm
0x14ee0  ldarg.0
0x14ee1  call     instance class Microsoft.Crm.Asynchronous.Operations.IServiceBehavior Microsoft.Crm.Asynchronous.Operations.ServiceOperationsFactory::get_ServiceBehavior()
0x14ee6  brtrue.s loc_14EE9
0x14ee8  ret
0x14ee9  ldarg.0
0x14eea  call     instance class Microsoft.Crm.Asynchronous.Operations.IServiceBehavior Microsoft.Crm.Asynchronous.Operations.ServiceOperationsFactory::get_ServiceBehavior()
0x14eef  ldarg.1
0x14ef0  callvirt instance void Microsoft.Crm.Asynchronous.Operations.IServiceBehavior::ApplyBehavior(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x14ef5  ret
```
