# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailEngagementActionsControl::GenerateClientStrings

- ea: `0x167a0`
- end: `0x16d3c`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailEngagementActionsControl::GenerateClientStrings`
- size: `1436`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x159e0`

## string_xrefs

- `0x16880`: `Email_Engagement_Actions_Link_Delay_Mail`
- `0x16cf8`: `Email_Engagement_Actions_Link_Delay_Mail_Title`
- `0x16832`: `Email_Engagement_Actions_Email_Scheduled`
- `0x1685c`: `EMAIL_ACT_LINK_RECEIPIENTS_PREF`
- `0x16866`: `Email_Engagement_Actions_Link_Receipients_Preferences`
- `0x16876`: `EMAIL_ACT_LINK_DELAY_SEND`
- `0x16890`: `EMAIL_ACT_LINK_SET_REMINDER`
- `0x1689a`: `Email_Engagement_Actions_Link_Set_Reminder`
- `0x168aa`: `EMAIL_ACT_LINK_DONT_FOLLOW`
- `0x168b4`: `Email_Engagement_Actions_Link_Dont_Follow`
- `0x168c4`: `EMAIL_ACT_LINK_CONTACT_PREFERENCES`
- `0x168ce`: `Email_Engagement_Actions_Link_View_Contact_Preferences`
- `0x168de`: `EMAIL_ACT_LINK_CHANGE_SCHEDULE`
- `0x168e8`: `Email_Engagement_Actions_Link_Change_Schedule`
- `0x168f8`: `EMAIL_ACT_LINK_CHANGE_REMINDER`
- `0x16902`: `Email_Engagement_Actions_Link_Change_Reminder`
- `0x16912`: `EMAIL_ACT_LINK_REMOVE_REMINDER`
- `0x1691c`: `Email_Engagement_Actions_Link_Remove_Reminder`
- `0x1692c`: `EMAIL_ACT_LINK_RETRY_FOLLOW`
- `0x16936`: `Email_Engagement_Actions_Link_Retry_Follow`
- `0x169ae`: `EMAIL_ACT_LINK_SET_DELAY`
- `0x169b8`: `Email_Engagement_Actions_Link_Set_Delay`
- `0x169c8`: `EMAIL_ACT_LINK_REMOVE_DELAY`
- `0x169d2`: `Email_Engagement_Actions_Link_Reset_Schedule`
- `0x16cee`: `EMAIL_ENGAGEMENT_ACTIONS_LINK_DELAY_MAIL_TITLE`
- `0x16d08`: `EMAIL_ENGAGEMENT_ACTIONS_LINK_HELP_URL`
- `0x16d12`: `Email_Engagement_Actions_Link_Help_Url`
- `0x16d22`: `EMAIL_ENGAGEMENT_ACTIONS_LINK_HELP_TOOLTIP`
- `0x16d2c`: `Email_Engagement_Actions_Link_Help_Tooltip`

## pseudocode

```c

```

## disassembly

