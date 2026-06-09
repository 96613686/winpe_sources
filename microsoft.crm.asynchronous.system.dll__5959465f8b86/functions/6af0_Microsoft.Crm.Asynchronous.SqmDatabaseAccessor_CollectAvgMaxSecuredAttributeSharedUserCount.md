# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectAvgMaxSecuredAttributeSharedUserCount

- ea: `0x6af0`
- end: `0x6b36`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectAvgMaxSecuredAttributeSharedUserCount`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x4d60`

## callees

- `0x6af0`
- `0xe820`

## string_xrefs

- `0x6b0b`: `SELECT AVG(Result.usercount), MAX(Result.usercount) FROM (SELECT COUNT(P.AttributeId) AS usercount FROM PrincipalObjectAttributeAccess AS P \nFULL OUTER JOIN (SELECT AttributeId FROM AttributeView WHERE IsSecured = 1) AS A \nON A.AttributeId = P.AttributeId GROUP BY (A.AttributeId)) AS Result`

## pseudocode

```c

```

## disassembly

```asm
0x6af0  newobj   instance void <>c__DisplayClass23_0::.ctor()
0x6af5  stloc.0
0x6af6  ldloc.0
0x6af7  ldarg.0
0x6af8  stfld    class Microsoft.Crm.Asynchronous.SqmDatabaseAccessor <>c__DisplayClass23_0::<>4__this
0x6afd  ldloc.0
0x6afe  ldarg.1
0x6aff  stfld    class [Microsoft.Crm]Microsoft.Crm.ISqmSession <>c__DisplayClass23_0::session
0x6b04  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x6b09  stloc.1
0x6b0a  ldloc.1
0x6b0b  ldstr    aSelectAvgResul// "SELECT AVG(Result.usercount), MAX(Resul"...
0x6b10  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x6b15  ldarg.0
0x6b16  ldloc.1
0x6b17  ldloc.0
0x6b18  ldftn    instance void <>c__DisplayClass23_0::<CollectAvgMaxSecuredAttributeSharedUserCount>b__0(object[] values)
0x6b1e  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x6b23  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x6b28  pop
0x6b29  leave.s  loc_6B35
0x6b2b  ldloc.1
0x6b2c  brfalse.s loc_6B34
0x6b2e  ldloc.1
0x6b2f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6b34  endfinally
0x6b35  ret
```
