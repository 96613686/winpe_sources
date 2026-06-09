# Microsoft.Crm.WebServices.LangTranslationsService::ImportTranslation

- ea: `0xe930`
- end: `0xe967`
- name: `Microsoft.Crm.WebServices.LangTranslationsService::ImportTranslation`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xe9a0`

## callees

- `0xea80`
- `0xeef0`
- `0xef00`

## string_xrefs

- `0xe958`: `CrmTranslations.xml`

## pseudocode

```c

```

## disassembly

```asm
0xe930  ldarg.1
0xe931  ldstr    aTranslationfil// "translationFile"
0xe936  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xe93b  ldarg.2
0xe93c  box      [mscorlib]System.Guid
0xe941  ldstr    aImportjobid// "importJobId"
0xe946  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xe94b  ldarg.0
0xe94c  ldarg.3
0xe94d  call     instance void Microsoft.Crm.WebServices.LangTranslationsService::CheckImportPrivileges(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xe952  ldc.i4.1
0xe953  newobj   instance void Microsoft.Crm.WebServices.TranslationImportExportService::.ctor(bool isSolutionAware)
0xe958  ldstr    aCrmtranslation// "CrmTranslations.xml"
0xe95d  ldarg.1
0xe95e  ldarga.s 2
0xe960  ldarg.3
0xe961  callvirt instance void Microsoft.Crm.WebServices.TranslationImportExportService::ImportTranslation(string translationXmlFileName, unsigned int8[] translationFile, valuetype [mscorlib]System.Guid& importJobId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xe966  ret
```
