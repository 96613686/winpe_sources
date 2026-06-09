# Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignAreaPageHandler::ConfigurePageHandler

- ea: `0x1220`
- end: `0x1237`
- name: `Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignAreaPageHandler::ConfigurePageHandler`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1220  ldarg.0
0x1221  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::ConfigurePageHandler()
0x1226  ldarg.0
0x1227  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::get_CurrentHeader()
0x122c  ldstr    aStaticMaCampai// "/_static/MA/campaign/campaign.js"
0x1231  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1236  ret
```
