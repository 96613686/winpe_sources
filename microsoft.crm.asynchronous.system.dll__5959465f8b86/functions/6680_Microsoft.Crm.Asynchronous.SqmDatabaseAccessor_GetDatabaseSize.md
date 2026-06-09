# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetDatabaseSize

- ea: `0x6680`
- end: `0x66f7`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetDatabaseSize`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4340`

## callees

- `0x6680`

## pseudocode

```c

```

## disassembly

```asm
0x6680  ldc.i4.0
0x6681  stloc.0
0x6682  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x6687  stloc.1
0x6688  ldloc.1
0x6689  ldstr    aSysSpSpaceused// "sys.sp_spaceused"
0x668e  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x6693  ldloc.1
0x6694  ldc.i4.4
0x6695  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x669a  ldloc.1
0x669b  callvirt instance class [System.Data]System.Data.IDataReader [System.Data]System.Data.IDbCommand::ExecuteReader()
0x66a0  castclass [System.Data]System.Data.SqlClient.SqlDataReader
0x66a5  stloc.2
0x66a6  ldloc.2
0x66a7  callvirt instance bool [System.Data]System.Data.Common.DbDataReader::get_HasRows()
0x66ac  brfalse.s loc_66DF
0x66ae  ldloc.2
0x66af  callvirt instance bool [System.Data]System.Data.Common.DbDataReader::Read()
0x66b4  brfalse.s loc_66DF
0x66b6  ldloc.2
0x66b7  ldstr    aDatabaseSize// "database_size"
0x66bc  callvirt instance object [System.Data]System.Data.Common.DbDataReader::get_Item(string)
0x66c1  callvirt instance string [mscorlib]System.Object::ToString()
0x66c6  ldc.i4.1
0x66c7  newarr   [mscorlib]System.Char
0x66cc  dup
0x66cd  ldc.i4.0
0x66ce  ldc.i4.s 0x20
0x66d0  stelem.i2
0x66d1  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x66d6  ldc.i4.0
0x66d7  ldelem.ref
0x66d8  call     float64 [mscorlib]System.Double::Parse(string)
0x66dd  conv.i4
0x66de  stloc.0
0x66df  leave.s  loc_66F5
0x66e1  ldloc.2
0x66e2  brfalse.s loc_66EA
0x66e4  ldloc.2
0x66e5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x66ea  endfinally
0x66eb  ldloc.1
0x66ec  brfalse.s loc_66F4
0x66ee  ldloc.1
0x66ef  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x66f4  endfinally
0x66f5  ldloc.0
0x66f6  ret
```
