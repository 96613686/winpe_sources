# Microsoft.Crm.MetadataService.Utility.ClientMetadataHelper::GetSiteMapSubAreaDescriptor

- ea: `0x30c50`
- end: `0x30e61`
- name: `Microsoft.Crm.MetadataService.Utility.ClientMetadataHelper::GetSiteMapSubAreaDescriptor`
- size: `529`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x30b90`

## callees

- `0x30c50`
- `0x21a490`

## string_xrefs

- `0x30d65`: `GetStartedPanePath`
- `0x30d79`: `GetStartedPanePath`
- `0x30d8f`: `GetStartedPanePathAdmin`
- `0x30da3`: `GetStartedPanePathAdmin`
- `0x30db9`: `GetStartedPanePathAdminOutlook`
- `0x30dcd`: `GetStartedPanePathAdminOutlook`
- `0x30de3`: `GetStartedPanePathOutlook`
- `0x30df7`: `GetStartedPanePathOutlook`

## pseudocode

```c

```

## disassembly

```asm
0x30c50  newobj   instance void Microsoft.Crm.ObjectModel.Descriptors.SiteMapSubAreaDescriptor::.ctor()
0x30c55  stloc.0
0x30c56  ldarg.0
0x30c57  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x30c5c  stloc.1
0x30c5d  ldloc.1
0x30c5e  brfalse  loc_30E5F
0x30c63  ldloc.0
0x30c64  ldloc.1
0x30c65  ldstr    aId_0// "Id"
0x30c6a  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x30c6f  brtrue.s loc_30C78
0x30c71  ldsfld   string [mscorlib]System.String::Empty
0x30c76  br.s     loc_30C88
0x30c78  ldloc.1
0x30c79  ldstr    aId_0// "Id"
0x30c7e  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x30c83  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x30c88  stfld    string Microsoft.Crm.ObjectModel.Descriptors.SiteMapSubAreaDescriptor::Id
0x30c8d  ldc.i4.0
0x30c8e  stloc.2
0x30c8f  ldloc.1
0x30c90  ldstr    aAvailableoffli// "AvailableOffline"
0x30c95  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x30c9a  brfalse.s loc_30CB4
0x30c9c  ldloc.1
0x30c9d  ldstr    aAvailableoffli// "AvailableOffline"
0x30ca2  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x30ca7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x30cac  ldloca.s 2
0x30cae  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x30cb3  pop
0x30cb4  ldloc.0
0x30cb5  ldloc.2
0x30cb6  stfld    bool Microsoft.Crm.ObjectModel.Descriptors.SiteMapSubAreaDescriptor::AvailableOffline
0x30cbb  ldloc.0
0x30cbc  ldloc.1
0x30cbd  ldstr    aIcon// "Icon"
0x30cc2  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x30cc7  brtrue.s loc_30CD0
0x30cc9  ldsfld   string [mscorlib]System.String::Empty
0x30cce  br.s     loc_30CE0
0x30cd0  ldloc.1
0x30cd1  ldstr    aIcon// "Icon"
0x30cd6  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x30cdb  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x30ce0  stfld    string Microsoft.Crm.ObjectModel.Descriptors.SiteMapSubAreaDescriptor::Icon
0x30ce5  ldloc.0
0x30ce6  ldloc.1
0x30ce7  ldstr    aUrl_0// "Url"
0x30cec  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x30cf1  brtrue.s loc_30CFA
0x30cf3  ldsfld   string [mscorlib]System.String::Empty
0x30cf8  br.s     loc_30D0A
0x30cfa  ldloc.1
0x30cfb  ldstr    aUrl_0// "Url"
0x30d00  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x30d05  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x30d0a  stfld    string Microsoft.Crm.ObjectModel.Descriptors.SiteMapSubAreaDescriptor::Url
0x30d0f  ldloc.0
0x30d10  ldloc.1
0x30d11  ldstr    aDefaultdashboa// "DefaultDashboard"
0x30d16  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x30d1b  brtrue.s loc_30D24
0x30d1d  ldsfld   string [mscorlib]System.String::Empty
0x30d22  br.s     loc_30D34
0x30d24  ldloc.1
0x30d25  ldstr    aDefaultdashboa// "DefaultDashboard"
0x30d2a  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x30d2f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x30d34  stfld    string Microsoft.Crm.ObjectModel.Descriptors.SiteMapSubAreaDescriptor::DefaultDashboard
0x30d39  ldloc.0
0x30d3a  ldloc.1
0x30d3b  ldstr    aEntity// "Entity"
0x30d40  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x30d45  brtrue.s loc_30D4E
0x30d47  ldsfld   string [mscorlib]System.String::Empty
0x30d4c  br.s     loc_30D5E
0x30d4e  ldloc.1
0x30d4f  ldstr    aEntity// "Entity"
0x30d54  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x30d59  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x30d5e  stfld    string Microsoft.Crm.ObjectModel.Descriptors.SiteMapSubAreaDescriptor::Entity
0x30d63  ldloc.0
0x30d64  ldloc.1
0x30d65  ldstr    aGetstartedpane// "GetStartedPanePath"
0x30d6a  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x30d6f  brtrue.s loc_30D78
0x30d71  ldsfld   string [mscorlib]System.String::Empty
0x30d76  br.s     loc_30D88
0x30d78  ldloc.1
0x30d79  ldstr    aGetstartedpane// "GetStartedPanePath"
0x30d7e  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x30d83  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x30d88  stfld    string Microsoft.Crm.ObjectModel.Descriptors.SiteMapSubAreaDescriptor::GetStartedPanePath
0x30d8d  ldloc.0
0x30d8e  ldloc.1
0x30d8f  ldstr    aGetstartedpane_0// "GetStartedPanePathAdmin"
0x30d94  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x30d99  brtrue.s loc_30DA2
0x30d9b  ldsfld   string [mscorlib]System.String::Empty
0x30da0  br.s     loc_30DB2
0x30da2  ldloc.1
0x30da3  ldstr    aGetstartedpane_0// "GetStartedPanePathAdmin"
0x30da8  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x30dad  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x30db2  stfld    string Microsoft.Crm.ObjectModel.Descriptors.SiteMapSubAreaDescriptor::GetStartedPanePathAdmin
0x30db7  ldloc.0
0x30db8  ldloc.1
0x30db9  ldstr    aGetstartedpane_1// "GetStartedPanePathAdminOutlook"
0x30dbe  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x30dc3  brtrue.s loc_30DCC
0x30dc5  ldsfld   string [mscorlib]System.String::Empty
0x30dca  br.s     loc_30DDC
0x30dcc  ldloc.1
0x30dcd  ldstr    aGetstartedpane_1// "GetStartedPanePathAdminOutlook"
0x30dd2  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x30dd7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x30ddc  stfld    string Microsoft.Crm.ObjectModel.Descriptors.SiteMapSubAreaDescriptor::GetStartedPanePathAdminOutlook
0x30de1  ldloc.0
0x30de2  ldloc.1
0x30de3  ldstr    aGetstartedpane_2// "GetStartedPanePathOutlook"
0x30de8  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x30ded  brtrue.s loc_30DF6
0x30def  ldsfld   string [mscorlib]System.String::Empty
0x30df4  br.s     loc_30E06
0x30df6  ldloc.1
0x30df7  ldstr    aGetstartedpane_2// "GetStartedPanePathOutlook"
0x30dfc  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x30e01  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x30e06  stfld    string Microsoft.Crm.ObjectModel.Descriptors.SiteMapSubAreaDescriptor::GetStartedPanePathOutlook
0x30e0b  ldloc.0
0x30e0c  ldloc.1
0x30e0d  ldstr    aOutlookshortcu// "OutlookShortcutIcon"
0x30e12  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x30e17  brtrue.s loc_30E20
0x30e19  ldsfld   string [mscorlib]System.String::Empty
0x30e1e  br.s     loc_30E30
0x30e20  ldloc.1
0x30e21  ldstr    aOutlookshortcu// "OutlookShortcutIcon"
0x30e26  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x30e2b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x30e30  stfld    string Microsoft.Crm.ObjectModel.Descriptors.SiteMapSubAreaDescriptor::OutlookShortcutIcon
0x30e35  ldloc.0
0x30e36  ldloc.1
0x30e37  ldstr    aVectoricon// "VectorIcon"
0x30e3c  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x30e41  brtrue.s loc_30E4A
0x30e43  ldsfld   string [mscorlib]System.String::Empty
0x30e48  br.s     loc_30E5A
0x30e4a  ldloc.1
0x30e4b  ldstr    aVectoricon// "VectorIcon"
0x30e50  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x30e55  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x30e5a  stfld    string Microsoft.Crm.ObjectModel.Descriptors.SiteMapSubAreaDescriptor::VectorIcon
0x30e5f  ldloc.0
0x30e60  ret
```
