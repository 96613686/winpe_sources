# Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenMonthlyThEveryMonth

- ea: `0x489e0`
- end: `0x489fe`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenMonthlyThEveryMonth`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x42a90`

## callees

- `0x47bd0`

## string_xrefs

- `0x489e0`: `TaskWhenMonthlyThEveryMonth`

## pseudocode

```c

```

## disassembly

```asm
0x489e0  ldstr    aTaskwhenmonthl// "TaskWhenMonthlyThEveryMonth"
0x489e5  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x489ea  ldc.i4.2
0x489eb  newarr   [mscorlib]System.Object
0x489f0  dup
0x489f1  ldc.i4.0
0x489f2  ldarg.0
0x489f3  stelem.ref
0x489f4  dup
0x489f5  ldc.i4.1
0x489f6  ldarg.1
0x489f7  stelem.ref
0x489f8  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x489fd  ret
```
