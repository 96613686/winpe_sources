# Microsoft.Crm.ExchangeRecurrence.ClientStrings::AlternateCalendarTaskWhenYearlyTh

- ea: `0x48690`
- end: `0x486c0`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::AlternateCalendarTaskWhenYearlyTh`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x47720`

## callees

- `0x47bd0`

## string_xrefs

- `0x48690`: `AlternateCalendarTaskWhenYearlyTh`

## pseudocode

```c

```

## disassembly

```asm
0x48690  ldstr    aAlternatecalen_3// "AlternateCalendarTaskWhenYearlyTh"
0x48695  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x4869a  ldc.i4.4
0x4869b  newarr   [mscorlib]System.Object
0x486a0  dup
0x486a1  ldc.i4.0
0x486a2  ldarg.0
0x486a3  box      Microsoft.Crm.ExchangeRecurrence.LocalizedString
0x486a8  stelem.ref
0x486a9  dup
0x486aa  ldc.i4.1
0x486ab  ldarg.1
0x486ac  box      Microsoft.Crm.ExchangeRecurrence.LocalizedString
0x486b1  stelem.ref
0x486b2  dup
0x486b3  ldc.i4.2
0x486b4  ldarg.2
0x486b5  stelem.ref
0x486b6  dup
0x486b7  ldc.i4.3
0x486b8  ldarg.3
0x486b9  stelem.ref
0x486ba  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x486bf  ret
```
