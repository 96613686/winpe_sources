# Microsoft.Crm.Metadata.AttributeLookupValueDescription::FillPropertiesFromXml_0

- ea: `0x27c10`
- end: `0x27cc1`
- name: `Microsoft.Crm.Metadata.AttributeLookupValueDescription::FillPropertiesFromXml_0`
- size: `177`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x27c10`
- `0x27cf0`
- `0x27d10`
- `0x27d30`

## string_xrefs

- `0x27c47`: `Attribute lookup value XML must contain the attribute lookup value id`
- `0x27cb5`: `Attribute lookup value XML must contain the AttributeId property`

## pseudocode

```c

```

## disassembly

```asm
0x27c10  ldarg.1
0x27c11  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x27c16  ldstr    aId// "id"
0x27c1b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x27c20  brfalse.s loc_27C44
0x27c22  ldarg.0
0x27c23  ldarg.1
0x27c24  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x27c29  ldstr    aId// "id"
0x27c2e  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x27c33  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x27c38  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x27c3d  callvirt instance void Microsoft.Crm.Metadata.AttributeLookupValueDescription::set_AttributeLookupValueId(valuetype [mscorlib]System.Guid value)
0x27c42  br.s     loc_27C52
0x27c44  ldarg.2
0x27c45  brfalse.s loc_27C52
0x27c47  ldstr    aAttributeLooku// "Attribute lookup value XML must contain"...
0x27c4c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x27c51  throw
0x27c52  ldarg.1
0x27c53  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x27c58  brfalse.s loc_27C75
0x27c5a  ldarg.0
0x27c5b  ldarg.1
0x27c5c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x27c61  callvirt instance string [mscorlib]System.String::Trim()
0x27c66  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x27c6b  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x27c70  callvirt instance void Microsoft.Crm.Metadata.AttributeLookupValueDescription::set_EntityId(int32 value)
0x27c75  ldarg.1
0x27c76  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x27c7b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x27c80  ldstr    aAttributeid// "AttributeId"
0x27c85  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x27c8a  brfalse.s loc_27CB2
0x27c8c  ldarg.0
0x27c8d  ldarg.1
0x27c8e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x27c93  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x27c98  ldstr    aAttributeid// "AttributeId"
0x27c9d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x27ca2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x27ca7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x27cac  callvirt instance void Microsoft.Crm.Metadata.AttributeLookupValueDescription::set_AttributeId(valuetype [mscorlib]System.Guid value)
0x27cb1  ret
0x27cb2  ldarg.2
0x27cb3  brfalse.s loc_27CC0
0x27cb5  ldstr    aAttributeLooku_0// "Attribute lookup value XML must contain"...
0x27cba  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x27cbf  throw
0x27cc0  ret
```
