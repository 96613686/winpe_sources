# Microsoft.Crm.Application.MasterSiteMapSubArea::.ctor_3

- ea: `0x258d0`
- end: `0x25c9a`
- name: `Microsoft.Crm.Application.MasterSiteMapSubArea::.ctor_3`
- size: `970`
- prototype: ``
- caller_count: `6`
- callee_count: `23`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x22230`
- `0x22e00`
- `0x232e0`
- `0x233c0`
- `0x234a0`
- `0x23580`

## callees

- `0x11760`
- `0x24a10`
- `0x24be0`
- `0x24c10`
- `0x24c30`
- `0x24c70`
- `0x24c80`
- `0x24ca0`
- `0x24f50`
- `0x25020`
- `0x25030`
- `0x25050`
- `0x250a0`
- `0x250e0`
- `0x258d0`
- `0x25ca0`
- `0x26080`
- `0x30260`
- `0x308a0`
- `0x39f50`
- `0x39f70`
- `0x47920`
- `0x47940`

## string_xrefs

- `0x25c8a`: `Privilege`
- `0x2596b`: `UpdateBreadcrumb`
- `0x25923`: `GetStartedPanePath`
- `0x2592f`: `GetStartedPanePathOutlook`
- `0x2593b`: `GetStartedPanePathAdmin`
- `0x25947`: `GetStartedPanePathAdminOutlook`
- `0x25a2e`: `CheckExtensionProperty`
- `0x25b65`: `Sitemap subArea with id "{0}" has empty Title. Created title {1} for it`

## pseudocode

```c

