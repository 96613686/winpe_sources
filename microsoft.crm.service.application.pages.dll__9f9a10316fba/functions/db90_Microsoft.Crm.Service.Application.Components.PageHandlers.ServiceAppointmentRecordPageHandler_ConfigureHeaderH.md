# Microsoft.Crm.Service.Application.Components.PageHandlers.ServiceAppointmentRecordPageHandler::ConfigureHeaderHandler

- ea: `0xdb90`
- end: `0xdbdf`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.ServiceAppointmentRecordPageHandler::ConfigureHeaderHandler`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0xdb90`

## string_xrefs

- `0xdb9c`: `Service`
- `0xdbac`: `/_static/activities/serviceappointment/serviceappointment.js`

## pseudocode

```c

```

## disassembly

```asm
0xdb90  ldarg.0
0xdb91  call     instance void [Microsoft.Crm.Common.Application.Pages]Microsoft.Crm.Common.Application.Components.PageHandlers.SchedulableActivityBasePageHandler::ConfigureHeaderHandler()
0xdb96  ldarg.0
0xdb97  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xdb9c  ldstr    aService// "Service"
0xdba1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xdba6  ldarg.0
0xdba7  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xdbac  ldstr    aStaticActiviti// "/_static/activities/serviceappointment/"...
0xdbb1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xdbb6  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0xdbbb  brtrue.s loc_DBDE
0xdbbd  ldarg.0
0xdbbe  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xdbc3  ldstr    aLocidGoOnlineT// "LOCID_GO_ONLINE_TO_SCHEDULE"
0xdbc8  ldarg.0
0xdbc9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xdbce  ldstr    aGoOnlineToSche// "Go_Online_To_Schedule"
0xdbd3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdbd8  ldc.i4.0
0xdbd9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xdbde  ret
```
