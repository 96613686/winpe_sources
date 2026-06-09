# Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::ConfigurePage

- ea: `0x70f0`
- end: `0x71b3`
- name: `Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::ConfigurePage`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x7136`: `/tools/kbtemplateeditor/styles/kbtemplatemanager.css.aspx`
- `0x7106`: `/_common/styles/select.css.aspx`
- `0x70f6`: `/_nav/taskbox.css.aspx`
- `0x7146`: `/_static/tools/kbtemplateeditor/scripts/objects.js`
- `0x7156`: `/_static/tools/kbtemplateeditor/scripts/kbtemplateeditor.js`
- `0x7166`: `/_static/_common/scripts/CommandBarActions.js`
- `0x7181`: `Tools.KBTemplateEditor.kbtemplateeditor.aspx_save_alert`

## pseudocode

```c

```

## disassembly

```asm
0x70f0  ldarg.0
0x70f1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x70f6  ldstr    aNavTaskboxCssA// "/_nav/taskbox.css.aspx"
0x70fb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x7100  ldarg.0
0x7101  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7106  ldstr    aCommonStylesSe// "/_common/styles/select.css.aspx"
0x710b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x7110  ldarg.0
0x7111  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7116  ldstr    aControlsHtmlba// "/_controls/htmlbar/htmlbar.css.aspx"
0x711b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x7120  ldarg.0
0x7121  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7126  ldstr    aStaticToolsSys// "/_static/tools/systemcustomization/scri"...
0x712b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7130  ldarg.0
0x7131  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7136  ldstr    aToolsKbtemplat// "/tools/kbtemplateeditor/styles/kbtempla"...
0x713b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x7140  ldarg.0
0x7141  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7146  ldstr    aStaticToolsKbt// "/_static/tools/kbtemplateeditor/scripts"...
0x714b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7150  ldarg.0
0x7151  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7156  ldstr    aStaticToolsKbt_0// "/_static/tools/kbtemplateeditor/scripts"...
0x715b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7160  ldarg.0
0x7161  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7166  ldstr    aStaticCommonSc_5// "/_static/_common/scripts/CommandBarActi"...
0x716b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7170  ldarg.0
0x7171  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7176  ldstr    aLocidErrNosect// "LOCID_ERR_NOSECTIONS"
0x717b  ldarg.0
0x717c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7181  ldstr    aToolsKbtemplat_0// "Tools.KBTemplateEditor.kbtemplateeditor"...
0x7186  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x718b  ldc.i4.0
0x718c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7191  ldarg.0
0x7192  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7197  ldstr    aLocidSelectbox// "LOCID_SELECTBOX_BUTTON_ALT"
0x719c  ldarg.0
0x719d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x71a2  ldstr    aSelectButtonAl// "Select.Button.AltTag"
0x71a7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x71ac  ldc.i4.0
0x71ad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x71b2  ret
```
