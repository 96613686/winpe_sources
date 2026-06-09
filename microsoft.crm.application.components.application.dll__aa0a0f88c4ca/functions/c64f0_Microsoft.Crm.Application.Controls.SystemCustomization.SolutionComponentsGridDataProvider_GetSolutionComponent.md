# Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::GetSolutionComponentsXml

- ea: `0xc64f0`
- end: `0xc68c3`
- name: `Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::GetSolutionComponentsXml`
- size: `979`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0xc64f0`
- `0xc68d0`
- `0xc6980`

## string_xrefs

- `0xc6833`: `nav_components`
- `0xc66e4`: `Solution.TreeNav.Nodes.Configuration.Title`
- `0xc6745`: `nav_Configuration`
- `0xc6755`: `areaSolutionComponent`
- `0xc6843`: `areaSolutionComponent`
- `0xc67cc`: `/tools/solution/areas.aspx?tabset=areaSolutionComponent`
- `0xc67f0`: `Solution.TreeNav.Nodes.Components.Title`
- `0xc6868`: `/_imgs/solution/component.png`

## pseudocode

```c

```

## disassembly

```asm
0xc64f0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xc64f5  stloc.0
0xc64f6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc64fb  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc6500  ldc.i4   0x1BBC
0xc6505  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xc650a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0xc650f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc6514  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::GetLabelString(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc6519  stloc.2
0xc651a  ldarg.1
0xc651b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc6520  brtrue.s loc_C6557
0xc6522  ldstr    aSolution// "solution"
0xc6527  ldarg.1
0xc6528  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xc652d  ldc.i4.1
0xc652e  newarr   [mscorlib]System.String
0xc6533  dup
0xc6534  ldc.i4.0
0xc6535  ldstr    aFriendlyname// "friendlyname"
0xc653a  stelem.ref
0xc653b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc6540  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc6545  ldstr    aFriendlyname// "friendlyname"
0xc654a  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xc654f  isinst   [mscorlib]System.String
0xc6554  stloc.1
0xc6555  br.s     loc_C6567
0xc6557  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xc655c  ldstr    aFormTitleNew// "Form_Title_New"
0xc6561  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc6566  stloc.1
0xc6567  ldloc.0
0xc6568  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.Text.StringBuilder)
0xc656d  stloc.3
0xc656e  ldloc.3
0xc656f  ldstr    aNavigation// "navigation"
0xc6574  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xc6579  ldloc.3
0xc657a  ldstr    aTitle// "title"
0xc657f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xc6584  ldstr    aGridTitleMask// "Grid_Title_Mask"
0xc6589  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc658e  ldc.i4.2
0xc658f  newarr   [mscorlib]System.Object
0xc6594  dup
0xc6595  ldc.i4.0
0xc6596  ldloc.2
0xc6597  stelem.ref
0xc6598  dup
0xc6599  ldc.i4.1
0xc659a  ldloc.1
0xc659b  stelem.ref
0xc659c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, object[])
0xc65a1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc65a6  ldarg.0
0xc65a7  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::GetDefaultSelectedNodeId()
0xc65ac  stloc.s  4
0xc65ae  ldloc.s  4
0xc65b0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc65b5  brtrue.s loc_C65C4
0xc65b7  ldloc.3
0xc65b8  ldstr    aDefaultselecte_0// "defaultselectednodeid"
0xc65bd  ldloc.s  4
0xc65bf  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc65c4  ldloc.3
0xc65c5  ldstr    aDefaultwidth// "defaultwidth"
0xc65ca  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xc65cf  ldstr    aDetailformLeft// "DetailForm_Left_Navigation_Width"
0xc65d4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc65d9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc65de  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc65e3  ldloc.3
0xc65e4  ldstr    aGrouparea// "grouparea"
0xc65e9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xc65ee  ldloc.3
0xc65ef  ldstr    aDisplayname// "displayname"
0xc65f4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xc65f9  ldstr    aAreaLabelInfo// "Area_Label_Info"
0xc65fe  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc6603  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6608  ldloc.3
0xc6609  ldstr    aLevel_0// "level"
0xc660e  ldstr    a0// "0"
0xc6613  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6618  ldloc.3
0xc6619  ldstr    aType// "type"
0xc661e  ldc.i4   0x1BBC
0xc6623  stloc.s  6
0xc6625  ldloca.s 6
0xc6627  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc662c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xc6631  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6636  ldloc.3
0xc6637  ldstr    aCode// "code"
0xc663c  ldc.i4   0x1BBC
0xc6641  stloc.s  6
0xc6643  ldloca.s 6
0xc6645  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc664a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xc664f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6654  ldloc.3
0xc6655  ldstr    aId_1// "id"
0xc665a  ldstr    aNavDetails// "nav_Details"
0xc665f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6664  ldloc.3
0xc6665  ldstr    aTabset_0// "tabset"
0xc666a  ldstr    aAreaform// "areaForm"
0xc666f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6674  ldloc.3
0xc6675  ldstr    aAction// "action"
0xc667a  ldstr    asc_F5812// "."
0xc667f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6684  ldloc.3
0xc6685  ldstr    aIcon_0// "icon"
0xc668a  ldc.i4   0x1BBC
0xc668f  ldc.i4.0
0xc6690  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc6695  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::GetIconPath(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc669a  callvirt instance string [mscorlib]System.Object::ToString()
0xc669f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc66a4  ldloc.3
0xc66a5  ldstr    aExpanded// "expanded"
0xc66aa  ldstr    aTrue// "true"
0xc66af  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc66b4  ldloc.3
0xc66b5  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xc66ba  ldarg.1
0xc66bb  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext::GetConfigurationPath(string)
0xc66c0  stloc.s  5
0xc66c2  ldloc.s  5
0xc66c4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc66c9  brtrue   loc_C67BB
0xc66ce  ldloc.3
0xc66cf  ldstr    aGrouparea// "grouparea"
0xc66d4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xc66d9  ldloc.3
0xc66da  ldstr    aDisplayname// "displayname"
0xc66df  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xc66e4  ldstr    aSolutionTreena// "Solution.TreeNav.Nodes.Configuration.Ti"...
0xc66e9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc66ee  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc66f3  ldloc.3
0xc66f4  ldstr    aLevel_0// "level"
0xc66f9  ldstr    a0// "0"
0xc66fe  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6703  ldloc.3
0xc6704  ldstr    aType// "type"
0xc6709  ldc.i4   0x1BBC
0xc670e  stloc.s  6
0xc6710  ldloca.s 6
0xc6712  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc6717  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xc671c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6721  ldloc.3
0xc6722  ldstr    aCode// "code"
0xc6727  ldc.i4   0x1BBC
0xc672c  stloc.s  6
0xc672e  ldloca.s 6
0xc6730  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc6735  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xc673a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc673f  ldloc.3
0xc6740  ldstr    aId_1// "id"
0xc6745  ldstr    aNavConfigurati// "nav_Configuration"
0xc674a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc674f  ldloc.3
0xc6750  ldstr    aTabset_0// "tabset"
0xc6755  ldstr    aAreasolutionco// "areaSolutionComponent"
0xc675a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc675f  ldloc.3
0xc6760  ldstr    aAction// "action"
0xc6765  ldloc.s  5
0xc6767  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc676c  ldloc.3
0xc676d  ldstr    aIcon_0// "icon"
0xc6772  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xc6777  ldc.i4.1
0xc6778  newarr   [mscorlib]System.Char
0xc677d  dup
0xc677e  ldc.i4.0
0xc677f  ldc.i4.s 0x2F
0xc6781  stelem.i2
0xc6782  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xc6787  ldstr    aImgsSolutionPo// "/_imgs/solution/poperties_16.png"
0xc678c  call     string [mscorlib]System.String::Concat(string, string)
0xc6791  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc6796  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc679b  callvirt instance string [mscorlib]System.Object::ToString()
0xc67a0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc67a5  ldloc.3
0xc67a6  ldstr    aExpanded// "expanded"
0xc67ab  ldstr    aTrue// "true"
0xc67b0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc67b5  ldloc.3
0xc67b6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xc67bb  ldloc.3
0xc67bc  ldstr    aGrouparea// "grouparea"
0xc67c1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xc67c6  ldloc.3
0xc67c7  ldstr    aAction// "action"
0xc67cc  ldstr    aToolsSolutionA// "/tools/solution/areas.aspx?tabset=areaS"...
0xc67d1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc67d6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc67db  callvirt instance string [mscorlib]System.Object::ToString()
0xc67e0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc67e5  ldloc.3
0xc67e6  ldstr    aDisplayname// "displayname"
0xc67eb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xc67f0  ldstr    aSolutionTreena_0// "Solution.TreeNav.Nodes.Components.Title"
0xc67f5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc67fa  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc67ff  ldloc.3
0xc6800  ldstr    aLevel_0// "level"
0xc6805  ldstr    a0// "0"
0xc680a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc680f  ldloc.3
0xc6810  ldstr    aType// "type"
0xc6815  ldc.i4   0x1BBF
0xc681a  stloc.s  6
0xc681c  ldloca.s 6
0xc681e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc6823  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xc6828  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc682d  ldloc.3
0xc682e  ldstr    aId_1// "id"
0xc6833  ldstr    aNavComponents// "nav_components"
0xc6838  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc683d  ldloc.3
0xc683e  ldstr    aTabset_0// "tabset"
0xc6843  ldstr    aAreasolutionco// "areaSolutionComponent"
0xc6848  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc684d  ldloc.3
0xc684e  ldstr    aIcon_0// "icon"
0xc6853  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xc6858  ldc.i4.1
0xc6859  newarr   [mscorlib]System.Char
0xc685e  dup
0xc685f  ldc.i4.0
0xc6860  ldc.i4.s 0x2F
0xc6862  stelem.i2
0xc6863  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xc6868  ldstr    aImgsSolutionCo// "/_imgs/solution/component.png"
0xc686d  call     string [mscorlib]System.String::Concat(string, string)
0xc6872  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc6877  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc687c  callvirt instance string [mscorlib]System.Object::ToString()
0xc6881  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6886  ldloc.3
0xc6887  ldstr    aExpanded// "expanded"
0xc688c  ldstr    aTrue// "true"
0xc6891  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xc6896  ldarg.0
0xc6897  ldloc.3
0xc6898  ldarg.1
0xc6899  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::OutputComponents(class [System.Xml]System.Xml.XmlWriter treeXmlWriter, string solutionId)
0xc689e  ldloc.3
0xc689f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xc68a4  ldloc.3
0xc68a5  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xc68aa  ldloc.3
0xc68ab  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0xc68b0  leave.s  loc_C68BC
0xc68b2  ldloc.3
0xc68b3  brfalse.s loc_C68BB
0xc68b5  ldloc.3
0xc68b6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc68bb  endfinally
0xc68bc  ldloc.0
0xc68bd  callvirt instance string [mscorlib]System.Object::ToString()
0xc68c2  ret
```
