# Microsoft.Crm.Tools.Admin.DBImportHelper::SetIsActiveDirectoryUser

- ea: `0x13bb0`
- end: `0x13c33`
- name: `Microsoft.Crm.Tools.Admin.DBImportHelper::SetIsActiveDirectoryUser`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x13bb0`
- `0x14170`

## string_xrefs

- `0x13bcd`: `UPDATE SystemUserBase SET IsActiveDirectoryUser= @IsActiveDirectoryUser WHERE SystemUserId = @DBSystemUserId`
- `0x13be3`: `@IsActiveDirectoryUser`
- `0x13c0c`: `SetIsActiveDirectoryUser`

## pseudocode

```c

```

## disassembly

```asm
0x13bb0  ldarg.0
0x13bb1  ldarg.1
0x13bb2  ldc.i4.0
0x13bb3  ldc.i4.0
0x13bb4  call     string [Microsoft.Crm.DatabaseInstaller.Common]Microsoft.Crm.DatabaseInstaller.Common.SharedDatabaseUtility::GetConnectionString(string, string, bool, bool)
0x13bb9  newobj   instance void [System.Data]System.Data.SqlClient.SqlConnection::.ctor(string)
0x13bbe  stloc.0
0x13bbf  ldloc.0
0x13bc0  callvirt instance void [System.Data]System.Data.Common.DbConnection::Open()
0x13bc5  ldloc.0
0x13bc6  callvirt instance class [System.Data]System.Data.SqlClient.SqlCommand [System.Data]System.Data.SqlClient.SqlConnection::CreateCommand()
0x13bcb  stloc.1
0x13bcc  ldloc.1
0x13bcd  ldstr    aUpdateSystemus// "UPDATE SystemUserBase SET IsActiveDirec"...
0x13bd2  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x13bd7  ldloc.1
0x13bd8  ldarg.2
0x13bd9  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::get_DBIsActiveDirectoryUser()
0x13bde  box      [mscorlib]System.Boolean
0x13be3  ldstr    aIsactivedirect// "@IsActiveDirectoryUser"
0x13be8  ldc.i4.3
0x13be9  call     void Microsoft.Crm.Tools.Admin.DBImportHelper::AddParameter(class [System.Data]System.Data.IDbCommand command, object value, string parameterName, valuetype [System.Data]System.Data.DbType dbType)
0x13bee  ldloc.1
0x13bef  ldarg.2
0x13bf0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::get_DBSystemUserId()
0x13bf5  box      [mscorlib]System.Guid
0x13bfa  ldstr    aDbsystemuserid// "@DBSystemUserId"
0x13bff  ldc.i4.s 9
0x13c01  call     void Microsoft.Crm.Tools.Admin.DBImportHelper::AddParameter(class [System.Data]System.Data.IDbCommand command, object value, string parameterName, valuetype [System.Data]System.Data.DbType dbType)
0x13c06  ldloc.1
0x13c07  ldc.i4   0xCA
0x13c0c  ldstr    aSetisactivedir// "SetIsActiveDirectoryUser"
0x13c11  ldstr    aDDbsShDccm2110_10// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0x13c16  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x13c1b  pop
0x13c1c  leave.s  loc_13C32
0x13c1e  ldloc.1
0x13c1f  brfalse.s loc_13C27
0x13c21  ldloc.1
0x13c22  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13c27  endfinally
0x13c28  ldloc.0
0x13c29  brfalse.s loc_13C31
0x13c2b  ldloc.0
0x13c2c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13c31  endfinally
0x13c32  ret
```
