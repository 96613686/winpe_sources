# Microsoft.Crm.Metadata.AttributeInfo::GetXmlNode

- ea: `0x189f0`
- end: `0x18ad7`
- name: `Microsoft.Crm.Metadata.AttributeInfo::GetXmlNode`
- size: `231`
- prototype: ``
- caller_count: `10`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x19b70`
- `0x2bfc0`
- `0x2c2a0`
- `0x43370`
- `0x43670`
- `0x43a70`
- `0x44180`
- `0x446f0`
- `0x4a4f0`
- `0x58d80`

## callees

- `0x18470`
- `0x18570`
- `0x185b0`
- `0x185d0`
- `0x189f0`

## string_xrefs

- `0x18a74`: `recommended`

## pseudocode

```c

```

## disassembly

```asm
0x189f0  ldarg.1
0x189f1  ldstr    aField// "field"
0x189f6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x189fb  stloc.0
0x189fc  ldarg.0
0x189fd  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::attributeData
0x18a02  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_LogicalName()
0x18a07  ldstr    aLogicalname_1// "logicalName"
0x18a0c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x18a11  ldloc.0
0x18a12  ldstr    aName// "name"
0x18a17  ldarg.0
0x18a18  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::attributeData
0x18a1d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_LogicalName()
0x18a22  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x18a27  ldloc.0
0x18a28  ldarg.0
0x18a29  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.AttributeInfo::get_DisplayNames()
0x18a2e  ldarg.1
0x18a2f  callvirt instance class [System.Xml]System.Xml.XmlNode [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::GetXmlNode(class [System.Xml]System.Xml.XmlDocument)
0x18a34  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x18a39  pop
0x18a3a  ldarg.0
0x18a3b  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel> Microsoft.Crm.Metadata.AttributeInfo::get_RequiredLevel()
0x18a40  stloc.3
0x18a41  ldloca.s 3
0x18a43  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel>::get_HasValue()
0x18a48  brfalse.s loc_18A84
0x18a4a  ldloca.s 3
0x18a4c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel>::GetValueOrDefault()
0x18a51  stloc.s  4
0x18a53  ldloc.s  4
0x18a55  switch   loc_18A6C, loc_18A7C, loc_18A7C, loc_18A74
0x18a6a  br.s     loc_18A84
0x18a6c  ldstr    aNone// "none"
0x18a71  stloc.1
0x18a72  br.s     loc_18A8F
0x18a74  ldstr    aRecommended// "recommended"
0x18a79  stloc.1
0x18a7a  br.s     loc_18A8F
0x18a7c  ldstr    aRequired// "required"
0x18a81  stloc.1
0x18a82  br.s     loc_18A8F
0x18a84  ldstr    aInvalidRequire// "Invalid requirement level"
0x18a89  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x18a8e  throw
0x18a8f  ldloc.0
0x18a90  ldstr    aRequiredlevel// "requiredlevel"
0x18a95  ldloc.1
0x18a96  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x18a9b  ldarg.0
0x18a9c  call     instance bool Microsoft.Crm.Metadata.AttributeInfo::get_Locked()
0x18aa1  brfalse.s loc_18AB3
0x18aa3  ldloc.0
0x18aa4  ldstr    aLocked// "locked"
0x18aa9  ldstr    aTrue// "true"
0x18aae  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x18ab3  ldarg.0
0x18ab4  call     instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeIMEMode Microsoft.Crm.Metadata.AttributeInfo::get_IMEMode()
0x18ab9  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeIMEMode
0x18abe  ldstr    aG// "g"
0x18ac3  call     instance string [mscorlib]System.Enum::ToString(string)
0x18ac8  stloc.2
0x18ac9  ldloc.0
0x18aca  ldstr    aImemode// "imemode"
0x18acf  ldloc.2
0x18ad0  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x18ad5  ldloc.0
0x18ad6  ret
```
