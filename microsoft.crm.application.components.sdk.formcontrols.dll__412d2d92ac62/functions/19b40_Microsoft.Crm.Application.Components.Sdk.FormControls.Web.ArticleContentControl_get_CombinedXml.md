# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::get_CombinedXml

- ea: `0x19b40`
- end: `0x19b75`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::get_CombinedXml`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x19b80`

## callees

- `0x19ac0`
- `0x19b40`
- `0x19d40`

## string_xrefs

- `0x19b59`: `<combinedxml>`
- `0x19b6a`: `</combinedxml>`

## pseudocode

```c

```

## disassembly

```asm
0x19b40  ldarg.0
0x19b41  ldfld    string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::_templateXml
0x19b46  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x19b4b  brfalse.s loc_19B59
0x19b4d  ldarg.0
0x19b4e  ldarg.0
0x19b4f  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::GetTemplateXml()
0x19b54  stfld    string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::_templateXml
0x19b59  ldstr    aCombinedxml// "<combinedxml>"
0x19b5e  ldarg.0
0x19b5f  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::get_ArticleXml()
0x19b64  ldarg.0
0x19b65  ldfld    string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::_templateXml
0x19b6a  ldstr    aCombinedxml_0// "</combinedxml>"
0x19b6f  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x19b74  ret
```
