# Microsoft.Crm.ExchangeRecurrence.ClientStrings::get_TaskWhenYearlyRegeneratingPattern

- ea: `0x48550`
- end: `0x48566`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::get_TaskWhenYearlyRegeneratingPattern`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x46c90`

## callees

- `0x47bd0`

## string_xrefs

- `0x48550`: `TaskWhenYearlyRegeneratingPattern`

## pseudocode

```c

```

## disassembly

```asm
0x48550  ldstr    aTaskwhenyearly// "TaskWhenYearlyRegeneratingPattern"
0x48555  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x4855a  ldc.i4.0
0x4855b  newarr   [mscorlib]System.Object
0x48560  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x48565  ret
```
