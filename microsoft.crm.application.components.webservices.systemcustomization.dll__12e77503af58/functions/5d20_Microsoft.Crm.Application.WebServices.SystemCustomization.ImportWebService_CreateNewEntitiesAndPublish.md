# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::CreateNewEntitiesAndPublish

- ea: `0x5d20`
- end: `0x5de8`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::CreateNewEntitiesAndPublish`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x57e0`

## callees

- `0x5d20`
- `0x5df0`
- `0x5ea0`
- `0x5ed0`
- `0x6960`

## string_xrefs

- `0x5d3c`: `CustomizationXml`

## pseudocode

```c

```

## disassembly

```asm
0x5d20  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x5d25  stloc.0
0x5d26  ldarg.1
0x5d27  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x5d2c  stloc.1
0x5d2d  br.s     loc_5DAB
0x5d2f  ldloc.1
0x5d30  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5d35  castclass [System.Xml]System.Xml.XmlNode
0x5d3a  stloc.2
0x5d3b  ldloc.2
0x5d3c  ldstr    aCustomizationx// "CustomizationXml"
0x5d41  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5d46  brfalse.s loc_5DAB
0x5d48  ldarg.0
0x5d49  ldloc.2
0x5d4a  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::CreateEntity(class [System.Xml]System.Xml.XmlNode entityNode)
0x5d4f  stloc.3
0x5d50  ldarg.0
0x5d51  ldloc.3
0x5d52  call     instance string Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::GetEntityUpdateXml(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity)
0x5d57  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x5d5c  stloc.s  4
0x5d5e  ldarg.0
0x5d5f  ldloc.s  4
0x5d61  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UpdateEntity(class [System.Xml]System.Xml.XmlDocument entityUpdateDoc)
0x5d66  ldloc.2
0x5d67  ldstr    aLogicalname// "LogicalName"
0x5d6c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5d71  stloc.s  5
0x5d73  ldloc.s  5
0x5d75  brtrue.s loc_5D92
0x5d77  ldloc.2
0x5d78  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x5d7d  ldstr    aLogicalname// "LogicalName"
0x5d82  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x5d87  stloc.s  5
0x5d89  ldloc.2
0x5d8a  ldloc.s  5
0x5d8c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x5d91  pop
0x5d92  ldloc.s  5
0x5d94  ldloc.3
0x5d95  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x5d9a  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x5d9f  ldloc.0
0x5da0  ldloc.3
0x5da1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x5da6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5dab  ldloc.1
0x5dac  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5db1  brtrue   loc_5D2F
0x5db6  leave.s  loc_5DCC
0x5db8  ldloc.1
0x5db9  isinst   [mscorlib]System.IDisposable
0x5dbe  stloc.s  6
0x5dc0  ldloc.s  6
0x5dc2  brfalse.s loc_5DCB
0x5dc4  ldloc.s  6
0x5dc6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5dcb  endfinally
0x5dcc  ldarg.1
0x5dcd  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x5dd2  ldc.i4.0
0x5dd3  ble.s    loc_5DE7
0x5dd5  ldarg.0
0x5dd6  ldarg.1
0x5dd7  ldc.i4.0
0x5dd8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x5ddd  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x5de2  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::PublishAllCustomizations(class [System.Xml]System.Xml.XmlDocument mapDoc)
0x5de7  ret
```
