# Microsoft.Crm.WebServices.LangTranslationsService::ExportTranslation

- ea: `0xe900`
- end: `0xe925`
- name: `Microsoft.Crm.WebServices.LangTranslationsService::ExportTranslation`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xe980`

## callees

- `0xe9b0`
- `0xeef0`
- `0xf170`

## string_xrefs

- `0xe918`: `CrmTranslations.xml`

## pseudocode

```c

```

## disassembly

```asm
0xe900  ldarg.1
0xe901  ldstr    aSolutionname// "solutionName"
0xe906  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xe90b  ldarg.0
0xe90c  ldarg.2
0xe90d  call     instance void Microsoft.Crm.WebServices.LangTranslationsService::CheckExportPrivileges(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xe912  ldc.i4.1
0xe913  newobj   instance void Microsoft.Crm.WebServices.TranslationImportExportService::.ctor(bool isSolutionAware)
0xe918  ldstr    aCrmtranslation// "CrmTranslations.xml"
0xe91d  ldarg.2
0xe91e  ldarg.1
0xe91f  callvirt instance unsigned int8[] Microsoft.Crm.WebServices.TranslationImportExportService::ExportTranslations(string translationXmlFileName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string solutionName)
0xe924  ret
```
