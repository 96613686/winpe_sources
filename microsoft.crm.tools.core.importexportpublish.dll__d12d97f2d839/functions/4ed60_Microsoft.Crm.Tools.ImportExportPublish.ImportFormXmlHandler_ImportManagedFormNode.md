# Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::ImportManagedFormNode

- ea: `0x4ed60`
- end: `0x4f285`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::ImportManagedFormNode`
- size: `1317`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x4e370`
- `0x4ec40`

## callees

- `0x4ed60`
- `0x4f290`
- `0x4f380`
- `0x4f440`
- `0x4f540`
- `0x4fd90`
- `0x4fdb0`
- `0x4ff60`
- `0x4ff70`
- `0x50510`

## string_xrefs

- `0x4ee15`: `formxml`
- `0x4ee8c`: `formxml`
- `0x4f011`: `formxml`
- `0x4f215`: `formxml`
- `0x4f259`: `formxml`

## pseudocode

```c

```

## disassembly

```asm
0x4ed60  ldarg.0
0x4ed61  ldarg.s  4
0x4ed63  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::GetIdFromFormNode(class [System.Xml]System.Xml.XmlNode formNode)
0x4ed68  stloc.0
0x4ed69  ldloc.0
0x4ed6a  ldarg.0
0x4ed6b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::context
0x4ed70  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormSolutionUtility::IsFormInDeletedState(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4ed75  stloc.1
0x4ed76  ldloc.0
0x4ed77  ldarg.0
0x4ed78  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::context
0x4ed7d  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormSolutionUtility::IsExistingForm(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4ed82  stloc.2
0x4ed83  ldarg.0
0x4ed84  ldarg.s  4
0x4ed86  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::GetFormXmlNodeFromSystemFormNode(class [System.Xml]System.Xml.XmlNode systemFormNode)
0x4ed8b  stloc.3
0x4ed8c  ldloc.3
0x4ed8d  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormSolutionUtility::ImportingFullFormXml(class [System.Xml]System.Xml.XPath.IXPathNavigable)
0x4ed92  brfalse.s loc_4EDCD
0x4ed94  ldstr    aCellControl_0// ".//cell/control"
0x4ed99  stloc.s  0xE
0x4ed9b  ldloc.2
0x4ed9c  brfalse.s loc_4EDCD
0x4ed9e  ldloc.3
0x4ed9f  ldloc.s  0xE
0x4eda1  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x4eda6  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x4edab  brtrue.s loc_4EDCD
0x4edad  ldarg.s  4
0x4edaf  ldstr    aFormactivation_0// "FormActivationState"
0x4edb4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x4edb9  brfalse.s loc_4EDCC
0x4edbb  ldarg.0
0x4edbc  ldarg.1
0x4edbd  ldarg.2
0x4edbe  ldarg.3
0x4edbf  ldarg.s  4
0x4edc1  ldarg.s  5
0x4edc3  ldnull
0x4edc4  ldarg.s  6
0x4edc6  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::ImportSystemForm(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormService formService, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ILocalizedLabelService localizedLabelService, class [System.Xml]System.Xml.XmlNode formNode, string formType, string formXmlManaged, string originalBaseLanguage)
0x4edcb  ret
0x4edcc  ret
0x4edcd  ldnull
0x4edce  stloc.s  4
0x4edd0  ldarg.0
0x4edd1  ldarg.s  5
0x4edd3  call     instance int32 Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::ConvertFormTypeToInt(string formType)
0x4edd8  stloc.s  5
0x4edda  leave.s  loc_4EDE2
0x4eddc  pop
0x4eddd  leave    loc_4F284
0x4ede2  ldc.i4.4
0x4ede3  ldloc.s  5
0x4ede5  beq.s    loc_4EDFB
0x4ede7  ldc.i4.s 9
0x4ede9  ldloc.s  5
0x4edeb  beq.s    loc_4EDFB
0x4eded  ldloc.0
0x4edee  ldarg.0
0x4edef  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::context
0x4edf4  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormSolutionUtility::CalculateCustomizationFormXmlDiff(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4edf9  stloc.s  4
0x4edfb  ldnull
0x4edfc  stloc.s  6
0x4edfe  ldnull
0x4edff  stloc.s  7
0x4ee01  ldloc.2
0x4ee02  brfalse.s loc_4EE33
0x4ee04  ldarg.1
0x4ee05  ldloc.0
0x4ee06  ldarg.0
0x4ee07  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::context
0x4ee0c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormService::RetrieveLastPublishedForm(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4ee11  stloc.s  7
0x4ee13  ldloc.s  7
0x4ee15  ldstr    aFormxml_0// "formxml"
0x4ee1a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4ee1f  castclass [mscorlib]System.String
0x4ee24  stloc.s  6
0x4ee26  ldloc.0
0x4ee27  ldarg.0
0x4ee28  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::context
0x4ee2d  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormSolutionUtility::IsSharedPublisherContext(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4ee32  pop
0x4ee33  ldnull
0x4ee34  stloc.s  8
0x4ee36  ldnull
0x4ee37  stloc.s  9
0x4ee39  ldnull
0x4ee3a  stloc.s  0xA
0x4ee3c  ldc.i4.0
0x4ee3d  stloc.s  0xB
0x4ee3f  ldloc.0
0x4ee40  ldarg.0
0x4ee41  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::context
0x4ee46  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormSolutionUtility::IsExistingSolution(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4ee4b  stloc.s  0xC
0x4ee4d  ldarg.0
0x4ee4e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::context
0x4ee53  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x4ee58  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SolutionsHelper::IsInSystemConvertedSolutionUpgradeContext(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x4ee5d  stloc.s  0xD
0x4ee5f  ldloc.s  0xC
0x4ee61  brfalse.s loc_4EEE0
0x4ee63  ldc.i4.s 9
0x4ee65  ldloc.s  5
0x4ee67  bne.un.s loc_4EEE0
0x4ee69  ldloc.s  7
0x4ee6b  brfalse.s loc_4EECA
0x4ee6d  ldloc.s  7
0x4ee6f  ldstr    aSolutionid// "solutionid"
0x4ee74  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4ee79  unbox.any [mscorlib]System.Guid
0x4ee7e  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x4ee83  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4ee88  brfalse.s loc_4EECA
0x4ee8a  ldloc.s  7
0x4ee8c  ldstr    aFormxml_0// "formxml"
0x4ee91  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4ee96  castclass [mscorlib]System.String
0x4ee9b  stloc.s  8
0x4ee9d  ldarg.0
0x4ee9e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::context
0x4eea3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x4eea8  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_OverwriteUnmanagedCustomizations()
0x4eead  brfalse.s loc_4EEC3
0x4eeaf  ldloc.0
0x4eeb0  ldloc.3
0x4eeb1  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x4eeb6  ldarg.0
0x4eeb7  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::context
0x4eebc  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormSolutionUtility::OverwriteActivelayerFormXml(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4eec1  br.s     loc_4EECA
0x4eec3  ldloc.s  8
0x4eec5  stloc.s  0xA
0x4eec7  ldc.i4.1
0x4eec8  stloc.s  0xB
0x4eeca  ldarg.0
0x4eecb  ldarg.1
0x4eecc  ldarg.2
0x4eecd  ldarg.3
0x4eece  ldarg.s  4
0x4eed0  ldarg.s  5
0x4eed2  ldarg.s  6
0x4eed4  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::ImportManagedFormNodeDiff(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormService service, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ILocalizedLabelService localizedLabelService, class [System.Xml]System.Xml.XmlNode formNodeDiff, string formType, string originalBaseLanguage)
0x4eed9  stloc.s  9
0x4eedb  br       loc_4EF8E
0x4eee0  ldloc.s  0xC
0x4eee2  brtrue.s loc_4EEED
0x4eee4  ldloc.s  0xD
0x4eee6  ldloc.2
0x4eee7  and
0x4eee8  brfalse  loc_4EF7D
0x4eeed  ldarg.0
0x4eeee  ldloc.0
0x4eeef  ldloc.3
0x4eef0  ldloc.s  0xD
0x4eef2  ldloca.s 0xA
0x4eef4  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::CalculateFormSolutionBase(valuetype [mscorlib]System.Guid formId, class [System.Xml]System.Xml.XmlNode formNodeDiff, bool isFormFromSystemConvertedSolution, [out] string& managedFormXml)
0x4eef9  stloc.s  0xF
0x4eefb  ldloc.0
0x4eefc  ldloc.s  0xF
0x4eefe  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x4ef03  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4ef08  ldarg.0
0x4ef09  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::context
0x4ef0e  ldloc.s  0xD
0x4ef10  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormSolutionUtility::RecalculateFormSolutionStacks(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x4ef15  stloc.s  9
0x4ef17  ldc.i4.7
0x4ef18  ldloc.s  5
0x4ef1a  beq.s    loc_4EF21
0x4ef1c  ldc.i4.6
0x4ef1d  ldloc.s  5
0x4ef1f  bne.un.s loc_4EF59
0x4ef21  ldloc.s  0xF
0x4ef23  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x4ef28  stloc.s  0x10
0x4ef2a  ldloc.s  0x10
0x4ef2c  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.XmlDiffUtility::MergeConflictsTabWithMainTab(string)
0x4ef31  stloc.s  0x10
0x4ef33  ldarg.s  4
0x4ef35  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x4ef3a  ldstr    aHoldingnode// "holdingNode"
0x4ef3f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x4ef44  dup
0x4ef45  ldloc.s  0x10
0x4ef47  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x4ef4c  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x4ef51  ldc.i4.0
0x4ef52  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x4ef57  stloc.s  0xF
0x4ef59  ldloc.s  0xF
0x4ef5b  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormSolutionUtility::RemoveLabelsNodesFromFormXml(class [System.Xml]System.Xml.XPath.IXPathNavigable)
0x4ef60  ldarg.0
0x4ef61  ldarg.s  4
0x4ef63  ldloc.s  0xF
0x4ef65  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::ReplaceFormXmlNodeInSystemFormNode(class [System.Xml]System.Xml.XmlNode systemFormNode, class [System.Xml]System.Xml.XmlNode newFormXmlNode)
0x4ef6a  ldarg.0
0x4ef6b  ldarg.1
0x4ef6c  ldarg.2
0x4ef6d  ldarg.3
0x4ef6e  ldarg.s  4
0x4ef70  ldarg.s  5
0x4ef72  ldloc.s  0xA
0x4ef74  ldarg.s  6
0x4ef76  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::ImportSystemForm(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormService formService, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ILocalizedLabelService localizedLabelService, class [System.Xml]System.Xml.XmlNode formNode, string formType, string formXmlManaged, string originalBaseLanguage)
0x4ef7b  br.s     loc_4EF8E
0x4ef7d  ldarg.0
0x4ef7e  ldarg.1
0x4ef7f  ldarg.2
0x4ef80  ldarg.3
0x4ef81  ldarg.s  4
0x4ef83  ldarg.s  5
0x4ef85  ldarg.s  6
0x4ef87  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::ImportManagedFormNodeDiff(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormService service, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ILocalizedLabelService localizedLabelService, class [System.Xml]System.Xml.XmlNode formNodeDiff, string formType, string originalBaseLanguage)
0x4ef8c  stloc.s  9
0x4ef8e  ldloc.s  4
0x4ef90  brfalse  loc_4F1EA
0x4ef95  ldloc.s  7
0x4ef97  brfalse  loc_4F1EA
0x4ef9c  ldloc.s  9
0x4ef9e  ldloc.s  4
0x4efa0  ldarg.0
0x4efa1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::context
0x4efa6  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormSolutionUtility::MergeFormXmlDiff(string, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4efab  stloc.s  8
0x4efad  ldc.i4.7
0x4efae  ldloc.s  5
0x4efb0  beq.s    loc_4EFB7
0x4efb2  ldc.i4.6
0x4efb3  ldloc.s  5
0x4efb5  bne.un.s loc_4EFC0
0x4efb7  ldloc.s  8
0x4efb9  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.XmlDiffUtility::MergeConflictsTabWithMainTab(string)
0x4efbe  stloc.s  8
0x4efc0  ldarg.s  4
0x4efc2  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x4efc7  ldstr    aHoldingnode// "holdingNode"
0x4efcc  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x4efd1  stloc.s  0x11
0x4efd3  ldloc.s  0x11
0x4efd5  ldloc.s  8
0x4efd7  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x4efdc  ldloc.s  0x11
0x4efde  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormSolutionUtility::RemoveLabelsNodesFromFormXml(class [System.Xml]System.Xml.XPath.IXPathNavigable)
0x4efe3  ldarg.0
0x4efe4  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::context
0x4efe9  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoSetSolutionToDefaultModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4efee  stloc.s  0x12
0x4eff0  ldarg.0
0x4eff1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::context
0x4eff6  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SystemForm::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4effb  stloc.s  0x13
0x4effd  ldloc.s  0x13
0x4efff  ldstr    aFormid// "formid"
0x4f004  ldloc.0
0x4f005  box      [mscorlib]System.Guid
0x4f00a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4f00f  ldloc.s  0x13
0x4f011  ldstr    aFormxml_0// "formxml"
0x4f016  ldloc.s  0x11
0x4f018  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x4f01d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4f022  ldloc.s  0x13
0x4f024  ldstr    aName// "name"
0x4f029  ldloc.s  7
0x4f02b  ldstr    aName// "name"
0x4f030  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4f035  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4f03a  ldloc.s  0x13
0x4f03c  ldstr    aDescription// "description"
0x4f041  ldloc.s  7
0x4f043  ldstr    aDescription// "description"
0x4f048  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4f04d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4f052  ldc.i4.2
0x4f053  ldloc.s  7
0x4f055  ldstr    aType_0// "type"
0x4f05a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4f05f  unbox.any [mscorlib]System.Int32
0x4f064  bne.un.s loc_4F09E
0x4f066  ldarg.1
0x4f067  ldloc.s  7
0x4f069  ldstr    aObjecttypecode_0// "objecttypecode"
0x4f06e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4f073  unbox.any [mscorlib]System.Int32
0x4f078  ldc.i4.2
0x4f079  ldloc.0
0x4f07a  ldarg.0
0x4f07b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::context
0x4f080  callvirt instance bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormService::HaveOtherActiveForm(int32, int32, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4f085  brtrue.s loc_4F09E
0x4f087  ldloc.s  0x13
0x4f089  ldstr    aFormactivation// "formactivationstate"
0x4f08e  ldc.i4.1
0x4f08f  box      [mscorlib]System.Int32
  ... truncated ...
```
