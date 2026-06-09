# Microsoft.Crm.Common.Application.Pages.Common.GlobalHandler::GetGlobalJsPath

- ea: `0x1bf30`
- end: `0x1bf6a`
- name: `Microsoft.Crm.Common.Application.Pages.Common.GlobalHandler::GetGlobalJsPath`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1bc80`

## callees

- `0x1bf30`

## string_xrefs

- `0x1bf3b`: `/_common/global.ashx`
- `0x1bf4e`: `/_static/_common/scripts/global.js`
- `0x1bf5f`: `/help/common/global.js`

## pseudocode

```c

```

## disassembly

```asm
0x1bf30  ldarg.0
0x1bf31  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x1bf36  callvirt instance string [System.Web]System.Web.HttpRequest::get_Path()
0x1bf3b  ldstr    aCommonGlobalAs// "/_common/global.ashx"
0x1bf40  ldc.i4.5
0x1bf41  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x1bf46  brfalse.s loc_1BF59
0x1bf48  ldarg.0
0x1bf49  callvirt instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.HttpContext::get_Server()
0x1bf4e  ldstr    aStaticCommonSc_19// "/_static/_common/scripts/global.js"
0x1bf53  callvirt instance string [System.Web]System.Web.HttpServerUtility::MapPath(string)
0x1bf58  ret
0x1bf59  ldarg.0
0x1bf5a  callvirt instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.HttpContext::get_Server()
0x1bf5f  ldstr    aHelpCommonGlob// "/help/common/global.js"
0x1bf64  callvirt instance string [System.Web]System.Web.HttpServerUtility::MapPath(string)
0x1bf69  ret
```
