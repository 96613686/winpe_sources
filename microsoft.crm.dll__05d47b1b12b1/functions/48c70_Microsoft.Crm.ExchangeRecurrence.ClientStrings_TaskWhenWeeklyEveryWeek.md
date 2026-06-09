# Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenWeeklyEveryWeek

- ea: `0x48c70`
- end: `0x48c8a`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenWeeklyEveryWeek`
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

- `0x48c70`: `TaskWhenWeeklyEveryWeek`

## pseudocode

```c

```

## disassembly

```asm
0x48c70  ldstr    aTaskwhenweekly_1// "TaskWhenWeeklyEveryWeek"
0x48c75  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x48c7a  ldc.i4.1
0x48c7b  newarr   [mscorlib]System.Object
0x48c80  dup
0x48c81  ldc.i4.0
0x48c82  ldarg.0
0x48c83  stelem.ref
0x48c84  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x48c89  ret
```
