# Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::UpdateSlaKpiInstanceStatus

- ea: `0x13780`
- end: `0x13838`
- name: `Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::UpdateSlaKpiInstanceStatus`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x12850`

## callees

- `0x13780`

## string_xrefs

- `0x137f9`: `d:\dbs\sh\dccm2\1101_190851\cmd\5\src\Service\ObjectModel\Services\Plugins\SLAHelper.cs`
- `0x13790`: `UPDATE SLAKPIInstanceBase SET Status = @canceledstatus`
- `0x137f4`: `UpdateSlaKpiInstanceStatus`

## pseudocode

```c

```

## disassembly

```asm
0x13780  ldarg.0
0x13781  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x13786  stloc.0
0x13787  ldnull
0x13788  stloc.1
0x13789  ldloc.0
0x1378a  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x1378f  stloc.1
0x13790  ldstr    aUpdateSlakpiin// "UPDATE SLAKPIInstanceBase SET Status = "...
0x13795  stloc.2
0x13796  ldloc.2
0x13797  ldc.i4.1
0x13798  newarr   [mscorlib]System.Char
0x1379d  dup
0x1379e  ldc.i4.0
0x1379f  ldc.i4.s 0x2C
0x137a1  stelem.i2
0x137a2  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x137a7  ldstr    aWhereRegarding// " WHERE Regarding=@incidentid "
0x137ac  call     string [mscorlib]System.String::Concat(string, string)
0x137b1  stloc.2
0x137b2  ldloc.1
0x137b3  ldloc.2
0x137b4  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x137b9  ldloc.1
0x137ba  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x137bf  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x137c4  dup
0x137c5  ldstr    aIncidentid_0// "@incidentid"
0x137ca  ldarga.s 1
0x137cc  constrained. [mscorlib]System.Guid
0x137d2  callvirt instance string [mscorlib]System.Object::ToString()
0x137d7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x137dc  pop
0x137dd  ldstr    aCanceledstatus// "@canceledstatus"
0x137e2  ldc.i4.5
0x137e3  box      [mscorlib]System.Int32
0x137e8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x137ed  pop
0x137ee  ldloc.1
0x137ef  ldc.i4   0x471
0x137f4  ldstr    aUpdateslakpiin// "UpdateSlaKpiInstanceStatus"
0x137f9  ldstr    aDDbsShDccm2110_3// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\5"...
0x137fe  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x13803  pop
0x13804  leave.s  loc_13837
0x13806  stloc.3
0x13807  ldloc.3
0x13808  ldarg.0
0x13809  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1380e  ldc.i4.s 0x14
0x13810  ldstr    aErrorWhileUpda_1// "Error while updating SlaKpiInstance Sta"...
0x13815  ldc.i4.1
0x13816  newarr   [mscorlib]System.Object
0x1381b  dup
0x1381c  ldc.i4.0
0x1381d  ldloc.3
0x1381e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x13823  stelem.ref
0x13824  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x13829  rethrow
0x1382b  ldloc.1
0x1382c  brfalse.s loc_13836
0x1382e  ldloc.1
0x1382f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13834  ldnull
0x13835  stloc.1
0x13836  endfinally
0x13837  ret
```
