# Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess::ExecuteSqlCommand

- ea: `0xe600`
- end: `0xe608`
- name: `Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess::ExecuteSqlCommand`
- size: `8`
- prototype: ``
- caller_count: `9`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xc210`
- `0xd320`
- `0xd3b0`
- `0xd410`
- `0x17000`
- `0x17080`
- `0x170c0`
- `0x17100`
- `0x17170`

## pseudocode

```c

```

## disassembly

```asm
0xe600  ldarg.0
0xe601  ldarg.1
0xe602  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand)
0xe607  ret
```
