# Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::ConfigureFormHandler

- ea: `0x11550`
- end: `0x115d5`
- name: `Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::ConfigureFormHandler`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x10ff0`
- `0x11c00`

## callees

- `0x11510`
- `0x11550`
- `0x117e0`

## pseudocode

```c

```

## disassembly

```asm
0x11550  ldarg.0
0x11551  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::ConfigureFormHandler()
0x11556  ldarg.0
0x11557  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0x1155c  ldc.i4.5
0x1155d  ldarg.0
0x1155e  ldftn    instance void Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::ChangeStateHandler(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x11564  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x11569  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x1156e  ldarg.0
0x1156f  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0x11574  ldc.i4.6
0x11575  ldarg.0
0x11576  ldftn    instance void Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::ChangeStateHandler(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x1157c  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x11581  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x11586  ldarg.0
0x11587  call     instance bool Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::SaveAsCompletedMenuOk()
0x1158c  brfalse.s loc_115A7
0x1158e  ldarg.0
0x1158f  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0x11594  ldc.i4.s 0x3A
0x11596  ldarg.0
0x11597  ldftn    instance void Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::SaveAsCompleted(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x1159d  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x115a2  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x115a7  ldarg.0
0x115a8  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0x115ad  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm
0x115b2  ldarg.0
0x115b3  ldftn    instance void Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::CheckPromoteOption(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs e)
0x115b9  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm/DataBoundEventHandler::.ctor(object, native int)
0x115be  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::add_DataBound(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm/DataBoundEventHandler)
0x115c3  ldarg.0
0x115c4  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0x115c9  ldarg.0
0x115ca  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x115cf  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0x115d4  ret
```
