# Microsoft.Crm.WebServices.TranslationImportExportService::ImportTranslationsInternal

- ea: `0xf0a0`
- end: `0xf0d0`
- name: `Microsoft.Crm.WebServices.TranslationImportExportService::ImportTranslationsInternal`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xef00`

## callees

- `0xf0a0`
- `0xf0d0`

## pseudocode

```c

```

## disassembly

```asm
0xf0a0  ldarg.0
0xf0a1  ldfld    bool Microsoft.Crm.WebServices.TranslationImportExportService::_isSolutionAware
0xf0a6  brfalse.s loc_F0C1
0xf0a8  ldarg.3
0xf0a9  ldarg.0
0xf0aa  ldfld    bool Microsoft.Crm.WebServices.TranslationImportExportService::_isSolutionAware
0xf0af  newobj   instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.LanguageTranslations::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0xf0b4  ldarg.1
0xf0b5  ldarg.2
0xf0b6  ldobj    [mscorlib]System.Guid
0xf0bb  callvirt instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.LanguageTranslations::ImportTranslationsWithProgress(string, valuetype [mscorlib]System.Guid)
0xf0c0  ret
0xf0c1  ldarg.2
0xf0c2  ldarg.0
0xf0c3  ldarg.1
0xf0c4  ldarg.3
0xf0c5  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.WebServices.TranslationImportExportService::CreateImportTranslationsAsyncJob(string crmTranslationsXml, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xf0ca  stobj    [mscorlib]System.Guid
0xf0cf  ret
```
