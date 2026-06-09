# Microsoft.Crm.Asynchronous.DataAccessSharedBase::CreateConnection_0

- ea: `0xe380`
- end: `0xe38e`
- name: `Microsoft.Crm.Asynchronous.DataAccessSharedBase::CreateConnection_0`
- size: `14`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xda20`
- `0xe2a0`

## callees

- `0xe390`
- `0xe3d0`

## pseudocode

```c

```

## disassembly

```asm
0xe380  ldarg.0
0xe381  ldarg.1
0xe382  ldarg.0
0xe383  callvirt instance int32 Microsoft.Crm.Asynchronous.DataAccessSharedBase::GetConnectionTimeout()
0xe388  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.DataAccessSharedBase::CreateConnection(valuetype [mscorlib]System.Guid organizationId, int32 connectionTimeout)
0xe38d  ret
```
