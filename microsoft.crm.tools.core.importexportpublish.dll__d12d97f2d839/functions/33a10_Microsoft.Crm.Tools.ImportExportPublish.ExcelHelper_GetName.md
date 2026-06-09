# Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::GetName

- ea: `0x33a10`
- end: `0x33b0d`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::GetName`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x33530`

## callees

- `0x33a10`

## string_xrefs

- `0x33ac7`: `FieldSecurityProfile`
- `0x33a7f`: `PluginAssembly`
- `0x33aa3`: `ServiceEndpoint`
- `0x33ab5`: `template`
- `0x33a34`: `securityrole`

## pseudocode

```c

```

## disassembly

```asm
0x33a10  ldarg.1
0x33a11  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x33a16  ldstr    aLanguage// "language"
0x33a1b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x33a20  brfalse.s loc_33A28
0x33a22  ldsfld   string [mscorlib]System.String::Empty
0x33a27  ret
0x33a28  ldsfld   string [mscorlib]System.String::Empty
0x33a2d  stloc.0
0x33a2e  ldarg.1
0x33a2f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x33a34  ldstr    aSecurityrole_0// "securityrole"
0x33a39  call     bool [mscorlib]System.String::op_Equality(string, string)
0x33a3e  brtrue   loc_33AD3
0x33a43  ldarg.1
0x33a44  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x33a49  ldstr    aConnectionrole// "ConnectionRole"
0x33a4e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x33a53  brtrue.s loc_33AD3
0x33a55  ldarg.1
0x33a56  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x33a5b  ldstr    aWorkflow_1// "workflow"
0x33a60  call     bool [mscorlib]System.String::op_Equality(string, string)
0x33a65  brtrue.s loc_33AD3
0x33a67  ldarg.1
0x33a68  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x33a6d  ldstr    aPublishworkflo// "publishworkflow"
0x33a72  call     bool [mscorlib]System.String::op_Equality(string, string)
0x33a77  brtrue.s loc_33AD3
0x33a79  ldarg.1
0x33a7a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x33a7f  ldstr    aPluginassembly_0// "PluginAssembly"
0x33a84  call     bool [mscorlib]System.String::op_Equality(string, string)
0x33a89  brtrue.s loc_33AD3
0x33a8b  ldarg.1
0x33a8c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x33a91  ldstr    aSdkmessageproc// "SdkMessageProcessingStep"
0x33a96  call     bool [mscorlib]System.String::op_Equality(string, string)
0x33a9b  brtrue.s loc_33AD3
0x33a9d  ldarg.1
0x33a9e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x33aa3  ldstr    aServiceendpoin// "ServiceEndpoint"
0x33aa8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x33aad  brtrue.s loc_33AD3
0x33aaf  ldarg.1
0x33ab0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x33ab5  ldstr    aTemplate_0// "template"
0x33aba  call     bool [mscorlib]System.String::op_Equality(string, string)
0x33abf  brtrue.s loc_33AD3
0x33ac1  ldarg.1
0x33ac2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x33ac7  ldstr    aFieldsecurityp// "FieldSecurityProfile"
0x33acc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x33ad1  brfalse.s loc_33AF0
0x33ad3  ldarg.1
0x33ad4  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x33ad9  ldstr    aName// "name"
0x33ade  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x33ae3  stloc.1
0x33ae4  ldloc.1
0x33ae5  brfalse.s loc_33B0B
0x33ae7  ldloc.1
0x33ae8  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x33aed  stloc.0
0x33aee  br.s     loc_33B0B
0x33af0  ldarg.1
0x33af1  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x33af6  ldstr    aId// "id"
0x33afb  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x33b00  stloc.2
0x33b01  ldloc.2
0x33b02  brfalse.s loc_33B0B
0x33b04  ldloc.2
0x33b05  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x33b0a  stloc.0
0x33b0b  ldloc.0
0x33b0c  ret
```
