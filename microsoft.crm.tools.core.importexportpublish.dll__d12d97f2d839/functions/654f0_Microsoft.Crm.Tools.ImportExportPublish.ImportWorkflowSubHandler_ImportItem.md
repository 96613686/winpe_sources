# Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandler::ImportItem

- ea: `0x654f0`
- end: `0x66000`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandler::ImportItem`
- size: `2832`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x4dee0`
- `0x4df00`
- `0x4df10`
- `0x508e0`
- `0x511e0`
- `0x520f0`
- `0x52610`
- `0x63db0`
- `0x63df0`
- `0x64f10`
- `0x64f30`
- `0x64f50`
- `0x64f70`
- `0x64f90`
- `0x64fb0`
- `0x65000`
- `0x651c0`
- `0x654f0`
- `0x66020`
- `0x660d0`
- `0x66120`
- `0x661b0`
- `0x686f0`

## string_xrefs

- `0x657d0`: `TriggerOnUpdateAttributeList`
- `0x65c4d`: `triggeronupdateattributelist`
- `0x65ee0`: `triggeronupdateattributelist`
- `0x65ef5`: `triggeronupdateattributelist`
- `0x6579a`: `TriggerOnCreate`
- `0x65b6d`: `triggeroncreate`
- `0x65e0c`: `triggeroncreate`
- `0x65788`: `TriggerOnDelete`
- `0x65ba5`: `triggerondelete`
- `0x65e41`: `triggerondelete`
- `0x657ac`: `AsyncAutodelete`
- `0x65bdd`: `asyncautodelete`
- `0x65e76`: `asyncautodelete`

## pseudocode

```c

```

## disassembly

