# Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenYearly

- ea: `0x494c0`
- end: `0x494e3`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenYearly`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x473c0`

## callees

- `0x47bd0`

## string_xrefs

- `0x494c0`: `TaskWhenYearly`

## pseudocode

```c

```

## disassembly

```asm
0x494c0  ldstr    aTaskwhenyearly_1// "TaskWhenYearly"
0x494c5  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x494ca  ldc.i4.2
0x494cb  newarr   [mscorlib]System.Object
0x494d0  dup
0x494d1  ldc.i4.0
0x494d2  ldarg.0
0x494d3  stelem.ref
0x494d4  dup
0x494d5  ldc.i4.1
0x494d6  ldarg.1
0x494d7  box      [mscorlib]System.Int32
0x494dc  stelem.ref
0x494dd  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x494e2  ret
```
