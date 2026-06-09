# Microsoft.Crm.ExchangeRecurrence.ClientStrings::AlternateCalendarTaskWhenMonthlyThEveryOtherMonth

- ea: `0x48e90`
- end: `0x48eb7`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::AlternateCalendarTaskWhenMonthlyThEveryOtherMonth`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x42a90`

## callees

- `0x47bd0`

## string_xrefs

- `0x48e90`: `AlternateCalendarTaskWhenMonthlyThEveryOtherMonth`

## pseudocode

```c

```

## disassembly

```asm
0x48e90  ldstr    aAlternatecalen_14// "AlternateCalendarTaskWhenMonthlyThEvery"...
0x48e95  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x48e9a  ldc.i4.3
0x48e9b  newarr   [mscorlib]System.Object
0x48ea0  dup
0x48ea1  ldc.i4.0
0x48ea2  ldarg.0
0x48ea3  box      Microsoft.Crm.ExchangeRecurrence.LocalizedString
0x48ea8  stelem.ref
0x48ea9  dup
0x48eaa  ldc.i4.1
0x48eab  ldarg.1
0x48eac  stelem.ref
0x48ead  dup
0x48eae  ldc.i4.2
0x48eaf  ldarg.2
0x48eb0  stelem.ref
0x48eb1  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x48eb6  ret
```
