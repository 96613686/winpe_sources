# Microsoft.Crm.Asynchronous.ImportDataAccess::GetContentFromImportFile

- ea: `0x4320`
- end: `0x4416`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::GetContentFromImportFile`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14cb0`

## callees

- `0x4320`

## string_xrefs

- `0x434c`: `{Import}: Exception while trying to open the database connection {0} : {1}`
- `0x43a7`: `d:\dbs\sh\dccm2\1101_190851\cmd\32\src\Core\ObjectModel\Async\Handlers\DataManagement\ImportDataAccess.cs`

## pseudocode

```c

```

## disassembly

```asm
0x4320  ldsfld   string [mscorlib]System.String::Empty
0x4325  stloc.0
0x4326  ldsfld   string [mscorlib]System.String::Empty
0x432b  pop
0x432c  ldarg.0
0x432d  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x4332  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x4337  ldc.i4.0
0x4338  ldc.i4.0
0x4339  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x433e  stloc.1
0x433f  ldloc.1
0x4340  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x4345  leave.s  loc_436B
0x4347  stloc.2
0x4348  ldloc.2
0x4349  ldarg.1
0x434a  ldc.i4.s 0x18
0x434c  ldstr    aImportExceptio// "{Import}: Exception while trying to ope"...
0x4351  ldc.i4.2
0x4352  newarr   [mscorlib]System.Object
0x4357  dup
0x4358  ldc.i4.0
0x4359  ldloc.1
0x435a  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_ConnectionString()
0x435f  stelem.ref
0x4360  dup
0x4361  ldc.i4.1
0x4362  ldloc.2
0x4363  stelem.ref
0x4364  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4369  rethrow
0x436b  ldloc.1
0x436c  ldstr    aSelectContentF// "Select Content From ImportFileBase Wher"...
0x4371  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x4376  stloc.3
0x4377  ldloc.3
0x4378  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x437d  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x4382  ldstr    aImportfileid_0// "@importFileId"
0x4387  ldarga.s 2
0x4389  ldstr    aD_0// "D"
0x438e  call     instance string [mscorlib]System.Guid::ToString(string)
0x4393  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4398  pop
0x4399  ldnull
0x439a  stloc.s  4
0x439c  ldloc.3
0x439d  ldc.i4   0x16C
0x43a2  ldstr    aGetcontentfrom// "GetContentFromImportFile"
0x43a7  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\3"...
0x43ac  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x43b1  stloc.s  4
0x43b3  ldloc.s  4
0x43b5  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x43ba  brfalse.s loc_43CA
0x43bc  ldloc.s  4
0x43be  ldc.i4.0
0x43bf  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(int32)
0x43c4  callvirt instance string [mscorlib]System.Object::ToString()
0x43c9  stloc.0
0x43ca  leave.s  loc_4414
0x43cc  stloc.s  5
0x43ce  ldloc.s  5
0x43d0  ldarg.1
0x43d1  ldc.i4.s 0x18
0x43d3  ldstr    aImportExceptio_0// "{Import}: Exception while trying to exe"...
0x43d8  ldc.i4.2
0x43d9  newarr   [mscorlib]System.Object
0x43de  dup
0x43df  ldc.i4.0
0x43e0  ldloc.3
0x43e1  stelem.ref
0x43e2  dup
0x43e3  ldc.i4.1
0x43e4  ldloc.s  5
0x43e6  stelem.ref
0x43e7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x43ec  ldloc.3
0x43ed  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x43f2  rethrow
0x43f4  ldloc.s  4
0x43f6  brfalse.s loc_43FF
0x43f8  ldloc.s  4
0x43fa  callvirt instance void [System.Data]System.Data.IDataReader::Close()
0x43ff  endfinally
0x4400  ldloc.3
0x4401  brfalse.s loc_4409
0x4403  ldloc.3
0x4404  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4409  endfinally
0x440a  ldloc.1
0x440b  brfalse.s loc_4413
0x440d  ldloc.1
0x440e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4413  endfinally
0x4414  ldloc.0
0x4415  ret
```
