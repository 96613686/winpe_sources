# Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::ImportItem

- ea: `0x54950`
- end: `0x54edd`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::ImportItem`
- size: `1421`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x35d00`
- `0x36310`
- `0x36320`
- `0x4ded0`
- `0x4df00`
- `0x4df10`
- `0x508e0`
- `0x50be0`
- `0x511e0`
- `0x54950`
- `0x550e0`
- `0x551b0`
- `0x553e0`
- `0x554c0`
- `0x554f0`
- `0x55510`
- `0x55530`
- `0x63db0`
- `0x63df0`
- `0x686f0`

## string_xrefs

- `0x54a58`: `PluginAssemblyId`
- `0x54a6b`: `PluginAssemblyId`
- `0x54a89`: `PluginAssemblyId`
- `0x54973`: `PluginAssembly`
- `0x549d2`: `PluginAssembly`
- `0x54c97`: `pluginassemblyid`
- `0x54c9e`: `pluginassemblyid`
- `0x54c3e`: `PluginType`
- `0x54c63`: `PluginType`
- `0x5495f`: `SolutionPluginAssemblies`
- `0x54998`: `ImportPluginAssemblyHandler.ImportItem`
- `0x549c2`: `Re-loaded the MetadataCache for PluginAssemblyImport.`
- `0x54c52`: `PluginTypes`
- `0x54cc5`: `{0}. Error: Plugin: {1} of PluginTypeName: {2} and PluginTypeNode: {3} caused an exception.`
- `0x54e86`: `{0}. Error: Plugin: {1} of PluginTypeName: {2} and PluginTypeNode: {3} caused an exception.`
- `0x54d81`: `{0}. Error: Plugin: {1} of PluginTypeName: {2} caused an exception.`
- `0x54e5c`: `{0}. Error: Plugin: {1} caused an exception.`

## pseudocode

```c

```

## disassembly

