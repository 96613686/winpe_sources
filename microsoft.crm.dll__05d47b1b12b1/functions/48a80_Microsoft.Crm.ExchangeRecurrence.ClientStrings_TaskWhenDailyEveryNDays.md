# Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenDailyEveryNDays

- ea: `0x48a80`
- end: `0x48a9f`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenDailyEveryNDays`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x42120`

## callees

- `0x47bd0`

## string_xrefs

- `0x48a80`: `TaskWhenDailyEveryNDays`

## pseudocode

```c

```

## disassembly

```asm
0x48a80  ldstr    aTaskwhendailye// "TaskWhenDailyEveryNDays"
0x48a85  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x48a8a  ldc.i4.1
0x48a8b  newarr   [mscorlib]System.Object
0x48a90  dup
0x48a91  ldc.i4.0
0x48a92  ldarg.0
0x48a93  box      [mscorlib]System.Int32
0x48a98  stelem.ref
0x48a99  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x48a9e  ret
```
