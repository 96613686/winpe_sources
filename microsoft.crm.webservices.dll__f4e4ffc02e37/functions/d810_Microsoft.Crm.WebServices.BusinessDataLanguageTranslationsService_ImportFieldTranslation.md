# Microsoft.Crm.WebServices.BusinessDataLanguageTranslationsService::ImportFieldTranslation

- ea: `0xd810`
- end: `0xd83e`
- name: `Microsoft.Crm.WebServices.BusinessDataLanguageTranslationsService::ImportFieldTranslation`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xd840`
- `0xeef0`
- `0xef00`

## string_xrefs

- `0xd82e`: `CrmFieldTranslations.xml`

## pseudocode

```c

```

## disassembly

```asm
0xd810  ldarg.1
0xd811  ldstr    aTranslationfil// "translationFile"
0xd816  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xd81b  ldarg.0
0xd81c  ldarg.2
0xd81d  call     instance void Microsoft.Crm.WebServices.BusinessDataLanguageTranslationsService::CheckImportPrivileges(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xd822  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xd827  stloc.0
0xd828  ldc.i4.0
0xd829  newobj   instance void Microsoft.Crm.WebServices.TranslationImportExportService::.ctor(bool isSolutionAware)
0xd82e  ldstr    aCrmfieldtransl// "CrmFieldTranslations.xml"
0xd833  ldarg.1
0xd834  ldloca.s 0
0xd836  ldarg.2
0xd837  callvirt instance void Microsoft.Crm.WebServices.TranslationImportExportService::ImportTranslation(string translationXmlFileName, unsigned int8[] translationFile, valuetype [mscorlib]System.Guid& importJobId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xd83c  ldloc.0
0xd83d  ret
```
