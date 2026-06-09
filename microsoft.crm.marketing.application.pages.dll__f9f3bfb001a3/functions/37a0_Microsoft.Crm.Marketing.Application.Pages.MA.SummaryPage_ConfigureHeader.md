# Microsoft.Crm.Marketing.Application.Pages.MA.SummaryPage::ConfigureHeader

- ea: `0x37a0`
- end: `0x37e4`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.SummaryPage::ConfigureHeader`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3130`

## string_xrefs

- `0x37b8`: `LOCID_MC_BTN_CREATE`
- `0x37c3`: `MC_Button_Create`

## pseudocode

```c

```

## disassembly

```asm
0x37a0  ldarg.0
0x37a1  call     instance void Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignBasePage::ConfigureHeader()
0x37a6  ldarg.0
0x37a7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x37ac  ldc.i4.1
0x37ad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0x37b2  ldarg.0
0x37b3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x37b8  ldstr    aLocidMcBtnCrea// "LOCID_MC_BTN_CREATE"
0x37bd  ldarg.0
0x37be  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x37c3  ldstr    aMcButtonCreate// "MC_Button_Create"
0x37c8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x37cd  ldc.i4.0
0x37ce  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x37d3  ldarg.0
0x37d4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x37d9  ldstr    aStaticControls// "/_static/_controls/lookup/lookup.js"
0x37de  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x37e3  ret
```