```

## disassembly

```asm
0x258d0  ldarg.0
0x258d1  newobj   instance void Microsoft.Crm.Application.PrivilegeIdDictionary::.ctor()
0x258d6  stfld    class Microsoft.Crm.Application.PrivilegeIdDictionary Microsoft.Crm.Application.MasterSiteMapSubArea::_privileges
0x258db  ldarg.0
0x258dc  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x258e1  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Application.MasterSiteMapSubArea::_nonEntityPrivileges
0x258e6  ldarg.0
0x258e7  ldc.i4.7
0x258e8  stfld    valuetype Microsoft.Crm.Application.Types.Client Microsoft.Crm.Application.MasterSiteMapSubArea::_client
0x258ed  ldarg.0
0x258ee  ldc.i4.7
0x258ef  stfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.Application.MasterSiteMapSubArea::_sku
0x258f4  ldarg.0
0x258f5  ldarg.1
0x258f6  ldarg.2
0x258f7  ldstr    aId_0// "Id"
0x258fc  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x25901  ldsfld   string [mscorlib]System.String::Empty
0x25906  ldnull
0x25907  ldnull
0x25908  ldnull
0x25909  ldnull
0x2590a  ldarg.2
0x2590b  ldstr    aDynamicpage// "DynamicPage"
0x25910  ldnull
0x25911  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string, string)
0x25916  ldarg.2
0x25917  ldstr    aPassparams// "PassParams"
0x2591c  ldc.i4.0
0x2591d  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetBooleanAttribute(class [System.Xml]System.Xml.XmlNode, string, bool)
0x25922  ldarg.2
0x25923  ldstr    aGetstartedpane// "GetStartedPanePath"
0x25928  ldnull
0x25929  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string, string)
0x2592e  ldarg.2
0x2592f  ldstr    aGetstartedpane_0// "GetStartedPanePathOutlook"
0x25934  ldnull
0x25935  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string, string)
0x2593a  ldarg.2
0x2593b  ldstr    aGetstartedpane_1// "GetStartedPanePathAdmin"
0x25940  ldnull
0x25941  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string, string)
0x25946  ldarg.2
0x25947  ldstr    aGetstartedpane_2// "GetStartedPanePathAdminOutlook"
0x2594c  ldnull
0x2594d  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string, string)
0x25952  ldarg.2
0x25953  ldstr    aAvailableoffli// "AvailableOffline"
0x25958  ldc.i4.1
0x25959  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetBooleanAttribute(class [System.Xml]System.Xml.XmlNode, string, bool)
0x2595e  ldarg.2
0x2595f  ldstr    aDefaultdashboa// "DefaultDashboard"
0x25964  ldnull
0x25965  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string, string)
0x2596a  ldarg.2
0x2596b  ldstr    aUpdatebreadcru// "UpdateBreadcrumb"
0x25970  ldc.i4.1
0x25971  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetBooleanAttribute(class [System.Xml]System.Xml.XmlNode, string, bool)
0x25976  call     instance void Microsoft.Crm.Application.SiteMapSubArea::.ctor(class Microsoft.Crm.Application.SiteMapGroup parentGroup, string id, string title, class Microsoft.Crm.Application.Utility.CrmUri icon, class Microsoft.Crm.Application.Utility.CrmUri vectorIcon, class Microsoft.Crm.Application.Utility.CrmUri outlookIcon, class Microsoft.Crm.Application.Utility.CrmUri url, string dynamicPage, bool passParameters, string getStartedPanePath, string getStartedPanePathOutlook, string getStartedPanePathAdmin, string getStartedPanePathAdminOutlook, bool availableOffline, string defaultDashboard, bool updateBreadcrumb)
0x2597b  ldarg.3
0x2597c  isinst   [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext
0x25981  stloc.0
0x25982  ldloc.0
0x25983  brfalse.s loc_2598A
0x25985  ldloc.0
0x25986  starg.s  3
0x25988  br.s     loc_25992
0x2598a  ldarg.0
0x2598b  ldfld    class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.SiteMapSubArea::_currentUserInformation
0x25990  starg.s  3
0x25992  ldarg.0
0x25993  ldarg.2
0x25994  ldstr    aIcon_0// "Icon"
0x25999  ldstr    aImgsIco16Gif// "/_imgs/ico_16.gif"
0x2599e  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string, string)
0x259a3  ldarg.3
0x259a4  call     class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string path, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x259a9  call     instance void Microsoft.Crm.Application.SiteMapSubArea::SetIcon(class Microsoft.Crm.Application.Utility.CrmUri value)
0x259ae  ldarg.0
0x259af  ldarg.2
0x259b0  ldstr    aVectoricon// "VectorIcon"
0x259b5  ldnull
0x259b6  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string, string)
0x259bb  ldarg.3
0x259bc  call     class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string path, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x259c1  call     instance void Microsoft.Crm.Application.SiteMapSubArea::SetVectorIcon(class Microsoft.Crm.Application.Utility.CrmUri value)
0x259c6  ldarg.0
0x259c7  ldarg.2
0x259c8  ldstr    aOutlookshortcu// "OutlookShortcutIcon"
0x259cd  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x259d2  ldarg.3
0x259d3  call     class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Utility.CrmUri::Create(string uri, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x259d8  call     instance void Microsoft.Crm.Application.SiteMapSubArea::SetOutlookShortcutIcon(class Microsoft.Crm.Application.Utility.CrmUri value)
0x259dd  ldarg.0
0x259de  ldarg.2
0x259df  ldstr    aUrl// "Url"
0x259e4  ldnull
0x259e5  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string, string)
0x259ea  ldarg.3
0x259eb  call     class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string path, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x259f0  call     instance void Microsoft.Crm.Application.SiteMapSubArea::SetUrl(class Microsoft.Crm.Application.Utility.CrmUri value)
0x259f5  ldarg.0
0x259f6  ldtoken  Microsoft.Crm.Application.Types.Client
0x259fb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x25a00  ldarg.2
0x25a01  ldstr    aClient// "Client"
0x25a06  ldarg.0
0x25a07  ldflda   valuetype Microsoft.Crm.Application.Types.Client Microsoft.Crm.Application.MasterSiteMapSubArea::_client
0x25a0c  constrained. Microsoft.Crm.Application.Types.Client
0x25a12  callvirt instance string [mscorlib]System.Object::ToString()
0x25a17  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string, string)
0x25a1c  ldc.i4.0
0x25a1d  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string, bool)
0x25a22  unbox.any Microsoft.Crm.Application.Types.Client
0x25a27  stfld    valuetype Microsoft.Crm.Application.Types.Client Microsoft.Crm.Application.MasterSiteMapSubArea::_client
0x25a2c  ldarg.0
0x25a2d  ldarg.2
0x25a2e  ldstr    aCheckextension// "CheckExtensionProperty"
0x25a33  ldarg.0
0x25a34  ldfld    string Microsoft.Crm.Application.MasterSiteMapSubArea::_extensionPropertyName
0x25a39  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string, string)
0x25a3e  stfld    string Microsoft.Crm.Application.MasterSiteMapSubArea::_extensionPropertyName
0x25a43  ldarg.2
0x25a44  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x25a49  ldstr    aSku// "Sku"
0x25a4e  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x25a53  brfalse.s loc_25A8C
0x25a55  ldarg.0
0x25a56  ldtoken  [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku
0x25a5b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x25a60  ldarg.2
0x25a61  ldstr    aSku// "Sku"
0x25a66  ldarg.0
0x25a67  ldflda   valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.Application.MasterSiteMapSubArea::_sku
0x25a6c  constrained. [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku
0x25a72  callvirt instance string [mscorlib]System.Object::ToString()
0x25a77  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string, string)
0x25a7c  ldc.i4.0
0x25a7d  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string, bool)
0x25a82  unbox.any [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku
0x25a87  stfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.Application.MasterSiteMapSubArea::_sku
0x25a8c  ldarg.2
0x25a8d  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x25a92  ldstr    aTitle// "Title"
0x25a97  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x25a9c  brfalse.s loc_25AB6
0x25a9e  ldarg.0
0x25a9f  ldarg.2
0x25aa0  ldstr    aTitle// "Title"
0x25aa5  ldsfld   string [mscorlib]System.String::Empty
0x25aaa  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string, string)
0x25aaf  call     instance void Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::SetTitle(string value)
0x25ab4  br.s     loc_25B2A
0x25ab6  ldarg.2
0x25ab7  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x25abc  ldstr    aResourceid_0// "ResourceId"
0x25ac1  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x25ac6  brfalse.s loc_25B2A
0x25ac8  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x25acd  ldarg.2
0x25ace  ldstr    aResourceid_0// "ResourceId"
0x25ad3  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x25ad8  ldarg.0
0x25ad9  ldfld    class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.SiteMapSubArea::_currentUserInformation
0x25ade  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::TryGetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x25ae3  stloc.1
0x25ae4  ldloc.1
0x25ae5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x25aea  brfalse.s loc_25B23
0x25aec  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x25af1  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x25af6  ldstr    aCanTFindResour_2// "Can't find resource with id \"{0}\" for"...
0x25afb  ldc.i4.2
0x25afc  newarr   [mscorlib]System.Object
0x25b01  dup
0x25b02  ldc.i4.0
0x25b03  ldarg.2
0x25b04  ldstr    aResourceid_0// "ResourceId"
0x25b09  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x25b0e  stelem.ref
0x25b0f  dup
0x25b10  ldc.i4.1
0x25b11  ldarg.0
0x25b12  call     instance string Microsoft.Crm.Application.SiteMapSubArea::get_Id()
0x25b17  stelem.ref
0x25b18  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x25b1d  ldsfld   string [mscorlib]System.String::Empty
0x25b22  stloc.1
0x25b23  ldarg.0
0x25b24  ldloc.1
0x25b25  call     instance void Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::SetTitle(string value)
0x25b2a  ldarg.0
0x25b2b  call     instance string Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::get_Title()
0x25b30  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x25b35  brfalse.s loc_25B95
0x25b37  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x25b3c  ldstr    aWebCrmtodayXsl// "Web.crmToday.xsl.aspx_122"
0x25b41  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x25b46  ldsflda  int32 Microsoft.Crm.Application.MasterSiteMapSubArea::_blankSubAreaTitleCount
0x25b4b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x25b50  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x25b55  call     string [mscorlib]System.String::Concat(string, string)
0x25b5a  stloc.2
0x25b5b  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x25b60  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x25b65  ldstr    aSitemapSubarea// "Sitemap subArea with id \"{0}\" has emp"...
0x25b6a  ldc.i4.2
0x25b6b  newarr   [mscorlib]System.Object
0x25b70  dup
0x25b71  ldc.i4.0
0x25b72  ldarg.0
0x25b73  call     instance string Microsoft.Crm.Application.SiteMapSubArea::get_Id()
0x25b78  stelem.ref
0x25b79  dup
0x25b7a  ldc.i4.1
0x25b7b  ldloc.2
0x25b7c  stelem.ref
0x25b7d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x25b82  ldarg.0
0x25b83  ldloc.2
0x25b84  call     instance void Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::SetTitle(string value)
0x25b89  ldsfld   int32 Microsoft.Crm.Application.MasterSiteMapSubArea::_blankSubAreaTitleCount
0x25b8e  ldc.i4.1
0x25b8f  add
0x25b90  stsfld   int32 Microsoft.Crm.Application.MasterSiteMapSubArea::_blankSubAreaTitleCount
0x25b95  ldarg.2
0x25b96  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x25b9b  ldstr    aDescription_1// "Description"
0x25ba0  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x25ba5  brfalse.s loc_25BBF
0x25ba7  ldarg.0
0x25ba8  ldarg.2
0x25ba9  ldstr    aDescription_1// "Description"
0x25bae  ldsfld   string [mscorlib]System.String::Empty
0x25bb3  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string, string)
0x25bb8  call     instance void Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::SetDescription(string value)
0x25bbd  br.s     loc_25C3D
0x25bbf  ldarg.2
0x25bc0  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x25bc5  ldstr    aDescriptionres// "DescriptionResourceId"
0x25bca  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x25bcf  brfalse.s loc_25C3D
0x25bd1  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x25bd6  ldarg.2
0x25bd7  ldstr    aDescriptionres// "DescriptionResourceId"
0x25bdc  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x25be1  ldarg.0
0x25be2  ldfld    class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.SiteMapSubArea::_currentUserInformation
0x25be7  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::TryGetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x25bec  stloc.3
0x25bed  ldloc.3
0x25bee  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x25bf3  brfalse.s loc_25C36
0x25bf5  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x25bfa  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x25bff  ldstr    aCanTFindResour_2// "Can't find resource with id \"{0}\" for"...
0x25c04  ldc.i4.2
0x25c05  newarr   [mscorlib]System.Object
0x25c0a  dup
0x25c0b  ldc.i4.0
0x25c0c  ldarg.2
0x25c0d  ldstr    aDescriptionres// "DescriptionResourceId"
0x25c12  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x25c17  stelem.ref
0x25c18  dup
0x25c19  ldc.i4.1
0x25c1a  ldarg.0
0x25c1b  call     instance string Microsoft.Crm.Application.SiteMapSubArea::get_Id()
0x25c20  stelem.ref
0x25c21  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x25c26  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x25c2b  ldstr    aWebCrmtodayXsl// "Web.crmToday.xsl.aspx_122"
0x25c30  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x25c35  stloc.3
0x25c36  ldarg.0
0x25c37  ldloc.3
0x25c38  call     instance void Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::SetDescription(string value)
0x25c3d  ldarg.2
0x25c3e  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x25c43  ldstr    aTooltipresours// "ToolTipResourseId"
0x25c48  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x25c4d  brfalse.s loc_25C70
0x25c4f  ldarg.0
0x25c50  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x25c55  ldarg.2
0x25c56  ldstr    aTooltipresours// "ToolTipResourseId"
0x25c5b  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x25c60  ldarg.0
0x25c61  ldfld    class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.SiteMapSubArea::_currentUserInformation
0x25c66  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::TryGetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x25c6b  call     instance void Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::SetToolTip(string value)
0x25c70  ldarg.0
0x25c71  call     instance class Microsoft.Crm.Application.PairDictionaryHelper Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::get_TitlesHelper()
0x25c76  ldarg.2
0x25c77  callvirt instance void Microsoft.Crm.Application.PairDictionaryHelper::AddToDictionary(class [System.Xml]System.Xml.XPath.IXPathNavigable navigable)
0x25c7c  ldarg.0
0x25c7d  call     instance class Microsoft.Crm.Application.PairDictionaryHelper Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::get_DescriptionsHelper()
0x25c82  ldarg.2
0x25c83  callvirt instance void Microsoft.Crm.Application.PairDictionaryHelper::AddToDictionary(class [System.Xml]System.Xml.XPath.IXPathNavigable navigable)
0x25c88  ldarg.0
  ... truncated ...
```
