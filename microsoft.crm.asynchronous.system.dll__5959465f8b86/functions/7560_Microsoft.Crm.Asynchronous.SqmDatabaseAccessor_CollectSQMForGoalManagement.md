# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectSQMForGoalManagement

- ea: `0x7560`
- end: `0x76e0`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectSQMForGoalManagement`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x5290`

## callees

- `0x7560`

## pseudocode

```c

```

## disassembly

```asm
0x7560  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x7565  stloc.0
0x7566  ldloc.0
0x7567  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x756c  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x7571  dup
0x7572  ldstr    aNoofproductuni// "@NoofProductUnits"
0x7577  ldstr    aAe39f33041c145// "AE39F330-41C1-4543-AAB1-05002B02C09B"
0x757c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7581  pop
0x7582  dup
0x7583  ldstr    aRevenue// "@Revenue"
0x7588  ldstr    a9241f883Ceb146// "9241F883-CEB1-4600-9C32-7CB1D9ECF6A3"
0x758d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7592  pop
0x7593  ldstr    aNoofcases// "@NoofCases"
0x7598  ldstr    a8f11e745986047// "8F11E745-9860-475A-A613-D360D1F3AF87"
0x759d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x75a2  pop
0x75a3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x75a8  ldstr    aSelectSelectCo// "SELECT (SELECT COUNT(MetricId)FROM Metr"...
0x75ad  ldc.i4.0
0x75ae  newarr   [mscorlib]System.Object
0x75b3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x75b8  stloc.1
0x75b9  ldloc.0
0x75ba  ldloc.1
0x75bb  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x75c0  ldarg.0
0x75c1  ldloc.0
0x75c2  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand)
0x75c7  unbox.any [mscorlib]System.Int32
0x75cc  stloc.2
0x75cd  ldarg.1
0x75ce  ldc.i4   0x1F5
0x75d3  ldloc.2
0x75d4  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x75d9  ldloc.0
0x75da  ldstr    aSelectCountGoa// "SELECT COUNT(GoalRollupQueryId) FROM Go"...
0x75df  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x75e4  ldarg.0
0x75e5  ldloc.0
0x75e6  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand)
0x75eb  unbox.any [mscorlib]System.Int32
0x75f0  stloc.3
0x75f1  ldloc.0
0x75f2  ldstr    aSelectCountSys// "SELECT COUNT(SystemUserId) FROM SystemU"...
0x75f7  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x75fc  ldarg.0
0x75fd  ldloc.0
0x75fe  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand)
0x7603  unbox.any [mscorlib]System.Int32
0x7608  stloc.s  4
0x760a  ldarg.1
0x760b  ldc.i4   0x1F6
0x7610  ldloc.3
0x7611  ldloc.s  4
0x7613  div
0x7614  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x7619  ldloc.0
0x761a  ldstr    aSelectCountGoa_0// "SELECT COUNT(GoalId) FROM Goal"
0x761f  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x7624  ldarg.0
0x7625  ldloc.0
0x7626  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand)
0x762b  unbox.any [mscorlib]System.Int32
0x7630  stloc.s  5
0x7632  ldloc.0
0x7633  ldstr    aSelectCountDis_3// "SELECT COUNT(DISTINCT TreeId) FROM Goal"
0x7638  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x763d  ldarg.0
0x763e  ldloc.0
0x763f  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand)
0x7644  unbox.any [mscorlib]System.Int32
0x7649  stloc.s  6
0x764b  ldarg.1
0x764c  ldc.i4   0x1F7
0x7651  ldloc.s  5
0x7653  ldloc.s  6
0x7655  div
0x7656  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x765b  ldstr    aFetchDistinctF// "<fetch distinct='false' mapping='logica"...
0x7660  stloc.s  7
0x7662  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ExecuteFetchRequest::.ctor()
0x7667  stloc.s  8
0x7669  ldarg.0
0x766a  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x766f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x7674  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7679  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.SdkServiceFactory::CreateInstance(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x767e  ldloc.s  8
0x7680  ldloc.s  7
0x7682  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ExecuteFetchRequest::set_FetchXml(string)
0x7687  ldloc.s  8
0x7689  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x768e  castclass [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ExecuteFetchResponse
0x7693  callvirt instance string [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ExecuteFetchResponse::get_FetchXmlResult()
0x7698  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x769d  ldstr    aResultsetResul_2// "resultset/result/goalcount"
0x76a2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x76a7  stloc.s  9
0x76a9  ldc.i4.0
0x76aa  stloc.s  0xA
0x76ac  ldloc.s  9
0x76ae  brfalse.s loc_76C3
0x76b0  ldloc.s  9
0x76b2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x76b7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x76bc  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x76c1  stloc.s  0xA
0x76c3  ldarg.1
0x76c4  ldc.i4   0x1F8
0x76c9  ldloc.s  0xA
0x76cb  ldloc.s  4
0x76cd  div
0x76ce  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x76d3  leave.s  loc_76DF
0x76d5  ldloc.0
0x76d6  brfalse.s loc_76DE
0x76d8  ldloc.0
0x76d9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x76de  endfinally
0x76df  ret
```
