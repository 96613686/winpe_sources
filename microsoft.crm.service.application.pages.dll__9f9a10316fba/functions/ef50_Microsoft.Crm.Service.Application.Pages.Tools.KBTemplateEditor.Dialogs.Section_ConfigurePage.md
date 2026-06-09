# Microsoft.Crm.Service.Application.Pages.Tools.KBTemplateEditor.Dialogs.Section::ConfigurePage

- ea: `0xef50`
- end: `0xf0b1`
- name: `Microsoft.Crm.Service.Application.Pages.Tools.KBTemplateEditor.Dialogs.Section::ConfigurePage`
- size: `353`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xef50`

## string_xrefs

- `0xefbd`: `/_static/_common/styles/AutoToolTip.js`
- `0xef7c`: `/_common/styles/dialogs.css.aspx`
- `0xef8c`: `/tools/kbtemplateeditor/styles/kbtemplatemanager.css.aspx`
- `0xefad`: `/_static/tools/kbtemplateeditor/scripts/objects.js`
- `0xeff9`: `Web.Tools.KBTemplateEditor.Dialogs.section.aspx_64`
- `0xf05e`: `Title_Add_New_Section_Art_Templ_Dlg`
- `0xf074`: `Subtitle_Add_New_Section_Art_Templ_Dlg`
- `0xf08b`: `Title_Section_Properties_Art_Templ_Dlg`
- `0xf0a1`: `Subtitle_Section_Properties_Art_Templ_Dlg`

## pseudocode

```c

```

## disassembly

```asm
0xef50  ldarg.0
0xef51  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0xef56  ldarg.0
0xef57  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xef5c  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
0xef61  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xef66  ldarg.0
0xef67  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xef6c  ldstr    aFormsControlsC// "/_forms/controls/controls.css.aspx"
0xef71  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xef76  ldarg.0
0xef77  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xef7c  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0xef81  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xef86  ldarg.0
0xef87  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xef8c  ldstr    aToolsKbtemplat// "/tools/kbtemplateeditor/styles/kbtempla"...
0xef91  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xef96  ldarg.0
0xef97  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xef9c  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0xefa1  ldnull
0xefa2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0xefa7  ldarg.0
0xefa8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xefad  ldstr    aStaticToolsKbt// "/_static/tools/kbtemplateeditor/scripts"...
0xefb2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xefb7  ldarg.0
0xefb8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xefbd  ldstr    aStaticCommonSt// "/_static/_common/styles/AutoToolTip.js"
0xefc2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xefc7  ldarg.0
0xefc8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xefcd  ldstr    aLocidExceededM// "LOCID_EXCEEDED_MAX_CHARS_MASK"
0xefd2  ldarg.0
0xefd3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xefd8  ldstr    aWebFormsStyles// "Web._forms.styles.TEXTAREA.htc_11_0"
0xefdd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xefe2  ldc.i4.0
0xefe3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xefe8  ldarg.0
0xefe9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xefee  ldstr    aLocidKbtedEnte_0// "LOCID_KBTED_ENTERSECTIONTITLE"
0xeff3  ldarg.0
0xeff4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xeff9  ldstr    aWebToolsKbtemp_2// "Web.Tools.KBTemplateEditor.Dialogs.sect"...
0xeffe  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf003  ldc.i4.0
0xf004  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf009  ldarg.0
0xf00a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf00f  ldstr    aMscrmAutotoolt// "Mscrm.AutoToolTip"
0xf014  ldstr    aTitleC// "title_c"
0xf019  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0xf01e  ldarg.0
0xf01f  ldarg.0
0xf020  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf025  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf02a  ldstr    aMode// "mode"
0xf02f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf034  ldstr    aNew// "new"
0xf039  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf03e  stfld    bool Microsoft.Crm.Service.Application.Pages.Tools.KBTemplateEditor.Dialogs.Section::isNew
0xf043  ldarg.0
0xf044  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0xf049  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0xf04e  stloc.0
0xf04f  ldarg.0
0xf050  ldfld    bool Microsoft.Crm.Service.Application.Pages.Tools.KBTemplateEditor.Dialogs.Section::isNew
0xf055  brfalse.s loc_F084
0xf057  ldloc.0
0xf058  ldarg.0
0xf059  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf05e  ldstr    aTitleAddNewSec// "Title_Add_New_Section_Art_Templ_Dlg"
0xf063  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf068  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0xf06d  ldloc.0
0xf06e  ldarg.0
0xf06f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf074  ldstr    aSubtitleAddNew// "Subtitle_Add_New_Section_Art_Templ_Dlg"
0xf079  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf07e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0xf083  ret
0xf084  ldloc.0
0xf085  ldarg.0
0xf086  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf08b  ldstr    aTitleSectionPr// "Title_Section_Properties_Art_Templ_Dlg"
0xf090  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf095  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0xf09a  ldloc.0
0xf09b  ldarg.0
0xf09c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf0a1  ldstr    aSubtitleSectio// "Subtitle_Section_Properties_Art_Templ_D"...
0xf0a6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf0ab  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0xf0b0  ret
```
