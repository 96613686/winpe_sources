# Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::DisableChildControls

- ea: `0xe120`
- end: `0xe183`
- name: `Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::DisableChildControls`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xd870`

## callees

- `0xe650`

## string_xrefs

- `0xe122`: `scheduledstart`
- `0xe134`: `scheduledend`
- `0xe146`: `scheduleddurationminutes`

## pseudocode

```c

```

## disassembly

```asm
0xe120  ldarg.0
0xe121  ldarg.0
0xe122  ldstr    aScheduledstart// "scheduledstart"
0xe127  call     instance class [System.Web]System.Web.UI.Control Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::FindChildControl(class [System.Web]System.Web.UI.Control control, string id)
0xe12c  isinst   [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl
0xe131  stloc.0
0xe132  ldarg.0
0xe133  ldarg.0
0xe134  ldstr    aScheduledend// "scheduledend"
0xe139  call     instance class [System.Web]System.Web.UI.Control Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::FindChildControl(class [System.Web]System.Web.UI.Control control, string id)
0xe13e  isinst   [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl
0xe143  stloc.1
0xe144  ldarg.0
0xe145  ldarg.0
0xe146  ldstr    aScheduleddurat// "scheduleddurationminutes"
0xe14b  call     instance class [System.Web]System.Web.UI.Control Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::FindChildControl(class [System.Web]System.Web.UI.Control control, string id)
0xe150  isinst   [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DurationControl
0xe155  stloc.2
0xe156  ldarg.0
0xe157  ldarg.0
0xe158  ldstr    aRangeoption1Pa// "rangeOption1_patternstartdate"
0xe15d  call     instance class [System.Web]System.Web.UI.Control Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::FindChildControl(class [System.Web]System.Web.UI.Control control, string id)
0xe162  isinst   [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl
0xe167  ldloc.0
0xe168  ldc.i4.1
0xe169  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0xe16e  ldloc.1
0xe16f  ldc.i4.1
0xe170  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0xe175  ldloc.2
0xe176  ldc.i4.1
0xe177  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0xe17c  ldc.i4.1
0xe17d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0xe182  ret
```
