# Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords_4

- ea: `0xd780`
- end: `0xd78c`
- name: `Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords_4`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x169e0`
- `0x17180`
- `0x17230`

## callees

- `0xd9c0`

## pseudocode

```c

```

## disassembly

```asm
0xd780  ldarg.0
0xd781  ldarg.1
0xd782  ldarg.2
0xd783  ldarg.3
0xd784  ldloca.s 0
0xd786  call     instance int32 Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo command, class RecordProcessor recordProcessor, valuetype [mscorlib]System.Guid inputOrganizationId, [out] string& databaseName)
0xd78b  ret
```
