# Microsoft.Crm.Application.MasterSiteMapArea::.ctor_0

- ea: `0x218f0`
- end: `0x21ea1`
- name: `Microsoft.Crm.Application.MasterSiteMapArea::.ctor_0`
- size: `1457`
- prototype: ``
- caller_count: `1`
- callee_count: `33`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x24780`

## callees

- `0x82d0`
- `0x83d0`
- `0x83f0`
- `0x11760`
- `0x21480`
- `0x214f0`
- `0x21560`
- `0x21590`
- `0x215d0`
- `0x218f0`
- `0x22010`
- `0x227e0`
- `0x22930`
- `0x22950`
- `0x23270`
- `0x24a10`
- `0x24be0`
- `0x24c10`
- `0x24c30`
- `0x24c70`
- `0x24c80`
- `0x24ca0`
- `0x26310`
- `0x2fb90`
- `0x30260`
- `0x308a0`
- `0x337d0`
- `0x39f70`
- `0x440f0`
- `0x47920`
- `0x47940`
- `0x487e0`
- `0x49ba0`

## string_xrefs

- `0x21dee`: `Extensions`
- `0x2194a`: `UpdateBreadcrumb`
- `0x21a42`: `Sitemap area with id "{0}" has an empty title (Areas have to have titles.). Create a title {1} for it`
- `0x21d8f`: `A site map group with title {0} already exists, it will not be added.  The site groups must have unique titles under a single area.\nDuplicate site map group XML : {1}`
- `0x21df4`: `Group_Extensions`
- `0x21e03`: `Extensions_Description`
- `0x21e78`: `ISV Extensions group with title {0} already exists, it will not be added.  The site groups must have unique titles under a single area.`

## pseudocode

```c

