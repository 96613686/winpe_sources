# Microsoft.Crm.Service.Application.Components.PageHandlers.ServiceAppointmentRecordPageHandler::InitializeEntity

- ea: `0xdb50`
- end: `0xdb6c`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.ServiceAppointmentRecordPageHandler::InitializeEntity`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0xdb57`: `serviceappointment`

## pseudocode

```c

```

## disassembly

```asm
0xdb50  ldarg.0
0xdb51  ldc.i4.1
0xdb52  call     instance void [Microsoft.Crm.Common.Application.Pages]Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::set_ShowSaveAsCompleted(bool)
0xdb57  ldstr    aServiceappoint// "serviceappointment"
0xdb5c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xdb61  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xdb66  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xdb6b  ret
```
