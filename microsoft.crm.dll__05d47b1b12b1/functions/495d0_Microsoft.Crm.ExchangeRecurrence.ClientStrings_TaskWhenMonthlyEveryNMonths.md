# Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenMonthlyEveryNMonths

- ea: `0x495d0`
- end: `0x495f8`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenMonthlyEveryNMonths`
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

- `0x495d0`: `TaskWhenMonthlyEveryNMonths`

## pseudocode

```c

```

## disassembly

```asm
0x495d0  ldstr    aTaskwhenmonthl_5// "TaskWhenMonthlyEveryNMonths"
0x495d5  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x495da  ldc.i4.2
0x495db  newarr   [mscorlib]System.Object
0x495e0  dup
0x495e1  ldc.i4.0
0x495e2  ldarg.0
0x495e3  box      [mscorlib]System.Int32
0x495e8  stelem.ref
0x495e9  dup
0x495ea  ldc.i4.1
0x495eb  ldarg.1
0x495ec  box      [mscorlib]System.Int32
0x495f1  stelem.ref
0x495f2  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x495f7  ret
```
