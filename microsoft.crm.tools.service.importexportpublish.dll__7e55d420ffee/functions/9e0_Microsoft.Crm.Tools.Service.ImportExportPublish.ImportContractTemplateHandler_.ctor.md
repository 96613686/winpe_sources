# Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::.ctor

- ea: `0x9e0`
- end: `0xa23`
- name: `Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::.ctor`
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
0x9e0  ldarg.0
0x9e1  call     instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::.ctor()
0x9e6  ldarg.0
0x9e7  ldarg.s  5
0x9e9  stfld    class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::tracer
0x9ee  ldarg.0
0x9ef  ldarg.1
0x9f0  stfld    class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x9f5  ldarg.0
0x9f6  ldarg.3
0x9f7  stfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::context
0x9fc  ldarg.0
0x9fd  ldnull
0x9fe  stfld    class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHandler[] [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::ImportHandlerChildren
0xa03  ldarg.0
0xa04  ldarg.s  4
0xa06  stfld    class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::_importHelper
0xa0b  ldarg.0
0xa0c  ldarg.2
0xa0d  stfld    string Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::_templateId
0xa12  ldarg.0
0xa13  ldarg.s  6
0xa15  stfld    class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportXml [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::_parent
0xa1a  ldarg.0
0xa1b  ldarg.s  7
0xa1d  stfld    string Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::_langFilter
0xa22  ret
```
