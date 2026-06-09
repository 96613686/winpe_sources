# Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignResponseRecordPageHandler::BuildOpenItems

- ea: `0x2450`
- end: `0x2474`
- name: `Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignResponseRecordPageHandler::BuildOpenItems`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x22e0`
- `0x2450`

## string_xrefs

- `0x2463`: `openNewItems`

## pseudocode

```c

```

## disassembly

```asm
0x2450  ldarg.0
0x2451  call     instance string Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignResponseRecordPageHandler::get_NewItemScript()
0x2456  callvirt instance int32 [mscorlib]System.String::get_Length()
0x245b  brfalse.s loc_2473
0x245d  ldarg.0
0x245e  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x2463  ldstr    aOpennewitems// "openNewItems"
0x2468  ldarg.0
0x2469  call     instance string Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignResponseRecordPageHandler::get_NewItemScript()
0x246e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(string, string)
0x2473  ret
```
