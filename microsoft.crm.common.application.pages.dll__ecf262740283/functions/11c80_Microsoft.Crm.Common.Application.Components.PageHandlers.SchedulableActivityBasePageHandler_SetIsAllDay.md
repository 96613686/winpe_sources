# Microsoft.Crm.Common.Application.Components.PageHandlers.SchedulableActivityBasePageHandler::SetIsAllDay

- ea: `0x11c80`
- end: `0x11cc2`
- name: `Microsoft.Crm.Common.Application.Components.PageHandlers.SchedulableActivityBasePageHandler::SetIsAllDay`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x11c00`

## callees

- `0x11510`
- `0x11c80`

## string_xrefs

- `0x11ca7`: `scheduledend`

## pseudocode

```c

```

## disassembly

```asm
0x11c80  ldarg.0
0x11c81  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x11c86  ldstr    aIsalldayevent// "isalldayevent"
0x11c8b  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x11c90  stloc.0
0x11c91  ldloc.0
0x11c92  brfalse.s loc_11CC1
0x11c94  ldloc.0
0x11c95  unbox.any [mscorlib]System.Boolean
0x11c9a  brfalse.s loc_11CC1
0x11c9c  ldarg.0
0x11c9d  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentForm()
0x11ca2  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm
0x11ca7  ldstr    aScheduledend// "scheduledend"
0x11cac  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x11cb1  castclass [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl
0x11cb6  stloc.1
0x11cb7  ldloc.1
0x11cb8  brfalse.s loc_11CC1
0x11cba  ldloc.1
0x11cbb  ldc.i4.1
0x11cbc  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl::set_AllDayDisplayMode(bool)
0x11cc1  ret
```
