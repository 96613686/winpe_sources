# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailEngagementActionsControl::Render

- ea: `0x15af0`
- end: `0x1675e`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailEngagementActionsControl::Render`
- size: `3182`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x15a90`
- `0x15ab0`
- `0x15af0`
- `0x16760`

## string_xrefs

- `0x15c3f`: `<div id="activityLink" class="activityLink">`
- `0x15d48`: `<div id="activityLink" class="activityLink">`
- `0x15f69`: `<div id="activityLink" class="activityLink">`
- `0x16139`: `<div id="activityLink" class="activityLink">`
- `0x16216`: `<div id="activityLink" class="activityLink">`
- `0x16318`: `<div id="activityLink" class="activityLink">`
- `0x164e8`: `<div id="activityLink" class="activityLink">`
- `0x165ea`: `<div id="activityLink" class="activityLink">`
- `0x166ec`: `<div id="activityLink" class="activityLink">`
- `0x15c4a`: `<a class="emailActivityLink" tabindex="{1}" href="#" id="email_followed_link" aria-label="{0}" title="{0}"></a>`
- `0x15c54`: `Email_Engagement_Follow_Section_Link_Follow_Links_ON`
- `0x15da7`: `Email_Engagement_Follow_Section_Link_Follow_Links_ON`
- `0x15cb0`: `Email_Engagement_Follow_Section_Link_Follow_Icon_Warning`
- `0x15cd5`: `Email_Engagement_Follow_Section_Link_Follow_Icon_Warning`
- `0x15e03`: `Email_Engagement_Follow_Section_Link_Follow_Icon_Warning`
- `0x15e28`: `Email_Engagement_Follow_Section_Link_Follow_Icon_Warning`
- `0x15d53`: `<a class="emailActivityLink" tabindex="{1}" href="#" id="email_cannot_be_followed_link" aria-label="{0}" title="{0}"></a>`
- `0x15d5d`: `Email_Engagement_Follow_Section_Link_Follow_Links_Warning_Preferences`
- `0x15d78`: `<a class="emailActivityLink" tabindex="{1}" href="#" id="email_retry_follow_link" aria-label="{0}" title="{0}"></a>`
- `0x15d82`: `Email_Engagement_Follow_Section_Link_Follow_Links_Warning_Retry`
- `0x15d9d`: `<a class="emailActivityLink" tabindex="{1}" href="#" id="email_donot_follow_link" aria-label="{0}" title="{0}"></a>`
- `0x15f74`: `<a class="emailActivityLink" tabindex="{1}" href="#" id="email_not_followed_link" aria-label="{0}" title="{0}"></a>`
- `0x15f7e`: `Email_Engagement_Follow_Section_Link_Follow_Links_OFF`
- `0x1605c`: `<div class="activityLink">`
- `0x1640b`: `<div class="activityLink">`
- `0x16067`: `<a class="emailActivityLink" tabindex="{1}" href="#" id="delaySendNotSet_link" aria-label="{0}" title="{0}"></a>`
- `0x16071`: `Email_Engagement_Actions_Link_Delay_Mail`
- `0x16144`: `<a class="emailActivityLink" tabindex="{1}" href="#" id="delaySendNotSet_hassuggestion_link" aria-label="{0}" title="{0}"></a>`
- `0x1614e`: `Email_Engagement_Actions_Link_Delay_Mail_Title`
- `0x16221`: `<a class="emailActivityLink" tabindex="{1}" href="#" id="delaySendSet_link" aria-label="{0}" title="{0}"></a>`
- `0x1622b`: `Email_Engagement_Delay_Send_Section_Delay_Send_Link_SetState_Change`
- `0x16246`: `<a class="emailActivityLink" tabindex="{1}" href="#" id="resetDelaySend_link" aria-label="{0}" title="{0}"></a>`
- `0x16250`: `Email_Engagement_Actions_Link_Remove_Delay`
- `0x16323`: `<a class="emailActivityLink emailLink-disabled" tabindex="{1}" href="#" id="emailSent_link" aria-label="{0}" title="{0}"></a>`
- `0x16416`: `<a class="emailActivityLink" tabindex="{1}" href="#" id="reminderNotSet_link" aria-label="{0}" title="{0}"></a>`
- `0x16420`: `Email_Engagement_Reminder_Section_Reminder_Link_UnSetState`
- `0x16701`: `Email_Engagement_Reminder_Section_Reminder_Link_UnSetState`
- `0x164f3`: `<a class="emailActivityLink" tabindex="{1}" href="#" id="reminderSet_link" aria-label="{0}" title="{0}"></a>`
- `0x164fd`: `Email_Engagement_Reminder_Section_Reminder_Link_SetState_Change`
- `0x165ff`: `Email_Engagement_Reminder_Section_Reminder_Link_SetState_Change`
- `0x16518`: `<a class="emailActivityLink" tabindex="{1}" href="#" id="reminderRemove_link" aria-label="{0}" title="{0}"></a>`
- `0x16522`: `Email_Engagement_Reminder_Section_Reminder_Link_SetState_Remove`
- `0x16624`: `Email_Engagement_Reminder_Section_Reminder_Link_SetState_Remove`
- `0x165f5`: `<a class="emailActivityLink" tabindex="{1}" href="#" id="reminderHasWarning_change_link" aria-label="{0}" title="{0}"></a>`
- `0x1661a`: `<a class="emailActivityLink" tabindex="{1}" href="#" id="reminderHasWarning_remove_link" aria-label="{0}" title="{0}"></a>`
- `0x166f7`: `<a class="emailActivityLink" tabindex="{1}" href="#" id="reminderMet_link" aria-label="{0}" title="{0}"></a>`