```asm
0x167a0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x167a5  dup
0x167a6  ldstr    aEmailActNotFol// "EMAIL_ACT_NOT_FOLLOWED"
0x167ab  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x167b0  ldstr    aEmailEngagemen_20// "Email_Engagement_Actions_Not_Followed"
0x167b5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x167ba  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x167bf  dup
0x167c0  ldstr    aEmailActDelayM// "EMAIL_ACT_DELAY_MAIL"
0x167c5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x167ca  ldstr    aEmailEngagemen_21// "Email_Engagement_Actions_Delay_Sending_"...
0x167cf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x167d4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x167d9  dup
0x167da  ldstr    aEmailActRemind// "EMAIL_ACT_REMINDER"
0x167df  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x167e4  ldstr    aEmailEngagemen_22// "Email_Engagement_Actions_Reminder"
0x167e9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x167ee  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x167f3  dup
0x167f4  ldstr    aEmailActFollow// "EMAIL_ACT_FOLLOWED"
0x167f9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x167fe  ldstr    aEmailEngagemen_23// "Email_Engagement_Actions_Followed"
0x16803  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16808  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1680d  dup
0x1680e  ldstr    aEmailActFollow_0// "EMAIL_ACT_FOLLOW_AUTO"
0x16813  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16818  ldstr    aEmailEngagemen_24// "Email_Engagement_Actions_Follow_Automat"...
0x1681d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16822  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16827  dup
0x16828  ldstr    aEmailActSch// "EMAIL_ACT_SCH"
0x1682d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16832  ldstr    aEmailEngagemen_25// "Email_Engagement_Actions_Email_Schedule"...
0x16837  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1683c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16841  dup
0x16842  ldstr    aEmailActToolti// "EMAIL_ACT_TOOLTIP_SUGGESTION"
0x16847  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1684c  ldstr    aEmailEngagemen_8// "Email_Engagement_Actions_Tooltip_Has_Su"...
0x16851  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16856  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1685b  dup
0x1685c  ldstr    aEmailActLinkRe// "EMAIL_ACT_LINK_RECEIPIENTS_PREF"
0x16861  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16866  ldstr    aEmailEngagemen_26// "Email_Engagement_Actions_Link_Receipien"...
0x1686b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16870  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16875  dup
0x16876  ldstr    aEmailActLinkDe// "EMAIL_ACT_LINK_DELAY_SEND"
0x1687b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16880  ldstr    aEmailEngagemen_7// "Email_Engagement_Actions_Link_Delay_Mai"...
0x16885  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1688a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1688f  dup
0x16890  ldstr    aEmailActLinkSe// "EMAIL_ACT_LINK_SET_REMINDER"
0x16895  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1689a  ldstr    aEmailEngagemen_27// "Email_Engagement_Actions_Link_Set_Remin"...
0x1689f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x168a4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x168a9  dup
0x168aa  ldstr    aEmailActLinkDo// "EMAIL_ACT_LINK_DONT_FOLLOW"
0x168af  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x168b4  ldstr    aEmailEngagemen_28// "Email_Engagement_Actions_Link_Dont_Foll"...
0x168b9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x168be  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x168c3  dup
0x168c4  ldstr    aEmailActLinkCo// "EMAIL_ACT_LINK_CONTACT_PREFERENCES"
0x168c9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x168ce  ldstr    aEmailEngagemen_29// "Email_Engagement_Actions_Link_View_Cont"...
0x168d3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x168d8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x168dd  dup
0x168de  ldstr    aEmailActLinkCh// "EMAIL_ACT_LINK_CHANGE_SCHEDULE"
0x168e3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x168e8  ldstr    aEmailEngagemen_30// "Email_Engagement_Actions_Link_Change_Sc"...
0x168ed  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x168f2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x168f7  dup
0x168f8  ldstr    aEmailActLinkCh_0// "EMAIL_ACT_LINK_CHANGE_REMINDER"
0x168fd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16902  ldstr    aEmailEngagemen_31// "Email_Engagement_Actions_Link_Change_Re"...
0x16907  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1690c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16911  dup
0x16912  ldstr    aEmailActLinkRe_0// "EMAIL_ACT_LINK_REMOVE_REMINDER"
0x16917  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1691c  ldstr    aEmailEngagemen_32// "Email_Engagement_Actions_Link_Remove_Re"...
0x16921  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16926  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1692b  dup
0x1692c  ldstr    aEmailActLinkRe_1// "EMAIL_ACT_LINK_RETRY_FOLLOW"
0x16931  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16936  ldstr    aEmailEngagemen_33// "Email_Engagement_Actions_Link_Retry_Fol"...
0x1693b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16940  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16945  dup
0x16946  ldstr    aEmailActNotFol_0// "EMAIL_ACT_NOT_FOLLOW"
0x1694b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16950  ldstr    aEmailEngagemen_34// "Email_Engagement_Actions_Email_Not_Foll"...
0x16955  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1695a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1695f  dup
0x16960  ldstr    aEmailActFollow_1// "EMAIL_ACT_FOLLOW"
0x16965  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1696a  ldstr    aEmailEngagemen_35// "Email_Engagement_Actions_Follow"
0x1696f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16974  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16979  dup
0x1697a  ldstr    aEmailActSent// "EMAIL_ACT_SENT"
0x1697f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16984  ldstr    aEmailEngagemen_36// "Email_Engagement_Actions_Email_Sent"
0x16989  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1698e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16993  dup
0x16994  ldstr    aEmailActDelayS// "EMAIL_ACT_DELAY_SEND_SET"
0x16999  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1699e  ldstr    aEmailEngagemen_37// "Email_Engagement_Actions_Delay_Send_Set"
0x169a3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x169a8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x169ad  dup
0x169ae  ldstr    aEmailActLinkSe_0// "EMAIL_ACT_LINK_SET_DELAY"
0x169b3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x169b8  ldstr    aEmailEngagemen_38// "Email_Engagement_Actions_Link_Set_Delay"
0x169bd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x169c2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x169c7  dup
0x169c8  ldstr    aEmailActLinkRe_2// "EMAIL_ACT_LINK_REMOVE_DELAY"
0x169cd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x169d2  ldstr    aEmailEngagemen_39// "Email_Engagement_Actions_Link_Reset_Sch"...
0x169d7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x169dc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x169e1  dup
0x169e2  ldstr    aEmailActClickS// "EMAIL_ACT_CLICK_SAVE"
0x169e7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x169ec  ldstr    aEmailEngagemen_40// "Email_Engagement_Actions_ToolTip_Click_"...
0x169f1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x169f6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x169fb  dup
0x169fc  ldstr    aEmailActDelayS_0// "EMAIL_ACT_DELAY_SCH_EMAIL"
0x16a01  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16a06  ldstr    aEmailEngagemen_41// "Email_Engagement_Actions_Schedule_Email"
0x16a0b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16a10  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16a15  dup
0x16a16  ldstr    aEmailActRemind_0// "EMAIL_ACT_REMIND_EMAIL_NOREPLYBY"
0x16a1b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16a20  ldstr    aEmailEngagemen_42// "Email_Engagement_Actions_Remind_Email_N"...
0x16a25  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16a2a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16a2f  dup
0x16a30  ldstr    aEmailActRemind_1// "EMAIL_ACT_REMIND_NOREPLYBY_USER"
0x16a35  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16a3a  ldstr    aEmailEngagemen_43// "Email_Engagement_Actions_Remind_Email_N"...
0x16a3f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16a44  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16a49  dup
0x16a4a  ldstr    aEmailActFollow_2// "EMAIL_ACT_FOLLOW_DONTFOLLOW_ARIA_TEXT"
0x16a4f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16a54  ldstr    aEmailEngagemen_44// "Email_Engagement_Actions_Follow_DonotFo"...
0x16a59  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16a5e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16a63  dup
0x16a64  ldstr    aEmailActNonFol// "EMAIL_ACT_NON_FOLLOWABLE_ENTITY_TEXT"
0x16a69  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16a6e  ldstr    aEmailEngagemen_45// "Email_Engagement_Actions_NonFollowable_"...
0x16a73  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16a78  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16a7d  dup
0x16a7e  ldstr    aEmailDialogDat// "EMAIL_DIALOG_DATE_ERROR"
0x16a83  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16a88  ldstr    aEmailDialogDat_0// "Email_Dialog_Date_Error"
0x16a8d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16a92  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16a97  dup
0x16a98  ldstr    aEmailDelaySend// "EMAIL_DELAY_SEND_INLINEDLG_FOOTERTEXT"
0x16a9d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16aa2  ldstr    aEmailEngagemen_37// "Email_Engagement_Actions_Delay_Send_Set"
0x16aa7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16aac  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16ab1  dup
0x16ab2  ldstr    aViewContactPre// "VIEW_CONTACT_PREFERENCES_INLINEDLG_FOLL"...
0x16ab7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16abc  ldstr    aViewContactPre_0// "View_Contact_Preferences_InlineDlg_Foll"...
0x16ac1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16ac6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16acb  dup
0x16acc  ldstr    aViewContactPre_1// "VIEW_CONTACT_PREFERENCES_INLINEDLG_DONO"...
0x16ad1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16ad6  ldstr    aViewContactPre_2// "View_Contact_Preferences_InlineDlg_DoNo"...
0x16adb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16ae0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16ae5  dup
0x16ae6  ldstr    aViewContactPre_3// "VIEW_CONTACT_PREFERENCES_INLINEDLG_TABL"...
0x16aeb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16af0  ldstr    aViewContactPre_4// "View_Contact_Preferences_InlineDlg_tabl"...
0x16af5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16afa  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16aff  dup
0x16b00  ldstr    aViewContactPre_5// "VIEW_CONTACT_PREFERENCES_INLINEDLG_TABL"...
0x16b05  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16b0a  ldstr    aViewContactPre_6// "View_Contact_Preferences_InlineDlg_tabl"...
0x16b0f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16b14  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16b19  dup
0x16b1a  ldstr    aSetReminderInl// "SET_REMINDER_INLINEDLG_REMINDOPTION1_1"
0x16b1f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16b24  ldstr    aSetReminderInl_0// "Set_Reminder_InlineDlg_RemindOption1_1"
0x16b29  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16b2e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16b33  dup
0x16b34  ldstr    aSetReminderInl_1// "SET_REMINDER_INLINEDLG_REMINDOPTION1_2"
0x16b39  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16b3e  ldstr    aSetReminderInl_2// "Set_Reminder_InlineDlg_RemindOption1_2"
0x16b43  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16b48  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16b4d  dup
0x16b4e  ldstr    aSetReminderInl_3// "SET_REMINDER_INLINEDLG_REMINDOPTION2_1"
0x16b53  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16b58  ldstr    aSetReminderInl_4// "Set_Reminder_InlineDlg_RemindOption2_1"
0x16b5d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16b62  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16b67  dup
0x16b68  ldstr    aSetReminderInl_5// "SET_REMINDER_INLINEDLG_REMINDOPTION2_2"
0x16b6d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16b72  ldstr    aSetReminderInl_6// "Set_Reminder_InlineDlg_RemindOption2_2"
0x16b77  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16b7c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16b81  dup
0x16b82  ldstr    aSetReminderInl_7// "SET_REMINDER_INLINEDLG_REMINDOPTION3_1"
0x16b87  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16b8c  ldstr    aSetReminderInl_8// "Set_Reminder_InlineDlg_RemindOption3_1"
0x16b91  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16b96  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16b9b  dup
0x16b9c  ldstr    aSetReminderInl_9// "SET_REMINDER_INLINEDLG_REMINDOPTIONBY"
0x16ba1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16ba6  ldstr    aSetReminderInl_10// "Set_Reminder_InlineDlg_RemindOptionBy"
0x16bab  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16bb0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16bb5  dup
0x16bb6  ldstr    aFollowEmailInv// "FOLLOW_EMAIL_INVALID_CHOICE"
0x16bbb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16bc0  ldstr    aFollowEmailInv_0// "Follow_Email_Invalid_Choice"
0x16bc5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16bca  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16bcf  dup
0x16bd0  ldstr    aEmailEngagemen_46// "EMAIL_ENGAGEMENT_ACTIONS_ERROR_DIALOG_C"...
0x16bd5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16bda  ldstr    aEmailEngagemen_47// "Email_Engagement_Actions_Error_Dialog_C"...
0x16bdf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16be4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16be9  dup
0x16bea  ldstr    aEmailEngagemen_48// "EMAIL_ENGAGEMENT_ACTIONS_ERROR_DIALOG_R"...
0x16bef  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16bf4  ldstr    aEmailEngagemen_49// "Email_Engagement_Actions_error_dialog_r"...
0x16bf9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16bfe  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16c03  dup
0x16c04  ldstr    aEmailEngagemen_50// "EMAIL_ENGAGEMENT_ACTIONS_WARNING_ATTACH"...
0x16c09  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16c0e  ldstr    aEmailEngagemen_51// "Email_Engagement_Actions_Warning_attach"...
0x16c13  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16c18  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16c1d  dup
0x16c1e  ldstr    aEmailActButton// "EMAIL_ACT_BUTTON_OK"
0x16c23  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16c28  ldstr    aLOkText// "L_OK_Text"
0x16c2d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16c32  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16c37  dup
0x16c38  ldstr    aEmailActButton_0// "EMAIL_ACT_BUTTON_CANCEL"
0x16c3d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16c42  ldstr    aLCancelText// "L_Cancel_Text"
0x16c47  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16c4c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16c51  dup
0x16c52  ldstr    aEmailEngagemen_52// "EMAIL_ENGAGEMENT_ACTIONS_DIALOG_TITLE_F"...
0x16c57  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16c5c  ldstr    aEmailEngagemen_53// "Email_Engagement_Actions_Dialog_Title_F"...
0x16c61  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16c66  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16c6b  dup
0x16c6c  ldstr    aEmailEngagemen_54// "EMAIL_ENGAGEMENT_ACTIONS_DIALOG_TITLE_D"...
0x16c71  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16c76  ldstr    aEmailEngagemen_55// "Email_Engagement_Actions_Dialog_Title_D"...
0x16c7b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16c80  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16c85  dup
0x16c86  ldstr    aEmailActHeader// "EMAIL_ACT_HEADER"
0x16c8b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16c90  ldstr    aEmailEngagemen_56// "Email_Engagement_Header_Tooltip"
0x16c95  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16c9a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x16c9f  dup
0x16ca0  ldstr    aEmailEngagemen_57// "EMAIL_ENGAGEMENT_ACTIONS_REMINDER_NOT_F"...
0x16ca5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x16caa  ldstr    aEmailEngagemen_58// "Email_Engagement_Actions_Reminder_Not_F"...
0x16caf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
  ... truncated ...
```
