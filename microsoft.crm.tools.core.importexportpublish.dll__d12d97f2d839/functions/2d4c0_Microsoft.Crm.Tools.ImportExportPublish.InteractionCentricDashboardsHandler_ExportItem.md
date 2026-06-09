# Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::ExportItem

- ea: `0x2d4c0`
- end: `0x2d85b`
- name: `Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::ExportItem`
- size: `923`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x2d4c0`
- `0x2d860`
- `0x2db20`
- `0x2df00`
- `0x2dff0`
- `0x391e0`
- `0x39460`
- `0x39940`
- `0x39d50`
- `0x3a5e0`
- `0x3b380`
- `0x3b3c0`
- `0x4d4a0`
- `0x7bc70`

## string_xrefs

- `0x2d732`: `FormXml`
- `0x2d743`: `FormXml`
- `0x2d754`: `FormXml`
- `0x2d774`: `FormXml`

## pseudocode

```c

```

## disassembly

```asm
0x2d4c0  ldnull
0x2d4c1  stloc.0
0x2d4c2  ldarg.1
0x2d4c3  brfalse.s loc_2D4FF
0x2d4c5  ldarg.1
0x2d4c6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x2d4cb  brfalse.s loc_2D4FF
0x2d4cd  ldarg.1
0x2d4ce  ldstr    aInteractioncen_0// "InteractionCentricDashboards"
0x2d4d3  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlDocument::GetElementsByTagName(string)
0x2d4d8  stloc.1
0x2d4d9  ldloc.1
0x2d4da  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x2d4df  ldc.i4.0
0x2d4e0  ble.s    loc_2D4FF
0x2d4e2  ldloc.1
0x2d4e3  ldc.i4.0
0x2d4e4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x2d4e9  isinst   [System.Xml]System.Xml.XmlElement
0x2d4ee  stloc.0
0x2d4ef  ldloc.0
0x2d4f0  brfalse.s loc_2D4FF
0x2d4f2  ldarg.1
0x2d4f3  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x2d4f8  ldloc.0
0x2d4f9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x2d4fe  pop
0x2d4ff  ldarg.0
0x2d500  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::_solutionComponentDashboardSet
0x2d505  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x2d50a  brtrue.s loc_2D515
0x2d50c  ldarg.0
0x2d50d  ldfld    int32 Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::_objectTypeCode
0x2d512  brtrue.s loc_2D515
0x2d514  ret
0x2d515  ldarg.0
0x2d516  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::_solutionComponentDashboardSet
0x2d51b  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x2d520  brtrue.s loc_2D532
0x2d522  ldarg.0
0x2d523  ldfld    int32 Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::_objectTypeCode
0x2d528  brfalse.s loc_2D532
0x2d52a  ldarg.0
0x2d52b  ldarg.1
0x2d52c  call     instance void Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::ExportEntityDashboardsFromAddAllAssets(class [System.Xml]System.Xml.XmlDocument importDocument)
0x2d531  ret
0x2d532  ldarg.1
0x2d533  call     bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::IsManagedSolutionInDocument(class [System.Xml]System.Xml.XmlDocument xmlDocument)
0x2d538  stloc.2
0x2d539  ldloc.0
0x2d53a  brtrue.s loc_2D548
0x2d53c  ldarg.1
0x2d53d  ldstr    aInteractioncen_0// "InteractionCentricDashboards"
0x2d542  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x2d547  stloc.0
0x2d548  ldc.i4.1
0x2d549  stloc.3
0x2d54a  ldnull
0x2d54b  stloc.s  4
0x2d54d  ldarg.0
0x2d54e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::_context
0x2d553  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2d558  stloc.s  5
0x2d55a  ldarg.0
0x2d55b  ldloc.3
0x2d55c  ldloc.s  4
0x2d55e  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::RetrieveDashboardsForExport(int32 pageNumber, string pagingCookie)
0x2d563  stloc.s  6
0x2d565  ldloc.s  6
0x2d567  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x2d56c  stloc.s  7
0x2d56e  br       loc_2D7DA
0x2d573  ldloc.s  7
0x2d575  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2d57a  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x2d57f  stloc.s  8
0x2d581  ldc.i4.0
0x2d582  stloc.s  9
0x2d584  ldloc.s  8
0x2d586  ldstr    aFormid// "formid"
0x2d58b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2d590  unbox.any [mscorlib]System.Guid
0x2d595  stloc.s  0xA
0x2d597  ldarg.0
0x2d598  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::_solutionComponentDashboardSet
0x2d59d  ldloc.s  0xA
0x2d59f  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x2d5a4  brfalse  loc_2D7DA
0x2d5a9  ldarg.0
0x2d5aa  ldloc.s  8
0x2d5ac  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::DoesDashboardNeedToBeSkippedForExportToTargetVersion(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity dashboard)
0x2d5b1  brtrue   loc_2D7DA
0x2d5b6  ldloc.s  8
0x2d5b8  ldstr    aObjecttypecode_0// "objecttypecode"
0x2d5bd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2d5c2  unbox.any [mscorlib]System.Int32
0x2d5c7  brfalse.s loc_2D60E
0x2d5c9  ldarg.0
0x2d5ca  ldloc.s  8
0x2d5cc  ldstr    aObjecttypecode_0// "objecttypecode"
0x2d5d1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2d5d6  unbox.any [mscorlib]System.Int32
0x2d5db  ldloc.s  5
0x2d5dd  ldloc.s  8
0x2d5df  ldstr    aObjecttypecode_0// "objecttypecode"
0x2d5e4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2d5e9  unbox.any [mscorlib]System.Int32
0x2d5ee  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x2d5f3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x2d5f8  ldarg.0
0x2d5f9  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::get_SolutionId()
0x2d5fe  ldarg.0
0x2d5ff  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::_context
0x2d604  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::IsEntitySingleRootComponent(int32 objectTypeCode, valuetype [mscorlib]System.Guid entityId, valuetype [mscorlib]System.Guid solutionId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext ec)
0x2d609  brtrue   loc_2D7DA
0x2d60e  ldarg.1
0x2d60f  ldstr    aInteractioncen// "InteractionCentricDashboard"
0x2d614  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x2d619  stloc.s  0xB
0x2d61b  ldarg.0
0x2d61c  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::_exportDeltaOverride
0x2d621  brtrue.s loc_2D64F
0x2d623  ldloc.s  8
0x2d625  ldstr    aSolutionid// "solutionid"
0x2d62a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2d62f  unbox.any [mscorlib]System.Guid
0x2d634  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x2d639  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2d63e  brtrue.s loc_2D64F
0x2d640  ldloc.s  8
0x2d642  ldarg.0
0x2d643  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::_context
0x2d648  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormLabelHelper::HaveLabelsOfFormXmlChanged(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2d64d  brfalse.s loc_2D652
0x2d64f  ldc.i4.1
0x2d650  stloc.s  9
0x2d652  ldloc.s  0xA
0x2d654  ldstr    aSystemform_0// "SystemForm"
0x2d659  ldarg.0
0x2d65a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::_context
0x2d65f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x2d664  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x2d669  stloc.s  0xC
0x2d66b  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionAwareLocalizedLabelService::.ctor()
0x2d670  stloc.s  0xD
0x2d672  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LabelCollectionGenerator::.ctor()
0x2d677  stloc.s  0xE
0x2d679  ldloc.s  0xD
0x2d67b  ldloc.s  0xE
0x2d67d  ldloc.s  0xC
0x2d67f  ldstr    aName// "name"
0x2d684  ldc.i4.0
0x2d685  ldarg.0
0x2d686  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::_context
0x2d68b  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionAwareLocalizedLabelService::RetrieveLocLabelsIncludeDeleted(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ILocalizedLabelGenerator, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, string, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2d690  ldloc.s  0xE
0x2d692  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LabelCollectionGenerator::GetLabel()
0x2d697  stloc.s  0xF
0x2d699  ldloc.s  9
0x2d69b  ldarg.0
0x2d69c  ldarg.1
0x2d69d  ldloc.s  0xB
0x2d69f  ldloc.s  0xF
0x2d6a1  ldstr    aLocalizedname// "LocalizedName"
0x2d6a6  ldstr    aLocalizednames_1// "LocalizedNames"
0x2d6ab  ldc.i4.1
0x2d6ac  ldnull
0x2d6ad  ldnull
0x2d6ae  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddLabels(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode rootNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection labelCollection, string singularName, string pluralName, bool force, [opt] string defaultLabel, [opt] string baseLanguage)
0x2d6b3  or
0x2d6b4  stloc.s  9
0x2d6b6  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LabelCollectionGenerator::.ctor()
0x2d6bb  stloc.s  0xE
0x2d6bd  ldloc.s  0xD
0x2d6bf  ldloc.s  0xE
0x2d6c1  ldloc.s  0xC
0x2d6c3  ldstr    aDescription// "description"
0x2d6c8  ldc.i4.0
0x2d6c9  ldarg.0
0x2d6ca  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::_context
0x2d6cf  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionAwareLocalizedLabelService::RetrieveLocLabelsIncludeDeleted(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ILocalizedLabelGenerator, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, string, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2d6d4  ldloc.s  0xE
0x2d6d6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LabelCollectionGenerator::GetLabel()
0x2d6db  stloc.s  0x10
0x2d6dd  ldloc.s  9
0x2d6df  ldarg.0
0x2d6e0  ldarg.1
0x2d6e1  ldloc.s  0xB
0x2d6e3  ldloc.s  0x10
0x2d6e5  ldstr    aDescription_0// "Description"
0x2d6ea  ldstr    aDescriptions// "Descriptions"
0x2d6ef  ldc.i4.1
0x2d6f0  ldnull
0x2d6f1  ldnull
0x2d6f2  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddLabels(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode rootNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection labelCollection, string singularName, string pluralName, bool force, [opt] string defaultLabel, [opt] string baseLanguage)
0x2d6f7  or
0x2d6f8  stloc.s  9
0x2d6fa  ldloc.s  9
0x2d6fc  brfalse  loc_2D78C
0x2d701  ldloc.0
0x2d702  ldloc.s  0xB
0x2d704  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x2d709  pop
0x2d70a  ldarg.0
0x2d70b  ldstr    aInteractioncen// "InteractionCentricDashboard"
0x2d710  ldarg.1
0x2d711  ldloc.s  0xB
0x2d713  ldloc.s  8
0x2d715  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be)
0x2d71a  ldloc.s  8
0x2d71c  ldstr    aIsmanaged// "ismanaged"
0x2d721  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2d726  unbox.any [mscorlib]System.Boolean
0x2d72b  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlProperties(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container, bool managed)
0x2d730  ldloc.s  0xB
0x2d732  ldstr    aFormxml// "FormXml"
0x2d737  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2d73c  brfalse  loc_2D7DA
0x2d741  ldloc.s  0xB
0x2d743  ldstr    aFormxml// "FormXml"
0x2d748  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2d74d  ldstr    aFormsTypeInter// "<forms type='interactioncentricdashboar"...
0x2d752  ldloc.s  0xB
0x2d754  ldstr    aFormxml// "FormXml"
0x2d759  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2d75e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x2d763  ldstr    aForms// "</forms>"
0x2d768  call     string [mscorlib]System.String::Concat(string, string, string)
0x2d76d  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x2d772  ldloc.s  0xB
0x2d774  ldstr    aFormxml// "FormXml"
0x2d779  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2d77e  ldloc.2
0x2d77f  ldarg.0
0x2d780  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::_context
0x2d785  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportExportFormXmlUtils::ProcessRoleIds(class [System.Xml]System.Xml.XmlElement formXml, bool removeNonRootBURoles, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2d78a  br.s     loc_2D7DA
0x2d78c  ldarg.1
0x2d78d  ldarg.0
0x2d78e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::_context
0x2d793  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::ExportAsUnmodified(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2d798  brfalse.s loc_2D7DA
0x2d79a  ldloc.0
0x2d79b  ldloc.s  0xB
0x2d79d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x2d7a2  pop
0x2d7a3  ldarg.0
0x2d7a4  ldstr    aUnmodifieddash// "UnmodifiedDashboard"
0x2d7a9  ldarg.1
0x2d7aa  ldloc.s  0xB
0x2d7ac  ldloc.s  8
0x2d7ae  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be)
0x2d7b3  ldloc.s  8
0x2d7b5  ldstr    aIsmanaged// "ismanaged"
0x2d7ba  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2d7bf  unbox.any [mscorlib]System.Boolean
0x2d7c4  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlProperties(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container, bool managed)
0x2d7c9  ldloc.s  0xB
0x2d7cb  ldstr    aUnmodified// "unmodified"
0x2d7d0  ldstr    a1// "1"
0x2d7d5  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x2d7da  ldloc.s  7
0x2d7dc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2d7e1  brtrue   loc_2D573
0x2d7e6  leave.s  loc_2D7FD
0x2d7e8  ldloc.s  7
0x2d7ea  isinst   [mscorlib]System.IDisposable
0x2d7ef  stloc.s  0x11
0x2d7f1  ldloc.s  0x11
0x2d7f3  brfalse.s loc_2D7FC
0x2d7f5  ldloc.s  0x11
0x2d7f7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2d7fc  endfinally
0x2d7fd  ldloc.3
0x2d7fe  ldc.i4.1
0x2d7ff  add
0x2d800  stloc.3
0x2d801  ldloc.s  6
0x2d803  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_PagingCookie()
0x2d808  stloc.s  4
0x2d80a  ldloc.s  6
0x2d80c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_MoreRecords()
0x2d811  brtrue   loc_2D55A
0x2d816  ldloc.0
0x2d817  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x2d81c  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x2d821  ldc.i4.0
0x2d822  ble.s    loc_2D841
0x2d824  ldarg.1
0x2d825  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x2d82a  ldloc.0
0x2d82b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x2d830  pop
0x2d831  ldarg.0
0x2d832  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::_tracer
0x2d837  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::DashboardExportSuccessMessage
0x2d83c  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddSuccess(string successMessage)
0x2d841  leave.s  loc_2D85A
0x2d843  stloc.s  0x12
0x2d845  ldarg.0
  ... truncated ...
```
