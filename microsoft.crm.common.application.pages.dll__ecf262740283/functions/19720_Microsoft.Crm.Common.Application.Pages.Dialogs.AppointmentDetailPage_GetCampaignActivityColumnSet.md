# Microsoft.Crm.Common.Application.Pages.Dialogs.AppointmentDetailPage::GetCampaignActivityColumnSet

- ea: `0x19720`
- end: `0x1973f`
- name: `Microsoft.Crm.Common.Application.Pages.Dialogs.AppointmentDetailPage::GetCampaignActivityColumnSet`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x19730`: `scheduledstart`
- `0x19738`: `scheduledend`

## pseudocode

```c

```

## disassembly

```asm
0x19720  ldc.i4.3
0x19721  newarr   [mscorlib]System.String
0x19726  dup
0x19727  ldc.i4.0
0x19728  ldstr    aRegardingobjec_0// "regardingobjectid"
0x1972d  stelem.ref
0x1972e  dup
0x1972f  ldc.i4.1
0x19730  ldstr    aScheduledstart// "scheduledstart"
0x19735  stelem.ref
0x19736  dup
0x19737  ldc.i4.2
0x19738  ldstr    aScheduledend// "scheduledend"
0x1973d  stelem.ref
0x1973e  ret
```
