# Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthHandler::CompleteAdminAuthorization

- ea: `0x8ad0`
- end: `0x8b13`
- name: `Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthHandler::CompleteAdminAuthorization`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x8a50`

## callees

- `0x88f0`
- `0x8a20`
- `0x8ad0`
- `0x8c20`

## pseudocode

```c

```

## disassembly

```asm
0x8ad0  ldarg.0
0x8ad1  call     instance class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AccessTokenResponse Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::get_OAuthTokenResponse()
0x8ad6  callvirt instance class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AuthenticatedUser [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AccessTokenResponse::get_User()
0x8adb  callvirt instance bool [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AuthenticatedUser::get_IsAdmin()
0x8ae0  brfalse.s loc_8AF4
0x8ae2  ldarg.0
0x8ae3  call     instance class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AccessTokenResponse Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::get_OAuthTokenResponse()
0x8ae8  callvirt instance class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AuthenticatedUser [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AccessTokenResponse::get_User()
0x8aed  callvirt instance bool [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AuthenticatedUser::get_IsVerifiedAdmin()
0x8af2  brtrue.s loc_8B05
0x8af4  ldc.i4   0x8005F106
0x8af9  ldc.i4.0
0x8afa  newarr   [mscorlib]System.Object
0x8aff  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x8b04  throw
0x8b05  ldarg.0
0x8b06  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthHandler::SaveAdminOAuthToken()
0x8b0b  ldarg.0
0x8b0c  ldc.i4.1
0x8b0d  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthHandler::set_CloseWindow(bool value)
0x8b12  ret
```
