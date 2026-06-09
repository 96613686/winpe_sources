# Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::ExportEntityDashboardsFromAddAllAssets

- ea: `0x2d860`
- end: `0x2db18`
- name: `Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::ExportEntityDashboardsFromAddAllAssets`
- size: `696`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x2d4c0`

## callees

- `0x2d860`
- `0x2dd00`
- `0x2dff0`
- `0x391e0`
- `0x39940`
- `0x39d50`
- `0x3a5e0`
- `0x3b380`
- `0x3b3c0`
- `0x4d4a0`
- `0x7bc70`

## string_xrefs

- `0x2da0a`: `FormXml`
- `0x2da1b`: `FormXml`
- `0x2da2c`: `FormXml`
- `0x2da4c`: `FormXml`

## pseudocode

```c

```

## disassembly

```asm
0x2d860  ldarg.1
0x2d861  call     bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::IsManagedSolutionInDocument(class [System.Xml]System.Xml.XmlDocument xmlDocument)
0x2d866  stloc.0
0x2d867  ldnull
0x2d868  stloc.1
0x2d869  ldarg.1
0x2d86a  ldstr    aInteractioncen_0// "InteractionCentricDashboards"
0x2d86f  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlDocument::GetElementsByTagName(string)
0x2d874  stloc.2
0x2d875  ldloc.2
0x2d876  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x2d87b  ldc.i4.1
0x2d87c  bne.un.s loc_2D88B
0x2d87e  ldloc.2
0x2d87f  ldc.i4.0
0x2d880  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x2d885  isinst   [System.Xml]System.Xml.XmlElement
0x2d88a  stloc.1
0x2d88b  ldloc.1
0x2d88c  brtrue.s loc_2D89A
0x2d88e  ldarg.1
0x2d88f  ldstr    aInteractioncen_0// "InteractionCentricDashboards"
0x2d894  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x2d899  stloc.1
0x2d89a  ldarg.0
0x2d89b  ldfld    int32 Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::_objectTypeCode
0x2d8a0  ldarg.0
0x2d8a1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::_context
0x2d8a6  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::RetrieveEntityDashboardsForExport(int32 objectTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2d8ab  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x2d8b0  stloc.3
0x2d8b1  br       loc_2DAB2
0x2d8b6  ldloc.3
0x2d8b7  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2d8bc  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x2d8c1  stloc.s  4
0x2d8c3  ldc.i4.0
0x2d8c4  stloc.s  5
0x2d8c6  ldloc.s  4
0x2d8c8  ldstr    aFormid// "formid"
0x2d8cd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2d8d2  unbox.any [mscorlib]System.Guid
0x2d8d7  stloc.s  6
0x2d8d9  ldarg.0
0x2d8da  ldloc.s  4
0x2d8dc  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::DoesDashboardNeedToBeSkippedForExportToTargetVersion(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity dashboard)
0x2d8e1  brtrue   loc_2DAB2
0x2d8e6  ldarg.1
0x2d8e7  ldstr    aInteractioncen// "InteractionCentricDashboard"
0x2d8ec  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x2d8f1  stloc.s  7
0x2d8f3  ldarg.0
0x2d8f4  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::_exportDeltaOverride
0x2d8f9  brtrue.s loc_2D927
0x2d8fb  ldloc.s  4
0x2d8fd  ldstr    aSolutionid// "solutionid"
0x2d902  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2d907  unbox.any [mscorlib]System.Guid
0x2d90c  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x2d911  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2d916  brtrue.s loc_2D927
0x2d918  ldloc.s  4
0x2d91a  ldarg.0
0x2d91b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::_context
0x2d920  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormLabelHelper::HaveLabelsOfFormXmlChanged(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2d925  brfalse.s loc_2D92A
0x2d927  ldc.i4.1
0x2d928  stloc.s  5
0x2d92a  ldloc.s  6
0x2d92c  ldstr    aSystemform_0// "SystemForm"
0x2d931  ldarg.0
0x2d932  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::_context
0x2d937  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x2d93c  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x2d941  stloc.s  8
0x2d943  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionAwareLocalizedLabelService::.ctor()
0x2d948  stloc.s  9
0x2d94a  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LabelCollectionGenerator::.ctor()
0x2d94f  stloc.s  0xA
0x2d951  ldloc.s  9
0x2d953  ldloc.s  0xA
0x2d955  ldloc.s  8
0x2d957  ldstr    aName// "name"
0x2d95c  ldc.i4.0
0x2d95d  ldarg.0
0x2d95e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::_context
0x2d963  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionAwareLocalizedLabelService::RetrieveLocLabelsIncludeDeleted(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ILocalizedLabelGenerator, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, string, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2d968  ldloc.s  0xA
0x2d96a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LabelCollectionGenerator::GetLabel()
0x2d96f  stloc.s  0xB
0x2d971  ldloc.s  5
0x2d973  ldarg.0
0x2d974  ldarg.1
0x2d975  ldloc.s  7
0x2d977  ldloc.s  0xB
0x2d979  ldstr    aLocalizedname// "LocalizedName"
0x2d97e  ldstr    aLocalizednames_1// "LocalizedNames"
0x2d983  ldc.i4.1
0x2d984  ldnull
0x2d985  ldnull
0x2d986  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddLabels(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode rootNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection labelCollection, string singularName, string pluralName, bool force, [opt] string defaultLabel, [opt] string baseLanguage)
0x2d98b  or
0x2d98c  stloc.s  5
0x2d98e  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LabelCollectionGenerator::.ctor()
0x2d993  stloc.s  0xA
0x2d995  ldloc.s  9
0x2d997  ldloc.s  0xA
0x2d999  ldloc.s  8
0x2d99b  ldstr    aDescription// "description"
0x2d9a0  ldc.i4.0
0x2d9a1  ldarg.0
0x2d9a2  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::_context
0x2d9a7  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionAwareLocalizedLabelService::RetrieveLocLabelsIncludeDeleted(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ILocalizedLabelGenerator, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, string, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2d9ac  ldloc.s  0xA
0x2d9ae  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LabelCollectionGenerator::GetLabel()
0x2d9b3  stloc.s  0xC
0x2d9b5  ldloc.s  5
0x2d9b7  ldarg.0
0x2d9b8  ldarg.1
0x2d9b9  ldloc.s  7
0x2d9bb  ldloc.s  0xC
0x2d9bd  ldstr    aDescription_0// "Description"
0x2d9c2  ldstr    aDescriptions// "Descriptions"
0x2d9c7  ldc.i4.1
0x2d9c8  ldnull
0x2d9c9  ldnull
0x2d9ca  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddLabels(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode rootNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection labelCollection, string singularName, string pluralName, bool force, [opt] string defaultLabel, [opt] string baseLanguage)
0x2d9cf  or
0x2d9d0  stloc.s  5
0x2d9d2  ldloc.s  5
0x2d9d4  brfalse  loc_2DA64
0x2d9d9  ldloc.1
0x2d9da  ldloc.s  7
0x2d9dc  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x2d9e1  pop
0x2d9e2  ldarg.0
0x2d9e3  ldstr    aInteractioncen// "InteractionCentricDashboard"
0x2d9e8  ldarg.1
0x2d9e9  ldloc.s  7
0x2d9eb  ldloc.s  4
0x2d9ed  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be)
0x2d9f2  ldloc.s  4
0x2d9f4  ldstr    aIsmanaged// "ismanaged"
0x2d9f9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2d9fe  unbox.any [mscorlib]System.Boolean
0x2da03  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlProperties(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container, bool managed)
0x2da08  ldloc.s  7
0x2da0a  ldstr    aFormxml// "FormXml"
0x2da0f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2da14  brfalse  loc_2DAB2
0x2da19  ldloc.s  7
0x2da1b  ldstr    aFormxml// "FormXml"
0x2da20  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2da25  ldstr    aFormsTypeInter// "<forms type='interactioncentricdashboar"...
0x2da2a  ldloc.s  7
0x2da2c  ldstr    aFormxml// "FormXml"
0x2da31  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2da36  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x2da3b  ldstr    aForms// "</forms>"
0x2da40  call     string [mscorlib]System.String::Concat(string, string, string)
0x2da45  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x2da4a  ldloc.s  7
0x2da4c  ldstr    aFormxml// "FormXml"
0x2da51  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2da56  ldloc.0
0x2da57  ldarg.0
0x2da58  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::_context
0x2da5d  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportExportFormXmlUtils::ProcessRoleIds(class [System.Xml]System.Xml.XmlElement formXml, bool removeNonRootBURoles, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2da62  br.s     loc_2DAB2
0x2da64  ldarg.1
0x2da65  ldarg.0
0x2da66  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::_context
0x2da6b  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::ExportAsUnmodified(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2da70  brfalse.s loc_2DAB2
0x2da72  ldloc.1
0x2da73  ldloc.s  7
0x2da75  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x2da7a  pop
0x2da7b  ldarg.0
0x2da7c  ldstr    aUnmodifieddash// "UnmodifiedDashboard"
0x2da81  ldarg.1
0x2da82  ldloc.s  7
0x2da84  ldloc.s  4
0x2da86  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be)
0x2da8b  ldloc.s  4
0x2da8d  ldstr    aIsmanaged// "ismanaged"
0x2da92  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2da97  unbox.any [mscorlib]System.Boolean
0x2da9c  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlProperties(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container, bool managed)
0x2daa1  ldloc.s  7
0x2daa3  ldstr    aUnmodified// "unmodified"
0x2daa8  ldstr    a1// "1"
0x2daad  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x2dab2  ldloc.3
0x2dab3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2dab8  brtrue   loc_2D8B6
0x2dabd  leave.s  loc_2DAD3
0x2dabf  ldloc.3
0x2dac0  isinst   [mscorlib]System.IDisposable
0x2dac5  stloc.s  0xD
0x2dac7  ldloc.s  0xD
0x2dac9  brfalse.s loc_2DAD2
0x2dacb  ldloc.s  0xD
0x2dacd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2dad2  endfinally
0x2dad3  ldloc.1
0x2dad4  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x2dad9  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x2dade  ldc.i4.0
0x2dadf  ble.s    loc_2DAFE
0x2dae1  ldarg.1
0x2dae2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x2dae7  ldloc.1
0x2dae8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x2daed  pop
0x2daee  ldarg.0
0x2daef  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::_tracer
0x2daf4  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::DashboardExportSuccessMessage
0x2daf9  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddSuccess(string successMessage)
0x2dafe  leave.s  loc_2DB17
0x2db00  stloc.s  0xE
0x2db02  ldarg.0
0x2db03  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::_tracer
0x2db08  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::DashboardExportErrorMessage
0x2db0d  ldloc.s  0xE
0x2db0f  ldc.i4.3
0x2db10  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x2db15  leave.s  loc_2DB17
0x2db17  ret
```
