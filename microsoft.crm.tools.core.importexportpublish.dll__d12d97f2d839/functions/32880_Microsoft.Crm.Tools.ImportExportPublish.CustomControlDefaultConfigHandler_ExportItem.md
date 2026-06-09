# Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigHandler::ExportItem

- ea: `0x32880`
- end: `0x32be5`
- name: `Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigHandler::ExportItem`
- size: `869`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x32880`
- `0x32bf0`
- `0x32d60`
- `0x37ad0`
- `0x37c20`
- `0x383c0`
- `0x38770`
- `0x38b70`
- `0x391e0`
- `0x39940`
- `0x3a780`
- `0x3b380`
- `0x3b3c0`
- `0x4c8d0`
- `0x96600`
- `0x96660`
- `0x966b0`

## string_xrefs

- `0x32972`: `CustomControlDefaultConfig`
- `0x329ae`: `CustomControlDefaultConfig`
- `0x32ae1`: `CustomControlDefaultConfig`
- `0x32b35`: `CustomControlDefaultConfig`
- `0x32b4d`: `CustomControlDefaultConfig`
- `0x328e8`: `customcontroldefaultconfigid`
- `0x32aaf`: `ControlDescriptionXML`
- `0x32a87`: `controldescriptionxml`
- `0x328b6`: `CustomControlDefaultConfigs`
- `0x329fa`: `eventsxml`
- `0x32a29`: `/customControlDefaultConfig/formLibraries`
- `0x32a57`: `/customControlDefaultConfig/events`

## pseudocode

```c

