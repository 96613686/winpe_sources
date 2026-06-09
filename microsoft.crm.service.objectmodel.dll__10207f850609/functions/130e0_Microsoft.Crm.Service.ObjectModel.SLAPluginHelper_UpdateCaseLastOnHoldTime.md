# Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::UpdateCaseLastOnHoldTime

- ea: `0x130e0`
- end: `0x1319c`
- name: `Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::UpdateCaseLastOnHoldTime`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x135b0`

## callees

- `0x130e0`

## string_xrefs

- `0x1315d`: `d:\dbs\sh\dccm2\1101_190851\cmd\5\src\Service\ObjectModel\Services\Plugins\SLAHelper.cs`
- `0x130f0`: `UPDATE IncidentBase SET LastOnHoldTime = @lastonholdtime`
- `0x13158`: `UpdateCaseLastOnHoldTime`

## pseudocode

```c

```

## disassembly

```asm
0x130e0  ldarg.0
0x130e1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x130e6  stloc.0
0x130e7  ldnull
0x130e8  stloc.1
0x130e9  ldloc.0
0x130ea  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x130ef  stloc.1
0x130f0  ldstr    aUpdateIncident_2// "UPDATE IncidentBase SET LastOnHoldTime "...
0x130f5  stloc.2
0x130f6  ldloc.2
0x130f7  ldc.i4.1
0x130f8  newarr   [mscorlib]System.Char
0x130fd  dup
0x130fe  ldc.i4.0
0x130ff  ldc.i4.s 0x2C
0x13101  stelem.i2
0x13102  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x13107  ldstr    aWhereIncidenti// " WHERE IncidentId=@incidentid"
0x1310c  call     string [mscorlib]System.String::Concat(string, string)
0x13111  stloc.2
0x13112  ldloc.1
0x13113  ldloc.2
0x13114  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x13119  ldloc.1
0x1311a  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1311f  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x13124  dup
0x13125  ldstr    aIncidentid_0// "@incidentid"
0x1312a  ldarga.s 1
0x1312c  constrained. [mscorlib]System.Guid
0x13132  callvirt instance string [mscorlib]System.Object::ToString()
0x13137  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1313c  pop
0x1313d  ldstr    aLastonholdtime_0// "@lastonholdtime"
0x13142  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x13147  box      [mscorlib]System.DateTime
0x1314c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x13151  pop
0x13152  ldloc.1
0x13153  ldc.i4   0x2FD
0x13158  ldstr    aUpdatecaselast// "UpdateCaseLastOnHoldTime"
0x1315d  ldstr    aDDbsShDccm2110_3// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\5"...
0x13162  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x13167  pop
0x13168  leave.s  loc_1319B
0x1316a  stloc.3
0x1316b  ldloc.3
0x1316c  ldarg.0
0x1316d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x13172  ldc.i4.s 0x14
0x13174  ldstr    aErrorWhileUpda// "Error while updating INCIDENT last on h"...
0x13179  ldc.i4.1
0x1317a  newarr   [mscorlib]System.Object
0x1317f  dup
0x13180  ldc.i4.0
0x13181  ldloc.3
0x13182  callvirt instance string [mscorlib]System.Exception::get_Message()
0x13187  stelem.ref
0x13188  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1318d  rethrow
0x1318f  ldloc.1
0x13190  brfalse.s loc_1319A
0x13192  ldloc.1
0x13193  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13198  ldnull
0x13199  stloc.1
0x1319a  endfinally
0x1319b  ret
```
