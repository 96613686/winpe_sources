# Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::ConfigureHeader

- ea: `0x69f90`
- end: `0x6a13f`
- name: `Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::ConfigureHeader`
- size: `431`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x69e50`
- `0x69e60`
- `0x69e70`
- `0x69e80`
- `0x69f90`

## string_xrefs

- `0x69fe8`: `Web.Tools.MobileOfflineProvisioning.Config.MobileOfflineProvisionedConfirmation`
- `0x6a009`: `Web.Tools.MobileOfflineProvisioning.Config.MobileOfflineDeprovisionedConfirmation`
- `0x6a02a`: `Web.Tools.MobileOfflineProvisioning.Config.DisableWarningTitle`
- `0x6a096`: `Web.Tools.MobileOfflineProvisioning.Config.MobileOfflineProvisioningStatusInProcess`
- `0x6a11e`: `Web.Tools.MobileOfflineProvisioning.Config.MobileOfflineProvisioningStatusInProcess`
- `0x6a0b9`: `Web.Tools.MobileOfflineProvisioning.Config.MobileOfflineDedicatedStatusInProcess`
- `0x6a0da`: `Web.Tools.MobileOfflineProvisioning.Config.DisableDedicatedWarningMessage`
- `0x6a0fd`: `Web.Tools.MobileOfflineProvisioning.Config.DisableWarningMessage`
- `0x6a134`: `/Tools/MobileOffline/cmds/cmd_update.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x69f90  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x69f95  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MobileOfflineEligibilityChecker::IsOrgEligibleForMobileOffline(class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x69f9a  pop
0x69f9b  ldarg.0
0x69f9c  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::ConfigureHeader()
0x69fa1  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::.ctor()
0x69fa6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x69fab  ldarg.0
0x69fac  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x69fb1  ldc.i4.1
0x69fb2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0x69fb7  ldarg.0
0x69fb8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x69fbd  ldstr    aToolsMobileoff_0// "/tools/MobileOffline/MobileOfflineStyle"...
0x69fc2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x69fc7  ldarg.0
0x69fc8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x69fcd  ldstr    aStaticToolsMob// "/_static/tools/mobileoffline/scripts/mo"...
0x69fd2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x69fd7  ldarg.0
0x69fd8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x69fdd  ldstr    aLocidMopProvis// "LOCID_MOP_PROVISIONED_CONFIRM"
0x69fe2  ldarg.0
0x69fe3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x69fe8  ldstr    aWebToolsMobile_0// "Web.Tools.MobileOfflineProvisioning.Con"...
0x69fed  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x69ff2  ldc.i4.0
0x69ff3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x69ff8  ldarg.0
0x69ff9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x69ffe  ldstr    aLocidMopDeprov// "LOCID_MOP_DEPROVISIONED_CONFIRM"
0x6a003  ldarg.0
0x6a004  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6a009  ldstr    aWebToolsMobile_1// "Web.Tools.MobileOfflineProvisioning.Con"...
0x6a00e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6a013  ldc.i4.0
0x6a014  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6a019  ldarg.0
0x6a01a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6a01f  ldstr    aLocidMopDisabl// "LOCID_MOP_DISABLE_ALERT_TITLE"
0x6a024  ldarg.0
0x6a025  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6a02a  ldstr    aWebToolsMobile_2// "Web.Tools.MobileOfflineProvisioning.Con"...
0x6a02f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6a034  ldc.i4.0
0x6a035  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6a03a  ldarg.0
0x6a03b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6a040  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x6a045  ldc.i4.1
0x6a046  ldnull
0x6a047  call     class [Microsoft.Crm]Microsoft.Crm.IMobileOfflineState [Microsoft.Crm]Microsoft.Crm.MobileOfflineUtility::Read(valuetype [mscorlib]System.Guid, bool, string)
0x6a04c  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.IMobileOfflineState::get_MobileOfflineStatus()
0x6a051  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_MobileOfflineStatus(int32 value)
0x6a056  ldarg.0
0x6a057  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6a05c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x6a061  call     bool [Microsoft.Crm]Microsoft.Crm.MobileOfflineUtility::IsOrgDedicated(valuetype [mscorlib]System.Guid)
0x6a066  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_OrgDedicated(bool value)
0x6a06b  ldarg.0
0x6a06c  call     instance bool Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::get_OrgDedicated()
0x6a071  brfalse.s loc_6A0EC
0x6a073  ldarg.0
0x6a074  call     instance int32 Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::get_MobileOfflineStatus()
0x6a079  ldc.i4.6
0x6a07a  beq.s    loc_6A085
0x6a07c  ldarg.0
0x6a07d  call     instance int32 Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::get_MobileOfflineStatus()
0x6a082  ldc.i4.2
0x6a083  bne.un.s loc_6A0A8
0x6a085  ldarg.0
0x6a086  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6a08b  ldstr    aLocidMopStatus// "LOCID_MOP_STATUS_INPROCESS"
0x6a090  ldarg.0
0x6a091  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6a096  ldstr    aWebToolsMobile_3// "Web.Tools.MobileOfflineProvisioning.Con"...
0x6a09b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6a0a0  ldc.i4.0
0x6a0a1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6a0a6  br.s     loc_6A0C9
0x6a0a8  ldarg.0
0x6a0a9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6a0ae  ldstr    aLocidMopStatus// "LOCID_MOP_STATUS_INPROCESS"
0x6a0b3  ldarg.0
0x6a0b4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6a0b9  ldstr    aWebToolsMobile_4// "Web.Tools.MobileOfflineProvisioning.Con"...
0x6a0be  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6a0c3  ldc.i4.0
0x6a0c4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6a0c9  ldarg.0
0x6a0ca  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6a0cf  ldstr    aLocidMopDisabl_0// "LOCID_MOP_DISABLE_ALERT_MSG"
0x6a0d4  ldarg.0
0x6a0d5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6a0da  ldstr    aWebToolsMobile_5// "Web.Tools.MobileOfflineProvisioning.Con"...
0x6a0df  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6a0e4  ldc.i4.0
0x6a0e5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6a0ea  br.s     loc_6A12E
0x6a0ec  ldarg.0
0x6a0ed  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6a0f2  ldstr    aLocidMopDisabl_0// "LOCID_MOP_DISABLE_ALERT_MSG"
0x6a0f7  ldarg.0
0x6a0f8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6a0fd  ldstr    aWebToolsMobile_6// "Web.Tools.MobileOfflineProvisioning.Con"...
0x6a102  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6a107  ldc.i4.0
0x6a108  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6a10d  ldarg.0
0x6a10e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6a113  ldstr    aLocidMopStatus// "LOCID_MOP_STATUS_INPROCESS"
0x6a118  ldarg.0
0x6a119  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6a11e  ldstr    aWebToolsMobile_3// "Web.Tools.MobileOfflineProvisioning.Con"...
0x6a123  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6a128  ldc.i4.0
0x6a129  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6a12e  ldarg.0
0x6a12f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6a134  ldstr    aToolsMobileoff_1// "/Tools/MobileOffline/cmds/cmd_update.as"...
0x6a139  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0x6a13e  ret
```
