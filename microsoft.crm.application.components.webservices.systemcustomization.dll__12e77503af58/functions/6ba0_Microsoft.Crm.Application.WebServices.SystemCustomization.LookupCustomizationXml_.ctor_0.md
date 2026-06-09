# Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::.ctor_0

- ea: `0x6ba0`
- end: `0x6cc4`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::.ctor_0`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6380`

## string_xrefs

- `0x6c0f`: `RemoveLink`

## pseudocode

```c

```

## disassembly

```asm
0x6ba0  ldarg.0
0x6ba1  ldsfld   string [mscorlib]System.String::Empty
0x6ba6  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_schemaName
0x6bab  ldarg.0
0x6bac  ldstr    aFalse// "false"
0x6bb1  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_manyToMany
0x6bb6  ldarg.0
0x6bb7  ldsfld   string [mscorlib]System.String::Empty
0x6bbc  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_referencedEntityName
0x6bc1  ldarg.0
0x6bc2  ldsfld   string [mscorlib]System.String::Empty
0x6bc7  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_referencedInstanceName
0x6bcc  ldarg.0
0x6bcd  ldsfld   string [mscorlib]System.String::Empty
0x6bd2  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_referencingEntityName
0x6bd7  ldarg.0
0x6bd8  ldsfld   string [mscorlib]System.String::Empty
0x6bdd  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_attributeSchemaName
0x6be2  ldarg.0
0x6be3  ldstr    aNocascade// "NoCascade"
0x6be8  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_assignCascade
0x6bed  ldarg.0
0x6bee  ldstr    aNocascade// "NoCascade"
0x6bf3  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_shareCascade
0x6bf8  ldarg.0
0x6bf9  ldstr    aNocascade// "NoCascade"
0x6bfe  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_unshareCascade
0x6c03  ldarg.0
0x6c04  ldstr    aNocascade// "NoCascade"
0x6c09  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_reparentCascade
0x6c0e  ldarg.0
0x6c0f  ldstr    aRemovelink// "RemoveLink"
0x6c14  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_deleteCascade
0x6c19  ldarg.0
0x6c1a  ldsfld   string [mscorlib]System.String::Empty
0x6c1f  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_description
0x6c24  ldarg.0
0x6c25  ldstr    aUsecollectionn// "UseCollectionName"
0x6c2a  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_displayOption
0x6c2f  ldarg.0
0x6c30  ldstr    aDetails// "Details"
0x6c35  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_displayArea
0x6c3a  ldarg.0
0x6c3b  ldc.i4   0x2710
0x6c40  stfld    int32 Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_navPaneOrder
0x6c45  ldarg.0
0x6c46  call     instance void [mscorlib]System.Object::.ctor()
0x6c4b  ldarg.0
0x6c4c  ldarg.1
0x6c4d  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_referencedEntityName
0x6c52  ldarg.0
0x6c53  ldarg.2
0x6c54  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_referencedInstanceName
0x6c59  ldarg.0
0x6c5a  ldarg.3
0x6c5b  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_referencingEntityName
0x6c60  ldarg.0
0x6c61  ldarg.0
0x6c62  ldfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_referencedEntityName
0x6c67  ldstr    asc_F08C// "_"
0x6c6c  ldarg.0
0x6c6d  ldfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_referencingEntityName
0x6c72  call     string [mscorlib]System.String::Concat(string, string, string)
0x6c77  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_schemaName
0x6c7c  ldarg.0
0x6c7d  ldarg.0
0x6c7e  ldfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_schemaName
0x6c83  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetSchemaName(string)
0x6c88  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_schemaName
0x6c8d  ldarg.0
0x6c8e  ldarg.0
0x6c8f  ldfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_schemaName
0x6c94  ldstr    aAZaZ09// "[^a-zA-Z_0-9]"
0x6c99  ldsfld   string [mscorlib]System.String::Empty
0x6c9e  call     string [System]System.Text.RegularExpressions.Regex::Replace(string, string, string)
0x6ca3  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_schemaName
0x6ca8  ldarg.0
0x6ca9  ldarg.0
0x6caa  ldfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_referencedInstanceName
0x6caf  ldstr    aAZaZ09// "[^a-zA-Z_0-9]"
0x6cb4  ldsfld   string [mscorlib]System.String::Empty
0x6cb9  call     string [System]System.Text.RegularExpressions.Regex::Replace(string, string, string)
0x6cbe  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_attributeSchemaName
0x6cc3  ret
```
