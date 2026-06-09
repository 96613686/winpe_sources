# Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::SaveSelectedGroup

- ea: `0x440`
- end: `0x495`
- name: `Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::SaveSelectedGroup`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x440  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x445  call     void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.YammerState::EnsureUserCanConfigureYammer(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation)
0x44a  ldstr    aOrganization// "organization"
0x44f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x454  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x459  dup
0x45a  ldstr    aOrganizationid// "organizationid"
0x45f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x464  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x469  box      [mscorlib]System.Guid
0x46e  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x473  dup
0x474  ldstr    aYammergroupid// "yammergroupid"
0x479  ldarg.1
0x47a  box      [mscorlib]System.Int32
0x47f  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x484  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x489  newobj   instance void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Components.Platform.ServiceCommands.UpdateYammerPropertiesCommand::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x48e  callvirt instance class [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.UpdateYammerPropertiesResponse [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Components.Platform.ServiceCommands.UpdateYammerPropertiesCommand::Execute()
0x493  pop
0x494  ret
```