```asm
0x654f0  ldstr    asc_9A18C// ""
0x654f5  stloc.0
0x654f6  ldsfld   string [mscorlib]System.String::Empty
0x654fb  stloc.1
0x654fc  ldarg.0
0x654fd  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_Helper()
0x65502  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::get_MetadataCache()
0x65507  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowService::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache)
0x6550c  stloc.2
0x6550d  ldarg.0
0x6550e  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_Helper()
0x65513  ldarg.0
0x65514  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_WorkflowNode()
0x65519  ldstr    aName_1// "Name"
0x6551e  ldstr    aName// "name"
0x65523  ldloca.s 3
0x65525  callvirt instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::TryGetLocalizedLabelForImportXmlNodeAttribute(class [System.Xml]System.Xml.XmlNode importXmlNode, string xmlNodeAttributeName, string localizedLabelAttributeName, [out] string& labelForAttributeValue)
0x6552a  brfalse.s loc_6552E
0x6552c  ldloc.3
0x6552d  stloc.0
0x6552e  ldarg.0
0x6552f  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_WorkflowNode()
0x65534  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x65539  ldstr    aWorkflowid// "WorkflowId"
0x6553e  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x65543  brfalse.s loc_65560
0x65545  ldarg.0
0x65546  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_WorkflowNode()
0x6554b  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x65550  ldstr    aWorkflowid// "WorkflowId"
0x65555  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x6555a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x6555f  stloc.1
0x65560  ldarg.0
0x65561  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_WorkflowNode()
0x65566  ldstr    aPrimaryentity// "PrimaryEntity"
0x6556b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x65570  stloc.s  4
0x65572  ldarg.0
0x65573  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_Helper()
0x65578  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::get_MetadataCache()
0x6557d  ldloc.s  4
0x6557f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x65584  ldc.i4.2
0x65585  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x6558a  stloc.s  5
0x6558c  ldloc.s  5
0x6558e  brtrue.s loc_655B7
0x65590  ldarg.0
0x65591  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_Helper()
0x65596  callvirt instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::get_LookupNameMatches()
0x6559b  brfalse.s loc_655B7
0x6559d  ldarg.0
0x6559e  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_Helper()
0x655a3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::get_MetadataCache()
0x655a8  ldloc.s  4
0x655aa  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x655af  ldc.i4.1
0x655b0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x655b5  stloc.s  5
0x655b7  ldarg.0
0x655b8  ldloc.2
0x655b9  ldarg.0
0x655ba  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_Workflowid()
0x655bf  ldloc.0
0x655c0  ldloc.s  5
0x655c2  call     instance class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowEntity Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandler::CheckUpdateWorkflow(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowService w, string id, string name, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata emd)
0x655c7  stloc.s  6
0x655c9  ldarg.0
0x655ca  ldarg.0
0x655cb  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_WorkflowNode()
0x655d0  ldloc.s  6
0x655d2  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::AddUnmodifiedWorkflowToSolutionComponent(class [System.Xml]System.Xml.XmlNode workflowNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowEntity workflowToUpdate)
0x655d7  brfalse.s loc_655DE
0x655d9  leave    loc_65FFF
0x655de  ldloc.s  6
0x655e0  brfalse  loc_6566F
0x655e5  ldloc.s  6
0x655e7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x655ec  ldstr    aStatuscode// "statuscode"
0x655f1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x655f6  brfalse.s loc_6566F
0x655f8  ldc.i4.2
0x655f9  ldloc.s  6
0x655fb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x65600  ldstr    aStatuscode// "statuscode"
0x65605  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x6560a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x6560f  unbox.any [mscorlib]System.Int32
0x65614  bne.un.s loc_6566F
0x65616  ldarg.0
0x65617  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::_parent
0x6561c  brfalse.s loc_65646
0x6561e  ldarg.0
0x6561f  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::_parent
0x65624  ldarg.0
0x65625  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetParameterXPath()
0x6562a  ldstr    aWarning// "warning"
0x6562f  ldc.i4   0x80045042
0x65634  ldc.i4.0
0x65635  newarr   [mscorlib]System.Object
0x6563a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x6563f  ldc.i4.0
0x65640  ldc.i4.0
0x65641  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::UpdateProgress(string path, string result, class [mscorlib]System.Exception ex, bool isProcessed, [opt] int32 errorCode)
0x65646  ldloc.1
0x65647  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x6564c  ldstr    aWorkflow// "Workflow"
0x65651  ldarg.0
0x65652  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_Context()
0x65657  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6565c  stloc.s  0x1F
0x6565e  ldloc.2
0x6565f  ldloc.s  0x1F
0x65661  ldc.i4.0
0x65662  ldc.i4.m1
0x65663  ldarg.0
0x65664  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_Context()
0x65669  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::SetState(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, int32, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6566e  pop
0x6566f  ldarg.0
0x65670  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_Context()
0x65675  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x6567a  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowEntity::.ctor(valuetype [mscorlib]System.Guid)
0x6567f  stloc.s  7
0x65681  ldarg.0
0x65682  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_WorkflowNode()
0x65687  ldstr    aScope// "Scope"
0x6568c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x65691  brtrue.s loc_65696
0x65693  ldc.i4.1
0x65694  br.s     loc_656B5
0x65696  ldarg.0
0x65697  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_WorkflowNode()
0x6569c  ldstr    aScope// "Scope"
0x656a1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x656a6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x656ab  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x656b0  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x656b5  stloc.s  8
0x656b7  ldloc.s  7
0x656b9  ldstr    aScope_0// "scope"
0x656be  ldloc.s  8
0x656c0  box      [mscorlib]System.Int32
0x656c5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x656ca  ldarg.0
0x656cb  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_Helper()
0x656d0  ldarg.0
0x656d1  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_WorkflowNode()
0x656d6  ldstr    aDescription_0// "Description"
0x656db  ldstr    aDescription// "description"
0x656e0  ldloca.s 9
0x656e2  callvirt instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::TryGetLocalizedLabelForImportXmlNodeAttribute(class [System.Xml]System.Xml.XmlNode importXmlNode, string xmlNodeAttributeName, string localizedLabelAttributeName, [out] string& labelForAttributeValue)
0x656e7  brfalse.s loc_656F7
0x656e9  ldloc.s  7
0x656eb  ldstr    aDescription// "description"
0x656f0  ldloc.s  9
0x656f2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x656f7  ldloc.s  7
0x656f9  ldstr    aName// "name"
0x656fe  ldloc.0
0x656ff  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x65704  ldarg.0
0x65705  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_WorkflowNode()
0x6570a  ldstr    aSubprocess// "Subprocess"
0x6570f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x65714  stloc.s  0xA
0x65716  ldarg.0
0x65717  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_WorkflowNode()
0x6571c  ldstr    aCategory_0// "Category"
0x65721  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x65726  stloc.s  0xB
0x65728  ldarg.0
0x65729  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_WorkflowNode()
0x6572e  ldstr    aMode// "Mode"
0x65733  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x65738  stloc.s  0xC
0x6573a  ldarg.0
0x6573b  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_WorkflowNode()
0x65740  ldstr    aLanguagecode_0// "LanguageCode"
0x65745  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x6574a  stloc.s  0xD
0x6574c  ldarg.0
0x6574d  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_WorkflowNode()
0x65752  ldstr    aType// "Type"
0x65757  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x6575c  stloc.s  0xE
0x6575e  ldarg.0
0x6575f  ldloc.s  0xB
0x65761  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandler::SetOnDemandNode(class [System.Xml]System.Xml.XmlNode workflowCategoryNode)
0x65766  stloc.s  0xF
0x65768  ldloc.s  7
0x6576a  ldstr    aFormid// "formid"
0x6576f  ldarg.0
0x65770  ldarg.0
0x65771  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_WorkflowNode()
0x65776  ldloc.s  0xB
0x65778  call     instance object Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandler::SetFormIdForProcessAction(class [System.Xml]System.Xml.XmlNode workflowNode, class [System.Xml]System.Xml.XmlNode workflowCategoryNode)
0x6577d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x65782  ldarg.0
0x65783  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_WorkflowNode()
0x65788  ldstr    aTriggerondelet// "TriggerOnDelete"
0x6578d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x65792  stloc.s  0x10
0x65794  ldarg.0
0x65795  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_WorkflowNode()
0x6579a  ldstr    aTriggeroncreat// "TriggerOnCreate"
0x6579f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x657a4  stloc.s  0x11
0x657a6  ldarg.0
0x657a7  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_WorkflowNode()
0x657ac  ldstr    aAsyncautodelet// "AsyncAutodelete"
0x657b1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x657b6  stloc.s  0x12
0x657b8  ldarg.0
0x657b9  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_WorkflowNode()
0x657be  ldstr    aSyncworkflowlo// "SyncWorkflowLogOnFailure"
0x657c3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x657c8  stloc.s  0x13
0x657ca  ldarg.0
0x657cb  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_WorkflowNode()
0x657d0  ldstr    aTriggeronupdat// "TriggerOnUpdateAttributeList"
0x657d5  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x657da  stloc.s  0x14
0x657dc  ldarg.0
0x657dd  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_WorkflowNode()
0x657e2  ldstr    aIscustomizable_0// "IsCustomizable"
0x657e7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x657ec  stloc.s  0x15
0x657ee  ldarg.0
0x657ef  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_WorkflowNode()
0x657f4  ldstr    aXamlfilename// "XamlFileName"
0x657f9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x657fe  stloc.s  0x16
0x65800  ldarg.0
0x65801  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_WorkflowNode()
0x65806  ldstr    aIntroducedvers_0// "IntroducedVersion"
0x6580b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x65810  stloc.s  0x17
0x65812  ldarg.0
0x65813  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_WorkflowNode()
0x65818  ldstr    aStatecode_0// "StateCode"
0x6581d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x65822  stloc.s  0x18
0x65824  ldloc.s  0x18
0x65826  brfalse.s loc_6584A
0x65828  ldloc.s  7
0x6582a  ldstr    aStatecode// "statecode"
0x6582f  ldloc.s  0x18
0x65831  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x65836  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6583b  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x65840  box      [mscorlib]System.Int32
0x65845  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6584a  ldarg.0
0x6584b  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_WorkflowNode()
0x65850  ldstr    aStatuscode_0// "StatusCode"
0x65855  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x6585a  stloc.s  0x19
0x6585c  ldloc.s  0x19
0x6585e  brfalse.s loc_65882
0x65860  ldloc.s  7
0x65862  ldstr    aStatuscode// "statuscode"
0x65867  ldloc.s  0x19
0x65869  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6586e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x65873  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x65878  box      [mscorlib]System.Int32
0x6587d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x65882  ldloc.s  7
0x65884  ldstr    aWorkflowid_0// "workflowid"
0x65889  ldarg.0
0x6588a  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_Workflowid()
0x6588f  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x65894  box      [mscorlib]System.Guid
0x65899  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6589e  ldarg.0
0x6589f  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_WorkflowNode()
0x658a4  ldstr    aSdkmessageid_0// "SdkMessageId"
0x658a9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x658ae  stloc.s  0x1A
0x658b0  ldloc.s  0x1A
0x658b2  brfalse.s loc_658D1
0x658b4  ldloc.s  7
0x658b6  ldstr    aSdkmessageid// "sdkmessageid"
0x658bb  ldloc.s  0x1A
0x658bd  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x658c2  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x658c7  box      [mscorlib]System.Guid
0x658cc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x658d1  ldarg.0
0x658d2  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandlerBase::get_WorkflowNode()
0x658d7  ldstr    aUniquename_0// "UniqueName"
0x658dc  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x658e1  stloc.s  0x1B
0x658e3  ldloc.s  7
0x658e5  ldstr    aUniquename// "uniquename"
0x658ea  ldloc.s  0x1B
0x658ec  brfalse.s loc_658F7
0x658ee  ldloc.s  0x1B
  ... truncated ...
```
