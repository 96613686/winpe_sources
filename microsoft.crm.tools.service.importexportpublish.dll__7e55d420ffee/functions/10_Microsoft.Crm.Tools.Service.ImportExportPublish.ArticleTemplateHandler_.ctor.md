# Microsoft.Crm.Tools.Service.ImportExportPublish.ArticleTemplateHandler::.ctor

- ea: `0x10`
- end: `0x3b`
- name: `Microsoft.Crm.Tools.Service.ImportExportPublish.ArticleTemplateHandler::.ctor`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x10  ldarg.0
0x11  call     instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::.ctor()
0x16  ldarg.0
0x17  ldarg.3
0x18  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.Service.ImportExportPublish.ArticleTemplateHandler::_solutionComponentTemplateSet
0x1d  ldarg.0
0x1e  ldarg.1
0x1f  stfld    class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.Service.ImportExportPublish.ArticleTemplateHandler::tracer
0x24  ldarg.0
0x25  ldarg.2
0x26  stfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ArticleTemplateHandler::context
0x2b  ldarg.0
0x2c  ldarg.s  4
0x2e  stfld    bool [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::_exportDeltaOverride
0x33  ldarg.0
0x34  ldnull
0x35  stfld    class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler[] [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::ExportHandlerChildren
0x3a  ret
```
