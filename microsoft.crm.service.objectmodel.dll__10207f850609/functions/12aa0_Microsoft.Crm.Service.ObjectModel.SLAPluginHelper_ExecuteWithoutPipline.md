# Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::ExecuteWithoutPipline

- ea: `0x12aa0`
- end: `0x12b2e`
- name: `Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::ExecuteWithoutPipline`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x12990`

## callees

- `0x12aa0`

## string_xrefs

- `0x12aef`: `d:\dbs\sh\dccm2\1101_190851\cmd\5\src\Service\ObjectModel\Services\Plugins\SLAHelper.cs`
- `0x12ab6`: `UPDATE IncidentBase SET SlaInvokedId=@slainvokedid WHERE IncidentId=@incidentid`
- `0x12b06`: `Error in Sla Invoked ID update:  {0}`

## pseudocode

```c

```

## disassembly

```asm
0x12aa0  ldarg.0
0x12aa1  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x12aa6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x12aab  stloc.0
0x12aac  ldnull
0x12aad  stloc.1
0x12aae  ldloc.0
0x12aaf  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x12ab4  stloc.1
0x12ab5  ldloc.1
0x12ab6  ldstr    aUpdateIncident_0// "UPDATE IncidentBase SET SlaInvokedId=@s"...
0x12abb  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x12ac0  ldloc.1
0x12ac1  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x12ac6  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x12acb  dup
0x12acc  ldstr    aSlainvokedid_0// "@slainvokedid"
0x12ad1  ldarg.1
0x12ad2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x12ad7  pop
0x12ad8  ldstr    aIncidentid_0// "@incidentid"
0x12add  ldarg.2
0x12ade  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x12ae3  pop
0x12ae4  ldloc.1
0x12ae5  ldc.i4   0x1BC
0x12aea  ldstr    aExecutewithout// "ExecuteWithoutPipline"
0x12aef  ldstr    aDDbsShDccm2110_3// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\5"...
0x12af4  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x12af9  pop
0x12afa  leave.s  loc_12B2D
0x12afc  stloc.2
0x12afd  ldloc.2
0x12afe  ldarg.0
0x12aff  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_OrganizationId()
0x12b04  ldc.i4.s 0x14
0x12b06  ldstr    aErrorInSlaInvo// "Error in Sla Invoked ID update:  {0}"
0x12b0b  ldc.i4.1
0x12b0c  newarr   [mscorlib]System.Object
0x12b11  dup
0x12b12  ldc.i4.0
0x12b13  ldloc.2
0x12b14  callvirt instance string [mscorlib]System.Exception::get_Message()
0x12b19  stelem.ref
0x12b1a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x12b1f  rethrow
0x12b21  ldloc.1
0x12b22  brfalse.s loc_12B2C
0x12b24  ldloc.1
0x12b25  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12b2a  ldnull
0x12b2b  stloc.1
0x12b2c  endfinally
0x12b2d  ret
```
