# Microsoft.Crm.ExchangeRecurrence.ClientStrings::AlternateCalendarTaskWhenYearlyLeap

- ea: `0x48780`
- end: `0x487ac`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::AlternateCalendarTaskWhenYearlyLeap`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x473c0`

## callees

- `0x47bd0`

## string_xrefs

- `0x48780`: `AlternateCalendarTaskWhenYearlyLeap`

## pseudocode

```c

```

## disassembly

```asm
0x48780  ldstr    aAlternatecalen_4// "AlternateCalendarTaskWhenYearlyLeap"
0x48785  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x4878a  ldc.i4.3
0x4878b  newarr   [mscorlib]System.Object
0x48790  dup
0x48791  ldc.i4.0
0x48792  ldarg.0
0x48793  box      Microsoft.Crm.ExchangeRecurrence.LocalizedString
0x48798  stelem.ref
0x48799  dup
0x4879a  ldc.i4.1
0x4879b  ldarg.1
0x4879c  stelem.ref
0x4879d  dup
0x4879e  ldc.i4.2
0x4879f  ldarg.2
0x487a0  box      [mscorlib]System.Int32
0x487a5  stelem.ref
0x487a6  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x487ab  ret
```
