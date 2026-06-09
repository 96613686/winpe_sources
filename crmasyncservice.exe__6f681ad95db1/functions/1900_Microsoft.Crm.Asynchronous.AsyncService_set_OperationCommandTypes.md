# Microsoft.Crm.Asynchronous.AsyncService::set_OperationCommandTypes

- ea: `0x1900`
- end: `0x1908`
- name: `Microsoft.Crm.Asynchronous.AsyncService::set_OperationCommandTypes`
- size: `8`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xe20`

## pseudocode

```c

```

## disassembly

```asm
0x1900  ldarg.0
0x1901  ldarg.1
0x1902  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype Microsoft.Crm.Asynchronous.AsyncEventHandlerCommandRegistration> Microsoft.Crm.Asynchronous.AsyncService::<OperationCommandTypes>k__BackingField
0x1907  ret
```
