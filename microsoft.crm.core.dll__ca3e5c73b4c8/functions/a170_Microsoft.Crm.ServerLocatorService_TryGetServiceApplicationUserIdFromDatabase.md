# Microsoft.Crm.ServerLocatorService::TryGetServiceApplicationUserIdFromDatabase

- ea: `0xa170`
- end: `0xa276`
- name: `Microsoft.Crm.ServerLocatorService::TryGetServiceApplicationUserIdFromDatabase`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6d20`

## callees

- `0xa170`
- `0xbfc0`
- `0xd2f0`
- `0xd620`
- `0xdb00`
- `0x1be90`
- `0x4d7b0`
- `0x626d0`

## string_xrefs

- `0xa1ff`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0xa171`: `tokenApplicationId`
- `0xa1fa`: `TryGetServiceApplicationUserIdFromDatabase`

## pseudocode

```c

```

## disassembly

```asm
0xa170  ldarg.2
0xa171  ldstr    aTokenapplicati// "tokenApplicationId"
0xa176  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0xa17b  ldarg.1
0xa17c  ldstr    aOrganizationid_0// "organizationId"
0xa181  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0xa186  ldarg.3
0xa187  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa18c  stobj    [mscorlib]System.Guid
0xa191  ldarg.0
0xa192  ldfld    valuetype Microsoft.Crm.LocatorServiceContext Microsoft.Crm.ServerLocatorService::_locatorServiceContext
0xa197  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor(valuetype Microsoft.Crm.LocatorServiceContext locatorServiceContext)
0xa19c  stloc.0
0xa19d  ldloc.0
0xa19e  ldc.i4.2
0xa19f  callvirt instance class Microsoft.Crm.CrmDbConnection Microsoft.Crm.SharedDatabase.DatabaseService::CreateConnection(valuetype Microsoft.Crm.SharedDatabase.ConfigScope scope)
0xa1a4  stloc.1
0xa1a5  ldloc.1
0xa1a6  callvirt instance void Microsoft.Crm.CrmDbConnection::Open()
0xa1ab  ldloc.1
0xa1ac  ldstr    aExecPGetdefaul// "exec p_GetDefaultOrgFromAuthInfo @AuthI"...
0xa1b1  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.CrmDbConnection::CreateCommand(string commandText)
0xa1b6  stloc.2
0xa1b7  ldloc.2
0xa1b8  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xa1bd  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xa1c2  ldstr    aAuthinfo_0// "@AuthInfo"
0xa1c7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa1cc  ldstr    aAppid0// "appid:{0}"
0xa1d1  ldc.i4.1
0xa1d2  newarr   [mscorlib]System.Object
0xa1d7  dup
0xa1d8  ldc.i4.0
0xa1d9  ldarg.2
0xa1da  box      [mscorlib]System.Guid
0xa1df  stelem.ref
0xa1e0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa1e5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xa1ea  pop
0xa1eb  ldc.i4.0
0xa1ec  ldc.i4.2
0xa1ed  ldloc.2
0xa1ee  call     void Microsoft.Crm.ServerLocatorService::LogSqlCommand(valuetype Microsoft.Crm.InstrumentationOperationType type, valuetype Microsoft.Crm.SharedDatabase.ConfigScope scope, class [System.Data]System.Data.IDbCommand command)
0xa1f3  ldloc.2
0xa1f4  ldc.i4.1
0xa1f5  ldc.i4   0x8FC
0xa1fa  ldstr    aTrygetservicea// "TryGetServiceApplicationUserIdFromDatab"...
0xa1ff  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xa204  call     class [System.Data]System.Data.IDataReader Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand command, bool impersonate, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xa209  stloc.3
0xa20a  ldloc.3
0xa20b  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0xa210  brfalse.s loc_A23C
0xa212  ldloc.3
0xa213  ldstr    aOrganizationid_1// "OrganizationId"
0xa218  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xa21d  unbox.any [mscorlib]System.Guid
0xa222  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa227  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xa22c  brfalse.s loc_A237
0xa22e  ldarg.3
0xa22f  ldarg.2
0xa230  stobj    [mscorlib]System.Guid
0xa235  leave.s  loc_A266
0xa237  ldc.i4.0
0xa238  stloc.s  4
0xa23a  leave.s  loc_A273
0xa23c  leave.s  loc_A266
0xa23e  ldloc.3
0xa23f  brfalse.s loc_A247
0xa241  ldloc.3
0xa242  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa247  endfinally
0xa248  ldloc.2
0xa249  brfalse.s loc_A251
0xa24b  ldloc.2
0xa24c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa251  endfinally
0xa252  ldloc.1
0xa253  brfalse.s loc_A25B
0xa255  ldloc.1
0xa256  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa25b  endfinally
0xa25c  ldloc.0
0xa25d  brfalse.s loc_A265
0xa25f  ldloc.0
0xa260  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa265  endfinally
0xa266  ldarg.2
0xa267  ldarg.3
0xa268  ldobj    [mscorlib]System.Guid
0xa26d  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xa272  ret
0xa273  ldloc.s  4
0xa275  ret
```
