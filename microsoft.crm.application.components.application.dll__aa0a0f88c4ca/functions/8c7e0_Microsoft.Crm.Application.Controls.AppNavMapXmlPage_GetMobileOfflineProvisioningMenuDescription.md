# Microsoft.Crm.Application.Controls.AppNavMapXmlPage::GetMobileOfflineProvisioningMenuDescription

- ea: `0x8c7e0`
- end: `0x8c89c`
- name: `Microsoft.Crm.Application.Controls.AppNavMapXmlPage::GetMobileOfflineProvisioningMenuDescription`
- size: `188`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x8c7d0`
- `0x8c7e0`

## string_xrefs

- `0x8c7ed`: `Web.Tools.MobileOfflineProvisioning.Config.DisabledTitle.Help.OnPremOrIFD`
- `0x8c80e`: `Web.Tools.MobileOfflineProvisioning.Config.DisabledTitle.Help.Version`
- `0x8c871`: `Web.Tools.MobileOfflineProvisioning.Config.DisabledTitle.Help.OrgType`
- `0x8c881`: `Web.Tools.MobileOfflineProvisioning.Config.DisabledTitle.Help.OrgTypeNonFCB`
- `0x8c891`: `Web.Tools.MobileOfflineProvisioning.Config.DisabledTitle.Help.Generic`

## pseudocode

```c

```

## disassembly

```asm
0x8c7e0  ldarg.0
0x8c7e1  call     instance bool Microsoft.Crm.Application.Controls.AppNavMapXmlPage::IsOnlineOrg()
0x8c7e6  brtrue.s loc_8C7F8
0x8c7e8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c7ed  ldstr    aWebToolsMobile// "Web.Tools.MobileOfflineProvisioning.Con"...
0x8c7f2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c7f7  ret
0x8c7f8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8c7fd  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MobileOfflineEligibilityChecker::IsOrgAraPlus(class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x8c802  brtrue.s loc_8C840
0x8c804  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8c809  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c80e  ldstr    aWebToolsMobile_0// "Web.Tools.MobileOfflineProvisioning.Con"...
0x8c813  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c818  ldc.i4.1
0x8c819  newarr   [mscorlib]System.Object
0x8c81e  dup
0x8c81f  ldc.i4.0
0x8c820  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c825  ldstr    aBrandCrmOnline_0// "Brand_CRM_Online_Trademark"
0x8c82a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c82f  ldstr    a1_9// " 1"
0x8c834  call     string [mscorlib]System.String::Concat(string, string)
0x8c839  stelem.ref
0x8c83a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8c83f  ret
0x8c840  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8c845  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MobileOfflineEligibilityChecker::IsOrgTypeEligibleForMobileOffline(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8c84a  brtrue.s loc_8C88C
0x8c84c  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x8c851  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x8c856  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_MobileOfflineDefaultNonProductionInstanceSupport()
0x8c85b  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x8c860  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8c865  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8c86a  brfalse.s loc_8C87C
0x8c86c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c871  ldstr    aWebToolsMobile_1// "Web.Tools.MobileOfflineProvisioning.Con"...
0x8c876  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c87b  ret
0x8c87c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c881  ldstr    aWebToolsMobile_2// "Web.Tools.MobileOfflineProvisioning.Con"...
0x8c886  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c88b  ret
0x8c88c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c891  ldstr    aWebToolsMobile_3// "Web.Tools.MobileOfflineProvisioning.Con"...
0x8c896  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c89b  ret
```
