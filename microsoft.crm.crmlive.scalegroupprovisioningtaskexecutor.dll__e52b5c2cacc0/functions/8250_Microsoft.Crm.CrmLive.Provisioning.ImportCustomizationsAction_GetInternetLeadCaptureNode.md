# Microsoft.Crm.CrmLive.Provisioning.ImportCustomizationsAction::GetInternetLeadCaptureNode

- ea: `0x8250`
- end: `0x8361`
- name: `Microsoft.Crm.CrmLive.Provisioning.ImportCustomizationsAction::GetInternetLeadCaptureNode`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x81f0`

## string_xrefs

- `0x8303`: `CheckExtensionProperty`
- `0x8328`: `Privilege`
- `0x8335`: `Privilege`

## pseudocode

```c

```

## disassembly

```asm
0x8250  ldarg.0
0x8251  ldc.i4.1
0x8252  ldstr    aSubarea// "SubArea"
0x8257  ldnull
0x8258  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x825d  ldarg.0
0x825e  ldstr    aId// "Id"
0x8263  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x8268  stloc.0
0x8269  ldloc.0
0x826a  ldarg.1
0x826b  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x8270  dup
0x8271  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x8276  ldloc.0
0x8277  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x827c  pop
0x827d  ldarg.0
0x827e  ldstr    aResourceid// "ResourceId"
0x8283  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x8288  stloc.0
0x8289  ldloc.0
0x828a  ldarg.2
0x828b  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x8290  dup
0x8291  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x8296  ldloc.0
0x8297  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x829c  pop
0x829d  ldarg.0
0x829e  ldstr    aIcon// "Icon"
0x82a3  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x82a8  stloc.0
0x82a9  ldloc.0
0x82aa  ldarg.3
0x82ab  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x82b0  dup
0x82b1  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x82b6  ldloc.0
0x82b7  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x82bc  pop
0x82bd  ldarg.0
0x82be  ldstr    aUrl// "Url"
0x82c3  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x82c8  stloc.0
0x82c9  ldloc.0
0x82ca  ldarg.s  4
0x82cc  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x82d1  dup
0x82d2  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x82d7  ldloc.0
0x82d8  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x82dd  pop
0x82de  ldarg.0
0x82df  ldstr    aAvailableoffli// "AvailableOffline"
0x82e4  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x82e9  stloc.0
0x82ea  ldloc.0
0x82eb  ldstr    aFalse// "false"
0x82f0  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x82f5  dup
0x82f6  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x82fb  ldloc.0
0x82fc  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x8301  pop
0x8302  ldarg.0
0x8303  ldstr    aCheckextension// "CheckExtensionProperty"
0x8308  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x830d  stloc.0
0x830e  ldloc.0
0x830f  ldstr    aInternetleadca// "InternetLeadCaptureOsdpCheck"
0x8314  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x8319  dup
0x831a  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x831f  ldloc.0
0x8320  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x8325  pop
0x8326  ldarg.0
0x8327  ldc.i4.1
0x8328  ldstr    aPrivilege// "Privilege"
0x832d  ldnull
0x832e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x8333  stloc.1
0x8334  ldarg.0
0x8335  ldstr    aPrivilege// "Privilege"
0x833a  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x833f  stloc.0
0x8340  ldloc.0
0x8341  ldstr    aUseinternetmar// "UseInternetMarketing"
0x8346  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x834b  ldloc.1
0x834c  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x8351  ldloc.0
0x8352  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x8357  pop
0x8358  dup
0x8359  ldloc.1
0x835a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x835f  pop
0x8360  ret
```
