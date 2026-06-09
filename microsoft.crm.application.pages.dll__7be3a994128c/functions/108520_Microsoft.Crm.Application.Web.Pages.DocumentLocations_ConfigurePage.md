# Microsoft.Crm.Application.Web.Pages.DocumentLocations::ConfigurePage

- ea: `0x108520`
- end: `0x108b70`
- name: `Microsoft.Crm.Application.Web.Pages.DocumentLocations::ConfigurePage`
- size: `1616`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x108520`
- `0x108b70`

## string_xrefs

- `0x108998`: `DocumentManagementWebService`
- `0x108a57`: `DocumentManagement.CreateFolder.GenericError`
- `0x108ad0`: `LOCID_SHAREPOINT_ACCESS_DENIED`
- `0x108adb`: `DocumentManagement.AddLocation.AccessDenied`
- `0x108b12`: `LOCID_DOCM__INVALID_PROTOCOL`
- `0x108b3e`: `DocumentManagement.Settings.AlternateAccessMappingError`
- `0x108531`: `autocreatelocation`
- `0x108550`: `autocreatelocation`
- `0x108580`: `autocreatelocation`
- `0x108685`: `DocumentManagement.AutoCreate.DefaultLocationName.Text`
- `0x10886a`: `DocumentManagement.AddLocation.InsufficientPrivileges`
- `0x1088a7`: `ListComponentInstalled`
- `0x1088c3`: `ListComponentInstalled`
- `0x10894a`: `documentLocationsXml`

## pseudocode

```c

