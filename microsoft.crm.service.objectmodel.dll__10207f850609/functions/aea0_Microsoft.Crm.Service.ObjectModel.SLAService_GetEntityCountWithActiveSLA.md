# Microsoft.Crm.Service.ObjectModel.SLAService::GetEntityCountWithActiveSLA

- ea: `0xaea0`
- end: `0xaf43`
- name: `Microsoft.Crm.Service.ObjectModel.SLAService::GetEntityCountWithActiveSLA`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xac70`

## callees

- `0xaea0`

## string_xrefs

- `0xaf08`: `d:\dbs\sh\dccm2\1101_190851\cmd\5\src\Service\ObjectModel\Services\CS\SLAService.cs`

## pseudocode

```c

```

## disassembly

```asm
0xaea0  ldstr    aSelectCountDis_0// "SELECT count(DISTINCT [ObjectTypeCode])"...
0xaea5  stloc.0
0xaea6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryParameterManager::.ctor()
0xaeab  stloc.1
0xaeac  ldstr    aStatuscode_0// "StatusCode"
0xaeb1  stloc.2
0xaeb2  ldloc.1
0xaeb3  ldloc.2
0xaeb4  ldc.i4.2
0xaeb5  box      [mscorlib]System.Int32
0xaeba  ldc.i4.8
0xaebb  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ParameterValueAndType::.ctor(object, valuetype [System.Data]System.Data.SqlDbType)
0xaec0  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryParameterManager::AddParameterWithName(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ParameterValueAndType)
0xaec5  stloc.3
0xaec6  ldarg.0
0xaec7  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CreateCommand()
0xaecc  stloc.s  4
0xaece  ldloc.1
0xaecf  ldloc.s  4
0xaed1  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xaed6  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xaedb  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryParameterManager::AddParametersToSqlParameterCollection(class [System.Data]System.Data.SqlClient.SqlParameterCollection)
0xaee0  ldloc.s  4
0xaee2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xaee7  ldloc.0
0xaee8  ldc.i4.1
0xaee9  newarr   [mscorlib]System.Object
0xaeee  dup
0xaeef  ldc.i4.0
0xaef0  ldloc.3
0xaef1  stelem.ref
0xaef2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xaef7  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xaefc  ldloc.s  4
0xaefe  ldc.i4   0x325
0xaf03  ldstr    aGetentitycount// "GetEntityCountWithActiveSLA"
0xaf08  ldstr    aDDbsShDccm2110_1// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\5"...
0xaf0d  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteScalar(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xaf12  unbox.any [mscorlib]System.Int32
0xaf17  stloc.s  5
0xaf19  leave.s  loc_AF40
0xaf1b  stloc.s  6
0xaf1d  ldstr    aFailedToRetrie_0// "Failed to retrieve Entity Count with Ac"...
0xaf22  ldloc.s  6
0xaf24  callvirt instance string [mscorlib]System.Exception::get_Message()
0xaf29  call     string [mscorlib]System.String::Concat(string, string)
0xaf2e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xaf33  throw
0xaf34  ldloc.s  4
0xaf36  brfalse.s loc_AF3F
0xaf38  ldloc.s  4
0xaf3a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xaf3f  endfinally
0xaf40  ldloc.s  5
0xaf42  ret
```
