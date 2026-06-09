# Microsoft.Crm.ExchangeRecurrence.ClientStrings::get_TaskWhenWeeklyRegeneratingPattern

- ea: `0x48340`
- end: `0x48356`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::get_TaskWhenWeeklyRegeneratingPattern`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x46b70`

## callees

- `0x47bd0`

## string_xrefs

- `0x48340`: `TaskWhenWeeklyRegeneratingPattern`

## pseudocode

```c

```

## disassembly

```asm
0x48340  ldstr    aTaskwhenweekly// "TaskWhenWeeklyRegeneratingPattern"
0x48345  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x4834a  ldc.i4.0
0x4834b  newarr   [mscorlib]System.Object
0x48350  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x48355  ret
```
