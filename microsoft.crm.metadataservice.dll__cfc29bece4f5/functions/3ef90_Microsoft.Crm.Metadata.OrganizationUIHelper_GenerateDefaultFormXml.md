# Microsoft.Crm.Metadata.OrganizationUIHelper::GenerateDefaultFormXml

- ea: `0x3ef90`
- end: `0x3f85b`
- name: `Microsoft.Crm.Metadata.OrganizationUIHelper::GenerateDefaultFormXml`
- size: `2251`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x3dcb0`

## callees

- `0x18490`
- `0x2cb30`
- `0x2cb70`
- `0x2d050`
- `0x2d1b0`
- `0x3ef90`
- `0x403d0`
- `0x43df0`

## string_xrefs

- `0x3f6ea`: `scheduledend`
- `0x3f14a`: `classid`
- `0x3f1fd`: `classid`
- `0x3f29f`: `classid`
- `0x3f4fb`: `classid`
- `0x3f643`: `classid`
- `0x3f6d4`: `classid`
- `0x3f765`: `classid`
- `0x3f7f6`: `classid`
- `0x3f6c8`: `header_scheduledend`

## pseudocode

```c

```

## disassembly

```asm
0x3ef90  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument()
0x3ef95  stloc.0
0x3ef96  ldstr    aDisplayname_0// "displayname"
0x3ef9b  stloc.1
0x3ef9c  ldloc.0
0x3ef9d  ldstr    aForm// "form"
0x3efa2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3efa7  stloc.2
0x3efa8  ldloc.0
0x3efa9  ldstr    aTabs// "tabs"
0x3efae  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3efb3  stloc.3
0x3efb4  ldloc.0
0x3efb5  ldstr    aTab// "tab"
0x3efba  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3efbf  stloc.s  4
0x3efc1  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3efc6  stloc.s  5
0x3efc8  ldloc.s  4
0x3efca  ldstr    aVerticallayout// "verticallayout"
0x3efcf  ldstr    aTrue// "true"
0x3efd4  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3efd9  ldloc.s  4
0x3efdb  ldstr    aId// "id"
0x3efe0  ldloca.s 5
0x3efe2  ldstr    aB// "B"
0x3efe7  call     instance string [mscorlib]System.Guid::ToString(string)
0x3efec  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3eff1  ldloc.s  4
0x3eff3  ldstr    aIsuserdefined// "IsUserDefined"
0x3eff8  ldstr    a1// "1"
0x3effd  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f002  ldarg.0
0x3f003  ldstr    aGeneraltablabe// "GeneralTabLabel"
0x3f008  ldloc.s  5
0x3f00a  ldloc.1
0x3f00b  ldc.i4.6
0x3f00c  ldarg.3
0x3f00d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.LocalizationHelper::GetLabelsForResource(string resourceName, valuetype [mscorlib]System.Guid objectId, string objectColumnName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelTypeCode, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3f012  ldarg.2
0x3f013  call     instance void Microsoft.Crm.Metadata.OrganizationUIHelper::AddLabelsToList(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection labels, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity> labelsToAddTo)
0x3f018  ldloc.0
0x3f019  ldstr    aColumns// "columns"
0x3f01e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3f023  stloc.s  6
0x3f025  ldloc.0
0x3f026  ldstr    aColumn// "column"
0x3f02b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3f030  stloc.s  7
0x3f032  ldloc.s  7
0x3f034  ldstr    aWidth// "width"
0x3f039  ldarg.1
0x3f03a  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_HasRelatedNotes()
0x3f03f  brtrue.s loc_3F048
0x3f041  ldstr    a100// "100%"
0x3f046  br.s     loc_3F04D
0x3f048  ldstr    a33// "33%"
0x3f04d  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f052  ldloc.0
0x3f053  ldstr    aSections// "sections"
0x3f058  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3f05d  stloc.s  8
0x3f05f  ldloc.0
0x3f060  ldstr    aSection// "section"
0x3f065  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3f06a  stloc.s  9
0x3f06c  ldloc.s  9
0x3f06e  ldstr    aShowlabel// "showlabel"
0x3f073  ldstr    aFalse// "false"
0x3f078  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f07d  ldloc.s  9
0x3f07f  ldstr    aShowbar// "showbar"
0x3f084  ldstr    aFalse// "false"
0x3f089  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f08e  ldloc.s  9
0x3f090  ldstr    aIsuserdefined// "IsUserDefined"
0x3f095  ldstr    a0_1// "0"
0x3f09a  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f09f  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3f0a4  stloc.s  0xA
0x3f0a6  ldloc.s  9
0x3f0a8  ldstr    aId// "id"
0x3f0ad  ldloca.s 0xA
0x3f0af  ldstr    aB// "B"
0x3f0b4  call     instance string [mscorlib]System.Guid::ToString(string)
0x3f0b9  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f0be  ldarg.0
0x3f0bf  ldstr    aGeneralsection// "GeneralSectionLabel"
0x3f0c4  ldloc.s  0xA
0x3f0c6  ldloc.1
0x3f0c7  ldc.i4.7
0x3f0c8  ldarg.3
0x3f0c9  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.LocalizationHelper::GetLabelsForResource(string resourceName, valuetype [mscorlib]System.Guid objectId, string objectColumnName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelTypeCode, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3f0ce  ldarg.2
0x3f0cf  call     instance void Microsoft.Crm.Metadata.OrganizationUIHelper::AddLabelsToList(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection labels, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity> labelsToAddTo)
0x3f0d4  ldloc.0
0x3f0d5  ldstr    aRows// "rows"
0x3f0da  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3f0df  stloc.s  0xB
0x3f0e1  ldloc.0
0x3f0e2  ldstr    aRow// "row"
0x3f0e7  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3f0ec  stloc.s  0xC
0x3f0ee  ldloc.0
0x3f0ef  ldstr    aCell// "cell"
0x3f0f4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3f0f9  stloc.s  0xD
0x3f0fb  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3f100  stloc.s  0xE
0x3f102  ldloc.s  0xD
0x3f104  ldstr    aId// "id"
0x3f109  ldloca.s 0xE
0x3f10b  ldstr    aB// "B"
0x3f110  call     instance string [mscorlib]System.Guid::ToString(string)
0x3f115  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f11a  ldloc.0
0x3f11b  ldstr    aControl// "control"
0x3f120  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3f125  stloc.s  0xF
0x3f127  ldloc.s  0xF
0x3f129  ldstr    aId// "id"
0x3f12e  ldarg.1
0x3f12f  callvirt instance class Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Metadata.EntityCreateInfo::get_PrimaryField()
0x3f134  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x3f139  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3f13e  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x3f143  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f148  ldloc.s  0xF
0x3f14a  ldstr    aClassid// "classid"
0x3f14f  ldstr    a4273edbdAc1d40// "{4273EDBD-AC1D-40d3-9FB2-095C621B552D}"
0x3f154  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f159  ldloc.s  0xF
0x3f15b  ldstr    aDatafieldname// "datafieldname"
0x3f160  ldarg.1
0x3f161  callvirt instance class Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Metadata.EntityCreateInfo::get_PrimaryField()
0x3f166  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x3f16b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3f170  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x3f175  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f17a  ldloc.s  0xD
0x3f17c  ldloc.s  0xF
0x3f17e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3f183  pop
0x3f184  ldloc.s  0xC
0x3f186  ldloc.s  0xD
0x3f188  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3f18d  pop
0x3f18e  ldloc.s  0xB
0x3f190  ldloc.s  0xC
0x3f192  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3f197  pop
0x3f198  ldc.i4.1
0x3f199  ldarg.1
0x3f19a  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes Microsoft.Crm.Metadata.EntityCreateInfo::get_OwnershipTypeMask()
0x3f19f  bne.un   loc_3F23B
0x3f1a4  ldloc.0
0x3f1a5  ldstr    aRow// "row"
0x3f1aa  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3f1af  stloc.s  0x11
0x3f1b1  ldloc.0
0x3f1b2  ldstr    aCell// "cell"
0x3f1b7  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3f1bc  stloc.s  0x12
0x3f1be  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3f1c3  stloc.s  0xE
0x3f1c5  ldloc.s  0x12
0x3f1c7  ldstr    aId// "id"
0x3f1cc  ldloca.s 0xE
0x3f1ce  ldstr    aB// "B"
0x3f1d3  call     instance string [mscorlib]System.Guid::ToString(string)
0x3f1d8  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f1dd  ldloc.0
0x3f1de  ldstr    aControl// "control"
0x3f1e3  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3f1e8  stloc.s  0x13
0x3f1ea  ldloc.s  0x13
0x3f1ec  ldstr    aId// "id"
0x3f1f1  ldstr    aOwnerid// "ownerid"
0x3f1f6  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f1fb  ldloc.s  0x13
0x3f1fd  ldstr    aClassid// "classid"
0x3f202  ldstr    a270bd3dbD9af47// "{270BD3DB-D9AF-4782-9025-509E298DEC0A}"
0x3f207  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f20c  ldloc.s  0x13
0x3f20e  ldstr    aDatafieldname// "datafieldname"
0x3f213  ldstr    aOwnerid// "ownerid"
0x3f218  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f21d  ldloc.s  0x12
0x3f21f  ldloc.s  0x13
0x3f221  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3f226  pop
0x3f227  ldloc.s  0x11
0x3f229  ldloc.s  0x12
0x3f22b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3f230  pop
0x3f231  ldloc.s  0xB
0x3f233  ldloc.s  0x11
0x3f235  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3f23a  pop
0x3f23b  ldarg.1
0x3f23c  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsActivity()
0x3f241  brfalse  loc_3F2DD
0x3f246  ldloc.0
0x3f247  ldstr    aRow// "row"
0x3f24c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3f251  stloc.s  0x14
0x3f253  ldloc.0
0x3f254  ldstr    aCell// "cell"
0x3f259  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3f25e  stloc.s  0x15
0x3f260  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3f265  stloc.s  0xE
0x3f267  ldloc.s  0x15
0x3f269  ldstr    aId// "id"
0x3f26e  ldloca.s 0xE
0x3f270  ldstr    aB// "B"
0x3f275  call     instance string [mscorlib]System.Guid::ToString(string)
0x3f27a  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f27f  ldloc.0
0x3f280  ldstr    aControl// "control"
0x3f285  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3f28a  stloc.s  0x16
0x3f28c  ldloc.s  0x16
0x3f28e  ldstr    aId// "id"
0x3f293  ldstr    aRegardingobjec// "regardingobjectid"
0x3f298  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f29d  ldloc.s  0x16
0x3f29f  ldstr    aClassid// "classid"
0x3f2a4  ldstr    aF301535044a24a// "{F3015350-44A2-4aa0-97B5-00166532B5E9}"
0x3f2a9  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f2ae  ldloc.s  0x16
0x3f2b0  ldstr    aDatafieldname// "datafieldname"
0x3f2b5  ldstr    aRegardingobjec// "regardingobjectid"
0x3f2ba  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f2bf  ldloc.s  0x15
0x3f2c1  ldloc.s  0x16
0x3f2c3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3f2c8  pop
0x3f2c9  ldloc.s  0x14
0x3f2cb  ldloc.s  0x15
0x3f2cd  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3f2d2  pop
0x3f2d3  ldloc.s  0xB
0x3f2d5  ldloc.s  0x14
0x3f2d7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3f2dc  pop
0x3f2dd  ldloc.s  9
0x3f2df  ldloc.s  0xB
0x3f2e1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3f2e6  pop
0x3f2e7  ldloc.s  8
0x3f2e9  ldloc.s  9
0x3f2eb  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3f2f0  pop
0x3f2f1  ldloc.s  7
0x3f2f3  ldloc.s  8
0x3f2f5  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3f2fa  pop
0x3f2fb  ldloc.s  6
0x3f2fd  ldloc.s  7
0x3f2ff  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3f304  pop
0x3f305  ldarg.1
0x3f306  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_HasRelatedNotes()
0x3f30b  brfalse  loc_3F558
0x3f310  ldc.i4.s 0xF
0x3f312  stloc.s  0x17
0x3f314  ldloc.0
0x3f315  ldstr    aColumn// "column"
0x3f31a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3f31f  stloc.s  0x18
0x3f321  ldloc.s  0x18
0x3f323  ldstr    aWidth// "width"
0x3f328  ldstr    a66// "66%"
0x3f32d  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f332  ldloc.s  6
0x3f334  ldloc.s  0x18
0x3f336  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3f33b  pop
0x3f33c  ldloc.0
0x3f33d  ldstr    aSections// "sections"
0x3f342  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3f347  stloc.s  0x19
0x3f349  ldloc.s  0x18
0x3f34b  ldloc.s  0x19
0x3f34d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3f352  pop
0x3f353  ldloc.0
0x3f354  ldstr    aSection// "section"
0x3f359  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3f35e  stloc.s  0x1A
0x3f360  ldloc.s  0x19
0x3f362  ldloc.s  0x1A
0x3f364  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3f369  pop
0x3f36a  ldloc.s  0x1A
0x3f36c  ldstr    aShowlabel// "showlabel"
0x3f371  ldstr    aFalse// "false"
0x3f376  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f37b  ldloc.s  0x1A
  ... truncated ...
```
