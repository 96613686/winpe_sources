# Microsoft.Crm.Tools.ImportExportPublish.ImportInteractionCentricDashboardsHandler::PopulateDashboardFromNode

- ea: `0x40230`
- end: `0x40535`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportInteractionCentricDashboardsHandler::PopulateDashboardFromNode`
- size: `773`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x3ff80`
- `0x40030`

## callees

- `0x400e0`
- `0x40230`
- `0x50dc0`
- `0x50e50`

## string_xrefs

- `0x4033f`: `FormXml`
- `0x4034c`: `FormXml`
- `0x40357`: `FormXml`
- `0x40377`: `FormXml`
- `0x40302`: `CanBeDeleted`
- `0x4030f`: `CanBeDeleted`
- `0x4031a`: `CanBeDeleted`
- `0x403fb`: `IsDesktopEnabled`
- `0x40408`: `IsDesktopEnabled`
- `0x40413`: `IsDesktopEnabled`
- `0x40438`: `FormXml/forms/form/tabs/@dashboardCategory`
- `0x4047e`: `FormXml/forms/form/tabs/@primaryentitylogicalname`

## pseudocode

```c

```

## disassembly

```asm
0x40230  ldarg.1
0x40231  ldstr    aType// "Type"
0x40236  call     instance string [mscorlib]System.String::ToLowerInvariant()
0x4023b  ldc.i4.s 0xA
0x4023d  box      [mscorlib]System.Int32
0x40242  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x40247  ldarg.1
0x40248  ldstr    aObjecttypecode// "ObjectTypeCode"
0x4024d  call     instance string [mscorlib]System.String::ToLowerInvariant()
0x40252  ldc.i4.0
0x40253  box      [mscorlib]System.Int32
0x40258  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4025d  ldarg.1
0x4025e  ldstr    aFormid_0// "FormId"
0x40263  call     instance string [mscorlib]System.String::ToLowerInvariant()
0x40268  ldarg.2
0x40269  ldstr    aFormid_0// "FormId"
0x4026e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40273  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x40278  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4027d  box      [mscorlib]System.Guid
0x40282  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x40287  ldarg.2
0x40288  ldstr    aIscustomizable_0// "IsCustomizable"
0x4028d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40292  brfalse.s loc_402C4
0x40294  ldarg.1
0x40295  ldstr    aIscustomizable_0// "IsCustomizable"
0x4029a  call     instance string [mscorlib]System.String::ToLowerInvariant()
0x4029f  ldarg.2
0x402a0  ldstr    aIscustomizable_0// "IsCustomizable"
0x402a5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x402aa  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x402af  ldstr    a1// "1"
0x402b4  ldc.i4.4
0x402b5  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x402ba  box      [mscorlib]System.Boolean
0x402bf  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x402c4  ldarg.2
0x402c5  ldstr    aIsdefault_0// "IsDefault"
0x402ca  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x402cf  brfalse.s loc_40301
0x402d1  ldarg.1
0x402d2  ldstr    aIsdefault_0// "IsDefault"
0x402d7  call     instance string [mscorlib]System.String::ToLowerInvariant()
0x402dc  ldarg.2
0x402dd  ldstr    aIsdefault_0// "IsDefault"
0x402e2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x402e7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x402ec  ldstr    a1// "1"
0x402f1  ldc.i4.4
0x402f2  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x402f7  box      [mscorlib]System.Boolean
0x402fc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x40301  ldarg.2
0x40302  ldstr    aCanbedeleted_0// "CanBeDeleted"
0x40307  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4030c  brfalse.s loc_4033E
0x4030e  ldarg.1
0x4030f  ldstr    aCanbedeleted_0// "CanBeDeleted"
0x40314  call     instance string [mscorlib]System.String::ToLowerInvariant()
0x40319  ldarg.2
0x4031a  ldstr    aCanbedeleted_0// "CanBeDeleted"
0x4031f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40324  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x40329  ldstr    a1// "1"
0x4032e  ldc.i4.4
0x4032f  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x40334  box      [mscorlib]System.Boolean
0x40339  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4033e  ldarg.2
0x4033f  ldstr    aFormxml// "FormXml"
0x40344  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40349  brfalse.s loc_40390
0x4034b  ldarg.1
0x4034c  ldstr    aFormxml// "FormXml"
0x40351  call     instance string [mscorlib]System.String::ToLowerInvariant()
0x40356  ldarg.2
0x40357  ldstr    aFormxml// "FormXml"
0x4035c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40361  ldstr    aForms_0// "forms"
0x40366  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4036b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x40370  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x40375  ldarg.0
0x40376  ldarg.2
0x40377  ldstr    aFormxml// "FormXml"
0x4037c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40381  ldstr    aForms_0// "forms"
0x40386  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4038b  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportInteractionCentricDashboardsHandler::CheckQueues(class [System.Xml]System.Xml.XmlElement dashboardNode)
0x40390  ldarg.2
0x40391  ldstr    aIntroducedvers_0// "IntroducedVersion"
0x40396  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4039b  brfalse.s loc_403BD
0x4039d  ldarg.1
0x4039e  ldstr    aIntroducedvers_0// "IntroducedVersion"
0x403a3  call     instance string [mscorlib]System.String::ToLowerInvariant()
0x403a8  ldarg.2
0x403a9  ldstr    aIntroducedvers_0// "IntroducedVersion"
0x403ae  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x403b3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x403b8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x403bd  ldarg.2
0x403be  ldstr    aIstabletenable_0// "IsTabletEnabled"
0x403c3  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x403c8  brfalse.s loc_403FA
0x403ca  ldarg.1
0x403cb  ldstr    aIstabletenable_0// "IsTabletEnabled"
0x403d0  call     instance string [mscorlib]System.String::ToLowerInvariant()
0x403d5  ldarg.2
0x403d6  ldstr    aIstabletenable_0// "IsTabletEnabled"
0x403db  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x403e0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x403e5  ldstr    a1// "1"
0x403ea  ldc.i4.4
0x403eb  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x403f0  box      [mscorlib]System.Boolean
0x403f5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x403fa  ldarg.2
0x403fb  ldstr    aIsdesktopenabl// "IsDesktopEnabled"
0x40400  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x40405  brfalse.s loc_40437
0x40407  ldarg.1
0x40408  ldstr    aIsdesktopenabl// "IsDesktopEnabled"
0x4040d  call     instance string [mscorlib]System.String::ToLowerInvariant()
0x40412  ldarg.2
0x40413  ldstr    aIsdesktopenabl// "IsDesktopEnabled"
0x40418  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4041d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x40422  ldstr    a1// "1"
0x40427  ldc.i4.4
0x40428  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x4042d  box      [mscorlib]System.Boolean
0x40432  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x40437  ldarg.2
0x40438  ldstr    aFormxmlFormsFo_0// "FormXml/forms/form/tabs/@dashboardCateg"...
0x4043d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x40442  stloc.0
0x40443  ldloc.0
0x40444  brfalse.s loc_4047D
0x40446  ldloc.0
0x40447  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x4044c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x40451  brtrue.s loc_4047D
0x40453  ldloc.0
0x40454  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x40459  ldstr    a11// "1_1"
0x4045e  callvirt instance bool [mscorlib]System.String::Equals(string)
0x40463  brtrue.s loc_4047D
0x40465  ldarg.1
0x40466  ldstr    aObjecttypecode// "ObjectTypeCode"
0x4046b  call     instance string [mscorlib]System.String::ToLowerInvariant()
0x40470  ldc.i4.0
0x40471  box      [mscorlib]System.Int32
0x40476  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4047b  br.s     loc_404DB
0x4047d  ldarg.2
0x4047e  ldstr    aFormxmlFormsFo_1// "FormXml/forms/form/tabs/@primaryentityl"...
0x40483  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x40488  stloc.s  4
0x4048a  ldloc.s  4
0x4048c  brfalse.s loc_404DB
0x4048e  ldloc.s  4
0x40490  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x40495  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4049a  brtrue.s loc_404DB
0x4049c  ldloc.s  4
0x4049e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x404a3  stloc.s  5
0x404a5  ldarg.0
0x404a6  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportInteractionCentricDashboardsHandler::context
0x404ab  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x404b0  ldloc.s  5
0x404b2  ldc.i4.1
0x404b3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x404b8  stloc.s  6
0x404ba  ldarg.1
0x404bb  ldstr    aObjecttypecode// "ObjectTypeCode"
0x404c0  call     instance string [mscorlib]System.String::ToLowerInvariant()
0x404c5  ldloc.s  6
0x404c7  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x404cc  box      [mscorlib]System.Int32
0x404d1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x404d6  leave.s  loc_404DB
0x404d8  pop
0x404d9  leave.s  loc_404DB
0x404db  ldarg.0
0x404dc  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportInteractionCentricDashboardsHandler::context
0x404e1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x404e6  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_LanguageCode()
0x404eb  stloc.s  7
0x404ed  ldloca.s 7
0x404ef  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x404f4  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x404f9  stloc.1
0x404fa  ldarg.2
0x404fb  ldloc.1
0x404fc  ldarg.3
0x404fd  call     string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetBaseLanguageName(class [System.Xml]System.Xml.XmlNode node, string baseLanguage, string originalBaseLanguage)
0x40502  stloc.2
0x40503  ldarg.2
0x40504  ldloc.1
0x40505  ldarg.3
0x40506  call     string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetBaseLanguageDescription(class [System.Xml]System.Xml.XmlNode node, string baseLanguage, string originalBaseLanguage)
0x4050b  stloc.3
0x4050c  ldloc.2
0x4050d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x40512  brtrue.s loc_40520
0x40514  ldarg.1
0x40515  ldstr    aName// "name"
0x4051a  ldloc.2
0x4051b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x40520  ldloc.3
0x40521  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x40526  brtrue.s loc_40534
0x40528  ldarg.1
0x40529  ldstr    aDescription// "description"
0x4052e  ldloc.3
0x4052f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x40534  ret
```
