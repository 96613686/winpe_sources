# Microsoft.Crm.Asynchronous.DataAccessSharedBase::CreateConnection

- ea: `0xe360`
- end: `0xe373`
- name: `Microsoft.Crm.Asynchronous.DataAccessSharedBase::CreateConnection`
- size: `19`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xda20`
- `0xe2a0`
- `0xe3e0`

## callees

- `0xe180`
- `0xe390`
- `0xe3d0`

## pseudocode

```c

```

## disassembly

```asm
0xe360  ldarg.0
0xe361  ldarg.0
0xe362  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0xe367  ldarg.0
0xe368  callvirt instance int32 Microsoft.Crm.Asynchronous.DataAccessSharedBase::GetConnectionTimeout()
0xe36d  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.DataAccessSharedBase::CreateConnection(valuetype [mscorlib]System.Guid organizationId, int32 connectionTimeout)
0xe372  ret
```
