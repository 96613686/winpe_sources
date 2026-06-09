# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetSolutionComponentCount

- ea: `0x6fd0`
- end: `0x702e`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetSolutionComponentCount`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x6d90`

## callees

- `0x6fd0`

## string_xrefs

- `0x6fe4`: `@ComponentType`

## pseudocode

```c

```

## disassembly

```asm
0x6fd0  ldc.i4.0
0x6fd1  stloc.0
0x6fd2  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x6fd7  stloc.1
0x6fd8  ldloc.1
0x6fd9  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x6fde  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x6fe3  dup
0x6fe4  ldstr    aComponenttype// "@ComponentType"
0x6fe9  ldarg.2
0x6fea  box      [mscorlib]System.Int32
0x6fef  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6ff4  pop
0x6ff5  ldstr    aSolutionid// "@SolutionId"
0x6ffa  ldc.i4.s 0xE
0x6ffc  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x7001  ldarg.3
0x7002  box      [mscorlib]System.Guid
0x7007  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x700c  ldloc.1
0x700d  ldarg.1
0x700e  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x7013  ldarg.0
0x7014  ldloc.1
0x7015  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand)
0x701a  unbox.any [mscorlib]System.Int32
0x701f  stloc.0
0x7020  leave.s  loc_702C
0x7022  ldloc.1
0x7023  brfalse.s loc_702B
0x7025  ldloc.1
0x7026  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x702b  endfinally
0x702c  ldloc.0
0x702d  ret
```
