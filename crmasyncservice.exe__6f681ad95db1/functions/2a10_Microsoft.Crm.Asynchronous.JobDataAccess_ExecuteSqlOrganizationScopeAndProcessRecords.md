# Microsoft.Crm.Asynchronous.JobDataAccess::ExecuteSqlOrganizationScopeAndProcessRecords

- ea: `0x2a10`
- end: `0x2ade`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::ExecuteSqlOrganizationScopeAndProcessRecords`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x37f0`

## callees

- `0x2a10`

## string_xrefs

- `0x2a74`: `d:\dbs\sh\dccm2\1101_190851\cmd\34\src\Core\ObjectModel\Async\AsyncService\JobDataAccess.cs`
- `0x2a44`: `Exception while trying to open database connection for organization {0}`

## pseudocode

```c

```

## disassembly

```asm
0x2a10  ldarg.0
0x2a11  ldarg.2
0x2a12  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::CreateConnection(valuetype [mscorlib]System.Guid)
0x2a17  stloc.0
0x2a18  ldloc.0
0x2a19  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x2a1e  leave.s  loc_2A61
0x2a20  stloc.1
0x2a21  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2a26  ldstr    aConnectionstri// "ConnectionString: {0}, "
0x2a2b  ldc.i4.1
0x2a2c  newarr   [mscorlib]System.Object
0x2a31  dup
0x2a32  ldc.i4.0
0x2a33  ldloc.0
0x2a34  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_ConnectionString()
0x2a39  stelem.ref
0x2a3a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2a3f  stloc.2
0x2a40  ldarg.0
0x2a41  ldloc.1
0x2a42  ldnull
0x2a43  ldloc.2
0x2a44  ldstr    aExceptionWhile_3// "Exception while trying to open database"...
0x2a49  call     string [mscorlib]System.String::Concat(string, string)
0x2a4e  ldloc.0
0x2a4f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_OrganizationId()
0x2a54  ldarg.0
0x2a55  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_Name()
0x2a5a  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::HandleDatabaseException(class [mscorlib]System.Exception, class [System.Data]System.Data.IDbCommand, string, valuetype [mscorlib]System.Guid, string)
0x2a5f  rethrow
0x2a61  ldloc.0
0x2a62  ldarga.s 1
0x2a64  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(class [System.Data]System.Data.IDbCommand&)
0x2a69  ldarg.1
0x2a6a  ldc.i4   0x222
0x2a6f  ldstr    aExecutesqlorga// "ExecuteSqlOrganizationScopeAndProcessRe"...
0x2a74  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\3"...
0x2a79  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x2a7e  stloc.3
0x2a7f  ldloc.3
0x2a80  callvirt instance int32 [System.Data]System.Data.IDataRecord::get_FieldCount()
0x2a85  newarr   [mscorlib]System.Object
0x2a8a  stloc.s  4
0x2a8c  br.s     loc_2A9F
0x2a8e  ldloc.3
0x2a8f  ldloc.s  4
0x2a91  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetValues(object[])
0x2a96  pop
0x2a97  ldarg.3
0x2a98  ldloc.s  4
0x2a9a  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::Invoke(object[])
0x2a9f  ldloc.3
0x2aa0  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x2aa5  brtrue.s loc_2A8E
0x2aa7  leave.s  loc_2AB3
0x2aa9  ldloc.3
0x2aaa  brfalse.s loc_2AB2
0x2aac  ldloc.3
0x2aad  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2ab2  endfinally
0x2ab3  leave.s  loc_2ADD
0x2ab5  stloc.s  5
0x2ab7  ldarg.0
0x2ab8  ldloc.s  5
0x2aba  ldarg.1
0x2abb  ldstr    aExceptionWhile_4// "Exception while executing database quer"...
0x2ac0  ldloc.0
0x2ac1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_OrganizationId()
0x2ac6  ldarg.0
0x2ac7  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_Name()
0x2acc  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::HandleDatabaseException(class [mscorlib]System.Exception, class [System.Data]System.Data.IDbCommand, string, valuetype [mscorlib]System.Guid, string)
0x2ad1  rethrow
0x2ad3  ldloc.0
0x2ad4  brfalse.s loc_2ADC
0x2ad6  ldloc.0
0x2ad7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2adc  endfinally
0x2add  ret
```
