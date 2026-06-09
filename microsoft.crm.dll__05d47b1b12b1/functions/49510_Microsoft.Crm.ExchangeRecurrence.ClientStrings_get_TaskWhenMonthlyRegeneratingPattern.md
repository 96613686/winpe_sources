# Microsoft.Crm.ExchangeRecurrence.ClientStrings::get_TaskWhenMonthlyRegeneratingPattern

- ea: `0x49510`
- end: `0x49526`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::get_TaskWhenMonthlyRegeneratingPattern`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x46c00`

## callees

- `0x47bd0`

## string_xrefs

- `0x49510`: `TaskWhenMonthlyRegeneratingPattern`

## pseudocode

```c

```

## disassembly

```asm
0x49510  ldstr    aTaskwhenmonthl_4// "TaskWhenMonthlyRegeneratingPattern"
0x49515  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x4951a  ldc.i4.0
0x4951b  newarr   [mscorlib]System.Object
0x49520  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x49525  ret
```
