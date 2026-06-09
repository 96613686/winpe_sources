# Microsoft.Crm.Asynchronous.AsyncService::InitializeServiceComponents

- ea: `0x1200`
- end: `0x120d`
- name: `Microsoft.Crm.Asynchronous.AsyncService::InitializeServiceComponents`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xe20`

## callees

- `0x1920`

## pseudocode

```c

```

## disassembly

```asm
0x1200  ldarg.0
0x1201  ldarg.0
0x1202  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationsFactory::Create(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IOperationsBasedService)
0x1207  call     instance void Microsoft.Crm.Asynchronous.AsyncService::set_OperationsFactory(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory value)
0x120c  ret
```
