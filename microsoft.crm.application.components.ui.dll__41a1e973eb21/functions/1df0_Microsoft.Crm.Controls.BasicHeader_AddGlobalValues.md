# Microsoft.Crm.Controls.BasicHeader::AddGlobalValues

- ea: `0x1df0`
- end: `0x20d1`
- name: `Microsoft.Crm.Controls.BasicHeader::AddGlobalValues`
- size: `737`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x2ef0`
- `0x38d0`
- `0x40f0`
- `0x7070`
- `0x7920`

## string_xrefs

- `0x1e25`: `LOCID_FORM_RECOMMENDED_ALT`
- `0x1e2b`: `Forms.Recommended.AltTag`
- `0x1e3c`: `LOCID_COPY_SHORTCUT_ERROR`
- `0x1f11`: `Web._common.error.unsupported.action`
- `0x2047`: `LOCID_NAV_RIGHTLINK_TOOLTIP`
- `0x204d`: `Homepage_Navigation_RightNavLink_Tooltip`
- `0x205e`: `LOCID_NAV_LEFTLINK_TOOLTIP`
- `0x2064`: `Homepage_Navigation_LeftNavLink_Tooltip`

## pseudocode

```c

```

## disassembly

```asm
0x1df0  ldarg.0
0x1df1  call     instance void Microsoft.Crm.Controls.Header::AddGlobalValues()
0x1df6  ldarg.0
0x1df7  ldstr    aLocidFormRequi// "LOCID_FORM_REQUIRED_BKG_COLOR"
0x1dfc  ldarg.0
0x1dfd  ldstr    aRequiredFields// "Required_Fields_Background_Color"
0x1e02  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1e07  ldc.i4.0
0x1e08  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1e0d  ldarg.0
0x1e0e  ldstr    aLocidFormRequi_0// "LOCID_FORM_REQUIRED_ALT"
0x1e13  ldarg.0
0x1e14  ldstr    aFormsRequiredA// "Forms.Required.AltTag"
0x1e19  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1e1e  ldc.i4.0
0x1e1f  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1e24  ldarg.0
0x1e25  ldstr    aLocidFormRecom// "LOCID_FORM_RECOMMENDED_ALT"
0x1e2a  ldarg.0
0x1e2b  ldstr    aFormsRecommend// "Forms.Recommended.AltTag"
0x1e30  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1e35  ldc.i4.0
0x1e36  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1e3b  ldarg.0
0x1e3c  ldstr    aLocidCopyShort// "LOCID_COPY_SHORTCUT_ERROR"
0x1e41  ldarg.0
0x1e42  ldstr    aShortcutToClip// "Shortcut_To_Clipboard_Error"
0x1e47  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1e4c  ldc.i4.0
0x1e4d  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1e52  ldarg.0
0x1e53  ldstr    aLocidRvPinicon// "LOCID_RV_PINICON_TOOLTIP"
0x1e58  ldarg.0
0x1e59  ldstr    aRecentlyviewed// "RecentlyViewed_PinIcon_Tooltip"
0x1e5e  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1e63  ldc.i4.0
0x1e64  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1e69  ldarg.0
0x1e6a  ldstr    aLocidRvUnpinic// "LOCID_RV_UNPINICON_TOOLTIP"
0x1e6f  ldarg.0
0x1e70  ldstr    aRecentlyviewed_0// "RecentlyViewed_UnpinIcon_Tooltip"
0x1e75  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1e7a  ldc.i4.0
0x1e7b  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1e80  ldarg.0
0x1e81  ldstr    aLocidCtrlMulti// "LOCID_CTRL_MULTIS_SEP"
0x1e86  ldarg.0
0x1e87  ldstr    aControlMultise// "Control.MultiSelect.Separator"
0x1e8c  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1e91  ldc.i4.0
0x1e92  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1e97  ldarg.0
0x1e98  ldstr    aLocidCtrlMulti_0// "LOCID_CTRL_MULTIS_SELECT"
0x1e9d  ldarg.0
0x1e9e  ldstr    aControlMultise_0// "Control.MultiSelect.Select.Tooltip"
0x1ea3  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1ea8  ldc.i4.0
0x1ea9  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1eae  ldarg.0
0x1eaf  ldstr    aLocidCtrlMulti_1// "LOCID_CTRL_MULTIS_UNSELECT"
0x1eb4  ldarg.0
0x1eb5  ldstr    aControlMultise_1// "Control.MultiSelect.Unselect.Tooltip"
0x1eba  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1ebf  ldc.i4.0
0x1ec0  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1ec5  ldarg.0
0x1ec6  ldstr    aLocidCtrlMulti_2// "LOCID_CTRL_MULTIS_BTN_OK"
0x1ecb  ldarg.0
0x1ecc  ldstr    aControlMultise_2// "Control.MultiSelect.Button.Ok"
0x1ed1  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1ed6  ldc.i4.0
0x1ed7  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1edc  ldarg.0
0x1edd  ldstr    aLocidCtrlMulti_3// "LOCID_CTRL_MULTIS_BTN_CANCEL"
0x1ee2  ldarg.0
0x1ee3  ldstr    aControlMultise_3// "Control.MultiSelect.Button.Cancel"
0x1ee8  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1eed  ldc.i4.0
0x1eee  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1ef3  ldarg.0
0x1ef4  ldstr    aLocidActionUns// "LOCID_ACTION_UNSUPPORTED_ERROR"
0x1ef9  ldarg.0
0x1efa  ldstr    aErrorMessage0x_0// "Error_Message_0x80040315"
0x1eff  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1f04  ldc.i4.0
0x1f05  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1f0a  ldarg.0
0x1f0b  ldstr    aLocidUnsupport// "LOCID_UNSUPPORTED_RIBBONACTION"
0x1f10  ldarg.0
0x1f11  ldstr    aWebCommonError// "Web._common.error.unsupported.action"
0x1f16  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1f1b  ldc.i4.0
0x1f1c  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1f21  ldarg.0
0x1f22  ldstr    aLocidLookupLab// "LOCID_LOOKUP_LABEL_FOR_EDIT"
0x1f27  ldarg.0
0x1f28  ldstr    aLookuplabelfor// "LookupLabelForEditElement"
0x1f2d  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1f32  ldc.i4.0
0x1f33  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1f38  ldarg.0
0x1f39  ldstr    aLocidEmailPref// "LOCID_EMAIL_PREFIX_REPLY"
0x1f3e  ldarg.0
0x1f3f  ldstr    aEmailPrefixRep// "Email_Prefix_Reply"
0x1f44  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1f49  ldc.i4.0
0x1f4a  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1f4f  ldarg.0
0x1f50  ldstr    aLocidEmailPref_0// "LOCID_EMAIL_PREFIX_FORWARD"
0x1f55  ldarg.0
0x1f56  ldstr    aEmailPrefixFor// "Email_Prefix_Forward"
0x1f5b  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1f60  ldc.i4.0
0x1f61  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1f66  ldarg.0
0x1f67  ldstr    aLocidEmailFoll// "LOCID_EMAIL_FOLLOWUP_TO"
0x1f6c  ldarg.0
0x1f6d  ldstr    aEmailFollowupT// "Email_Followup_ToRecipients"
0x1f72  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1f77  ldc.i4.0
0x1f78  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1f7d  ldarg.0
0x1f7e  ldstr    aLocidEmailFoll_0// "LOCID_EMAIL_FOLLOWUP_SUBJECT"
0x1f83  ldarg.0
0x1f84  ldstr    aEmailFollowupS// "Email_Followup_Subject"
0x1f89  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1f8e  ldc.i4.0
0x1f8f  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1f94  ldarg.0
0x1f95  ldstr    aLocidEmailFoll_1// "LOCID_EMAIL_FOLLOWUP_SENDER"
0x1f9a  ldarg.0
0x1f9b  ldstr    aEmailFollowupS_0// "Email_Followup_Sender"
0x1fa0  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1fa5  ldc.i4.0
0x1fa6  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1fab  ldarg.0
0x1fac  ldstr    aLocidEmailFoll_2// "LOCID_EMAIL_FOLLOWUP_RECEIVED"
0x1fb1  ldarg.0
0x1fb2  ldstr    aEmailFollowupR// "Email_Followup_ReceivedDate"
0x1fb7  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1fbc  ldc.i4.0
0x1fbd  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1fc2  ldarg.0
0x1fc3  ldstr    aLocidEmailFoll_3// "LOCID_EMAIL_FOLLOWUP_HEADER"
0x1fc8  ldarg.0
0x1fc9  ldstr    aEmailFollowupH// "Email_Followup_Header"
0x1fce  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1fd3  ldc.i4.0
0x1fd4  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1fd9  ldarg.0
0x1fda  ldstr    aLocidEmailFoll_4// "LOCID_EMAIL_FOLLOWUP_CC"
0x1fdf  ldarg.0
0x1fe0  ldstr    aEmailFollowupC// "Email_Followup_CcRecipients"
0x1fe5  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1fea  ldc.i4.0
0x1feb  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1ff0  ldarg.0
0x1ff1  ldstr    aLocidMscrmMsgb// "LOCID_MSCRM_MSGBODY_FONTS"
0x1ff6  ldarg.0
0x1ff7  ldstr    aMicrosoftCrmMs// "Microsoft_Crm_Msgbody_Default_fonts"
0x1ffc  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x2001  ldc.i4.0
0x2002  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x2007  ldarg.0
0x2008  ldstr    aLocidDlgOkBtnL// "LOCID_DLG_OK_BTN_LABEL"
0x200d  ldarg.0
0x200e  ldstr    aDialogButtonOk// "Dialog_Button_Ok"
0x2013  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x2018  ldc.i4.0
0x2019  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x201e  ldarg.0
0x201f  ldstr    aLocidDlgCancel// "LOCID_DLG_CANCEL_BTN_LABEL"
0x2024  ldarg.0
0x2025  ldstr    aDialogButtonCa// "Dialog_Button_Cancel"
0x202a  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x202f  ldc.i4.0
0x2030  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x2035  ldarg.0
0x2036  ldstr    aIsvAdditionalA// "ISV_ADDITIONAL_AUTH"
0x203b  ldarg.0
0x203c  call     instance string Microsoft.Crm.Controls.Header::BuildExternalAuthParameters()
0x2041  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0x2046  ldarg.0
0x2047  ldstr    aLocidNavRightl// "LOCID_NAV_RIGHTLINK_TOOLTIP"
0x204c  ldarg.0
0x204d  ldstr    aHomepageNaviga// "Homepage_Navigation_RightNavLink_Toolti"...
0x2052  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x2057  ldc.i4.0
0x2058  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x205d  ldarg.0
0x205e  ldstr    aLocidNavLeftli// "LOCID_NAV_LEFTLINK_TOOLTIP"
0x2063  ldarg.0
0x2064  ldstr    aHomepageNaviga_0// "Homepage_Navigation_LeftNavLink_Tooltip"
0x2069  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x206e  ldc.i4.0
0x206f  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x2074  ldarg.0
0x2075  ldstr    aLocidDlgReturn// "LOCID_DLG_RETURNTOCRM_TITLE"
0x207a  ldarg.0
0x207b  ldstr    aReturntocrmlis// "ReturnToCrmList.Warning.Dialog.Tite"
0x2080  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x2085  ldc.i4.0
0x2086  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x208b  ldarg.0
0x208c  ldstr    aLocidDlgReturn_0// "LOCID_DLG_RETURNTOCRM_TEXT"
0x2091  ldarg.0
0x2092  ldstr    aReturntocrmlis_0// "ReturnToCrmList.Warning.Dialog.Text"
0x2097  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x209c  ldc.i4.0
0x209d  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x20a2  ldarg.0
0x20a3  ldstr    aLocidResolveWa// "LOCID_RESOLVE_WARNING_TEXT"
0x20a8  ldarg.0
0x20a9  ldstr    aResolvedSyncer// "Resolved.SyncError.Notification.Warning"...
0x20ae  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x20b3  ldc.i4.0
0x20b4  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x20b9  ldarg.0
0x20ba  ldstr    aLocidResolveIn// "LOCID_RESOLVE_INFO_TEXT"
0x20bf  ldarg.0
0x20c0  ldstr    aResolvedSyncer_0// "Resolved.SyncError.Notification.Informa"...
0x20c5  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x20ca  ldc.i4.0
0x20cb  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x20d0  ret
```
