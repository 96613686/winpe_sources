# Microsoft.Crm.ExchangeRecurrence.ClientStrings::AlternateCalendarTaskWhenYearlyThLeap

- ea: `0x48660`
- end: `0x48690`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::AlternateCalendarTaskWhenYearlyThLeap`
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

- `0x48660`: `AlternateCalendarTaskWhenYearlyThLeap`

## pseudocode

```c

```

## disassembly

```asm
0x48660  ldstr    aAlternatecalen_2// "AlternateCalendarTaskWhenYearlyThLeap"
0x48665  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x4866a  ldc.i4.4
0x4866b  newarr   [mscorlib]System.Object
0x48670  dup
0x48671  ldc.i4.0
0x48672  ldarg.0
0x48673  box      Microsoft.Crm.ExchangeRecurrence.LocalizedString
0x48678  stelem.ref
0x48679  dup
0x4867a  ldc.i4.1
0x4867b  ldarg.1
0x4867c  box      Microsoft.Crm.ExchangeRecurrence.LocalizedString
0x48681  stelem.ref
0x48682  dup
0x48683  ldc.i4.2
0x48684  ldarg.2
0x48685  stelem.ref
0x48686  dup
0x48687  ldc.i4.3
0x48688  ldarg.3
0x48689  stelem.ref
0x4868a  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x4868f  ret
```
