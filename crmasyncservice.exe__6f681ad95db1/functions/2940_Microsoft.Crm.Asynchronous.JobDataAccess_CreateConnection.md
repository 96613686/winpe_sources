# Microsoft.Crm.Asynchronous.JobDataAccess::CreateConnection

- ea: `0x2940`
- end: `0x2948`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::CreateConnection`
- size: `8`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2950`

## pseudocode

```c

```

## disassembly

```asm
0x2940  ldarg.0
0x2941  ldc.i4.1
0x2942  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.JobDataAccess::CreateConnection(valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigScope configScope)
0x2947  ret
```
