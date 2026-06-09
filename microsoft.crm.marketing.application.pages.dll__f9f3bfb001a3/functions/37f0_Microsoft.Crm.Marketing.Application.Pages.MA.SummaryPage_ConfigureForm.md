# Microsoft.Crm.Marketing.Application.Pages.MA.SummaryPage::ConfigureForm

- ea: `0x37f0`
- end: `0x3801`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.SummaryPage::ConfigureForm`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3190`

## string_xrefs

- `0x37f1`: `MC_MSG_Header_Complete`
- `0x37f6`: `MC_MSG_StepsCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x37f0  ldarg.0
0x37f1  ldstr    aMcMsgHeaderCom// "MC_MSG_Header_Complete"
0x37f6  ldstr    aMcMsgStepscomp// "MC_MSG_StepsCompleted"
0x37fb  call     instance void Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignBasePage::SetTitleAndDescription(string titleId, string descriptionId)
0x3800  ret
```
