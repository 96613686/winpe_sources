# Microsoft.Crm.Marketing.Application.Pages.MA.QuickCampaignPage::ConfigureForm

- ea: `0x3750`
- end: `0x3761`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.QuickCampaignPage::ConfigureForm`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3190`

## string_xrefs

- `0x3751`: `MC_MSG_Header_Welcome`

## pseudocode

```c

```

## disassembly

```asm
0x3750  ldarg.0
0x3751  ldstr    aMcMsgHeaderWel// "MC_MSG_Header_Welcome"
0x3756  ldstr    aMcMsgWizardpur// "MC_MSG_WizardPurpose"
0x375b  call     instance void Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignBasePage::SetTitleAndDescription(string titleId, string descriptionId)
0x3760  ret
```
