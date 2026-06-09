# Microsoft.Crm.Metadata.OrganizationUIHelper::GenerateDefaultCardFormXml

- ea: `0x3dfd0`
- end: `0x3ec5b`
- name: `Microsoft.Crm.Metadata.OrganizationUIHelper::GenerateDefaultCardFormXml`
- size: `3211`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x3dcb0`

## callees

- `0x18490`
- `0x2cb70`
- `0x2d1b0`
- `0x3dfd0`
- `0x403d0`
- `0x43df0`

## string_xrefs

- `0x3eb0b`: `createdon`
- `0x3eb2d`: `createdon`
- `0x3e428`: `scheduledend`
- `0x3e44a`: `scheduledend`
- `0x3e1b5`: `classid`
- `0x3e381`: `classid`
- `0x3e434`: `classid`
- `0x3e4ec`: `classid`
- `0x3e729`: `classid`
- `0x3e7f3`: `classid`
- `0x3e8d2`: `classid`
- `0x3ea64`: `classid`
- `0x3eb17`: `classid`

## pseudocode

```c

```

## disassembly

```asm
0x3dfd0  ldstr    aDisplayname_0// "displayname"
0x3dfd5  stloc.0
0x3dfd6  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument()
0x3dfdb  stloc.1
0x3dfdc  ldloc.1
0x3dfdd  ldstr    aForm// "form"
0x3dfe2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3dfe7  stloc.2
0x3dfe8  ldloc.1
0x3dfe9  ldstr    aTabs// "tabs"
0x3dfee  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3dff3  stloc.3
0x3dff4  ldloc.1
0x3dff5  ldstr    aTab// "tab"
0x3dffa  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3dfff  stloc.s  4
0x3e001  ldloc.s  4
0x3e003  ldstr    aName// "name"
0x3e008  ldstr    aGeneral// "general"
0x3e00d  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e012  ldloc.s  4
0x3e014  ldstr    aVerticallayout// "verticallayout"
0x3e019  ldstr    aTrue// "true"
0x3e01e  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e023  ldloc.s  4
0x3e025  ldstr    aId// "id"
0x3e02a  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3e02f  stloc.s  0x23
0x3e031  ldloca.s 0x23
0x3e033  ldstr    aB// "B"
0x3e038  call     instance string [mscorlib]System.Guid::ToString(string)
0x3e03d  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e042  ldloc.s  4
0x3e044  ldstr    aIsuserdefined// "IsUserDefined"
0x3e049  ldstr    a0_1// "0"
0x3e04e  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e053  ldloc.1
0x3e054  ldstr    aColumns// "columns"
0x3e059  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3e05e  stloc.s  5
0x3e060  ldloc.1
0x3e061  ldstr    aColumn// "column"
0x3e066  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3e06b  stloc.s  6
0x3e06d  ldloc.s  6
0x3e06f  ldstr    aWidth// "width"
0x3e074  ldstr    a25// "25%"
0x3e079  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e07e  ldloc.1
0x3e07f  ldstr    aSections// "sections"
0x3e084  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3e089  stloc.s  7
0x3e08b  ldloc.1
0x3e08c  ldstr    aSection// "section"
0x3e091  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3e096  stloc.s  8
0x3e098  ldloc.s  8
0x3e09a  ldstr    aName// "name"
0x3e09f  ldstr    aColorstrip// "ColorStrip"
0x3e0a4  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e0a9  ldloc.s  8
0x3e0ab  ldstr    aShowlabel// "showlabel"
0x3e0b0  ldstr    aFalse// "false"
0x3e0b5  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e0ba  ldloc.s  8
0x3e0bc  ldstr    aShowbar// "showbar"
0x3e0c1  ldstr    aFalse// "false"
0x3e0c6  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e0cb  ldloc.s  8
0x3e0cd  ldstr    aColumns// "columns"
0x3e0d2  ldstr    a1// "1"
0x3e0d7  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e0dc  ldloc.s  8
0x3e0de  ldstr    aIsuserdefined// "IsUserDefined"
0x3e0e3  ldstr    a0_1// "0"
0x3e0e8  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e0ed  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3e0f2  stloc.s  9
0x3e0f4  ldloc.s  8
0x3e0f6  ldstr    aId// "id"
0x3e0fb  ldloca.s 9
0x3e0fd  ldstr    aB// "B"
0x3e102  call     instance string [mscorlib]System.Guid::ToString(string)
0x3e107  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e10c  ldarg.0
0x3e10d  ldstr    aColorstripsect// "ColorStripSectionLabel"
0x3e112  ldloc.s  9
0x3e114  ldloc.0
0x3e115  ldc.i4.7
0x3e116  ldarg.3
0x3e117  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.LocalizationHelper::GetLabelsForResource(string resourceName, valuetype [mscorlib]System.Guid objectId, string objectColumnName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelTypeCode, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3e11c  ldarg.2
0x3e11d  call     instance void Microsoft.Crm.Metadata.OrganizationUIHelper::AddLabelsToList(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection labels, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity> labelsToAddTo)
0x3e122  ldarg.1
0x3e123  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsActivity()
0x3e128  brfalse  loc_3E20E
0x3e12d  ldloc.1
0x3e12e  ldstr    aRows// "rows"
0x3e133  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3e138  stloc.s  0x24
0x3e13a  ldloc.1
0x3e13b  ldstr    aRow// "row"
0x3e140  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3e145  stloc.s  0x25
0x3e147  ldloc.1
0x3e148  ldstr    aCell// "cell"
0x3e14d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3e152  stloc.s  0x26
0x3e154  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3e159  stloc.s  0x27
0x3e15b  ldloc.s  0x26
0x3e15d  ldstr    aId// "id"
0x3e162  ldloca.s 0x27
0x3e164  ldstr    aB// "B"
0x3e169  call     instance string [mscorlib]System.Guid::ToString(string)
0x3e16e  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e173  ldloc.s  0x26
0x3e175  ldstr    aShowlabel// "showlabel"
0x3e17a  ldstr    aTrue// "true"
0x3e17f  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e184  ldloc.s  0x26
0x3e186  ldstr    aLocklevel// "locklevel"
0x3e18b  ldstr    a0_1// "0"
0x3e190  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e195  ldloc.1
0x3e196  ldstr    aControl// "control"
0x3e19b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3e1a0  stloc.s  0x28
0x3e1a2  ldloc.s  0x28
0x3e1a4  ldstr    aId// "id"
0x3e1a9  ldstr    aStatuscode// "statuscode"
0x3e1ae  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e1b3  ldloc.s  0x28
0x3e1b5  ldstr    aClassid// "classid"
0x3e1ba  ldstr    a5d68b98806614d// "{5D68B988-0661-4db2-BC3E-17598AD3BE6C}"
0x3e1bf  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e1c4  ldloc.s  0x28
0x3e1c6  ldstr    aDatafieldname// "datafieldname"
0x3e1cb  ldstr    aStatuscode// "statuscode"
0x3e1d0  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e1d5  ldloc.s  0x28
0x3e1d7  ldstr    aDisabled// "disabled"
0x3e1dc  ldstr    aFalse// "false"
0x3e1e1  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e1e6  ldloc.s  0x26
0x3e1e8  ldloc.s  0x28
0x3e1ea  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3e1ef  pop
0x3e1f0  ldloc.s  0x25
0x3e1f2  ldloc.s  0x26
0x3e1f4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3e1f9  pop
0x3e1fa  ldloc.s  0x24
0x3e1fc  ldloc.s  0x25
0x3e1fe  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3e203  pop
0x3e204  ldloc.s  8
0x3e206  ldloc.s  0x24
0x3e208  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3e20d  pop
0x3e20e  ldloc.s  7
0x3e210  ldloc.s  8
0x3e212  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3e217  pop
0x3e218  ldloc.s  6
0x3e21a  ldloc.s  7
0x3e21c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3e221  pop
0x3e222  ldloc.s  5
0x3e224  ldloc.s  6
0x3e226  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3e22b  pop
0x3e22c  ldloc.1
0x3e22d  ldstr    aColumn// "column"
0x3e232  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3e237  stloc.s  0xA
0x3e239  ldloc.s  0xA
0x3e23b  ldstr    aWidth// "width"
0x3e240  ldstr    a75// "75%"
0x3e245  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e24a  ldloc.1
0x3e24b  ldstr    aSections// "sections"
0x3e250  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3e255  stloc.s  0xB
0x3e257  ldloc.1
0x3e258  ldstr    aSection// "section"
0x3e25d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3e262  stloc.s  0xC
0x3e264  ldloc.s  0xC
0x3e266  ldstr    aName// "name"
0x3e26b  ldstr    aCardheader// "CardHeader"
0x3e270  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e275  ldloc.s  0xC
0x3e277  ldstr    aShowlabel// "showlabel"
0x3e27c  ldstr    aFalse// "false"
0x3e281  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e286  ldloc.s  0xC
0x3e288  ldstr    aShowbar// "showbar"
0x3e28d  ldstr    aFalse// "false"
0x3e292  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e297  ldloc.s  0xC
0x3e299  ldstr    aColumns// "columns"
0x3e29e  ldstr    a111// "111"
0x3e2a3  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e2a8  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3e2ad  stloc.s  0xD
0x3e2af  ldloc.s  0xC
0x3e2b1  ldstr    aId// "id"
0x3e2b6  ldloca.s 0xD
0x3e2b8  ldstr    aB// "B"
0x3e2bd  call     instance string [mscorlib]System.Guid::ToString(string)
0x3e2c2  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e2c7  ldloc.s  0xC
0x3e2c9  ldstr    aIsuserdefined// "IsUserDefined"
0x3e2ce  ldstr    a0_1// "0"
0x3e2d3  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e2d8  ldarg.0
0x3e2d9  ldstr    aCardheadersect// "CardHeaderSectionLabel"
0x3e2de  ldloc.s  0xD
0x3e2e0  ldloc.0
0x3e2e1  ldc.i4.7
0x3e2e2  ldarg.3
0x3e2e3  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.LocalizationHelper::GetLabelsForResource(string resourceName, valuetype [mscorlib]System.Guid objectId, string objectColumnName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelTypeCode, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3e2e8  ldarg.2
0x3e2e9  call     instance void Microsoft.Crm.Metadata.OrganizationUIHelper::AddLabelsToList(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection labels, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity> labelsToAddTo)
0x3e2ee  ldloc.1
0x3e2ef  ldstr    aRows// "rows"
0x3e2f4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3e2f9  stloc.s  0xE
0x3e2fb  ldloc.1
0x3e2fc  ldstr    aRow// "row"
0x3e301  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3e306  stloc.s  0xF
0x3e308  ldarg.1
0x3e309  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsActivity()
0x3e30e  brfalse  loc_3E47E
0x3e313  ldloc.1
0x3e314  ldstr    aCell// "cell"
0x3e319  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3e31e  stloc.s  0x29
0x3e320  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3e325  stloc.s  0x2A
0x3e327  ldloc.s  0x29
0x3e329  ldstr    aId// "id"
0x3e32e  ldloca.s 0x2A
0x3e330  ldstr    aB// "B"
0x3e335  call     instance string [mscorlib]System.Guid::ToString(string)
0x3e33a  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e33f  ldloc.s  0x29
0x3e341  ldstr    aShowlabel// "showlabel"
0x3e346  ldstr    aTrue// "true"
0x3e34b  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e350  ldloc.s  0x29
0x3e352  ldstr    aLocklevel// "locklevel"
0x3e357  ldstr    a0_1// "0"
0x3e35c  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e361  ldloc.1
0x3e362  ldstr    aControl// "control"
0x3e367  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3e36c  stloc.s  0x2B
0x3e36e  ldloc.s  0x2B
0x3e370  ldstr    aId// "id"
0x3e375  ldstr    aPrioritycode// "prioritycode"
0x3e37a  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e37f  ldloc.s  0x2B
0x3e381  ldstr    aClassid// "classid"
0x3e386  ldstr    a3ef3998822bb4f// "{3EF39988-22BB-4f0b-BBBE-64B5A3748AEE}"
0x3e38b  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e390  ldloc.s  0x2B
0x3e392  ldstr    aDatafieldname// "datafieldname"
0x3e397  ldstr    aPrioritycode// "prioritycode"
0x3e39c  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e3a1  ldloc.s  0x2B
0x3e3a3  ldstr    aDisabled// "disabled"
0x3e3a8  ldstr    aFalse// "false"
0x3e3ad  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e3b2  ldloc.s  0x29
0x3e3b4  ldloc.s  0x2B
0x3e3b6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3e3bb  pop
0x3e3bc  ldloc.s  0xF
0x3e3be  ldloc.s  0x29
0x3e3c0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x3e3c5  pop
0x3e3c6  ldloc.1
0x3e3c7  ldstr    aCell// "cell"
0x3e3cc  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3e3d1  stloc.s  0x2C
0x3e3d3  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3e3d8  stloc.s  0x2D
0x3e3da  ldloc.s  0x2C
0x3e3dc  ldstr    aId// "id"
0x3e3e1  ldloca.s 0x2D
0x3e3e3  ldstr    aB// "B"
0x3e3e8  call     instance string [mscorlib]System.Guid::ToString(string)
0x3e3ed  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x3e3f2  ldloc.s  0x2C
0x3e3f4  ldstr    aShowlabel// "showlabel"
0x3e3f9  ldstr    aTrue// "true"
0x3e3fe  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
  ... truncated ...
```