```

## disassembly

```asm
0x108520  ldarg.0
0x108521  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager::ConfigurePage()
0x108526  ldarg.0
0x108527  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x10852c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x108531  ldstr    aAutocreateloca// "autocreatelocation"
0x108536  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x10853b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x108540  brtrue   loc_10888E
0x108545  ldarg.0
0x108546  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x10854b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x108550  ldstr    aAutocreateloca// "autocreatelocation"
0x108555  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x10855a  call     bool [mscorlib]System.Boolean::Parse(string)
0x10855f  brfalse  loc_10888E
0x108564  ldstr    aSharepointdocu_3// "sharepointdocumentlocation"
0x108569  ldc.i4.s 0x20
0x10856b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x108570  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x108575  brfalse  loc_108859
0x10857a  ldarg.0
0x10857b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x108580  ldstr    aAutocreateloca// "autocreatelocation"
0x108585  ldc.i4.1
0x108586  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x10858b  ldarg.0
0x10858c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x108591  ldstr    aDefaultlocatio// "defaultLocationId"
0x108596  ldarg.0
0x108597  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x10859c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1085a1  ldstr    aDefaultlocatio// "defaultLocationId"
0x1085a6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1085ab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x1085b0  ldarg.0
0x1085b1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1085b6  ldstr    aDefaultlocatio_0// "defaultLocationUrl"
0x1085bb  ldarg.0
0x1085bc  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1085c1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1085c6  ldstr    aDefaultlocatio_0// "defaultLocationUrl"
0x1085cb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1085d0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x1085d5  ldarg.0
0x1085d6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1085db  ldstr    aDefaultlocatio_1// "defaultLocationType"
0x1085e0  ldarg.0
0x1085e1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1085e6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1085eb  ldstr    aDefaultlocatio_1// "defaultLocationType"
0x1085f0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1085f5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1085fa  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x1085ff  conv.i8
0x108600  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x108605  ldarg.0
0x108606  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10860b  ldstr    aSitecollection_1// "siteCollectionUrl"
0x108610  ldarg.0
0x108611  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x108616  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x10861b  ldstr    aSitecollection_1// "siteCollectionUrl"
0x108620  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x108625  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x10862a  ldarg.0
0x10862b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x108630  ldstr    aFoldername// "folderName"
0x108635  ldarg.0
0x108636  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x10863b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x108640  ldstr    aFoldername// "folderName"
0x108645  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x10864a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x10864f  ldarg.0
0x108650  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x108655  ldstr    aEntitycentricp// "entityCentricPrimaryId"
0x10865a  ldarg.0
0x10865b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x108660  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x108665  ldstr    aEcid// "ecId"
0x10866a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x10866f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x108674  ldarg.0
0x108675  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10867a  ldstr    aLocidDocmAutoN// "LOCID_DOCM_AUTO_NAME_FORMAT"
0x10867f  ldarg.0
0x108680  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x108685  ldstr    aDocumentmanage_22// "DocumentManagement.AutoCreate.DefaultLo"...
0x10868a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10868f  ldc.i4.0
0x108690  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x108695  ldarg.0
0x108696  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10869b  ldstr    aLocidDocmDefau// "LOCID_DOCM_DEFAULT_AUTO_NAME"
0x1086a0  ldarg.0
0x1086a1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1086a6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1086ab  ldstr    aDefaultlocatio_2// "defaultLocationName"
0x1086b0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1086b5  ldc.i4.0
0x1086b6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1086bb  ldarg.0
0x1086bc  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x1086c1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x1086c6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x1086cb  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1086d0  ldc.i4   0x2524
0x1086d5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x1086da  ldstr    aName// "name"
0x1086df  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x1086e4  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StringAttributeMetadata
0x1086e9  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.TextAttributeMetadata::get_MaxLength()
0x1086ee  stloc.2
0x1086ef  ldarg.0
0x1086f0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1086f5  ldstr    aDocmLocationna// "DOCM_LOCATIONNAME_MAXLENGTH"
0x1086fa  ldloc.2
0x1086fb  conv.i8
0x1086fc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x108701  ldarg.0
0x108702  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x108707  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x10870c  ldstr    aEcetc// "ecEtc"
0x108711  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x108716  stloc.3
0x108717  ldarg.0
0x108718  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x10871d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x108722  ldstr    aEclogicalname// "ecLogicalName"
0x108727  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x10872c  stloc.s  4
0x10872e  ldarg.0
0x10872f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x108734  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x108739  ldstr    aEntitylogicaln// "entityLogicalName"
0x10873e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x108743  stloc.s  5
0x108745  ldarg.0
0x108746  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10874b  ldstr    aEntitylogicaln// "entityLogicalName"
0x108750  ldloc.s  5
0x108752  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x108757  ldloc.3
0x108758  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10875d  brfalse.s loc_1087C1
0x10875f  ldarg.0
0x108760  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x108765  ldstr    aEntitycentrice// "entityCentricEntityType"
0x10876a  ldc.i4.0
0x10876b  conv.i8
0x10876c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x108771  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x108776  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x10877b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x108780  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x108785  ldloc.s  5
0x108787  ldc.i4.1
0x108788  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x10878d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x108792  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x108797  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_LanguageCode()
0x10879c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1087a1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1087a6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x1087ab  stloc.s  6
0x1087ad  ldarg.0
0x1087ae  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1087b3  ldstr    aEntitydisplayn_1// "entityDisplayName"
0x1087b8  ldloc.s  6
0x1087ba  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x1087bf  br.s     loc_108820
0x1087c1  ldarg.0
0x1087c2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1087c7  ldstr    aEntitycentrice// "entityCentricEntityType"
0x1087cc  ldloc.3
0x1087cd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x1087d2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1087d7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x1087dc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x1087e1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1087e6  ldloc.s  4
0x1087e8  ldc.i4.1
0x1087e9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x1087ee  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x1087f3  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x1087f8  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_LanguageCode()
0x1087fd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x108802  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x108807  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x10880c  stloc.s  7
0x10880e  ldarg.0
0x10880f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x108814  ldstr    aEntitydisplayn_1// "entityDisplayName"
0x108819  ldloc.s  7
0x10881b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x108820  ldarg.0
0x108821  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x108826  ldstr    aEntitycentricp_0// "entityCentricPrimaryName"
0x10882b  ldarg.0
0x10882c  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x108831  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x108836  ldstr    aEcname// "ecName"
0x10883b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x108840  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x108845  ldarg.0
0x108846  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10884b  ldstr    aEntitycentrice_0// "entityCentricEntityName"
0x108850  ldloc.s  4
0x108852  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x108857  br.s     loc_10888E
0x108859  ldarg.0
0x10885a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10885f  ldstr    aLocidDocmInsuf// "LOCID_DOCM_INSUFFICIENT_PRIV"
0x108864  ldarg.0
0x108865  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10886a  ldstr    aDocumentmanage_23// "DocumentManagement.AddLocation.Insuffic"...
0x10886f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x108874  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x108879  ldarg.0
0x10887a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10887f  ldstr    aErrormessage_0// "errorMessage"
0x108884  ldstr    aLocidDocmInsuf// "LOCID_DOCM_INSUFFICIENT_PRIV"
0x108889  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x10888e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x108893  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x108898  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x10889d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1088a2  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x1088a7  ldstr    aListcomponenti// "ListComponentInstalled"
0x1088ac  ldc.i4.0
0x1088ad  box      [mscorlib]System.Boolean
0x1088b2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::GetOrgDBOrgSetting(string, object)
0x1088b7  unbox.any [mscorlib]System.Boolean
0x1088bc  stloc.0
0x1088bd  ldarg.0
0x1088be  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1088c3  ldstr    aListcomponenti// "ListComponentInstalled"
0x1088c8  ldloc.0
0x1088c9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x1088ce  ldarg.0
0x1088cf  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1088d4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1088d9  ldstr    aLocationid// "locationId"
0x1088de  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1088e3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1088e8  brtrue.s loc_108922
0x1088ea  ldarg.0
0x1088eb  ldarg.0
0x1088ec  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1088f1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1088f6  ldstr    aLocationid// "locationId"
0x1088fb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x108900  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x108905  stloc.s  8
0x108907  ldloca.s 8
0x108909  ldstr    aB// "B"
0x10890e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x108913  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x108918  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x10891d  stfld    string Microsoft.Crm.Application.Web.Pages.DocumentLocations::_locationId
0x108922  ldarg.0
0x108923  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x108928  ldstr    aLocidAssociate_0// "LOCID_ASSOCIATE_LOCATION"
0x10892d  ldarg.0
0x10892e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x108933  ldstr    aDocumentmanage_24// "DocumentManagement.AddLocation.Label"
0x108938  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10893d  ldc.i4.0
0x10893e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x108943  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x108948  stloc.1
0x108949  ldloc.1
0x10894a  ldstr    aDocumentlocati// "documentLocationsXml"
0x10894f  ldarg.0
0x108950  call     instance string Microsoft.Crm.Application.Web.Pages.DocumentLocations::RetrieveAssociatedDocumentLocations()
0x108955  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x10895a  ldarg.0
0x10895b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x108960  ldstr    aMscrmDocumentl// "Mscrm.DocumentLocationSelector"
0x108965  ldloc.1
0x108966  ldnull
0x108967  ldnull
0x108968  ldstr    aDocumentsgridD// "documentsGrid_DocumentLocationSelector"
0x10896d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string)
0x108972  ldarg.0
0x108973  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x108978  ldstr    aStaticControls_62// "/_static/_controls/locationselector/Doc"...
0x10897d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x108982  ldarg.0
0x108983  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x108988  ldstr    aStaticToolsDoc_2// "/_static/tools/documentmanagement/scrip"...
0x10898d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x108992  ldarg.0
0x108993  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x108998  ldstr    aDocumentmanage_1// "DocumentManagementWebService"
0x10899d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x1089a2  ldarg.0
0x1089a3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1089a8  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
  ... truncated ...
```
