# Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::SaveYammerPostMethod

- ea: `0x4a0`
- end: `0x514`
- name: `Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::SaveYammerPostMethod`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x4a0  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.Sdk.Caching.CacheData.YammerPostMethod
0x4a5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4aa  ldarg.1
0x4ab  box      [mscorlib]System.Int32
0x4b0  call     bool [mscorlib]System.Enum::IsDefined(class [mscorlib]System.Type, object)
0x4b5  ldstr    aSuppliedValueD// "Supplied value doesn't fall within the "...
0x4ba  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x4bf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4c4  call     void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.YammerState::EnsureUserCanConfigureYammer(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation)
0x4c9  ldstr    aOrganization// "organization"
0x4ce  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4d3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4d8  dup
0x4d9  ldstr    aOrganizationid// "organizationid"
0x4de  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4e3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x4e8  box      [mscorlib]System.Guid
0x4ed  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x4f2  dup
0x4f3  ldstr    aYammerpostmeth// "yammerpostmethod"
0x4f8  ldarg.1
0x4f9  box      [mscorlib]System.Int32
0x4fe  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x503  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x508  newobj   instance void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Components.Platform.ServiceCommands.UpdateYammerPropertiesCommand::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x50d  callvirt instance class [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.UpdateYammerPropertiesResponse [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Components.Platform.ServiceCommands.UpdateYammerPropertiesCommand::Execute()
0x512  pop
0x513  ret
```