```

## disassembly

```asm
0x32880  ldarg.0
0x32881  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigHandler::metadataCache
0x32886  ldarg.0
0x32887  ldfld    int32 Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigHandler::_objectTypeCode
0x3288c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x32891  stloc.0
0x32892  ldarg.0
0x32893  ldarg.0
0x32894  ldfld    int32 Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigHandler::_objectTypeCode
0x32899  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigHandler::RetrieveCustomControlDefaultConfigForExport(int32 otc)
0x3289e  stloc.1
0x3289f  ldarg.1
0x328a0  ldloc.0
0x328a1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PhysicalName()
0x328a6  ldnull
0x328a7  ldloc.0
0x328a8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x328ad  call     class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportExportUtils::GetEntityNodeByName(class [System.Xml]System.Xml.XmlDocument importDocument, string physicalName, [opt] string logicalName, [opt] string platformName)
0x328b2  stloc.2
0x328b3  ldc.i4.0
0x328b4  stloc.3
0x328b5  ldarg.1
0x328b6  ldstr    aCustomcontrold_2// "CustomControlDefaultConfigs"
0x328bb  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x328c0  stloc.s  4
0x328c2  ldloc.1
0x328c3  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x328c8  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Item>::.ctor(int32)
0x328cd  stloc.s  5
0x328cf  ldc.i4.0
0x328d0  stloc.s  6
0x328d2  ldloc.1
0x328d3  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x328d8  stloc.s  7
0x328da  br.s     loc_3291E
0x328dc  ldloc.s  7
0x328de  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x328e3  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x328e8  ldstr    aCustomcontrold_1// "customcontroldefaultconfigid"
0x328ed  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x328f2  unbox.any [mscorlib]System.Guid
0x328f7  stloc.s  9
0x328f9  ldloca.s 9
0x328fb  constrained. [mscorlib]System.Guid
0x32901  callvirt instance string [mscorlib]System.Object::ToString()
0x32906  stloc.s  8
0x32908  ldloc.s  5
0x3290a  ldloc.s  8
0x3290c  ldloc.s  6
0x3290e  newobj   instance void Item::.ctor(string key, int32 index)
0x32913  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Item>::Add(var<u1>)
0x32918  ldloc.s  6
0x3291a  ldc.i4.1
0x3291b  add
0x3291c  stloc.s  6
0x3291e  ldloc.s  7
0x32920  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x32925  brtrue.s loc_328DC
0x32927  leave.s  loc_3293E
0x32929  ldloc.s  7
0x3292b  isinst   [mscorlib]System.IDisposable
0x32930  stloc.s  0xA
0x32932  ldloc.s  0xA
0x32934  brfalse.s loc_3293D
0x32936  ldloc.s  0xA
0x32938  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3293d  endfinally
0x3293e  ldloc.s  5
0x32940  newobj   instance void ListComparer::.ctor()
0x32945  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Item>::Sort(class [mscorlib]System.Collections.Generic.IComparer`1<var<u1>>)
0x3294a  ldloc.s  5
0x3294c  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Item>::GetEnumerator()
0x32951  stloc.s  0xB
0x32953  br       loc_32B79
0x32958  ldloca.s 0xB
0x3295a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Item>::get_Current()
0x3295f  stloc.s  0xC
0x32961  ldloc.1
0x32962  ldloc.s  0xC
0x32964  callvirt instance int32 Item::get_Index()
0x32969  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x3296e  stloc.s  0xD
0x32970  ldc.i4.0
0x32971  ldarg.1
0x32972  ldstr    aCustomcontrold// "CustomControlDefaultConfig"
0x32977  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3297c  stloc.s  0xE
0x3297e  ldloc.s  0xD
0x32980  ldstr    aSolutionid// "solutionid"
0x32985  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3298a  unbox.any [mscorlib]System.Guid
0x3298f  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x32994  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x32999  or
0x3299a  ldloc.s  0xD
0x3299c  ldstr    aIsmanaged// "ismanaged"
0x329a1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x329a6  unbox.any [mscorlib]System.Boolean
0x329ab  stloc.s  0xF
0x329ad  ldarg.0
0x329ae  ldstr    aCustomcontrold// "CustomControlDefaultConfig"
0x329b3  ldarg.1
0x329b4  ldloc.s  0xE
0x329b6  ldloc.s  0xD
0x329b8  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be)
0x329bd  ldloc.s  0xF
0x329bf  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlProperties(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container, bool managed)
0x329c4  ldarg.0
0x329c5  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigHandler::get_ExportToTargetVersionContext()
0x329ca  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::get_TargetVersion()
0x329cf  ldsfld   class [mscorlib]System.Version [Microsoft.Crm]Microsoft.Crm.CrmVersions::AraVersion
0x329d4  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x329d9  brfalse  loc_32A85
0x329de  ldarg.0
0x329df  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigHandler::get_ExportToTargetVersionContext()
0x329e4  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::get_TargetVersion()
0x329e9  ldsfld   class [mscorlib]System.Version [Microsoft.Crm]Microsoft.Crm.CrmVersions::NaosVersion
0x329ee  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x329f3  brfalse  loc_32A85
0x329f8  ldloc.s  0xD
0x329fa  ldstr    aEventsxml// "eventsxml"
0x329ff  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x32a04  castclass [mscorlib]System.String
0x32a09  stloc.s  0x12
0x32a0b  ldloc.s  0x12
0x32a0d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x32a12  brtrue.s loc_32A85
0x32a14  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x32a19  dup
0x32a1a  ldnull
0x32a1b  callvirt instance void [System.Xml]System.Xml.XmlDocument::set_XmlResolver(class [System.Xml]System.Xml.XmlResolver)
0x32a20  dup
0x32a21  ldloc.s  0x12
0x32a23  callvirt instance void [System.Xml]System.Xml.XmlDocument::LoadXml(string)
0x32a28  dup
0x32a29  ldstr    aCustomcontrold_4// "/customControlDefaultConfig/formLibrari"...
0x32a2e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x32a33  stloc.s  0x13
0x32a35  ldloc.s  0x13
0x32a37  brfalse.s loc_32A57
0x32a39  ldloc.s  0x13
0x32a3b  callvirt instance bool [System.Xml]System.Xml.XmlNode::get_HasChildNodes()
0x32a40  brfalse.s loc_32A57
0x32a42  ldarg.1
0x32a43  ldloc.s  0x13
0x32a45  ldc.i4.1
0x32a46  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::ImportNode(class [System.Xml]System.Xml.XmlNode, bool)
0x32a4b  stloc.s  0x15
0x32a4d  ldloc.s  0xE
0x32a4f  ldloc.s  0x15
0x32a51  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x32a56  pop
0x32a57  ldstr    aCustomcontrold_5// "/customControlDefaultConfig/events"
0x32a5c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x32a61  stloc.s  0x14
0x32a63  ldloc.s  0x14
0x32a65  brfalse.s loc_32A85
0x32a67  ldloc.s  0x14
0x32a69  callvirt instance bool [System.Xml]System.Xml.XmlNode::get_HasChildNodes()
0x32a6e  brfalse.s loc_32A85
0x32a70  ldarg.1
0x32a71  ldloc.s  0x14
0x32a73  ldc.i4.1
0x32a74  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::ImportNode(class [System.Xml]System.Xml.XmlNode, bool)
0x32a79  stloc.s  0x16
0x32a7b  ldloc.s  0xE
0x32a7d  ldloc.s  0x16
0x32a7f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x32a84  pop
0x32a85  ldloc.s  0xD
0x32a87  ldstr    aControldescrip_0// "controldescriptionxml"
0x32a8c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x32a91  castclass [mscorlib]System.String
0x32a96  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x32a9b  stloc.s  0x10
0x32a9d  ldarg.1
0x32a9e  ldloc.s  0x10
0x32aa0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x32aa5  ldc.i4.1
0x32aa6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::ImportNode(class [System.Xml]System.Xml.XmlNode, bool)
0x32aab  stloc.s  0x11
0x32aad  ldloc.s  0xE
0x32aaf  ldstr    aControldescrip// "ControlDescriptionXML"
0x32ab4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x32ab9  ldloc.s  0x11
0x32abb  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x32ac0  pop
0x32ac1  ldloc.s  0x11
0x32ac3  ldarg.1
0x32ac4  ldarg.0
0x32ac5  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigHandler::context
0x32aca  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormSolutionUtility::PreProcessCustomControls(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlDocument, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x32acf  ldloc.s  0xE
0x32ad1  ldarg.0
0x32ad2  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigHandler::get_ExportToTargetVersionContext()
0x32ad7  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::UnsupportedCustomControlsExists(class [System.Xml]System.Xml.XmlNode rootNode, class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext exportToTargetVersionContext)
0x32adc  brfalse.s loc_32AF9
0x32ade  ldloc.s  0xE
0x32ae0  ldnull
0x32ae1  ldstr    aCustomcontrold// "CustomControlDefaultConfig"
0x32ae6  ldarg.0
0x32ae7  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigHandler::get_ExportToTargetVersionContext()
0x32aec  ldarg.0
0x32aed  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigHandler::context
0x32af2  call     void Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::RemoveUnsupportedCustomControls(class [System.Xml]System.Xml.XmlNode rootNode, class [mscorlib]System.Action`1<class [System.Xml]System.Xml.XmlNode> actionBeforeDeleteNode, string handlerType, class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext exportToTargetVersionContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x32af7  ldc.i4.1
0x32af8  stloc.3
0x32af9  ldloc.s  0x11
0x32afb  ldstr    aCustomcontrol_1// "//customControl"
0x32b00  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x32b05  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x32b0a  ldc.i4.0
0x32b0b  ble.s    loc_32B63
0x32b0d  ldarg.0
0x32b0e  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigHandler::get_ExportToTargetVersionContext()
0x32b13  ldloc.s  0x11
0x32b15  ldarg.1
0x32b16  ldarg.0
0x32b17  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigHandler::context
0x32b1c  call     void Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::ProcessCustomControlsToExportAs(class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext exportToTargetVersionContext, class [System.Xml]System.Xml.XmlNode systemFormNode, class [System.Xml]System.Xml.XmlDocument containingDocument, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x32b21  ldloc.s  0x11
0x32b23  ldarg.0
0x32b24  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigHandler::get_ExportToTargetVersionContext()
0x32b29  ldarg.0
0x32b2a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigHandler::context
0x32b2f  ldarg.0
0x32b30  ldfld    int32 Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigHandler::_objectTypeCode
0x32b35  ldstr    aCustomcontrold// "CustomControlDefaultConfig"
0x32b3a  call     void Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::AddTypeAttributeForBoundFields(class [System.Xml]System.Xml.XmlNode rootNode, class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext exportToTargetVersionContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, int32 otc, string handlerType)
0x32b3f  ldloc.s  0x11
0x32b41  ldarg.0
0x32b42  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.CustomControlsExportAsHandlerRegistry Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::registryInstance
0x32b47  ldarg.0
0x32b48  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigHandler::get_ExportToTargetVersionContext()
0x32b4d  ldstr    aCustomcontrold// "CustomControlDefaultConfig"
0x32b52  ldarg.0
0x32b53  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigHandler::tracer
0x32b58  ldarg.0
0x32b59  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigHandler::context
0x32b5e  call     void Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::ModifyControlProperties(class [System.Xml]System.Xml.XmlNode rootNode, class Microsoft.Crm.Tools.ImportExportPublish.CustomControlsExportAsHandlerRegistry registryInstance, class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext exportToTargetVersionContext, string handlerType, class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer tracer, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x32b63  brtrue.s loc_32B6D
0x32b65  ldarg.0
0x32b66  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::_exportDeltaOverride
0x32b6b  brfalse.s loc_32B79
0x32b6d  ldloc.s  4
0x32b6f  ldloc.s  0xE
0x32b71  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x32b76  pop
0x32b77  ldc.i4.1
0x32b78  stloc.3
0x32b79  ldloca.s 0xB
0x32b7b  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Item>::MoveNext()
0x32b80  brtrue   loc_32958
0x32b85  leave.s  loc_32B95
0x32b87  ldloca.s 0xB
0x32b89  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Item>
0x32b8f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32b94  endfinally
0x32b95  ldloc.3
0x32b96  brfalse.s loc_32BA1
0x32b98  ldloc.2
0x32b99  ldloc.s  4
0x32b9b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x32ba0  pop
0x32ba1  ldarg.0
0x32ba2  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigHandler::tracer
0x32ba7  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::CustomControlDefaultConfigExportSuccessMessage
0x32bac  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddSuccess(string successMessage)
0x32bb1  leave.s  loc_32BE4
0x32bb3  stloc.s  0x17
0x32bb5  ldarg.0
0x32bb6  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigHandler::tracer
0x32bbb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x32bc0  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::CustomControlDefaultConfigExportErrorMessage
0x32bc5  ldc.i4.1
0x32bc6  newarr   [mscorlib]System.Object
0x32bcb  dup
0x32bcc  ldc.i4.0
0x32bcd  ldloc.s  0x17
0x32bcf  callvirt instance string [mscorlib]System.Exception::get_Message()
0x32bd4  stelem.ref
0x32bd5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x32bda  ldloc.s  0x17
0x32bdc  ldc.i4.3
0x32bdd  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x32be2  leave.s  loc_32BE4
0x32be4  ret
```
