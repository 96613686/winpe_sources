# Microsoft.Crm.Tools.Service.ImportExportPublish.ContractTemplateConvertor::GetBusinessEntity

- ea: `0xf20`
- end: `0x10ff`
- name: `Microsoft.Crm.Tools.Service.ImportExportPublish.ContractTemplateConvertor::GetBusinessEntity`
- size: `479`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xf20`

## string_xrefs

- `0x107f`: `contracttemplateid`
- `0x108e`: `contracttemplateid`
- `0xf8d`: `contractservicelevelcode`
- `0xf9c`: `contractservicelevelcode`

## pseudocode

```c

```

## disassembly

```asm
0xf20  ldarg.1
0xf21  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xf26  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.ContractTemplate::.ctor(valuetype [mscorlib]System.Guid)
0xf2b  stloc.0
0xf2c  ldarg.2
0xf2d  ldstr    aName// "name"
0xf32  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xf37  stloc.1
0xf38  ldloc.1
0xf39  brfalse.s loc_F4C
0xf3b  ldloc.0
0xf3c  ldstr    aName// "name"
0xf41  ldloc.1
0xf42  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xf47  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xf4c  ldarg.2
0xf4d  ldstr    aAbbreviation// "abbreviation"
0xf52  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xf57  stloc.1
0xf58  ldloc.1
0xf59  brfalse.s loc_F6C
0xf5b  ldloc.0
0xf5c  ldstr    aAbbreviation// "abbreviation"
0xf61  ldloc.1
0xf62  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xf67  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xf6c  ldarg.2
0xf6d  ldstr    aDescription// "description"
0xf72  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xf77  stloc.1
0xf78  ldloc.1
0xf79  brfalse.s loc_F8C
0xf7b  ldloc.0
0xf7c  ldstr    aDescription// "description"
0xf81  ldloc.1
0xf82  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xf87  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xf8c  ldarg.2
0xf8d  ldstr    aContractservic// "contractservicelevelcode"
0xf92  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xf97  stloc.1
0xf98  ldloc.1
0xf99  brfalse.s loc_FBB
0xf9b  ldloc.0
0xf9c  ldstr    aContractservic// "contractservicelevelcode"
0xfa1  ldloc.1
0xfa2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0xfa7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xfac  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0xfb1  box      [mscorlib]System.Int32
0xfb6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xfbb  ldarg.2
0xfbc  ldstr    aBillingfrequen// "billingfrequencycode"
0xfc1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xfc6  stloc.1
0xfc7  ldloc.1
0xfc8  brfalse.s loc_FEA
0xfca  ldloc.0
0xfcb  ldstr    aBillingfrequen// "billingfrequencycode"
0xfd0  ldloc.1
0xfd1  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0xfd6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xfdb  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0xfe0  box      [mscorlib]System.Int32
0xfe5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xfea  ldarg.2
0xfeb  ldstr    aAllotmenttypec// "allotmenttypecode"
0xff0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xff5  stloc.1
0xff6  ldloc.1
0xff7  brfalse.s loc_1019
0xff9  ldloc.0
0xffa  ldstr    aAllotmenttypec// "allotmenttypecode"
0xfff  ldloc.1
0x1000  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x1005  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x100a  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x100f  box      [mscorlib]System.Int32
0x1014  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1019  ldarg.2
0x101a  ldstr    aUsediscountasp// "usediscountaspercentage"
0x101f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x1024  stloc.1
0x1025  ldloc.1
0x1026  brfalse.s loc_105E
0x1028  ldloc.1
0x1029  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x102e  ldstr    a0// "0"
0x1033  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1038  brfalse.s loc_104D
0x103a  ldloc.0
0x103b  ldstr    aUsediscountasp// "usediscountaspercentage"
0x1040  ldc.i4.0
0x1041  box      [mscorlib]System.Boolean
0x1046  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x104b  br.s     loc_105E
0x104d  ldloc.0
0x104e  ldstr    aUsediscountasp// "usediscountaspercentage"
0x1053  ldc.i4.1
0x1054  box      [mscorlib]System.Boolean
0x1059  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x105e  ldarg.2
0x105f  ldstr    aEffectivitycal// "effectivitycalendar"
0x1064  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x1069  stloc.1
0x106a  ldloc.1
0x106b  brfalse.s loc_107E
0x106d  ldloc.0
0x106e  ldstr    aEffectivitycal// "effectivitycalendar"
0x1073  ldloc.1
0x1074  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x1079  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x107e  ldarg.2
0x107f  ldstr    aContracttempla_1// "contracttemplateid"
0x1084  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x1089  stloc.1
0x108a  ldloc.1
0x108b  brfalse.s loc_10A8
0x108d  ldloc.0
0x108e  ldstr    aContracttempla_1// "contracttemplateid"
0x1093  ldloc.1
0x1094  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x1099  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x109e  box      [mscorlib]System.Guid
0x10a3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x10a8  ldarg.2
0x10a9  ldstr    aIscustomizable_0// "IsCustomizable"
0x10ae  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x10b3  stloc.1
0x10b4  ldloc.1
0x10b5  brfalse.s loc_10DD
0x10b7  ldloc.0
0x10b8  ldstr    aIscustomizable// "iscustomizable"
0x10bd  ldloc.1
0x10be  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x10c3  ldstr    a1// "1"
0x10c8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10cd  brtrue.s loc_10D2
0x10cf  ldc.i4.0
0x10d0  br.s     loc_10D3
0x10d2  ldc.i4.1
0x10d3  box      [mscorlib]System.Boolean
0x10d8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x10dd  ldarg.2
0x10de  ldstr    aIntroducedvers_0// "IntroducedVersion"
0x10e3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x10e8  stloc.1
0x10e9  ldloc.1
0x10ea  brfalse.s loc_10FD
0x10ec  ldloc.0
0x10ed  ldstr    aIntroducedvers// "introducedversion"
0x10f2  ldloc.1
0x10f3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x10f8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x10fd  ldloc.0
0x10fe  ret
```
