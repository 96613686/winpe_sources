# Microsoft.Crm.Asynchronous.ImportDataAccess::CreateDatabaseConnection

- ea: `0x3c60`
- end: `0x3c68`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::CreateDatabaseConnection`
- size: `8`
- prototype: ``
- caller_count: `8`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14940`
- `0x158d0`
- `0x17130`
- `0x17750`
- `0x18490`
- `0x19b90`
- `0x1b1e0`
- `0x1c630`

## pseudocode

```c

```

## disassembly

```asm
0x3c60  ldarg.0
0x3c61  ldarg.1
0x3c62  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::CreateConnection(valuetype [mscorlib]System.Guid)
0x3c67  ret
```
