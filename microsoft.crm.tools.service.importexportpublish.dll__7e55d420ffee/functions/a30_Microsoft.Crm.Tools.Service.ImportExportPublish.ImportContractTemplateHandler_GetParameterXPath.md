# Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::GetParameterXPath

- ea: `0xa30`
- end: `0xa46`
- name: `Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::GetParameterXPath`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0xa30`: `/importexportxml/templates/template[@id='`

## pseudocode

```c

```

## disassembly

```asm
0xa30  ldstr    aImportexportxm// "/importexportxml/templates/template[@id"...
0xa35  ldarg.0
0xa36  ldfld    string Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::_templateId
0xa3b  ldstr    asc_2426// "']"
0xa40  call     string [mscorlib]System.String::Concat(string, string, string)
0xa45  ret
```
