# Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::InjectOOBCustomizations

- ea: `0x62570`
- end: `0x62974`
- name: `Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::InjectOOBCustomizations`
- size: `1028`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x60e70`

## callees

- `0xe1c0`
- `0x3aa00`
- `0x41d50`
- `0x420a0`
- `0x5be20`
- `0x5fb30`
- `0x5fc90`
- `0x62570`
- `0x62980`
- `0x62f90`
- `0x63200`
- `0x63250`
- `0x63310`
- `0x64f70`

## string_xrefs

- `0x62698`: `CustomizationXml/ShortLogicalName`
- `0x62798`: `CreateEntityMap/EntityMap`

## pseudocode

```c

```

## disassembly

```asm
0x62570  ldc.i4.0
0x62571  stloc.0
0x62572  ldarg.2
0x62573  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.ImportWizardState::get_Context()
0x62578  call     bool Microsoft.Crm.Application.Utility.SystemCustomizationSecurity::CheckPublishPrivileges(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6257d  brfalse.s loc_6258E
0x6257f  ldarg.2
0x62580  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.ImportWizardState::get_Context()
0x62585  call     bool Microsoft.Crm.Application.Utility.SystemCustomizationSecurity::CheckPublishCustomizationsPrivileges(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6258a  brfalse.s loc_6258E
0x6258c  ldc.i4.1
0x6258d  stloc.0
0x6258e  ldarg.2
0x6258f  callvirt instance class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.ImportWizardState::get_ImportMapEntity()
0x62594  brfalse.s loc_625C4
0x62596  ldarg.2
0x62597  callvirt instance class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.ImportWizardState::get_ImportMapEntity()
0x6259c  ldstr    aMapcustomizati// "mapcustomizations"
0x625a1  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x625a6  brfalse.s loc_625C4
0x625a8  ldarg.2
0x625a9  callvirt instance class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.ImportWizardState::get_ImportMapEntity()
0x625ae  ldstr    aMapcustomizati// "mapcustomizations"
0x625b3  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x625b8  castclass [mscorlib]System.String
0x625bd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x625c2  brfalse.s loc_625C6
0x625c4  ldarg.1
0x625c5  ret
0x625c6  ldarg.2
0x625c7  callvirt instance class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.ImportWizardState::get_ImportMapEntity()
0x625cc  ldstr    aMapcustomizati// "mapcustomizations"
0x625d1  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x625d6  castclass [mscorlib]System.String
0x625db  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x625e0  stloc.1
0x625e1  ldarg.2
0x625e2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.ImportWizardState::get_Context()
0x625e7  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings Microsoft.Crm.Security.Organization::GetSettings(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x625ec  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_SchemaNamePrefix()
0x625f1  ldstr    asc_A93D6// "_"
0x625f6  call     string [mscorlib]System.String::Concat(string, string)
0x625fb  stloc.2
0x625fc  ldloc.2
0x625fd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x62602  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x62607  stloc.2
0x62608  ldloc.2
0x62609  ldstr    aNew// "new_"
0x6260e  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x62613  brfalse.s loc_62623
0x62615  ldarg.0
0x62616  ldloc.1
0x62617  ldstr    aNew// "new_"
0x6261c  ldloc.2
0x6261d  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::ReplaceSchemaNamePrefixForCustomizationXml(class [System.Xml]System.Xml.XmlDocument doc, string oldPrefix, string newPrefix)
0x62622  pop
0x62623  ldarg.1
0x62624  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x62629  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x6262e  stloc.3
0x6262f  ldloc.1
0x62630  ldstr    aImportcustomiz// "/ImportCustomizations/Entities/CustomEn"...
0x62635  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x6263a  stloc.s  4
0x6263c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x62641  stloc.s  5
0x62643  ldloc.s  4
0x62645  brfalse  loc_6294D
0x6264a  ldloc.s  4
0x6264c  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x62651  ldc.i4.0
0x62652  ble      loc_6294D
0x62657  ldloc.s  4
0x62659  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x6265e  stloc.s  6
0x62660  br       loc_6292A
0x62665  ldloc.s  6
0x62667  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6266c  castclass [System.Xml]System.Xml.XmlNode
0x62671  stloc.s  7
0x62673  ldloc.s  7
0x62675  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x6267a  ldstr    aId_0// "Id"
0x6267f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x62684  stloc.s  8
0x62686  ldloc.s  8
0x62688  brfalse  loc_6292A
0x6268d  ldloc.s  8
0x6268f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x62694  stloc.s  9
0x62696  ldloc.s  7
0x62698  ldstr    aCustomizationx// "CustomizationXml/ShortLogicalName"
0x6269d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x626a2  stloc.s  0xA
0x626a4  ldloc.s  0xA
0x626a6  brfalse  loc_6292A
0x626ab  ldloc.s  0xA
0x626ad  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x626b2  stloc.s  0xB
0x626b4  ldloc.2
0x626b5  ldloc.s  0xB
0x626b7  call     string [mscorlib]System.String::Concat(string, string)
0x626bc  stloc.s  0xC
0x626be  ldarg.0
0x626bf  ldloc.s  7
0x626c1  ldloc.2
0x626c2  ldarg.2
0x626c3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.ImportWizardState::get_Context()
0x626c8  call     instance valuetype EntityInjectionState Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::GetEntityInjectionState(class [System.Xml]System.Xml.XmlNode customEntityNode, string metadataPrefix, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x626cd  stloc.s  0xD
0x626cf  ldloc.s  0xD
0x626d1  brtrue   loc_6284D
0x626d6  ldstr    aMapEntitymapsE_1// "/Map/EntityMaps/EntityMap[@ProcessCode="...
0x626db  ldc.i4.3
0x626dc  stloc.s  0xF
0x626de  ldloca.s 0xF
0x626e0  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode
0x626e6  callvirt instance string [mscorlib]System.Object::ToString()
0x626eb  ldstr    asc_B6994// "']"
0x626f0  call     string [mscorlib]System.String::Concat(string, string, string)
0x626f5  stloc.s  0xE
0x626f7  ldarg.1
0x626f8  ldloc.s  0xE
0x626fa  ldstr    aTargetentityre// "TargetEntityRef"
0x626ff  ldloc.s  9
0x62701  ldc.i4.1
0x62702  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x62707  call     class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.Platform.XPathHelper::SelectSingleNode(class [System.Xml]System.Xml.XmlNode xmlNode, string initialXPath, string name, string value, valuetype XPathCondition condition, class [mscorlib]System.Globalization.CultureInfo culture)
0x6270c  brtrue   loc_6292A
0x62711  ldstr    aMapEntitymapsE// "/Map/EntityMaps/EntityMap[not(@Unused) "...
0x62716  ldc.i4.1
0x62717  stloc.s  0xF
0x62719  ldloca.s 0xF
0x6271b  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode
0x62721  callvirt instance string [mscorlib]System.Object::ToString()
0x62726  ldstr    asc_B6994// "']"
0x6272b  call     string [mscorlib]System.String::Concat(string, string, string)
0x62730  stloc.s  0x10
0x62732  ldloc.3
0x62733  ldloc.s  0x10
0x62735  ldstr    aSourceentityna_0// "SourceEntityName"
0x6273a  ldloc.s  9
0x6273c  ldc.i4.1
0x6273d  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x62742  call     class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.Platform.XPathHelper::SelectSingleNode(class [System.Xml]System.Xml.XmlNode xmlNode, string initialXPath, string name, string value, valuetype XPathCondition condition, class [mscorlib]System.Globalization.CultureInfo culture)
0x62747  stloc.s  0x11
0x62749  ldloc.s  0x11
0x6274b  ldnull
0x6274c  cgt.un
0x6274e  ldloc.0
0x6274f  and
0x62750  brfalse  loc_6292A
0x62755  ldarg.0
0x62756  ldloca.s 3
0x62758  call     instance void Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::CreateCustomizationSectionIfNotPresent(class [System.Xml]System.Xml.XmlDocument& doc)
0x6275d  ldloc.3
0x6275e  ldstr    aMapCustomizati_0// "/Map/Customizations/Entities"
0x62763  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x62768  ldloc.3
0x62769  ldloc.s  7
0x6276b  ldc.i4.1
0x6276c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::ImportNode(class [System.Xml]System.Xml.XmlNode, bool)
0x62771  stloc.s  0x12
0x62773  ldloc.s  0x12
0x62775  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x6277a  pop
0x6277b  ldarg.0
0x6277c  ldloca.s 3
0x6277e  call     instance void Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::MarkMapAsInjected(class [System.Xml]System.Xml.XmlDocument& doc)
0x62783  ldloc.s  0x11
0x62785  ldstr    aAttributemaps// "AttributeMaps"
0x6278a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x6278f  stloc.s  0x13
0x62791  ldloc.s  7
0x62793  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x62798  ldstr    aCreateentityma// "CreateEntityMap/EntityMap"
0x6279d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x627a2  stloc.s  0x14
0x627a4  ldloc.s  0x14
0x627a6  brfalse  loc_62839
0x627ab  ldloc.3
0x627ac  ldstr    aMapEntitymaps// "/Map/EntityMaps"
0x627b1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x627b6  ldloc.3
0x627b7  ldloc.s  0x14
0x627b9  ldc.i4.1
0x627ba  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::ImportNode(class [System.Xml]System.Xml.XmlNode, bool)
0x627bf  stloc.s  0x15
0x627c1  ldloc.s  0x13
0x627c3  brfalse.s loc_627D9
0x627c5  ldloc.s  0x13
0x627c7  ldc.i4.1
0x627c8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::CloneNode(bool)
0x627cd  stloc.s  0x16
0x627cf  ldloc.s  0x15
0x627d1  ldloc.s  0x16
0x627d3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x627d8  pop
0x627d9  ldloc.s  0x15
0x627db  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x627e0  ldstr    aSourceentityna_0// "SourceEntityName"
0x627e5  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x627ea  ldloc.s  0x11
0x627ec  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x627f1  ldstr    aSourceentityna_0// "SourceEntityName"
0x627f6  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x627fb  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x62800  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x62805  ldloc.s  0x15
0x62807  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x6280c  ldstr    aInputfilename// "InputFileName"
0x62811  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x62816  ldloc.s  0x11
0x62818  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x6281d  ldstr    aInputfilename// "InputFileName"
0x62822  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x62827  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x6282c  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x62831  ldloc.s  0x15
0x62833  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x62838  pop
0x62839  ldloc.s  0x11
0x6283b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x62840  ldloc.s  0x11
0x62842  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x62847  pop
0x62848  br       loc_6292A
0x6284d  ldloc.s  0xD
0x6284f  ldc.i4.1
0x62850  bne.un   loc_62921
0x62855  ldarg.1
0x62856  ldstr    aMapEntitymapsE_17// "/Map/EntityMaps/EntityMap[not(@Unused) "...
0x6285b  ldloc.s  0xC
0x6285d  ldstr    aAndProcesscode_0// "\" and @ProcessCode=\"Process\"]"
0x62862  call     string [mscorlib]System.String::Concat(string, string, string)
0x62867  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x6286c  brtrue   loc_6292A
0x62871  ldstr    aMapEntitymapsE// "/Map/EntityMaps/EntityMap[not(@Unused) "...
0x62876  ldc.i4.1
0x62877  stloc.s  0xF
0x62879  ldloca.s 0xF
0x6287b  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode
0x62881  callvirt instance string [mscorlib]System.Object::ToString()
0x62886  ldstr    asc_B6994// "']"
0x6288b  call     string [mscorlib]System.String::Concat(string, string, string)
0x62890  stloc.s  0x17
0x62892  ldloc.3
0x62893  ldloc.s  0x17
0x62895  ldstr    aSourceentityna_0// "SourceEntityName"
0x6289a  ldloc.s  9
0x6289c  ldc.i4.1
0x6289d  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x628a2  call     class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.Platform.XPathHelper::SelectSingleNode(class [System.Xml]System.Xml.XmlNode xmlNode, string initialXPath, string name, string value, valuetype XPathCondition condition, class [mscorlib]System.Globalization.CultureInfo culture)
0x628a7  stloc.s  0x18
0x628a9  ldloc.s  0x18
0x628ab  brfalse.s loc_6292A
0x628ad  ldloc.s  7
0x628af  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x628b4  ldstr    aExistingentity// "ExistingEntityMap/EntityMap"
0x628b9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x628be  stloc.s  0x19
0x628c0  ldloc.s  0x19
0x628c2  brfalse.s loc_6292A
0x628c4  ldloc.s  0x18
0x628c6  ldstr    aAttributemaps// "AttributeMaps"
0x628cb  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x628d0  stloc.s  0x1A
0x628d2  ldloc.3
0x628d3  ldstr    aMapEntitymaps// "/Map/EntityMaps"
0x628d8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x628dd  ldloc.3
0x628de  ldloc.s  0x19
0x628e0  ldc.i4.1
0x628e1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::ImportNode(class [System.Xml]System.Xml.XmlNode, bool)
0x628e6  stloc.s  0x1B
0x628e8  ldloc.s  0x1A
0x628ea  brfalse.s loc_62900
0x628ec  ldloc.s  0x1A
0x628ee  ldc.i4.1
0x628ef  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::CloneNode(bool)
0x628f4  stloc.s  0x1C
0x628f6  ldloc.s  0x1B
0x628f8  ldloc.s  0x1C
0x628fa  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x628ff  pop
0x62900  ldloc.s  0x1B
0x62902  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x62907  pop
0x62908  ldloc.s  0x18
0x6290a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x6290f  ldloc.s  0x18
0x62911  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x62916  pop
0x62917  ldarg.0
0x62918  ldloca.s 3
0x6291a  call     instance void Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::MarkMapAsInjected(class [System.Xml]System.Xml.XmlDocument& doc)
0x6291f  br.s     loc_6292A
0x62921  ldloc.s  5
0x62923  ldloc.s  0xB
  ... truncated ...
```
