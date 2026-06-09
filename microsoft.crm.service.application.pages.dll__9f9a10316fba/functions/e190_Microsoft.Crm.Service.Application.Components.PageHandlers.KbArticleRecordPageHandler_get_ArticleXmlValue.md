# Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::get_ArticleXmlValue

- ea: `0xe190`
- end: `0xe1a6`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::get_ArticleXmlValue`
- size: `22`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0xe240`
- `0xe3a0`

## callees

- `0xe130`

## pseudocode

```c

```

## disassembly

```asm
0xe190  ldarg.0
0xe191  call     instance string Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::get_ArticleXml()
0xe196  ldstr    asc_2272E// "\r\n"
0xe19b  ldstr    aRN// "\\r\\n"
0xe1a0  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xe1a5  ret
```
