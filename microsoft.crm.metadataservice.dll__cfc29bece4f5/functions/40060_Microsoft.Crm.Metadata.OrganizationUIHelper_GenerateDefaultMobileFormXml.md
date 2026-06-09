# Microsoft.Crm.Metadata.OrganizationUIHelper::GenerateDefaultMobileFormXml

- ea: `0x40060`
- end: `0x403c6`
- name: `Microsoft.Crm.Metadata.OrganizationUIHelper::GenerateDefaultMobileFormXml`
- size: `870`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18490`
- `0x2cb30`
- `0x2d1b0`
- `0x40060`

## string_xrefs

- `0x40241`: `classid`
- `0x402e2`: `classid`
- `0x4037f`: `classid`

## pseudocode

```c

```

## disassembly

```asm
0x40060  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument()
0x40065  stloc.0
0x40066  ldloc.0
0x40067  ldstr    aForm// "form"
0x4006c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x40071  stloc.1
0x40072  ldloc.0
0x40073  ldstr    aTabs// "tabs"
0x40078  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x4007d  stloc.2
0x4007e  ldloc.1
0x4007f  ldloc.2
0x40080  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x40085  pop
0x40086  ldloc.0
0x40087  ldstr    aTab// "tab"
0x4008c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x40091  stloc.3
0x40092  ldloc.3
0x40093  ldstr    aName// "name"
0x40098  ldstr    aGeneral// "general"
0x4009d  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x400a2  ldloc.3
0x400a3  ldstr    aVerticallayout// "verticallayout"
0x400a8  ldstr    aTrue// "true"
0x400ad  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x400b2  ldloc.3
0x400b3  ldstr    aId// "id"
0x400b8  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x400bd  stloc.s  0xE
0x400bf  ldloca.s 0xE
0x400c1  ldstr    aB// "B"
0x400c6  call     instance string [mscorlib]System.Guid::ToString(string)
0x400cb  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x400d0  ldloc.3
0x400d1  ldstr    aIsuserdefined// "IsUserDefined"
0x400d6  ldstr    a0_1// "0"
0x400db  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x400e0  ldloc.2
0x400e1  ldloc.3
0x400e2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x400e7  pop
0x400e8  ldloc.0
0x400e9  ldstr    aColumns// "columns"
0x400ee  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x400f3  stloc.s  4
0x400f5  ldloc.0
0x400f6  ldstr    aColumn// "column"
0x400fb  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x40100  stloc.s  5
0x40102  ldloc.s  5
0x40104  ldstr    aWidth// "width"
0x40109  ldstr    a100// "100%"
0x4010e  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x40113  ldloc.3
0x40114  ldloc.s  4
0x40116  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x4011b  pop
0x4011c  ldloc.s  4
0x4011e  ldloc.s  5
0x40120  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x40125  pop
0x40126  ldloc.0
0x40127  ldstr    aSections// "sections"
0x4012c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x40131  stloc.s  6
0x40133  ldloc.s  5
0x40135  ldloc.s  6
0x40137  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x4013c  pop
0x4013d  ldloc.0
0x4013e  ldstr    aSection// "section"
0x40143  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x40148  stloc.s  7
0x4014a  ldloc.s  7
0x4014c  ldstr    aName// "name"
0x40151  ldstr    aAccountInforma// "account information"
0x40156  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x4015b  ldloc.s  7
0x4015d  ldstr    aShowlabel// "showlabel"
0x40162  ldstr    aFalse// "false"
0x40167  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x4016c  ldloc.s  7
0x4016e  ldstr    aShowbar// "showbar"
0x40173  ldstr    aFalse// "false"
0x40178  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x4017d  ldloc.s  7
0x4017f  ldstr    aId// "id"
0x40184  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x40189  stloc.s  0xE
0x4018b  ldloca.s 0xE
0x4018d  ldstr    aB// "B"
0x40192  call     instance string [mscorlib]System.Guid::ToString(string)
0x40197  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x4019c  ldloc.s  7
0x4019e  ldstr    aIsuserdefined// "IsUserDefined"
0x401a3  ldstr    a0_1// "0"
0x401a8  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x401ad  ldloc.s  6
0x401af  ldloc.s  7
0x401b1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x401b6  pop
0x401b7  ldloc.0
0x401b8  ldstr    aRows// "rows"
0x401bd  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x401c2  stloc.s  8
0x401c4  ldloc.s  7
0x401c6  ldloc.s  8
0x401c8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x401cd  pop
0x401ce  ldloc.0
0x401cf  ldstr    aRow// "row"
0x401d4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x401d9  stloc.s  9
0x401db  ldloc.s  8
0x401dd  ldloc.s  9
0x401df  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x401e4  pop
0x401e5  ldloc.0
0x401e6  ldstr    aCell// "cell"
0x401eb  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x401f0  stloc.s  0xA
0x401f2  ldloc.s  0xA
0x401f4  ldstr    aId// "id"
0x401f9  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x401fe  stloc.s  0xE
0x40200  ldloca.s 0xE
0x40202  ldstr    aB// "B"
0x40207  call     instance string [mscorlib]System.Guid::ToString(string)
0x4020c  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x40211  ldloc.0
0x40212  ldstr    aControl// "control"
0x40217  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x4021c  stloc.s  0xB
0x4021e  ldloc.s  0xB
0x40220  ldstr    aId// "id"
0x40225  ldarg.1
0x40226  callvirt instance class Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Metadata.EntityCreateInfo::get_PrimaryField()
0x4022b  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x40230  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x40235  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x4023a  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x4023f  ldloc.s  0xB
0x40241  ldstr    aClassid// "classid"
0x40246  ldstr    a4273edbdAc1d40// "{4273EDBD-AC1D-40d3-9FB2-095C621B552D}"
0x4024b  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x40250  ldloc.s  0xB
0x40252  ldstr    aDatafieldname// "datafieldname"
0x40257  ldarg.1
0x40258  callvirt instance class Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Metadata.EntityCreateInfo::get_PrimaryField()
0x4025d  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x40262  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x40267  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x4026c  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x40271  ldloc.s  0xB
0x40273  ldstr    aDisabled// "disabled"
0x40278  ldstr    aFalse// "false"
0x4027d  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x40282  ldloc.s  0xA
0x40284  ldloc.s  0xB
0x40286  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x4028b  pop
0x4028c  ldloc.s  9
0x4028e  ldloc.s  0xA
0x40290  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x40295  pop
0x40296  ldloc.0
0x40297  ldstr    aCell// "cell"
0x4029c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x402a1  stloc.s  0xC
0x402a3  ldloc.s  0xC
0x402a5  ldstr    aId// "id"
0x402aa  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x402af  stloc.s  0xE
0x402b1  ldloca.s 0xE
0x402b3  ldstr    aB// "B"
0x402b8  call     instance string [mscorlib]System.Guid::ToString(string)
0x402bd  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x402c2  ldloc.0
0x402c3  ldstr    aControl// "control"
0x402c8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x402cd  stloc.s  0xD
0x402cf  ldloc.s  0xD
0x402d1  ldstr    aId// "id"
0x402d6  ldstr    aStatecode_1// "statecode"
0x402db  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x402e0  ldloc.s  0xD
0x402e2  ldstr    aClassid// "classid"
0x402e7  ldstr    a3ef3998822bb4f// "{3EF39988-22BB-4f0b-BBBE-64B5A3748AEE}"
0x402ec  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x402f1  ldloc.s  0xD
0x402f3  ldstr    aDatafieldname// "datafieldname"
0x402f8  ldstr    aStatecode_1// "statecode"
0x402fd  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x40302  ldloc.s  0xD
0x40304  ldstr    aDisabled// "disabled"
0x40309  ldstr    aFalse// "false"
0x4030e  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x40313  ldloc.s  0xC
0x40315  ldloc.s  0xD
0x40317  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x4031c  pop
0x4031d  ldloc.s  9
0x4031f  ldloc.s  0xC
0x40321  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x40326  pop
0x40327  ldc.i4.1
0x40328  ldarg.1
0x40329  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes Microsoft.Crm.Metadata.EntityCreateInfo::get_OwnershipTypeMask()
0x4032e  bne.un   loc_403C4
0x40333  ldloc.0
0x40334  ldstr    aCell// "cell"
0x40339  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x4033e  stloc.s  0xF
0x40340  ldloc.s  0xF
0x40342  ldstr    aId// "id"
0x40347  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x4034c  stloc.s  0xE
0x4034e  ldloca.s 0xE
0x40350  ldstr    aB// "B"
0x40355  call     instance string [mscorlib]System.Guid::ToString(string)
0x4035a  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x4035f  ldloc.0
0x40360  ldstr    aControl// "control"
0x40365  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x4036a  stloc.s  0x10
0x4036c  ldloc.s  0x10
0x4036e  ldstr    aId// "id"
0x40373  ldstr    aOwnerid// "ownerid"
0x40378  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x4037d  ldloc.s  0x10
0x4037f  ldstr    aClassid// "classid"
0x40384  ldstr    a270bd3dbD9af47// "{270BD3DB-D9AF-4782-9025-509E298DEC0A}"
0x40389  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x4038e  ldloc.s  0x10
0x40390  ldstr    aDatafieldname// "datafieldname"
0x40395  ldstr    aOwnerid// "ownerid"
0x4039a  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x4039f  ldloc.s  0x10
0x403a1  ldstr    aDisabled// "disabled"
0x403a6  ldstr    aFalse// "false"
0x403ab  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x403b0  ldloc.s  0xF
0x403b2  ldloc.s  0x10
0x403b4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x403b9  pop
0x403ba  ldloc.s  9
0x403bc  ldloc.s  0xF
0x403be  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x403c3  pop
0x403c4  ldloc.1
0x403c5  ret
```
