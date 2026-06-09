# Microsoft.Crm.Tools.Admin.OrganizationController::RestoreDB

- ea: `0x7b80`
- end: `0x7c91`
- name: `Microsoft.Crm.Tools.Admin.OrganizationController::RestoreDB`
- size: `273`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x7b80`

## string_xrefs

- `0x7bbb`: `RESTORE DATABASE @databaseName FROM  DISK = @backupFileName WITH  REPLACE;`

## pseudocode

```c

```

## disassembly

```asm
0x7b80  ldarg.2
0x7b81  ldstr    aSqlservername// "SqlServerName"
0x7b86  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7b8b  ldarg.1
0x7b8c  ldstr    aDatabasename// "DatabaseName"
0x7b91  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7b96  ldarg.3
0x7b97  ldstr    aBackupfilename// "BackupFileName"
0x7b9c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7ba1  ldarg.2
0x7ba2  call     class [System.Data]System.Data.SqlClient.SqlConnection [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.SqlUtility::GetConnection(string)
0x7ba7  stloc.0
0x7ba8  ldloc.0
0x7ba9  callvirt instance class [System.Data]System.Data.SqlClient.SqlCommand [System.Data]System.Data.SqlClient.SqlConnection::CreateCommand()
0x7bae  stloc.1
0x7baf  ldloc.1
0x7bb0  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x7bb5  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x7bba  ldloc.1
0x7bbb  ldstr    aRestoreDatabas// "RESTORE DATABASE @databaseName FROM  DI"...
0x7bc0  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x7bc5  dup
0x7bc6  ldstr    aDatabasename_0// "@databaseName"
0x7bcb  ldarg.1
0x7bcc  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7bd1  pop
0x7bd2  ldstr    aBackupfilename_0// "@backupFileName"
0x7bd7  ldarg.3
0x7bd8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7bdd  pop
0x7bde  ldstr    aStartRestoring// "[start] Restoring the database {0} onto"...
0x7be3  ldc.i4.3
0x7be4  newarr   [mscorlib]System.Object
0x7be9  dup
0x7bea  ldc.i4.0
0x7beb  ldarg.1
0x7bec  stelem.ref
0x7bed  dup
0x7bee  ldc.i4.1
0x7bef  ldarg.2
0x7bf0  stelem.ref
0x7bf1  dup
0x7bf2  ldc.i4.2
0x7bf3  ldarg.3
0x7bf4  stelem.ref
0x7bf5  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x7bfa  ldloc.0
0x7bfb  callvirt instance void [System.Data]System.Data.Common.DbConnection::Open()
0x7c00  ldloc.1
0x7c01  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x7c06  pop
0x7c07  ldstr    aSuccessfullyRe// "Successfully restored the database {0} "...
0x7c0c  ldc.i4.3
0x7c0d  newarr   [mscorlib]System.Object
0x7c12  dup
0x7c13  ldc.i4.0
0x7c14  ldarg.1
0x7c15  stelem.ref
0x7c16  dup
0x7c17  ldc.i4.1
0x7c18  ldarg.2
0x7c19  stelem.ref
0x7c1a  dup
0x7c1b  ldc.i4.2
0x7c1c  ldarg.3
0x7c1d  stelem.ref
0x7c1e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x7c23  leave.s  loc_7C90
0x7c25  stloc.2
0x7c26  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7c2b  ldstr    aErrorWhenTryin_1// "Error when trying to restore the databa"...
0x7c30  ldc.i4.3
0x7c31  newarr   [mscorlib]System.Object
0x7c36  dup
0x7c37  ldc.i4.0
0x7c38  ldarg.1
0x7c39  stelem.ref
0x7c3a  dup
0x7c3b  ldc.i4.1
0x7c3c  ldarg.2
0x7c3d  stelem.ref
0x7c3e  dup
0x7c3f  ldc.i4.2
0x7c40  ldarg.3
0x7c41  stelem.ref
0x7c42  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7c47  ldloc.2
0x7c48  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteError(string, class [mscorlib]System.Exception)
0x7c4d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7c52  ldstr    aErrorWhenTryin_1// "Error when trying to restore the databa"...
0x7c57  ldc.i4.3
0x7c58  newarr   [mscorlib]System.Object
0x7c5d  dup
0x7c5e  ldc.i4.0
0x7c5f  ldarg.1
0x7c60  stelem.ref
0x7c61  dup
0x7c62  ldc.i4.1
0x7c63  ldarg.2
0x7c64  stelem.ref
0x7c65  dup
0x7c66  ldc.i4.2
0x7c67  ldarg.3
0x7c68  stelem.ref
0x7c69  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7c6e  ldloc.2
0x7c6f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x7c74  throw
0x7c75  ldloc.0
0x7c76  callvirt instance void [System.Data]System.Data.Common.DbConnection::Close()
0x7c7b  endfinally
0x7c7c  ldloc.1
0x7c7d  brfalse.s loc_7C85
0x7c7f  ldloc.1
0x7c80  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7c85  endfinally
0x7c86  ldloc.0
0x7c87  brfalse.s loc_7C8F
0x7c89  ldloc.0
0x7c8a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7c8f  endfinally
0x7c90  ret
```
