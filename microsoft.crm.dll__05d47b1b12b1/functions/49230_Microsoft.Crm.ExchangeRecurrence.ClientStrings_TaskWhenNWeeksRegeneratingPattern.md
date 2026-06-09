# Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenNWeeksRegeneratingPattern

- ea: `0x49230`
- end: `0x4924f`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenNWeeksRegeneratingPattern`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x46b70`

## callees

- `0x47bd0`

## string_xrefs

- `0x49230`: `TaskWhenNWeeksRegeneratingPattern`

## pseudocode

```c

```

## disassembly

```asm
0x49230  ldstr    aTaskwhennweeks// "TaskWhenNWeeksRegeneratingPattern"
0x49235  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x4923a  ldc.i4.1
0x4923b  newarr   [mscorlib]System.Object
0x49240  dup
0x49241  ldc.i4.0
0x49242  ldarg.0
0x49243  box      [mscorlib]System.Int32
0x49248  stelem.ref
0x49249  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x4924e  ret
```
