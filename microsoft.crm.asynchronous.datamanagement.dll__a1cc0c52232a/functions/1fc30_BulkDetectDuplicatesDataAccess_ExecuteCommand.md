# BulkDetectDuplicatesDataAccess::ExecuteCommand

- ea: `0x1fc30`
- end: `0x1fc38`
- name: `BulkDetectDuplicatesDataAccess::ExecuteCommand`
- size: `8`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x3550`
- `0x36d0`
- `0x3740`
- `0x37b0`

## pseudocode

```c

```

## disassembly

```asm
0x1fc30  ldarg.0
0x1fc31  ldarg.1
0x1fc32  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand)
0x1fc37  ret
```
