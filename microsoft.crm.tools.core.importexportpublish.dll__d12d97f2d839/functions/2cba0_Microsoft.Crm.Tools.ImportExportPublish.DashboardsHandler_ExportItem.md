# Microsoft.Crm.Tools.ImportExportPublish.DashboardsHandler::ExportItem

- ea: `0x2cba0`
- end: `0x2cf49`
- name: `Microsoft.Crm.Tools.ImportExportPublish.DashboardsHandler::ExportItem`
- size: `937`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x2cb30`
- `0x2cba0`
- `0x2d080`
- `0x2d170`
- `0x37290`
- `0x37ad0`
- `0x37c20`
- `0x383c0`
- `0x38770`
- `0x38b70`
- `0x391e0`
- `0x39940`
- `0x39d50`
- `0x3a5e0`
- `0x3b380`
- `0x3b3c0`
- `0x4d4a0`
- `0x7bc70`

## string_xrefs

- `0x2ce21`: `FormXml`
- `0x2ce32`: `FormXml`
- `0x2ce43`: `FormXml`
- `0x2ce63`: `FormXml`
- `0x2cc23`: `formxml`
- `0x2ccec`: `formxml`

## pseudocode

```c

```

## disassembly

```asm
0x2cba0  ldarg.0
0x2cba1  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.DashboardsHandler::_solutionComponentDashboardSet
0x2cba6  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x2cbab  ldc.i4.0
0x2cbac  bgt.s    loc_2CBAF
0x2cbae  ret
0x2cbaf  ldarg.1
0x2cbb0  call     bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::IsManagedSolutionInDocument(class [System.Xml]System.Xml.XmlDocument xmlDocument)
0x2cbb5  stloc.0
0x2cbb6  ldarg.1
0x2cbb7  ldstr    aDashboards// "Dashboards"
0x2cbbc  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x2cbc1  stloc.1
0x2cbc2  ldc.i4.1
0x2cbc3  stloc.2
0x2cbc4  ldnull
0x2cbc5  stloc.3
0x2cbc6  ldarg.0
0x2cbc7  ldloc.2
0x2cbc8  ldloc.3
0x2cbc9  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.DashboardsHandler::RetrieveDashboardsForExport(int32 pageNumber, string pagingCookie)
0x2cbce  stloc.s  4
0x2cbd0  ldloc.s  4
0x2cbd2  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x2cbd7  stloc.s  5
0x2cbd9  br       loc_2CEC9
0x2cbde  ldloc.s  5
0x2cbe0  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2cbe5  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x2cbea  stloc.s  6
0x2cbec  ldc.i4.0
0x2cbed  stloc.s  7
0x2cbef  ldloc.s  6
0x2cbf1  ldstr    aFormid// "formid"
0x2cbf6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2cbfb  unbox.any [mscorlib]System.Guid
0x2cc00  stloc.s  8
0x2cc02  ldarg.0
0x2cc03  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.DashboardsHandler::_solutionComponentDashboardSet
0x2cc08  ldloc.s  8
0x2cc0a  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x2cc0f  brfalse  loc_2CEC9
0x2cc14  ldarg.0
0x2cc15  ldloc.s  6
0x2cc17  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.DashboardsHandler::DoesDashboardNeedToBeSkippedForExportToTargetVersion(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity dashboard)
0x2cc1c  brtrue   loc_2CEC9
0x2cc21  ldloc.s  6
0x2cc23  ldstr    aFormxml_0// "formxml"
0x2cc28  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2cc2d  isinst   [mscorlib]System.String
0x2cc32  stloc.s  9
0x2cc34  ldloc.s  9
0x2cc36  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x2cc3b  brtrue   loc_2CCFD
0x2cc40  ldloc.s  9
0x2cc42  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x2cc47  stloc.s  0x10
0x2cc49  ldloc.s  0x10
0x2cc4b  ldarg.0
0x2cc4c  ldfld    class [mscorlib]System.Action`1<class [System.Xml]System.Xml.XmlNode> Microsoft.Crm.Tools.ImportExportPublish.DashboardsHandler::removeLabelsDelegate
0x2cc51  ldarg.0
0x2cc52  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.DashboardsHandler::get_ExportToTargetVersionContext()
0x2cc57  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::ProcessCustomControlNodesForExportToTargetVersion(class [System.Xml]System.Xml.XmlNode rootNode, class [mscorlib]System.Action`1<class [System.Xml]System.Xml.XmlNode> actionBeforeDeleteNode, class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext exportToTargetVersionContext)
0x2cc5c  brtrue.s loc_2CC98
0x2cc5e  ldloc.s  0x10
0x2cc60  ldloc.s  0x10
0x2cc62  ldarg.0
0x2cc63  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.DashboardsHandler::_context
0x2cc68  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormSolutionUtility::PreProcessCustomControls(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlDocument, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2cc6d  ldloc.s  0x10
0x2cc6f  ldarg.0
0x2cc70  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.DashboardsHandler::get_ExportToTargetVersionContext()
0x2cc75  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::UnsupportedCustomControlsExists(class [System.Xml]System.Xml.XmlNode rootNode, class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext exportToTargetVersionContext)
0x2cc7a  brfalse.s loc_2CC98
0x2cc7c  ldloc.s  0x10
0x2cc7e  ldnull
0x2cc7f  ldstr    aDashboards// "Dashboards"
0x2cc84  ldarg.0
0x2cc85  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.DashboardsHandler::get_ExportToTargetVersionContext()
0x2cc8a  ldarg.0
0x2cc8b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.DashboardsHandler::_context
0x2cc90  call     void Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::RemoveUnsupportedCustomControls(class [System.Xml]System.Xml.XmlNode rootNode, class [mscorlib]System.Action`1<class [System.Xml]System.Xml.XmlNode> actionBeforeDeleteNode, string handlerType, class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext exportToTargetVersionContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2cc95  ldc.i4.1
0x2cc96  stloc.s  7
0x2cc98  ldarg.0
0x2cc99  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.DashboardsHandler::get_ExportToTargetVersionContext()
0x2cc9e  ldloc.s  0x10
0x2cca0  ldloc.s  0x10
0x2cca2  ldarg.0
0x2cca3  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.DashboardsHandler::_context
0x2cca8  call     void Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::ProcessCustomControlsToExportAs(class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext exportToTargetVersionContext, class [System.Xml]System.Xml.XmlNode systemFormNode, class [System.Xml]System.Xml.XmlDocument containingDocument, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2ccad  ldloc.s  0x10
0x2ccaf  ldarg.0
0x2ccb0  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.DashboardsHandler::get_ExportToTargetVersionContext()
0x2ccb5  ldarg.0
0x2ccb6  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.DashboardsHandler::_context
0x2ccbb  ldc.i4.0
0x2ccbc  ldstr    aDashboards// "Dashboards"
0x2ccc1  call     void Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::AddTypeAttributeForBoundFields(class [System.Xml]System.Xml.XmlNode rootNode, class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext exportToTargetVersionContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, int32 otc, string handlerType)
0x2ccc6  ldloc.s  0x10
0x2ccc8  ldarg.0
0x2ccc9  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.CustomControlsExportAsHandlerRegistry Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::registryInstance
0x2ccce  ldarg.0
0x2cccf  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.DashboardsHandler::get_ExportToTargetVersionContext()
0x2ccd4  ldstr    aDashboards// "Dashboards"
0x2ccd9  ldarg.0
0x2ccda  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.DashboardsHandler::_tracer
0x2ccdf  ldarg.0
0x2cce0  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.DashboardsHandler::_context
0x2cce5  call     void Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::ModifyControlProperties(class [System.Xml]System.Xml.XmlNode rootNode, class Microsoft.Crm.Tools.ImportExportPublish.CustomControlsExportAsHandlerRegistry registryInstance, class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext exportToTargetVersionContext, string handlerType, class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer tracer, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2ccea  ldloc.s  6
0x2ccec  ldstr    aFormxml_0// "formxml"
0x2ccf1  ldloc.s  0x10
0x2ccf3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x2ccf8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x2ccfd  ldarg.1
0x2ccfe  ldstr    aDashboard// "Dashboard"
0x2cd03  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x2cd08  stloc.s  0xA
0x2cd0a  ldarg.0
0x2cd0b  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::_exportDeltaOverride
0x2cd10  brtrue.s loc_2CD3E
0x2cd12  ldloc.s  6
0x2cd14  ldstr    aSolutionid// "solutionid"
0x2cd19  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2cd1e  unbox.any [mscorlib]System.Guid
0x2cd23  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x2cd28  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2cd2d  brtrue.s loc_2CD3E
0x2cd2f  ldloc.s  6
0x2cd31  ldarg.0
0x2cd32  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.DashboardsHandler::_context
0x2cd37  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormLabelHelper::HaveLabelsOfFormXmlChanged(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2cd3c  brfalse.s loc_2CD41
0x2cd3e  ldc.i4.1
0x2cd3f  stloc.s  7
0x2cd41  ldloc.s  8
0x2cd43  ldstr    aSystemform_0// "SystemForm"
0x2cd48  ldarg.0
0x2cd49  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.DashboardsHandler::_context
0x2cd4e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x2cd53  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x2cd58  stloc.s  0xB
0x2cd5a  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionAwareLocalizedLabelService::.ctor()
0x2cd5f  stloc.s  0xC
0x2cd61  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LabelCollectionGenerator::.ctor()
0x2cd66  stloc.s  0xD
0x2cd68  ldloc.s  0xC
0x2cd6a  ldloc.s  0xD
0x2cd6c  ldloc.s  0xB
0x2cd6e  ldstr    aName// "name"
0x2cd73  ldc.i4.0
0x2cd74  ldarg.0
0x2cd75  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.DashboardsHandler::_context
0x2cd7a  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionAwareLocalizedLabelService::RetrieveLocLabelsIncludeDeleted(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ILocalizedLabelGenerator, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, string, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2cd7f  ldloc.s  0xD
0x2cd81  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LabelCollectionGenerator::GetLabel()
0x2cd86  stloc.s  0xE
0x2cd88  ldloc.s  7
0x2cd8a  ldarg.0
0x2cd8b  ldarg.1
0x2cd8c  ldloc.s  0xA
0x2cd8e  ldloc.s  0xE
0x2cd90  ldstr    aLocalizedname// "LocalizedName"
0x2cd95  ldstr    aLocalizednames_1// "LocalizedNames"
0x2cd9a  ldc.i4.1
0x2cd9b  ldnull
0x2cd9c  ldnull
0x2cd9d  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddLabels(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode rootNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection labelCollection, string singularName, string pluralName, bool force, [opt] string defaultLabel, [opt] string baseLanguage)
0x2cda2  or
0x2cda3  stloc.s  7
0x2cda5  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LabelCollectionGenerator::.ctor()
0x2cdaa  stloc.s  0xD
0x2cdac  ldloc.s  0xC
0x2cdae  ldloc.s  0xD
0x2cdb0  ldloc.s  0xB
0x2cdb2  ldstr    aDescription// "description"
0x2cdb7  ldc.i4.0
0x2cdb8  ldarg.0
0x2cdb9  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.DashboardsHandler::_context
0x2cdbe  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionAwareLocalizedLabelService::RetrieveLocLabelsIncludeDeleted(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ILocalizedLabelGenerator, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, string, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2cdc3  ldloc.s  0xD
0x2cdc5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LabelCollectionGenerator::GetLabel()
0x2cdca  stloc.s  0xF
0x2cdcc  ldloc.s  7
0x2cdce  ldarg.0
0x2cdcf  ldarg.1
0x2cdd0  ldloc.s  0xA
0x2cdd2  ldloc.s  0xF
0x2cdd4  ldstr    aDescription_0// "Description"
0x2cdd9  ldstr    aDescriptions// "Descriptions"
0x2cdde  ldc.i4.1
0x2cddf  ldnull
0x2cde0  ldnull
0x2cde1  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddLabels(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode rootNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection labelCollection, string singularName, string pluralName, bool force, [opt] string defaultLabel, [opt] string baseLanguage)
0x2cde6  or
0x2cde7  stloc.s  7
0x2cde9  ldloc.s  7
0x2cdeb  brfalse  loc_2CE7B
0x2cdf0  ldloc.1
0x2cdf1  ldloc.s  0xA
0x2cdf3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x2cdf8  pop
0x2cdf9  ldarg.0
0x2cdfa  ldstr    aDashboard// "Dashboard"
0x2cdff  ldarg.1
0x2ce00  ldloc.s  0xA
0x2ce02  ldloc.s  6
0x2ce04  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be)
0x2ce09  ldloc.s  6
0x2ce0b  ldstr    aIsmanaged// "ismanaged"
0x2ce10  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2ce15  unbox.any [mscorlib]System.Boolean
0x2ce1a  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlProperties(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container, bool managed)
0x2ce1f  ldloc.s  0xA
0x2ce21  ldstr    aFormxml// "FormXml"
0x2ce26  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2ce2b  brfalse  loc_2CEC9
0x2ce30  ldloc.s  0xA
0x2ce32  ldstr    aFormxml// "FormXml"
0x2ce37  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2ce3c  ldstr    aFormsTypeDashb// "<forms type='dashboard'>"
0x2ce41  ldloc.s  0xA
0x2ce43  ldstr    aFormxml// "FormXml"
0x2ce48  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2ce4d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x2ce52  ldstr    aForms// "</forms>"
0x2ce57  call     string [mscorlib]System.String::Concat(string, string, string)
0x2ce5c  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x2ce61  ldloc.s  0xA
0x2ce63  ldstr    aFormxml// "FormXml"
0x2ce68  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2ce6d  ldloc.0
0x2ce6e  ldarg.0
0x2ce6f  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.DashboardsHandler::_context
0x2ce74  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportExportFormXmlUtils::ProcessRoleIds(class [System.Xml]System.Xml.XmlElement formXml, bool removeNonRootBURoles, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2ce79  br.s     loc_2CEC9
0x2ce7b  ldarg.1
0x2ce7c  ldarg.0
0x2ce7d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.DashboardsHandler::_context
0x2ce82  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::ExportAsUnmodified(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2ce87  brfalse.s loc_2CEC9
0x2ce89  ldloc.1
0x2ce8a  ldloc.s  0xA
0x2ce8c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x2ce91  pop
0x2ce92  ldarg.0
0x2ce93  ldstr    aUnmodifieddash// "UnmodifiedDashboard"
0x2ce98  ldarg.1
0x2ce99  ldloc.s  0xA
0x2ce9b  ldloc.s  6
0x2ce9d  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be)
0x2cea2  ldloc.s  6
0x2cea4  ldstr    aIsmanaged// "ismanaged"
0x2cea9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2ceae  unbox.any [mscorlib]System.Boolean
0x2ceb3  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlProperties(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container, bool managed)
0x2ceb8  ldloc.s  0xA
0x2ceba  ldstr    aUnmodified// "unmodified"
0x2cebf  ldstr    a1// "1"
0x2cec4  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x2cec9  ldloc.s  5
0x2cecb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2ced0  brtrue   loc_2CBDE
0x2ced5  leave.s  loc_2CEEC
0x2ced7  ldloc.s  5
0x2ced9  isinst   [mscorlib]System.IDisposable
0x2cede  stloc.s  0x11
0x2cee0  ldloc.s  0x11
0x2cee2  brfalse.s loc_2CEEB
0x2cee4  ldloc.s  0x11
0x2cee6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2ceeb  endfinally
0x2ceec  ldloc.2
0x2ceed  ldc.i4.1
0x2ceee  add
0x2ceef  stloc.2
0x2cef0  ldloc.s  4
0x2cef2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_PagingCookie()
0x2cef7  stloc.3
0x2cef8  ldloc.s  4
0x2cefa  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_MoreRecords()
0x2ceff  brtrue   loc_2CBC6
0x2cf04  ldloc.1
0x2cf05  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x2cf0a  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x2cf0f  ldc.i4.0
0x2cf10  ble.s    loc_2CF2F
0x2cf12  ldarg.1
0x2cf13  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x2cf18  ldloc.1
0x2cf19  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x2cf1e  pop
0x2cf1f  ldarg.0
0x2cf20  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.DashboardsHandler::_tracer
0x2cf25  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::DashboardExportSuccessMessage
0x2cf2a  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddSuccess(string successMessage)
0x2cf2f  leave.s  loc_2CF48
0x2cf31  stloc.s  0x12
0x2cf33  ldarg.0
  ... truncated ...
```
