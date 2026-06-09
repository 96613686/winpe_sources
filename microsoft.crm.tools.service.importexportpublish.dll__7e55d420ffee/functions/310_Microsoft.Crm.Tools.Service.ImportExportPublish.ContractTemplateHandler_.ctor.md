# Microsoft.Crm.Tools.Service.ImportExportPublish.ContractTemplateHandler::.ctor

- ea: `0x310`
- end: `0x33b`
- name: `Microsoft.Crm.Tools.Service.ImportExportPublish.ContractTemplateHandler::.ctor`
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
0x310  ldarg.0
0x311  call     instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::.ctor()
0x316  ldarg.0
0x317  ldarg.3
0x318  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.Service.ImportExportPublish.ContractTemplateHandler::_solutionComponentTemplateSet
0x31d  ldarg.0
0x31e  ldarg.1
0x31f  stfld    class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.Service.ImportExportPublish.ContractTemplateHandler::tracer
0x324  ldarg.0
0x325  ldarg.2
0x326  stfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ContractTemplateHandler::context
0x32b  ldarg.0
0x32c  ldarg.s  4
0x32e  stfld    bool [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::_exportDeltaOverride
0x333  ldarg.0
0x334  ldnull
0x335  stfld    class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler[] [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::ExportHandlerChildren
0x33a  ret
```
