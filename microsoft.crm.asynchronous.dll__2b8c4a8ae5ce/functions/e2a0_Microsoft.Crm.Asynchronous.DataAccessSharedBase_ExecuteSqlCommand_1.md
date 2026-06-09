# Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand_1

- ea: `0xe2a0`
- end: `0xe355`
- name: `Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand_1`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0xe290`

## callees

- `0xe170`
- `0xe1a0`
- `0xe2a0`
- `0xe360`
- `0xe380`

## string_xrefs

- `0xe2e9`: `Exception while trying to open database connection for organization {0}`
- `0xe313`: `ExecuteSqlCommand`
- `0xe318`: `d:\dbs\sh\dccm2\1101_190851\cmd\13\src\Core\ObjectModel\Async\Shared\DataAccessSharedBase.cs`

## pseudocode

```c

```

## disassembly

```asm
0xe2a0  ldarg.2
0xe2a1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xe2a6  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xe2ab  brtrue.s loc_E2B6
0xe2ad  ldarg.0
0xe2ae  ldarg.2
0xe2af  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.DataAccessSharedBase::CreateConnection(valuetype [mscorlib]System.Guid organizationId)
0xe2b4  br.s     loc_E2BC
0xe2b6  ldarg.0
0xe2b7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.DataAccessSharedBase::CreateConnection()
0xe2bc  stloc.0
0xe2bd  ldloc.0
0xe2be  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0xe2c3  leave.s  loc_E306
0xe2c5  stloc.2
0xe2c6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe2cb  ldstr    aConnectionstri_0// "ConnectionString: {0}, "
0xe2d0  ldc.i4.1
0xe2d1  newarr   [mscorlib]System.Object
0xe2d6  dup
0xe2d7  ldc.i4.0
0xe2d8  ldloc.0
0xe2d9  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_ConnectionString()
0xe2de  stelem.ref
0xe2df  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe2e4  stloc.3
0xe2e5  ldarg.0
0xe2e6  ldloc.2
0xe2e7  ldnull
0xe2e8  ldloc.3
0xe2e9  ldstr    aExceptionWhile_2// "Exception while trying to open database"...
0xe2ee  call     string [mscorlib]System.String::Concat(string, string)
0xe2f3  ldloc.0
0xe2f4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_OrganizationId()
0xe2f9  ldarg.0
0xe2fa  callvirt instance string Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_Name()
0xe2ff  callvirt instance void Microsoft.Crm.Asynchronous.DataAccessSharedBase::HandleDatabaseException(class [mscorlib]System.Exception exception, class [System.Data]System.Data.IDbCommand command, string contextMessage, valuetype [mscorlib]System.Guid organizationId, string instanceName)
0xe304  rethrow
0xe306  ldloc.0
0xe307  ldarga.s 1
0xe309  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(class [System.Data]System.Data.IDbCommand&)
0xe30e  ldnull
0xe30f  stloc.1
0xe310  ldarg.1
0xe311  ldc.i4.s 0x6B
0xe313  ldstr    aExecutesqlcomm_0// "ExecuteSqlCommand"
0xe318  ldstr    aDDbsShDccm2110_1// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\1"...
0xe31d  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteScalar(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xe322  stloc.1
0xe323  leave.s  loc_E343
0xe325  stloc.s  4
0xe327  ldarg.0
0xe328  ldloc.s  4
0xe32a  ldarg.1
0xe32b  ldstr    aExceptionWhile_3// "Exception while executing database quer"...
0xe330  ldloc.0
0xe331  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_OrganizationId()
0xe336  ldarg.0
0xe337  callvirt instance string Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_Name()
0xe33c  callvirt instance void Microsoft.Crm.Asynchronous.DataAccessSharedBase::HandleDatabaseException(class [mscorlib]System.Exception exception, class [System.Data]System.Data.IDbCommand command, string contextMessage, valuetype [mscorlib]System.Guid organizationId, string instanceName)
0xe341  rethrow
0xe343  ldloc.1
0xe344  stloc.s  5
0xe346  leave.s  loc_E352
0xe348  ldloc.0
0xe349  brfalse.s loc_E351
0xe34b  ldloc.0
0xe34c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe351  endfinally
0xe352  ldloc.s  5
0xe354  ret
```
