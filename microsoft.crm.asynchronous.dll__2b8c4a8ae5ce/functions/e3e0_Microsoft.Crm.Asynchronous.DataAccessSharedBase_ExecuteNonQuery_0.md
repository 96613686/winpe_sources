# Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteNonQuery_0

- ea: `0xe3e0`
- end: `0xe48d`
- name: `Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteNonQuery_0`
- size: `173`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xe1f0`
- `0xe200`

## callees

- `0xe170`
- `0xe1a0`
- `0xe360`
- `0xe3e0`

## string_xrefs

- `0xe413`: `Exception while trying to open database connection for organization {0}`
- `0xe450`: `d:\dbs\sh\dccm2\1101_190851\cmd\13\src\Core\ObjectModel\Async\Shared\DataAccessSharedBase.cs`

## pseudocode

```c

```

## disassembly

```asm
0xe3e0  ldarg.0
0xe3e1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.DataAccessSharedBase::CreateConnection()
0xe3e6  stloc.0
0xe3e7  ldloc.0
0xe3e8  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0xe3ed  leave.s  loc_E430
0xe3ef  stloc.2
0xe3f0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe3f5  ldstr    aConnectionstri_0// "ConnectionString: {0}, "
0xe3fa  ldc.i4.1
0xe3fb  newarr   [mscorlib]System.Object
0xe400  dup
0xe401  ldc.i4.0
0xe402  ldloc.0
0xe403  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_ConnectionString()
0xe408  stelem.ref
0xe409  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe40e  stloc.3
0xe40f  ldarg.0
0xe410  ldloc.2
0xe411  ldnull
0xe412  ldloc.3
0xe413  ldstr    aExceptionWhile_2// "Exception while trying to open database"...
0xe418  call     string [mscorlib]System.String::Concat(string, string)
0xe41d  ldloc.0
0xe41e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_OrganizationId()
0xe423  ldarg.0
0xe424  callvirt instance string Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_Name()
0xe429  callvirt instance void Microsoft.Crm.Asynchronous.DataAccessSharedBase::HandleDatabaseException(class [mscorlib]System.Exception exception, class [System.Data]System.Data.IDbCommand command, string contextMessage, valuetype [mscorlib]System.Guid organizationId, string instanceName)
0xe42e  rethrow
0xe430  ldloc.0
0xe431  ldarga.s 1
0xe433  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(class [System.Data]System.Data.IDbCommand&)
0xe438  ldarg.2
0xe439  ldarg.1
0xe43a  callvirt instance class [System.Data]System.Data.IDbConnection [System.Data]System.Data.IDbCommand::get_Connection()
0xe43f  callvirt instance string [System.Data]System.Data.IDbConnection::get_Database()
0xe444  stind.ref
0xe445  ldarg.1
0xe446  ldc.i4   0xB0
0xe44b  ldstr    aExecutenonquer// "ExecuteNonQuery"
0xe450  ldstr    aDDbsShDccm2110_1// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\1"...
0xe455  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xe45a  stloc.1
0xe45b  leave.s  loc_E47B
0xe45d  stloc.s  4
0xe45f  ldarg.0
0xe460  ldloc.s  4
0xe462  ldarg.1
0xe463  ldstr    aExceptionWhile_3// "Exception while executing database quer"...
0xe468  ldloc.0
0xe469  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_OrganizationId()
0xe46e  ldarg.0
0xe46f  callvirt instance string Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_Name()
0xe474  callvirt instance void Microsoft.Crm.Asynchronous.DataAccessSharedBase::HandleDatabaseException(class [mscorlib]System.Exception exception, class [System.Data]System.Data.IDbCommand command, string contextMessage, valuetype [mscorlib]System.Guid organizationId, string instanceName)
0xe479  rethrow
0xe47b  ldloc.1
0xe47c  stloc.s  5
0xe47e  leave.s  loc_E48A
0xe480  ldloc.0
0xe481  brfalse.s loc_E489
0xe483  ldloc.0
0xe484  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe489  endfinally
0xe48a  ldloc.s  5
0xe48c  ret
```
