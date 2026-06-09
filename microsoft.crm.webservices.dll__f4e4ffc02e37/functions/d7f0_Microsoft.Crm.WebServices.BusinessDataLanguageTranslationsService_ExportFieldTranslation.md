# Microsoft.Crm.WebServices.BusinessDataLanguageTranslationsService::ExportFieldTranslation

- ea: `0xd7f0`
- end: `0xd807`
- name: `Microsoft.Crm.WebServices.BusinessDataLanguageTranslationsService::ExportFieldTranslation`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xeef0`
- `0xf170`

## string_xrefs

- `0xd7f6`: `CrmFieldTranslations.xml`

## pseudocode

```c

```

## disassembly

```asm
0xd7f0  ldc.i4.0
0xd7f1  newobj   instance void Microsoft.Crm.WebServices.TranslationImportExportService::.ctor(bool isSolutionAware)
0xd7f6  ldstr    aCrmfieldtransl// "CrmFieldTranslations.xml"
0xd7fb  ldarg.1
0xd7fc  ldsfld   string [mscorlib]System.String::Empty
0xd801  callvirt instance unsigned int8[] Microsoft.Crm.WebServices.TranslationImportExportService::ExportTranslations(string translationXmlFileName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string solutionName)
0xd806  ret
```
