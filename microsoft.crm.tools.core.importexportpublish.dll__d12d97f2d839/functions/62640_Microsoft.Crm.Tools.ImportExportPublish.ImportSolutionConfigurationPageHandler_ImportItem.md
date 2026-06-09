# Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionConfigurationPageHandler::ImportItem

- ea: `0x62640`
- end: `0x628b6`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionConfigurationPageHandler::ImportItem`
- size: `630`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x36310`
- `0x36320`
- `0x62640`
- `0x63df0`

## string_xrefs

- `0x6264b`: `SolutionManifest`
- `0x6273a`: `ConfigurationPage`
- `0x6277d`: `RootComponents/RootComponent[@type="{0}" and @schemaName="{1}"]`
- `0x627b1`: `The web resource with the name {0} must be a component in this managed solution for it to be the configuration page of the solution`
- `0x62849`: `configurationpageid`
- `0x62873`: `configurationpageid`

## pseudocode

```c

```

## disassembly

```asm
0x62640  ldarg.0
0x62641  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x62646  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x6264b  ldstr    aSolutionmanife_2// "SolutionManifest"
0x62650  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x62655  stloc.0
0x62656  ldloc.0
0x62657  brtrue.s loc_6265A
0x62659  ret
0x6265a  nop
0x6265b  ldloc.0
0x6265c  ldstr    aUniquename_0// "UniqueName"
0x62661  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x62666  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6266b  stloc.1
0x6266c  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionService::.ctor()
0x62671  stloc.2
0x62672  ldstr    aSolution// "Solution"
0x62677  ldarg.0
0x62678  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionConfigurationPageHandler::context
0x6267d  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x62682  stloc.3
0x62683  ldarg.0
0x62684  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionConfigurationPageHandler::isHolding
0x62689  brfalse.s loc_626A5
0x6268b  ldloc.3
0x6268c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x62691  ldstr    aUniquename// "uniquename"
0x62696  ldc.i4.0
0x62697  ldloc.1
0x62698  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.SolutionHelper::GetHoldingSolutionName(string)
0x6269d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x626a2  pop
0x626a3  br.s     loc_626B8
0x626a5  ldloc.3
0x626a6  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x626ab  ldstr    aUniquename// "uniquename"
0x626b0  ldc.i4.0
0x626b1  ldloc.1
0x626b2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x626b7  pop
0x626b8  ldloc.3
0x626b9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x626be  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddPrimaryKey()
0x626c3  ldloc.2
0x626c4  ldloc.3
0x626c5  ldarg.0
0x626c6  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionConfigurationPageHandler::context
0x626cb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x626d0  stloc.s  4
0x626d2  ldloc.s  4
0x626d4  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x626d9  ldc.i4.1
0x626da  beq.s    loc_626FB
0x626dc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x626e1  ldstr    aThereIsNoSolut_0// "There is no solution with the unique na"...
0x626e6  ldc.i4.1
0x626e7  newarr   [mscorlib]System.Object
0x626ec  dup
0x626ed  ldc.i4.0
0x626ee  ldloc.1
0x626ef  stelem.ref
0x626f0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x626f5  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionException::.ctor(string message)
0x626fa  throw
0x626fb  ldloc.s  4
0x626fd  ldc.i4.0
0x626fe  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x62703  ldstr    aSolutionid// "solutionid"
0x62708  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6270d  unbox.any [mscorlib]System.Guid
0x62712  stloc.s  5
0x62714  ldarg.0
0x62715  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionConfigurationPageHandler::context
0x6271a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x6271f  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Solution::.ctor(valuetype [mscorlib]System.Guid)
0x62724  stloc.s  6
0x62726  ldloc.s  6
0x62728  ldstr    aSolutionid// "solutionid"
0x6272d  ldloc.s  5
0x6272f  box      [mscorlib]System.Guid
0x62734  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x62739  ldloc.0
0x6273a  ldstr    aConfigurationp// "ConfigurationPage"
0x6273f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x62744  stloc.s  7
0x62746  ldloc.s  7
0x62748  brfalse  loc_62871
0x6274d  ldloc.s  7
0x6274f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x62754  stloc.s  8
0x62756  ldloc.0
0x62757  ldstr    aManaged// "Managed"
0x6275c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x62761  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x62766  ldstr    a0_1// "0"
0x6276b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x62770  brtrue.s loc_62775
0x62772  ldc.i4.1
0x62773  br.s     loc_62776
0x62775  ldc.i4.0
0x62776  brfalse.s loc_627D1
0x62778  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6277d  ldstr    aRootcomponents_2// "RootComponents/RootComponent[@type=\"{0"...
0x62782  ldc.i4.2
0x62783  newarr   [mscorlib]System.Object
0x62788  dup
0x62789  ldc.i4.0
0x6278a  ldc.i4.s 0x3D
0x6278c  box      [mscorlib]System.Int32
0x62791  stelem.ref
0x62792  dup
0x62793  ldc.i4.1
0x62794  ldloc.s  8
0x62796  stelem.ref
0x62797  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6279c  stloc.s  0xB
0x6279e  ldloc.0
0x6279f  ldloc.s  0xB
0x627a1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x627a6  stloc.s  0xC
0x627a8  ldloc.s  0xC
0x627aa  brtrue.s loc_627D1
0x627ac  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x627b1  ldstr    aTheWebResource_0// "The web resource with the name {0} must"...
0x627b6  ldc.i4.1
0x627b7  newarr   [mscorlib]System.Object
0x627bc  dup
0x627bd  ldc.i4.0
0x627be  ldloc.s  8
0x627c0  stelem.ref
0x627c1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x627c6  ldc.i4   0x8004701D
0x627cb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x627d0  throw
0x627d1  ldstr    aWebresource// "WebResource"
0x627d6  ldarg.0
0x627d7  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionConfigurationPageHandler::context
0x627dc  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x627e1  stloc.s  9
0x627e3  ldloc.s  9
0x627e5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x627ea  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddPrimaryKey()
0x627ef  ldloc.s  9
0x627f1  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x627f6  ldstr    aName// "name"
0x627fb  ldc.i4.0
0x627fc  ldloc.s  8
0x627fe  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x62803  pop
0x62804  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WebResourceService::.ctor()
0x62809  ldloc.s  9
0x6280b  ldarg.0
0x6280c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionConfigurationPageHandler::context
0x62811  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x62816  stloc.s  0xA
0x62818  ldc.i4.1
0x62819  ldloc.s  0xA
0x6281b  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x62820  beq.s    loc_62847
0x62822  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x62827  ldstr    aThereIsEitherZ// "There is either zero or more than one w"...
0x6282c  ldc.i4.1
0x6282d  newarr   [mscorlib]System.Object
0x62832  dup
0x62833  ldc.i4.0
0x62834  ldloc.s  8
0x62836  stelem.ref
0x62837  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6283c  ldc.i4   0x8004701B
0x62841  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x62846  throw
0x62847  ldloc.s  6
0x62849  ldstr    aConfigurationp_0// "configurationpageid"
0x6284e  ldloc.s  0xA
0x62850  ldc.i4.0
0x62851  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x62856  ldstr    aWebresourceid// "webresourceid"
0x6285b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x62860  unbox.any [mscorlib]System.Guid
0x62865  box      [mscorlib]System.Guid
0x6286a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6286f  br.s     loc_62882
0x62871  ldloc.s  6
0x62873  ldstr    aConfigurationp_0// "configurationpageid"
0x62878  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x6287d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x62882  ldloc.2
0x62883  ldloc.s  6
0x62885  ldarg.0
0x62886  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionConfigurationPageHandler::context
0x6288b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x62890  leave.s  loc_628B5
0x62892  stloc.s  0xD
0x62894  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::SolutionImportErrorMessage
0x62899  stloc.s  0xE
0x6289b  ldarg.0
0x6289c  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionConfigurationPageHandler::tracer
0x628a1  ldloc.s  0xE
0x628a3  ldloc.s  0xD
0x628a5  ldc.i4.3
0x628a6  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x628ab  ldloc.s  0xE
0x628ad  ldloc.s  0xD
0x628af  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x628b4  throw
0x628b5  ret
```
