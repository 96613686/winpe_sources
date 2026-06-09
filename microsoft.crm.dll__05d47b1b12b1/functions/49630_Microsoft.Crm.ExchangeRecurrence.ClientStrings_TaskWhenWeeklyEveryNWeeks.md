# Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenWeeklyEveryNWeeks

- ea: `0x49630`
- end: `0x49653`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenWeeklyEveryNWeeks`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x46db0`

## callees

- `0x47bd0`

## string_xrefs

- `0x49630`: `TaskWhenWeeklyEveryNWeeks`

## pseudocode

```c

```

## disassembly

```asm
0x49630  ldstr    aTaskwhenweekly_2// "TaskWhenWeeklyEveryNWeeks"
0x49635  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x4963a  ldc.i4.2
0x4963b  newarr   [mscorlib]System.Object
0x49640  dup
0x49641  ldc.i4.0
0x49642  ldarg.0
0x49643  box      [mscorlib]System.Int32
0x49648  stelem.ref
0x49649  dup
0x4964a  ldc.i4.1
0x4964b  ldarg.1
0x4964c  stelem.ref
0x4964d  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x49652  ret
```
