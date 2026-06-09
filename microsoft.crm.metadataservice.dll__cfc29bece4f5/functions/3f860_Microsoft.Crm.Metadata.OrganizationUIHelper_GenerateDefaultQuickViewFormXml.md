# Microsoft.Crm.Metadata.OrganizationUIHelper::GenerateDefaultQuickViewFormXml

- ea: `0x3f860`
- end: `0x3fed5`
- name: `Microsoft.Crm.Metadata.OrganizationUIHelper::GenerateDefaultQuickViewFormXml`
- size: `1653`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x3dcb0`

## callees

- `0x18490`
- `0x2cb30`
- `0x2cb70`
- `0x2d1b0`
- `0x3f860`
- `0x403d0`
- `0x43df0`

## string_xrefs

- `0x3fdaf`: `scheduledend`
- `0x3fdd1`: `scheduledend`
- `0x3f9f5`: `classid`
- `0x3fab3`: `classid`
- `0x3fb55`: `classid`
- `0x3fbec`: `classid`
- `0x3fd24`: `classid`
- `0x3fdbb`: `classid`
- `0x3fe52`: `classid`

## pseudocode

```c

```

## disassembly

```asm
0x3f860  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument()
0x3f865  stloc.0
0x3f866  ldstr    aDisplayname_0// "displayname"
0x3f86b  stloc.1
0x3f86c  ldloc.0
0x3f86d  ldstr    aForm// "form"
0x3f872  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3f877  stloc.2
0x3f878  ldloc.0
0x3f879  ldstr    aTabs// "tabs"
0x3f87e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3f883  stloc.3
0x3f884  ldloc.0
0x3f885  ldstr    aTab// "tab"
0x3f88a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3f88f  stloc.s  4
0x3f891  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3f896  stloc.s  5
0x3f898  ldloc.s  4
0x3f89a  ldstr    aVerticallayout// "verticallayout"
0x3f89f  ldstr    aTrue// "true"
0x3f8a4  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f8a9  ldloc.s  4
0x3f8ab  ldstr    aId// "id"
0x3f8b0  ldloca.s 5
0x3f8b2  ldstr    aB// "B"
0x3f8b7  call     instance string [mscorlib]System.Guid::ToString(string)
0x3f8bc  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f8c1  ldloc.s  4
0x3f8c3  ldstr    aIsuserdefined// "IsUserDefined"
0x3f8c8  ldstr    a1// "1"
0x3f8cd  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f8d2  ldloc.0
0x3f8d3  ldstr    aColumns// "columns"
0x3f8d8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3f8dd  stloc.s  6
0x3f8df  ldloc.0
0x3f8e0  ldstr    aColumn// "column"
0x3f8e5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3f8ea  stloc.s  7
0x3f8ec  ldloc.s  7
0x3f8ee  ldstr    aWidth// "width"
0x3f8f3  ldstr    a100// "100%"
0x3f8f8  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f8fd  ldloc.0
0x3f8fe  ldstr    aSections// "sections"
0x3f903  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3f908  stloc.s  8
0x3f90a  ldloc.0
0x3f90b  ldstr    aSection// "section"
0x3f910  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3f915  stloc.s  9
0x3f917  ldloc.s  9
0x3f919  ldstr    aShowlabel// "showlabel"
0x3f91e  ldstr    aFalse// "false"
0x3f923  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f928  ldloc.s  9
0x3f92a  ldstr    aShowbar// "showbar"
0x3f92f  ldstr    aFalse// "false"
0x3f934  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f939  ldloc.s  9
0x3f93b  ldstr    aIsuserdefined// "IsUserDefined"
0x3f940  ldstr    a0_1// "0"
0x3f945  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f94a  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3f94f  stloc.s  0xA
0x3f951  ldloc.s  9
0x3f953  ldstr    aId// "id"
0x3f958  ldloca.s 0xA
0x3f95a  ldstr    aB// "B"
0x3f95f  call     instance string [mscorlib]System.Guid::ToString(string)
0x3f964  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f969  ldarg.0
0x3f96a  ldstr    aGenerallabel// "generalLabel"
0x3f96f  ldloc.s  0xA
0x3f971  ldloc.1
0x3f972  ldc.i4.7
0x3f973  ldarg.3
0x3f974  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.LocalizationHelper::GetLabelsForResource(string resourceName, valuetype [mscorlib]System.Guid objectId, string objectColumnName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelTypeCode, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3f979  ldarg.2
0x3f97a  call     instance void Microsoft.Crm.Metadata.OrganizationUIHelper::AddLabelsToList(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection labels, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity> labelsToAddTo)
0x3f97f  ldloc.0
0x3f980  ldstr    aRows// "rows"
0x3f985  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3f98a  stloc.s  0xB
0x3f98c  ldloc.0
0x3f98d  ldstr    aRow// "row"
0x3f992  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3f997  stloc.s  0xC
0x3f999  ldloc.0
0x3f99a  ldstr    aCell// "cell"
0x3f99f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3f9a4  stloc.s  0xD
0x3f9a6  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3f9ab  stloc.s  0xE
0x3f9ad  ldloc.s  0xD
0x3f9af  ldstr    aId// "id"
0x3f9b4  ldloca.s 0xE
0x3f9b6  ldstr    aB// "B"
0x3f9bb  call     instance string [mscorlib]System.Guid::ToString(string)
0x3f9c0  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f9c5  ldloc.0
0x3f9c6  ldstr    aControl// "control"
0x3f9cb  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3f9d0  stloc.s  0xF
0x3f9d2  ldloc.s  0xF
0x3f9d4  ldstr    aId// "id"
0x3f9d9  ldarg.1
0x3f9da  callvirt instance class Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Metadata.EntityCreateInfo::get_PrimaryField()
0x3f9df  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x3f9e4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3f9e9  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x3f9ee  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3f9f3  ldloc.s  0xF
0x3f9f5  ldstr    aClassid// "classid"
0x3f9fa  ldstr    a4273edbdAc1d40// "{4273EDBD-AC1D-40d3-9FB2-095C621B552D}"
0x3f9ff  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3fa04  ldloc.s  0xF
0x3fa06  ldstr    aDatafieldname// "datafieldname"
0x3fa0b  ldarg.1
0x3fa0c  callvirt instance class Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Metadata.EntityCreateInfo::get_PrimaryField()
0x3fa11  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x3fa16  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3fa1b  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x3fa20  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3fa25  ldloc.s  0xD
0x3fa27  ldloc.s  0xF
0x3fa29  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3fa2e  pop
0x3fa2f  ldloc.s  0xC
0x3fa31  ldloc.s  0xD
0x3fa33  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3fa38  pop
0x3fa39  ldloc.s  0xB
0x3fa3b  ldloc.s  0xC
0x3fa3d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3fa42  pop
0x3fa43  ldc.i4.1
0x3fa44  ldarg.1
0x3fa45  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes Microsoft.Crm.Metadata.EntityCreateInfo::get_OwnershipTypeMask()
0x3fa4a  bne.un   loc_3FAF1
0x3fa4f  ldarg.1
0x3fa50  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsActivity()
0x3fa55  brtrue   loc_3FAF1
0x3fa5a  ldloc.0
0x3fa5b  ldstr    aRow// "row"
0x3fa60  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3fa65  stloc.s  0x10
0x3fa67  ldloc.0
0x3fa68  ldstr    aCell// "cell"
0x3fa6d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3fa72  stloc.s  0x11
0x3fa74  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3fa79  stloc.s  0xE
0x3fa7b  ldloc.s  0x11
0x3fa7d  ldstr    aId// "id"
0x3fa82  ldloca.s 0xE
0x3fa84  ldstr    aB// "B"
0x3fa89  call     instance string [mscorlib]System.Guid::ToString(string)
0x3fa8e  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3fa93  ldloc.0
0x3fa94  ldstr    aControl// "control"
0x3fa99  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3fa9e  stloc.s  0x12
0x3faa0  ldloc.s  0x12
0x3faa2  ldstr    aId// "id"
0x3faa7  ldstr    aOwnerid// "ownerid"
0x3faac  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3fab1  ldloc.s  0x12
0x3fab3  ldstr    aClassid// "classid"
0x3fab8  ldstr    a270bd3dbD9af47// "{270BD3DB-D9AF-4782-9025-509E298DEC0A}"
0x3fabd  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3fac2  ldloc.s  0x12
0x3fac4  ldstr    aDatafieldname// "datafieldname"
0x3fac9  ldstr    aOwnerid// "ownerid"
0x3face  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3fad3  ldloc.s  0x11
0x3fad5  ldloc.s  0x12
0x3fad7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3fadc  pop
0x3fadd  ldloc.s  0x10
0x3fadf  ldloc.s  0x11
0x3fae1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3fae6  pop
0x3fae7  ldloc.s  0xB
0x3fae9  ldloc.s  0x10
0x3faeb  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3faf0  pop
0x3faf1  ldarg.1
0x3faf2  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsActivity()
0x3faf7  brfalse  loc_3FC2A
0x3fafc  ldloc.0
0x3fafd  ldstr    aRow// "row"
0x3fb02  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3fb07  stloc.s  0x13
0x3fb09  ldloc.0
0x3fb0a  ldstr    aCell// "cell"
0x3fb0f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3fb14  stloc.s  0x14
0x3fb16  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3fb1b  stloc.s  0xE
0x3fb1d  ldloc.s  0x14
0x3fb1f  ldstr    aId// "id"
0x3fb24  ldloca.s 0xE
0x3fb26  ldstr    aB// "B"
0x3fb2b  call     instance string [mscorlib]System.Guid::ToString(string)
0x3fb30  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3fb35  ldloc.0
0x3fb36  ldstr    aControl// "control"
0x3fb3b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3fb40  stloc.s  0x15
0x3fb42  ldloc.s  0x15
0x3fb44  ldstr    aId// "id"
0x3fb49  ldstr    aRegardingobjec// "regardingobjectid"
0x3fb4e  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3fb53  ldloc.s  0x15
0x3fb55  ldstr    aClassid// "classid"
0x3fb5a  ldstr    aF301535044a24a// "{F3015350-44A2-4aa0-97B5-00166532B5E9}"
0x3fb5f  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3fb64  ldloc.s  0x15
0x3fb66  ldstr    aDatafieldname// "datafieldname"
0x3fb6b  ldstr    aRegardingobjec// "regardingobjectid"
0x3fb70  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3fb75  ldloc.s  0x14
0x3fb77  ldloc.s  0x15
0x3fb79  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3fb7e  pop
0x3fb7f  ldloc.s  0x13
0x3fb81  ldloc.s  0x14
0x3fb83  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3fb88  pop
0x3fb89  ldloc.s  0xB
0x3fb8b  ldloc.s  0x13
0x3fb8d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3fb92  pop
0x3fb93  ldloc.0
0x3fb94  ldstr    aRow// "row"
0x3fb99  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3fb9e  stloc.s  0x16
0x3fba0  ldloc.0
0x3fba1  ldstr    aCell// "cell"
0x3fba6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3fbab  stloc.s  0x17
0x3fbad  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3fbb2  stloc.s  0xE
0x3fbb4  ldloc.s  0x17
0x3fbb6  ldstr    aId// "id"
0x3fbbb  ldloca.s 0xE
0x3fbbd  ldstr    aB// "B"
0x3fbc2  call     instance string [mscorlib]System.Guid::ToString(string)
0x3fbc7  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3fbcc  ldloc.0
0x3fbcd  ldstr    aControl// "control"
0x3fbd2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3fbd7  stloc.s  0x18
0x3fbd9  ldloc.s  0x18
0x3fbdb  ldstr    aId// "id"
0x3fbe0  ldstr    aStatecode_1// "statecode"
0x3fbe5  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3fbea  ldloc.s  0x18
0x3fbec  ldstr    aClassid// "classid"
0x3fbf1  ldstr    a3ef3998822bb4f// "{3EF39988-22BB-4f0b-BBBE-64B5A3748AEE}"
0x3fbf6  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3fbfb  ldloc.s  0x18
0x3fbfd  ldstr    aDatafieldname// "datafieldname"
0x3fc02  ldstr    aStatecode_1// "statecode"
0x3fc07  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3fc0c  ldloc.s  0x17
0x3fc0e  ldloc.s  0x18
0x3fc10  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3fc15  pop
0x3fc16  ldloc.s  0x16
0x3fc18  ldloc.s  0x17
0x3fc1a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3fc1f  pop
0x3fc20  ldloc.s  0xB
0x3fc22  ldloc.s  0x16
0x3fc24  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3fc29  pop
0x3fc2a  ldloc.s  9
0x3fc2c  ldloc.s  0xB
0x3fc2e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3fc33  pop
0x3fc34  ldloc.s  8
0x3fc36  ldloc.s  9
0x3fc38  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3fc3d  pop
0x3fc3e  ldarg.1
0x3fc3f  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsActivity()
0x3fc44  brfalse  loc_3FEA4
0x3fc49  ldloc.0
0x3fc4a  ldstr    aSection// "section"
0x3fc4f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3fc54  stloc.s  0x19
0x3fc56  ldloc.s  0x19
0x3fc58  ldstr    aShowlabel// "showlabel"
0x3fc5d  ldstr    aFalse// "false"
0x3fc62  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3fc67  ldloc.s  0x19
0x3fc69  ldstr    aShowbar// "showbar"
  ... truncated ...
```
