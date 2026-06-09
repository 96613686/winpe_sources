# Microsoft.Crm.Reporting.SRSReport::StoreOriginalCommandText

- ea: `0xeb0`
- end: `0xf5b`
- name: `Microsoft.Crm.Reporting.SRSReport::StoreOriginalCommandText`
- size: `171`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xbc0`
- `0xe90`

## callees

- `0xeb0`

## string_xrefs

- `0xf24`: `CommandText`
- `0xf3a`: `CommandText`

## pseudocode

```c

```

## disassembly

```asm
0xeb0  ldarg.2
0xeb1  ldstr    aDataset// "DataSet"
0xeb6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xebb  ldarg.2
0xebc  ldstr    aName// "Name"
0xec1  ldarg.1
0xec2  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xec7  ldstr    aName// "Name"
0xecc  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xed1  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xed6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xedb  ldarg.2
0xedc  ldstr    aTimeout// "Timeout"
0xee1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xee6  ldarg.1
0xee7  ldstr    aQuery// "Query"
0xeec  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0xef1  ldstr    aTimeout// "Timeout"
0xef6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0xefb  brfalse.s loc_F1D
0xefd  ldarg.2
0xefe  ldarg.1
0xeff  ldstr    aQuery// "Query"
0xf04  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0xf09  ldstr    aTimeout// "Timeout"
0xf0e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0xf13  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xf18  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteString(string)
0xf1d  ldarg.2
0xf1e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xf23  ldarg.2
0xf24  ldstr    aCommandtext// "CommandText"
0xf29  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xf2e  ldarg.2
0xf2f  ldarg.1
0xf30  ldstr    aQuery// "Query"
0xf35  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0xf3a  ldstr    aCommandtext// "CommandText"
0xf3f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0xf44  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xf49  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteString(string)
0xf4e  ldarg.2
0xf4f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xf54  ldarg.2
0xf55  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xf5a  ret
```
