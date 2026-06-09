# Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::ConfigureHeader

- ea: `0x90960`
- end: `0x90ebd`
- name: `Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::ConfigureHeader`
- size: `1373`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x90960`
- `0x92cf0`
- `0x96500`

## string_xrefs

- `0x9097c`: `/_common/styles/miniCal.css.aspx`
- `0x909ad`: `/Tools/SystemSettings/cmds/cmd_update.aspx`
- `0x90a35`: `LOCID_CALENDAR_UPDATE_FAILED`
- `0x90a40`: `Error_Calendar_DateFormatUpdate_Fail`
- `0x90afb`: `LOCID_INVALID_EMAIL_TEMPLATE`
- `0x90b06`: `SystemCustomization.SystemSettingsDialog.MarketingTab.UnsubscribeSection.Labels.TemplateNotSelected`

## pseudocode

```c

```

## disassembly

```asm
0x90960  ldarg.0
0x90961  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureHeader()
0x90966  ldarg.0
0x90967  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9096c  ldstr    aStaticControls// "/_static/_controls/datetime/date.js"
0x90971  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x90976  ldarg.0
0x90977  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9097c  ldstr    aCommonStylesMi// "/_common/styles/miniCal.css.aspx"
0x90981  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x90986  ldarg.0
0x90987  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9098c  ldstr    aStaticToolsSys_1// "/_static/tools/systemcustomization/scri"...
0x90991  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x90996  ldarg.0
0x90997  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9099c  ldstr    aBisattribute// "_bIsAttribute"
0x909a1  ldc.i4.0
0x909a2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x909a7  ldarg.0
0x909a8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x909ad  ldstr    aToolsSystemset// "/Tools/SystemSettings/cmds/cmd_update.a"...
0x909b2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0x909b7  ldarg.0
0x909b8  ldfld    bool Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::IsCRMOrganization
0x909bd  brfalse.s loc_90A2F
0x909bf  ldarg.0
0x909c0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x909c5  ldstr    aToolsFieldsele// "/_tools/fieldselect/fieldselect.css.asp"...
0x909ca  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x909cf  ldarg.0
0x909d0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x909d5  ldstr    aStaticToolsFor// "/_static/tools/formeditor/scripts/objec"...
0x909da  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x909df  ldarg.0
0x909e0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x909e5  ldstr    aStaticToolsFor_0// "/_static/tools/formeditor/scripts/field"...
0x909ea  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x909ef  ldarg.0
0x909f0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x909f5  ldstr    aStaticToolsFie// "/_static/_tools/fieldselect/fieldselect"...
0x909fa  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x909ff  ldarg.0
0x90a00  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90a05  ldstr    aStaticToolsVie_2// "/_static/tools/vieweditor/scripts/selec"...
0x90a0a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x90a0f  ldarg.0
0x90a10  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90a15  ldstr    aStaticToolsSol_4// "/_static/tools/Solution/Scripts/StatusR"...
0x90a1a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x90a1f  ldarg.0
0x90a20  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90a25  ldstr    aStaticToolsSys_0// "/_static/tools/systemcustomization/scri"...
0x90a2a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x90a2f  ldarg.0
0x90a30  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90a35  ldstr    aLocidCalendarU// "LOCID_CALENDAR_UPDATE_FAILED"
0x90a3a  ldarg.0
0x90a3b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x90a40  ldstr    aErrorCalendarD// "Error_Calendar_DateFormatUpdate_Fail"
0x90a45  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x90a4a  ldc.i4.0
0x90a4b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x90a50  ldarg.0
0x90a51  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90a56  ldstr    aLocidCurrencyR// "LOCID_CURRENCY_REQUIRED"
0x90a5b  ldarg.0
0x90a5c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x90a61  ldstr    aWebToolsSystem// "Web.Tools.SystemSettings.Dialogs.system"...
0x90a66  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x90a6b  ldc.i4.0
0x90a6c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x90a71  ldarg.0
0x90a72  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90a77  ldstr    aLocidTrackingi// "LOCID_TRACKINGID_REQUIRED"
0x90a7c  ldarg.0
0x90a7d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x90a82  ldstr    aWebToolsSystem_0// "Web.Tools.SystemSettings.Dialogs.system"...
0x90a87  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x90a8c  ldc.i4.0
0x90a8d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x90a92  ldarg.0
0x90a93  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90a98  ldstr    aLocidTrackingi_0// "LOCID_TRACKINGID_LENGTH_ERROR"
0x90a9d  ldarg.0
0x90a9e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x90aa3  ldstr    aWebToolsSystem_1// "Web.Tools.SystemSettings.Dialogs.system"...
0x90aa8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x90aad  ldc.i4.0
0x90aae  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x90ab3  ldarg.0
0x90ab4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90ab9  ldstr    aLocidInvalidTr// "LOCID_INVALID_TRACKING_PREFIX"
0x90abe  ldarg.0
0x90abf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x90ac4  ldstr    aWebToolsSystem_2// "Web.Tools.SystemSettings.Dialogs.system"...
0x90ac9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x90ace  ldc.i4.0
0x90acf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x90ad4  ldarg.0
0x90ad5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90ada  ldstr    aLocidInvalidSm// "LOCID_INVALID_SM_FILTER"
0x90adf  ldarg.0
0x90ae0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x90ae5  ldstr    aWebToolsSystem_3// "Web.Tools.SystemSettings.Dialogs.system"...
0x90aea  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x90aef  ldc.i4.0
0x90af0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x90af5  ldarg.0
0x90af6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90afb  ldstr    aLocidInvalidEm_0// "LOCID_INVALID_EMAIL_TEMPLATE"
0x90b00  ldarg.0
0x90b01  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x90b06  ldstr    aSystemcustomiz_108// "SystemCustomization.SystemSettingsDialo"...
0x90b0b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x90b10  ldc.i4.0
0x90b11  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x90b16  ldarg.0
0x90b17  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90b1c  ldstr    aLocidNameOrder// "LOCID_NAME_ORDER_CONFIRM"
0x90b21  ldarg.0
0x90b22  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x90b27  ldstr    aWebToolsSystem_4// "Web.Tools.SystemSettings.Dialogs.system"...
0x90b2c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x90b31  ldc.i4.0
0x90b32  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x90b37  ldarg.0
0x90b38  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90b3d  ldstr    aLocidIisResetR// "LOCID_IIS_RESET_REQUIRED"
0x90b42  ldarg.0
0x90b43  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x90b48  ldstr    aSystemcustomiz_109// "SystemCustomization.SystemSettingsDialo"...
0x90b4d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x90b52  ldc.i4.0
0x90b53  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x90b58  ldarg.0
0x90b59  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90b5e  ldstr    aLocidInvalidSc// "LOCID_INVALID_SCHEMA_NAME_PREFIX"
0x90b63  ldarg.0
0x90b64  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x90b69  ldstr    aSystemcustomiz_46// "SystemCustomization.SystemSettingsDialo"...
0x90b6e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x90b73  ldc.i4.0
0x90b74  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x90b79  ldarg.0
0x90b7a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90b7f  ldstr    aLocidOlksyncin// "LOCID_OLKSYNCINTERVAL_REQUIRED"
0x90b84  ldarg.0
0x90b85  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x90b8a  ldstr    aWebToolsSystem_5// "Web.Tools.SystemSettings.Dialogs.system"...
0x90b8f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x90b94  ldc.i4.0
0x90b95  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x90b9a  ldarg.0
0x90b9b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90ba0  ldstr    aLocidTagpollin// "LOCID_TAGPOLLINGPERIOD_REQUIRED"
0x90ba5  ldarg.0
0x90ba6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x90bab  ldstr    aWebToolsSystem_6// "Web.Tools.SystemSettings.Dialogs.system"...
0x90bb0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x90bb5  ldc.i4.0
0x90bb6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x90bbb  ldarg.0
0x90bbc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90bc1  ldstr    aLocidSelvalsTi// "LOCID_SELVALS_TITLE_AVAILVALS"
0x90bc6  ldarg.0
0x90bc7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x90bcc  ldstr    aWebToolsViewed_0// "Web.Tools.ViewEditor.Dialogs.SelectValu"...
0x90bd1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x90bd6  ldc.i4.0
0x90bd7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x90bdc  ldarg.0
0x90bdd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90be2  ldstr    aLocidSelvalsTi_0// "LOCID_SELVALS_TITLE_SELTDVALS"
0x90be7  ldarg.0
0x90be8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x90bed  ldstr    aWebToolsViewed_1// "Web.Tools.ViewEditor.Dialogs.SelectValu"...
0x90bf2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x90bf7  ldc.i4.0
0x90bf8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x90bfd  ldarg.0
0x90bfe  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90c03  ldstr    aLocidSyscustCa// "LOCID_SYSCUST_CANTBEBLANK"
0x90c08  ldarg.0
0x90c09  ldstr    aValidationErro// "Validation.Errors.CannotBeBlank"
0x90c0e  call     instance string Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::GetSCString(string name)
0x90c13  ldc.i4.0
0x90c14  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x90c19  ldarg.0
0x90c1a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90c1f  ldstr    aLocidSyscustIn// "LOCID_SYSCUST_INVALCHARS"
0x90c24  ldarg.0
0x90c25  ldstr    aValidationErro_0// "Validation.Errors.CannotHaveInvalidChar"...
0x90c2a  call     instance string Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::GetSCString(string name)
0x90c2f  ldc.i4.0
0x90c30  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x90c35  ldarg.0
0x90c36  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90c3b  ldstr    aLocidSyscustAl// "LOCID_SYSCUST_ALPHANUMSONLY"
0x90c40  ldarg.0
0x90c41  ldstr    aValidationErro_1// "Validation.Errors.CanOnlyHaveAlphaNumer"...
0x90c46  call     instance string Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::GetSCString(string name)
0x90c4b  ldc.i4.0
0x90c4c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x90c51  ldarg.0
0x90c52  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90c57  ldstr    aLocidConfirmAu// "LOCID_CONFIRM_AUDIT_DISABLE"
0x90c5c  ldarg.0
0x90c5d  ldstr    aSystemsettings_9// "SystemSettingsDialog.AuditTab.MainSecti"...
0x90c62  call     instance string Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::GetSCString(string name)
0x90c67  ldc.i4.0
0x90c68  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x90c6d  ldarg.0
0x90c6e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90c73  ldstr    aLocidCheckCoun// "LOCID_CHECK_COUNTRY_CODE_VALUE"
0x90c78  ldarg.0
0x90c79  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x90c7e  ldstr    aDefaultcountry// "DefaultCountryCode_Error"
0x90c83  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x90c88  ldc.i4.0
0x90c89  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x90c8e  ldarg.0
0x90c8f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90c94  ldstr    aLocidInvalidDe// "LOCID_INVALID_DEFAULT_APP_NAME"
0x90c99  ldarg.0
0x90c9a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x90c9f  ldstr    aDefaultappname// "DefaultAppName_Error"
0x90ca4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x90ca9  ldc.i4.0
0x90caa  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x90caf  ldarg.0
0x90cb0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90cb5  ldstr    aLocidSessionti// "LOCID_SESSIONTIMEOUT_REQUIRED"
0x90cba  ldarg.0
0x90cbb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x90cc0  ldstr    aSystemcustomiz_110// "SystemCustomization.SystemSettingsDialo"...
0x90cc5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x90cca  ldc.i4.0
0x90ccb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x90cd0  ldarg.0
0x90cd1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90cd6  ldstr    aLocidSessionti_0// "LOCID_SESSIONTIMEOUT_REMINDER"
0x90cdb  ldarg.0
0x90cdc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x90ce1  ldstr    aSystemcustomiz_111// "SystemCustomization.SystemSettingsDialo"...
0x90ce6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x90ceb  ldc.i4.0
0x90cec  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x90cf1  ldarg.0
0x90cf2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90cf7  ldstr    aLocidSessionti_1// "LOCID_SESSIONTIMEOUT_VALIDATION"
0x90cfc  ldarg.0
0x90cfd  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x90d02  ldstr    aSystemcustomiz_112// "SystemCustomization.SystemSettingsDialo"...
0x90d07  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x90d0c  ldc.i4.0
0x90d0d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x90d12  ldarg.0
0x90d13  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90d18  ldstr    aEmailRouterWar// "EMAIL_ROUTER_WARNING_MESSAGE"
0x90d1d  ldarg.0
0x90d1e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x90d23  ldstr    aSystemsettings_10// "SystemSettings.ProcessEmailsUsing.Email"...
0x90d28  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x90d2d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x90d32  ldarg.0
0x90d33  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90d38  ldstr    aEmailRouterWar_0// "EMAIL_ROUTER_WARNING_TITLE"
0x90d3d  ldarg.0
0x90d3e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x90d43  ldstr    aSystemsettings_11// "SystemSettings.ProcessEmailsUsing.Email"...
0x90d48  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x90d4d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x90d52  ldarg.0
0x90d53  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90d58  ldstr    aHasPasswordFor// "HAS_PASSWORD_FOR_A_MAILBOX"
0x90d5d  ldarg.0
0x90d5e  call     instance bool Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::HasPasswordForMailboxes()
0x90d63  brtrue.s loc_90D6C
0x90d65  ldstr    a0_1// "0"
0x90d6a  br.s     loc_90D71
0x90d6c  ldstr    a1// "1"
0x90d71  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x90d76  ldarg.0
0x90d77  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90d7c  ldstr    aLocidMicrosoft_0// "LOCID_MICROSOFTFLOW_PICKLISTDISABLED_TE"...
0x90d81  ldarg.0
0x90d82  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x90d87  ldstr    aSystemcustomiz_113// "SystemCustomization.SystemSettingsDialo"...
0x90d8c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x90d91  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x90d96  ldarg.0
0x90d97  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x90d9c  ldstr    aLocidMicrosoft_1// "LOCID_MICROSOFTFLOW_LOGINDISABLED_TEXT"
0x90da1  ldarg.0
0x90da2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x90da7  ldstr    aSystemcustomiz_114// "SystemCustomization.SystemSettingsDialo"...
0x90dac  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x90db1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x90db6  ldarg.0
  ... truncated ...
```
