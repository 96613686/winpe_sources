# Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::PopulateFormFromNode_0

- ea: `0x4fa10`
- end: `0x4fc88`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::PopulateFormFromNode_0`
- size: `632`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x4f560`
- `0x4f9f0`

## callees

- `0x4fa10`
- `0x4fc90`
- `0x4fd90`
- `0x4fdb0`
- `0x50510`
- `0x50550`
- `0x50dc0`
- `0x50e50`

## string_xrefs

- `0x4fb39`: `formxmlmanaged`
- `0x4fab4`: `formxml`
- `0x4fb05`: `canbedeleted`
- `0x4faf8`: `CanBeDeleted`
- `0x4fb0b`: `CanBeDeleted`

## pseudocode

```c

```

## disassembly

```asm
0x4fa10  ldarg.1
0x4fa11  ldstr    aFormid// "formid"
0x4fa16  ldarg.0
0x4fa17  ldarg.2
0x4fa18  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::GetIdFromFormNode(class [System.Xml]System.Xml.XmlNode formNode)
0x4fa1d  box      [mscorlib]System.Guid
0x4fa22  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4fa27  ldarg.1
0x4fa28  ldstr    aType_0// "type"
0x4fa2d  ldarg.0
0x4fa2e  ldarg.3
0x4fa2f  call     instance int32 Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::ConvertFormTypeToInt(string formType)
0x4fa34  box      [mscorlib]System.Int32
0x4fa39  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4fa3e  ldarg.1
0x4fa3f  ldstr    aObjecttypecode_0// "objecttypecode"
0x4fa44  ldarg.0
0x4fa45  ldfld    int32 Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::objectTypeCode
0x4fa4a  box      [mscorlib]System.Int32
0x4fa4f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4fa54  ldarg.2
0x4fa55  ldstr    aForm// "form"
0x4fa5a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4fa5f  brfalse.s loc_4FABF
0x4fa61  ldarg.2
0x4fa62  ldstr    aForm// "form"
0x4fa67  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4fa6c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x4fa71  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4fa76  brtrue.s loc_4FABF
0x4fa78  ldsfld   string [mscorlib]System.String::Empty
0x4fa7d  stloc.3
0x4fa7e  ldarg.s  5
0x4fa80  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x4fa85  brtrue.s loc_4FAA2
0x4fa87  ldarg.0
0x4fa88  ldarg.2
0x4fa89  ldstr    aForm// "form"
0x4fa8e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4fa93  ldarg.s  5
0x4fa95  call     instance class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::PopulateControlDescriptions(class [System.Xml]System.Xml.XmlElement formNode, string lastManagedFormXml)
0x4fa9a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x4fa9f  stloc.3
0x4faa0  br.s     loc_4FAB3
0x4faa2  ldarg.2
0x4faa3  ldstr    aForm// "form"
0x4faa8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4faad  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x4fab2  stloc.3
0x4fab3  ldarg.1
0x4fab4  ldstr    aFormxml_0// "formxml"
0x4fab9  ldloc.3
0x4faba  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4fabf  ldarg.2
0x4fac0  ldstr    aIscustomizable_0// "IsCustomizable"
0x4fac5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4faca  brfalse.s loc_4FAF7
0x4facc  ldarg.1
0x4facd  ldstr    aIscustomizable// "iscustomizable"
0x4fad2  ldarg.2
0x4fad3  ldstr    aIscustomizable_0// "IsCustomizable"
0x4fad8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4fadd  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x4fae2  ldstr    a1// "1"
0x4fae7  ldc.i4.4
0x4fae8  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x4faed  box      [mscorlib]System.Boolean
0x4faf2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4faf7  ldarg.2
0x4faf8  ldstr    aCanbedeleted_0// "CanBeDeleted"
0x4fafd  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4fb02  brfalse.s loc_4FB2F
0x4fb04  ldarg.1
0x4fb05  ldstr    aCanbedeleted// "canbedeleted"
0x4fb0a  ldarg.2
0x4fb0b  ldstr    aCanbedeleted_0// "CanBeDeleted"
0x4fb10  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4fb15  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x4fb1a  ldstr    a1// "1"
0x4fb1f  ldc.i4.4
0x4fb20  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x4fb25  box      [mscorlib]System.Boolean
0x4fb2a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4fb2f  ldarg.s  4
0x4fb31  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4fb36  brtrue.s loc_4FB45
0x4fb38  ldarg.1
0x4fb39  ldstr    aFormxmlmanaged// "formxmlmanaged"
0x4fb3e  ldarg.s  4
0x4fb40  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4fb45  ldarg.2
0x4fb46  ldstr    aFormpresentati_0// "FormPresentation"
0x4fb4b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4fb50  brfalse.s loc_4FB7C
0x4fb52  ldarg.1
0x4fb53  ldstr    aFormpresentati// "formpresentation"
0x4fb58  ldarg.2
0x4fb59  ldstr    aFormpresentati_0// "FormPresentation"
0x4fb5e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4fb63  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x4fb68  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4fb6d  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x4fb72  box      [mscorlib]System.Int32
0x4fb77  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4fb7c  ldarg.2
0x4fb7d  ldstr    aIntroducedvers_0// "IntroducedVersion"
0x4fb82  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4fb87  brfalse.s loc_4FBA4
0x4fb89  ldarg.1
0x4fb8a  ldstr    aIntroducedvers// "introducedversion"
0x4fb8f  ldarg.2
0x4fb90  ldstr    aIntroducedvers_0// "IntroducedVersion"
0x4fb95  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4fb9a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x4fb9f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4fba4  ldarg.2
0x4fba5  ldstr    aUniquename_0// "UniqueName"
0x4fbaa  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4fbaf  brfalse.s loc_4FBCC
0x4fbb1  ldarg.1
0x4fbb2  ldstr    aUniquename// "uniquename"
0x4fbb7  ldarg.2
0x4fbb8  ldstr    aUniquename_0// "UniqueName"
0x4fbbd  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4fbc2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x4fbc7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4fbcc  ldarg.0
0x4fbcd  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::get_Setup()
0x4fbd2  brfalse.s loc_4FBE2
0x4fbd4  ldarg.0
0x4fbd5  call     instance class [mscorlib]System.Version Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::get_ExistingDatabaseVersion()
0x4fbda  ldnull
0x4fbdb  call     bool [mscorlib]System.Version::op_Equality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x4fbe0  brfalse.s loc_4FC2C
0x4fbe2  ldarg.2
0x4fbe3  ldstr    aFormactivation_0// "FormActivationState"
0x4fbe8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4fbed  brfalse.s loc_4FC1B
0x4fbef  ldarg.1
0x4fbf0  ldstr    aFormactivation// "formactivationstate"
0x4fbf5  ldarg.2
0x4fbf6  ldstr    aFormactivation_0// "FormActivationState"
0x4fbfb  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4fc00  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x4fc05  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4fc0a  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x4fc0f  box      [mscorlib]System.Int32
0x4fc14  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4fc19  br.s     loc_4FC2C
0x4fc1b  ldarg.1
0x4fc1c  ldstr    aFormactivation// "formactivationstate"
0x4fc21  ldc.i4.1
0x4fc22  box      [mscorlib]System.Int32
0x4fc27  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4fc2c  ldarg.0
0x4fc2d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::context
0x4fc32  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4fc37  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_LanguageCode()
0x4fc3c  stloc.s  4
0x4fc3e  ldloca.s 4
0x4fc40  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4fc45  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x4fc4a  stloc.0
0x4fc4b  ldarg.2
0x4fc4c  ldloc.0
0x4fc4d  ldarg.s  6
0x4fc4f  call     string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetBaseLanguageName(class [System.Xml]System.Xml.XmlNode node, string baseLanguage, string originalBaseLanguage)
0x4fc54  stloc.1
0x4fc55  ldarg.2
0x4fc56  ldloc.0
0x4fc57  ldarg.s  6
0x4fc59  call     string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetBaseLanguageDescription(class [System.Xml]System.Xml.XmlNode node, string baseLanguage, string originalBaseLanguage)
0x4fc5e  stloc.2
0x4fc5f  ldloc.1
0x4fc60  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4fc65  brtrue.s loc_4FC73
0x4fc67  ldarg.1
0x4fc68  ldstr    aName// "name"
0x4fc6d  ldloc.1
0x4fc6e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4fc73  ldloc.2
0x4fc74  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4fc79  brtrue.s loc_4FC87
0x4fc7b  ldarg.1
0x4fc7c  ldstr    aDescription// "description"
0x4fc81  ldloc.2
0x4fc82  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4fc87  ret
```
