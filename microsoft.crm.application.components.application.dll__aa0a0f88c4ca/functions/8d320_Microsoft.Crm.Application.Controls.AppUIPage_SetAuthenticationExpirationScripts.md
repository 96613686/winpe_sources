# Microsoft.Crm.Application.Controls.AppUIPage::SetAuthenticationExpirationScripts

- ea: `0x8d320`
- end: `0x8d46b`
- name: `Microsoft.Crm.Application.Controls.AppUIPage::SetAuthenticationExpirationScripts`
- size: `331`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x8d5c0`
- `0x8e1a0`

## callees

- `0x8d1e0`
- `0x8d320`

## string_xrefs

- `0x8d343`: `/_static/_common/styles/sessionmanagement.css`
- `0x8d372`: `AUTH_EXPIRATION_LAST_UPDATE`
- `0x8d445`: `/_static/_common/scripts/MaxSessionMonitor.js`

## pseudocode

```c

```

## disassembly

```asm
0x8d320  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.AuthenticationExpirationInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::RetrieveAuthExpirationInfo()
0x8d325  stloc.0
0x8d326  ldarg.1
0x8d327  ldstr    aRemindAuthExpi// "REMIND_AUTH_EXPIRATION"
0x8d32c  ldloc.0
0x8d32d  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.AuthenticationExpirationInfo::get_IsAuthExpirationEnabled()
0x8d332  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x8d337  ldloc.0
0x8d338  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.AuthenticationExpirationInfo::get_IsAuthExpirationEnabled()
0x8d33d  brfalse  loc_8D450
0x8d342  ldarg.1
0x8d343  ldstr    aStaticCommonSt_0// "/_static/_common/styles/sessionmanageme"...
0x8d348  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x8d34d  ldarg.1
0x8d34e  ldstr    aAuthExpiration// "AUTH_EXPIRATION_REMINDER_TIME_IN_SECOND"...
0x8d353  ldloc.0
0x8d354  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.AuthenticationExpirationInfo::get_ReminderTimeInSeconds()
0x8d359  conv.i8
0x8d35a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x8d35f  ldarg.1
0x8d360  ldstr    aAuthExpiration_0// "AUTH_EXPIRATION_AFTER_REMINDER_IN_SECON"...
0x8d365  ldloc.0
0x8d366  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.AuthenticationExpirationInfo::get_ExpirationTimeAfterReminderInSeconds()
0x8d36b  conv.i8
0x8d36c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x8d371  ldarg.1
0x8d372  ldstr    aAuthExpiration_1// "AUTH_EXPIRATION_LAST_UPDATE"
0x8d377  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x8d37c  stloc.2
0x8d37d  ldloca.s 2
0x8d37f  ldstr    aYyyymmddhhmmss// "yyyyMMddHHmmss"
0x8d384  call     instance string [mscorlib]System.DateTime::ToString(string)
0x8d389  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x8d38e  ldarg.0
0x8d38f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8d394  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsLive()
0x8d399  brtrue.s loc_8D3A2
0x8d39b  ldstr    aBrandCrm// "Brand_CRM"
0x8d3a0  br.s     loc_8D3A7
0x8d3a2  ldstr    aBrandCrmOnline// "Brand_CRM_Online"
0x8d3a7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8d3ac  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8d3b1  stloc.1
0x8d3b2  ldarg.1
0x8d3b3  ldstr    aDialogReauthDe// "DIALOG_REAUTH_DESCRIPTION"
0x8d3b8  ldarg.0
0x8d3b9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8d3be  ldstr    aDialogReauthen// "Dialog_Reauthenticate_Dialog_Descriptio"...
0x8d3c3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8d3c8  ldc.i4.1
0x8d3c9  newarr   [mscorlib]System.Object
0x8d3ce  dup
0x8d3cf  ldc.i4.0
0x8d3d0  ldloc.1
0x8d3d1  stelem.ref
0x8d3d2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, object[])
0x8d3d7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x8d3dc  ldarg.1
0x8d3dd  ldstr    aDialogReauthEx// "DIALOG_REAUTH_EXPIRED_DESCRIPTION"
0x8d3e2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8d3e7  ldstr    aDialogReauthen_0// "Dialog_Reauthenticate_Dialog_Expired_De"...
0x8d3ec  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8d3f1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x8d3f6  ldarg.1
0x8d3f7  ldstr    aDialogReauthSi// "DIALOG_REAUTH_SIGNIN_BUTTON"
0x8d3fc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8d401  ldstr    aDialogReauthen_1// "Dialog_Reauthenticate_Signin_Button"
0x8d406  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8d40b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x8d410  ldarg.1
0x8d411  ldstr    aDialogReauthCa// "DIALOG_REAUTH_CANCEL_BUTTON"
0x8d416  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8d41b  ldstr    aDialogReauthen_2// "Dialog_Reauthenticate_Cancel_Button"
0x8d420  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8d425  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x8d42a  ldarg.1
0x8d42b  ldstr    aDialogReauthCl// "DIALOG_REAUTH_CLOSE_BUTTON"
0x8d430  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8d435  ldstr    aDialogReauthen_3// "Dialog_Reauthenticate_Close_Button"
0x8d43a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8d43f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x8d444  ldarg.1
0x8d445  ldstr    aStaticCommonSc_16// "/_static/_common/scripts/MaxSessionMoni"...
0x8d44a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x8d44f  ret
0x8d450  ldarg.1
0x8d451  ldstr    aAuthExpiration// "AUTH_EXPIRATION_REMINDER_TIME_IN_SECOND"...
0x8d456  ldc.i4.0
0x8d457  conv.i8
0x8d458  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x8d45d  ldarg.1
0x8d45e  ldstr    aAuthExpiration_0// "AUTH_EXPIRATION_AFTER_REMINDER_IN_SECON"...
0x8d463  ldc.i4.0
0x8d464  conv.i8
0x8d465  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x8d46a  ret
```
