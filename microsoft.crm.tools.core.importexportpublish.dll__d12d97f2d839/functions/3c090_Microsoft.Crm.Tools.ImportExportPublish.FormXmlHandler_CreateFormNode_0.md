# Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::CreateFormNode_0

- ea: `0x3c090`
- end: `0x3c44e`
- name: `Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::CreateFormNode_0`
- size: `958`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x3b9c0`
- `0x3c070`

## callees

- `0x37290`
- `0x37ad0`
- `0x37c20`
- `0x37fd0`
- `0x38120`
- `0x383c0`
- `0x38770`
- `0x38b70`
- `0x391e0`
- `0x39940`
- `0x39d50`
- `0x3a5e0`
- `0x3a780`
- `0x3af00`
- `0x3b550`
- `0x3c090`

## string_xrefs

- `0x3c226`: `canbedeleted`
- `0x3c217`: `CanBeDeleted`
- `0x3c307`: `FormXML`
- `0x3c367`: `FormXML`
- `0x3c37e`: `FormXML`
- `0x3c098`: `taskBasedForm`
- `0x3c0c7`: `Workflow.TaskBasedFlow.ExportAs.TaskFlowForm.FilteredMessage`

## pseudocode

```c

```

## disassembly

```asm
0x3c090  ldarg.1
0x3c091  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x3c096  stloc.0
0x3c097  ldarg.2
0x3c098  ldstr    aTaskbasedform// "taskBasedForm"
0x3c09d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3c0a2  brfalse.s loc_3C118
0x3c0a4  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x3c0a9  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x3c0ae  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_TaskBasedFlowSolutionAware()
0x3c0b3  ldarg.0
0x3c0b4  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::context
0x3c0b9  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3c0be  brfalse.s loc_3C0C7
0x3c0c0  ldsfld   bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ApplicationXmlDiffCalculatorBase::IsTargetVersionSupportsTaskBasedFlow
0x3c0c5  brtrue.s loc_3C118
0x3c0c7  ldstr    aWorkflowTaskba// "Workflow.TaskBasedFlow.ExportAs.TaskFlo"...
0x3c0cc  ldarg.0
0x3c0cd  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::context
0x3c0d2  ldc.i4.1
0x3c0d3  newarr   [mscorlib]System.Object
0x3c0d8  dup
0x3c0d9  ldc.i4.0
0x3c0da  ldarg.3
0x3c0db  ldstr    aUniquename// "uniquename"
0x3c0e0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3c0e5  stelem.ref
0x3c0e6  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, object[])
0x3c0eb  stloc.s  7
0x3c0ed  ldarg.3
0x3c0ee  ldstr    aFormid// "formid"
0x3c0f3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3c0f8  unbox.any [mscorlib]System.Guid
0x3c0fd  ldc.i4.s 0x3C
0x3c0ff  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>::.ctor(var<u1>, !!T0)
0x3c104  stloc.s  8
0x3c106  ldarg.0
0x3c107  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::get_ExportToTargetVersionContext()
0x3c10c  ldloc.s  8
0x3c10e  ldc.i4.1
0x3c10f  ldloc.s  7
0x3c111  ldc.i4.0
0x3c112  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::AddFilteredComponentAndComment(class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32> dependentComponent, valuetype Microsoft.Crm.Tools.ImportExportPublish.FilteredComponentAction action, string comment, bool addToExistingComments)
0x3c117  ret
0x3c118  ldarg.1
0x3c119  ldstr    aFormsType// "forms[@type='"
0x3c11e  ldarg.2
0x3c11f  ldstr    asc_A2596// "']"
0x3c124  call     string [mscorlib]System.String::Concat(string, string, string)
0x3c129  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x3c12e  stloc.1
0x3c12f  ldloc.1
0x3c130  brtrue.s loc_3C157
0x3c132  ldloc.0
0x3c133  ldstr    aForms_0// "forms"
0x3c138  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3c13d  stloc.1
0x3c13e  ldloc.1
0x3c13f  castclass [System.Xml]System.Xml.XmlElement
0x3c144  ldstr    aType_0// "type"
0x3c149  ldarg.2
0x3c14a  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3c14f  ldarg.1
0x3c150  ldloc.1
0x3c151  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3c156  pop
0x3c157  ldloc.0
0x3c158  ldstr    aSystemform// "systemform"
0x3c15d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3c162  stloc.2
0x3c163  ldarg.0
0x3c164  ldstr    aSystemform// "systemform"
0x3c169  ldloc.0
0x3c16a  ldloc.2
0x3c16b  ldarg.3
0x3c16c  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be)
0x3c171  ldarg.s  5
0x3c173  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlProperties(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container, bool managed)
0x3c178  ldarg.3
0x3c179  ldstr    aSolutionid// "solutionid"
0x3c17e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3c183  unbox.any [mscorlib]System.Guid
0x3c188  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x3c18d  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3c192  brfalse.s loc_3C1C9
0x3c194  ldloc.0
0x3c195  ldarg.0
0x3c196  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::context
0x3c19b  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::ExportAsUnmodified(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3c1a0  brfalse.s loc_3C1C9
0x3c1a2  ldloc.0
0x3c1a3  ldstr    aUnmodified// "unmodified"
0x3c1a8  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x3c1ad  stloc.s  9
0x3c1af  ldloc.s  9
0x3c1b1  ldstr    a1// "1"
0x3c1b6  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x3c1bb  ldloc.2
0x3c1bc  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x3c1c1  ldloc.s  9
0x3c1c3  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x3c1c8  pop
0x3c1c9  ldarg.3
0x3c1ca  ldstr    aIsmanaged// "ismanaged"
0x3c1cf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3c1d4  unbox.any [mscorlib]System.Boolean
0x3c1d9  brtrue.s loc_3C251
0x3c1db  ldloc.0
0x3c1dc  ldstr    aIscustomizable_0// "IsCustomizable"
0x3c1e1  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3c1e6  stloc.s  0xA
0x3c1e8  ldloc.s  0xA
0x3c1ea  ldarg.3
0x3c1eb  ldstr    aIscustomizable// "iscustomizable"
0x3c1f0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3c1f5  unbox.any [mscorlib]System.Boolean
0x3c1fa  brtrue.s loc_3C203
0x3c1fc  ldstr    a0_1// "0"
0x3c201  br.s     loc_3C208
0x3c203  ldstr    a1// "1"
0x3c208  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x3c20d  ldloc.2
0x3c20e  ldloc.s  0xA
0x3c210  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3c215  pop
0x3c216  ldloc.0
0x3c217  ldstr    aCanbedeleted_0// "CanBeDeleted"
0x3c21c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3c221  stloc.s  0xB
0x3c223  ldloc.s  0xB
0x3c225  ldarg.3
0x3c226  ldstr    aCanbedeleted// "canbedeleted"
0x3c22b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3c230  unbox.any [mscorlib]System.Boolean
0x3c235  brtrue.s loc_3C23E
0x3c237  ldstr    a0_1// "0"
0x3c23c  br.s     loc_3C243
0x3c23e  ldstr    a1// "1"
0x3c243  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x3c248  ldloc.2
0x3c249  ldloc.s  0xB
0x3c24b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3c250  pop
0x3c251  ldarg.s  7
0x3c253  brfalse.s loc_3C270
0x3c255  ldarg.s  4
0x3c257  brtrue.s loc_3C270
0x3c259  ldloc.2
0x3c25a  ldstr    aForm// "form"
0x3c25f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3c264  ldsfld   string [mscorlib]System.String::Empty
0x3c269  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x3c26e  br.s     loc_3C2BF
0x3c270  ldloc.2
0x3c271  ldstr    aForm// "form"
0x3c276  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3c27b  ldarg.s  5
0x3c27d  brtrue.s loc_3C291
0x3c27f  ldloc.2
0x3c280  ldstr    aForm// "form"
0x3c285  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3c28a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3c28f  br.s     loc_3C293
0x3c291  ldarg.s  4
0x3c293  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x3c298  ldloc.2
0x3c299  ldloc.2
0x3c29a  ldstr    aForm// "form"
0x3c29f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3c2a4  ldstr    aForm// "form"
0x3c2a9  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3c2ae  ldloc.2
0x3c2af  ldstr    aForm// "form"
0x3c2b4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3c2b9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::ReplaceChild(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0x3c2be  pop
0x3c2bf  ldsfld   bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ApplicationXmlDiffCalculatorBase::IsCustomControlFeatureEnabled
0x3c2c4  brfalse.s loc_3C2CD
0x3c2c6  ldsfld   bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ApplicationXmlDiffCalculatorBase::IsTargetVersionSupportsCustomControl
0x3c2cb  brtrue.s loc_3C2E5
0x3c2cd  ldloc.2
0x3c2ce  ldarg.0
0x3c2cf  ldfld    class [mscorlib]System.Action`1<class [System.Xml]System.Xml.XmlNode> Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::removeLabelsAndEventsNodes
0x3c2d4  ldarg.0
0x3c2d5  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::get_ExportToTargetVersionContext()
0x3c2da  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::ProcessCustomControlNodesForExportToTargetVersion(class [System.Xml]System.Xml.XmlNode rootNode, class [mscorlib]System.Action`1<class [System.Xml]System.Xml.XmlNode> actionBeforeDeleteNode, class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext exportToTargetVersionContext)
0x3c2df  pop
0x3c2e0  br       loc_3C394
0x3c2e5  ldloc.2
0x3c2e6  ldloc.0
0x3c2e7  ldarg.0
0x3c2e8  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::context
0x3c2ed  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormSolutionUtility::PreProcessCustomControls(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlDocument, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x3c2f2  ldloc.2
0x3c2f3  ldarg.0
0x3c2f4  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::get_ExportToTargetVersionContext()
0x3c2f9  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::UnsupportedCustomControlsExists(class [System.Xml]System.Xml.XmlNode rootNode, class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext exportToTargetVersionContext)
0x3c2fe  brfalse.s loc_3C31D
0x3c300  ldloc.2
0x3c301  ldarg.0
0x3c302  ldfld    class [mscorlib]System.Action`1<class [System.Xml]System.Xml.XmlNode> Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::removeLabelsAndEventsNodes
0x3c307  ldstr    aFormxml_2// "FormXML"
0x3c30c  ldarg.0
0x3c30d  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::get_ExportToTargetVersionContext()
0x3c312  ldarg.0
0x3c313  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::context
0x3c318  call     void Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::RemoveUnsupportedCustomControls(class [System.Xml]System.Xml.XmlNode rootNode, class [mscorlib]System.Action`1<class [System.Xml]System.Xml.XmlNode> actionBeforeDeleteNode, string handlerType, class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext exportToTargetVersionContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3c31d  ldloc.2
0x3c31e  ldarg.3
0x3c31f  ldarg.0
0x3c320  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::get_ExportToTargetVersionContext()
0x3c325  ldarg.0
0x3c326  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::context
0x3c32b  call     void Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::RemoveCustomControlsForUnsupportedTypes(class [System.Xml]System.Xml.XmlNode rootNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity formEntity, class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext exportToTargetVersionContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3c330  ldloc.2
0x3c331  ldarg.0
0x3c332  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::get_ExportToTargetVersionContext()
0x3c337  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::get_TargetVersion()
0x3c33c  call     void Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::RemoveUnsupportedEvents(class [System.Xml]System.Xml.XmlNode rootNode, class [mscorlib]System.Version targetVersion)
0x3c341  ldarg.0
0x3c342  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::get_ExportToTargetVersionContext()
0x3c347  ldloc.2
0x3c348  ldloc.0
0x3c349  ldarg.0
0x3c34a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::context
0x3c34f  call     void Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::ProcessCustomControlsToExportAs(class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext exportToTargetVersionContext, class [System.Xml]System.Xml.XmlNode systemFormNode, class [System.Xml]System.Xml.XmlDocument containingDocument, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3c354  ldloc.2
0x3c355  ldarg.0
0x3c356  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::get_ExportToTargetVersionContext()
0x3c35b  ldarg.0
0x3c35c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::context
0x3c361  ldarg.0
0x3c362  ldfld    int32 Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::objectTypeCode
0x3c367  ldstr    aFormxml_2// "FormXML"
0x3c36c  call     void Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::AddTypeAttributeForBoundFields(class [System.Xml]System.Xml.XmlNode rootNode, class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext exportToTargetVersionContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, int32 otc, string handlerType)
0x3c371  ldloc.2
0x3c372  ldarg.0
0x3c373  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.CustomControlsExportAsHandlerRegistry Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::registryInstance
0x3c378  ldarg.0
0x3c379  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::get_ExportToTargetVersionContext()
0x3c37e  ldstr    aFormxml_2// "FormXML"
0x3c383  ldarg.0
0x3c384  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::tracer
0x3c389  ldarg.0
0x3c38a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::context
0x3c38f  call     void Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::ModifyControlProperties(class [System.Xml]System.Xml.XmlNode rootNode, class Microsoft.Crm.Tools.ImportExportPublish.CustomControlsExportAsHandlerRegistry registryInstance, class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext exportToTargetVersionContext, string handlerType, class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer tracer, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3c394  ldarg.3
0x3c395  ldstr    aFormid// "formid"
0x3c39a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3c39f  unbox.any [mscorlib]System.Guid
0x3c3a4  ldstr    aSystemform_0// "SystemForm"
0x3c3a9  ldarg.0
0x3c3aa  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::context
0x3c3af  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3c3b4  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x3c3b9  stloc.3
0x3c3ba  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LabelCollectionGenerator::.ctor()
0x3c3bf  stloc.s  4
0x3c3c1  ldarg.s  6
0x3c3c3  ldloc.s  4
0x3c3c5  ldloc.3
0x3c3c6  ldstr    aName// "name"
0x3c3cb  ldc.i4.0
0x3c3cc  ldarg.0
0x3c3cd  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::context
0x3c3d2  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionAwareLocalizedLabelService::RetrieveLocLabelsIncludeDeleted(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ILocalizedLabelGenerator, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, string, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x3c3d7  ldloc.s  4
0x3c3d9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LabelCollectionGenerator::GetLabel()
0x3c3de  stloc.s  5
0x3c3e0  ldarg.0
0x3c3e1  ldloc.0
0x3c3e2  ldloc.2
0x3c3e3  ldloc.s  5
0x3c3e5  ldstr    aLocalizedname// "LocalizedName"
0x3c3ea  ldstr    aLocalizednames_1// "LocalizedNames"
0x3c3ef  ldc.i4.1
0x3c3f0  ldnull
0x3c3f1  ldnull
0x3c3f2  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddLabels(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode rootNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection labelCollection, string singularName, string pluralName, bool force, [opt] string defaultLabel, [opt] string baseLanguage)
0x3c3f7  pop
0x3c3f8  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LabelCollectionGenerator::.ctor()
0x3c3fd  stloc.s  4
0x3c3ff  ldarg.s  6
0x3c401  ldloc.s  4
0x3c403  ldloc.3
0x3c404  ldstr    aDescription// "description"
0x3c409  ldc.i4.0
0x3c40a  ldarg.0
0x3c40b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::context
0x3c410  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionAwareLocalizedLabelService::RetrieveLocLabels(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ILocalizedLabelGenerator, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, string, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x3c415  ldloc.s  4
0x3c417  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LabelCollectionGenerator::GetLabel()
0x3c41c  stloc.s  6
0x3c41e  ldarg.0
0x3c41f  ldloc.0
0x3c420  ldloc.2
0x3c421  ldloc.s  6
0x3c423  ldstr    aDescription_0// "Description"
0x3c428  ldstr    aDescriptions// "Descriptions"
0x3c42d  ldc.i4.1
  ... truncated ...
```
