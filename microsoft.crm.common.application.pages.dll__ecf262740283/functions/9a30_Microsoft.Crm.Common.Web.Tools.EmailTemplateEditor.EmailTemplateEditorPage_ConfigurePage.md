# Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::ConfigurePage

- ea: `0x9a30`
- end: `0x9b76`
- name: `Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::ConfigurePage`
- size: `326`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x9a66`: `/_static/_common/scripts/CommandBarActions.js`
- `0x9a56`: `/_static/tools/emailtemplateeditor/scripts/emailtemplateeditor.js`
- `0x9b05`: `EmailTemplate_Delete_NoDataSlugSelected`
- `0x9b26`: `EmailTemplate_SlugInsert_FieldNotSupportedSlug`

## pseudocode

```c

```

## disassembly

```asm
0x9a30  ldarg.0
0x9a31  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::attachmentGrid
0x9a36  ldstr    a270de234E46948// "{270DE234-E469-4806-9C7E-8D94901CD521}"
0x9a3b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ViewId(string)
0x9a40  ldarg.0
0x9a41  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9a46  ldstr    aControlsHtmlba// "/_controls/htmlbar/htmlbar.css.aspx"
0x9a4b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x9a50  ldarg.0
0x9a51  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9a56  ldstr    aStaticToolsEma// "/_static/tools/emailtemplateeditor/scri"...
0x9a5b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9a60  ldarg.0
0x9a61  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9a66  ldstr    aStaticCommonSc_2// "/_static/_common/scripts/CommandBarActi"...
0x9a6b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9a70  ldarg.0
0x9a71  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9a76  ldstr    aLocidEtmplSubj// "LOCID_ETMPL_SUBJECT_REQUIRED"
0x9a7b  ldarg.0
0x9a7c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9a81  ldstr    aMsgSubjectRequ// "Msg_Subject_Required"
0x9a86  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a8b  ldc.i4.0
0x9a8c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9a91  ldarg.0
0x9a92  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9a97  ldstr    aLocidEtmplSubj_0// "LOCID_ETMPL_SUBJECT_TOO_LONG"
0x9a9c  ldarg.0
0x9a9d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9aa2  ldstr    aMsgSubjectTooL// "Msg_Subject_Too_Long"
0x9aa7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9aac  ldc.i4.0
0x9aad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9ab2  ldarg.0
0x9ab3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9ab8  ldstr    aLocidEtmplsubj// "LOCID_ETMPLSUBJECTDATAFIELDWARN"
0x9abd  ldarg.0
0x9abe  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9ac3  ldstr    aMsgSubjectData// "Msg_Subject_DataField_Warning"
0x9ac8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9acd  ldc.i4.0
0x9ace  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9ad3  ldarg.0
0x9ad4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9ad9  ldstr    aLocidEtmplsubj_0// "LOCID_ETMPLSUBJECTNOFORMAT"
0x9ade  ldarg.0
0x9adf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9ae4  ldstr    aMsgFormattingn// "Msg_FormattingNotSupportedInSubject"
0x9ae9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9aee  ldc.i4.0
0x9aef  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9af4  ldarg.0
0x9af5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9afa  ldstr    aLocidNodataslu// "LOCID_NODATASLUGSELECTED"
0x9aff  ldarg.0
0x9b00  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9b05  ldstr    aEmailtemplateD// "EmailTemplate_Delete_NoDataSlugSelected"
0x9b0a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9b0f  ldc.i4.0
0x9b10  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9b15  ldarg.0
0x9b16  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9b1b  ldstr    aLocidFieldnots// "LOCID_FIELDNOTSUPPORTEDSLUG"
0x9b20  ldarg.0
0x9b21  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9b26  ldstr    aEmailtemplateS// "EmailTemplate_SlugInsert_FieldNotSuppor"...
0x9b2b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9b30  ldc.i4.0
0x9b31  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9b36  ldarg.0
0x9b37  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9b3c  ldstr    aMscrmAutotoolt// "Mscrm.AutoToolTip"
0x9b41  ldstr    aTypeC// "type_c"
0x9b46  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x9b4b  ldarg.0
0x9b4c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9b51  ldstr    aMscrmAutotoolt// "Mscrm.AutoToolTip"
0x9b56  ldstr    aTitleC// "title_c"
0x9b5b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x9b60  ldarg.0
0x9b61  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9b66  ldstr    aMscrmAutotoolt// "Mscrm.AutoToolTip"
0x9b6b  ldstr    aSubjectC// "subject_c"
0x9b70  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x9b75  ret
```
