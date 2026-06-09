# Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::GetParameterXPath

- ea: `0x6a0`
- end: `0x6b6`
- name: `Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::GetParameterXPath`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x6a0`: `/importexportxml/templates/template[@id='`

## pseudocode

```c

```

## disassembly

```asm
0x6a0  ldstr    aImportexportxm// "/importexportxml/templates/template[@id"...
0x6a5  ldarg.0
0x6a6  ldfld    string Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::_templateId
0x6ab  ldstr    asc_2426// "']"
0x6b0  call     string [mscorlib]System.String::Concat(string, string, string)
0x6b5  ret
```
