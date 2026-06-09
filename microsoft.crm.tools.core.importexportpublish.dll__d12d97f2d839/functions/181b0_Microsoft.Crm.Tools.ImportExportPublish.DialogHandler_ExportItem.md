# Microsoft.Crm.Tools.ImportExportPublish.DialogHandler::ExportItem

- ea: `0x181b0`
- end: `0x1847f`
- name: `Microsoft.Crm.Tools.ImportExportPublish.DialogHandler::ExportItem`
- size: `719`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x181b0`
- `0x185b0`
- `0x186a0`
- `0x391e0`
- `0x39940`
- `0x39d50`
- `0x3a5e0`
- `0x3b380`
- `0x3b3c0`
- `0x4d4a0`
- `0x7bc70`

## string_xrefs

- `0x18355`: `FormXml`
- `0x18366`: `FormXml`
- `0x18377`: `FormXml`
- `0x18397`: `FormXml`

## pseudocode

```c

```

## disassembly

```asm
0x181b0  ldarg.0
0x181b1  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.DialogHandler::_solutionComponentDialogSet
0x181b6  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x181bb  ldc.i4.0
0x181bc  bgt.s    loc_181BF
0x181be  ret
0x181bf  ldarg.1
0x181c0  call     bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::IsManagedSolutionInDocument(class [System.Xml]System.Xml.XmlDocument xmlDocument)
0x181c5  stloc.0
0x181c6  ldarg.1
0x181c7  ldstr    aDialogs// "Dialogs"
0x181cc  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x181d1  stloc.1
0x181d2  ldc.i4.1
0x181d3  stloc.2
0x181d4  ldnull
0x181d5  stloc.3
0x181d6  ldarg.0
0x181d7  ldloc.2
0x181d8  ldloc.3
0x181d9  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.DialogHandler::RetrieveDialogsForExport(int32 pageNumber, string pagingCookie)
0x181de  stloc.s  4
0x181e0  ldloc.s  4
0x181e2  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x181e7  stloc.s  5
0x181e9  br       loc_183FD
0x181ee  ldloc.s  5
0x181f0  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x181f5  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x181fa  stloc.s  6
0x181fc  ldc.i4.0
0x181fd  stloc.s  7
0x181ff  ldloc.s  6
0x18201  ldstr    aFormid// "formid"
0x18206  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1820b  unbox.any [mscorlib]System.Guid
0x18210  stloc.s  8
0x18212  ldarg.0
0x18213  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.DialogHandler::_solutionComponentDialogSet
0x18218  ldloc.s  8
0x1821a  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x1821f  brfalse  loc_183FD
0x18224  ldarg.0
0x18225  ldloc.s  6
0x18227  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.DialogHandler::DoesDialogNeedToBeSkippedForExportToTargetVersion(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity dialog)
0x1822c  brtrue   loc_183FD
0x18231  ldarg.1
0x18232  ldstr    aDialog// "Dialog"
0x18237  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x1823c  stloc.s  9
0x1823e  ldarg.0
0x1823f  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::_exportDeltaOverride
0x18244  brtrue.s loc_18272
0x18246  ldloc.s  6
0x18248  ldstr    aSolutionid// "solutionid"
0x1824d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x18252  unbox.any [mscorlib]System.Guid
0x18257  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x1825c  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x18261  brtrue.s loc_18272
0x18263  ldloc.s  6
0x18265  ldarg.0
0x18266  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.DialogHandler::_context
0x1826b  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormLabelHelper::HaveLabelsOfFormXmlChanged(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x18270  brfalse.s loc_18275
0x18272  ldc.i4.1
0x18273  stloc.s  7
0x18275  ldloc.s  8
0x18277  ldstr    aSystemform_0// "SystemForm"
0x1827c  ldarg.0
0x1827d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.DialogHandler::_context
0x18282  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x18287  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x1828c  stloc.s  0xA
0x1828e  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionAwareLocalizedLabelService::.ctor()
0x18293  stloc.s  0xB
0x18295  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LabelCollectionGenerator::.ctor()
0x1829a  stloc.s  0xC
0x1829c  ldloc.s  0xB
0x1829e  ldloc.s  0xC
0x182a0  ldloc.s  0xA
0x182a2  ldstr    aName// "name"
0x182a7  ldc.i4.0
0x182a8  ldarg.0
0x182a9  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.DialogHandler::_context
0x182ae  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionAwareLocalizedLabelService::RetrieveLocLabelsIncludeDeleted(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ILocalizedLabelGenerator, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, string, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x182b3  ldloc.s  0xC
0x182b5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LabelCollectionGenerator::GetLabel()
0x182ba  stloc.s  0xD
0x182bc  ldloc.s  7
0x182be  ldarg.0
0x182bf  ldarg.1
0x182c0  ldloc.s  9
0x182c2  ldloc.s  0xD
0x182c4  ldstr    aLocalizedname// "LocalizedName"
0x182c9  ldstr    aLocalizednames_1// "LocalizedNames"
0x182ce  ldc.i4.1
0x182cf  ldnull
0x182d0  ldnull
0x182d1  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddLabels(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode rootNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection labelCollection, string singularName, string pluralName, bool force, [opt] string defaultLabel, [opt] string baseLanguage)
0x182d6  or
0x182d7  stloc.s  7
0x182d9  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LabelCollectionGenerator::.ctor()
0x182de  stloc.s  0xC
0x182e0  ldloc.s  0xB
0x182e2  ldloc.s  0xC
0x182e4  ldloc.s  0xA
0x182e6  ldstr    aDescription// "description"
0x182eb  ldc.i4.0
0x182ec  ldarg.0
0x182ed  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.DialogHandler::_context
0x182f2  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionAwareLocalizedLabelService::RetrieveLocLabelsIncludeDeleted(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ILocalizedLabelGenerator, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, string, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x182f7  ldloc.s  0xC
0x182f9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LabelCollectionGenerator::GetLabel()
0x182fe  stloc.s  0xE
0x18300  ldloc.s  7
0x18302  ldarg.0
0x18303  ldarg.1
0x18304  ldloc.s  9
0x18306  ldloc.s  0xE
0x18308  ldstr    aDescription_0// "Description"
0x1830d  ldstr    aDescriptions// "Descriptions"
0x18312  ldc.i4.1
0x18313  ldnull
0x18314  ldnull
0x18315  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddLabels(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode rootNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection labelCollection, string singularName, string pluralName, bool force, [opt] string defaultLabel, [opt] string baseLanguage)
0x1831a  or
0x1831b  stloc.s  7
0x1831d  ldloc.s  7
0x1831f  brfalse  loc_183AF
0x18324  ldloc.1
0x18325  ldloc.s  9
0x18327  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x1832c  pop
0x1832d  ldarg.0
0x1832e  ldstr    aDialog// "Dialog"
0x18333  ldarg.1
0x18334  ldloc.s  9
0x18336  ldloc.s  6
0x18338  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be)
0x1833d  ldloc.s  6
0x1833f  ldstr    aIsmanaged// "ismanaged"
0x18344  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x18349  unbox.any [mscorlib]System.Boolean
0x1834e  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlProperties(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container, bool managed)
0x18353  ldloc.s  9
0x18355  ldstr    aFormxml// "FormXml"
0x1835a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x1835f  brfalse  loc_183FD
0x18364  ldloc.s  9
0x18366  ldstr    aFormxml// "FormXml"
0x1836b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x18370  ldstr    aFormsTypeDialo// "<forms type='dialog'>"
0x18375  ldloc.s  9
0x18377  ldstr    aFormxml// "FormXml"
0x1837c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x18381  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x18386  ldstr    aForms// "</forms>"
0x1838b  call     string [mscorlib]System.String::Concat(string, string, string)
0x18390  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x18395  ldloc.s  9
0x18397  ldstr    aFormxml// "FormXml"
0x1839c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x183a1  ldloc.0
0x183a2  ldarg.0
0x183a3  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.DialogHandler::_context
0x183a8  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportExportFormXmlUtils::ProcessRoleIds(class [System.Xml]System.Xml.XmlElement formXml, bool removeNonRootBURoles, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x183ad  br.s     loc_183FD
0x183af  ldarg.1
0x183b0  ldarg.0
0x183b1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.DialogHandler::_context
0x183b6  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::ExportAsUnmodified(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x183bb  brfalse.s loc_183FD
0x183bd  ldloc.1
0x183be  ldloc.s  9
0x183c0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x183c5  pop
0x183c6  ldarg.0
0x183c7  ldstr    aUnmodifieddial// "UnmodifiedDialog"
0x183cc  ldarg.1
0x183cd  ldloc.s  9
0x183cf  ldloc.s  6
0x183d1  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be)
0x183d6  ldloc.s  6
0x183d8  ldstr    aIsmanaged// "ismanaged"
0x183dd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x183e2  unbox.any [mscorlib]System.Boolean
0x183e7  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlProperties(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container, bool managed)
0x183ec  ldloc.s  9
0x183ee  ldstr    aUnmodified// "unmodified"
0x183f3  ldstr    a1// "1"
0x183f8  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x183fd  ldloc.s  5
0x183ff  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x18404  brtrue   loc_181EE
0x18409  leave.s  loc_18420
0x1840b  ldloc.s  5
0x1840d  isinst   [mscorlib]System.IDisposable
0x18412  stloc.s  0xF
0x18414  ldloc.s  0xF
0x18416  brfalse.s loc_1841F
0x18418  ldloc.s  0xF
0x1841a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1841f  endfinally
0x18420  ldloc.s  4
0x18422  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_MoreRecords()
0x18427  brfalse.s loc_1843A
0x18429  ldloc.2
0x1842a  ldc.i4.1
0x1842b  add
0x1842c  stloc.2
0x1842d  ldloc.s  4
0x1842f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_PagingCookie()
0x18434  stloc.3
0x18435  br       loc_181D6
0x1843a  ldloc.1
0x1843b  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x18440  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x18445  ldc.i4.0
0x18446  ble.s    loc_18465
0x18448  ldarg.1
0x18449  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x1844e  ldloc.1
0x1844f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x18454  pop
0x18455  ldarg.0
0x18456  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.DialogHandler::_tracer
0x1845b  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::DialogExportSuccessMessage
0x18460  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddSuccess(string successMessage)
0x18465  leave.s  loc_1847E
0x18467  stloc.s  0x10
0x18469  ldarg.0
0x1846a  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.DialogHandler::_tracer
0x1846f  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::DialogExportErrorMessage
0x18474  ldloc.s  0x10
0x18476  ldc.i4.3
0x18477  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x1847c  leave.s  loc_1847E
0x1847e  ret
```
