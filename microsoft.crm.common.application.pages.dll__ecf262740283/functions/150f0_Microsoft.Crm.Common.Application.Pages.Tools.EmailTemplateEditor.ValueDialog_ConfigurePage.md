# Microsoft.Crm.Common.Application.Pages.Tools.EmailTemplateEditor.ValueDialog::ConfigurePage

- ea: `0x150f0`
- end: `0x15220`
- name: `Microsoft.Crm.Common.Application.Pages.Tools.EmailTemplateEditor.ValueDialog::ConfigurePage`
- size: `304`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x150f0`

## string_xrefs

- `0x1510c`: `/_common/styles/dialogs.css.aspx`
- `0x150fc`: `/_common/styles/select.css.aspx`
- `0x1513d`: `/_static/tools/emailtemplateeditor/scripts/datafields.js`
- `0x1514d`: `/_static/tools/emailtemplateeditor/scripts/objects.js`

## pseudocode

```c

```

## disassembly

```asm
0x150f0  ldarg.0
0x150f1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x150f6  ldarg.0
0x150f7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x150fc  ldstr    aCommonStylesSe// "/_common/styles/select.css.aspx"
0x15101  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x15106  ldarg.0
0x15107  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1510c  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x15111  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x15116  ldarg.0
0x15117  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1511c  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x15121  ldnull
0x15122  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x15127  ldarg.0
0x15128  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1512d  ldstr    aStaticFormsSel// "/_static/_forms/select.js"
0x15132  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x15137  ldarg.0
0x15138  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1513d  ldstr    aStaticToolsEma_0// "/_static/tools/emailtemplateeditor/scri"...
0x15142  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x15147  ldarg.0
0x15148  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1514d  ldstr    aStaticToolsEma_1// "/_static/tools/emailtemplateeditor/scri"...
0x15152  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x15157  ldarg.0
0x15158  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1515d  ldstr    aLocidSelectbox// "LOCID_SELECTBOX_BUTTON_ALT"
0x15162  ldarg.0
0x15163  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x15168  ldstr    aSelectButtonAl// "Select.Button.AltTag"
0x1516d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15172  ldc.i4.0
0x15173  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x15178  ldarg.0
0x15179  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x1517e  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x15183  stloc.0
0x15184  ldarg.0
0x15185  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1518a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1518f  ldstr    aMode// "mode"
0x15194  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x15199  ldstr    aAdd// "add"
0x1519e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x151a3  brfalse.s loc_151D2
0x151a5  ldloc.0
0x151a6  ldarg.0
0x151a7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x151ac  ldstr    aEmailTmplDlgDa// "Email_Tmpl_Dlg_Data_Fields_Add_Title"
0x151b1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x151b6  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x151bb  ldloc.0
0x151bc  ldarg.0
0x151bd  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x151c2  ldstr    aEmailTmplDlgDa_0// "Email_Tmpl_Dlg_Data_Fields_Add_Desc"
0x151c7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x151cc  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x151d1  ret
0x151d2  ldarg.0
0x151d3  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x151d8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x151dd  ldstr    aMode// "mode"
0x151e2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x151e7  ldstr    aEdit// "edit"
0x151ec  call     bool [mscorlib]System.String::op_Equality(string, string)
0x151f1  brfalse.s loc_1521F
0x151f3  ldloc.0
0x151f4  ldarg.0
0x151f5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x151fa  ldstr    aEmailTmplDlgDa_1// "Email_Tmpl_Dlg_Data_Fields_Edit_Title"
0x151ff  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15204  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x15209  ldloc.0
0x1520a  ldarg.0
0x1520b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x15210  ldstr    aEmailTmplDlgDa_2// "Email_Tmpl_Dlg_Data_Fields_Edit_Desc"
0x15215  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1521a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x1521f  ret
```
