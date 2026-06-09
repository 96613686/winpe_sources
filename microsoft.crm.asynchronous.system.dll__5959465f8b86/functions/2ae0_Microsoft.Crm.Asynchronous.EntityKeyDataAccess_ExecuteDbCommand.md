# Microsoft.Crm.Asynchronous.EntityKeyDataAccess::ExecuteDbCommand

- ea: `0x2ae0`
- end: `0x2ae9`
- name: `Microsoft.Crm.Asynchronous.EntityKeyDataAccess::ExecuteDbCommand`
- size: `9`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x28c0`

## pseudocode

```c

```

## disassembly

```asm
0x2ae0  ldarg.0
0x2ae1  ldarg.1
0x2ae2  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand)
0x2ae7  pop
0x2ae8  ret
```
