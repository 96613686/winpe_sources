# Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenNDaysRegeneratingPattern

- ea: `0x48430`
- end: `0x4844f`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenNDaysRegeneratingPattern`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x46b10`

## callees

- `0x47bd0`

## string_xrefs

- `0x48430`: `TaskWhenNDaysRegeneratingPattern`

## pseudocode

```c

```

## disassembly

```asm
0x48430  ldstr    aTaskwhenndaysr// "TaskWhenNDaysRegeneratingPattern"
0x48435  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x4843a  ldc.i4.1
0x4843b  newarr   [mscorlib]System.Object
0x48440  dup
0x48441  ldc.i4.0
0x48442  ldarg.0
0x48443  box      [mscorlib]System.Int32
0x48448  stelem.ref
0x48449  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x4844e  ret
```
