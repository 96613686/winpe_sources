# Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::SaveAsCompletedMenuOk

- ea: `0x117e0`
- end: `0x11816`
- name: `Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::SaveAsCompletedMenuOk`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x11550`

## callees

- `0x114d0`
- `0x11510`
- `0x117e0`

## pseudocode

```c

```

## disassembly

```asm
0x117e0  ldarg.0
0x117e1  call     instance bool Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_ShowSaveAsCompleted()
0x117e6  brfalse.s loc_11814
0x117e8  ldarg.0
0x117e9  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x117ee  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0x117f3  brfalse.s loc_117F7
0x117f5  ldc.i4.1
0x117f6  ret
0x117f7  ldc.i4.2
0x117f8  ldarg.0
0x117f9  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0x117fe  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormState [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_State()
0x11803  bne.un.s loc_11814
0x11805  ldarg.0
0x11806  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x1180b  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Disabled()
0x11810  brtrue.s loc_11814
0x11812  ldc.i4.1
0x11813  ret
0x11814  ldc.i4.0
0x11815  ret
```
