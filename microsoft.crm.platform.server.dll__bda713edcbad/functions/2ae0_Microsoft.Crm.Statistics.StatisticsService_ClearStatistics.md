# Microsoft.Crm.Statistics.StatisticsService::ClearStatistics

- ea: `0x2ae0`
- end: `0x2be5`
- name: `Microsoft.Crm.Statistics.StatisticsService::ClearStatistics`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x25b0`

## callees

- `0x2ae0`
- `0x66530`
- `0x66ae0`
- `0x66b00`
- `0x67140`
- `0x67450`
- `0x674c0`

## string_xrefs

- `0x2b82`: `D:\a\1\s\src\ManagedPlatform\Server\Statistics\StatisticsService.cs`
- `0x2af6`: `delete from OrganizationStatisticBase \n												where (ServerName = @ServerName and Hour != @ThisHour and Hour != @LastHour)`
- `0x2b91`: `OrganizationStatistic removed (count={0}) rows for server({1})`

## pseudocode

```c

```

## disassembly

```asm
0x2ae0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0x2ae5  stloc.0
0x2ae6  ldarg.2
0x2ae7  ldc.i4.0
0x2ae8  ldc.i4.0
0x2ae9  newobj   instance void Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid organizationId, [opt] bool isReader, [opt] valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority priority)
0x2aee  stloc.1
0x2aef  ldloc.1
0x2af0  ldc.i4.1
0x2af1  callvirt instance void Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(bool startTransaction)
0x2af6  ldstr    aDeleteFromOrga// "delete from OrganizationStatisticBase "...
0x2afb  stloc.2
0x2afc  ldloc.1
0x2afd  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x2b02  ldloc.2
0x2b03  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x2b08  stloc.3
0x2b09  ldloc.3
0x2b0a  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x2b0f  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x2b14  dup
0x2b15  ldstr    aServername_0// "@ServerName"
0x2b1a  call     string [mscorlib]System.Environment::get_MachineName()
0x2b1f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2b24  pop
0x2b25  dup
0x2b26  ldstr    aThishour// "@ThisHour"
0x2b2b  ldarga.s 1
0x2b2d  call     instance int32 [mscorlib]System.DateTime::get_Hour()
0x2b32  box      [mscorlib]System.Int32
0x2b37  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2b3c  pop
0x2b3d  ldstr    aLasthour// "@LastHour"
0x2b42  ldarga.s 1
0x2b44  ldc.r8   -1.0
0x2b4d  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddHours(float64)
0x2b52  stloc.s  5
0x2b54  ldloca.s 5
0x2b56  call     instance int32 [mscorlib]System.DateTime::get_Hour()
0x2b5b  box      [mscorlib]System.Int32
0x2b60  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2b65  pop
0x2b66  ldloc.3
0x2b67  ldloc.1
0x2b68  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x2b6d  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_SqlTransaction()
0x2b72  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::SetTransaction(class [System.Data]System.Data.IDbCommand, class [System.Data]System.Data.IDbTransaction)
0x2b77  ldloc.3
0x2b78  ldc.i4   0x162
0x2b7d  ldstr    aClearstatistic// "ClearStatistics"
0x2b82  ldstr    aDA1SSrcManaged// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x2b87  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x2b8c  stloc.s  4
0x2b8e  ldarg.2
0x2b8f  ldc.i4.s 0x14
0x2b91  ldstr    aOrganizationst_4// "OrganizationStatistic removed (count={0"...
0x2b96  ldc.i4.2
0x2b97  newarr   [mscorlib]System.Object
0x2b9c  dup
0x2b9d  ldc.i4.0
0x2b9e  ldloc.s  4
0x2ba0  box      [mscorlib]System.Int32
0x2ba5  stelem.ref
0x2ba6  dup
0x2ba7  ldc.i4.1
0x2ba8  call     string [mscorlib]System.Environment::get_MachineName()
0x2bad  stelem.ref
0x2bae  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2bb3  leave.s  loc_2BBF
0x2bb5  ldloc.3
0x2bb6  brfalse.s loc_2BBE
0x2bb8  ldloc.3
0x2bb9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2bbe  endfinally
0x2bbf  ldloc.1
0x2bc0  callvirt instance void Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x2bc5  leave.s  loc_2BE4
0x2bc7  pop
0x2bc8  ldloc.1
0x2bc9  callvirt instance void Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0x2bce  rethrow
0x2bd0  ldloc.1
0x2bd1  brfalse.s loc_2BD9
0x2bd3  ldloc.1
0x2bd4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2bd9  endfinally
0x2bda  ldloc.0
0x2bdb  brfalse.s loc_2BE3
0x2bdd  ldloc.0
0x2bde  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2be3  endfinally
0x2be4  ret
```
