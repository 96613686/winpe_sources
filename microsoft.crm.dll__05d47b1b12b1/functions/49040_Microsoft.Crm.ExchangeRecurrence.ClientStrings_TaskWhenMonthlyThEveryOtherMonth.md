# Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenMonthlyThEveryOtherMonth

- ea: `0x49040`
- end: `0x4905e`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenMonthlyThEveryOtherMonth`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x42a90`

## callees

- `0x47bd0`

## string_xrefs

- `0x49040`: `TaskWhenMonthlyThEveryOtherMonth`

## pseudocode

```c

```

## disassembly

```asm
0x49040  ldstr    aTaskwhenmonthl_1// "TaskWhenMonthlyThEveryOtherMonth"
0x49045  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x4904a  ldc.i4.2
0x4904b  newarr   [mscorlib]System.Object
0x49050  dup
0x49051  ldc.i4.0
0x49052  ldarg.0
0x49053  stelem.ref
0x49054  dup
0x49055  ldc.i4.1
0x49056  ldarg.1
0x49057  stelem.ref
0x49058  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x4905d  ret
```
