# Microsoft.Crm.ExchangeRecurrence.ClientStrings::get_TaskWhenEveryOtherDay

- ea: `0x494f0`
- end: `0x49506`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::get_TaskWhenEveryOtherDay`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x42120`

## callees

- `0x47bd0`

## string_xrefs

- `0x494f0`: `TaskWhenEveryOtherDay`

## pseudocode

```c

```

## disassembly

```asm
0x494f0  ldstr    aTaskwheneveryo// "TaskWhenEveryOtherDay"
0x494f5  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x494fa  ldc.i4.0
0x494fb  newarr   [mscorlib]System.Object
0x49500  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x49505  ret
```
