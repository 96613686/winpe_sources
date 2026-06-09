# Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::WriteSessionManagementScripts

- ea: `0x1a8e0`
- end: `0x1ab06`
- name: `Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::WriteSessionManagementScripts`
- size: `550`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1a700`

## callees

- `0x19f10`
- `0x19f20`
- `0x19f40`
- `0x1a860`
- `0x1a8a0`
- `0x1a8e0`

## string_xrefs

- `0x1a903`: `/_static/_common/styles/sessionmanagement.css`
- `0x1a974`: `AUTH_EXPIRATION_LAST_UPDATE`
- `0x1aa35`: `/_static/_common/scripts/MaxSessionMonitor.js`
- `0x1aafb`: `/_static/_common/scripts/InactivityTimeoutMonitor.js`

## pseudocode

```c

```

## disassembly

```asm
0x1a8e0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1a8e5  stloc.0
0x1a8e6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.AuthenticationExpirationInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::RetrieveAuthExpirationInfo()
0x1a8eb  stloc.1
0x1a8ec  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.InactivityTimeoutInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::RetrieveInactivityTimeoutInfo()
0x1a8f1  stloc.2
0x1a8f2  ldloc.1
0x1a8f3  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.AuthenticationExpirationInfo::get_IsAuthExpirationEnabled()
0x1a8f8  brtrue.s loc_1A902
0x1a8fa  ldloc.2
0x1a8fb  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.InactivityTimeoutInfo::get_IsInactivityTimeoutEnabled()
0x1a900  brfalse.s loc_1A90D
0x1a902  ldarg.1
0x1a903  ldstr    aStaticCommonSt_0// "/_static/_common/styles/sessionmanageme"...
0x1a908  call     void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::WriteStyleReference(class [mscorlib]System.IO.TextWriter output, string stylePath)
0x1a90d  ldarg.0
0x1a90e  ldloc.0
0x1a90f  ldstr    aRemindAuthExpi// "REMIND_AUTH_EXPIRATION"
0x1a914  ldloc.1
0x1a915  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.AuthenticationExpirationInfo::get_IsAuthExpirationEnabled()
0x1a91a  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, bool varValue)
0x1a91f  ldloc.1
0x1a920  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.AuthenticationExpirationInfo::get_IsAuthExpirationEnabled()
0x1a925  brfalse  loc_1AA41
0x1a92a  ldarg.0
0x1a92b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1a930  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsLive()
0x1a935  brtrue.s loc_1A93E
0x1a937  ldstr    aBrandCrm// "Brand_CRM"
0x1a93c  br.s     loc_1A943
0x1a93e  ldstr    aBrandCrmOnline// "Brand_CRM_Online"
0x1a943  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a948  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a94d  stloc.3
0x1a94e  ldarg.0
0x1a94f  ldloc.0
0x1a950  ldstr    aAuthExpiration// "AUTH_EXPIRATION_REMINDER_TIME_IN_SECOND"...
0x1a955  ldloc.1
0x1a956  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.AuthenticationExpirationInfo::get_ReminderTimeInSeconds()
0x1a95b  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, int32 varValue)
0x1a960  ldarg.0
0x1a961  ldloc.0
0x1a962  ldstr    aAuthExpiration_0// "AUTH_EXPIRATION_AFTER_REMINDER_IN_SECON"...
0x1a967  ldloc.1
0x1a968  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.AuthenticationExpirationInfo::get_ExpirationTimeAfterReminderInSeconds()
0x1a96d  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, int32 varValue)
0x1a972  ldarg.0
0x1a973  ldloc.0
0x1a974  ldstr    aAuthExpiration_1// "AUTH_EXPIRATION_LAST_UPDATE"
0x1a979  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1a97e  stloc.s  4
0x1a980  ldloca.s 4
0x1a982  ldstr    aYyyymmddhhmmss// "yyyyMMddHHmmss"
0x1a987  call     instance string [mscorlib]System.DateTime::ToString(string)
0x1a98c  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a991  ldarg.0
0x1a992  ldloc.0
0x1a993  ldstr    aDialogReauthDe// "DIALOG_REAUTH_DESCRIPTION"
0x1a998  ldarg.0
0x1a999  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1a99e  ldstr    aDialogReauthen// "Dialog_Reauthenticate_Dialog_Descriptio"...
0x1a9a3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a9a8  ldc.i4.1
0x1a9a9  newarr   [mscorlib]System.Object
0x1a9ae  dup
0x1a9af  ldc.i4.0
0x1a9b0  ldloc.3
0x1a9b1  stelem.ref
0x1a9b2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, object[])
0x1a9b7  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a9bc  ldarg.0
0x1a9bd  ldloc.0
0x1a9be  ldstr    aDialogReauthEx// "DIALOG_REAUTH_EXPIRED_DESCRIPTION"
0x1a9c3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1a9c8  ldstr    aDialogReauthen_0// "Dialog_Reauthenticate_Dialog_Expired_De"...
0x1a9cd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1a9d2  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a9d7  ldarg.0
0x1a9d8  ldloc.0
0x1a9d9  ldstr    aDialogReauthSi// "DIALOG_REAUTH_SIGNIN_BUTTON"
0x1a9de  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1a9e3  ldstr    aDialogReauthen_1// "Dialog_Reauthenticate_Signin_Button"
0x1a9e8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1a9ed  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a9f2  ldarg.0
0x1a9f3  ldloc.0
0x1a9f4  ldstr    aDialogReauthCa// "DIALOG_REAUTH_CANCEL_BUTTON"
0x1a9f9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1a9fe  ldstr    aDialogReauthen_2// "Dialog_Reauthenticate_Cancel_Button"
0x1aa03  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1aa08  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1aa0d  ldarg.0
0x1aa0e  ldloc.0
0x1aa0f  ldstr    aDialogReauthCl// "DIALOG_REAUTH_CLOSE_BUTTON"
0x1aa14  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1aa19  ldstr    aDialogReauthen_3// "Dialog_Reauthenticate_Close_Button"
0x1aa1e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1aa23  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1aa28  ldarg.1
0x1aa29  ldloc.0
0x1aa2a  callvirt instance string [mscorlib]System.Object::ToString()
0x1aa2f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1aa34  ldarg.1
0x1aa35  ldstr    aStaticCommonSc_16// "/_static/_common/scripts/MaxSessionMoni"...
0x1aa3a  call     void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::WriteScriptReference(class [mscorlib]System.IO.TextWriter output, string scriptPath)
0x1aa3f  br.s     loc_1AA67
0x1aa41  ldarg.0
0x1aa42  ldloc.0
0x1aa43  ldstr    aAuthExpiration// "AUTH_EXPIRATION_REMINDER_TIME_IN_SECOND"...
0x1aa48  ldc.i4.0
0x1aa49  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, int32 varValue)
0x1aa4e  ldarg.0
0x1aa4f  ldloc.0
0x1aa50  ldstr    aAuthExpiration_0// "AUTH_EXPIRATION_AFTER_REMINDER_IN_SECON"...
0x1aa55  ldc.i4.0
0x1aa56  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, int32 varValue)
0x1aa5b  ldarg.1
0x1aa5c  ldloc.0
0x1aa5d  callvirt instance string [mscorlib]System.Object::ToString()
0x1aa62  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1aa67  ldloc.2
0x1aa68  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.InactivityTimeoutInfo::get_IsInactivityTimeoutEnabled()
0x1aa6d  brfalse  loc_1AB05
0x1aa72  ldloc.0
0x1aa73  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Clear()
0x1aa78  pop
0x1aa79  ldarg.0
0x1aa7a  ldloc.0
0x1aa7b  ldstr    aInactivityShow// "INACTIVITY_SHOW_WARNING_IN_SECONDS"
0x1aa80  ldloc.2
0x1aa81  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.InactivityTimeoutInfo::get_ShowWarningAfterInactivityInSeconds()
0x1aa86  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, int32 varValue)
0x1aa8b  ldarg.0
0x1aa8c  ldloc.0
0x1aa8d  ldstr    aInactivitySign// "INACTIVITY_SIGNOUT_IN_SECONDS"
0x1aa92  ldloc.2
0x1aa93  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.InactivityTimeoutInfo::get_SignoutAfterInactivityInSeconds()
0x1aa98  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, int32 varValue)
0x1aa9d  ldarg.0
0x1aa9e  ldloc.0
0x1aa9f  ldstr    aInactivityDial// "INACTIVITY_DIALOG_WARNING_DESCRIPTION"
0x1aaa4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1aaa9  ldstr    aInactivityDial_0// "Inactivity_Dialog_Warning_Description"
0x1aaae  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1aab3  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1aab8  ldarg.0
0x1aab9  ldloc.0
0x1aaba  ldstr    aInactivityDial_1// "INACTIVITY_DIALOG_ERROR_DESCRIPTION"
0x1aabf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1aac4  ldstr    aInactivityDial_2// "Inactivity_Dialog_Error_Description"
0x1aac9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1aace  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1aad3  ldarg.0
0x1aad4  ldloc.0
0x1aad5  ldstr    aInactivityDial_3// "INACTIVITY_DIALOG_CONTINUE_BUTTON"
0x1aada  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1aadf  ldstr    aInactivityDial_4// "Inactivity_Dialog_Continue_Button"
0x1aae4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1aae9  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1aaee  ldarg.1
0x1aaef  ldloc.0
0x1aaf0  callvirt instance string [mscorlib]System.Object::ToString()
0x1aaf5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1aafa  ldarg.1
0x1aafb  ldstr    aStaticCommonSc_17// "/_static/_common/scripts/InactivityTime"...
0x1ab00  call     void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::WriteScriptReference(class [mscorlib]System.IO.TextWriter output, string scriptPath)
0x1ab05  ret
```
