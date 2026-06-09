# Microsoft.Crm.ServiceBus.WebhookClient::ExtractKeyValuePairs

- ea: `0x61c0`
- end: `0x6327`
- name: `Microsoft.Crm.ServiceBus.WebhookClient::ExtractKeyValuePairs`
- size: `359`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x60b0`
- `0x63e0`

## callees

- `0x61c0`

## pseudocode

```c

```

## disassembly

```asm
0x61c0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x61c5  stloc.0
0x61c6  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x61cb  dup
0x61cc  ldnull
0x61cd  callvirt instance void [System.Xml]System.Xml.XmlDocument::set_XmlResolver(class [System.Xml]System.Xml.XmlResolver)
0x61d2  dup
0x61d3  ldarg.1
0x61d4  callvirt instance void [System.Xml]System.Xml.XmlDocument::LoadXml(string)
0x61d9  ldstr    aSettings// "settings"
0x61de  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlDocument::GetElementsByTagName(string)
0x61e3  stloc.1
0x61e4  ldloc.1
0x61e5  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x61ea  ldc.i4.1
0x61eb  bne.un   loc_631A
0x61f0  ldloc.1
0x61f1  ldc.i4.0
0x61f2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x61f7  callvirt instance bool [System.Xml]System.Xml.XmlNode::get_HasChildNodes()
0x61fc  brfalse  loc_630F
0x6201  ldloc.1
0x6202  ldc.i4.0
0x6203  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x6208  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x620d  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x6212  stloc.2
0x6213  br       loc_62EE
0x6218  ldloc.2
0x6219  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x621e  castclass [System.Xml]System.Xml.XmlNode
0x6223  stloc.3
0x6224  ldloc.3
0x6225  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x622a  ldstr    aSetting// "setting"
0x622f  ldc.i4.5
0x6230  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x6235  brfalse.s loc_62A9
0x6237  ldloc.3
0x6238  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x623d  brfalse.s loc_62A9
0x623f  ldloc.3
0x6240  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x6245  callvirt instance int32 [System.Xml]System.Xml.XmlNamedNodeMap::get_Count()
0x624a  ldc.i4.2
0x624b  bne.un.s loc_62A9
0x624d  ldloc.3
0x624e  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x6253  ldstr    aName// "name"
0x6258  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x625d  brfalse.s loc_62A9
0x625f  ldloc.3
0x6260  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x6265  ldstr    aName// "name"
0x626a  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x626f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x6274  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x6279  brtrue.s loc_62A9
0x627b  ldloc.3
0x627c  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x6281  ldstr    aValue// "value"
0x6286  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x628b  brfalse.s loc_62A9
0x628d  ldloc.3
0x628e  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x6293  ldstr    aValue// "value"
0x6298  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x629d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x62a2  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x62a7  brfalse.s loc_62B4
0x62a9  ldstr    aInvalidSetting// "Invalid 'setting' node found in authVal"...
0x62ae  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x62b3  throw
0x62b4  ldloc.0
0x62b5  ldloc.3
0x62b6  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x62bb  ldstr    aName// "name"
0x62c0  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x62c5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x62ca  callvirt instance string [mscorlib]System.String::Trim()
0x62cf  ldloc.3
0x62d0  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x62d5  ldstr    aValue// "value"
0x62da  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x62df  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x62e4  callvirt instance string [mscorlib]System.String::Trim()
0x62e9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x62ee  ldloc.2
0x62ef  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x62f4  brtrue   loc_6218
0x62f9  leave.s  loc_6325
0x62fb  ldloc.2
0x62fc  isinst   [mscorlib]System.IDisposable
0x6301  stloc.s  4
0x6303  ldloc.s  4
0x6305  brfalse.s loc_630E
0x6307  ldloc.s  4
0x6309  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x630e  endfinally
0x630f  ldstr    aAtleastOneSett// "Atleast one 'setting' node is expected "...
0x6314  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x6319  throw
0x631a  ldstr    aSettingsNodeIs// "'settings' node is expected for authVal"...
0x631f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x6324  throw
0x6325  ldloc.0
0x6326  ret
```
