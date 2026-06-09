# Microsoft.Crm.ExchangeRecurrence.ClientStrings::AlternateCalendarTaskWhenMonthlyEveryOtherMonth

- ea: `0x48d60`
- end: `0x48d88`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::AlternateCalendarTaskWhenMonthlyEveryOtherMonth`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x427f0`

## callees

- `0x47bd0`

## string_xrefs

- `0x48d60`: `AlternateCalendarTaskWhenMonthlyEveryOtherMonth`

## pseudocode

```c

```

## disassembly

```asm
0x48d60  ldstr    aAlternatecalen_11// "AlternateCalendarTaskWhenMonthlyEveryOt"...
0x48d65  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x48d6a  ldc.i4.2
0x48d6b  newarr   [mscorlib]System.Object
0x48d70  dup
0x48d71  ldc.i4.0
0x48d72  ldarg.0
0x48d73  box      Microsoft.Crm.ExchangeRecurrence.LocalizedString
0x48d78  stelem.ref
0x48d79  dup
0x48d7a  ldc.i4.1
0x48d7b  ldarg.1
0x48d7c  box      [mscorlib]System.Int32
0x48d81  stelem.ref
0x48d82  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x48d87  ret
```
