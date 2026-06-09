# Microsoft.Crm.Application.SiteMapSubArea::Deserialize_0

- ea: `0x25270`
- end: `0x25658`
- name: `Microsoft.Crm.Application.SiteMapSubArea::Deserialize_0`
- size: `1000`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x22800`
- `0x25260`

## callees

- `0xee20`
- `0x24be0`
- `0x25000`
- `0x25070`
- `0x250c0`
- `0x250e0`
- `0x250f0`
- `0x25130`
- `0x25150`
- `0x25170`
- `0x25190`
- `0x251b0`
- `0x25270`
- `0x2fbc0`
- `0x39d60`
- `0x39e00`
- `0x3a150`
- `0x47940`

## string_xrefs

- `0x25460`: `CanCreate`
- `0x255ab`: `GetStartedPanePath`
- `0x255c9`: `GetStartedPanePathOutlook`
- `0x255e7`: `GetStartedPanePathAdmin`
- `0x25605`: `GetStartedPanePathAdminOutlook`

## pseudocode

```c

```

## disassembly

```asm
0x25270  ldarg.1
0x25271  ldstr    aSubarea// "SubArea"
0x25276  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x2527b  ldarg.1
0x2527c  ldstr    aId_0// "Id"
0x25281  ldarg.0
0x25282  call     instance string Microsoft.Crm.Application.SiteMapSubArea::get_Id()
0x25287  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x2528c  ldarg.0
0x2528d  call     instance class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.SiteMapSubArea::get_Url()
0x25292  callvirt instance bool Microsoft.Crm.Application.Utility.CrmUri::IsEmpty()
0x25297  brtrue.s loc_252AF
0x25299  ldarg.1
0x2529a  ldstr    aUrl// "Url"
0x2529f  ldarg.0
0x252a0  call     instance class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.SiteMapSubArea::get_Url()
0x252a5  callvirt instance string [mscorlib]System.Object::ToString()
0x252aa  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x252af  ldarg.1
0x252b0  ldstr    aPassparams// "PassParams"
0x252b5  ldarg.0
0x252b6  call     instance bool Microsoft.Crm.Application.SiteMapSubArea::get_PassParameters()
0x252bb  brtrue.s loc_252C4
0x252bd  ldstr    a0_0// "0"
0x252c2  br.s     loc_252C9
0x252c4  ldstr    a1// "1"
0x252c9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x252ce  ldarg.2
0x252cf  brtrue   loc_25651
0x252d4  ldarg.1
0x252d5  ldstr    aTitle// "Title"
0x252da  ldarg.0
0x252db  call     instance string Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::get_Title()
0x252e0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x252e5  ldarg.0
0x252e6  call     instance class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.SiteMapSubArea::get_Icon()
0x252eb  callvirt instance bool Microsoft.Crm.Application.Utility.CrmUri::IsEmpty()
0x252f0  brtrue.s loc_25308
0x252f2  ldarg.1
0x252f3  ldstr    aIcon_0// "Icon"
0x252f8  ldarg.0
0x252f9  call     instance class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.SiteMapSubArea::get_Icon()
0x252fe  callvirt instance string [mscorlib]System.Object::ToString()
0x25303  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x25308  ldnull
0x25309  stloc.0
0x2530a  ldarg.0
0x2530b  ldfld    string Microsoft.Crm.Application.SiteMapSubArea::_entityName
0x25310  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x25315  brtrue.s loc_2533E
0x25317  ldarg.0
0x25318  ldfld    class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.SiteMapSubArea::_currentUserInformation
0x2531d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x25322  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x25327  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2532c  ldarg.0
0x2532d  ldfld    string Microsoft.Crm.Application.SiteMapSubArea::_entityName
0x25332  ldc.i4.1
0x25333  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x25338  stloc.0
0x25339  br       loc_25435
0x2533e  ldarg.0
0x2533f  ldfld    class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.SiteMapSubArea::_url
0x25344  callvirt instance string Microsoft.Crm.Application.Utility.CrmUri::get_Path()
0x25349  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x2534e  ldstr    aRootHomepageAs_0// "/_ROOT/HOMEPAGE.ASPX"
0x25353  ldc.i4.5
0x25354  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x25359  brtrue   loc_25435
0x2535e  ldarg.0
0x2535f  ldfld    class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.SiteMapSubArea::_url
0x25364  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x25369  ldstr    aEtc// "etc"
0x2536e  callvirt instance bool class [System]System.Collections.Generic.SortedDictionary`2<string, string>::ContainsKey(var<u1>)
0x25373  brfalse.s loc_253CF
0x25375  ldarg.0
0x25376  ldfld    class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.SiteMapSubArea::_url
0x2537b  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x25380  ldstr    aEtc// "etc"
0x25385  callvirt instance var<u1> class [System]System.Collections.Generic.SortedDictionary`2<string, string>::get_Item(void)
0x2538a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2538f  brtrue.s loc_253CF
0x25391  ldarg.0
0x25392  ldfld    class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.SiteMapSubArea::_url
0x25397  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x2539c  ldstr    aEtc// "etc"
0x253a1  callvirt instance var<u1> class [System]System.Collections.Generic.SortedDictionary`2<string, string>::get_Item(void)
0x253a6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x253ab  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x253b0  stloc.1
0x253b1  ldarg.0
0x253b2  ldfld    class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.SiteMapSubArea::_currentUserInformation
0x253b7  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x253bc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x253c1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x253c6  ldloc.1
0x253c7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x253cc  stloc.0
0x253cd  br.s     loc_25435
0x253cf  ldarg.0
0x253d0  ldfld    class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.SiteMapSubArea::_url
0x253d5  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x253da  ldstr    aEtn// "etn"
0x253df  callvirt instance bool class [System]System.Collections.Generic.SortedDictionary`2<string, string>::ContainsKey(var<u1>)
0x253e4  brfalse.s loc_25435
0x253e6  ldarg.0
0x253e7  ldfld    class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.SiteMapSubArea::_url
0x253ec  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x253f1  ldstr    aEtn// "etn"
0x253f6  callvirt instance var<u1> class [System]System.Collections.Generic.SortedDictionary`2<string, string>::get_Item(void)
0x253fb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x25400  brtrue.s loc_25435
0x25402  ldarg.0
0x25403  ldfld    class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.SiteMapSubArea::_url
0x25408  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x2540d  ldstr    aEtn// "etn"
0x25412  callvirt instance var<u1> class [System]System.Collections.Generic.SortedDictionary`2<string, string>::get_Item(void)
0x25417  stloc.2
0x25418  ldarg.0
0x25419  ldfld    class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.SiteMapSubArea::_currentUserInformation
0x2541e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x25423  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x25428  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2542d  ldloc.2
0x2542e  ldc.i4.1
0x2542f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x25434  stloc.0
0x25435  leave.s  loc_25459
0x25437  stloc.3
0x25438  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x2543d  ldc.i4.0
0x2543e  ldstr    aEntitymetadata// "EntityMetadata not found while loading "...
0x25443  ldc.i4.1
0x25444  newarr   [mscorlib]System.Object
0x25449  dup
0x2544a  ldc.i4.0
0x2544b  ldloc.3
0x2544c  callvirt instance string [mscorlib]System.Object::ToString()
0x25451  stelem.ref
0x25452  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x25457  leave.s  loc_25459
0x25459  ldloc.0
0x2545a  brfalse  loc_254E9
0x2545f  ldarg.1
0x25460  ldstr    aCancreate// "CanCreate"
0x25465  ldloc.0
0x25466  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0x2546b  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_ObjectTypeCode()
0x25470  ldc.i4.s 0x20
0x25472  ldarg.0
0x25473  ldfld    class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.SiteMapSubArea::_currentUserInformation
0x25478  call     bool Microsoft.Crm.Security.User::GetPrivilege(int32 objectType, valuetype Microsoft.Crm.Application.Types.PrivilegeId privilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x2547d  stloc.s  4
0x2547f  ldloca.s 4
0x25481  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x25486  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x2548b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x25490  ldarg.1
0x25491  ldstr    aEntityname// "EntityName"
0x25496  ldloc.0
0x25497  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0x2549c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_LogicalName()
0x254a1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x254a6  ldarg.1
0x254a7  ldstr    aEtc_0// "Etc"
0x254ac  ldloc.0
0x254ad  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0x254b2  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_ObjectTypeCode()
0x254b7  stloc.s  5
0x254b9  ldloca.s 5
0x254bb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x254c0  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x254c5  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x254ca  ldarg.1
0x254cb  ldstr    aIsactivity// "IsActivity"
0x254d0  ldloc.0
0x254d1  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0x254d6  stloc.s  4
0x254d8  ldloca.s 4
0x254da  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x254df  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x254e4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x254e9  ldarg.0
0x254ea  ldfld    class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.SiteMapSubArea::_url
0x254ef  callvirt instance string Microsoft.Crm.Application.Utility.CrmUri::get_Path()
0x254f4  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x254f9  ldstr    aHomeDashboards// "/HOME_DASHBOARDS.ASPX"
0x254fe  ldc.i4.5
0x254ff  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x25504  brfalse  loc_2559D
0x25509  ldarg.1
0x2550a  ldstr    aHascustomvs// "hasCustomVs"
0x2550f  ldstr    aTrue// "true"
0x25514  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x25519  ldarg.1
0x2551a  ldstr    aCustomvshandle// "customVSHandler"
0x2551f  ldstr    aGetdashboardli// "GetDashboardList"
0x25524  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x25529  ldarg.1
0x2552a  ldstr    aEntityname// "EntityName"
0x2552f  ldstr    aDashboard// "Dashboard"
0x25534  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x25539  ldarg.0
0x2553a  ldfld    class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.SiteMapSubArea::_currentUserInformation
0x2553f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x25544  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x25549  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2554e  ldstr    aSystemform// "systemform"
0x25553  ldc.i4.1
0x25554  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x25559  stloc.0
0x2555a  ldarg.1
0x2555b  ldstr    aEtc_0// "Etc"
0x25560  ldloc.0
0x25561  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0x25566  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_ObjectTypeCode()
0x2556b  stloc.s  5
0x2556d  ldloca.s 5
0x2556f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x25574  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x25579  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x2557e  ldarg.1
0x2557f  ldstr    aIsactivity// "IsActivity"
0x25584  ldloc.0
0x25585  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0x2558a  stloc.s  4
0x2558c  ldloca.s 4
0x2558e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x25593  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x25598  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x2559d  ldarg.0
0x2559e  call     instance string Microsoft.Crm.Application.SiteMapSubArea::get_GetStartedPanePath()
0x255a3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x255a8  brtrue.s loc_255BB
0x255aa  ldarg.1
0x255ab  ldstr    aGetstartedpane// "GetStartedPanePath"
0x255b0  ldarg.0
0x255b1  call     instance string Microsoft.Crm.Application.SiteMapSubArea::get_GetStartedPanePath()
0x255b6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x255bb  ldarg.0
0x255bc  call     instance string Microsoft.Crm.Application.SiteMapSubArea::get_GetStartedPanePathOutlook()
0x255c1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x255c6  brtrue.s loc_255D9
0x255c8  ldarg.1
0x255c9  ldstr    aGetstartedpane_0// "GetStartedPanePathOutlook"
0x255ce  ldarg.0
0x255cf  call     instance string Microsoft.Crm.Application.SiteMapSubArea::get_GetStartedPanePathOutlook()
0x255d4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x255d9  ldarg.0
0x255da  call     instance string Microsoft.Crm.Application.SiteMapSubArea::get_GetStartedPanePathAdmin()
0x255df  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x255e4  brtrue.s loc_255F7
0x255e6  ldarg.1
0x255e7  ldstr    aGetstartedpane_1// "GetStartedPanePathAdmin"
0x255ec  ldarg.0
0x255ed  call     instance string Microsoft.Crm.Application.SiteMapSubArea::get_GetStartedPanePathAdmin()
0x255f2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x255f7  ldarg.0
0x255f8  call     instance string Microsoft.Crm.Application.SiteMapSubArea::get_GetStartedPanePathAdminOutlook()
0x255fd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x25602  brtrue.s loc_25615
0x25604  ldarg.1
0x25605  ldstr    aGetstartedpane_2// "GetStartedPanePathAdminOutlook"
0x2560a  ldarg.0
0x2560b  call     instance string Microsoft.Crm.Application.SiteMapSubArea::get_GetStartedPanePathAdminOutlook()
0x25610  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x25615  ldarg.0
0x25616  call     instance string Microsoft.Crm.Application.SiteMapSubArea::get_DefaultDashboard()
0x2561b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x25620  brtrue.s loc_25633
0x25622  ldarg.1
0x25623  ldstr    aDefaultdashboa// "DefaultDashboard"
0x25628  ldarg.0
0x25629  call     instance string Microsoft.Crm.Application.SiteMapSubArea::get_DefaultDashboard()
0x2562e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x25633  ldarg.0
0x25634  call     instance string Microsoft.Crm.Application.SiteMapSubArea::get_DynamicPage()
0x25639  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2563e  brtrue.s loc_25651
0x25640  ldarg.1
0x25641  ldstr    aDynamicpage// "DynamicPage"
0x25646  ldarg.0
0x25647  call     instance string Microsoft.Crm.Application.SiteMapSubArea::get_DynamicPage()
0x2564c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x25651  ldarg.1
0x25652  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x25657  ret
```
