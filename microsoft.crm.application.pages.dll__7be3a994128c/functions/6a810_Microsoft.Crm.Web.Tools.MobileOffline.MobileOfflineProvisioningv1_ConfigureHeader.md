# Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioningv1::ConfigureHeader

- ea: `0x6a810`
- end: `0x6aa3b`
- name: `Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioningv1::ConfigureHeader`
- size: `555`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x6a680`
- `0x6a690`
- `0x6a810`

## string_xrefs

- `0x6a868`: `Web.Tools.MobileOfflineProvisioning.Config.DisableWarningTitle`
- `0x6a9f7`: `Web.Tools.MobileOfflineProvisioning.Config.DisableDedicatedWarningMessage`
- `0x6aa1a`: `Web.Tools.MobileOfflineProvisioning.Config.DisableWarningMessage`
- `0x6aa30`: `/Tools/MobileOffline/cmds/cmd_update.aspx`
- `0x6a889`: `Web.Tools.MobileOfflineProvisioning.Config.StopProvisioningWarningMessage`
- `0x6a8aa`: `Web.Tools.MobileOfflineProvisioning.Config.StopProvisioningWarningMessageTitle`
- `0x6a8c0`: `LOCID_MOP_TOTAL_PER_COMP_MSG`
- `0x6a8cb`: `Web.Tools.MobileOfflineProvisioning.DataSync.TotalPercentageCompleted.Message`
- `0x6a92e`: `Web.Tools.MobileOfflineProvisioning.User.Message.After.Provisioning.Complete`
- `0x6a94f`: `Web.Tools.MobileOfflineProvisioning.Tab.EntityStatus.After.Provisioning.Complete`
- `0x6a970`: `Web.Tools.MobileOfflineProvisioning.Config.ProvisioningFailed.MetadataFailed`
- `0x6a991`: `Web.Tools.MobileOfflineProvisioning.Config.ProvisioningFailed.EntityDownloadFailed`
- `0x6a9b2`: `Web.Tools.MobileOfflineProvisioning.Config.ProvisioningFailed.UnknownFailure`

## pseudocode

```c

