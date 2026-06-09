# Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthHandler::SaveAdminOAuthToken

- ea: `0x8c20`
- end: `0x8c97`
- name: `Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthHandler::SaveAdminOAuthToken`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x8ad0`

## callees

- `0x88f0`

## string_xrefs

- `0x8c65`: `yammeroauthaccesstokenexpired`

## pseudocode

```c

```

## disassembly

```asm
0x8c20  ldstr    aOrganization// "organization"
0x8c25  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8c2a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8c2f  dup
0x8c30  ldstr    aOrganizationid// "organizationid"
0x8c35  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8c3a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x8c3f  box      [mscorlib]System.Guid
0x8c44  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x8c49  dup
0x8c4a  ldstr    aDisabledreason// "disabledreason"
0x8c4f  ldarg.0
0x8c50  call     instance class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AccessTokenResponse Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::get_OAuthTokenResponse()
0x8c55  callvirt instance class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AccessToken [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AccessTokenResponse::get_AccessToken()
0x8c5a  callvirt instance string [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AccessToken::get_Token()
0x8c5f  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x8c64  dup
0x8c65  ldstr    aYammeroauthacc// "yammeroauthaccesstokenexpired"
0x8c6a  ldc.i4.0
0x8c6b  box      [mscorlib]System.Boolean
0x8c70  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x8c75  dup
0x8c76  ldstr    aYammerpostmeth// "yammerpostmethod"
0x8c7b  ldc.i4.1
0x8c7c  box      [mscorlib]System.Int32
0x8c81  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x8c86  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8c8b  newobj   instance void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Components.Platform.ServiceCommands.UpdateYammerPropertiesCommand::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8c90  callvirt instance class [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.UpdateYammerPropertiesResponse [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Components.Platform.ServiceCommands.UpdateYammerPropertiesCommand::Execute()
0x8c95  pop
0x8c96  ret
```
