# Microsoft.Crm.Web.Tools.SystemCustomization.WebResourceEditPage::SetScriptFiles

- ea: `0x9cd50`
- end: `0x9d152`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.WebResourceEditPage::SetScriptFiles`
- size: `1026`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x9c0c0`

## string_xrefs

- `0x9cd86`: `/_common/styles/dialogs.css.aspx`
- `0x9ce17`: `/_static/_common/styles/AutoToolTip.js`
- `0x9cd56`: `/_common/styles/select.css.aspx`
- `0x9cfcd`: `SystemCustomization.EntityUtil.Messages.ConfirmEntityDelete`
- `0x9cf6a`: `SystemCustomization.EntityUtil.Messages.CannotUpdateSystemEntityIcons`
- `0x9cf8b`: `SystemCustomization.EntityUtil.Messages.CannotDeleteSystemEntity`
- `0x9ce99`: `LOCID_INVALID_WR_EXTENSION`
- `0x9cea4`: `WebResource_Editor_ValidExtension_Message`
- `0x9cec5`: `WebResource_Editor_PathAndName_Message`

## pseudocode

```c

```

## disassembly

```asm
0x9cd50  ldarg.0
0x9cd51  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9cd56  ldstr    aCommonStylesSe// "/_common/styles/select.css.aspx"
0x9cd5b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x9cd60  ldarg.0
0x9cd61  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9cd66  ldstr    aNavTabsCssAspx// "/_nav/tabs.css.aspx"
0x9cd6b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x9cd70  ldarg.0
0x9cd71  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9cd76  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
0x9cd7b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x9cd80  ldarg.0
0x9cd81  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9cd86  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x9cd8b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x9cd90  ldarg.0
0x9cd91  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9cd96  ldstr    aToolsFormedito_5// "/tools/formeditor/styles/dialogs.css.as"...
0x9cd9b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x9cda0  ldarg.0
0x9cda1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9cda6  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x9cdab  ldnull
0x9cdac  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x9cdb1  ldarg.0
0x9cdb2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9cdb7  ldstr    aStaticFormsSel// "/_static/_forms/select.js"
0x9cdbc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9cdc1  ldarg.0
0x9cdc2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9cdc7  ldstr    aStaticGridCmds// "/_static/_grid/cmds/util.js"
0x9cdcc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9cdd1  ldarg.0
0x9cdd2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9cdd7  ldstr    aStaticFormsFor// "/_static/_forms/form.js"
0x9cddc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9cde1  ldarg.0
0x9cde2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9cde7  ldstr    aStaticToolsSol_2// "/_static/tools/solution/scripts/solutio"...
0x9cdec  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9cdf1  ldarg.0
0x9cdf2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9cdf7  ldstr    aStaticToolsWeb// "/_static/tools/WebResourceEditor/script"...
0x9cdfc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9ce01  ldarg.0
0x9ce02  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9ce07  ldstr    aStaticToolsFor_2// "/_static/tools/formeditor/scripts/FormE"...
0x9ce0c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9ce11  ldarg.0
0x9ce12  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9ce17  ldstr    aStaticCommonSt// "/_static/_common/styles/AutoToolTip.js"
0x9ce1c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9ce21  ldarg.0
0x9ce22  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9ce27  ldstr    aStaticToolsSys_0// "/_static/tools/systemcustomization/scri"...
0x9ce2c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9ce31  ldarg.0
0x9ce32  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9ce37  ldstr    aStaticToolsSys_9// "/_static/tools/systemcustomization/enti"...
0x9ce3c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9ce41  ldarg.0
0x9ce42  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9ce47  ldstr    aStaticToolsSys_1// "/_static/tools/systemcustomization/scri"...
0x9ce4c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9ce51  ldarg.0
0x9ce52  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9ce57  ldstr    aLocidEntutlPub// "LOCID_ENTUTL_PUBLISHINGENT"
0x9ce5c  ldarg.0
0x9ce5d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9ce62  ldstr    aSystemcustomiz_10// "SystemCustomization.EntityUtil.Messages"...
0x9ce67  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ce6c  ldc.i4.0
0x9ce6d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9ce72  ldarg.0
0x9ce73  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9ce78  ldstr    aLocidInvalidWr// "LOCID_INVALID_WR_NAME"
0x9ce7d  ldarg.0
0x9ce7e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9ce83  ldstr    aErrorMessage0x_27// "Error_Message_0x8004f117"
0x9ce88  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ce8d  ldc.i4.0
0x9ce8e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9ce93  ldarg.0
0x9ce94  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9ce99  ldstr    aLocidInvalidWr_0// "LOCID_INVALID_WR_EXTENSION"
0x9ce9e  ldarg.0
0x9ce9f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9cea4  ldstr    aWebresourceEdi_6// "WebResource_Editor_ValidExtension_Messa"...
0x9cea9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ceae  ldc.i4.0
0x9ceaf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9ceb4  ldarg.0
0x9ceb5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9ceba  ldstr    aLocidEmptyWrNa// "LOCID_EMPTY_WR_NAME"
0x9cebf  ldarg.0
0x9cec0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9cec5  ldstr    aWebresourceEdi_7// "WebResource_Editor_PathAndName_Message"
0x9ceca  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9cecf  ldc.i4.0
0x9ced0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9ced5  ldarg.0
0x9ced6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9cedb  ldstr    aLocidUnsavedWr// "LOCID_UNSAVED_WR"
0x9cee0  ldarg.0
0x9cee1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9cee6  ldstr    aWebresourceEdi_8// "WebResource_Editor_Unsaved_Message"
0x9ceeb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9cef0  ldc.i4.0
0x9cef1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9cef6  ldarg.0
0x9cef7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9cefc  ldstr    aLocidInvalidTy// "LOCID_INVALID_TYPE"
0x9cf01  ldarg.0
0x9cf02  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9cf07  ldstr    aWebresourceEdi_9// "WebResource_EditPage_InvalidFileType"
0x9cf0c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9cf11  ldc.i4.0
0x9cf12  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9cf17  ldarg.0
0x9cf18  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9cf1d  ldstr    aLocidTypeMisma// "LOCID_TYPE_MISMATCH"
0x9cf22  ldarg.0
0x9cf23  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9cf28  ldstr    aWebresourceEdi_10// "WebResource_EditPage_TypeMismatch"
0x9cf2d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9cf32  ldc.i4.0
0x9cf33  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9cf38  ldarg.0
0x9cf39  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9cf3e  ldstr    aLocidEmptyWrCo// "LOCID_EMPTY_WR_CONTENT"
0x9cf43  ldarg.0
0x9cf44  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9cf49  ldstr    aWebresourceEdi_0// "WebResource_EditPage_NoWebResourceConte"...
0x9cf4e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9cf53  ldc.i4.0
0x9cf54  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9cf59  ldarg.0
0x9cf5a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9cf5f  ldstr    aLocidEntutlCan// "LOCID_ENTUTL_CANTUPDSYSENTICN"
0x9cf64  ldarg.0
0x9cf65  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9cf6a  ldstr    aSystemcustomiz_4// "SystemCustomization.EntityUtil.Messages"...
0x9cf6f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9cf74  ldc.i4.0
0x9cf75  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9cf7a  ldarg.0
0x9cf7b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9cf80  ldstr    aLocidEntutlCan_0// "LOCID_ENTUTL_CANTDELSYSENT"
0x9cf85  ldarg.0
0x9cf86  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9cf8b  ldstr    aSystemcustomiz_5// "SystemCustomization.EntityUtil.Messages"...
0x9cf90  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9cf95  ldc.i4.0
0x9cf96  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9cf9b  ldarg.0
0x9cf9c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9cfa1  ldstr    aLocidEntutlCan_1// "LOCID_ENTUTL_CANTPUBLISHENT"
0x9cfa6  ldarg.0
0x9cfa7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9cfac  ldstr    aSystemcustomiz_6// "SystemCustomization.EntityUtil.Messages"...
0x9cfb1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9cfb6  ldc.i4.0
0x9cfb7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9cfbc  ldarg.0
0x9cfbd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9cfc2  ldstr    aLocidEntutlCon// "LOCID_ENTUTL_CONFIRMDEL"
0x9cfc7  ldarg.0
0x9cfc8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9cfcd  ldstr    aSystemcustomiz_0// "SystemCustomization.EntityUtil.Messages"...
0x9cfd2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9cfd7  ldc.i4.0
0x9cfd8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9cfdd  ldarg.0
0x9cfde  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9cfe3  ldstr    aLocidEntutlCre// "LOCID_ENTUTL_CREATINGENT"
0x9cfe8  ldarg.0
0x9cfe9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9cfee  ldstr    aSystemcustomiz_7// "SystemCustomization.EntityUtil.Messages"...
0x9cff3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9cff8  ldc.i4.0
0x9cff9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9cffe  ldarg.0
0x9cfff  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9d004  ldstr    aLocidEntutlUpd// "LOCID_ENTUTL_UPDATINGENT"
0x9d009  ldarg.0
0x9d00a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9d00f  ldstr    aSystemcustomiz_8// "SystemCustomization.EntityUtil.Messages"...
0x9d014  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9d019  ldc.i4.0
0x9d01a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9d01f  ldarg.0
0x9d020  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9d025  ldstr    aLocidEntutlDel// "LOCID_ENTUTL_DELETINGENT"
0x9d02a  ldarg.0
0x9d02b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9d030  ldstr    aSystemcustomiz_9// "SystemCustomization.EntityUtil.Messages"...
0x9d035  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9d03a  ldc.i4.0
0x9d03b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9d040  ldarg.0
0x9d041  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9d046  ldstr    aLocidEntutlPub// "LOCID_ENTUTL_PUBLISHINGENT"
0x9d04b  ldarg.0
0x9d04c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9d051  ldstr    aSystemcustomiz_10// "SystemCustomization.EntityUtil.Messages"...
0x9d056  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9d05b  ldc.i4.0
0x9d05c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9d061  ldarg.0
0x9d062  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9d067  ldstr    aLocidSyscustCa// "LOCID_SYSCUST_CANTBEBLANK"
0x9d06c  ldarg.0
0x9d06d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9d072  ldstr    aSystemcustomiz_11// "SystemCustomization.Validation.Errors.C"...
0x9d077  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9d07c  ldc.i4.0
0x9d07d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9d082  ldarg.0
0x9d083  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9d088  ldstr    aLocidSyscustIn// "LOCID_SYSCUST_INVALCHARS"
0x9d08d  ldarg.0
0x9d08e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9d093  ldstr    aSystemcustomiz_12// "SystemCustomization.Validation.Errors.C"...
0x9d098  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9d09d  ldc.i4.0
0x9d09e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9d0a3  ldarg.0
0x9d0a4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9d0a9  ldstr    aLocidSyscustAl// "LOCID_SYSCUST_ALPHANUMSONLY"
0x9d0ae  ldarg.0
0x9d0af  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9d0b4  ldstr    aSystemcustomiz_13// "SystemCustomization.Validation.Errors.C"...
0x9d0b9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9d0be  ldc.i4.0
0x9d0bf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9d0c4  ldarg.0
0x9d0c5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9d0ca  ldstr    aLocidFormedCan// "LOCID_FORMED_CANNOTPUBLISH"
0x9d0cf  ldarg.0
0x9d0d0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9d0d5  ldstr    aWebToolsFormed_1// "Web.Tools.FormEditor.CanNotPublish.Mess"...
0x9d0da  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9d0df  ldc.i4.0
0x9d0e0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9d0e5  ldarg.0
0x9d0e6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9d0eb  ldstr    aLocidWreditSav// "LOCID_WREDIT_SAVECHANGES"
0x9d0f0  ldarg.0
0x9d0f1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9d0f6  ldstr    aWebToolsFormed_2// "Web.Tools.FormEditor.formeditor.aspx_72"
0x9d0fb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9d100  ldc.i4.0
0x9d101  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9d106  ldarg.0
0x9d107  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9d10c  ldstr    aLocidInvalidVe// "LOCID_INVALID_VERSION_FORMAT"
0x9d111  ldarg.0
0x9d112  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9d117  ldstr    aErrorMessage0x_5// "Error_Message_0x8004f01e"
0x9d11c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9d121  ldc.i4.0
0x9d122  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9d127  ldarg.0
0x9d128  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9d12d  ldstr    aMscrmAutotoolt// "Mscrm.AutoToolTip"
0x9d132  ldstr    aNameC// "name_c"
0x9d137  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x9d13c  ldarg.0
0x9d13d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9d142  ldstr    aMscrmAutotoolt// "Mscrm.AutoToolTip"
0x9d147  ldstr    aTypeC// "type_c"
0x9d14c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x9d151  ret
```
