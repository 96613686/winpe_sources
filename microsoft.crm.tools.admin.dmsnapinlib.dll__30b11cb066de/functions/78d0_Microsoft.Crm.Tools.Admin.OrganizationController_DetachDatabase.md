# Microsoft.Crm.Tools.Admin.OrganizationController::DetachDatabase

- ea: `0x78d0`
- end: `0x7a16`
- name: `Microsoft.Crm.Tools.Admin.OrganizationController::DetachDatabase`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x7870`

## callees

- `0x78d0`

## string_xrefs

- `0x78e3`: `if convert(nvarchar, serverproperty('Edition')) <> 'SQL Azure' begin; alter database {0} set single_user with rollback immediate; end;`
- `0x7949`: `Setting SINGLE_USER mode with ROLLBACK for database({0}) on sqlServer({1}).`

## pseudocode

```c

```

## disassembly

```asm
0x78d0  ldarg.1
0x78d1  call     class [System.Data]System.Data.SqlClient.SqlConnection [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.SqlUtility::GetConnection(string)
0x78d6  stloc.0
0x78d7  ldloc.0
0x78d8  callvirt instance class [System.Data]System.Data.SqlClient.SqlCommand [System.Data]System.Data.SqlClient.SqlConnection::CreateCommand()
0x78dd  stloc.1
0x78de  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x78e3  ldstr    aIfConvertNvarc// "if convert(nvarchar, serverproperty('Ed"...
0x78e8  ldc.i4.1
0x78e9  newarr   [mscorlib]System.Object
0x78ee  dup
0x78ef  ldc.i4.0
0x78f0  ldarg.2
0x78f1  stelem.ref
0x78f2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x78f7  stloc.2
0x78f8  ldstr    aExecSpDetachDb// "EXEC sp_detach_db @dbname = @databaseNa"...
0x78fd  stloc.3
0x78fe  ldstr    aDatabasename_0// "@databaseName"
0x7903  ldc.i4.s 0x16
0x7905  ldc.i4.s 0x1E
0x7907  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x790c  stloc.s  4
0x790e  ldloc.s  4
0x7910  ldarg.2
0x7911  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x7916  ldloc.1
0x7917  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x791c  ldloc.s  4
0x791e  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x7923  pop
0x7924  ldloc.1
0x7925  ldc.i4.1
0x7926  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x792b  ldstr    aStartDetaching// "[start] Detaching the database({0}) on "...
0x7930  ldc.i4.2
0x7931  newarr   [mscorlib]System.Object
0x7936  dup
0x7937  ldc.i4.0
0x7938  ldarg.2
0x7939  stelem.ref
0x793a  dup
0x793b  ldc.i4.1
0x793c  ldarg.1
0x793d  stelem.ref
0x793e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x7943  ldloc.0
0x7944  callvirt instance void [System.Data]System.Data.Common.DbConnection::Open()
0x7949  ldstr    aSettingSingleU// "Setting SINGLE_USER mode with ROLLBACK "...
0x794e  ldc.i4.2
0x794f  newarr   [mscorlib]System.Object
0x7954  dup
0x7955  ldc.i4.0
0x7956  ldarg.2
0x7957  stelem.ref
0x7958  dup
0x7959  ldc.i4.1
0x795a  ldarg.1
0x795b  stelem.ref
0x795c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x7961  ldloc.1
0x7962  ldloc.2
0x7963  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x7968  ldloc.1
0x7969  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x796e  pop
0x796f  ldstr    aDetachingTheDa// "Detaching the database({0}) on sqlServe"...
0x7974  ldc.i4.2
0x7975  newarr   [mscorlib]System.Object
0x797a  dup
0x797b  ldc.i4.0
0x797c  ldarg.2
0x797d  stelem.ref
0x797e  dup
0x797f  ldc.i4.1
0x7980  ldarg.1
0x7981  stelem.ref
0x7982  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x7987  ldloc.1
0x7988  ldloc.3
0x7989  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x798e  ldloc.1
0x798f  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x7994  pop
0x7995  ldstr    aSuccessfullyDe// "Successfully detached the database({0})"...
0x799a  ldc.i4.2
0x799b  newarr   [mscorlib]System.Object
0x79a0  dup
0x79a1  ldc.i4.0
0x79a2  ldarg.2
0x79a3  stelem.ref
0x79a4  dup
0x79a5  ldc.i4.1
0x79a6  ldarg.1
0x79a7  stelem.ref
0x79a8  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x79ad  leave.s  loc_7A15
0x79af  stloc.s  5
0x79b1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x79b6  ldstr    aErrorWhenTryin// "Error when trying to detach the databas"...
0x79bb  ldc.i4.2
0x79bc  newarr   [mscorlib]System.Object
0x79c1  dup
0x79c2  ldc.i4.0
0x79c3  ldarg.2
0x79c4  stelem.ref
0x79c5  dup
0x79c6  ldc.i4.1
0x79c7  ldarg.1
0x79c8  stelem.ref
0x79c9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x79ce  ldloc.s  5
0x79d0  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteError(string, class [mscorlib]System.Exception)
0x79d5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x79da  ldstr    aErrorWhenTryin// "Error when trying to detach the databas"...
0x79df  ldc.i4.2
0x79e0  newarr   [mscorlib]System.Object
0x79e5  dup
0x79e6  ldc.i4.0
0x79e7  ldarg.2
0x79e8  stelem.ref
0x79e9  dup
0x79ea  ldc.i4.1
0x79eb  ldarg.1
0x79ec  stelem.ref
0x79ed  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x79f2  ldloc.s  5
0x79f4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x79f9  throw
0x79fa  ldloc.0
0x79fb  callvirt instance void [System.Data]System.Data.Common.DbConnection::Close()
0x7a00  endfinally
0x7a01  ldloc.1
0x7a02  brfalse.s loc_7A0A
0x7a04  ldloc.1
0x7a05  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7a0a  endfinally
0x7a0b  ldloc.0
0x7a0c  brfalse.s loc_7A14
0x7a0e  ldloc.0
0x7a0f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7a14  endfinally
0x7a15  ret
```
