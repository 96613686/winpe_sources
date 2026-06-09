# Microsoft.Crm.Tools.Service.ImportExportPublish.KbArticleTemplateConvertor::GetBusinessEntity

- ea: `0xd80`
- end: `0xf00`
- name: `Microsoft.Crm.Tools.Service.ImportExportPublish.KbArticleTemplateConvertor::GetBusinessEntity`
- size: `384`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xd80`

## string_xrefs

- `0xe51`: `kbarticletemplateid`
- `0xe60`: `kbarticletemplateid`
- `0xd8d`: `structurexml`
- `0xd9c`: `structurexml`
- `0xdad`: `formatxml`
- `0xdbc`: `formatxml`

## pseudocode

```c

```

## disassembly

```asm
0xd80  ldarg.1
0xd81  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xd86  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.KbArticleTemplate::.ctor(valuetype [mscorlib]System.Guid)
0xd8b  stloc.0
0xd8c  ldarg.2
0xd8d  ldstr    aStructurexml// "structurexml"
0xd92  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xd97  stloc.1
0xd98  ldloc.1
0xd99  brfalse.s loc_DAC
0xd9b  ldloc.0
0xd9c  ldstr    aStructurexml// "structurexml"
0xda1  ldloc.1
0xda2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xda7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xdac  ldarg.2
0xdad  ldstr    aFormatxml// "formatxml"
0xdb2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xdb7  stloc.1
0xdb8  ldloc.1
0xdb9  brfalse.s loc_DCC
0xdbb  ldloc.0
0xdbc  ldstr    aFormatxml// "formatxml"
0xdc1  ldloc.1
0xdc2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xdc7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xdcc  ldarg.2
0xdcd  ldstr    aTitle// "title"
0xdd2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xdd7  stloc.1
0xdd8  ldloc.1
0xdd9  brfalse.s loc_DEE
0xddb  ldloc.0
0xddc  ldstr    aTitle// "title"
0xde1  ldloc.1
0xde2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xde7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xdec  br.s     loc_DFE
0xdee  ldloc.0
0xdef  ldstr    aTitle// "title"
0xdf4  ldsfld   string [mscorlib]System.String::Empty
0xdf9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xdfe  ldarg.2
0xdff  ldstr    aDescription// "description"
0xe04  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xe09  stloc.1
0xe0a  ldloc.1
0xe0b  brfalse.s loc_E1E
0xe0d  ldloc.0
0xe0e  ldstr    aDescription// "description"
0xe13  ldloc.1
0xe14  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xe19  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xe1e  ldarg.2
0xe1f  ldstr    aIsactive// "isactive"
0xe24  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xe29  stloc.1
0xe2a  ldloc.1
0xe2b  brfalse.s loc_E50
0xe2d  ldloc.0
0xe2e  ldstr    aIsactive// "isactive"
0xe33  ldloc.1
0xe34  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xe39  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe3e  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0xe43  ldc.i4.1
0xe44  ceq
0xe46  box      [mscorlib]System.Boolean
0xe4b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xe50  ldarg.2
0xe51  ldstr    aKbarticletempl_1// "kbarticletemplateid"
0xe56  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xe5b  stloc.1
0xe5c  ldloc.1
0xe5d  brfalse.s loc_E7A
0xe5f  ldloc.0
0xe60  ldstr    aKbarticletempl_1// "kbarticletemplateid"
0xe65  ldloc.1
0xe66  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xe6b  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xe70  box      [mscorlib]System.Guid
0xe75  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xe7a  ldarg.2
0xe7b  ldstr    aLanguagecode// "languagecode"
0xe80  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xe85  stloc.1
0xe86  ldloc.1
0xe87  brfalse.s loc_EA9
0xe89  ldloc.0
0xe8a  ldstr    aLanguagecode// "languagecode"
0xe8f  ldloc.1
0xe90  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0xe95  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe9a  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0xe9f  box      [mscorlib]System.Int32
0xea4  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xea9  ldarg.2
0xeaa  ldstr    aIscustomizable_0// "IsCustomizable"
0xeaf  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xeb4  stloc.1
0xeb5  ldloc.1
0xeb6  brfalse.s loc_EDE
0xeb8  ldloc.0
0xeb9  ldstr    aIscustomizable// "iscustomizable"
0xebe  ldloc.1
0xebf  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xec4  ldstr    a1// "1"
0xec9  call     bool [mscorlib]System.String::op_Equality(string, string)
0xece  brtrue.s loc_ED3
0xed0  ldc.i4.0
0xed1  br.s     loc_ED4
0xed3  ldc.i4.1
0xed4  box      [mscorlib]System.Boolean
0xed9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xede  ldarg.2
0xedf  ldstr    aIntroducedvers_0// "IntroducedVersion"
0xee4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xee9  stloc.1
0xeea  ldloc.1
0xeeb  brfalse.s loc_EFE
0xeed  ldloc.0
0xeee  ldstr    aIntroducedvers// "introducedversion"
0xef3  ldloc.1
0xef4  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xef9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xefe  ldloc.0
0xeff  ret
```
