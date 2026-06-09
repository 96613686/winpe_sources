# Microsoft.Crm.Common.Web.Tools.EmailSignatureEditor.EmailSignatureEditorPage::ConfigureHeader

- ea: `0x93a0`
- end: `0x93ec`
- name: `Microsoft.Crm.Common.Web.Tools.EmailSignatureEditor.EmailSignatureEditorPage::ConfigureHeader`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x93e1`: `EmailSignatureService`
- `0x93bc`: `/_static/_common/scripts/CommandBarActions.js`

## pseudocode

```c

```

## disassembly

```asm
0x93a0  ldarg.0
0x93a1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager::ConfigureHeader()
0x93a6  ldarg.0
0x93a7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x93ac  ldstr    aControlsHtmlba// "/_controls/htmlbar/htmlbar.css.aspx"
0x93b1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x93b6  ldarg.0
0x93b7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x93bc  ldstr    aStaticCommonSc_2// "/_static/_common/scripts/CommandBarActi"...
0x93c1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x93c6  ldarg.0
0x93c7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x93cc  ldstr    aMscrmAutotoolt// "Mscrm.AutoToolTip"
0x93d1  ldstr    aTitleC// "title_c"
0x93d6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x93db  ldarg.0
0x93dc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x93e1  ldstr    aEmailsignature// "EmailSignatureService"
0x93e6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x93eb  ret
```
