# Microsoft.Crm.Asynchronous.AsyncService::get_OperationCommandTypes

- ea: `0x18f0`
- end: `0x18f7`
- name: `Microsoft.Crm.Asynchronous.AsyncService::get_OperationCommandTypes`
- size: `7`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x540`
- `0xcd0`

## pseudocode

```c

```

## disassembly

```asm
0x18f0  ldarg.0
0x18f1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype Microsoft.Crm.Asynchronous.AsyncEventHandlerCommandRegistration> Microsoft.Crm.Asynchronous.AsyncService::<OperationCommandTypes>k__BackingField
0x18f6  ret
```
