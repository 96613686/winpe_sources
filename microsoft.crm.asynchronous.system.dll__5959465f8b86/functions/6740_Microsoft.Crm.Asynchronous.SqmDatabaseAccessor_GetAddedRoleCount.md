# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetAddedRoleCount

- ea: `0x6740`
- end: `0x6751`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetAddedRoleCount`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4600`

## callees

- `0x67f0`

## pseudocode

```c

```

## disassembly

```asm
0x6740  ldstr    aPGetaddedrolec// "p_GetAddedRoleCount"
0x6745  stloc.0
0x6746  ldc.i4.4
0x6747  stloc.1
0x6748  ldarg.0
0x6749  ldloc.0
0x674a  ldloc.1
0x674b  call     instance int32 Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::RetrieveOneInteger(string sqlCommand, valuetype [System.Data]System.Data.CommandType commandType)
0x6750  ret
```
