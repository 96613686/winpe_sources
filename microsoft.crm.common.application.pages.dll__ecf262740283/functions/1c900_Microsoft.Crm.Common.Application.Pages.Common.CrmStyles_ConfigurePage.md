# Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::ConfigurePage

- ea: `0x1c900`
- end: `0x1c9c4`
- name: `Microsoft.Crm.Common.Application.Pages.Common.CrmStyles::ConfigurePage`
- size: `196`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## string_xrefs

- `0x1c992`: `updateTimeStamp`

## pseudocode

```c

```

## disassembly

```asm
0x1c900  ldarg.0
0x1c901  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.StaticVersionedPage::ConfigurePage()
0x1c906  ldarg.0
0x1c907  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1c90c  ldstr    aTextCss// "text/css"
0x1c911  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x1c916  ldarg.0
0x1c917  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1c91c  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x1c921  callvirt instance class [System.Web]System.Web.HttpCacheVaryByParams [System.Web]System.Web.HttpCachePolicy::get_VaryByParams()
0x1c926  ldstr    aTheme// "theme"
0x1c92b  ldc.i4.1
0x1c92c  callvirt instance void [System.Web]System.Web.HttpCacheVaryByParams::set_Item(string, bool)
0x1c931  ldarg.0
0x1c932  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1c937  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x1c93c  callvirt instance class [System.Web]System.Web.HttpCacheVaryByParams [System.Web]System.Web.HttpCachePolicy::get_VaryByParams()
0x1c941  ldstr    aLcid// "lcid"
0x1c946  ldc.i4.1
0x1c947  callvirt instance void [System.Web]System.Web.HttpCacheVaryByParams::set_Item(string, bool)
0x1c94c  ldarg.0
0x1c94d  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1c952  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x1c957  callvirt instance class [System.Web]System.Web.HttpCacheVaryByParams [System.Web]System.Web.HttpCachePolicy::get_VaryByParams()
0x1c95c  ldstr    aSlugsupport// "slugsupport"
0x1c961  ldc.i4.1
0x1c962  callvirt instance void [System.Web]System.Web.HttpCacheVaryByParams::set_Item(string, bool)
0x1c967  ldarg.0
0x1c968  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1c96d  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x1c972  callvirt instance class [System.Web]System.Web.HttpCacheVaryByParams [System.Web]System.Web.HttpCachePolicy::get_VaryByParams()
0x1c977  ldstr    aThemeid// "themeId"
0x1c97c  ldc.i4.1
0x1c97d  callvirt instance void [System.Web]System.Web.HttpCacheVaryByParams::set_Item(string, bool)
0x1c982  ldarg.0
0x1c983  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1c988  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x1c98d  callvirt instance class [System.Web]System.Web.HttpCacheVaryByParams [System.Web]System.Web.HttpCachePolicy::get_VaryByParams()
0x1c992  ldstr    aUpdatetimestam// "updateTimeStamp"
0x1c997  ldc.i4.1
0x1c998  callvirt instance void [System.Web]System.Web.HttpCacheVaryByParams::set_Item(string, bool)
0x1c99d  ldarg.0
0x1c99e  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1c9a3  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x1c9a8  ldstr    aBrowser// "browser"
0x1c9ad  callvirt instance void [System.Web]System.Web.HttpCachePolicy::SetVaryByCustom(string)
0x1c9b2  ldarg.0
0x1c9b3  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1c9b8  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x1c9bd  ldc.i4.1
0x1c9be  callvirt instance void [System.Web]System.Web.HttpCachePolicy::SetOmitVaryStar(bool)
0x1c9c3  ret
```
