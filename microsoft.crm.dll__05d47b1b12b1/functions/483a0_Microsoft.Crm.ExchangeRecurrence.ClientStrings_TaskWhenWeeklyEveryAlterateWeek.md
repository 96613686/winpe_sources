# Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenWeeklyEveryAlterateWeek

- ea: `0x483a0`
- end: `0x483ba`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenWeeklyEveryAlterateWeek`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x46db0`

## callees

- `0x47bd0`

## string_xrefs

- `0x483a0`: `TaskWhenWeeklyEveryAlterateWeek`

## pseudocode

```c

```

## disassembly

```asm
0x483a0  ldstr    aTaskwhenweekly_0// "TaskWhenWeeklyEveryAlterateWeek"
0x483a5  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x483aa  ldc.i4.1
0x483ab  newarr   [mscorlib]System.Object
0x483b0  dup
0x483b1  ldc.i4.0
0x483b2  ldarg.0
0x483b3  stelem.ref
0x483b4  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x483b9  ret
```
