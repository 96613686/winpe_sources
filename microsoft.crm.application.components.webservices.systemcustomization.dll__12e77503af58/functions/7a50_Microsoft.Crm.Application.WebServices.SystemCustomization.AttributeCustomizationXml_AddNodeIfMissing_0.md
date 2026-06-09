# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::AddNodeIfMissing_0

- ea: `0x7a50`
- end: `0x7a85`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::AddNodeIfMissing_0`
- size: `53`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x76e0`
- `0x7780`
- `0x7a40`

## callees

- `0x7a50`

## pseudocode

```c

```

## disassembly

```asm
0x7a50  ldarg.0
0x7a51  ldarg.1
0x7a52  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x7a57  stloc.0
0x7a58  ldloc.0
0x7a59  brfalse.s loc_7A5D
0x7a5b  ldloc.0
0x7a5c  ret
0x7a5d  ldarg.0
0x7a5e  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x7a63  ldarg.1
0x7a64  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x7a69  stloc.0
0x7a6a  ldarg.2
0x7a6b  brfalse.s loc_7A7B
0x7a6d  ldarg.2
0x7a6e  callvirt instance string [mscorlib]System.Object::ToString()
0x7a73  stloc.1
0x7a74  ldloc.0
0x7a75  ldloc.1
0x7a76  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x7a7b  ldarg.0
0x7a7c  ldloc.0
0x7a7d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x7a82  pop
0x7a83  ldloc.0
0x7a84  ret
```
