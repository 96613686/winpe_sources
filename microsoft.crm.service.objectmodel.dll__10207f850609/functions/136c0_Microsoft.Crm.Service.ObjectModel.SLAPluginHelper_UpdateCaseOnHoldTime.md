# Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::UpdateCaseOnHoldTime

- ea: `0x136c0`
- end: `0x13779`
- name: `Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::UpdateCaseOnHoldTime`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x132b0`

## callees

- `0x136c0`

## string_xrefs

- `0x1373a`: `d:\dbs\sh\dccm2\1101_190851\cmd\5\src\Service\ObjectModel\Services\Plugins\SLAHelper.cs`
- `0x136d0`: `UPDATE IncidentBase SET OnHoldTime = @onholdtime`
- `0x13735`: `UpdateCaseOnHoldTime`

## pseudocode

```c

```

## disassembly

```asm
0x136c0  ldarg.0
0x136c1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x136c6  stloc.0
0x136c7  ldnull
0x136c8  stloc.1
0x136c9  ldloc.0
0x136ca  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x136cf  stloc.1
0x136d0  ldstr    aUpdateIncident_3// "UPDATE IncidentBase SET OnHoldTime = @o"...
0x136d5  stloc.2
0x136d6  ldloc.2
0x136d7  ldc.i4.1
0x136d8  newarr   [mscorlib]System.Char
0x136dd  dup
0x136de  ldc.i4.0
0x136df  ldc.i4.s 0x2C
0x136e1  stelem.i2
0x136e2  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x136e7  ldstr    aWhereIncidenti// " WHERE IncidentId=@incidentid"
0x136ec  call     string [mscorlib]System.String::Concat(string, string)
0x136f1  stloc.2
0x136f2  ldloc.1
0x136f3  ldloc.2
0x136f4  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x136f9  ldloc.1
0x136fa  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x136ff  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x13704  dup
0x13705  ldstr    aIncidentid_0// "@incidentid"
0x1370a  ldarga.s 1
0x1370c  constrained. [mscorlib]System.Guid
0x13712  callvirt instance string [mscorlib]System.Object::ToString()
0x13717  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1371c  pop
0x1371d  ldstr    aOnholdtime_0// "@onholdtime"
0x13722  ldarg.2
0x13723  conv.i4
0x13724  box      [mscorlib]System.Int32
0x13729  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1372e  pop
0x1372f  ldloc.1
0x13730  ldc.i4   0x44C
0x13735  ldstr    aUpdatecaseonho// "UpdateCaseOnHoldTime"
0x1373a  ldstr    aDDbsShDccm2110_3// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\5"...
0x1373f  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x13744  pop
0x13745  leave.s  loc_13778
0x13747  stloc.3
0x13748  ldloc.3
0x13749  ldarg.0
0x1374a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1374f  ldc.i4.s 0x14
0x13751  ldstr    aErrorWhileUpda_0// "Error while updating INCIDENT on hold t"...
0x13756  ldc.i4.1
0x13757  newarr   [mscorlib]System.Object
0x1375c  dup
0x1375d  ldc.i4.0
0x1375e  ldloc.3
0x1375f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x13764  stelem.ref
0x13765  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1376a  rethrow
0x1376c  ldloc.1
0x1376d  brfalse.s loc_13777
0x1376f  ldloc.1
0x13770  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13775  ldnull
0x13776  stloc.1
0x13777  endfinally
0x13778  ret
```
