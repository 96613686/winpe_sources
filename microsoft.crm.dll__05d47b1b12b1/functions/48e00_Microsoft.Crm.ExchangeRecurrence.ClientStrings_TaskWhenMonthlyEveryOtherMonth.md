# Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenMonthlyEveryOtherMonth

- ea: `0x48e00`
- end: `0x48e1f`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenMonthlyEveryOtherMonth`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x427f0`

## callees

- `0x47bd0`

## string_xrefs

- `0x48e00`: `TaskWhenMonthlyEveryOtherMonth`

## pseudocode

```c

```

## disassembly

```asm
0x48e00  ldstr    aTaskwhenmonthl_0// "TaskWhenMonthlyEveryOtherMonth"
0x48e05  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x48e0a  ldc.i4.1
0x48e0b  newarr   [mscorlib]System.Object
0x48e10  dup
0x48e11  ldc.i4.0
0x48e12  ldarg.0
0x48e13  box      [mscorlib]System.Int32
0x48e18  stelem.ref
0x48e19  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x48e1e  ret
```
