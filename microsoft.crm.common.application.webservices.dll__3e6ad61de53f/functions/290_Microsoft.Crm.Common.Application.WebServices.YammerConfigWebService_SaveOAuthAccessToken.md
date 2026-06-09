# Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::SaveOAuthAccessToken

- ea: `0x290`
- end: `0x303`
- name: `Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::SaveOAuthAccessToken`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xb0`

## string_xrefs

- `0x2d0`: `yammeroauthaccesstokenexpired`

## pseudocode

```c

```

## disassembly

```asm
0x290  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x295  call     void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.YammerState::EnsureUserCanConfigureYammer(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation)
0x29a  ldstr    aOrganization// "organization"
0x29f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2a4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2a9  dup
0x2aa  ldstr    aOrganizationid// "organizationid"
0x2af  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2b4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x2b9  box      [mscorlib]System.Guid
0x2be  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x2c3  dup
0x2c4  ldstr    aDisabledreason// "disabledreason"
0x2c9  ldarg.1
0x2ca  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x2cf  dup
0x2d0  ldstr    aYammeroauthacc// "yammeroauthaccesstokenexpired"
0x2d5  ldc.i4.0
0x2d6  box      [mscorlib]System.Boolean
0x2db  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x2e0  dup
0x2e1  ldstr    aYammerpostmeth// "yammerpostmethod"
0x2e6  ldc.i4.1
0x2e7  box      [mscorlib]System.Int32
0x2ec  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x2f1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2f6  newobj   instance void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Components.Platform.ServiceCommands.UpdateYammerPropertiesCommand::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2fb  callvirt instance class [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.UpdateYammerPropertiesResponse [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Components.Platform.ServiceCommands.UpdateYammerPropertiesCommand::Execute()
0x300  pop
0x301  ldc.i4.1
0x302  ret
```
