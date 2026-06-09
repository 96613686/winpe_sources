# Microsoft.Crm.Asynchronous.AuditPartitionDataAccess::.ctor

- ea: `0x7a0`
- end: `0x7af`
- name: `Microsoft.Crm.Asynchronous.AuditPartitionDataAccess::.ctor`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x720`

## callees

- `0x3a20`

## pseudocode

```c

```

## disassembly

```asm
0x7a0  ldarg.0
0x7a1  ldarg.1
0x7a2  call     instance void Microsoft.Crm.Asynchronous.DataManagementDataAccessBase::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration config)
0x7a7  ldarg.0
0x7a8  ldarg.1
0x7a9  stfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.AuditPartitionDataAccess::_config
0x7ae  ret
```
