# Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ExecuteSqlCommand

- ea: `0xe930`
- end: `0xe938`
- name: `Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ExecuteSqlCommand`
- size: `8`
- prototype: ``
- caller_count: `16`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xe8b0`
- `0xe9c0`
- `0xea70`
- `0xed70`
- `0xedf0`
- `0xeed0`
- `0xef40`
- `0xf010`
- `0xf0a0`
- `0xf180`
- `0xf260`
- `0xf300`
- `0xf370`
- `0xf4b0`
- `0xf640`
- `0xf6e0`

## pseudocode

```c

```

## disassembly

```asm
0xe930  ldarg.0
0xe931  ldarg.1
0xe932  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand)
0xe937  ret
```
