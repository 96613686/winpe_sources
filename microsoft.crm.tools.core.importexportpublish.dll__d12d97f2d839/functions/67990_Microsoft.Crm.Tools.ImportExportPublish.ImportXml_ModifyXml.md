# Microsoft.Crm.Tools.ImportExportPublish.ImportXml::ModifyXml

- ea: `0x67990`
- end: `0x67ea0`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportXml::ModifyXml`
- size: `1296`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x67880`

## callees

- `0x50dc0`
- `0x66b20`
- `0x674e0`
- `0x67990`
- `0x67f70`
- `0x68040`

## string_xrefs

- `0x67b30`: `ImportExportXml`
- `0x679a7`: `importexportxml`
- `0x67e49`: `importexportxml`
- `0x67a82`: `solutionManifests`
- `0x67a91`: `solutionManifests`
- `0x67a96`: `solutionManifest`
- `0x67c5a`: `formXml`
- `0x67d57`: `rootComponent`
- `0x67d02`: `ImportExportXml/SolutionManifest/Managed`
- `0x67a64`: `solutionManifests/solutionManifest/UniqueName`
- `0x67aa1`: `solutionManifests/solutionManifest`
- `0x67c49`: `ImportExportXml/Entities/Entity[Name='{0}']/SavedQueries/savedqueries/savedquery`
- `0x67c5f`: `ImportExportXml/Entities/Entity[Name='{0}']/FormXml/forms`
- `0x67c75`: `ImportExportXml/Entities/Entity[Name='{0}']/Icons/Icon`
- `0x67c8b`: `ImportExportXml/Entities/Entity[Name='{0}']/Strings/Strings`
- `0x67ca1`: `ImportExportXml/Entities/Entity[Name='{0}']/RibbonDiffXml`
- `0x67cb7`: `ImportExportXml/Entities/Entity[Name='{0}']/Visualizations/visualization`
- `0x67ccd`: `ImportExportXml/Entities/Entity[Name='{0}']/HierarchyRules/HierarchyRule`
- `0x67d52`: `rootComponents`
- `0x67e1d`: `importexportxml/upgradeHandlers`
- `0x67e2a`: `importexportxml/skuHandlers`
- `0x67e37`: `importexportxml/validateHandlers`

## pseudocode

```c

```

## disassembly

