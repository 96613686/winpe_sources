# Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignResponseRecordPageHandler::ConfigureHeaderHandler

- ea: `0x2350`
- end: `0x23f5`
- name: `Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignResponseRecordPageHandler::ConfigureHeaderHandler`
- size: `165`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x2350  ldarg.0
0x2351  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::ConfigureHeaderHandler()
0x2356  ldc.i4   0x1131
0x235b  call     class [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.EntityPageHeaders.IConfigHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.EntityPageHeaders.ConfigHeaderFactory::GetConfigHeader(int32)
0x2360  ldarg.0
0x2361  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x2366  ldarg.0
0x2367  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x236c  callvirt instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.EntityPageHeaders.IConfigHeader::ConfigHeader(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0x2371  ldarg.0
0x2372  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x2377  ldstr    aCampaignRespon_1// "CAMPAIGN_RESPONSE_CONVERTRESPONSE"
0x237c  ldc.i4.s 0x36
0x237e  box      [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId
0x2383  ldstr    aD// "D"
0x2388  call     instance string [mscorlib]System.Enum::ToString(string)
0x238d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x2392  ldarg.0
0x2393  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x2398  ldstr    aCampaignRespon_2// "CAMPAIGN_RESPONSE_DEACTIVATE"
0x239d  ldc.i4.5
0x239e  box      [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId
0x23a3  ldstr    aD// "D"
0x23a8  call     instance string [mscorlib]System.Enum::ToString(string)
0x23ad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x23b2  ldarg.0
0x23b3  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x23b8  ldstr    aCampaignLeadQu// "CAMPAIGN_LEAD_QUALIFY"
0x23bd  ldc.i4.s 0x10
0x23bf  box      [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId
0x23c4  ldstr    aD// "D"
0x23c9  call     instance string [mscorlib]System.Enum::ToString(string)
0x23ce  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x23d3  ldarg.0
0x23d4  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x23d9  ldstr    aCampaignLeadUn// "CAMPAIGN_LEAD_UNQUALIFY"
0x23de  ldc.i4.s 0xF
0x23e0  box      [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId
0x23e5  ldstr    aD// "D"
0x23ea  call     instance string [mscorlib]System.Enum::ToString(string)
0x23ef  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x23f4  ret
```
