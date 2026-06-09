# Microsoft.Crm.Asynchronous.AsyncService::set_OperationsFactory

- ea: `0x1920`
- end: `0x1928`
- name: `Microsoft.Crm.Asynchronous.AsyncService::set_OperationsFactory`
- size: `8`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1200`

## pseudocode

```c

```

## disassembly

```asm
0x1920  ldarg.0
0x1921  ldarg.1
0x1922  stfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncService::<OperationsFactory>k__BackingField
0x1927  ret
```
