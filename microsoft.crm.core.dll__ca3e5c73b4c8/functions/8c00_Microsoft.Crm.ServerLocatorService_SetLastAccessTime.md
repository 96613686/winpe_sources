# Microsoft.Crm.ServerLocatorService::SetLastAccessTime

- ea: `0x8c00`
- end: `0x8d12`
- name: `Microsoft.Crm.ServerLocatorService::SetLastAccessTime`
- size: `274`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7240`
- `0x8370`
- `0x8c00`
- `0xbfc0`
- `0xd2f0`
- `0xd620`
- `0xdab0`
- `0x1be90`
- `0x4d750`
- `0x626d0`

## string_xrefs

- `0x8ce8`: `GeoReadOnlyModeEnabled`
- `0x8cc4`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0x8c3b`: `exec p_SetLastAccessTime @OrganizationId, @CrmUserId, @LastAccessTime, @LastAccessServer`
- `0x8c89`: `@LastAccessTime`
- `0x8ca5`: `@LastAccessServer`
- `0x8cbf`: `SetLastAccessTime`

## pseudocode

```c

```

## disassembly

```asm
0x8c00  ldarg.1
0x8c01  ldstr    aOrganizationid_0// "organizationId"
0x8c06  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0x8c0b  ldarg.2
0x8c0c  ldstr    aUserid_0// "userId"
0x8c11  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0x8c16  ldstr    aLocalhost// "localhost"
0x8c1b  call     class [System]System.Net.IPHostEntry [System]System.Net.Dns::GetHostEntry(string)
0x8c20  callvirt instance string [System]System.Net.IPHostEntry::get_HostName()
0x8c25  stloc.0
0x8c26  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x8c2b  stloc.1
0x8c2c  ldloc.1
0x8c2d  ldc.i4.2
0x8c2e  callvirt instance class Microsoft.Crm.CrmDbConnection Microsoft.Crm.SharedDatabase.DatabaseService::CreateConnection(valuetype Microsoft.Crm.SharedDatabase.ConfigScope scope)
0x8c33  stloc.2
0x8c34  ldloc.2
0x8c35  callvirt instance void Microsoft.Crm.CrmDbConnection::Open()
0x8c3a  ldloc.2
0x8c3b  ldstr    aExecPSetlastac// "exec p_SetLastAccessTime @OrganizationI"...
0x8c40  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.CrmDbConnection::CreateCommand(string commandText)
0x8c45  stloc.3
0x8c46  ldloc.3
0x8c47  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x8c4c  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x8c51  ldstr    aOrganizationid_2// "@OrganizationId"
0x8c56  ldarg.1
0x8c57  box      [mscorlib]System.Guid
0x8c5c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8c61  pop
0x8c62  ldloc.3
0x8c63  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x8c68  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x8c6d  ldstr    aCrmuserid_1// "@CrmUserId"
0x8c72  ldarg.2
0x8c73  box      [mscorlib]System.Guid
0x8c78  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8c7d  pop
0x8c7e  ldloc.3
0x8c7f  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x8c84  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x8c89  ldstr    aLastaccesstime_0// "@LastAccessTime"
0x8c8e  ldarg.3
0x8c8f  box      [mscorlib]System.DateTime
0x8c94  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8c99  pop
0x8c9a  ldloc.3
0x8c9b  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x8ca0  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x8ca5  ldstr    aLastaccessserv// "@LastAccessServer"
0x8caa  ldloc.0
0x8cab  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8cb0  pop
0x8cb1  ldc.i4.1
0x8cb2  ldc.i4.2
0x8cb3  ldloc.3
0x8cb4  call     void Microsoft.Crm.ServerLocatorService::LogSqlCommand(valuetype Microsoft.Crm.InstrumentationOperationType type, valuetype Microsoft.Crm.SharedDatabase.ConfigScope scope, class [System.Data]System.Data.IDbCommand command)
0x8cb9  ldloc.3
0x8cba  ldc.i4   0x59A
0x8cbf  ldstr    aSetlastaccesst// "SetLastAccessTime"
0x8cc4  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x8cc9  call     int32 Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x8cce  pop
0x8ccf  leave.s  loc_8CDB
0x8cd1  ldloc.3
0x8cd2  brfalse.s loc_8CDA
0x8cd4  ldloc.3
0x8cd5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8cda  endfinally
0x8cdb  leave.s  loc_8D11
0x8cdd  pop
0x8cde  ldarg.0
0x8cdf  call     instance valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.ServerLocatorService::GetSku()
0x8ce4  ldc.i4.2
0x8ce5  bne.un.s loc_8CF9
0x8ce7  ldarg.0
0x8ce8  ldstr    aGeoreadonlymod// "GeoReadOnlyModeEnabled"
0x8ced  callvirt instance object Microsoft.Crm.ServerLocatorService::GetSiteSetting(string settingName)
0x8cf2  unbox.any [mscorlib]System.Boolean
0x8cf7  brtrue.s loc_8CFB
0x8cf9  rethrow
0x8cfb  leave.s  loc_8D11
0x8cfd  ldloc.2
0x8cfe  brfalse.s loc_8D06
0x8d00  ldloc.2
0x8d01  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8d06  endfinally
0x8d07  ldloc.1
0x8d08  brfalse.s loc_8D10
0x8d0a  ldloc.1
0x8d0b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8d10  endfinally
0x8d11  ret
```
