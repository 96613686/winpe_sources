# Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::ConfigureHeaderHandler

- ea: `0x11b00`
- end: `0x11b36`
- name: `Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::ConfigureHeaderHandler`
- size: `54`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x10db0`
- `0x11b90`

## callees

- `0x11510`
- `0x11b00`

## pseudocode

```c

```

## disassembly

```asm
0x11b00  ldarg.0
0x11b01  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::ConfigureHeaderHandler()
0x11b06  ldarg.0
0x11b07  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x11b0c  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Disabled()
0x11b11  brtrue.s loc_11B35
0x11b13  ldarg.0
0x11b14  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentForm()
0x11b19  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_ReadOnly()
0x11b1e  brtrue.s loc_11B35
0x11b20  ldarg.0
0x11b21  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x11b26  ldstr    aSetfocus// "SetFocus"
0x11b2b  ldstr    aExecutefunctio// "executeFunctionDeferred(SetFocusOnSubje"...
0x11b30  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(string, string)
0x11b35  ret
```
