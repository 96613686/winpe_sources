# Microsoft.Crm.ExchangeRecurrence.ClientStrings::AlternateCalendarTaskWhenMonthlyEveryMonth

- ea: `0x48520`
- end: `0x48548`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::AlternateCalendarTaskWhenMonthlyEveryMonth`
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

- `0x48520`: `AlternateCalendarTaskWhenMonthlyEveryMonth`

## pseudocode

```c

```

## disassembly

```asm
0x48520  ldstr    aAlternatecalen_1// "AlternateCalendarTaskWhenMonthlyEveryMo"...
0x48525  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x4852a  ldc.i4.2
0x4852b  newarr   [mscorlib]System.Object
0x48530  dup
0x48531  ldc.i4.0
0x48532  ldarg.0
0x48533  box      Microsoft.Crm.ExchangeRecurrence.LocalizedString
0x48538  stelem.ref
0x48539  dup
0x4853a  ldc.i4.1
0x4853b  ldarg.1
0x4853c  box      [mscorlib]System.Int32
0x48541  stelem.ref
0x48542  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x48547  ret
```
