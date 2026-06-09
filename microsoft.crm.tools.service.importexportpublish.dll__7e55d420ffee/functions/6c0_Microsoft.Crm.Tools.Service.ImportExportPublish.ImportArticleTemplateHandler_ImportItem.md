# Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::ImportItem

- ea: `0x6c0`
- end: `0x6ce`
- name: `Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::ImportItem`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x6c0  ldarg.0
0x6c1  ldarg.1
0x6c2  call     instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::set_Setup(bool)
0x6c7  ldarg.0
0x6c8  callvirt instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::ImportItem()
0x6cd  ret
```
