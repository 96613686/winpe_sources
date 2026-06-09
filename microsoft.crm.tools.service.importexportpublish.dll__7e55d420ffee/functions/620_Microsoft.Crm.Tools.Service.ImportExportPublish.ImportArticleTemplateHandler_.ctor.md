# Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::.ctor

- ea: `0x620`
- end: `0x663`
- name: `Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::.ctor`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x620  ldarg.0
0x621  call     instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::.ctor()
0x626  ldarg.0
0x627  ldarg.s  5
0x629  stfld    class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::tracer
0x62e  ldarg.0
0x62f  ldarg.1
0x630  stfld    class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x635  ldarg.0
0x636  ldarg.3
0x637  stfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::context
0x63c  ldarg.0
0x63d  ldnull
0x63e  stfld    class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHandler[] [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::ImportHandlerChildren
0x643  ldarg.0
0x644  ldarg.s  4
0x646  stfld    class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::_importHelper
0x64b  ldarg.0
0x64c  ldarg.2
0x64d  stfld    string Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::_templateId
0x652  ldarg.0
0x653  ldarg.s  6
0x655  stfld    class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportXml [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::_parent
0x65a  ldarg.0
0x65b  ldarg.s  7
0x65d  stfld    string Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::_langFilter
0x662  ret
```
