# Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::get_ArticleXml

- ea: `0xe130`
- end: `0xe18d`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::get_ArticleXml`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0xe190`
- `0xe490`

## callees

- `0xe130`

## string_xrefs

- `0xe144`: `articlexml`

## pseudocode

```c

```

## disassembly

```asm
0xe130  ldarg.0
0xe131  ldfld    string Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::_articleXml
0xe136  callvirt instance int32 [mscorlib]System.String::get_Length()
0xe13b  brtrue.s loc_E186
0xe13d  ldarg.0
0xe13e  ldarg.0
0xe13f  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xe144  ldstr    aArticlexml// "articlexml"
0xe149  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::GetDataValue(string)
0xe14e  stfld    string Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::_articleXml
0xe153  ldarg.0
0xe154  ldfld    string Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::_articleXml
0xe159  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xe15e  brfalse.s loc_E16B
0xe160  ldarg.0
0xe161  ldstr    aArticledataArt// "<articledata></articledata>"
0xe166  stfld    string Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::_articleXml
0xe16b  ldarg.0
0xe16c  ldarg.0
0xe16d  ldfld    string Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::_articleXml
0xe172  ldstr    asc_22726// "\""
0xe177  ldstr    asc_2272A// "'"
0xe17c  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xe181  stfld    string Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::_articleXml
0xe186  ldarg.0
0xe187  ldfld    string Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::_articleXml
0xe18c  ret
```
