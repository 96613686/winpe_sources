# Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::FromHoldtoInProgress

- ea: `0x13500`
- end: `0x135ac`
- name: `Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::FromHoldtoInProgress`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x13400`

## callees

- `0x13500`

## string_xrefs

- `0x13562`: `d:\dbs\sh\dccm2\1101_190851\cmd\5\src\Service\ObjectModel\Services\Plugins\SLAHelper.cs`

## pseudocode

```c

```

## disassembly

```asm
0x13500  ldarg.1
0x13501  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x13506  stloc.0
0x13507  ldnull
0x13508  stloc.1
0x13509  ldloc.0
0x1350a  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x1350f  stloc.1
0x13510  ldloc.1
0x13511  ldstr    aSelectTop1Stat// "select top 1 status from SLAKPIInstance"...
0x13516  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1351b  ldloc.1
0x1351c  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x13521  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x13526  dup
0x13527  ldstr    aEntityid_0// "@entityid"
0x1352c  ldarg.0
0x1352d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x13532  stloc.2
0x13533  ldloca.s 2
0x13535  constrained. [mscorlib]System.Guid
0x1353b  callvirt instance string [mscorlib]System.Object::ToString()
0x13540  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x13545  pop
0x13546  ldstr    aStatus_0// "@status"
0x1354b  ldc.i4.3
0x1354c  box      [mscorlib]System.Int32
0x13551  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x13556  pop
0x13557  ldloc.1
0x13558  ldc.i4   0x3D9
0x1355d  ldstr    aFromholdtoinpr// "FromHoldtoInProgress"
0x13562  ldstr    aDDbsShDccm2110_3// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\5"...
0x13567  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteScalar(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x1356c  brfalse.s loc_13572
0x1356e  ldc.i4.1
0x1356f  stloc.3
0x13570  leave.s  loc_135AA
0x13572  leave.s  loc_135A8
0x13574  stloc.s  4
0x13576  ldloc.s  4
0x13578  ldarg.1
0x13579  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1357e  ldc.i4.s 0x14
0x13580  ldstr    aErrorWhileRetr// "Error while retriving slakpistatus :  {"...
0x13585  ldc.i4.1
0x13586  newarr   [mscorlib]System.Object
0x1358b  dup
0x1358c  ldc.i4.0
0x1358d  ldloc.s  4
0x1358f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x13594  stelem.ref
0x13595  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1359a  rethrow
0x1359c  ldloc.1
0x1359d  brfalse.s loc_135A7
0x1359f  ldloc.1
0x135a0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x135a5  ldnull
0x135a6  stloc.1
0x135a7  endfinally
0x135a8  ldc.i4.0
0x135a9  ret
0x135aa  ldloc.3
0x135ab  ret
```
