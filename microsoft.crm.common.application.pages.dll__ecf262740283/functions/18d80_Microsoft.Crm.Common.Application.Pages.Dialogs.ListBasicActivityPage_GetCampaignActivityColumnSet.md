# Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::GetCampaignActivityColumnSet

- ea: `0x18d80`
- end: `0x18d97`
- name: `Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::GetCampaignActivityColumnSet`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x19500`

## string_xrefs

- `0x18d90`: `scheduledend`

## pseudocode

```c

```

## disassembly

```asm
0x18d80  ldc.i4.2
0x18d81  newarr   [mscorlib]System.String
0x18d86  dup
0x18d87  ldc.i4.0
0x18d88  ldstr    aRegardingobjec_0// "regardingobjectid"
0x18d8d  stelem.ref
0x18d8e  dup
0x18d8f  ldc.i4.1
0x18d90  ldstr    aScheduledend// "scheduledend"
0x18d95  stelem.ref
0x18d96  ret
```
