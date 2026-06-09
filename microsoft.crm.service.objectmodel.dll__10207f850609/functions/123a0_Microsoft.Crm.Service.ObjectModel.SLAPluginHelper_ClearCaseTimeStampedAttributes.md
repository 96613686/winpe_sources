# Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::ClearCaseTimeStampedAttributes

- ea: `0x123a0`
- end: `0x12518`
- name: `Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::ClearCaseTimeStampedAttributes`
- size: `376`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x12850`

## callees

- `0x123a0`

## string_xrefs

- `0x123d9`: `d:\dbs\sh\dccm2\1101_190851\cmd\5\src\Service\ObjectModel\Services\Plugins\SLAHelper.cs`
- `0x124d3`: `d:\dbs\sh\dccm2\1101_190851\cmd\5\src\Service\ObjectModel\Services\Plugins\SLAHelper.cs`
- `0x12422`: `UPDATE IncidentBase SET `

## pseudocode

```c

```

## disassembly

```asm
0x123a0  ldarg.0
0x123a1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x123a6  stloc.0
0x123a7  ldnull
0x123a8  stloc.1
0x123a9  ldc.i4.1
0x123aa  stloc.2
0x123ab  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x123b0  stloc.3
0x123b1  ldloc.0
0x123b2  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x123b7  stloc.1
0x123b8  ldloc.1
0x123b9  ldstr    aSelectRelatedf// "SELECT RelatedField from SLAItem INNER "...
0x123be  ldarg.2
0x123bf  ldstr    asc_23472// ")"
0x123c4  call     string [mscorlib]System.String::Concat(string, string, string)
0x123c9  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x123ce  ldloc.1
0x123cf  ldc.i4   0xC2
0x123d4  ldstr    aClearcasetimes// "ClearCaseTimeStampedAttributes"
0x123d9  ldstr    aDDbsShDccm2110_3// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\5"...
0x123de  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x123e3  stloc.s  4
0x123e5  br.s     loc_12400
0x123e7  ldloc.3
0x123e8  ldloc.s  4
0x123ea  ldloc.s  4
0x123ec  ldstr    aRelatedfield_0// "RelatedField"
0x123f1  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetOrdinal(string)
0x123f6  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x123fb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12400  ldloc.s  4
0x12402  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x12407  brtrue.s loc_123E7
0x12409  leave.s  loc_12417
0x1240b  ldloc.s  4
0x1240d  brfalse.s loc_12416
0x1240f  ldloc.s  4
0x12411  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12416  endfinally
0x12417  ldloc.3
0x12418  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x1241d  brfalse  loc_124E0
0x12422  ldstr    aUpdateIncident// "UPDATE IncidentBase SET "
0x12427  stloc.s  5
0x12429  ldloc.3
0x1242a  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x1242f  stloc.s  6
0x12431  br.s     loc_12455
0x12433  ldloca.s 6
0x12435  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x1243a  stloc.s  7
0x1243c  ldloc.s  7
0x1243e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12443  brtrue.s loc_12455
0x12445  ldloc.s  5
0x12447  ldloc.s  7
0x12449  ldstr    aNullvalue// "= @nullvalue,"
0x1244e  call     string [mscorlib]System.String::Concat(string, string, string)
0x12453  stloc.s  5
0x12455  ldloca.s 6
0x12457  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x1245c  brtrue.s loc_12433
0x1245e  leave.s  loc_1246E
0x12460  ldloca.s 6
0x12462  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x12468  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1246d  endfinally
0x1246e  ldloc.s  5
0x12470  ldc.i4.1
0x12471  newarr   [mscorlib]System.Char
0x12476  dup
0x12477  ldc.i4.0
0x12478  ldc.i4.s 0x2C
0x1247a  stelem.i2
0x1247b  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x12480  ldstr    aWhereIncidenti// " WHERE IncidentId=@incidentid"
0x12485  call     string [mscorlib]System.String::Concat(string, string)
0x1248a  stloc.s  5
0x1248c  ldloc.1
0x1248d  ldloc.s  5
0x1248f  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x12494  ldloc.1
0x12495  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1249a  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1249f  dup
0x124a0  ldstr    aNullvalue_0// "@nullvalue"
0x124a5  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x124aa  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x124af  pop
0x124b0  ldstr    aIncidentid_0// "@incidentid"
0x124b5  ldarga.s 1
0x124b7  constrained. [mscorlib]System.Guid
0x124bd  callvirt instance string [mscorlib]System.Object::ToString()
0x124c2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x124c7  pop
0x124c8  ldloc.1
0x124c9  ldc.i4   0xDB
0x124ce  ldstr    aClearcasetimes// "ClearCaseTimeStampedAttributes"
0x124d3  ldstr    aDDbsShDccm2110_3// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\5"...
0x124d8  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x124dd  pop
0x124de  ldc.i4.0
0x124df  stloc.2
0x124e0  leave.s  loc_12516
0x124e2  stloc.s  8
0x124e4  ldloc.s  8
0x124e6  ldarg.0
0x124e7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x124ec  ldc.i4.s 0x14
0x124ee  ldstr    aErrorWhileClea// "Error while clearing SLA time stamped a"...
0x124f3  ldc.i4.1
0x124f4  newarr   [mscorlib]System.Object
0x124f9  dup
0x124fa  ldc.i4.0
0x124fb  ldloc.s  8
0x124fd  callvirt instance string [mscorlib]System.Exception::get_Message()
0x12502  stelem.ref
0x12503  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x12508  rethrow
0x1250a  ldloc.1
0x1250b  brfalse.s loc_12515
0x1250d  ldloc.1
0x1250e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12513  ldnull
0x12514  stloc.1
0x12515  endfinally
0x12516  ldloc.2
0x12517  ret
```