```asm
0x67990  ldarg.0
0x67991  ldarg.0
0x67992  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXml
0x67997  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x6799c  stfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x679a1  ldarg.0
0x679a2  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x679a7  ldstr    aImportexportxm_95// "importexportxml"
0x679ac  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x679b1  stloc.0
0x679b2  ldloc.0
0x679b3  brtrue.s loc_679D0
0x679b5  ldstr    aInvalidParamet// "Invalid parameter root node name: "
0x679ba  ldarg.0
0x679bb  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x679c0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x679c5  call     string [mscorlib]System.String::Concat(string, string)
0x679ca  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x679cf  throw
0x679d0  ldarg.0
0x679d1  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x679d6  ldstr    aStart// "start"
0x679db  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x679e0  stloc.1
0x679e1  ldloc.0
0x679e2  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x679e7  ldloc.1
0x679e8  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x679ed  pop
0x679ee  ldloc.1
0x679ef  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x679f4  stloc.s  9
0x679f6  ldloca.s 9
0x679f8  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x679fd  stloc.s  0xA
0x679ff  ldloca.s 0xA
0x67a01  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x67a06  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x67a0b  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x67a10  ldarg.0
0x67a11  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x67a16  ldstr    aStop// "stop"
0x67a1b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x67a20  stloc.2
0x67a21  ldloc.0
0x67a22  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x67a27  ldloc.2
0x67a28  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x67a2d  pop
0x67a2e  ldloc.2
0x67a2f  ldloc.1
0x67a30  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x67a35  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x67a3a  ldarg.0
0x67a3b  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x67a40  ldstr    aProgress// "progress"
0x67a45  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x67a4a  stloc.3
0x67a4b  ldloc.0
0x67a4c  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x67a51  ldloc.3
0x67a52  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x67a57  pop
0x67a58  ldloc.3
0x67a59  ldstr    a00// "0.0"
0x67a5e  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x67a63  ldloc.0
0x67a64  ldstr    aSolutionmanife_3// "solutionManifests/solutionManifest/Uniq"...
0x67a69  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x67a6e  stloc.s  4
0x67a70  ldloc.s  4
0x67a72  brfalse.s loc_67A81
0x67a74  ldarg.0
0x67a75  ldloc.s  4
0x67a77  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x67a7c  stfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportXml::_solutionName
0x67a81  ldloc.0
0x67a82  ldstr    aSolutionmanife_0// "solutionManifests"
0x67a87  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x67a8c  brtrue.s loc_67AA0
0x67a8e  ldarg.0
0x67a8f  ldloc.0
0x67a90  ldc.i4.1
0x67a91  ldstr    aSolutionmanife_0// "solutionManifests"
0x67a96  ldstr    aSolutionmanife_1// "solutionManifest"
0x67a9b  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::AddNode(class [System.Xml]System.Xml.XmlNode rootNode, bool firstNode, string pluralName, string singularName)
0x67aa0  ldloc.0
0x67aa1  ldstr    aSolutionmanife_4// "solutionManifests/solutionManifest"
0x67aa6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x67aab  stloc.s  5
0x67aad  ldloc.s  5
0x67aaf  brfalse  loc_67B6A
0x67ab4  ldarg.0
0x67ab5  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x67aba  ldstr    aId// "id"
0x67abf  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x67ac4  stloc.s  0xB
0x67ac6  ldloc.s  5
0x67ac8  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x67acd  ldloc.s  0xB
0x67acf  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x67ad4  pop
0x67ad5  ldloc.s  0xB
0x67ad7  ldarg.0
0x67ad8  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportXml::_solutionName
0x67add  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x67ae2  ldarg.0
0x67ae3  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x67ae8  ldstr    aLocalizedname// "LocalizedName"
0x67aed  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x67af2  stloc.s  0xC
0x67af4  ldloc.s  5
0x67af6  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x67afb  ldloc.s  0xC
0x67afd  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x67b02  pop
0x67b03  ldarg.0
0x67b04  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportXml::context
0x67b09  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x67b0e  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_LanguageCode()
0x67b13  stloc.s  0x10
0x67b15  ldloca.s 0x10
0x67b17  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x67b1c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x67b21  stloc.s  0xD
0x67b23  ldsfld   string [mscorlib]System.String::Empty
0x67b28  stloc.s  0xE
0x67b2a  ldarg.0
0x67b2b  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_ImportDocument()
0x67b30  ldstr    aImportexportxm// "ImportExportXml"
0x67b35  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x67b3a  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x67b3f  ldstr    aLanguagecode// "languagecode"
0x67b44  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x67b49  stloc.s  0xF
0x67b4b  ldloc.s  0xF
0x67b4d  brfalse.s loc_67B58
0x67b4f  ldloc.s  0xF
0x67b51  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x67b56  stloc.s  0xE
0x67b58  ldloc.s  0xC
0x67b5a  ldloc.s  5
0x67b5c  ldloc.s  0xD
0x67b5e  ldloc.s  0xE
0x67b60  call     string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetBaseLanguageName(class [System.Xml]System.Xml.XmlNode node, string baseLanguage, string originalBaseLanguage)
0x67b65  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x67b6a  ldarg.0
0x67b6b  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x67b70  ldstr    aProcessed// "processed"
0x67b75  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x67b7a  stloc.s  6
0x67b7c  ldloc.0
0x67b7d  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x67b82  ldloc.s  6
0x67b84  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x67b89  pop
0x67b8a  ldloc.s  6
0x67b8c  ldstr    aFalse// "false"
0x67b91  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x67b96  ldloc.0
0x67b97  ldstr    aEntitiesEntity_5// "entities/entity"
0x67b9c  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x67ba1  stloc.s  0x11
0x67ba3  ldloc.s  0x11
0x67ba5  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x67baa  stloc.s  0x14
0x67bac  br.s     loc_67BCA
0x67bae  ldloc.s  0x14
0x67bb0  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x67bb5  castclass [System.Xml]System.Xml.XmlNode
0x67bba  dup
0x67bbb  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x67bc0  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x67bc5  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x67bca  ldloc.s  0x14
0x67bcc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x67bd1  brtrue.s loc_67BAE
0x67bd3  leave.s  loc_67BEA
0x67bd5  ldloc.s  0x14
0x67bd7  isinst   [mscorlib]System.IDisposable
0x67bdc  stloc.s  0x15
0x67bde  ldloc.s  0x15
0x67be0  brfalse.s loc_67BE9
0x67be2  ldloc.s  0x15
0x67be4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x67be9  endfinally
0x67bea  ldarg.0
0x67beb  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x67bf0  ldc.i4.1
0x67bf1  ldstr    aEntitysubhandl// "entitySubhandlers"
0x67bf6  ldsfld   string [mscorlib]System.String::Empty
0x67bfb  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x67c00  stloc.s  0x12
0x67c02  ldloc.0
0x67c03  ldloc.s  0x12
0x67c05  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x67c0a  pop
0x67c0b  ldloc.s  0x11
0x67c0d  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x67c12  stloc.s  0x14
0x67c14  br       loc_67CD9
0x67c19  ldloc.s  0x14
0x67c1b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x67c20  castclass [System.Xml]System.Xml.XmlNode
0x67c25  stloc.s  0x16
0x67c27  ldloc.s  0x16
0x67c29  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x67c2e  ldstr    aId// "id"
0x67c33  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x67c38  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x67c3d  stloc.s  0x17
0x67c3f  ldarg.0
0x67c40  ldloc.s  0x12
0x67c42  ldloc.s  0x16
0x67c44  ldstr    aSavedquery_0// "savedQuery"
0x67c49  ldstr    aImportexportxm_176// "ImportExportXml/Entities/Entity[Name='{"...
0x67c4e  ldloc.s  0x17
0x67c50  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::AddSubHandlerInfo(class [System.Xml]System.Xml.XmlNode entitySubhandlersNode, class [System.Xml]System.Xml.XmlNode node, string subhandlerName, string dataPath, string entityName)
0x67c55  ldarg.0
0x67c56  ldloc.s  0x12
0x67c58  ldloc.s  0x16
0x67c5a  ldstr    aFormxml_1// "formXml"
0x67c5f  ldstr    aImportexportxm_177// "ImportExportXml/Entities/Entity[Name='{"...
0x67c64  ldloc.s  0x17
0x67c66  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::AddSubHandlerInfo(class [System.Xml]System.Xml.XmlNode entitySubhandlersNode, class [System.Xml]System.Xml.XmlNode node, string subhandlerName, string dataPath, string entityName)
0x67c6b  ldarg.0
0x67c6c  ldloc.s  0x12
0x67c6e  ldloc.s  0x16
0x67c70  ldstr    aEntityicons// "entityIcons"
0x67c75  ldstr    aImportexportxm_178// "ImportExportXml/Entities/Entity[Name='{"...
0x67c7a  ldloc.s  0x17
0x67c7c  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::AddSubHandlerInfo(class [System.Xml]System.Xml.XmlNode entitySubhandlersNode, class [System.Xml]System.Xml.XmlNode node, string subhandlerName, string dataPath, string entityName)
0x67c81  ldarg.0
0x67c82  ldloc.s  0x12
0x67c84  ldloc.s  0x16
0x67c86  ldstr    aEntitycustomre// "entityCustomResources"
0x67c8b  ldstr    aImportexportxm_179// "ImportExportXml/Entities/Entity[Name='{"...
0x67c90  ldloc.s  0x17
0x67c92  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::AddSubHandlerInfo(class [System.Xml]System.Xml.XmlNode entitySubhandlersNode, class [System.Xml]System.Xml.XmlNode node, string subhandlerName, string dataPath, string entityName)
0x67c97  ldarg.0
0x67c98  ldloc.s  0x12
0x67c9a  ldloc.s  0x16
0x67c9c  ldstr    aEntityribbon// "entityRibbon"
0x67ca1  ldstr    aImportexportxm_180// "ImportExportXml/Entities/Entity[Name='{"...
0x67ca6  ldloc.s  0x17
0x67ca8  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::AddSubHandlerInfo(class [System.Xml]System.Xml.XmlNode entitySubhandlersNode, class [System.Xml]System.Xml.XmlNode node, string subhandlerName, string dataPath, string entityName)
0x67cad  ldarg.0
0x67cae  ldloc.s  0x12
0x67cb0  ldloc.s  0x16
0x67cb2  ldstr    aSavedqueryvisu_2// "savedQueryVisualization"
0x67cb7  ldstr    aImportexportxm_181// "ImportExportXml/Entities/Entity[Name='{"...
0x67cbc  ldloc.s  0x17
0x67cbe  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::AddSubHandlerInfo(class [System.Xml]System.Xml.XmlNode entitySubhandlersNode, class [System.Xml]System.Xml.XmlNode node, string subhandlerName, string dataPath, string entityName)
0x67cc3  ldarg.0
0x67cc4  ldloc.s  0x12
0x67cc6  ldloc.s  0x16
0x67cc8  ldstr    aHierarchyrule_0// "hierarchyRule"
0x67ccd  ldstr    aImportexportxm_182// "ImportExportXml/Entities/Entity[Name='{"...
0x67cd2  ldloc.s  0x17
0x67cd4  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::AddSubHandlerInfo(class [System.Xml]System.Xml.XmlNode entitySubhandlersNode, class [System.Xml]System.Xml.XmlNode node, string subhandlerName, string dataPath, string entityName)
0x67cd9  ldloc.s  0x14
0x67cdb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x67ce0  brtrue   loc_67C19
0x67ce5  leave.s  loc_67CFC
0x67ce7  ldloc.s  0x14
0x67ce9  isinst   [mscorlib]System.IDisposable
0x67cee  stloc.s  0x15
0x67cf0  ldloc.s  0x15
0x67cf2  brfalse.s loc_67CFB
0x67cf4  ldloc.s  0x15
0x67cf6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x67cfb  endfinally
0x67cfc  ldarg.0
0x67cfd  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_ImportDocument()
0x67d02  ldstr    aImportexportxm_133// "ImportExportXml/SolutionManifest/Manage"...
0x67d07  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x67d0c  stloc.s  0x13
0x67d0e  ldloc.s  0x13
0x67d10  brfalse.s loc_67D41
0x67d12  ldloc.s  0x13
0x67d14  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x67d19  ldstr    a1// "1"
0x67d1e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x67d23  brfalse.s loc_67D41
0x67d25  ldloc.s  0x11
0x67d27  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x67d2c  ldc.i4.0
0x67d2d  ble.s    loc_67D41
0x67d2f  ldarg.0
0x67d30  ldloc.0
0x67d31  ldc.i4.0
0x67d32  ldstr    aPublishes// "publishes"
0x67d37  ldstr    aPublish// "publish"
0x67d3c  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::AddNode(class [System.Xml]System.Xml.XmlNode rootNode, bool firstNode, string pluralName, string singularName)
0x67d41  leave.s  loc_67D4F
0x67d43  ldloc.s  0x11
0x67d45  brfalse.s loc_67D4E
0x67d47  ldloc.s  0x11
0x67d49  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x67d4e  endfinally
  ... truncated ...
```
