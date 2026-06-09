# Microsoft.Crm.ExchangeRecurrence.ClientStrings::AlternateCalendarTaskWhenMonthlyThEveryMonth

- ea: `0x49790`
- end: `0x497b7`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::AlternateCalendarTaskWhenMonthlyThEveryMonth`
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

- `0x49790`: `AlternateCalendarTaskWhenMonthlyThEveryMonth`

## pseudocode

```c

```

## disassembly

```asm
0x49790  ldstr    aAlternatecalen_18// "AlternateCalendarTaskWhenMonthlyThEvery"...
0x49795  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x4979a  ldc.i4.3
0x4979b  newarr   [mscorlib]System.Object
0x497a0  dup
0x497a1  ldc.i4.0
0x497a2  ldarg.0
0x497a3  box      Microsoft.Crm.ExchangeRecurrence.LocalizedString
0x497a8  stelem.ref
0x497a9  dup
0x497aa  ldc.i4.1
0x497ab  ldarg.1
0x497ac  stelem.ref
0x497ad  dup
0x497ae  ldc.i4.2
0x497af  ldarg.2
0x497b0  stelem.ref
0x497b1  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x497b6  ret
```
