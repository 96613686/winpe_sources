# Microsoft.Crm.Common.Application.Pages.Tools.EmailTemplateEditor.DataFieldProperties::ConfigurePage

- ea: `0x14f90`
- end: `0x15091`
- name: `Microsoft.Crm.Common.Application.Pages.Tools.EmailTemplateEditor.DataFieldProperties::ConfigurePage`
- size: `257`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x14fbc`: `/_common/styles/dialogs.css.aspx`
- `0x14f9c`: `/_common/styles/select.css.aspx`
- `0x14fdd`: `/_static/tools/emailtemplateeditor/scripts/datafields.js`
- `0x14fed`: `/_static/tools/emailtemplateeditor/scripts/objects.js`
- `0x15008`: `Web.Tools.emailtemplateeditor.dialogs.datefieldproperties.aspx_66`
- `0x15029`: `Web.Tools.emailtemplateeditor.dialogs.datafieldproperties.aspx_75`
- `0x1506c`: `Web.Tools.emailtemplateeditor.dialogs.datafieldproperties.aspx_86`
- `0x15081`: `Web.Tools.emailtemplateeditor.dialogs.datafieldproperties.aspx_87`

## pseudocode

```c

```

## disassembly

```asm
0x14f90  ldarg.0
0x14f91  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x14f96  ldarg.0
0x14f97  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x14f9c  ldstr    aCommonStylesSe// "/_common/styles/select.css.aspx"
0x14fa1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x14fa6  ldarg.0
0x14fa7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x14fac  ldstr    aNavTabsCssAspx// "/_nav/tabs.css.aspx"
0x14fb1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x14fb6  ldarg.0
0x14fb7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x14fbc  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x14fc1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x14fc6  ldarg.0
0x14fc7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x14fcc  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x14fd1  ldnull
0x14fd2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x14fd7  ldarg.0
0x14fd8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x14fdd  ldstr    aStaticToolsEma_0// "/_static/tools/emailtemplateeditor/scri"...
0x14fe2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x14fe7  ldarg.0
0x14fe8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x14fed  ldstr    aStaticToolsEma_1// "/_static/tools/emailtemplateeditor/scri"...
0x14ff2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x14ff7  ldarg.0
0x14ff8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x14ffd  ldstr    aLocidEmailedIn// "LOCID_EMAILED_INVALIDCHARS"
0x15002  ldarg.0
0x15003  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x15008  ldstr    aWebToolsEmailt// "Web.Tools.emailtemplateeditor.dialogs.d"...
0x1500d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15012  ldc.i4.0
0x15013  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x15018  ldarg.0
0x15019  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1501e  ldstr    aLocidEmailedNo// "LOCID_EMAILED_NODATAFIELDS"
0x15023  ldarg.0
0x15024  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x15029  ldstr    aWebToolsEmailt_0// "Web.Tools.emailtemplateeditor.dialogs.d"...
0x1502e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15033  ldc.i4.0
0x15034  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x15039  ldarg.0
0x1503a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1503f  ldstr    aLocidSelectbox// "LOCID_SELECTBOX_BUTTON_ALT"
0x15044  ldarg.0
0x15045  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1504a  ldstr    aSelectButtonAl// "Select.Button.AltTag"
0x1504f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15054  ldc.i4.0
0x15055  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1505a  ldarg.0
0x1505b  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x15060  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x15065  dup
0x15066  ldarg.0
0x15067  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1506c  ldstr    aWebToolsEmailt_1// "Web.Tools.emailtemplateeditor.dialogs.d"...
0x15071  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15076  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x1507b  ldarg.0
0x1507c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x15081  ldstr    aWebToolsEmailt_2// "Web.Tools.emailtemplateeditor.dialogs.d"...
0x15086  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1508b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x15090  ret
```
