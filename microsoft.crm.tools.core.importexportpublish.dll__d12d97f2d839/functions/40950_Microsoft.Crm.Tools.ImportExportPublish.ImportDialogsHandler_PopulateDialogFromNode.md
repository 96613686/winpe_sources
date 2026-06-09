# Microsoft.Crm.Tools.ImportExportPublish.ImportDialogsHandler::PopulateDialogFromNode

- ea: `0x40950`
- end: `0x40b86`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportDialogsHandler::PopulateDialogFromNode`
- size: `566`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x407e0`
- `0x40d20`

## callees

- `0x40950`
- `0x40b90`
- `0x4d2a0`
- `0x50dc0`
- `0x50e50`

## string_xrefs

- `0x40a40`: `FormXml`
- `0x40a74`: `FormXml`
- `0x40a5a`: `formxml`
- `0x40a6e`: `formxml`
- `0x40a15`: `canbedeleted`
- `0x40a08`: `CanBeDeleted`
- `0x40a1b`: `CanBeDeleted`

## pseudocode

```c

```

## disassembly

```asm
0x40950  ldarg.1
0x40951  ldstr    aType_0// "type"
0x40956  ldc.i4.8
0x40957  box      [mscorlib]System.Int32
0x4095c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x40961  ldarg.1
0x40962  ldstr    aObjecttypecode_0// "objecttypecode"
0x40967  ldc.i4.0
0x40968  box      [mscorlib]System.Int32
0x4096d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x40972  ldarg.1
0x40973  ldstr    aFormid// "formid"
0x40978  ldarg.2
0x40979  ldstr    aFormid_0// "FormId"
0x4097e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40983  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x40988  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4098d  box      [mscorlib]System.Guid
0x40992  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x40997  ldarg.2
0x40998  ldstr    aIscustomizable_0// "IsCustomizable"
0x4099d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x409a2  brfalse.s loc_409CF
0x409a4  ldarg.1
0x409a5  ldstr    aIscustomizable// "iscustomizable"
0x409aa  ldarg.2
0x409ab  ldstr    aIscustomizable_0// "IsCustomizable"
0x409b0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x409b5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x409ba  ldstr    a1// "1"
0x409bf  ldc.i4.4
0x409c0  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x409c5  box      [mscorlib]System.Boolean
0x409ca  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x409cf  ldarg.2
0x409d0  ldstr    aIsdefault_0// "IsDefault"
0x409d5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x409da  brfalse.s loc_40A07
0x409dc  ldarg.1
0x409dd  ldstr    aIsdefault// "isdefault"
0x409e2  ldarg.2
0x409e3  ldstr    aIsdefault_0// "IsDefault"
0x409e8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x409ed  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x409f2  ldstr    a1// "1"
0x409f7  ldc.i4.4
0x409f8  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x409fd  box      [mscorlib]System.Boolean
0x40a02  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x40a07  ldarg.2
0x40a08  ldstr    aCanbedeleted_0// "CanBeDeleted"
0x40a0d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40a12  brfalse.s loc_40A3F
0x40a14  ldarg.1
0x40a15  ldstr    aCanbedeleted// "canbedeleted"
0x40a1a  ldarg.2
0x40a1b  ldstr    aCanbedeleted_0// "CanBeDeleted"
0x40a20  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40a25  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x40a2a  ldstr    a1// "1"
0x40a2f  ldc.i4.4
0x40a30  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x40a35  box      [mscorlib]System.Boolean
0x40a3a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x40a3f  ldarg.2
0x40a40  ldstr    aFormxml// "FormXml"
0x40a45  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40a4a  brfalse.s loc_40A92
0x40a4c  ldarg.0
0x40a4d  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x40a52  call     bool Microsoft.Crm.Tools.ImportExportPublish.ImportExportUtils::IsInternalMicrosoftSolution(class [System.Xml]System.Xml.XmlDocument solDoc)
0x40a57  brfalse.s loc_40A6D
0x40a59  ldarg.1
0x40a5a  ldstr    aFormxml_0// "formxml"
0x40a5f  ldarg.0
0x40a60  ldarg.2
0x40a61  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ImportDialogsHandler::ReplaceOptionSetNamesWithOptionSetIds(class [System.Xml]System.Xml.XmlNode dialogNode)
0x40a66  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x40a6b  br.s     loc_40A92
0x40a6d  ldarg.1
0x40a6e  ldstr    aFormxml_0// "formxml"
0x40a73  ldarg.2
0x40a74  ldstr    aFormxml// "FormXml"
0x40a79  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40a7e  ldstr    aForms_0// "forms"
0x40a83  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40a88  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x40a8d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x40a92  ldarg.2
0x40a93  ldstr    aIntroducedvers_0// "IntroducedVersion"
0x40a98  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40a9d  brfalse.s loc_40ABA
0x40a9f  ldarg.1
0x40aa0  ldstr    aIntroducedvers// "introducedversion"
0x40aa5  ldarg.2
0x40aa6  ldstr    aIntroducedvers_0// "IntroducedVersion"
0x40aab  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40ab0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x40ab5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x40aba  ldarg.2
0x40abb  ldstr    aIstabletenable_0// "IsTabletEnabled"
0x40ac0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40ac5  brfalse.s loc_40AF2
0x40ac7  ldarg.1
0x40ac8  ldstr    aIstabletenable// "istabletenabled"
0x40acd  ldarg.2
0x40ace  ldstr    aIstabletenable_0// "IsTabletEnabled"
0x40ad3  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40ad8  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x40add  ldstr    a1// "1"
0x40ae2  ldc.i4.4
0x40ae3  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x40ae8  box      [mscorlib]System.Boolean
0x40aed  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x40af2  ldarg.2
0x40af3  ldstr    aUniquename_0// "UniqueName"
0x40af8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40afd  brfalse.s loc_40B2D
0x40aff  ldarg.1
0x40b00  ldstr    aType_0// "type"
0x40b05  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x40b0a  unbox.any [mscorlib]System.Int32
0x40b0f  ldc.i4.8
0x40b10  bne.un.s loc_40B2D
0x40b12  ldarg.1
0x40b13  ldstr    aUniquename// "uniquename"
0x40b18  ldarg.2
0x40b19  ldstr    aUniquename_0// "UniqueName"
0x40b1e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40b23  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x40b28  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x40b2d  ldarg.0
0x40b2e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportDialogsHandler::context
0x40b33  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x40b38  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_LanguageCode()
0x40b3d  stloc.3
0x40b3e  ldloca.s 3
0x40b40  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x40b45  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x40b4a  stloc.0
0x40b4b  ldarg.2
0x40b4c  ldloc.0
0x40b4d  ldarg.3
0x40b4e  call     string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetBaseLanguageName(class [System.Xml]System.Xml.XmlNode node, string baseLanguage, string originalBaseLanguage)
0x40b53  stloc.1
0x40b54  ldarg.2
0x40b55  ldloc.0
0x40b56  ldarg.3
0x40b57  call     string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetBaseLanguageDescription(class [System.Xml]System.Xml.XmlNode node, string baseLanguage, string originalBaseLanguage)
0x40b5c  stloc.2
0x40b5d  ldloc.1
0x40b5e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x40b63  brtrue.s loc_40B71
0x40b65  ldarg.1
0x40b66  ldstr    aName// "name"
0x40b6b  ldloc.1
0x40b6c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x40b71  ldloc.2
0x40b72  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x40b77  brtrue.s loc_40B85
0x40b79  ldarg.1
0x40b7a  ldstr    aDescription// "description"
0x40b7f  ldloc.2
0x40b80  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x40b85  ret
```
