# Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenNMonthsRegeneratingPattern

- ea: `0x48360`
- end: `0x4837f`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenNMonthsRegeneratingPattern`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x46c00`

## callees

- `0x47bd0`

## string_xrefs

- `0x48360`: `TaskWhenNMonthsRegeneratingPattern`

## pseudocode

```c

```

## disassembly

```asm
0x48360  ldstr    aTaskwhennmonth// "TaskWhenNMonthsRegeneratingPattern"
0x48365  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x4836a  ldc.i4.1
0x4836b  newarr   [mscorlib]System.Object
0x48370  dup
0x48371  ldc.i4.0
0x48372  ldarg.0
0x48373  box      [mscorlib]System.Int32
0x48378  stelem.ref
0x48379  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x4837e  ret
```