```asm
0x54950  ldnull
0x54951  stloc.0
0x54952  ldnull
0x54953  stloc.1
0x54954  ldarg.0
0x54955  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x5495a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x5495f  ldstr    aSolutionplugin// "SolutionPluginAssemblies"
0x54964  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x54969  stloc.2
0x5496a  ldloc.2
0x5496b  brtrue.s loc_54972
0x5496d  leave    loc_54EDC
0x54972  ldloc.2
0x54973  ldstr    aPluginassembly_0// "PluginAssembly"
0x54978  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x5497d  stloc.3
0x5497e  ldloc.3
0x5497f  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x54984  brtrue.s loc_5498B
0x54986  leave    loc_54EDC
0x5498b  ldarg.0
0x5498c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_context
0x54991  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x54996  ldc.i4.s 0x11
0x54998  ldstr    aImportpluginas// "ImportPluginAssemblyHandler.ImportItem"
0x5499d  ldc.i4.0
0x5499e  newarr   [mscorlib]System.Object
0x549a3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x549a8  ldarg.0
0x549a9  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_importHelper
0x549ae  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::get_MetadataCache()
0x549b3  brfalse.s loc_549D2
0x549b5  ldarg.0
0x549b6  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_context
0x549bb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x549c0  ldc.i4.s 0x11
0x549c2  ldstr    aReLoadedTheMet// "Re-loaded the MetadataCache for PluginA"...
0x549c7  ldc.i4.0
0x549c8  newarr   [mscorlib]System.Object
0x549cd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x549d2  ldstr    aPluginassembly_0// "PluginAssembly"
0x549d7  ldarg.0
0x549d8  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_context
0x549dd  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x549e2  stloc.s  4
0x549e4  ldarg.0
0x549e5  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_context
0x549ea  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x549ef  ldstr    aIssolutioninte// "issolutioninternal"
0x549f4  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x549f9  brtrue.s loc_549FE
0x549fb  ldc.i4.0
0x549fc  br.s     loc_54A18
0x549fe  ldarg.0
0x549ff  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_context
0x54a04  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x54a09  ldstr    aIssolutioninte// "issolutioninternal"
0x54a0e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x54a13  unbox.any [mscorlib]System.Boolean
0x54a18  stloc.s  5
0x54a1a  ldloc.3
0x54a1b  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x54a20  stloc.s  6
0x54a22  br       loc_54DE0
0x54a27  ldloc.s  6
0x54a29  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x54a2e  castclass [System.Xml]System.Xml.XmlNode
0x54a33  stloc.s  7
0x54a35  ldarg.0
0x54a36  ldloc.s  7
0x54a38  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x54a3d  ldstr    aFullname// "FullName"
0x54a42  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x54a47  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x54a4c  stfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_pluginAssemblyName
0x54a51  ldloc.s  7
0x54a53  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x54a58  ldstr    aPluginassembly// "PluginAssemblyId"
0x54a5d  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x54a62  brfalse.s loc_54AA4
0x54a64  ldloc.s  7
0x54a66  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x54a6b  ldstr    aPluginassembly// "PluginAssemblyId"
0x54a70  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x54a75  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x54a7a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x54a7f  brtrue.s loc_54AA4
0x54a81  ldarg.0
0x54a82  ldloc.s  7
0x54a84  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x54a89  ldstr    aPluginassembly// "PluginAssemblyId"
0x54a8e  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x54a93  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x54a98  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x54a9d  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_pluginAssemblyId
0x54aa2  br.s     loc_54AAF
0x54aa4  ldarg.0
0x54aa5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x54aaa  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_pluginAssemblyId
0x54aaf  ldc.i4.s 0x5B
0x54ab1  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ImportExportDependencyHelperFactory::RetrieveHelper(int32)
0x54ab6  ldarg.0
0x54ab7  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x54abc  ldarg.0
0x54abd  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_pluginAssemblyName
0x54ac2  ldarg.0
0x54ac3  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_pluginAssemblyId
0x54ac8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x54acd  ldarg.0
0x54ace  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_context
0x54ad3  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper::CheckForRootComponent(class [System.Xml]System.Xml.XmlDocument, string, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x54ad8  ldarg.0
0x54ad9  ldloc.s  7
0x54adb  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::IsUnmodified(class [System.Xml]System.Xml.XmlNode node)
0x54ae0  brfalse.s loc_54AF1
0x54ae2  ldarg.0
0x54ae3  ldloc.s  7
0x54ae5  ldloc.s  4
0x54ae7  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::AddUnmodified(class [System.Xml]System.Xml.XmlNode node, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject service)
0x54aec  br       loc_54DE0
0x54af1  ldarg.0
0x54af2  ldloc.s  7
0x54af4  call     instance class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PluginAssembly Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::GetPluginAssemblyFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x54af9  stloc.s  8
0x54afb  ldstr    aDotnetassembly// "DotNetAssembly"
0x54b00  ldloc.s  8
0x54b02  ldstr    aName// "name"
0x54b07  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x54b0c  castclass [mscorlib]System.String
0x54b11  call     bool [mscorlib]System.String::op_Equality(string, string)
0x54b16  brfalse.s loc_54B84
0x54b18  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x54b1d  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::PluginAssemblyImportWarningDotNetAssembly
0x54b22  ldc.i4.1
0x54b23  newarr   [mscorlib]System.Object
0x54b28  dup
0x54b29  ldc.i4.0
0x54b2a  ldarg.0
0x54b2b  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_pluginAssemblyName
0x54b30  stelem.ref
0x54b31  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x54b36  stloc.s  0x10
0x54b38  ldarg.0
0x54b39  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_tracer
0x54b3e  ldloc.s  0x10
0x54b40  ldc.i4.1
0x54b41  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddSuccess(string successMessage, int32 count)
0x54b46  ldarg.0
0x54b47  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetParameterXPath()
0x54b4c  stloc.s  0x11
0x54b4e  ldloc.s  0x10
0x54b50  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportSolutionException::.ctor(string message)
0x54b55  stloc.s  0x12
0x54b57  ldc.i4.0
0x54b58  stloc.s  0x13
0x54b5a  ldarg.0
0x54b5b  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::_parent
0x54b60  ldloc.s  0x11
0x54b62  ldstr    aWarning// "warning"
0x54b67  ldloc.s  0x12
0x54b69  ldloc.s  0x13
0x54b6b  ldc.i4.0
0x54b6c  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::UpdateProgress(string path, string result, class [mscorlib]System.Exception ex, bool isProcessed, [opt] int32 errorCode)
0x54b71  ldarg.0
0x54b72  ldc.i4.s 0x5B
0x54b74  ldarg.0
0x54b75  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_pluginAssemblyName
0x54b7a  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::RemoveFromRootComponentsList(int32 componentType, string schemaName)
0x54b7f  br       loc_54DE0
0x54b84  ldloc.s  7
0x54b86  ldstr    aSourcetype_0// "SourceType"
0x54b8b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x54b90  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x54b95  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x54b9a  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x54b9f  stloc.s  9
0x54ba1  ldnull
0x54ba2  stloc.s  0xA
0x54ba4  ldloc.s  9
0x54ba6  brtrue.s loc_54BEE
0x54ba8  ldloc.s  7
0x54baa  ldstr    aFilename// "FileName"
0x54baf  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x54bb4  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x54bb9  stloc.s  0x14
0x54bbb  ldloc.s  5
0x54bbd  brtrue.s loc_54BDD
0x54bbf  ldarg.0
0x54bc0  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.IImportFileSet Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_filesToImport
0x54bc5  ldloc.s  0x14
0x54bc7  callvirt instance bool Microsoft.Crm.Tools.ImportExportPublish.IImportFileSet::ContainsFile(string fileName)
0x54bcc  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::PluginAssembliesImportErrorFileName
0x54bd1  ldloc.s  0x14
0x54bd3  call     string [mscorlib]System.String::Concat(string, string)
0x54bd8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x54bdd  ldarg.0
0x54bde  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.IImportFileSet Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_filesToImport
0x54be3  ldloc.s  0x14
0x54be5  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.IImportFileSet::LeaseBufferForFileAsBase64EncodedString(string fileName)
0x54bea  stloc.s  0xA
0x54bec  br.s     loc_54C25
0x54bee  ldc.i4.1
0x54bef  ldloc.s  9
0x54bf1  bne.un.s loc_54C10
0x54bf3  ldloc.s  7
0x54bf5  ldstr    aPath_0// "Path"
0x54bfa  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x54bff  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x54c04  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::PluginAssembliesImportErrorPath
0x54c09  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x54c0e  br.s     loc_54C25
0x54c10  ldc.i4.2
0x54c11  ldloc.s  9
0x54c13  beq.s    loc_54C25
0x54c15  ldc.i4.3
0x54c16  ldloc.s  9
0x54c18  beq.s    loc_54C25
0x54c1a  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::PluginAssembliesImportErrorSourceType
0x54c1f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x54c24  throw
0x54c25  ldc.i4.3
0x54c26  ldloc.s  9
0x54c28  ceq
0x54c2a  stloc.s  0xB
0x54c2c  ldarg.0
0x54c2d  ldloc.s  8
0x54c2f  ldloc.s  0xA
0x54c31  ldloc.s  4
0x54c33  ldloc.s  0xB
0x54c35  ldloca.s 0xC
0x54c37  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::CreateOrGetExistingPluginAssembly(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PluginAssembly pluginAssembly, string fileContent, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject bpoService, bool skipValidation, [out] class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection& existingPluginAssemblies)
0x54c3c  stloc.s  0xD
0x54c3e  ldstr    aPlugintype// "PluginType"
0x54c43  ldarg.0
0x54c44  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_context
0x54c49  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x54c4e  stloc.s  0xE
0x54c50  ldloc.s  7
0x54c52  ldstr    aPlugintypes// "PluginTypes"
0x54c57  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x54c5c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PluginType>::.ctor()
0x54c61  stloc.s  0xF
0x54c63  ldstr    aPlugintype// "PluginType"
0x54c68  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x54c6d  stloc.s  0x15
0x54c6f  ldloc.s  0x15
0x54c71  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x54c76  stloc.s  0x16
0x54c78  br.s     loc_54CF6
0x54c7a  ldloc.s  0x16
0x54c7c  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x54c81  castclass [System.Xml]System.Xml.XmlNode
0x54c86  stloc.s  0x17
0x54c88  ldnull
0x54c89  stloc.s  0x18
0x54c8b  ldarg.0
0x54c8c  ldloc.s  0x17
0x54c8e  call     instance class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PluginType Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::GetPluginTypeFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x54c93  stloc.s  0x18
0x54c95  ldloc.s  0x18
0x54c97  ldstr    aPluginassembly_1// "pluginassemblyid"
0x54c9c  ldloc.s  8
0x54c9e  ldstr    aPluginassembly_1// "pluginassemblyid"
0x54ca3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x54ca8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x54cad  ldloc.s  0xF
0x54caf  ldloc.s  0x18
0x54cb1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PluginType>::Add(var<u1>)
0x54cb6  leave.s  loc_54CF6
0x54cb8  stloc.s  0x19
0x54cba  ldloc.s  0x17
0x54cbc  stloc.1
0x54cbd  ldloc.s  0x18
0x54cbf  stloc.0
0x54cc0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x54cc5  ldstr    a0ErrorPlugin1O// "{0}. Error: Plugin: {1} of PluginTypeNa"...
0x54cca  ldc.i4.4
0x54ccb  newarr   [mscorlib]System.Object
0x54cd0  dup
0x54cd1  ldc.i4.0
0x54cd2  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::PluginTypesImportErrorMessage
0x54cd7  stelem.ref
0x54cd8  dup
0x54cd9  ldc.i4.1
0x54cda  ldarg.0
0x54cdb  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_pluginAssemblyName
0x54ce0  stelem.ref
0x54ce1  dup
0x54ce2  ldc.i4.2
0x54ce3  ldloc.0
0x54ce4  stelem.ref
0x54ce5  dup
0x54ce6  ldc.i4.3
0x54ce7  ldloc.1
0x54ce8  stelem.ref
0x54ce9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x54cee  ldloc.s  0x19
0x54cf0  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportPluginTypesException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x54cf5  throw
  ... truncated ...
```
