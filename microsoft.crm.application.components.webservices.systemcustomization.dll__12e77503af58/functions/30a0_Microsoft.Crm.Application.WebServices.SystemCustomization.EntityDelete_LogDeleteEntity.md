# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityDelete::LogDeleteEntity

- ea: `0x30a0`
- end: `0x30f1`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityDelete::LogDeleteEntity`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x3040`

## string_xrefs

- `0x30d5`: `DeleteEntity`

## pseudocode

```c

```

## disassembly

```asm
0x30a0  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData::.ctor()
0x30a5  stloc.0
0x30a6  ldloc.0
0x30a7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x30ac  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x30b1  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData::set_SystemUserId(valuetype [mscorlib]System.Guid)
0x30b6  ldloc.0
0x30b7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x30bc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x30c1  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData::set_OrganizationId(valuetype [mscorlib]System.Guid)
0x30c6  ldloc.0
0x30c7  ldarg.1
0x30c8  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData::set_EntityName(string)
0x30cd  ldloc.0
0x30ce  ldarg.0
0x30cf  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData::set_EntityId(valuetype [mscorlib]System.Guid)
0x30d4  ldloc.0
0x30d5  ldstr    aDeleteentity// "DeleteEntity"
0x30da  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData::set_Operation(string)
0x30df  ldloc.0
0x30e0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData::get_OrganizationId()
0x30e5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x30ea  ldloc.0
0x30eb  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLogging::LogRequest(class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData)
0x30f0  ret
```
