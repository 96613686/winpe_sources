# Microsoft.Crm.ExchangeRecurrence.ClientStrings::AlternateCalendarTaskWhenMonthlyThEveryNMonths

- ea: `0x487b0`
- end: `0x487e0`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::AlternateCalendarTaskWhenMonthlyThEveryNMonths`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x42a90`

## callees

- `0x47bd0`

## string_xrefs

- `0x487b0`: `AlternateCalendarTaskWhenMonthlyThEveryNMonths`

## pseudocode

```c

```

## disassembly

```asm
0x487b0  ldstr    aAlternatecalen_5// "AlternateCalendarTaskWhenMonthlyThEvery"...
0x487b5  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x487ba  ldc.i4.4
0x487bb  newarr   [mscorlib]System.Object
0x487c0  dup
0x487c1  ldc.i4.0
0x487c2  ldarg.0
0x487c3  box      Microsoft.Crm.ExchangeRecurrence.LocalizedString
0x487c8  stelem.ref
0x487c9  dup
0x487ca  ldc.i4.1
0x487cb  ldarg.1
0x487cc  stelem.ref
0x487cd  dup
0x487ce  ldc.i4.2
0x487cf  ldarg.2
0x487d0  stelem.ref
0x487d1  dup
0x487d2  ldc.i4.3
0x487d3  ldarg.3
0x487d4  box      [mscorlib]System.Int32
0x487d9  stelem.ref
0x487da  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x487df  ret
```
