# Microsoft.Crm.Asynchronous.Operations.ServiceOperationsFactory::get_EventLog

- ea: `0x14f10`
- end: `0x14f1c`
- name: `Microsoft.Crm.Asynchronous.Operations.ServiceOperationsFactory::get_EventLog`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x14e00`
- `0x14e20`
- `0x14e40`
- `0x14e60`
- `0x14e80`
- `0x14ea0`

## callees

- `0x14da0`

## pseudocode

```c

```

## disassembly

```asm
0x14f10  ldarg.0
0x14f11  ldfld    class Microsoft.Crm.Asynchronous.Operations.IOperationsBasedService Microsoft.Crm.Asynchronous.Operations.ServiceOperationsFactory::_service
0x14f16  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog Microsoft.Crm.Asynchronous.Operations.IOperationsBasedService::get_CrmEventLog()
0x14f1b  ret
```
