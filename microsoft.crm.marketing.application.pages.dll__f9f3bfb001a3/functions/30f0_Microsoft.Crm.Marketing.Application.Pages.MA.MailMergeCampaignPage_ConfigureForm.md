# Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeCampaignPage::ConfigureForm

- ea: `0x30f0`
- end: `0x3101`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeCampaignPage::ConfigureForm`
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
0x30f0  ldarg.0
0x30f1  ldstr    aMcMsgHeaderMai// "MC_MSG_Header_MailMergeContent"
0x30f6  ldstr    aMcMsgDetailsMa// "MC_MSG_Details_MailMerge"
0x30fb  call     instance void Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignBasePage::SetTitleAndDescription(string titleId, string descriptionId)
0x3100  ret
```
