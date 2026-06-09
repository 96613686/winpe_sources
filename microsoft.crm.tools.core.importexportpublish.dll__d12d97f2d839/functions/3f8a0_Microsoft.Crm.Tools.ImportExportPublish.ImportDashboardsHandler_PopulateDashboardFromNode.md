# Microsoft.Crm.Tools.ImportExportPublish.ImportDashboardsHandler::PopulateDashboardFromNode

- ea: `0x3f8a0`
- end: `0x3fa7a`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportDashboardsHandler::PopulateDashboardFromNode`
- size: `474`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x3f750`
- `0x3f800`

## callees

- `0x3f8a0`
- `0x50dc0`
- `0x50e50`

## string_xrefs

- `0x3f990`: `FormXml`
- `0x3f9a3`: `FormXml`
- `0x3f99d`: `formxml`
- `0x3f965`: `canbedeleted`
- `0x3f958`: `CanBeDeleted`
- `0x3f96b`: `CanBeDeleted`

## pseudocode

```c

```

## disassembly

```asm
0x3f8a0  ldarg.1
0x3f8a1  ldstr    aType_0// "type"
0x3f8a6  ldc.i4.0
0x3f8a7  box      [mscorlib]System.Int32
0x3f8ac  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3f8b1  ldarg.1
0x3f8b2  ldstr    aObjecttypecode_0// "objecttypecode"
0x3f8b7  ldc.i4.0
0x3f8b8  box      [mscorlib]System.Int32
0x3f8bd  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3f8c2  ldarg.1
0x3f8c3  ldstr    aFormid// "formid"
0x3f8c8  ldarg.2
0x3f8c9  ldstr    aFormid_0// "FormId"
0x3f8ce  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3f8d3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3f8d8  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3f8dd  box      [mscorlib]System.Guid
0x3f8e2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3f8e7  ldarg.2
0x3f8e8  ldstr    aIscustomizable_0// "IsCustomizable"
0x3f8ed  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3f8f2  brfalse.s loc_3F91F
0x3f8f4  ldarg.1
0x3f8f5  ldstr    aIscustomizable// "iscustomizable"
0x3f8fa  ldarg.2
0x3f8fb  ldstr    aIscustomizable_0// "IsCustomizable"
0x3f900  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3f905  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3f90a  ldstr    a1// "1"
0x3f90f  ldc.i4.4
0x3f910  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x3f915  box      [mscorlib]System.Boolean
0x3f91a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3f91f  ldarg.2
0x3f920  ldstr    aIsdefault_0// "IsDefault"
0x3f925  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3f92a  brfalse.s loc_3F957
0x3f92c  ldarg.1
0x3f92d  ldstr    aIsdefault// "isdefault"
0x3f932  ldarg.2
0x3f933  ldstr    aIsdefault_0// "IsDefault"
0x3f938  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3f93d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3f942  ldstr    a1// "1"
0x3f947  ldc.i4.4
0x3f948  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x3f94d  box      [mscorlib]System.Boolean
0x3f952  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3f957  ldarg.2
0x3f958  ldstr    aCanbedeleted_0// "CanBeDeleted"
0x3f95d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3f962  brfalse.s loc_3F98F
0x3f964  ldarg.1
0x3f965  ldstr    aCanbedeleted// "canbedeleted"
0x3f96a  ldarg.2
0x3f96b  ldstr    aCanbedeleted_0// "CanBeDeleted"
0x3f970  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3f975  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3f97a  ldstr    a1// "1"
0x3f97f  ldc.i4.4
0x3f980  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x3f985  box      [mscorlib]System.Boolean
0x3f98a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3f98f  ldarg.2
0x3f990  ldstr    aFormxml// "FormXml"
0x3f995  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3f99a  brfalse.s loc_3F9C1
0x3f99c  ldarg.1
0x3f99d  ldstr    aFormxml_0// "formxml"
0x3f9a2  ldarg.2
0x3f9a3  ldstr    aFormxml// "FormXml"
0x3f9a8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3f9ad  ldstr    aForms_0// "forms"
0x3f9b2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3f9b7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x3f9bc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3f9c1  ldarg.2
0x3f9c2  ldstr    aIntroducedvers_0// "IntroducedVersion"
0x3f9c7  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3f9cc  brfalse.s loc_3F9E9
0x3f9ce  ldarg.1
0x3f9cf  ldstr    aIntroducedvers// "introducedversion"
0x3f9d4  ldarg.2
0x3f9d5  ldstr    aIntroducedvers_0// "IntroducedVersion"
0x3f9da  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3f9df  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x3f9e4  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3f9e9  ldarg.2
0x3f9ea  ldstr    aIstabletenable_0// "IsTabletEnabled"
0x3f9ef  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3f9f4  brfalse.s loc_3FA21
0x3f9f6  ldarg.1
0x3f9f7  ldstr    aIstabletenable// "istabletenabled"
0x3f9fc  ldarg.2
0x3f9fd  ldstr    aIstabletenable_0// "IsTabletEnabled"
0x3fa02  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3fa07  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3fa0c  ldstr    a1// "1"
0x3fa11  ldc.i4.4
0x3fa12  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x3fa17  box      [mscorlib]System.Boolean
0x3fa1c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3fa21  ldarg.0
0x3fa22  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportDashboardsHandler::context
0x3fa27  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3fa2c  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_LanguageCode()
0x3fa31  stloc.3
0x3fa32  ldloca.s 3
0x3fa34  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3fa39  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x3fa3e  stloc.0
0x3fa3f  ldarg.2
0x3fa40  ldloc.0
0x3fa41  ldarg.3
0x3fa42  call     string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetBaseLanguageName(class [System.Xml]System.Xml.XmlNode node, string baseLanguage, string originalBaseLanguage)
0x3fa47  stloc.1
0x3fa48  ldarg.2
0x3fa49  ldloc.0
0x3fa4a  ldarg.3
0x3fa4b  call     string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetBaseLanguageDescription(class [System.Xml]System.Xml.XmlNode node, string baseLanguage, string originalBaseLanguage)
0x3fa50  stloc.2
0x3fa51  ldloc.1
0x3fa52  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3fa57  brtrue.s loc_3FA65
0x3fa59  ldarg.1
0x3fa5a  ldstr    aName// "name"
0x3fa5f  ldloc.1
0x3fa60  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3fa65  ldloc.2
0x3fa66  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3fa6b  brtrue.s loc_3FA79
0x3fa6d  ldarg.1
0x3fa6e  ldstr    aDescription// "description"
0x3fa73  ldloc.2
0x3fa74  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3fa79  ret
```