```

## disassembly

```asm
0x6a810  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6a815  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MobileOfflineEligibilityChecker::IsOrgEligibleForMobileOffline(class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x6a81a  pop
0x6a81b  ldarg.0
0x6a81c  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::ConfigureHeader()
0x6a821  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::.ctor()
0x6a826  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x6a82b  ldarg.0
0x6a82c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6a831  ldc.i4.1
0x6a832  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0x6a837  ldarg.0
0x6a838  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6a83d  ldstr    aToolsMobileoff_0// "/tools/MobileOffline/MobileOfflineStyle"...
0x6a842  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x6a847  ldarg.0
0x6a848  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6a84d  ldstr    aStaticToolsMob// "/_static/tools/mobileoffline/scripts/mo"...
0x6a852  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x6a857  ldarg.0
0x6a858  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6a85d  ldstr    aLocidMopDisabl// "LOCID_MOP_DISABLE_ALERT_TITLE"
0x6a862  ldarg.0
0x6a863  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6a868  ldstr    aWebToolsMobile_2// "Web.Tools.MobileOfflineProvisioning.Con"...
0x6a86d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6a872  ldc.i4.0
0x6a873  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6a878  ldarg.0
0x6a879  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6a87e  ldstr    aLocidMopStopPr// "LOCID_MOP_STOP_PROVI_ALERT_MSG"
0x6a883  ldarg.0
0x6a884  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6a889  ldstr    aWebToolsMobile_14// "Web.Tools.MobileOfflineProvisioning.Con"...
0x6a88e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6a893  ldc.i4.0
0x6a894  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6a899  ldarg.0
0x6a89a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6a89f  ldstr    aLocidMopStopPr_0// "LOCID_MOP_STOP_PROVI_ALERT_TITLE"
0x6a8a4  ldarg.0
0x6a8a5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6a8aa  ldstr    aWebToolsMobile_15// "Web.Tools.MobileOfflineProvisioning.Con"...
0x6a8af  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6a8b4  ldc.i4.0
0x6a8b5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6a8ba  ldarg.0
0x6a8bb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6a8c0  ldstr    aLocidMopTotalP// "LOCID_MOP_TOTAL_PER_COMP_MSG"
0x6a8c5  ldarg.0
0x6a8c6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6a8cb  ldstr    aWebToolsMobile_16// "Web.Tools.MobileOfflineProvisioning.Dat"...
0x6a8d0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6a8d5  ldc.i4.0
0x6a8d6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6a8db  ldarg.0
0x6a8dc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6a8e1  ldstr    aLocidMopRemTim// "LOCID_MOP_REM_TIME_LEFT_MSG"
0x6a8e6  ldarg.0
0x6a8e7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6a8ec  ldstr    aWebToolsMobile_17// "Web.Tools.MobileOfflineProvisioning.Dat"...
0x6a8f1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6a8f6  ldc.i4.0
0x6a8f7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6a8fc  ldarg.0
0x6a8fd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6a902  ldstr    aLocidMopRemTim_0// "LOCID_MOP_REM_TIME_CALC_MSG"
0x6a907  ldarg.0
0x6a908  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6a90d  ldstr    aWebToolsMobile_18// "Web.Tools.MobileOfflineProvisioning.Gri"...
0x6a912  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6a917  ldc.i4.0
0x6a918  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6a91d  ldarg.0
0x6a91e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6a923  ldstr    aLocidMopUserMe// "LOCID_MOP_USER_MESSAGE_TEXT"
0x6a928  ldarg.0
0x6a929  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6a92e  ldstr    aWebToolsMobile_19// "Web.Tools.MobileOfflineProvisioning.Use"...
0x6a933  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6a938  ldc.i4.0
0x6a939  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6a93e  ldarg.0
0x6a93f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6a944  ldstr    aLocidMopTabEnt// "LOCID_MOP_TAB_ENT_STATUS_TEXT"
0x6a949  ldarg.0
0x6a94a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6a94f  ldstr    aWebToolsMobile_20// "Web.Tools.MobileOfflineProvisioning.Tab"...
0x6a954  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6a959  ldc.i4.0
0x6a95a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6a95f  ldarg.0
0x6a960  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6a965  ldstr    aLocidErrorMeta// "LOCID_ERROR_METADATAFAILED"
0x6a96a  ldarg.0
0x6a96b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6a970  ldstr    aWebToolsMobile_21// "Web.Tools.MobileOfflineProvisioning.Con"...
0x6a975  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6a97a  ldc.i4.0
0x6a97b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6a980  ldarg.0
0x6a981  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6a986  ldstr    aLocidErrorEnti// "LOCID_ERROR_ENTITYDOWNLOADFAILED"
0x6a98b  ldarg.0
0x6a98c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6a991  ldstr    aWebToolsMobile_22// "Web.Tools.MobileOfflineProvisioning.Con"...
0x6a996  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6a99b  ldc.i4.0
0x6a99c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6a9a1  ldarg.0
0x6a9a2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6a9a7  ldstr    aLocidErrorUnkn// "LOCID_ERROR_UNKNOWNFAILURE"
0x6a9ac  ldarg.0
0x6a9ad  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6a9b2  ldstr    aWebToolsMobile_23// "Web.Tools.MobileOfflineProvisioning.Con"...
0x6a9b7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6a9bc  ldc.i4.0
0x6a9bd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6a9c2  ldarg.0
0x6a9c3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6a9c8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x6a9cd  ldc.i4.0
0x6a9ce  ldnull
0x6a9cf  call     class [Microsoft.Crm]Microsoft.Crm.IMobileOfflineState [Microsoft.Crm]Microsoft.Crm.MobileOfflineUtility::Read(valuetype [mscorlib]System.Guid, bool, string)
0x6a9d4  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.IMobileOfflineState::get_MobileOfflineStatus()
0x6a9d9  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioningv1::set_MobileOfflineStatus(int32 value)
0x6a9de  ldarg.0
0x6a9df  call     instance bool Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioningv1::get_OrgDedicated()
0x6a9e4  brfalse.s loc_6AA09
0x6a9e6  ldarg.0
0x6a9e7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6a9ec  ldstr    aLocidMopDisabl_0// "LOCID_MOP_DISABLE_ALERT_MSG"
0x6a9f1  ldarg.0
0x6a9f2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6a9f7  ldstr    aWebToolsMobile_5// "Web.Tools.MobileOfflineProvisioning.Con"...
0x6a9fc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6aa01  ldc.i4.0
0x6aa02  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6aa07  br.s     loc_6AA2A
0x6aa09  ldarg.0
0x6aa0a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6aa0f  ldstr    aLocidMopDisabl_0// "LOCID_MOP_DISABLE_ALERT_MSG"
0x6aa14  ldarg.0
0x6aa15  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6aa1a  ldstr    aWebToolsMobile_6// "Web.Tools.MobileOfflineProvisioning.Con"...
0x6aa1f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6aa24  ldc.i4.0
0x6aa25  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6aa2a  ldarg.0
0x6aa2b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6aa30  ldstr    aToolsMobileoff_1// "/Tools/MobileOffline/cmds/cmd_update.as"...
0x6aa35  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0x6aa3a  ret
```
