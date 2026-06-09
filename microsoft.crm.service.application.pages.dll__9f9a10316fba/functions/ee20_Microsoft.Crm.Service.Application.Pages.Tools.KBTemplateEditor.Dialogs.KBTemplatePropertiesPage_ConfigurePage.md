# Microsoft.Crm.Service.Application.Pages.Tools.KBTemplateEditor.Dialogs.KBTemplatePropertiesPage::ConfigurePage

- ea: `0xee20`
- end: `0xef30`
- name: `Microsoft.Crm.Service.Application.Pages.Tools.KBTemplateEditor.Dialogs.KBTemplatePropertiesPage::ConfigurePage`
- size: `272`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0xeead`: `/_static/_common/styles/AutoToolTip.js`
- `0xee4c`: `/_common/styles/dialogs.css.aspx`
- `0xee5c`: `/tools/kbtemplateeditor/styles/kbtemplatemanager.css.aspx`
- `0xee7d`: `/_common/styles/select.css.aspx`
- `0xee8d`: `/_static/tools/kbtemplateeditor/scripts/objects.js`
- `0xee9d`: `/_static/tools/kbtemplateeditor/scripts/dialogs.js`
- `0xeee9`: `Web.Tools.KBTemplateEditor.Dialogs.kbtemplateproperties.aspx_29`
- `0xef25`: `templatetitle_c`

## pseudocode

```c

```

## disassembly

```asm
0xee20  ldarg.0
0xee21  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0xee26  ldarg.0
0xee27  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xee2c  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
0xee31  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xee36  ldarg.0
0xee37  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xee3c  ldstr    aFormsControlsC// "/_forms/controls/controls.css.aspx"
0xee41  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xee46  ldarg.0
0xee47  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xee4c  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0xee51  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xee56  ldarg.0
0xee57  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xee5c  ldstr    aToolsKbtemplat// "/tools/kbtemplateeditor/styles/kbtempla"...
0xee61  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xee66  ldarg.0
0xee67  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xee6c  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0xee71  ldnull
0xee72  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0xee77  ldarg.0
0xee78  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xee7d  ldstr    aCommonStylesSe// "/_common/styles/select.css.aspx"
0xee82  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xee87  ldarg.0
0xee88  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xee8d  ldstr    aStaticToolsKbt// "/_static/tools/kbtemplateeditor/scripts"...
0xee92  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xee97  ldarg.0
0xee98  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xee9d  ldstr    aStaticToolsKbt_1// "/_static/tools/kbtemplateeditor/scripts"...
0xeea2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xeea7  ldarg.0
0xeea8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xeead  ldstr    aStaticCommonSt// "/_static/_common/styles/AutoToolTip.js"
0xeeb2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xeeb7  ldarg.0
0xeeb8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xeebd  ldstr    aLocidExceededM// "LOCID_EXCEEDED_MAX_CHARS_MASK"
0xeec2  ldarg.0
0xeec3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xeec8  ldstr    aWebFormsStyles// "Web._forms.styles.TEXTAREA.htc_11_0"
0xeecd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xeed2  ldc.i4.0
0xeed3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xeed8  ldarg.0
0xeed9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xeede  ldstr    aLocidKbtedEnte// "LOCID_KBTED_ENTERARTICLETITLE"
0xeee3  ldarg.0
0xeee4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xeee9  ldstr    aWebToolsKbtemp_1// "Web.Tools.KBTemplateEditor.Dialogs.kbte"...
0xeeee  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xeef3  ldc.i4.0
0xeef4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xeef9  ldarg.0
0xeefa  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xeeff  ldstr    aLocidSelectbox// "LOCID_SELECTBOX_BUTTON_ALT"
0xef04  ldarg.0
0xef05  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xef0a  ldstr    aSelectButtonAl// "Select.Button.AltTag"
0xef0f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xef14  ldc.i4.0
0xef15  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xef1a  ldarg.0
0xef1b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xef20  ldstr    aMscrmAutotoolt// "Mscrm.AutoToolTip"
0xef25  ldstr    aTemplatetitleC// "templatetitle_c"
0xef2a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0xef2f  ret
```
