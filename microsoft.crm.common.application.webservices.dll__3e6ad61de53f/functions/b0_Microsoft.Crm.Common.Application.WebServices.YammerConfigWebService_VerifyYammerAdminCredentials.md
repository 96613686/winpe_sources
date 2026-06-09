# Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::VerifyYammerAdminCredentials

- ea: `0xb0`
- end: `0x122`
- name: `Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::VerifyYammerAdminCredentials`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xb0`
- `0x180`
- `0x290`

## pseudocode

```c

```

## disassembly

```asm
0xb0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb5  call     void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.YammerState::EnsureUserCanConfigureYammer(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation)
0xba  ldarg.0
0xbb  ldarg.1
0xbc  ldarg.2
0xbd  call     instance class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AccessTokenResponse Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::AuthenticateYammerUser(string userEmail, string userPassword)
0xc2  stloc.0
0xc3  ldloc.0
0xc4  brfalse.s loc_113
0xc6  ldloc.0
0xc7  callvirt instance class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AuthenticatedUser [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AccessTokenResponse::get_User()
0xcc  brfalse.s loc_113
0xce  ldloc.0
0xcf  callvirt instance class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AuthenticatedUser [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AccessTokenResponse::get_User()
0xd4  callvirt instance bool [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AuthenticatedUser::get_IsAdmin()
0xd9  brfalse.s loc_E8
0xdb  ldloc.0
0xdc  callvirt instance class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AuthenticatedUser [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AccessTokenResponse::get_User()
0xe1  callvirt instance bool [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AuthenticatedUser::get_IsVerifiedAdmin()
0xe6  brtrue.s loc_FD
0xe8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xed  ldstr    aWebToolsYammer// "Web.Tools.Yammer.NotANetworkAdministrat"...
0xf2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xfc  throw
0xfd  ldarg.0
0xfe  ldloc.0
0xff  callvirt instance class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AccessToken [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AccessTokenResponse::get_AccessToken()
0x104  callvirt instance string [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AccessToken::get_Token()
0x109  call     instance bool Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::SaveOAuthAccessToken(string accessToken)
0x10e  pop
0x10f  ldc.i4.1
0x110  stloc.1
0x111  leave.s  loc_120
0x113  ldc.i4.0
0x114  stloc.1
0x115  leave.s  loc_120
0x117  stloc.2
0x118  ldarg.0
0x119  ldloc.2
0x11a  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x11f  throw
0x120  ldloc.1
0x121  ret
```
