# Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::InitializeUpgradeHandlers

- ea: `0x670`
- end: `0x6a0`
- name: `Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::InitializeUpgradeHandlers`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x670  ldarg.0
0x671  ldc.i4.1
0x672  newarr   [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.UpgradeHandler
0x677  stfld    class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.UpgradeHandler[] [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::UpgradeHandlers
0x67c  ldarg.0
0x67d  ldfld    class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.UpgradeHandler[] [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::UpgradeHandlers
0x682  ldc.i4.0
0x683  ldarg.0
0x684  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::context
0x689  ldarg.0
0x68a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::context
0x68f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x694  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.KbArticleTemplate::.ctor(valuetype [mscorlib]System.Guid)
0x699  newobj   instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.InitTemplateLanguageCode::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity)
0x69e  stelem.ref
0x69f  ret
```
