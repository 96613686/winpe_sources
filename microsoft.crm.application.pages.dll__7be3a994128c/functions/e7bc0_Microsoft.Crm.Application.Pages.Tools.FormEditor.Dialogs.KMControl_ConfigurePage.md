# Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.KMControl::ConfigurePage

- ea: `0xe7bc0`
- end: `0xe84c4`
- name: `Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.KMControl::ConfigurePage`
- size: `2308`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0xe7bc0`
- `0xe8530`
- `0xe9360`
- `0xe94e0`
- `0xe95f0`

## string_xrefs

- `0xe7be6`: `/_common/styles/dialogs.css.aspx`
- `0xe7cac`: `/_static/_common/styles/AutoToolTip.js`
- `0xe7bc6`: `/_common/styles/select.css.aspx`
- `0xe7de5`: `LOCID_ACTIONS_COPY`
- `0xe7df0`: `KMControl.SearchKMArticles.CopyArticleIconAltText`

## pseudocode

```c

```

## disassembly

```asm
0xe7bc0  ldarg.0
0xe7bc1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7bc6  ldstr    aCommonStylesSe// "/_common/styles/select.css.aspx"
0xe7bcb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xe7bd0  ldarg.0
0xe7bd1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7bd6  ldstr    aNavTabsCssAspx// "/_nav/tabs.css.aspx"
0xe7bdb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xe7be0  ldarg.0
0xe7be1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7be6  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0xe7beb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xe7bf0  ldarg.0
0xe7bf1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7bf6  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0xe7bfb  ldnull
0xe7bfc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0xe7c01  ldarg.0
0xe7c02  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7c07  ldstr    aMscrmAutotoolt// "Mscrm.AutoToolTip"
0xe7c0c  ldstr    aIconresourceC// "iconresource_c"
0xe7c11  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0xe7c16  ldarg.0
0xe7c17  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7c1c  ldstr    aToolsFormedito_5// "/tools/formeditor/styles/dialogs.css.as"...
0xe7c21  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xe7c26  ldarg.0
0xe7c27  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7c2c  ldstr    aFormsControlsC// "/_forms/controls/controls.css.aspx"
0xe7c31  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xe7c36  ldarg.0
0xe7c37  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7c3c  ldstr    aToolsFieldsele// "/_tools/fieldselect/fieldselect.css.asp"...
0xe7c41  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xe7c46  ldarg.0
0xe7c47  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7c4c  ldstr    aStaticFormsSel// "/_static/_forms/select.js"
0xe7c51  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe7c56  ldarg.0
0xe7c57  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7c5c  ldstr    aStaticToolsFor// "/_static/tools/formeditor/scripts/objec"...
0xe7c61  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe7c66  ldarg.0
0xe7c67  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7c6c  ldstr    aStaticToolsFor_3// "/_static/tools/formeditor/scripts/dialo"...
0xe7c71  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe7c76  ldarg.0
0xe7c77  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7c7c  ldstr    aStaticToolsFor_1// "/_static/tools/formeditor/scripts/util."...
0xe7c81  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe7c86  ldarg.0
0xe7c87  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7c8c  ldstr    aStaticToolsFor_0// "/_static/tools/formeditor/scripts/field"...
0xe7c91  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe7c96  ldarg.0
0xe7c97  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7c9c  ldstr    aStaticToolsFie// "/_static/_tools/fieldselect/fieldselect"...
0xe7ca1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe7ca6  ldarg.0
0xe7ca7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7cac  ldstr    aStaticCommonSt// "/_static/_common/styles/AutoToolTip.js"
0xe7cb1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe7cb6  ldarg.0
0xe7cb7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7cbc  ldstr    aLocidEnterSear// "LOCID_ENTER_SEARCHWIDGET_NAME"
0xe7cc1  ldarg.0
0xe7cc2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe7cc7  ldstr    aWebToolsFormed_102// "Web.Tools.FormEditor.Dialogs.searchwidg"...
0xe7ccc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe7cd1  ldc.i4.0
0xe7cd2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe7cd7  ldarg.0
0xe7cd8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7cdd  ldstr    aLocidEnterSear_0// "LOCID_ENTER_SEARCHWIDGET_LABEL"
0xe7ce2  ldarg.0
0xe7ce3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe7ce8  ldstr    aWebToolsFormed_103// "Web.Tools.FormEditor.Dialogs.searchwidg"...
0xe7ced  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe7cf2  ldc.i4.0
0xe7cf3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe7cf8  ldarg.0
0xe7cf9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7cfe  ldstr    aLocidAlphanume// "LOCID_ALPHANUMERIC_ONLY"
0xe7d03  ldarg.0
0xe7d04  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe7d09  ldstr    aFormeditorDial// "Formeditor_Dialogs_SearchWidget_Invalid"...
0xe7d0e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe7d13  ldc.i4.0
0xe7d14  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe7d19  ldarg.0
0xe7d1a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7d1f  ldstr    aLocidValidRows// "LOCID_VALID_ROWSPERPAGE"
0xe7d24  ldarg.0
0xe7d25  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe7d2a  ldstr    aFormeditorDial_17// "Formeditor_Dialogs_SearchWidget_Invalid"...
0xe7d2f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe7d34  ldc.i4.0
0xe7d35  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe7d3a  ldarg.0
0xe7d3b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7d40  ldstr    aLocidIdInUse// "LOCID_ID_IN_USE"
0xe7d45  ldarg.0
0xe7d46  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe7d4b  ldstr    aWebToolsFormed_64// "Web.Tools.FormEditor.Dialogs.iframe.asp"...
0xe7d50  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe7d55  ldc.i4.0
0xe7d56  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe7d5b  ldarg.0
0xe7d5c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7d61  ldstr    aLocidViewsShow// "LOCID_VIEWS_SHOW_ALL"
0xe7d66  ldarg.0
0xe7d67  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe7d6c  ldstr    aWebToolsFormed_37// "Web.Tools.FormEditor.Dialogs.section.Ar"...
0xe7d71  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe7d76  ldc.i4.0
0xe7d77  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe7d7c  ldarg.0
0xe7d7d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7d82  ldstr    aLocidViewsShow_0// "LOCID_VIEWS_SHOW_SELECTED"
0xe7d87  ldarg.0
0xe7d88  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe7d8d  ldstr    aWebToolsFormed_38// "Web.Tools.FormEditor.Dialogs.section.Ar"...
0xe7d92  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe7d97  ldc.i4.0
0xe7d98  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe7d9d  ldarg.0
0xe7d9e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7da3  ldstr    aLocidActionsAs// "LOCID_ACTIONS_ASSOCIATE"
0xe7da8  ldarg.0
0xe7da9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe7dae  ldstr    aKmcontrolSearc_0// "KMControl.SearchKMArticles.AssociateArt"...
0xe7db3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe7db8  ldc.i4.0
0xe7db9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe7dbe  ldarg.0
0xe7dbf  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7dc4  ldstr    aLocidActionsDi// "LOCID_ACTIONS_DISASSOCIATE"
0xe7dc9  ldarg.0
0xe7dca  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe7dcf  ldstr    aKmcontrolSearc_1// "KMControl.SearchKMArticles.Disassociate"...
0xe7dd4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe7dd9  ldc.i4.0
0xe7dda  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe7ddf  ldarg.0
0xe7de0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7de5  ldstr    aLocidActionsCo// "LOCID_ACTIONS_COPY"
0xe7dea  ldarg.0
0xe7deb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe7df0  ldstr    aKmcontrolSearc_2// "KMControl.SearchKMArticles.CopyArticleI"...
0xe7df5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe7dfa  ldc.i4.0
0xe7dfb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe7e00  ldarg.0
0xe7e01  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7e06  ldstr    aLocidActionsEm// "LOCID_ACTIONS_EMAIL"
0xe7e0b  ldarg.0
0xe7e0c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe7e11  ldstr    aKmcontrolSearc_3// "KMControl.SearchKMArticles.EmailArticle"...
0xe7e16  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe7e1b  ldc.i4.0
0xe7e1c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe7e21  ldarg.0
0xe7e22  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7e27  ldstr    aLocidActionsEm_0// "LOCID_ACTIONS_EMAILCONTENT"
0xe7e2c  ldarg.0
0xe7e2d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe7e32  ldstr    aKmcontrolSearc_4// "KMControl.SearchKMArticles.EmailArticle"...
0xe7e37  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe7e3c  ldc.i4.0
0xe7e3d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe7e42  ldarg.0
0xe7e43  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7e48  ldstr    aLocidActionsPo// "LOCID_ACTIONS_POPOUT"
0xe7e4d  ldarg.0
0xe7e4e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe7e53  ldstr    aKmcontrolSearc_5// "KMControl.SearchKMArticles.PopOutAltTex"...
0xe7e58  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe7e5d  ldc.i4.0
0xe7e5e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe7e63  ldarg.0
0xe7e64  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7e69  ldstr    aLocidEnterIcon// "LOCID_ENTER_ICON"
0xe7e6e  ldarg.0
0xe7e6f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe7e74  ldstr    aWebToolsFormed_95// "Web.Tools.FormEditor.Dialogs.subform.as"...
0xe7e79  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe7e7e  ldc.i4.0
0xe7e7f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe7e84  ldarg.0
0xe7e85  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7e8a  ldstr    aLocidIconTypeN// "LOCID_ICON_TYPE_NOT_VALID"
0xe7e8f  ldarg.0
0xe7e90  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe7e95  ldstr    aWebToolsFormed_96// "Web.Tools.FormEditor.Dialogs.subform.as"...
0xe7e9a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe7e9f  ldc.i4.0
0xe7ea0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe7ea5  ldarg.0
0xe7ea6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7eab  ldstr    aLocidDefaultla// "LOCID_DEFAULTLANGUAGE_NOTACTIVE"
0xe7eb0  ldarg.0
0xe7eb1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe7eb6  ldstr    aWebToolsFormed_104// "Web.Tools.FormEditor.Dialogs.section.Ar"...
0xe7ebb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe7ec0  ldc.i4.0
0xe7ec1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe7ec6  ldarg.0
0xe7ec7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe7ecc  ldstr    aWebToolsFormed_36// "Web.Tools.FormEditor.Ribbon.Button.SubG"...
0xe7ed1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe7ed6  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xe7edb  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0xe7ee0  stloc.0
0xe7ee1  ldarg.0
0xe7ee2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe7ee7  ldstr    aLocidFormedSub// "LOCID_FORMED_SUBGRID_COLSPAN"
0xe7eec  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xe7ef1  ldarg.0
0xe7ef2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe7ef7  ldstr    aAddcolumnCapti// "AddColumn_Caption"
0xe7efc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe7f01  ldc.i4.1
0xe7f02  newarr   [mscorlib]System.Object
0xe7f07  dup
0xe7f08  ldc.i4.0
0xe7f09  ldloc.0
0xe7f0a  stelem.ref
0xe7f0b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe7f10  ldc.i4.0
0xe7f11  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe7f16  ldarg.0
0xe7f17  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTabBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmTabBar
0xe7f1c  ldarg.0
0xe7f1d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe7f22  ldstr    aTabLabelDispla// "Tab_Label_Display"
0xe7f27  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe7f2c  ldstr    aTab0// "tab0"
0xe7f31  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TabBar::AddTab(string, string)
0xe7f36  ldarg.0
0xe7f37  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTabBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmTabBar
0xe7f3c  ldarg.0
0xe7f3d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe7f42  ldstr    aTabLabelFormat// "Tab_Label_Formatting"
0xe7f47  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe7f4c  ldstr    aTab1// "tab1"
0xe7f51  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TabBar::AddTab(string, string)
0xe7f56  ldarg.0
0xe7f57  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.KMControl::displayLabel
0xe7f5c  ldarg.0
0xe7f5d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe7f62  ldstr    aWebToolsFormed_105// "Web.Tools.FormEditor.Dialogs.section.Ar"...
0xe7f67  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe7f6c  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0xe7f71  ldarg.0
0xe7f72  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.KMControl::allowChangeFiltersLabel
0xe7f77  ldarg.0
0xe7f78  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe7f7d  ldstr    aWebToolsFormed_39// "Web.Tools.FormEditor.Dialogs.section.Ar"...
0xe7f82  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe7f87  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0xe7f8c  ldarg.0
0xe7f8d  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.KMControl::allowChangeFiltersLabel
0xe7f92  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xe7f97  ldstr    aTitle// "title"
0xe7f9c  ldarg.0
0xe7f9d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe7fa2  ldstr    aWebToolsFormed_40// "Web.Tools.FormEditor.Dialogs.section.Ar"...
0xe7fa7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe7fac  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xe7fb1  ldarg.0
0xe7fb2  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.KMControl::enableAutomaticSuggestionsLabel
0xe7fb7  ldarg.0
0xe7fb8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe7fbd  ldstr    aWebToolsFormed_41// "Web.Tools.FormEditor.Dialogs.section.Ar"...
0xe7fc2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe7fc7  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0xe7fcc  ldarg.0
0xe7fcd  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.KMControl::enableAutomaticSuggestionsLabel
0xe7fd2  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xe7fd7  ldstr    aTitle// "title"
0xe7fdc  ldarg.0
0xe7fdd  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe7fe2  ldstr    aWebToolsFormed_42// "Web.Tools.FormEditor.Dialogs.section.Ar"...
0xe7fe7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe7fec  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xe7ff1  ldarg.0
0xe7ff2  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.KMControl::showLanguageFilterLabel
0xe7ff7  ldarg.0
0xe7ff8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe7ffd  ldstr    aWebToolsFormed_43// "Web.Tools.FormEditor.Dialogs.section.Ar"...
0xe8002  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe8007  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0xe800c  ldarg.0
0xe800d  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.KMControl::showLanguageFilterLabel
0xe8012  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xe8017  ldstr    aTitle// "title"
0xe801c  ldarg.0
0xe801d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe8022  ldstr    aWebToolsFormed_44// "Web.Tools.FormEditor.Dialogs.section.Ar"...
0xe8027  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
  ... truncated ...
```
