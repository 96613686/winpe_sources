# Microsoft.Crm.Common.Application.Components.PageHandlers.RecurringAppointmentMasterRecordPageHandler::ConfigureFormHandler

- ea: `0x10ff0`
- end: `0x11059`
- name: `Microsoft.Crm.Common.Application.Components.PageHandlers.RecurringAppointmentMasterRecordPageHandler::ConfigureFormHandler`
- size: `105`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x10ff0`
- `0x110c0`
- `0x11340`
- `0x11550`

## pseudocode

```c

```

## disassembly

```asm
0x10ff0  ldarg.0
0x10ff1  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0x10ff6  ldc.i4.1
0x10ff7  ldarg.0
0x10ff8  ldftn    instance void Microsoft.Crm.Common.Application.Components.PageHandlers.RecurringAppointmentMasterRecordPageHandler::SetStateCodeFromStatusCode(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x10ffe  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x11003  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x11008  ldarg.0
0x11009  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0x1100e  ldc.i4.2
0x1100f  ldarg.0
0x11010  ldftn    instance void Microsoft.Crm.Common.Application.Components.PageHandlers.RecurringAppointmentMasterRecordPageHandler::SetStateCodeFromStatusCode(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x11016  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x1101b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x11020  ldarg.0
0x11021  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0x11026  ldc.i4.s 0x3B
0x11028  ldarg.0
0x11029  ldftn    instance void Microsoft.Crm.Common.Application.Components.PageHandlers.RecurringAppointmentMasterRecordPageHandler::SetStateCodeFromStatusCode(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x1102f  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x11034  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x11039  ldarg.0
0x1103a  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x1103f  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0x11044  brfalse.s loc_1104C
0x11046  ldarg.0
0x11047  call     instance void Microsoft.Crm.Common.Application.Components.PageHandlers.RecurringAppointmentMasterRecordPageHandler::PrepopulateForm()
0x1104c  ldarg.0
0x1104d  call     instance void Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::ConfigureFormHandler()
0x11052  ldarg.0
0x11053  call     instance void Microsoft.Crm.Common.Application.Components.PageHandlers.RecurringAppointmentMasterRecordPageHandler::RestrictStatusCodes()
0x11058  ret
```
