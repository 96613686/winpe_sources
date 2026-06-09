# Microsoft.Crm.ExchangeRecurrence.ClientStrings::get_TaskWhenDailyEveryDay

- ea: `0x48c20`
- end: `0x48c36`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::get_TaskWhenDailyEveryDay`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x42120`

## callees

- `0x47bd0`

## string_xrefs

- `0x48c20`: `TaskWhenDailyEveryDay`

## pseudocode

```c

```

## disassembly

```asm
0x48c20  ldstr    aTaskwhendailye_0// "TaskWhenDailyEveryDay"
0x48c25  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x48c2a  ldc.i4.0
0x48c2b  newarr   [mscorlib]System.Object
0x48c30  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x48c35  ret
```
