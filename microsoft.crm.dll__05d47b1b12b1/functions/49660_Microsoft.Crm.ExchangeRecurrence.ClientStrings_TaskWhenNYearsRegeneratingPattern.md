# Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenNYearsRegeneratingPattern

- ea: `0x49660`
- end: `0x4967f`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenNYearsRegeneratingPattern`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x46c90`

## callees

- `0x47bd0`

## string_xrefs

- `0x49660`: `TaskWhenNYearsRegeneratingPattern`

## pseudocode

```c

```

## disassembly

```asm
0x49660  ldstr    aTaskwhennyears// "TaskWhenNYearsRegeneratingPattern"
0x49665  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x4966a  ldc.i4.1
0x4966b  newarr   [mscorlib]System.Object
0x49670  dup
0x49671  ldc.i4.0
0x49672  ldarg.0
0x49673  box      [mscorlib]System.Int32
0x49678  stelem.ref
0x49679  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x4967e  ret
```
