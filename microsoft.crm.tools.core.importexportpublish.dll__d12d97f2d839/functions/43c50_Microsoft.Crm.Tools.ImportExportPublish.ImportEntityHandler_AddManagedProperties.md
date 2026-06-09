# Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::AddManagedProperties

- ea: `0x43c50`
- end: `0x44118`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::AddManagedProperties`
- size: `1224`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x427e0`

## callees

- `0x43c50`

## string_xrefs

- `0x43c90`: `EntityInfo/entity/IsRenameable`
- `0x43dc1`: `EntityInfo/entity/CanModifyMobileClientReadOnly`
- `0x43f2f`: `EntityInfo/entity/CanCreateAttributes`
- `0x43f6c`: `EntityInfo/entity/CanCreateForms`
- `0x43fa9`: `EntityInfo/entity/CanCreateCharts`
- `0x43fe6`: `EntityInfo/entity/CanCreateViews`

## pseudocode

```c

```

## disassembly

```asm
0x43c50  ldc.i4.0
0x43c51  stloc.1
0x43c52  ldarg.1
0x43c53  ldstr    aEntityinfoEnti_2// "EntityInfo/entity/IsCustomizable"
0x43c58  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x43c5d  stloc.2
0x43c5e  ldloc.2
0x43c5f  brfalse.s loc_43C8F
0x43c61  ldloc.2
0x43c62  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x43c67  ldstr    a1// "1"
0x43c6c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x43c71  brtrue.s loc_43C76
0x43c73  ldc.i4.0
0x43c74  br.s     loc_43C77
0x43c76  ldc.i4.1
0x43c77  stloc.0
0x43c78  ldloc.0
0x43c79  ldarg.2
0x43c7a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomizable()
0x43c7f  beq.s    loc_43C8F
0x43c81  ldarg.0
0x43c82  ldfld    class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityUpdateInfo
0x43c87  ldloc.0
0x43c88  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IsCustomizable(bool)
0x43c8d  ldc.i4.1
0x43c8e  stloc.1
0x43c8f  ldarg.1
0x43c90  ldstr    aEntityinfoEnti_3// "EntityInfo/entity/IsRenameable"
0x43c95  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x43c9a  stloc.2
0x43c9b  ldloc.2
0x43c9c  brfalse.s loc_43CCC
0x43c9e  ldloc.2
0x43c9f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x43ca4  ldstr    a1// "1"
0x43ca9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x43cae  brtrue.s loc_43CB3
0x43cb0  ldc.i4.0
0x43cb1  br.s     loc_43CB4
0x43cb3  ldc.i4.1
0x43cb4  stloc.0
0x43cb5  ldloc.0
0x43cb6  ldarg.2
0x43cb7  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsRenameable()
0x43cbc  beq.s    loc_43CCC
0x43cbe  ldarg.0
0x43cbf  ldfld    class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityUpdateInfo
0x43cc4  ldloc.0
0x43cc5  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IsRenameable(bool)
0x43cca  ldc.i4.1
0x43ccb  stloc.1
0x43ccc  ldarg.1
0x43ccd  ldstr    aEntityinfoEnti_4// "EntityInfo/entity/IsMappable"
0x43cd2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x43cd7  stloc.2
0x43cd8  ldloc.2
0x43cd9  brfalse.s loc_43D09
0x43cdb  ldloc.2
0x43cdc  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x43ce1  ldstr    a1// "1"
0x43ce6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x43ceb  brtrue.s loc_43CF0
0x43ced  ldc.i4.0
0x43cee  br.s     loc_43CF1
0x43cf0  ldc.i4.1
0x43cf1  stloc.0
0x43cf2  ldloc.0
0x43cf3  ldarg.2
0x43cf4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsMappable()
0x43cf9  beq.s    loc_43D09
0x43cfb  ldarg.0
0x43cfc  ldfld    class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityUpdateInfo
0x43d01  ldloc.0
0x43d02  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IsMappable(bool)
0x43d07  ldc.i4.1
0x43d08  stloc.1
0x43d09  ldarg.1
0x43d0a  ldstr    aEntityinfoEnti_5// "EntityInfo/entity/CanModifyAuditSetting"...
0x43d0f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x43d14  stloc.2
0x43d15  ldloc.2
0x43d16  brfalse.s loc_43D46
0x43d18  ldloc.2
0x43d19  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x43d1e  ldstr    a1// "1"
0x43d23  call     bool [mscorlib]System.String::op_Equality(string, string)
0x43d28  brtrue.s loc_43D2D
0x43d2a  ldc.i4.0
0x43d2b  br.s     loc_43D2E
0x43d2d  ldc.i4.1
0x43d2e  stloc.0
0x43d2f  ldloc.0
0x43d30  ldarg.2
0x43d31  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_CanModifyAuditSettings()
0x43d36  beq.s    loc_43D46
0x43d38  ldarg.0
0x43d39  ldfld    class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityUpdateInfo
0x43d3e  ldloc.0
0x43d3f  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_CanModifyAuditSettings(bool)
0x43d44  ldc.i4.1
0x43d45  stloc.1
0x43d46  ldarg.1
0x43d47  ldstr    aEntityinfoEnti_6// "EntityInfo/entity/CanModifyMobileVisibi"...
0x43d4c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x43d51  stloc.2
0x43d52  ldloc.2
0x43d53  brfalse.s loc_43D83
0x43d55  ldloc.2
0x43d56  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x43d5b  ldstr    a1// "1"
0x43d60  call     bool [mscorlib]System.String::op_Equality(string, string)
0x43d65  brtrue.s loc_43D6A
0x43d67  ldc.i4.0
0x43d68  br.s     loc_43D6B
0x43d6a  ldc.i4.1
0x43d6b  stloc.0
0x43d6c  ldloc.0
0x43d6d  ldarg.2
0x43d6e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_CanModifyMobileVisibility()
0x43d73  beq.s    loc_43D83
0x43d75  ldarg.0
0x43d76  ldfld    class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityUpdateInfo
0x43d7b  ldloc.0
0x43d7c  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_CanModifyMobileVisibility(bool)
0x43d81  ldc.i4.1
0x43d82  stloc.1
0x43d83  ldarg.1
0x43d84  ldstr    aEntityinfoEnti_7// "EntityInfo/entity/CanModifyMobileClient"...
0x43d89  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x43d8e  stloc.2
0x43d8f  ldloc.2
0x43d90  brfalse.s loc_43DC0
0x43d92  ldloc.2
0x43d93  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x43d98  ldstr    a1// "1"
0x43d9d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x43da2  brtrue.s loc_43DA7
0x43da4  ldc.i4.0
0x43da5  br.s     loc_43DA8
0x43da7  ldc.i4.1
0x43da8  stloc.0
0x43da9  ldloc.0
0x43daa  ldarg.2
0x43dab  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_CanModifyMobileClientVisibility()
0x43db0  beq.s    loc_43DC0
0x43db2  ldarg.0
0x43db3  ldfld    class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityUpdateInfo
0x43db8  ldloc.0
0x43db9  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_CanModifyMobileClientVisibility(bool)
0x43dbe  ldc.i4.1
0x43dbf  stloc.1
0x43dc0  ldarg.1
0x43dc1  ldstr    aEntityinfoEnti_8// "EntityInfo/entity/CanModifyMobileClient"...
0x43dc6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x43dcb  stloc.2
0x43dcc  ldloc.2
0x43dcd  brfalse.s loc_43DFD
0x43dcf  ldloc.2
0x43dd0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x43dd5  ldstr    a1// "1"
0x43dda  call     bool [mscorlib]System.String::op_Equality(string, string)
0x43ddf  brtrue.s loc_43DE4
0x43de1  ldc.i4.0
0x43de2  br.s     loc_43DE5
0x43de4  ldc.i4.1
0x43de5  stloc.0
0x43de6  ldloc.0
0x43de7  ldarg.2
0x43de8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_CanModifyMobileClientReadOnly()
0x43ded  beq.s    loc_43DFD
0x43def  ldarg.0
0x43df0  ldfld    class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityUpdateInfo
0x43df5  ldloc.0
0x43df6  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_CanModifyMobileClientReadOnly(bool)
0x43dfb  ldc.i4.1
0x43dfc  stloc.1
0x43dfd  ldarg.1
0x43dfe  ldstr    aEntityinfoEnti_9// "EntityInfo/entity/CanModifyMobileClient"...
0x43e03  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x43e08  stloc.2
0x43e09  ldloc.2
0x43e0a  brfalse.s loc_43E3A
0x43e0c  ldloc.2
0x43e0d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x43e12  ldstr    a1// "1"
0x43e17  call     bool [mscorlib]System.String::op_Equality(string, string)
0x43e1c  brtrue.s loc_43E21
0x43e1e  ldc.i4.0
0x43e1f  br.s     loc_43E22
0x43e21  ldc.i4.1
0x43e22  stloc.0
0x43e23  ldloc.0
0x43e24  ldarg.2
0x43e25  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_CanModifyMobileClientOffline()
0x43e2a  beq.s    loc_43E3A
0x43e2c  ldarg.0
0x43e2d  ldfld    class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityUpdateInfo
0x43e32  ldloc.0
0x43e33  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_CanModifyMobileClientOffline(bool)
0x43e38  ldc.i4.1
0x43e39  stloc.1
0x43e3a  ldarg.1
0x43e3b  ldstr    aEntityinfoEnti_10// "EntityInfo/entity/CanModifyConnectionSe"...
0x43e40  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x43e45  stloc.2
0x43e46  ldloc.2
0x43e47  brfalse.s loc_43E77
0x43e49  ldloc.2
0x43e4a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x43e4f  ldstr    a1// "1"
0x43e54  call     bool [mscorlib]System.String::op_Equality(string, string)
0x43e59  brtrue.s loc_43E5E
0x43e5b  ldc.i4.0
0x43e5c  br.s     loc_43E5F
0x43e5e  ldc.i4.1
0x43e5f  stloc.0
0x43e60  ldloc.0
0x43e61  ldarg.2
0x43e62  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_CanModifyConnectionSettings()
0x43e67  beq.s    loc_43E77
0x43e69  ldarg.0
0x43e6a  ldfld    class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityUpdateInfo
0x43e6f  ldloc.0
0x43e70  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_CanModifyConnectionSettings(bool)
0x43e75  ldc.i4.1
0x43e76  stloc.1
0x43e77  ldarg.1
0x43e78  ldstr    aEntityinfoEnti_11// "EntityInfo/entity/CanModifyDuplicateDet"...
0x43e7d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x43e82  stloc.2
0x43e83  ldloc.2
0x43e84  brfalse.s loc_43EB4
0x43e86  ldloc.2
0x43e87  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x43e8c  ldstr    a1// "1"
0x43e91  call     bool [mscorlib]System.String::op_Equality(string, string)
0x43e96  brtrue.s loc_43E9B
0x43e98  ldc.i4.0
0x43e99  br.s     loc_43E9C
0x43e9b  ldc.i4.1
0x43e9c  stloc.0
0x43e9d  ldloc.0
0x43e9e  ldarg.2
0x43e9f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_CanModifyDuplicateDetectionSettings()
0x43ea4  beq.s    loc_43EB4
0x43ea6  ldarg.0
0x43ea7  ldfld    class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityUpdateInfo
0x43eac  ldloc.0
0x43ead  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_CanModifyDuplicateDetectionSettings(bool)
0x43eb2  ldc.i4.1
0x43eb3  stloc.1
0x43eb4  ldarg.1
0x43eb5  ldstr    aEntityinfoEnti_12// "EntityInfo/entity/CanModifyMailMergeSet"...
0x43eba  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x43ebf  stloc.2
0x43ec0  ldloc.2
0x43ec1  brfalse.s loc_43EF1
0x43ec3  ldloc.2
0x43ec4  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x43ec9  ldstr    a1// "1"
0x43ece  call     bool [mscorlib]System.String::op_Equality(string, string)
0x43ed3  brtrue.s loc_43ED8
0x43ed5  ldc.i4.0
0x43ed6  br.s     loc_43ED9
0x43ed8  ldc.i4.1
0x43ed9  stloc.0
0x43eda  ldloc.0
0x43edb  ldarg.2
0x43edc  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_CanModifyMailMergeSettings()
0x43ee1  beq.s    loc_43EF1
0x43ee3  ldarg.0
0x43ee4  ldfld    class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityUpdateInfo
0x43ee9  ldloc.0
0x43eea  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_CanModifyMailMergeSettings(bool)
0x43eef  ldc.i4.1
0x43ef0  stloc.1
0x43ef1  ldarg.1
0x43ef2  ldstr    aEntityinfoEnti_13// "EntityInfo/entity/CanModifyQueueSetting"...
0x43ef7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x43efc  stloc.2
0x43efd  ldloc.2
0x43efe  brfalse.s loc_43F2E
0x43f00  ldloc.2
0x43f01  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x43f06  ldstr    a1// "1"
0x43f0b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x43f10  brtrue.s loc_43F15
0x43f12  ldc.i4.0
0x43f13  br.s     loc_43F16
0x43f15  ldc.i4.1
0x43f16  stloc.0
0x43f17  ldloc.0
0x43f18  ldarg.2
0x43f19  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_CanModifyQueueSettings()
0x43f1e  beq.s    loc_43F2E
0x43f20  ldarg.0
0x43f21  ldfld    class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandler::_entityUpdateInfo
0x43f26  ldloc.0
0x43f27  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_CanModifyQueueSettings(bool)
  ... truncated ...
```
