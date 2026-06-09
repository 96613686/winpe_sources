# Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenYearlyTh

- ea: `0x48c40`
- end: `0x48c67`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::TaskWhenYearlyTh`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x47720`

## callees

- `0x47bd0`

## string_xrefs

- `0x48c40`: `TaskWhenYearlyTh`

## pseudocode

```c

```

## disassembly

```asm
0x48c40  ldstr    aTaskwhenyearly_0// "TaskWhenYearlyTh"
0x48c45  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x48c4a  ldc.i4.3
0x48c4b  newarr   [mscorlib]System.Object
0x48c50  dup
0x48c51  ldc.i4.0
0x48c52  ldarg.0
0x48c53  box      Microsoft.Crm.ExchangeRecurrence.LocalizedString
0x48c58  stelem.ref
0x48c59  dup
0x48c5a  ldc.i4.1
0x48c5b  ldarg.1
0x48c5c  stelem.ref
0x48c5d  dup
0x48c5e  ldc.i4.2
0x48c5f  ldarg.2
0x48c60  stelem.ref
0x48c61  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x48c66  ret
```
