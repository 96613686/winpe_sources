# Microsoft.Crm.CrmLive.Provisioning.ConfigureReportServerExecutor::GetOrganizationsToBeConfigured

- ea: `0x217e0`
- end: `0x21886`
- name: `Microsoft.Crm.CrmLive.Provisioning.ConfigureReportServerExecutor::GetOrganizationsToBeConfigured`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x21550`

## callees

- `0x217e0`

## string_xrefs

- `0x2182b`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\TaskExecutor\ConfigureReportsExecutor.cs`
- `0x21802`: `select o.Id from Organization o join OrganizationProperties op on o.Id = op.Id where op.ColumnName='IsRemoteReportServerConfigured' and o.State=1 and o.AvailabilityGroup=@Name and op.BitColumn=0`
- `0x21826`: `GetOrganizationsToBeConfigured`

## pseudocode

```c

```

## disassembly

```asm
0x217e0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x217e5  stloc.0
0x217e6  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x217eb  stloc.1
0x217ec  ldloc.1
0x217ed  ldc.i4.2
0x217ee  callvirt instance class [System.Data]System.Data.IDbConnection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::NewConnection(valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigScope)
0x217f3  stloc.2
0x217f4  ldloc.2
0x217f5  callvirt instance void [System.Data]System.Data.IDbConnection::Open()
0x217fa  ldloc.2
0x217fb  callvirt instance class [System.Data]System.Data.IDbCommand [System.Data]System.Data.IDbConnection::CreateCommand()
0x21800  stloc.3
0x21801  ldloc.3
0x21802  ldstr    aSelectOIdFromO// "select o.Id from Organization o join Or"...
0x21807  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x2180c  ldloc.3
0x2180d  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x21812  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x21817  ldstr    aName_1// "@Name"
0x2181c  ldarg.0
0x2181d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x21822  pop
0x21823  ldloc.3
0x21824  ldc.i4.s 0x7D
0x21826  ldstr    aGetorganizatio_4// "GetOrganizationsToBeConfigured"
0x2182b  ldstr    aDDbsShDccm2110_32// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x21830  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x21835  stloc.s  4
0x21837  br.s     loc_21847
0x21839  ldloc.0
0x2183a  ldloc.s  4
0x2183c  ldc.i4.0
0x2183d  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.IDataRecord::GetGuid(int32)
0x21842  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x21847  ldloc.s  4
0x21849  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x2184e  brtrue.s loc_21839
0x21850  leave.s  loc_21868
0x21852  ldloc.s  4
0x21854  brfalse.s loc_2185D
0x21856  ldloc.s  4
0x21858  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2185d  endfinally
0x2185e  ldloc.3
0x2185f  brfalse.s loc_21867
0x21861  ldloc.3
0x21862  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x21867  endfinally
0x21868  ldloc.2
0x21869  callvirt instance void [System.Data]System.Data.IDbConnection::Close()
0x2186e  leave.s  loc_21884
0x21870  ldloc.2
0x21871  brfalse.s loc_21879
0x21873  ldloc.2
0x21874  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x21879  endfinally
0x2187a  ldloc.1
0x2187b  brfalse.s loc_21883
0x2187d  ldloc.1
0x2187e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x21883  endfinally
0x21884  ldloc.0
0x21885  ret
```
