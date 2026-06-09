# Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::ClearManualSLA

- ea: `0x13030`
- end: `0x130d6`
- name: `Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::ClearManualSLA`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x12ca0`

## callees

- `0x13030`

## string_xrefs

- `0x13097`: `d:\dbs\sh\dccm2\1101_190851\cmd\5\src\Service\ObjectModel\Services\Plugins\SLAHelper.cs`
- `0x13040`: `UPDATE IncidentBase SET SLAId = null`

## pseudocode

```c

```

## disassembly

```asm
0x13030  ldarg.0
0x13031  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x13036  stloc.0
0x13037  ldnull
0x13038  stloc.1
0x13039  ldloc.0
0x1303a  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x1303f  stloc.1
0x13040  ldstr    aUpdateIncident_1// "UPDATE IncidentBase SET SLAId = null"
0x13045  stloc.2
0x13046  ldloc.2
0x13047  ldc.i4.1
0x13048  newarr   [mscorlib]System.Char
0x1304d  dup
0x1304e  ldc.i4.0
0x1304f  ldc.i4.s 0x2C
0x13051  stelem.i2
0x13052  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x13057  ldstr    aWhereIncidenti// " WHERE IncidentId=@incidentid"
0x1305c  call     string [mscorlib]System.String::Concat(string, string)
0x13061  stloc.2
0x13062  ldloc.1
0x13063  ldloc.2
0x13064  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x13069  ldloc.1
0x1306a  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1306f  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x13074  ldstr    aIncidentid_0// "@incidentid"
0x13079  ldarga.s 1
0x1307b  constrained. [mscorlib]System.Guid
0x13081  callvirt instance string [mscorlib]System.Object::ToString()
0x13086  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1308b  pop
0x1308c  ldloc.1
0x1308d  ldc.i4   0x2D7
0x13092  ldstr    aClearmanualsla// "ClearManualSLA"
0x13097  ldstr    aDDbsShDccm2110_3// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\5"...
0x1309c  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x130a1  pop
0x130a2  leave.s  loc_130D5
0x130a4  stloc.3
0x130a5  ldloc.3
0x130a6  ldarg.0
0x130a7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x130ac  ldc.i4.s 0x14
0x130ae  ldstr    aErrorWhileUpda// "Error while updating INCIDENT last on h"...
0x130b3  ldc.i4.1
0x130b4  newarr   [mscorlib]System.Object
0x130b9  dup
0x130ba  ldc.i4.0
0x130bb  ldloc.3
0x130bc  callvirt instance string [mscorlib]System.Exception::get_Message()
0x130c1  stelem.ref
0x130c2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x130c7  rethrow
0x130c9  ldloc.1
0x130ca  brfalse.s loc_130D4
0x130cc  ldloc.1
0x130cd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x130d2  ldnull
0x130d3  stloc.1
0x130d4  endfinally
0x130d5  ret
```
