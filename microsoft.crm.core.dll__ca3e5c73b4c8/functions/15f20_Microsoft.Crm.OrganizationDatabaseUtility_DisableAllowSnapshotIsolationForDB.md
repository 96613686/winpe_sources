# Microsoft.Crm.OrganizationDatabaseUtility::DisableAllowSnapshotIsolationForDB

- ea: `0x15f20`
- end: `0x15fb1`
- name: `Microsoft.Crm.OrganizationDatabaseUtility::DisableAllowSnapshotIsolationForDB`
- size: `145`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0xd020`
- `0xd180`
- `0xd2f0`
- `0xd5f0`
- `0xdab0`
- `0x15f20`
- `0x368f0`

## string_xrefs

- `0x15f8f`: `D:\a\1\s\src\Platform\Core\DataServices\OrganizationDatabaseUtility.cs`
- `0x15f20`: `IF ( CAST((select snapshot_isolation_state from sys.databases where name = @databaseName) AS BIT) = 1)\nBEGIN\nalter database {0} set single_user with rollback immediate;\nalter database {0} set allow_snapshot_isolation OFF;\nalter database {0} set multi_user;\nEND`

## pseudocode

```c

```

## disassembly

```asm
0x15f20  ldstr    aIfCastSelectSn// "IF ( CAST((select snapshot_isolation_st"...
0x15f25  stloc.0
0x15f26  ldarg.0
0x15f27  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.OrganizationDatabaseUtility::_organizationId
0x15f2c  ldc.i4.0
0x15f2d  ldc.i4.0
0x15f2e  newobj   instance void Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid organizationId, [opt] bool isReader, [opt] valuetype Microsoft.Crm.ReadPriority priority)
0x15f33  stloc.1
0x15f34  ldloc.1
0x15f35  callvirt instance void Microsoft.Crm.CrmDbConnection::Open()
0x15f3a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15f3f  ldloc.0
0x15f40  ldc.i4.1
0x15f41  newarr   [mscorlib]System.Object
0x15f46  dup
0x15f47  ldc.i4.0
0x15f48  ldloc.1
0x15f49  callvirt instance string Microsoft.Crm.CrmDbConnection::get_Database()
0x15f4e  call     string Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string input)
0x15f53  stelem.ref
0x15f54  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15f59  stloc.2
0x15f5a  ldloc.1
0x15f5b  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.CrmDbConnection::CreateCommand()
0x15f60  stloc.3
0x15f61  ldloc.3
0x15f62  ldloc.2
0x15f63  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x15f68  ldloc.3
0x15f69  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x15f6e  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x15f73  ldstr    aDatabasename_0// "@databaseName"
0x15f78  ldloc.1
0x15f79  callvirt instance string Microsoft.Crm.CrmDbConnection::get_Database()
0x15f7e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x15f83  pop
0x15f84  ldloc.3
0x15f85  ldc.i4   0x1E6
0x15f8a  ldstr    aDisableallowsn// "DisableAllowSnapshotIsolationForDB"
0x15f8f  ldstr    aDA1SSrcPlatfor_10// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x15f94  call     int32 Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x15f99  pop
0x15f9a  leave.s  loc_15FB0
0x15f9c  ldloc.3
0x15f9d  brfalse.s loc_15FA5
0x15f9f  ldloc.3
0x15fa0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15fa5  endfinally
0x15fa6  ldloc.1
0x15fa7  brfalse.s loc_15FAF
0x15fa9  ldloc.1
0x15faa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15faf  endfinally
0x15fb0  ret
```
