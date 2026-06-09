# Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::InitializeStartEndDuractionControls

- ea: `0xdf40`
- end: `0xdfa6`
- name: `Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::InitializeStartEndDuractionControls`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xd870`

## callees

- `0xe650`

## string_xrefs

- `0xdf47`: `scheduledstart`
- `0xdf67`: `scheduledend`
- `0xdf87`: `scheduleddurationminutes`

## pseudocode

```c

```

## disassembly

```asm
0xdf40  ldarg.0
0xdf41  ldarg.0
0xdf42  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0xdf47  ldstr    aScheduledstart// "scheduledstart"
0xdf4c  call     instance class [System.Web]System.Web.UI.Control Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::FindChildControl(class [System.Web]System.Web.UI.Control control, string id)
0xdf51  isinst   [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl
0xdf56  ldstr    aStarttimechang// "startTimeChanged"
0xdf5b  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl::set_OnChangeScript(string)
0xdf60  ldarg.0
0xdf61  ldarg.0
0xdf62  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0xdf67  ldstr    aScheduledend// "scheduledend"
0xdf6c  call     instance class [System.Web]System.Web.UI.Control Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::FindChildControl(class [System.Web]System.Web.UI.Control control, string id)
0xdf71  isinst   [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl
0xdf76  ldstr    aEndtimechanged// "endTimeChanged"
0xdf7b  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl::set_OnChangeScript(string)
0xdf80  ldarg.0
0xdf81  ldarg.0
0xdf82  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0xdf87  ldstr    aScheduleddurat// "scheduleddurationminutes"
0xdf8c  call     instance class [System.Web]System.Web.UI.Control Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::FindChildControl(class [System.Web]System.Web.UI.Control control, string id)
0xdf91  isinst   [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DurationControl
0xdf96  ldstr    aOnchangepreatt// "OnChangePreAttach"
0xdf9b  ldstr    aDurationchange// "durationChanged();"
0xdfa0  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::AddExpando(string, string)
0xdfa5  ret
```
