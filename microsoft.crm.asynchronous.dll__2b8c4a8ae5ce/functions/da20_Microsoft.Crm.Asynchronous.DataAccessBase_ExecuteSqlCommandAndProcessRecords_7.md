# Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords_7

- ea: `0xda20`
- end: `0xdb97`
- name: `Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords_7`
- size: `375`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0xd660`
- `0xd770`
- `0xd9b0`

## callees

- `0x520`
- `0x570`
- `0xd9c0`
- `0xda20`
- `0xe170`
- `0xe1a0`
- `0xe360`
- `0xe380`
- `0x17b80`

## string_xrefs

- `0xdae4`: `Exception while trying to open database connection for organization {0}`
- `0xdb1d`: `ExecuteSqlCommandAndProcessRecords`
- `0xdb22`: `d:\dbs\sh\dccm2\1101_190851\cmd\13\src\Core\ObjectModel\Async\Shared\DataAccessBase.cs`

## pseudocode

```c

```

## disassembly

```asm
0xda20  ldc.i4.0
0xda21  stloc.0
0xda22  ldarg.3
0xda23  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xda28  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xda2d  brfalse.s loc_DA45
0xda2f  ldarg.0
0xda30  ldarg.1
0xda31  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(class [System.Data]System.Data.IDbCommand)
0xda36  ldarg.2
0xda37  ldarg.3
0xda38  ldarg.s  4
0xda3a  call     instance int32 Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo command, class RecordProcessor recordProcessor, valuetype [mscorlib]System.Guid inputOrganizationId, [out] string& databaseName)
0xda3f  stloc.0
0xda40  br       loc_DB95
0xda45  ldarg.3
0xda46  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xda4b  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xda50  brtrue.s loc_DA5B
0xda52  ldarg.0
0xda53  ldarg.3
0xda54  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.DataAccessSharedBase::CreateConnection(valuetype [mscorlib]System.Guid organizationId)
0xda59  br.s     loc_DA61
0xda5b  ldarg.0
0xda5c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.DataAccessSharedBase::CreateConnection()
0xda61  stloc.1
0xda62  ldstr    aConnectionStri// "Connection String: "
0xda67  stloc.3
0xda68  ldloc.1
0xda69  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_ConnectionString()
0xda6e  ldloca.s 2
0xda70  call     bool Microsoft.Crm.Asynchronous.ConnectionString::TryParse(string connectionString, [out] class Microsoft.Crm.Asynchronous.ConnectionString& value)
0xda75  brfalse.s loc_DAA9
0xda77  ldstr    aDataSource0// "Data Source: {0}"
0xda7c  ldloc.2
0xda7d  ldstr    aDataSource// "Data Source"
0xda82  callvirt instance string Microsoft.Crm.Asynchronous.ConnectionString::get_Item(string key)
0xda87  call     string [mscorlib]System.String::Format(string, object)
0xda8c  stloc.3
0xda8d  ldloc.3
0xda8e  ldstr    aInitialCatalog// "Initial Catalog: {0}"
0xda93  ldloc.2
0xda94  ldstr    aInitialCatalog_0// "Initial Catalog"
0xda99  callvirt instance string Microsoft.Crm.Asynchronous.ConnectionString::get_Item(string key)
0xda9e  call     string [mscorlib]System.String::Format(string, object)
0xdaa3  call     string [mscorlib]System.String::Concat(string, string)
0xdaa8  stloc.3
0xdaa9  nop
0xdaaa  ldloc.1
0xdaab  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0xdab0  leave.s  loc_DB01
0xdab2  stloc.s  4
0xdab4  ldarg.0
0xdab5  ldloc.s  4
0xdab7  ldnull
0xdab8  ldstr    a0Exception1// "{0} | Exception - {1}"
0xdabd  ldloc.3
0xdabe  ldloc.s  4
0xdac0  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0xdac5  call     string [mscorlib]System.String::Format(string, object, object)
0xdaca  ldloc.1
0xdacb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_OrganizationId()
0xdad0  ldarg.0
0xdad1  callvirt instance string Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_Name()
0xdad6  callvirt instance void Microsoft.Crm.Asynchronous.DataAccessSharedBase::HandleDatabaseException(class [mscorlib]System.Exception exception, class [System.Data]System.Data.IDbCommand command, string contextMessage, valuetype [mscorlib]System.Guid organizationId, string instanceName)
0xdadb  leave.s  loc_DB01
0xdadd  stloc.s  5
0xdadf  ldarg.0
0xdae0  ldloc.s  5
0xdae2  ldnull
0xdae3  ldloc.3
0xdae4  ldstr    aExceptionWhile_2// "Exception while trying to open database"...
0xdae9  call     string [mscorlib]System.String::Concat(string, string)
0xdaee  ldloc.1
0xdaef  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_OrganizationId()
0xdaf4  ldarg.0
0xdaf5  callvirt instance string Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_Name()
0xdafa  callvirt instance void Microsoft.Crm.Asynchronous.DataAccessSharedBase::HandleDatabaseException(class [mscorlib]System.Exception exception, class [System.Data]System.Data.IDbCommand command, string contextMessage, valuetype [mscorlib]System.Guid organizationId, string instanceName)
0xdaff  rethrow
0xdb01  ldloc.1
0xdb02  ldarga.s 1
0xdb04  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(class [System.Data]System.Data.IDbCommand&)
0xdb09  ldarg.s  4
0xdb0b  ldarg.1
0xdb0c  callvirt instance class [System.Data]System.Data.IDbConnection [System.Data]System.Data.IDbCommand::get_Connection()
0xdb11  callvirt instance string [System.Data]System.Data.IDbConnection::get_Database()
0xdb16  stind.ref
0xdb17  ldarg.1
0xdb18  ldc.i4   0x17F
0xdb1d  ldstr    aExecutesqlcomm// "ExecuteSqlCommandAndProcessRecords"
0xdb22  ldstr    aDDbsShDccm2110_0// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\1"...
0xdb27  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xdb2c  stloc.s  6
0xdb2e  ldloc.s  6
0xdb30  callvirt instance int32 [System.Data]System.Data.IDataRecord::get_FieldCount()
0xdb35  newarr   [mscorlib]System.Object
0xdb3a  stloc.s  7
0xdb3c  br.s     loc_DB54
0xdb3e  ldloc.s  6
0xdb40  ldloc.s  7
0xdb42  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetValues(object[])
0xdb47  pop
0xdb48  ldarg.2
0xdb49  ldloc.s  7
0xdb4b  callvirt instance void RecordProcessor::Invoke(object[] columnValues)
0xdb50  ldloc.0
0xdb51  ldc.i4.1
0xdb52  add
0xdb53  stloc.0
0xdb54  ldloc.s  6
0xdb56  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0xdb5b  brtrue.s loc_DB3E
0xdb5d  leave.s  loc_DB6B
0xdb5f  ldloc.s  6
0xdb61  brfalse.s loc_DB6A
0xdb63  ldloc.s  6
0xdb65  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdb6a  endfinally
0xdb6b  leave.s  loc_DB95
0xdb6d  stloc.s  8
0xdb6f  ldarg.0
0xdb70  ldloc.s  8
0xdb72  ldarg.1
0xdb73  ldstr    aExceptionWhile_3// "Exception while executing database quer"...
0xdb78  ldloc.1
0xdb79  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_OrganizationId()
0xdb7e  ldarg.0
0xdb7f  callvirt instance string Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_Name()
0xdb84  callvirt instance void Microsoft.Crm.Asynchronous.DataAccessSharedBase::HandleDatabaseException(class [mscorlib]System.Exception exception, class [System.Data]System.Data.IDbCommand command, string contextMessage, valuetype [mscorlib]System.Guid organizationId, string instanceName)
0xdb89  rethrow
0xdb8b  ldloc.1
0xdb8c  brfalse.s loc_DB94
0xdb8e  ldloc.1
0xdb8f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdb94  endfinally
0xdb95  ldloc.0
0xdb96  ret
```
