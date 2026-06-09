# Microsoft.Crm.Metadata.SiteMapHelper::AddEntityToArea

- ea: `0x5adc0`
- end: `0x5ae66`
- name: `Microsoft.Crm.Metadata.SiteMapHelper::AddEntityToArea`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x5ad30`

## callees

- `0x5adc0`

## string_xrefs

- `0x5ade5`: `Group[@Id = 'Extensions']`
- `0x5ae0f`: `Extensions`
- `0x5ae1f`: `Group_Extensions`

## pseudocode

```c

```

## disassembly

```asm
0x5adc0  ldarg.0
0x5adc1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5adc6  ldstr    aGroupSubareaEn// "Group/SubArea[@Entity = '{0}']"
0x5adcb  ldc.i4.1
0x5adcc  newarr   [mscorlib]System.Object
0x5add1  dup
0x5add2  ldc.i4.0
0x5add3  ldarg.1
0x5add4  stelem.ref
0x5add5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5adda  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x5addf  brtrue   loc_5AE64
0x5ade4  ldarg.0
0x5ade5  ldstr    aGroupIdExtensi// "Group[@Id = 'Extensions']"
0x5adea  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x5adef  castclass [System.Xml]System.Xml.XmlElement
0x5adf4  stloc.0
0x5adf5  ldloc.0
0x5adf6  brtrue.s loc_5AE31
0x5adf8  ldarg.0
0x5adf9  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x5adfe  ldstr    aGroup// "Group"
0x5ae03  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x5ae08  stloc.0
0x5ae09  ldloc.0
0x5ae0a  ldstr    aId_0// "Id"
0x5ae0f  ldstr    aExtensions// "Extensions"
0x5ae14  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5ae19  ldloc.0
0x5ae1a  ldstr    aResourceid// "ResourceId"
0x5ae1f  ldstr    aGroupExtension// "Group_Extensions"
0x5ae24  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5ae29  ldarg.0
0x5ae2a  ldloc.0
0x5ae2b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x5ae30  pop
0x5ae31  ldloc.0
0x5ae32  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x5ae37  ldstr    aSubarea// "SubArea"
0x5ae3c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x5ae41  stloc.1
0x5ae42  ldloc.1
0x5ae43  ldstr    aId_0// "Id"
0x5ae48  ldarg.1
0x5ae49  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5ae4e  ldloc.1
0x5ae4f  ldstr    aEntity_0// "Entity"
0x5ae54  ldarg.1
0x5ae55  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x5ae5a  ldloc.0
0x5ae5b  ldloc.1
0x5ae5c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x5ae61  pop
0x5ae62  ldc.i4.1
0x5ae63  ret
0x5ae64  ldc.i4.0
0x5ae65  ret
```
