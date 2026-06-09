# Microsoft.Crm.CrmLive.Provisioning.SandboxInstanceCopyMassageDataExecutor::RemoveExternalSearchFeatureSetXML

- ea: `0x27310`
- end: `0x2745d`
- name: `Microsoft.Crm.CrmLive.Provisioning.SandboxInstanceCopyMassageDataExecutor::RemoveExternalSearchFeatureSetXML`
- size: `333`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x26eb0`

## callees

- `0x27310`

## string_xrefs

- `0x27339`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\TaskExecutor\SandboxInstanceCopyMassageDataExecutor.cs`
- `0x27334`: `RemoveExternalSearchFeatureSetXML`
- `0x27429`: `featureSetXML`
- `0x2743c`: `update OrganizationBase set FeatureSet = @featureSetXML`

## pseudocode

```c

```

## disassembly

```asm
0x27310  ldsfld   string [mscorlib]System.String::Empty
0x27315  stloc.0
0x27316  ldarg.0
0x27317  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x2731c  ldc.i4.1
0x2731d  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand(bool)
0x27322  stloc.3
0x27323  ldloc.3
0x27324  ldstr    aSelectFeatures// "select FeatureSet from OrganizationBase"
0x27329  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x2732e  ldloc.3
0x2732f  ldc.i4   0x1F0
0x27334  ldstr    aRemoveexternal// "RemoveExternalSearchFeatureSetXML"
0x27339  ldstr    aDDbsShDccm2110_41// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x2733e  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x27343  stloc.s  4
0x27345  br.s     loc_2735A
0x27347  ldloc.s  4
0x27349  ldc.i4.0
0x2734a  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x2734f  brtrue.s loc_2735A
0x27351  ldloc.s  4
0x27353  ldc.i4.0
0x27354  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x27359  stloc.0
0x2735a  ldloc.s  4
0x2735c  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x27361  brtrue.s loc_27347
0x27363  leave.s  loc_2737B
0x27365  ldloc.s  4
0x27367  brfalse.s loc_27370
0x27369  ldloc.s  4
0x2736b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x27370  endfinally
0x27371  ldloc.3
0x27372  brfalse.s loc_2737A
0x27374  ldloc.3
0x27375  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2737a  endfinally
0x2737b  ldloc.0
0x2737c  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x27381  brfalse.s loc_27384
0x27383  ret
0x27384  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x27389  stloc.1
0x2738a  ldloc.1
0x2738b  ldnull
0x2738c  callvirt instance void [System.Xml]System.Xml.XmlDocument::set_XmlResolver(class [System.Xml]System.Xml.XmlResolver)
0x27391  ldloc.1
0x27392  ldloc.0
0x27393  callvirt instance void [System.Xml]System.Xml.XmlDocument::LoadXml(string)
0x27398  ldloc.1
0x27399  ldstr    aFeaturesFeatur// "/features/feature"
0x2739e  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x273a3  stloc.2
0x273a4  ldloc.2
0x273a5  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x273aa  brtrue.s loc_273AD
0x273ac  ret
0x273ad  ldloc.2
0x273ae  call     T0x2B0000B3
0x273b3  ldsfld   class [mscorlib]System.Func`2<class [System.Xml]System.Xml.XmlNode, bool> <>c::<>9__20_0
0x273b8  dup
0x273b9  brtrue.s loc_273D2
0x273bb  pop
0x273bc  ldsfld   class <>c <>c::<>9
0x273c1  ldftn    instance bool <>c::<RemoveExternalSearchFeatureSetXML>b__20_0(class [System.Xml]System.Xml.XmlNode xmlNode)
0x273c7  newobj   instance void class [mscorlib]System.Func`2<class [System.Xml]System.Xml.XmlNode, bool>::.ctor(object, native int)
0x273cc  dup
0x273cd  stsfld   class [mscorlib]System.Func`2<class [System.Xml]System.Xml.XmlNode, bool> <>c::<>9__20_0
0x273d2  call     T0x2B0000B4
0x273d7  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml]System.Xml.XmlNode>::GetEnumerator()
0x273dc  stloc.s  5
0x273de  br.s     loc_273F8
0x273e0  ldloc.s  5
0x273e2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml]System.Xml.XmlNode>::get_Current()
0x273e7  stloc.s  6
0x273e9  ldloc.s  6
0x273eb  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x273f0  ldloc.s  6
0x273f2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x273f7  pop
0x273f8  ldloc.s  5
0x273fa  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x273ff  brtrue.s loc_273E0
0x27401  leave.s  loc_2740F
0x27403  ldloc.s  5
0x27405  brfalse.s loc_2740E
0x27407  ldloc.s  5
0x27409  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2740e  endfinally
0x2740f  ldarg.0
0x27410  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x27415  ldc.i4.1
0x27416  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand(bool)
0x2741b  stloc.s  7
0x2741d  ldloc.s  7
0x2741f  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x27424  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x27429  ldstr    aFeaturesetxml// "featureSetXML"
0x2742e  ldloc.1
0x2742f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x27434  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x27439  pop
0x2743a  ldloc.s  7
0x2743c  ldstr    aUpdateOrganiza_9// "update OrganizationBase set FeatureSet "...
0x27441  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x27446  ldloc.s  7
0x27448  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x2744d  pop
0x2744e  leave.s  loc_2745C
0x27450  ldloc.s  7
0x27452  brfalse.s loc_2745B
0x27454  ldloc.s  7
0x27456  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2745b  endfinally
0x2745c  ret
```
