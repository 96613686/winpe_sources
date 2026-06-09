# Microsoft.Crm.Marketing.Application.Pages.MA.FormActivityPage::ConfigureForm

- ea: `0x3080`
- end: `0x3091`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.FormActivityPage::ConfigureForm`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3190`

## pseudocode

```c

```

## disassembly

```asm
0x3080  ldarg.0
0x3081  ldstr    aMcMsgHeaderAct// "MC_MSG_Header_ActivityContent"
0x3086  ldstr    aMcMsgDetails// "MC_MSG_Details"
0x308b  call     instance void Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignBasePage::SetTitleAndDescription(string titleId, string descriptionId)
0x3090  ret
```
