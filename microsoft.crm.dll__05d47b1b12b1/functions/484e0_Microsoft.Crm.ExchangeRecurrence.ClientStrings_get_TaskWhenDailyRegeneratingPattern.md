# Microsoft.Crm.ExchangeRecurrence.ClientStrings::get_TaskWhenDailyRegeneratingPattern

- ea: `0x484e0`
- end: `0x484f6`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::get_TaskWhenDailyRegeneratingPattern`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x46b10`

## callees

- `0x47bd0`

## string_xrefs

- `0x484e0`: `TaskWhenDailyRegeneratingPattern`

## pseudocode

```c

```

## disassembly

```asm
0x484e0  ldstr    aTaskwhendailyr// "TaskWhenDailyRegeneratingPattern"
0x484e5  ldsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x484ea  ldc.i4.0
0x484eb  newarr   [mscorlib]System.Object
0x484f0  newobj   instance void Microsoft.Crm.ExchangeRecurrence.LocalizedString::.ctor(string id, class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager resourceManager, object[] inserts)
0x484f5  ret
```
