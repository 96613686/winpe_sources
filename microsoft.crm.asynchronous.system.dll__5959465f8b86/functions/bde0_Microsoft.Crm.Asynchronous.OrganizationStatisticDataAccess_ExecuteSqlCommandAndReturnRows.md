# Microsoft.Crm.Asynchronous.OrganizationStatisticDataAccess::ExecuteSqlCommandAndReturnRows

- ea: `0xbde0`
- end: `0xbedd`
- name: `Microsoft.Crm.Asynchronous.OrganizationStatisticDataAccess::ExecuteSqlCommandAndReturnRows`
- size: `253`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xb4c0`
- `0xb8b0`
- `0xb9c0`

## callees

- `0xbde0`
- `0xbf70`

## string_xrefs

- `0xbdf9`: `Exception while trying to open database connection for organization {0}`
- `0xbe15`: `OrganizationStatisticDataAccess: Exception while trying to open the database connection {0} : {1}`
- `0xbe44`: `ExecuteSqlCommandAndReturnRows`
- `0xbe49`: `d:\dbs\sh\dccm2\1101_190851\cmd\5\src\Core\ObjectModel\Async\Handlers\System\StatisticsSqm\OrganizationStatisticsDataAccess.cs`
- `0xbeac`: `OrganizationStatisticDataAccess: Exception while trying to execute query: {0} - {1}`

## pseudocode

```c

```

## disassembly

```asm
0xbde0  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object[]>::.ctor()
0xbde5  stloc.0
0xbde6  ldarg.0
0xbde7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::CreateConnection()
0xbdec  stloc.1
0xbded  ldloc.1
0xbdee  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0xbdf3  leave.s  loc_BE39
0xbdf5  stloc.2
0xbdf6  ldarg.0
0xbdf7  ldloc.2
0xbdf8  ldnull
0xbdf9  ldstr    aExceptionWhile_1// "Exception while trying to open database"...
0xbdfe  ldloc.1
0xbdff  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_OrganizationId()
0xbe04  ldarg.0
0xbe05  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_Name()
0xbe0a  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::HandleDatabaseException(class [mscorlib]System.Exception, class [System.Data]System.Data.IDbCommand, string, valuetype [mscorlib]System.Guid, string)
0xbe0f  ldarg.0
0xbe10  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbe15  ldstr    aOrganizationst_0// "OrganizationStatisticDataAccess: Except"...
0xbe1a  ldc.i4.2
0xbe1b  newarr   [mscorlib]System.Object
0xbe20  dup
0xbe21  ldc.i4.0
0xbe22  ldloc.1
0xbe23  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_ConnectionString()
0xbe28  stelem.ref
0xbe29  dup
0xbe2a  ldc.i4.1
0xbe2b  ldloc.2
0xbe2c  stelem.ref
0xbe2d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbe32  call     instance void Microsoft.Crm.Asynchronous.OrganizationStatisticDataAccess::LogSqlError(string error)
0xbe37  rethrow
0xbe39  ldloc.1
0xbe3a  ldarga.s 1
0xbe3c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(class [System.Data]System.Data.IDbCommand&)
0xbe41  ldarg.1
0xbe42  ldc.i4.s 0x45
0xbe44  ldstr    aExecutesqlcomm// "ExecuteSqlCommandAndReturnRows"
0xbe49  ldstr    aDDbsShDccm2110_14// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\5"...
0xbe4e  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xbe53  stloc.3
0xbe54  br.s     loc_BE74
0xbe56  ldloc.3
0xbe57  callvirt instance int32 [System.Data]System.Data.IDataRecord::get_FieldCount()
0xbe5c  newarr   [mscorlib]System.Object
0xbe61  stloc.s  4
0xbe63  ldloc.3
0xbe64  ldloc.s  4
0xbe66  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetValues(object[])
0xbe6b  pop
0xbe6c  ldloc.0
0xbe6d  ldloc.s  4
0xbe6f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object[]>::Add(var<u1>)
0xbe74  ldloc.3
0xbe75  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0xbe7a  brtrue.s loc_BE56
0xbe7c  leave.s  loc_BE88
0xbe7e  ldloc.3
0xbe7f  brfalse.s loc_BE87
0xbe81  ldloc.3
0xbe82  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbe87  endfinally
0xbe88  leave.s  loc_BEDB
0xbe8a  stloc.s  5
0xbe8c  ldarg.0
0xbe8d  ldloc.s  5
0xbe8f  ldarg.1
0xbe90  ldstr    aExceptionWhile_2// "Exception while executing database quer"...
0xbe95  ldloc.1
0xbe96  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_OrganizationId()
0xbe9b  ldarg.0
0xbe9c  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_Name()
0xbea1  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::HandleDatabaseException(class [mscorlib]System.Exception, class [System.Data]System.Data.IDbCommand, string, valuetype [mscorlib]System.Guid, string)
0xbea6  ldarg.0
0xbea7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbeac  ldstr    aOrganizationst_1// "OrganizationStatisticDataAccess: Except"...
0xbeb1  ldc.i4.2
0xbeb2  newarr   [mscorlib]System.Object
0xbeb7  dup
0xbeb8  ldc.i4.0
0xbeb9  ldloc.1
0xbeba  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_ConnectionString()
0xbebf  stelem.ref
0xbec0  dup
0xbec1  ldc.i4.1
0xbec2  ldloc.s  5
0xbec4  stelem.ref
0xbec5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbeca  call     instance void Microsoft.Crm.Asynchronous.OrganizationStatisticDataAccess::LogSqlError(string error)
0xbecf  rethrow
0xbed1  ldloc.1
0xbed2  brfalse.s loc_BEDA
0xbed4  ldloc.1
0xbed5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbeda  endfinally
0xbedb  ldloc.0
0xbedc  ret
```
