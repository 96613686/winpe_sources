# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::GetCompleteCustomizationXml

- ea: `0x76e0`
- end: `0x7776`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::GetCompleteCustomizationXml`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6240`

## callees

- `0x7780`
- `0x7a50`

## pseudocode

```c

```

## disassembly

```asm
0x76e0  ldarg.0
0x76e1  ldstr    aAttribute// "attribute"
0x76e6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x76eb  dup
0x76ec  ldstr    aDisplayname// "displayname"
0x76f1  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x76f6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x76fb  ldstr    aAZaZ09// "[^a-zA-Z_0-9]"
0x7700  ldsfld   string [mscorlib]System.String::Empty
0x7705  call     string [System]System.Text.RegularExpressions.Regex::Replace(string, string, string)
0x770a  stloc.0
0x770b  dup
0x770c  ldstr    aSchemaname// "schemaname"
0x7711  ldloc.0
0x7712  call     class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::AddNodeIfMissing(class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, object nodeValue)
0x7717  pop
0x7718  dup
0x7719  ldstr    aEntityid// "entityid"
0x771e  ldarg.1
0x771f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x7724  box      [mscorlib]System.Guid
0x7729  call     class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::AddNodeIfMissing(class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, object nodeValue)
0x772e  pop
0x772f  dup
0x7730  ldstr    aReqlevel// "reqlevel"
0x7735  ldc.i4.0
0x7736  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel
0x773b  call     class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::AddNodeIfMissing(class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, object nodeValue)
0x7740  pop
0x7741  dup
0x7742  ldstr    aImemode// "imemode"
0x7747  ldc.i4.0
0x7748  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeIMEMode
0x774d  call     class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::AddNodeIfMissing(class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, object nodeValue)
0x7752  pop
0x7753  dup
0x7754  ldstr    aSearchable// "searchable"
0x7759  ldc.i4.1
0x775a  box      [mscorlib]System.Int32
0x775f  call     class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::AddNodeIfMissing(class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, object nodeValue)
0x7764  pop
0x7765  dup
0x7766  ldstr    aType// "type"
0x776b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x7770  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::AddCustomAttributeTypeDefaults(class [System.Xml]System.Xml.XmlElement typeElement)
0x7775  ret
```
