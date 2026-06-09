# Microsoft.Crm.Web.Tools.AppsForCrm.AppsForCrmPage::ConfigurePage

- ea: `0x870a0`
- end: `0x8724b`
- name: `Microsoft.Crm.Web.Tools.AppsForCrm.AppsForCrmPage::ConfigurePage`
- size: `427`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x870a0`
- `0x87250`
- `0x874f0`
- `0x87580`

## string_xrefs

- `0x87191`: `IsServerSideSyncEnabledForOrg`
- `0x871a4`: `IsServerSideSyncEnabledForUser`
- `0x871f9`: `IsServerSideSyncEnabledForUser`
- `0x8720c`: `IsServerSideSyncEnabledForUser`

## pseudocode

```c

```

## disassembly

```asm
0x870a0  ldarg.0
0x870a1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::ConfigureForm()
0x870a6  ldarg.0
0x870a7  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.Crm.Web.Tools.AppsForCrm.AppsForCrmPage::orgUrl
0x870ac  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetWebServer()
0x870b1  callvirt instance void [System.Web]System.Web.UI.WebControls.Label::set_Text(string)
0x870b6  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x870bb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x870c0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x870c5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x870ca  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x870cf  stloc.0
0x870d0  ldloc.0
0x870d1  brfalse.s loc_870FD
0x870d3  ldarg.0
0x870d4  ldloc.0
0x870d5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_SignupOutlookDownloadFWLink()
0x870da  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x870df  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x870e4  call     instance class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UrlBuilder Microsoft.Crm.Web.Tools.AppsForCrm.AppsForCrmPage::AddLocaleToForwardingLink(string forwardingLink, int32 locale)
0x870e9  stloc.s  4
0x870eb  ldarg.0
0x870ec  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.Crm.Web.Tools.AppsForCrm.AppsForCrmPage::SignupOutlookDownloadFWLink
0x870f1  ldloc.s  4
0x870f3  callvirt instance string [mscorlib]System.Object::ToString()
0x870f8  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x870fd  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsIfdEnabled()
0x87102  stloc.1
0x87103  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnPremise()
0x87108  stloc.2
0x87109  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8710e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x87113  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.SolutionHelper::IsCRMOrg(valuetype [mscorlib]System.Guid)
0x87118  stloc.3
0x87119  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x8711e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x87123  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_PotassiumAppForOutlook()
0x87128  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8712d  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x87132  ldloc.3
0x87133  and
0x87134  brfalse  loc_87220
0x87139  ldarg.0
0x8713a  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Web.Tools.AppsForCrm.AppsForCrmPage::mailAppSection
0x8713f  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x87144  ldstr    aDisplay// "display"
0x87149  ldstr    asc_11EF2A// ""
0x8714e  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x87153  ldloc.0
0x87154  brfalse  loc_8723A
0x87159  ldloc.2
0x8715a  brfalse.s loc_87172
0x8715c  ldloc.1
0x8715d  brtrue.s loc_87172
0x8715f  ldarg.0
0x87160  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x87165  ldstr    aIsonpremserver// "IsOnPremServerIFDEnabled"
0x8716a  ldc.i4.0
0x8716b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x87170  br.s     loc_87183
0x87172  ldarg.0
0x87173  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x87178  ldstr    aIsonpremserver// "IsOnPremServerIFDEnabled"
0x8717d  ldc.i4.1
0x8717e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x87183  ldloc.0
0x87184  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailConnectionChannelType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_EmailConnectionChannel()
0x87189  brtrue.s loc_8719E
0x8718b  ldarg.0
0x8718c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x87191  ldstr    aIsserversidesy// "IsServerSideSyncEnabledForOrg"
0x87196  ldc.i4.1
0x87197  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x8719c  br.s     loc_871AF
0x8719e  ldarg.0
0x8719f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x871a4  ldstr    aIsserversidesy_0// "IsServerSideSyncEnabledForUser"
0x871a9  ldc.i4.0
0x871aa  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x871af  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MailboxCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MailboxCache::Instance()
0x871b4  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x871b9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_DefaultMailbox()
0x871be  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x871c3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x871c8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x871cd  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData>::LookupEntry(void, var<u1>)
0x871d2  stloc.s  5
0x871d4  ldloc.s  5
0x871d6  brfalse.s loc_87217
0x871d8  ldloc.s  5
0x871da  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailDeliveryMethod [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_IncomingEmailDeliveryMethod()
0x871df  ldc.i4.2
0x871e0  ceq
0x871e2  ldloc.s  5
0x871e4  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MailboxAccessStatus [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_IncomingEmailStatus()
0x871e9  ldc.i4.1
0x871ea  ceq
0x871ec  stloc.s  6
0x871ee  ldloc.s  6
0x871f0  and
0x871f1  brfalse.s loc_87206
0x871f3  ldarg.0
0x871f4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x871f9  ldstr    aIsserversidesy_0// "IsServerSideSyncEnabledForUser"
0x871fe  ldc.i4.1
0x871ff  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x87204  br.s     loc_87217
0x87206  ldarg.0
0x87207  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8720c  ldstr    aIsserversidesy_0// "IsServerSideSyncEnabledForUser"
0x87211  ldc.i4.0
0x87212  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x87217  ldarg.0
0x87218  call     instance bool Microsoft.Crm.Web.Tools.AppsForCrm.AppsForCrmPage::CheckIfCurrentUserHasOfficeAppsPrivilege()
0x8721d  pop
0x8721e  br.s     loc_8723A
0x87220  ldarg.0
0x87221  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Web.Tools.AppsForCrm.AppsForCrmPage::mailAppSection
0x87226  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x8722b  ldstr    aDisplay// "display"
0x87230  ldstr    aNone_0// "none"
0x87235  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x8723a  ldarg.0
0x8723b  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x87240  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x87245  call     instance void Microsoft.Crm.Web.Tools.AppsForCrm.AppsForCrmPage::LoadLanguageSpecificImages(int32 lcid)
0x8724a  ret
```