```

## disassembly

```asm
0x218f0  ldarg.0
0x218f1  ldarg.1
0x218f2  ldarg.2
0x218f3  ldstr    aId_0// "Id"
0x218f8  ldnull
0x218f9  call     string Microsoft.Crm.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode node, string attributeName, string defaultValue)
0x218fe  ldsfld   string [mscorlib]System.String::Empty
0x21903  ldarg.2
0x21904  ldstr    aIcon_0// "Icon"
0x21909  ldstr    aImgsDefaultsit// "/_imgs/defaultsitemaparea_24x24.gif"
0x2190e  call     string Microsoft.Crm.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode node, string attributeName, string defaultValue)
0x21913  ldarg.3
0x21914  call     class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string path, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x21919  ldarg.2
0x2191a  ldstr    aVectoricon// "VectorIcon"
0x2191f  ldnull
0x21920  call     string Microsoft.Crm.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode node, string attributeName, string defaultValue)
0x21925  ldarg.3
0x21926  call     class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string path, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x2192b  ldarg.2
0x2192c  ldstr    aUrl// "Url"
0x21931  ldnull
0x21932  call     string Microsoft.Crm.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode node, string attributeName, string defaultValue)
0x21937  ldarg.3
0x21938  call     class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string path, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x2193d  ldarg.2
0x2193e  ldstr    aShowgroups// "ShowGroups"
0x21943  ldc.i4.0
0x21944  call     bool Microsoft.Crm.XmlUtil::GetBooleanAttribute(class [System.Xml]System.Xml.XmlNode node, string attributeName, bool defaultValue)
0x21949  ldarg.2
0x2194a  ldstr    aUpdatebreadcru// "UpdateBreadcrumb"
0x2194f  ldc.i4.1
0x21950  call     bool Microsoft.Crm.XmlUtil::GetBooleanAttribute(class [System.Xml]System.Xml.XmlNode node, string attributeName, bool defaultValue)
0x21955  ldsfld   string [mscorlib]System.String::Empty
0x2195a  call     instance void Microsoft.Crm.Application.SiteMapArea::.ctor(class Microsoft.Crm.Application.SiteMap siteMap, string id, string title, class Microsoft.Crm.Application.Utility.CrmUri icon, class Microsoft.Crm.Application.Utility.CrmUri vectorIcon, class Microsoft.Crm.Application.Utility.CrmUri url, bool showGroups, bool updateBreadcrumb, string description)
0x2195f  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x21964  stloc.0
0x21965  ldarg.2
0x21966  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2196b  ldstr    aTitle// "Title"
0x21970  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x21975  brfalse.s loc_2198F
0x21977  ldarg.0
0x21978  ldarg.2
0x21979  ldstr    aTitle// "Title"
0x2197e  ldsfld   string [mscorlib]System.String::Empty
0x21983  call     string Microsoft.Crm.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode node, string attributeName, string defaultValue)
0x21988  call     instance void Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::SetTitle(string value)
0x2198d  br.s     loc_21A06
0x2198f  ldarg.2
0x21990  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x21995  ldstr    aResourceid_0// "ResourceId"
0x2199a  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x2199f  brfalse.s loc_21A06
0x219a1  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x219a6  ldarg.2
0x219a7  ldstr    aResourceid_0// "ResourceId"
0x219ac  call     string Microsoft.Crm.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode node, string attributeName)
0x219b1  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x219b6  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::TryGetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x219bb  stloc.s  4
0x219bd  ldloc.s  4
0x219bf  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x219c4  brfalse.s loc_219FE
0x219c6  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x219cb  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x219d0  ldstr    aCanTFindResour// "Can't find resource with id \"{0}\" for"...
0x219d5  ldc.i4.2
0x219d6  newarr   [mscorlib]System.Object
0x219db  dup
0x219dc  ldc.i4.0
0x219dd  ldarg.2
0x219de  ldstr    aResourceid_0// "ResourceId"
0x219e3  call     string Microsoft.Crm.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode node, string attributeName)
0x219e8  stelem.ref
0x219e9  dup
0x219ea  ldc.i4.1
0x219eb  ldarg.0
0x219ec  call     instance string Microsoft.Crm.Application.SiteMapArea::get_Id()
0x219f1  stelem.ref
0x219f2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x219f7  ldsfld   string [mscorlib]System.String::Empty
0x219fc  stloc.s  4
0x219fe  ldarg.0
0x219ff  ldloc.s  4
0x21a01  call     instance void Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::SetTitle(string value)
0x21a06  ldarg.0
0x21a07  call     instance string Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::get_Title()
0x21a0c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x21a11  brfalse.s loc_21A74
0x21a13  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x21a18  ldstr    aWebCrmtodayXsl// "Web.crmToday.xsl.aspx_122"
0x21a1d  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x21a22  ldsflda  int32 Microsoft.Crm.Application.MasterSiteMapArea::_blankAreaTitleCount
0x21a27  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x21a2c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x21a31  call     string [mscorlib]System.String::Concat(string, string)
0x21a36  stloc.s  5
0x21a38  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x21a3d  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x21a42  ldstr    aSitemapAreaWit// "Sitemap area with id \"{0}\" has an emp"...
0x21a47  ldc.i4.2
0x21a48  newarr   [mscorlib]System.Object
0x21a4d  dup
0x21a4e  ldc.i4.0
0x21a4f  ldarg.0
0x21a50  call     instance string Microsoft.Crm.Application.SiteMapArea::get_Id()
0x21a55  stelem.ref
0x21a56  dup
0x21a57  ldc.i4.1
0x21a58  ldloc.s  5
0x21a5a  stelem.ref
0x21a5b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x21a60  ldarg.0
0x21a61  ldloc.s  5
0x21a63  call     instance void Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::SetTitle(string value)
0x21a68  ldsfld   int32 Microsoft.Crm.Application.MasterSiteMapArea::_blankAreaTitleCount
0x21a6d  ldc.i4.1
0x21a6e  add
0x21a6f  stsfld   int32 Microsoft.Crm.Application.MasterSiteMapArea::_blankAreaTitleCount
0x21a74  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x21a79  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x21a7e  ldstr    aLoadingSiteMap// "Loading site map area \"{0}\""
0x21a83  ldc.i4.1
0x21a84  newarr   [mscorlib]System.Object
0x21a89  dup
0x21a8a  ldc.i4.0
0x21a8b  ldarg.0
0x21a8c  call     instance string Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::get_Title()
0x21a91  stelem.ref
0x21a92  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x21a97  ldarg.2
0x21a98  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x21a9d  ldstr    aDescription_1// "Description"
0x21aa2  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x21aa7  brfalse.s loc_21AC4
0x21aa9  ldarg.0
0x21aaa  ldarg.2
0x21aab  ldstr    aDescription_1// "Description"
0x21ab0  ldsfld   string [mscorlib]System.String::Empty
0x21ab5  call     string Microsoft.Crm.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode node, string attributeName, string defaultValue)
0x21aba  call     instance void Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::SetDescription(string value)
0x21abf  br       loc_21B45
0x21ac4  ldarg.2
0x21ac5  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x21aca  ldstr    aDescriptionres// "DescriptionResourceId"
0x21acf  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x21ad4  brfalse.s loc_21B45
0x21ad6  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x21adb  ldarg.2
0x21adc  ldstr    aDescriptionres// "DescriptionResourceId"
0x21ae1  call     string Microsoft.Crm.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode node, string attributeName)
0x21ae6  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x21aeb  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::TryGetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x21af0  stloc.s  6
0x21af2  ldloc.s  6
0x21af4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x21af9  brfalse.s loc_21B3D
0x21afb  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x21b00  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x21b05  ldstr    aCanTFindResour_0// "Can't find resource with id \"{0}\" for"...
0x21b0a  ldc.i4.2
0x21b0b  newarr   [mscorlib]System.Object
0x21b10  dup
0x21b11  ldc.i4.0
0x21b12  ldarg.2
0x21b13  ldstr    aDescriptionres// "DescriptionResourceId"
0x21b18  call     string Microsoft.Crm.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode node, string attributeName)
0x21b1d  stelem.ref
0x21b1e  dup
0x21b1f  ldc.i4.1
0x21b20  ldarg.0
0x21b21  call     instance string Microsoft.Crm.Application.SiteMapArea::get_Id()
0x21b26  stelem.ref
0x21b27  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x21b2c  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x21b31  ldstr    aWebCrmtodayXsl// "Web.crmToday.xsl.aspx_122"
0x21b36  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x21b3b  stloc.s  6
0x21b3d  ldarg.0
0x21b3e  ldloc.s  6
0x21b40  call     instance void Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::SetDescription(string value)
0x21b45  ldarg.2
0x21b46  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x21b4b  ldstr    aTooltipresours// "ToolTipResourseId"
0x21b50  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x21b55  brfalse.s loc_21B7C
0x21b57  ldarg.0
0x21b58  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x21b5d  ldarg.2
0x21b5e  ldstr    aTooltipresours// "ToolTipResourseId"
0x21b63  ldsfld   string [mscorlib]System.String::Empty
0x21b68  call     string Microsoft.Crm.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode node, string attributeName, string defaultValue)
0x21b6d  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x21b72  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::TryGetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x21b77  call     instance void Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::SetToolTip(string value)
0x21b7c  ldarg.0
0x21b7d  call     instance class Microsoft.Crm.Application.PairDictionaryHelper Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::get_TitlesHelper()
0x21b82  ldarg.2
0x21b83  callvirt instance void Microsoft.Crm.Application.PairDictionaryHelper::AddToDictionary(class [System.Xml]System.Xml.XPath.IXPathNavigable navigable)
0x21b88  ldarg.0
0x21b89  call     instance class Microsoft.Crm.Application.PairDictionaryHelper Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::get_DescriptionsHelper()
0x21b8e  ldarg.2
0x21b8f  callvirt instance void Microsoft.Crm.Application.PairDictionaryHelper::AddToDictionary(class [System.Xml]System.Xml.XPath.IXPathNavigable navigable)
0x21b94  ldarg.2
0x21b95  ldstr    aGroupSubareaId// "Group/SubArea[@Id = 'nav_mobileoffline'"...
0x21b9a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x21b9f  stloc.1
0x21ba0  ldloc.1
0x21ba1  brfalse.s loc_21BB0
0x21ba3  ldloc.1
0x21ba4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x21ba9  ldloc.1
0x21baa  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x21baf  pop
0x21bb0  ldarg.3
0x21bb1  call     bool Microsoft.Crm.Application.Utility.Util::IsMocaOfflineFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x21bb6  brtrue.s loc_21C10
0x21bb8  ldarg.2
0x21bb9  ldstr    aId_0// "Id"
0x21bbe  ldnull
0x21bbf  call     string Microsoft.Crm.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode node, string attributeName, string defaultValue)
0x21bc4  ldstr    aSettings// "Settings"
0x21bc9  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x21bce  brtrue.s loc_21C10
0x21bd0  ldarg.2
0x21bd1  ldstr    aGroupSubareaId_0// "Group/SubArea[@Id = 'nav_mocaoffline']"
0x21bd6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x21bdb  stloc.s  7
0x21bdd  ldloc.s  7
0x21bdf  brfalse.s loc_21BF0
0x21be1  ldloc.s  7
0x21be3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x21be8  ldloc.s  7
0x21bea  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x21bef  pop
0x21bf0  ldarg.2
0x21bf1  ldstr    aGroupSubareaId_1// "Group/SubArea[@Id = 'nav_syncerror']"
0x21bf6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x21bfb  stloc.s  8
0x21bfd  ldloc.s  8
0x21bff  brfalse.s loc_21C10
0x21c01  ldloc.s  8
0x21c03  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x21c08  ldloc.s  8
0x21c0a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x21c0f  pop
0x21c10  ldarg.0
0x21c11  ldarg.3
0x21c12  call     instance bool Microsoft.Crm.Application.MasterSiteMapArea::IsRelationshipIntelligenceEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x21c17  stloc.2
0x21c18  call     bool Microsoft.Crm.Application.Utility.Util::IsSystemAdministrator()
0x21c1d  stloc.3
0x21c1e  ldarg.2
0x21c1f  ldstr    aId_0// "Id"
0x21c24  ldnull
0x21c25  call     string Microsoft.Crm.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode node, string attributeName, string defaultValue)
0x21c2a  ldstr    aSettings// "Settings"
0x21c2f  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x21c34  brtrue.s loc_21C88
0x21c36  ldloc.2
0x21c37  brfalse.s loc_21C3C
0x21c39  ldloc.3
0x21c3a  brtrue.s loc_21C88
0x21c3c  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x21c41  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x21c46  ldstr    aRemovingNavRel// "Removing nav_relationshipIntelligence a"...
0x21c4b  ldc.i4.2
0x21c4c  newarr   [mscorlib]System.Object
0x21c51  dup
0x21c52  ldc.i4.0
0x21c53  ldloc.2
0x21c54  box      [mscorlib]System.Boolean
0x21c59  stelem.ref
0x21c5a  dup
0x21c5b  ldc.i4.1
0x21c5c  ldloc.3
0x21c5d  box      [mscorlib]System.Boolean
0x21c62  stelem.ref
0x21c63  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x21c68  ldarg.2
0x21c69  ldstr    aGroupSubareaId_2// "Group/SubArea[@Id = 'nav_relationshipIn"...
0x21c6e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x21c73  stloc.s  9
0x21c75  ldloc.s  9
0x21c77  brfalse.s loc_21C88
0x21c79  ldloc.s  9
0x21c7b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x21c80  ldloc.s  9
0x21c82  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x21c87  pop
0x21c88  ldarg.3
0x21c89  call     bool Microsoft.Crm.Application.Utility.MicrosoftFlowUtils::IsMicrosoftFlowIntegrationEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x21c8e  brfalse.s loc_21C9D
0x21c90  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x21c95  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x21c9a  ldc.i4.1
0x21c9b  bne.un.s loc_21CDD
0x21c9d  ldarg.2
0x21c9e  ldstr    aGroupSubareaId_3// "Group/SubArea[@Id = 'nav_microsoftflow'"...
  ... truncated ...
```
