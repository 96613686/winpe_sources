# Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenMonthlyThEveryNMonths

- ea: `0x49190`
- end: `0x491b7`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenMonthlyThEveryNMonths`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x42a90`

## callees

- `0x47bd0`

## string_xrefs

- `0x49190`: `TaskWhenMonthlyThEveryNMonths`

## pseudocode

```c

```

## disassembly

```asm
0x49190  ldstr    aTaskwhenmonthl_2// "TaskWhenMonthlyThEveryNMonths"
0x49195  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x4919a  ldc.i4.3
0x4919b  newarr   [mscorlib]System.Object
0x491a0  dup
0x491a1  ldc.i4.0
0x491a2  ldarg.0
0x491a3  stelem.ref
0x491a4  dup
0x491a5  ldc.i4.1
0x491a6  ldarg.1
0x491a7  stelem.ref
0x491a8  dup
0x491a9  ldc.i4.2
0x491aa  ldarg.2
0x491ab  box      [mscorlib]System.Int32
0x491b0  stelem.ref
0x491b1  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x491b6  ret
```
