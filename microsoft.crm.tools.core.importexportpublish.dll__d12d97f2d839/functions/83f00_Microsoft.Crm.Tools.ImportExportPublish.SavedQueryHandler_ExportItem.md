# Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::ExportItem

- ea: `0x83f00`
- end: `0x842a8`
- name: `Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::ExportItem`
- size: `936`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x391e0`
- `0x39940`
- `0x39d50`
- `0x3a520`
- `0x3a5e0`
- `0x3b380`
- `0x3b3c0`
- `0x4c8d0`
- `0x83f00`
- `0x842b0`
- `0x843d0`
- `0x84410`
- `0x84440`
- `0x96600`
- `0x96660`
- `0x966b0`

## string_xrefs

- `0x8410b`: `layoutxml`
- `0x84119`: `layoutxml`
- `0x84126`: `layoutxml`
- `0x840ab`: `columnsetxml`
- `0x840b9`: `columnsetxml`
- `0x840c5`: `columnsetxml`
- `0x840db`: `fetchxml`
- `0x840e9`: `fetchxml`
- `0x840f5`: `fetchxml`

## pseudocode

```c

```

## disassembly

```asm
0x83f00  ldarg.0
0x83f01  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::metadataCache
0x83f06  ldarg.0
0x83f07  ldfld    int32 Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::objectTypeCode
0x83f0c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x83f11  stloc.0
0x83f12  ldarg.0
0x83f13  ldloc.0
0x83f14  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x83f19  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::RetrieveSavedQueriesForExport(int32 otc)
0x83f1e  stloc.1
0x83f1f  ldarg.1
0x83f20  ldloc.0
0x83f21  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PhysicalName()
0x83f26  ldnull
0x83f27  ldloc.0
0x83f28  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x83f2d  call     class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportExportUtils::GetEntityNodeByName(class [System.Xml]System.Xml.XmlDocument importDocument, string physicalName, [opt] string logicalName, [opt] string platformName)
0x83f32  stloc.2
0x83f33  ldc.i4.0
0x83f34  stloc.3
0x83f35  ldarg.1
0x83f36  ldstr    aSavedqueries// "SavedQueries"
0x83f3b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x83f40  stloc.s  4
0x83f42  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionAwareLocalizedLabelService::.ctor()
0x83f47  stloc.s  5
0x83f49  ldarg.1
0x83f4a  ldstr    aSavedqueries_0// "savedqueries"
0x83f4f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x83f54  stloc.s  6
0x83f56  ldloc.s  4
0x83f58  ldloc.s  6
0x83f5a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x83f5f  pop
0x83f60  ldloc.1
0x83f61  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x83f66  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Item>::.ctor(int32)
0x83f6b  stloc.s  7
0x83f6d  ldc.i4.0
0x83f6e  stloc.s  8
0x83f70  ldloc.1
0x83f71  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x83f76  stloc.s  9
0x83f78  br.s     loc_83FD6
0x83f7a  ldloc.s  9
0x83f7c  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x83f81  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x83f86  stloc.s  0xA
0x83f88  ldloc.s  0xA
0x83f8a  ldstr    aName// "name"
0x83f8f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x83f94  castclass [mscorlib]System.String
0x83f99  ldloc.s  0xA
0x83f9b  ldstr    aSavedqueryid// "savedqueryid"
0x83fa0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x83fa5  unbox.any [mscorlib]System.Guid
0x83faa  stloc.s  0xC
0x83fac  ldloca.s 0xC
0x83fae  constrained. [mscorlib]System.Guid
0x83fb4  callvirt instance string [mscorlib]System.Object::ToString()
0x83fb9  call     string [mscorlib]System.String::Concat(string, string)
0x83fbe  stloc.s  0xB
0x83fc0  ldloc.s  7
0x83fc2  ldloc.s  0xB
0x83fc4  ldloc.s  8
0x83fc6  newobj   instance void Item::.ctor(string key, int32 index)
0x83fcb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Item>::Add(var<u1>)
0x83fd0  ldloc.s  8
0x83fd2  ldc.i4.1
0x83fd3  add
0x83fd4  stloc.s  8
0x83fd6  ldloc.s  9
0x83fd8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x83fdd  brtrue.s loc_83F7A
0x83fdf  leave.s  loc_83FF6
0x83fe1  ldloc.s  9
0x83fe3  isinst   [mscorlib]System.IDisposable
0x83fe8  stloc.s  0xD
0x83fea  ldloc.s  0xD
0x83fec  brfalse.s loc_83FF5
0x83fee  ldloc.s  0xD
0x83ff0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x83ff5  endfinally
0x83ff6  ldloc.s  7
0x83ff8  newobj   instance void ListComparer::.ctor()
0x83ffd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Item>::Sort(class [mscorlib]System.Collections.Generic.IComparer`1<var<u1>>)
0x84002  ldloc.s  7
0x84004  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Item>::GetEnumerator()
0x84009  stloc.s  0xE
0x8400b  br       loc_84256
0x84010  ldloca.s 0xE
0x84012  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Item>::get_Current()
0x84017  stloc.s  0xF
0x84019  ldloc.1
0x8401a  ldloc.s  0xF
0x8401c  callvirt instance int32 Item::get_Index()
0x84021  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x84026  stloc.s  0x10
0x84028  ldc.i4.0
0x84029  ldarg.1
0x8402a  ldstr    aSavedquery_1// "savedquery"
0x8402f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x84034  stloc.s  0x11
0x84036  ldloc.s  0x10
0x84038  ldstr    aSolutionid// "solutionid"
0x8403d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x84042  unbox.any [mscorlib]System.Guid
0x84047  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x8404c  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x84051  or
0x84052  ldloc.s  0x10
0x84054  ldstr    aIsmanaged// "ismanaged"
0x84059  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8405e  unbox.any [mscorlib]System.Boolean
0x84063  stloc.s  0x16
0x84065  ldarg.0
0x84066  ldstr    aSavedquery_0// "savedQuery"
0x8406b  ldarg.1
0x8406c  ldloc.s  0x11
0x8406e  ldloc.s  0x10
0x84070  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be)
0x84075  ldloc.s  0x16
0x84077  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlProperties(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container, bool managed)
0x8407c  ldloc.s  0x10
0x8407e  ldstr    aConditionalfor// "conditionalformatting"
0x84083  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x84088  brtrue.s loc_840A9
0x8408a  ldarg.0
0x8408b  ldarg.1
0x8408c  ldloc.s  0x11
0x8408e  ldstr    aConditionalfor// "conditionalformatting"
0x84093  ldloc.s  0x10
0x84095  ldstr    aConditionalfor// "conditionalformatting"
0x8409a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8409f  castclass [mscorlib]System.String
0x840a4  call     instance void Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::AddCDataNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string nodeValue)
0x840a9  ldloc.s  0x11
0x840ab  ldstr    aColumnsetxml// "columnsetxml"
0x840b0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x840b5  brfalse.s loc_840D9
0x840b7  ldloc.s  0x11
0x840b9  ldstr    aColumnsetxml// "columnsetxml"
0x840be  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x840c3  ldloc.s  0x11
0x840c5  ldstr    aColumnsetxml// "columnsetxml"
0x840ca  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x840cf  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x840d4  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x840d9  ldloc.s  0x11
0x840db  ldstr    aFetchxml// "fetchxml"
0x840e0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x840e5  brfalse.s loc_84109
0x840e7  ldloc.s  0x11
0x840e9  ldstr    aFetchxml// "fetchxml"
0x840ee  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x840f3  ldloc.s  0x11
0x840f5  ldstr    aFetchxml// "fetchxml"
0x840fa  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x840ff  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x84104  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x84109  ldloc.s  0x11
0x8410b  ldstr    aLayoutxml// "layoutxml"
0x84110  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x84115  brfalse.s loc_84147
0x84117  ldloc.s  0x11
0x84119  ldstr    aLayoutxml// "layoutxml"
0x8411e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x84123  ldarg.0
0x84124  ldloc.s  0x11
0x84126  ldstr    aLayoutxml// "layoutxml"
0x8412b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x84130  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x84135  call     instance string Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::RemoveGridImageProviderWebResource(string layoutXml)
0x8413a  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x8413f  ldarg.0
0x84140  ldloc.s  0x11
0x84142  call     instance void Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::RemoveObjectTypeCodeFromGridXml(class [System.Xml]System.Xml.XmlElement savedQueryNode)
0x84147  ldloc.s  0x10
0x84149  ldstr    aSavedqueryid// "savedqueryid"
0x8414e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x84153  unbox.any [mscorlib]System.Guid
0x84158  ldstr    aSavedquery// "SavedQuery"
0x8415d  ldarg.0
0x8415e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::_context
0x84163  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x84168  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x8416d  stloc.s  0x12
0x8416f  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LabelCollectionGenerator::.ctor()
0x84174  stloc.s  0x13
0x84176  ldloc.s  5
0x84178  ldloc.s  0x13
0x8417a  ldloc.s  0x12
0x8417c  ldstr    aName// "name"
0x84181  ldc.i4.0
0x84182  ldarg.0
0x84183  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::_context
0x84188  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionAwareLocalizedLabelService::RetrieveLocLabelsIncludeDeleted(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ILocalizedLabelGenerator, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, string, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x8418d  ldloc.s  0x13
0x8418f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LabelCollectionGenerator::GetLabel()
0x84194  stloc.s  0x14
0x84196  ldarg.0
0x84197  ldarg.1
0x84198  ldloc.s  0x11
0x8419a  ldloc.s  0x14
0x8419c  ldstr    aLocalizedname// "LocalizedName"
0x841a1  ldstr    aLocalizednames_1// "LocalizedNames"
0x841a6  ldc.i4.1
0x841a7  ldnull
0x841a8  ldnull
0x841a9  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddLabels(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode rootNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection labelCollection, string singularName, string pluralName, bool force, [opt] string defaultLabel, [opt] string baseLanguage)
0x841ae  or
0x841af  ldloc.s  5
0x841b1  ldloc.s  0x13
0x841b3  ldloc.s  0x12
0x841b5  ldstr    aDescription// "description"
0x841ba  ldc.i4.0
0x841bb  ldarg.0
0x841bc  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::_context
0x841c1  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionAwareLocalizedLabelService::RetrieveLocLabelsIncludeDeleted(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ILocalizedLabelGenerator, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, string, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x841c6  ldloc.s  0x13
0x841c8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LabelCollectionGenerator::GetLabel()
0x841cd  stloc.s  0x15
0x841cf  ldarg.0
0x841d0  ldarg.1
0x841d1  ldloc.s  0x11
0x841d3  ldloc.s  0x15
0x841d5  ldstr    aDescription_0// "Description"
0x841da  ldstr    aDescriptions// "Descriptions"
0x841df  ldc.i4.1
0x841e0  ldnull
0x841e1  ldnull
0x841e2  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddLabels(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode rootNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection labelCollection, string singularName, string pluralName, bool force, [opt] string defaultLabel, [opt] string baseLanguage)
0x841e7  or
0x841e8  brtrue.s loc_841F2
0x841ea  ldarg.0
0x841eb  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::_exportDeltaOverride
0x841f0  brfalse.s loc_84200
0x841f2  ldloc.s  6
0x841f4  ldloc.s  0x11
0x841f6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x841fb  pop
0x841fc  ldc.i4.1
0x841fd  stloc.3
0x841fe  br.s     loc_84256
0x84200  ldarg.1
0x84201  ldarg.0
0x84202  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::_context
0x84207  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::ExportAsUnmodified(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8420c  brfalse.s loc_84256
0x8420e  ldarg.0
0x8420f  ldloc.0
0x84210  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x84215  ldarg.0
0x84216  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::_context
0x8421b  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::IsIncludeSelfAndAllSubcomponentsInComponentTable(valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x84220  brtrue.s loc_84256
0x84222  ldarg.1
0x84223  ldstr    aUnmodified// "unmodified"
0x84228  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x8422d  stloc.s  0x17
0x8422f  ldloc.s  0x17
0x84231  ldstr    a1// "1"
0x84236  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x8423b  ldloc.s  0x11
0x8423d  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x84242  ldloc.s  0x17
0x84244  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x84249  pop
0x8424a  ldloc.s  6
0x8424c  ldloc.s  0x11
0x8424e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x84253  pop
0x84254  ldc.i4.1
0x84255  stloc.3
0x84256  ldloca.s 0xE
0x84258  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Item>::MoveNext()
0x8425d  brtrue   loc_84010
0x84262  leave.s  loc_84272
0x84264  ldloca.s 0xE
0x84266  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Item>
0x8426c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x84271  endfinally
0x84272  ldloc.3
0x84273  brfalse.s loc_8427E
0x84275  ldloc.2
0x84276  ldloc.s  4
0x84278  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x8427d  pop
0x8427e  ldarg.0
0x8427f  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::tracer
0x84284  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::QueryExportSuccessMessage
0x84289  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddSuccess(string successMessage)
0x8428e  leave.s  loc_842A7
0x84290  stloc.s  0x18
0x84292  ldarg.0
0x84293  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::tracer
0x84298  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::QueryExportErrorMessage
0x8429d  ldloc.s  0x18
0x8429f  ldc.i4.3
  ... truncated ...
```
