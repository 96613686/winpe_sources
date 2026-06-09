# Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorProperties::ConfigurePage

- ea: `0x9860`
- end: `0x9898`
- name: `Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorProperties::ConfigurePage`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x986c`: `/_common/styles/select.css.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x9860  ldarg.0
0x9861  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x9866  ldarg.0
0x9867  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x986c  ldstr    aCommonStylesSe// "/_common/styles/select.css.aspx"
0x9871  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x9876  ldarg.0
0x9877  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x987c  ldstr    aLocidSelectbox// "LOCID_SELECTBOX_BUTTON_ALT"
0x9881  ldarg.0
0x9882  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9887  ldstr    aSelectButtonAl// "Select.Button.AltTag"
0x988c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9891  ldc.i4.0
0x9892  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9897  ret
```
