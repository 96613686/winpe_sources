# Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::ConfigureHeader

- ea: `0x7fb0`
- end: `0x8018`
- name: `Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::ConfigureHeader`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x7ee0`
- `0x7fb0`
- `0x8950`

## string_xrefs

- `0x7fbc`: `/_static/_common/scripts/SalesCommonImported.js`
- `0x7fcc`: `/_static/_controls/YammerConfigHandler/YammerConfigHandler.js`
- `0x7fdc`: `YammerConfigWebService`

## pseudocode

```c

```

## disassembly

```asm
0x7fb0  ldarg.0
0x7fb1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::ConfigureHeader()
0x7fb6  ldarg.0
0x7fb7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7fbc  ldstr    aStaticCommonSc_7// "/_static/_common/scripts/SalesCommonImp"...
0x7fc1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7fc6  ldarg.0
0x7fc7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7fcc  ldstr    aStaticControls_6// "/_static/_controls/YammerConfigHandler/"...
0x7fd1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7fd6  ldarg.0
0x7fd7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0x7fdc  ldstr    aYammerconfigwe// "YammerConfigWebService"
0x7fe1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x7fe6  ldarg.0
0x7fe7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7fec  ldstr    aDisableAuthori// "DISABLE_AUTHORIZATION"
0x7ff1  ldarg.0
0x7ff2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x7ff7  callvirt instance bool [System.Web]System.Web.HttpRequest::get_IsSecureConnection()
0x7ffc  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::AllowCredentialsEntry(bool)
0x8001  ldc.i4.0
0x8002  ceq
0x8004  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x8009  ldarg.0
0x800a  call     instance bool Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::get_IsOnPremise()
0x800f  brtrue.s loc_8017
0x8011  ldarg.0
0x8012  call     void Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::SetHandlerWrpc(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage page)
0x8017  ret
```
