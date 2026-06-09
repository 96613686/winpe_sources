# Microsoft.Crm.Common.Web.Activities.CreateDialog::ConfigurePage

- ea: `0xb5d0`
- end: `0xb5e1`
- name: `Microsoft.Crm.Common.Web.Activities.CreateDialog::ConfigurePage`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0xb5d6`: `/_static/_common/scripts/newdialog.js`

## pseudocode

```c

```

## disassembly

```asm
0xb5d0  ldarg.0
0xb5d1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb5d6  ldstr    aStaticCommonSc_1// "/_static/_common/scripts/newdialog.js"
0xb5db  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb5e0  ret
```