## pseudocode

```c

```

## disassembly

```asm
0x15af0  ldarg.0
0x15af1  call     instance void [System.Web]System.Web.UI.Control::EnsureChildControls()
0x15af6  ldc.i4.0
0x15af7  stloc.0
0x15af8  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0x15afd  brfalse.s loc_15B08
0x15aff  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x15b04  brtrue.s loc_15B08
0x15b06  ldc.i4.1
0x15b07  stloc.0
0x15b08  ldarg.1
0x15b09  ldstr    aDivId0// "<div id=\"{0}\">"
0x15b0e  ldarg.0
0x15b0f  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x15b14  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x15b19  ldarg.1
0x15b1a  ldstr    aDivIdEmailenga// "<div id = \"EmailEngagementParentcontai"...
0x15b1f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15b24  call     bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailEngagementActionsControl::IsEmailEngagementFeatureEnabled()
0x15b29  brfalse  loc_16747
0x15b2e  ldloc.0
0x15b2f  brtrue   loc_16747
0x15b34  ldarg.0
0x15b35  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailEngagementActionsControl::get_CurrentForm()
0x15b3a  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_IsTurboForm()
0x15b3f  brfalse  loc_16747
0x15b44  ldarg.1
0x15b45  ldstr    aDivIdEmailenga_0// "<div id=\"EmailEngagementActionsTitle\""...
0x15b4a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15b4f  ldarg.1
0x15b50  ldstr    aH3IdEmailengag// "<h3 id=\"EmailEngagementActionsHeader\""...
0x15b55  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15b5a  ldarg.1
0x15b5b  ldstr    aH3// "</h3>"
0x15b60  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15b65  ldarg.1
0x15b66  ldstr    aDiv_0// "</div>"
0x15b6b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15b70  ldarg.1
0x15b71  ldstr    aDivClassMsCrmD// "<div class=\"ms-crm-div-NotVisible\" id"...
0x15b76  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15b7b  ldarg.1
0x15b7c  ldstr    aDivIdEmailfoll// "<div id=\"emailFollowUnfollow\">"
0x15b81  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15b86  ldarg.1
0x15b87  ldstr    aDivIdEmailFoll// "<div id=\"email_followed\" class =\"Chi"...
0x15b8c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15b91  ldarg.1
0x15b92  ldstr    aDivClassThumbn// "<div class=\"thumbnailImg\">"
0x15b97  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15b9c  ldarg.1
0x15b9d  ldstr    aDivClassIconId// "<div class=\"icon\" id=\"email_followed"...
0x15ba2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x15ba7  ldstr    aEmailEngagemen// "Email_Engagement_Follow_Section_Follow_"...
0x15bac  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15bb1  ldarg.0
0x15bb2  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailEngagementActionsControl::getCurrentTabIndex()
0x15bb7  box      [mscorlib]System.Int32
0x15bbc  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object)
0x15bc1  ldarg.1
0x15bc2  ldstr    aDivClassMsCrmD_0// "<div class=\"ms-crm-div-NotVisible\"> {"...
0x15bc7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x15bcc  ldstr    aEmailEngagemen// "Email_Engagement_Follow_Section_Follow_"...
0x15bd1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15bd6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x15bdb  ldarg.1
0x15bdc  ldstr    aDiv_0// "</div>"
0x15be1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15be6  ldarg.1
0x15be7  ldstr    aDiv_0// "</div>"
0x15bec  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15bf1  ldarg.1
0x15bf2  ldstr    aDivClassActivi// "<div class=\"activityText\">"
0x15bf7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15bfc  ldarg.1
0x15bfd  ldstr    aP// "<p>"
0x15c02  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15c07  ldarg.1
0x15c08  ldstr    aSpanTabindex0I// "<span tabindex=\"{0}\" id=\"email_follo"...
0x15c0d  ldarg.0
0x15c0e  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailEngagementActionsControl::getCurrentTabIndex()
0x15c13  box      [mscorlib]System.Int32
0x15c18  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x15c1d  ldarg.1
0x15c1e  ldstr    aATabindex0Href// "<a tabindex=\"{0}\" href=\"#\" id=\"ema"...
0x15c23  ldarg.0
0x15c24  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailEngagementActionsControl::getCurrentTabIndex()
0x15c29  box      [mscorlib]System.Int32
0x15c2e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x15c33  ldarg.1
0x15c34  ldstr    aP_0// "</p>"
0x15c39  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15c3e  ldarg.1
0x15c3f  ldstr    aDivIdActivityl// "<div id=\"activityLink\" class=\"activi"...
0x15c44  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15c49  ldarg.1
0x15c4a  ldstr    aAClassEmailact// "<a class=\"emailActivityLink\" tabindex"...
0x15c4f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x15c54  ldstr    aEmailEngagemen_0// "Email_Engagement_Follow_Section_Link_Fo"...
0x15c59  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15c5e  ldarg.0
0x15c5f  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailEngagementActionsControl::getCurrentTabIndex()
0x15c64  box      [mscorlib]System.Int32
0x15c69  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object)
0x15c6e  ldarg.1
0x15c6f  ldstr    aDiv_0// "</div>"
0x15c74  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15c79  ldarg.1
0x15c7a  ldstr    aDiv_0// "</div>"
0x15c7f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15c84  ldarg.1
0x15c85  ldstr    aDiv_0// "</div>"
0x15c8a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15c8f  ldarg.1
0x15c90  ldstr    aDivIdEmailCann// "<div id=\"email_cannot_be_followed\" cl"...
0x15c95  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15c9a  ldarg.1
0x15c9b  ldstr    aDivClassThumbn// "<div class=\"thumbnailImg\">"
0x15ca0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15ca5  ldarg.1
0x15ca6  ldstr    aDivClassIconTa// "<div class=\"icon\" tabindex=\"{1}\" ar"...
0x15cab  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x15cb0  ldstr    aEmailEngagemen_1// "Email_Engagement_Follow_Section_Link_Fo"...
0x15cb5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15cba  ldarg.0
0x15cbb  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailEngagementActionsControl::getCurrentTabIndex()
0x15cc0  box      [mscorlib]System.Int32
0x15cc5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object)
0x15cca  ldarg.1
0x15ccb  ldstr    aDivClassMsCrmD_0// "<div class=\"ms-crm-div-NotVisible\"> {"...
0x15cd0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x15cd5  ldstr    aEmailEngagemen_1// "Email_Engagement_Follow_Section_Link_Fo"...
0x15cda  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15cdf  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x15ce4  ldarg.1
0x15ce5  ldstr    aDiv_0// "</div>"
0x15cea  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15cef  ldarg.1
0x15cf0  ldstr    aDiv_0// "</div>"
0x15cf5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15cfa  ldarg.1
0x15cfb  ldstr    aDivClassActivi// "<div class=\"activityText\">"
0x15d00  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15d05  ldarg.1
0x15d06  ldstr    aP// "<p>"
0x15d0b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15d10  ldarg.1
0x15d11  ldstr    aSpanTabindex0I_0// "<span tabindex=\"{0}\" id=\"email_canno"...
0x15d16  ldarg.0
0x15d17  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailEngagementActionsControl::getCurrentTabIndex()
0x15d1c  box      [mscorlib]System.Int32
0x15d21  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x15d26  ldarg.1
0x15d27  ldstr    aATabindex0Href_0// "<a tabindex=\"{0}\" href=\"#\" id=\"ema"...
0x15d2c  ldarg.0
0x15d2d  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailEngagementActionsControl::getCurrentTabIndex()
0x15d32  box      [mscorlib]System.Int32
0x15d37  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x15d3c  ldarg.1
0x15d3d  ldstr    aP_0// "</p>"
0x15d42  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15d47  ldarg.1
0x15d48  ldstr    aDivIdActivityl// "<div id=\"activityLink\" class=\"activi"...
0x15d4d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15d52  ldarg.1
0x15d53  ldstr    aAClassEmailact_0// "<a class=\"emailActivityLink\" tabindex"...
0x15d58  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x15d5d  ldstr    aEmailEngagemen_2// "Email_Engagement_Follow_Section_Link_Fo"...
0x15d62  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15d67  ldarg.0
0x15d68  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailEngagementActionsControl::getCurrentTabIndex()
0x15d6d  box      [mscorlib]System.Int32
0x15d72  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object)
0x15d77  ldarg.1
0x15d78  ldstr    aAClassEmailact_1// "<a class=\"emailActivityLink\" tabindex"...
0x15d7d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x15d82  ldstr    aEmailEngagemen_3// "Email_Engagement_Follow_Section_Link_Fo"...
0x15d87  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15d8c  ldarg.0
0x15d8d  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailEngagementActionsControl::getCurrentTabIndex()
0x15d92  box      [mscorlib]System.Int32
0x15d97  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object)
0x15d9c  ldarg.1
0x15d9d  ldstr    aAClassEmailact_2// "<a class=\"emailActivityLink\" tabindex"...
0x15da2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x15da7  ldstr    aEmailEngagemen_0// "Email_Engagement_Follow_Section_Link_Fo"...
0x15dac  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15db1  ldarg.0
0x15db2  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailEngagementActionsControl::getCurrentTabIndex()
0x15db7  box      [mscorlib]System.Int32
0x15dbc  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object)
0x15dc1  ldarg.1
0x15dc2  ldstr    aDiv_0// "</div>"
0x15dc7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15dcc  ldarg.1
0x15dcd  ldstr    aDiv_0// "</div>"
0x15dd2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15dd7  ldarg.1
0x15dd8  ldstr    aDiv_0// "</div>"
0x15ddd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15de2  ldarg.1
0x15de3  ldstr    aDivIdEmailCann_0// "<div id=\"email_cannot_be_followed_for_"...
0x15de8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15ded  ldarg.1
0x15dee  ldstr    aDivClassThumbn// "<div class=\"thumbnailImg\">"
0x15df3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15df8  ldarg.1
0x15df9  ldstr    aDivClassIconTa// "<div class=\"icon\" tabindex=\"{1}\" ar"...
0x15dfe  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x15e03  ldstr    aEmailEngagemen_1// "Email_Engagement_Follow_Section_Link_Fo"...
0x15e08  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15e0d  ldarg.0
0x15e0e  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailEngagementActionsControl::getCurrentTabIndex()
0x15e13  box      [mscorlib]System.Int32
0x15e18  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object)
0x15e1d  ldarg.1
0x15e1e  ldstr    aDivClassMsCrmD_0// "<div class=\"ms-crm-div-NotVisible\"> {"...
0x15e23  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x15e28  ldstr    aEmailEngagemen_1// "Email_Engagement_Follow_Section_Link_Fo"...
0x15e2d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15e32  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x15e37  ldarg.1
0x15e38  ldstr    aDiv_0// "</div>"
0x15e3d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15e42  ldarg.1
0x15e43  ldstr    aDiv_0// "</div>"
0x15e48  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15e4d  ldarg.1
0x15e4e  ldstr    aDivClassActivi// "<div class=\"activityText\">"
0x15e53  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15e58  ldarg.1
0x15e59  ldstr    aP// "<p>"
0x15e5e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15e63  ldarg.1
0x15e64  ldstr    aSpanTabindex0I_1// "<span tabindex=\"{0}\" id=\"email_canno"...
0x15e69  ldarg.0
0x15e6a  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailEngagementActionsControl::getCurrentTabIndex()
0x15e6f  box      [mscorlib]System.Int32
0x15e74  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x15e79  ldarg.1
0x15e7a  ldstr    aATabindex0Href_1// "<a tabindex=\"{0}\" href=\"#\" id=\"ema"...
0x15e7f  ldarg.0
0x15e80  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailEngagementActionsControl::getCurrentTabIndex()
0x15e85  box      [mscorlib]System.Int32
0x15e8a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x15e8f  ldarg.1
0x15e90  ldstr    aP_0// "</p>"
0x15e95  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15e9a  ldarg.1
0x15e9b  ldstr    aDiv_0// "</div>"
0x15ea0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15ea5  ldarg.1
0x15ea6  ldstr    aDiv_0// "</div>"
0x15eab  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15eb0  ldarg.1
0x15eb1  ldstr    aDivIdEmailNotF// "<div id=\"email_not_followed\" class ="...
0x15eb6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15ebb  ldarg.1
0x15ebc  ldstr    aDivClassThumbn// "<div class=\"thumbnailImg\">"
0x15ec1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15ec6  ldarg.1
0x15ec7  ldstr    aDivClassIconTa// "<div class=\"icon\" tabindex=\"{1}\" ar"...
0x15ecc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x15ed1  ldstr    aEmailEngagemen_4// "Email_Engagement_Follow_Section_Follow_"...
0x15ed6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15edb  ldarg.0
0x15edc  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailEngagementActionsControl::getCurrentTabIndex()
0x15ee1  box      [mscorlib]System.Int32
0x15ee6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object)
0x15eeb  ldarg.1
0x15eec  ldstr    aDivClassMsCrmD_0// "<div class=\"ms-crm-div-NotVisible\"> {"...
0x15ef1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x15ef6  ldstr    aEmailEngagemen_4// "Email_Engagement_Follow_Section_Follow_"...
0x15efb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15f00  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x15f05  ldarg.1
0x15f06  ldstr    aDiv_0// "</div>"
0x15f0b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15f10  ldarg.1
0x15f11  ldstr    aDiv_0// "</div>"
0x15f16  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15f1b  ldarg.1
0x15f1c  ldstr    aDivClassActivi// "<div class=\"activityText\">"
0x15f21  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15f26  ldarg.1
0x15f27  ldstr    aP// "<p>"
0x15f2c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15f31  ldarg.1
0x15f32  ldstr    aSpanTabindex0I_2// "<span tabindex=\"{0}\" id=\"email_not_f"...
0x15f37  ldarg.0
0x15f38  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailEngagementActionsControl::getCurrentTabIndex()
0x15f3d  box      [mscorlib]System.Int32
0x15f42  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x15f47  ldarg.1
0x15f48  ldstr    aATabindex0Href_2// "<a tabindex=\"{0}\" href=\"#\" id=\"ema"...
0x15f4d  ldarg.0
0x15f4e  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailEngagementActionsControl::getCurrentTabIndex()
0x15f53  box      [mscorlib]System.Int32
0x15f58  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x15f5d  ldarg.1
  ... truncated ...
```
