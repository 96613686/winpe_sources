# Microsoft.Crm.Marketing.Application.Components.EntityPageHeaders.CampaignResponseConfigHeader::UpdateConfigHeaderForEntityRecord

- ea: `0x1150`
- end: `0x116a`
- name: `Microsoft.Crm.Marketing.Application.Components.EntityPageHeaders.CampaignResponseConfigHeader::UpdateConfigHeaderForEntityRecord`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1150  ldarg.0
0x1151  ldarg.1
0x1152  ldarg.2
0x1153  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.EntityPageHeaders.ConfigHeaderBase::UpdateConfigHeaderForEntityRecord(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0x1158  ldarg.1
0x1159  ldstr    aCampaignrespon// "CAMPAIGNRESPONSE_STATE"
0x115e  ldarg.2
0x115f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_State()
0x1164  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x1169  ret
```
