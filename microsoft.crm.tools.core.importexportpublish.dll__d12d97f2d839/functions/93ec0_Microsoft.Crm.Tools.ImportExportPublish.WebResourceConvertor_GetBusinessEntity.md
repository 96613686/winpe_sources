# Microsoft.Crm.Tools.ImportExportPublish.WebResourceConvertor::GetBusinessEntity

- ea: `0x93ec0`
- end: `0x9413c`
- name: `Microsoft.Crm.Tools.ImportExportPublish.WebResourceConvertor::GetBusinessEntity`
- size: `636`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x93ec0`

## string_xrefs

- `0x9404a`: `canbedeleted`
- `0x9403b`: `CanBeDeleted`
- `0x9411b`: `DependencyXml`
- `0x9412a`: `dependencyxml`

## pseudocode

```c

```

## disassembly

```asm
0x93ec0  ldarg.1
0x93ec1  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WebResource::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x93ec6  stloc.0
0x93ec7  ldarg.2
0x93ec8  ldstr    aWebresourceid_0// "WebResourceId"
0x93ecd  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x93ed2  stloc.1
0x93ed3  ldloc.1
0x93ed4  brfalse.s loc_93EF1
0x93ed6  ldloc.0
0x93ed7  ldstr    aWebresourceid// "webresourceid"
0x93edc  ldloc.1
0x93edd  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x93ee2  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x93ee7  box      [mscorlib]System.Guid
0x93eec  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x93ef1  ldarg.2
0x93ef2  ldstr    aName_1// "Name"
0x93ef7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x93efc  stloc.1
0x93efd  ldloc.1
0x93efe  brfalse.s loc_93F13
0x93f00  ldloc.0
0x93f01  ldstr    aName// "name"
0x93f06  ldloc.1
0x93f07  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x93f0c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x93f11  br.s     loc_93F4C
0x93f13  ldarg.2
0x93f14  ldstr    aNames// "Names"
0x93f19  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x93f1e  brfalse.s loc_93F4C
0x93f20  ldarg.2
0x93f21  ldstr    aNames// "Names"
0x93f26  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x93f2b  stloc.1
0x93f2c  ldloc.0
0x93f2d  ldstr    aName// "name"
0x93f32  ldloc.1
0x93f33  ldstr    aName_1// "Name"
0x93f38  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x93f3d  ldstr    aDescription// "description"
0x93f42  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x93f47  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x93f4c  ldarg.2
0x93f4d  ldstr    aDisplayname_0// "DisplayName"
0x93f52  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x93f57  stloc.1
0x93f58  ldloc.1
0x93f59  brfalse.s loc_93F6C
0x93f5b  ldloc.0
0x93f5c  ldstr    aDisplayname// "displayname"
0x93f61  ldloc.1
0x93f62  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x93f67  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x93f6c  ldarg.2
0x93f6d  ldstr    aDescription_0// "Description"
0x93f72  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x93f77  stloc.1
0x93f78  ldloc.1
0x93f79  brfalse.s loc_93F8C
0x93f7b  ldloc.0
0x93f7c  ldstr    aDescription// "description"
0x93f81  ldloc.1
0x93f82  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x93f87  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x93f8c  ldarg.2
0x93f8d  ldstr    aSilverlightver// "SilverlightVersion"
0x93f92  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x93f97  stloc.1
0x93f98  ldloc.1
0x93f99  brfalse.s loc_93FAC
0x93f9b  ldloc.0
0x93f9c  ldstr    aSilverlightver_0// "silverlightversion"
0x93fa1  ldloc.1
0x93fa2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x93fa7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x93fac  ldarg.2
0x93fad  ldstr    aLanguagecode_0// "LanguageCode"
0x93fb2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x93fb7  stloc.1
0x93fb8  ldloc.1
0x93fb9  brfalse.s loc_93FDB
0x93fbb  ldloc.0
0x93fbc  ldstr    aLanguagecode// "languagecode"
0x93fc1  ldloc.1
0x93fc2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x93fc7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x93fcc  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x93fd1  box      [mscorlib]System.Int32
0x93fd6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x93fdb  ldarg.2
0x93fdc  ldstr    aWebresourcetyp_0// "WebResourceType"
0x93fe1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x93fe6  stloc.1
0x93fe7  ldloc.1
0x93fe8  brfalse.s loc_9400A
0x93fea  ldloc.0
0x93feb  ldstr    aWebresourcetyp// "webresourcetype"
0x93ff0  ldloc.1
0x93ff1  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x93ff6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x93ffb  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x94000  box      [mscorlib]System.Int32
0x94005  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x9400a  ldarg.2
0x9400b  ldstr    aIscustomizable_0// "IsCustomizable"
0x94010  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x94015  stloc.1
0x94016  ldloc.1
0x94017  brfalse.s loc_9403A
0x94019  ldloc.0
0x9401a  ldstr    aIscustomizable// "iscustomizable"
0x9401f  ldloc.1
0x94020  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x94025  ldstr    a1// "1"
0x9402a  ldc.i4.4
0x9402b  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x94030  box      [mscorlib]System.Boolean
0x94035  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x9403a  ldarg.2
0x9403b  ldstr    aCanbedeleted_0// "CanBeDeleted"
0x94040  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x94045  stloc.1
0x94046  ldloc.1
0x94047  brfalse.s loc_9406A
0x94049  ldloc.0
0x9404a  ldstr    aCanbedeleted// "canbedeleted"
0x9404f  ldloc.1
0x94050  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x94055  ldstr    a1// "1"
0x9405a  ldc.i4.4
0x9405b  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x94060  box      [mscorlib]System.Boolean
0x94065  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x9406a  ldarg.2
0x9406b  ldstr    aIshidden// "IsHidden"
0x94070  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x94075  stloc.1
0x94076  ldloc.1
0x94077  brfalse.s loc_9409A
0x94079  ldloc.0
0x9407a  ldstr    aIshidden_0// "ishidden"
0x9407f  ldloc.1
0x94080  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x94085  ldstr    a1// "1"
0x9408a  ldc.i4.4
0x9408b  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x94090  box      [mscorlib]System.Boolean
0x94095  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x9409a  ldarg.2
0x9409b  ldstr    aIntroducedvers_0// "IntroducedVersion"
0x940a0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x940a5  stloc.1
0x940a6  ldloc.1
0x940a7  brfalse.s loc_940BA
0x940a9  ldloc.0
0x940aa  ldstr    aIntroducedvers// "introducedversion"
0x940af  ldloc.1
0x940b0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x940b5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x940ba  ldarg.2
0x940bb  ldstr    aIsenabledformo// "IsEnabledForMobileClient"
0x940c0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x940c5  stloc.1
0x940c6  ldloc.1
0x940c7  brfalse.s loc_940EA
0x940c9  ldloc.0
0x940ca  ldstr    aIsenabledformo_0// "isenabledformobileclient"
0x940cf  ldloc.1
0x940d0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x940d5  ldstr    a1// "1"
0x940da  ldc.i4.4
0x940db  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x940e0  box      [mscorlib]System.Boolean
0x940e5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x940ea  ldarg.2
0x940eb  ldstr    aIsavailablefor// "IsAvailableForMobileOffline"
0x940f0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x940f5  stloc.1
0x940f6  ldloc.1
0x940f7  brfalse.s loc_9411A
0x940f9  ldloc.0
0x940fa  ldstr    aIsavailablefor_0// "isavailableformobileoffline"
0x940ff  ldloc.1
0x94100  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x94105  ldstr    a1// "1"
0x9410a  ldc.i4.4
0x9410b  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x94110  box      [mscorlib]System.Boolean
0x94115  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x9411a  ldarg.2
0x9411b  ldstr    aDependencyxml// "DependencyXml"
0x94120  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x94125  stloc.1
0x94126  ldloc.1
0x94127  brfalse.s loc_9413A
0x94129  ldloc.0
0x9412a  ldstr    aDependencyxml_0// "dependencyxml"
0x9412f  ldloc.1
0x94130  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x94135  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x9413a  ldloc.0
0x9413b  ret
```
