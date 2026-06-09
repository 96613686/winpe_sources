# Microsoft.Crm.ExchangeRecurrence.ClientStrings::AlternateCalendarTaskWhenYearly

- ea: `0x49760`
- end: `0x4978c`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::AlternateCalendarTaskWhenYearly`
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

- `0x49760`: `AlternateCalendarTaskWhenYearly`

## pseudocode

```c

```

## disassembly

```asm
0x49760  ldstr    aAlternatecalen_17// "AlternateCalendarTaskWhenYearly"
0x49765  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x4976a  ldc.i4.3
0x4976b  newarr   [mscorlib]System.Object
0x49770  dup
0x49771  ldc.i4.0
0x49772  ldarg.0
0x49773  box      Microsoft.Crm.ExchangeRecurrence.LocalizedString
0x49778  stelem.ref
0x49779  dup
0x4977a  ldc.i4.1
0x4977b  ldarg.1
0x4977c  stelem.ref
0x4977d  dup
0x4977e  ldc.i4.2
0x4977f  ldarg.2
0x49780  box      [mscorlib]System.Int32
0x49785  stelem.ref
0x49786  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x4978b  ret
```
