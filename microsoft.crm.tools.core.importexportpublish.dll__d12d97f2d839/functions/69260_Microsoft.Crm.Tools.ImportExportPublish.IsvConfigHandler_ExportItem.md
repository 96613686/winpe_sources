# Microsoft.Crm.Tools.ImportExportPublish.IsvConfigHandler::ExportItem

- ea: `0x69260`
- end: `0x69344`
- name: `Microsoft.Crm.Tools.ImportExportPublish.IsvConfigHandler::ExportItem`
- size: `228`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x3b380`
- `0x69260`

## string_xrefs

- `0x69260`: `IsvConfig`
- `0x692e9`: `IsvConfig`
- `0x69299`: `configxml`
- `0x69308`: `configxml`

## pseudocode

```c

```

## disassembly

```asm
0x69260  ldstr    aIsvconfig// "IsvConfig"
0x69265  ldarg.0
0x69266  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.IsvConfigHandler::_context
0x6926b  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x69270  ldarg.0
0x69271  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.IsvConfigHandler::_context
0x69276  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x6927b  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.IsvConfig::.ctor(valuetype [mscorlib]System.Guid)
0x69280  dup
0x69281  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x69286  ldarg.0
0x69287  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.IsvConfigHandler::_context
0x6928c  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x69291  stloc.0
0x69292  ldloc.0
0x69293  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddPrimaryKey()
0x69298  ldloc.0
0x69299  ldstr    aConfigxml// "configxml"
0x6929e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x692a3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x692a8  ldarg.0
0x692a9  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.IsvConfigHandler::_context
0x692ae  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x692b3  stloc.1
0x692b4  ldloc.1
0x692b5  ldstr    aOrganizationid// "organizationid"
0x692ba  ldc.i4.0
0x692bb  ldarg.0
0x692bc  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.IsvConfigHandler::_context
0x692c1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x692c6  box      [mscorlib]System.Guid
0x692cb  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x692d0  pop
0x692d1  ldloc.1
0x692d2  ldloc.0
0x692d3  ldarg.0
0x692d4  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.IsvConfigHandler::_context
0x692d9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x692de  stloc.2
0x692df  ldloc.2
0x692e0  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x692e5  ldc.i4.0
0x692e6  ble.s    loc_69343
0x692e8  ldarg.1
0x692e9  ldstr    aIsvconfig// "IsvConfig"
0x692ee  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x692f3  stloc.3
0x692f4  ldarg.1
0x692f5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x692fa  ldloc.3
0x692fb  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x69300  pop
0x69301  ldloc.2
0x69302  ldc.i4.0
0x69303  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x69308  ldstr    aConfigxml// "configxml"
0x6930d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x69312  castclass [mscorlib]System.String
0x69317  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x6931c  stloc.s  4
0x6931e  ldloc.3
0x6931f  ldarg.1
0x69320  ldloc.s  4
0x69322  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x69327  ldc.i4.1
0x69328  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::ImportNode(class [System.Xml]System.Xml.XmlNode, bool)
0x6932d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x69332  pop
0x69333  ldarg.0
0x69334  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.IsvConfigHandler::tracer
0x69339  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::IsvExportSuccessMessage
0x6933e  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddSuccess(string successMessage)
0x69343  ret
```
