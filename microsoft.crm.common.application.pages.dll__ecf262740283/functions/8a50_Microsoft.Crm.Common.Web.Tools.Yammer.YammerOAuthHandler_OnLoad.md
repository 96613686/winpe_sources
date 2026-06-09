# Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthHandler::OnLoad

- ea: `0x8a50`
- end: `0x8ac1`
- name: `Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthHandler::OnLoad`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x8610`
- `0x8630`
- `0x8a50`
- `0x8ad0`
- `0x8b20`

## string_xrefs

- `0x8aa3`: `Completed`
- `0x8a9e`: `YamTokenRefreshing`

## pseudocode

```c

```

## disassembly

```asm
0x8a50  ldarg.0
0x8a51  ldarg.1
0x8a52  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::OnLoad(class [mscorlib]System.EventArgs)
0x8a57  ldarg.0
0x8a58  call     instance bool Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::get_IsAdminFlow()
0x8a5d  brfalse.s loc_8A69
0x8a5f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8a64  call     void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.YammerState::EnsureUserCanConfigureYammer(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation)
0x8a69  ldarg.0
0x8a6a  call     instance bool Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::OAuthHandleRequest()
0x8a6f  brfalse.s loc_8A72
0x8a71  ret
0x8a72  ldarg.0
0x8a73  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Security.WrpcContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentWrpcContext()
0x8a78  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Security.WrpcContext::ValidateToken()
0x8a7d  call     void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Security.WrpcContext::ValidateTokenState()
0x8a82  ldarg.0
0x8a83  call     instance bool Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::get_IsAdminFlow()
0x8a88  brfalse.s loc_8A92
0x8a8a  ldarg.0
0x8a8b  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthHandler::CompleteAdminAuthorization()
0x8a90  br.s     loc_8A98
0x8a92  ldarg.0
0x8a93  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthHandler::CompleteUserAuthorization()
0x8a98  ldarg.0
0x8a99  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x8a9e  ldstr    aYamtokenrefres// "YamTokenRefreshing"
0x8aa3  ldstr    aCompleted// "Completed"
0x8aa8  newobj   instance void [System.Web]System.Web.HttpCookie::.ctor(string, string)
0x8aad  dup
0x8aae  ldc.i4.1
0x8aaf  callvirt instance void [System.Web]System.Web.HttpCookie::set_HttpOnly(bool)
0x8ab4  dup
0x8ab5  ldc.i4.1
0x8ab6  callvirt instance void [System.Web]System.Web.HttpCookie::set_Secure(bool)
0x8abb  callvirt instance void [System.Web]System.Web.HttpResponse::SetCookie(class [System.Web]System.Web.HttpCookie)
0x8ac0  ret
```
