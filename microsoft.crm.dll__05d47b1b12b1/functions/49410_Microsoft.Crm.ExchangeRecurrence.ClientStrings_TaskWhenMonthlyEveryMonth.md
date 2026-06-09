# Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenMonthlyEveryMonth

- ea: `0x49410`
- end: `0x4942f`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenMonthlyEveryMonth`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x427f0`

## callees

- `0x47bd0`

## string_xrefs

- `0x49410`: `TaskWhenMonthlyEveryMonth`

## pseudocode

```c

```

## disassembly

```asm
0x49410  ldstr    aTaskwhenmonthl_3// "TaskWhenMonthlyEveryMonth"
0x49415  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x4941a  ldc.i4.1
0x4941b  newarr   [mscorlib]System.Object
0x49420  dup
0x49421  ldc.i4.0
0x49422  ldarg.0
0x49423  box      [mscorlib]System.Int32
0x49428  stelem.ref
0x49429  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x4942e  ret
```
