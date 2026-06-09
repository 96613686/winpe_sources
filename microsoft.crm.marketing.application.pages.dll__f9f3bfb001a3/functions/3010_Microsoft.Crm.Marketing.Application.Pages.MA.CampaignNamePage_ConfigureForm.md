# Microsoft.Crm.Marketing.Application.Pages.MA.CampaignNamePage::ConfigureForm

- ea: `0x3010`
- end: `0x3021`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.CampaignNamePage::ConfigureForm`
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
0x3010  ldarg.0
0x3011  ldstr    aMcMsgHeaderSpe// "MC_MSG_Header_SpecifyName"
0x3016  ldstr    aMcMsgResponse// "MC_MSG_Response"
0x301b  call     instance void Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignBasePage::SetTitleAndDescription(string titleId, string descriptionId)
0x3020  ret
```
