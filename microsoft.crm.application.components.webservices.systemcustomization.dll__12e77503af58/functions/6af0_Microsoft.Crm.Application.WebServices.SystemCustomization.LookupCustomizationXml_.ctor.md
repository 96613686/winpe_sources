# Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::.ctor

- ea: `0x6af0`
- end: `0x6b9c`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::.ctor`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x6b5f`: `RemoveLink`

## pseudocode

```c

```

## disassembly

```asm
0x6af0  ldarg.0
0x6af1  ldsfld   string [mscorlib]System.String::Empty
0x6af6  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_schemaName
0x6afb  ldarg.0
0x6afc  ldstr    aFalse// "false"
0x6b01  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_manyToMany
0x6b06  ldarg.0
0x6b07  ldsfld   string [mscorlib]System.String::Empty
0x6b0c  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_referencedEntityName
0x6b11  ldarg.0
0x6b12  ldsfld   string [mscorlib]System.String::Empty
0x6b17  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_referencedInstanceName
0x6b1c  ldarg.0
0x6b1d  ldsfld   string [mscorlib]System.String::Empty
0x6b22  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_referencingEntityName
0x6b27  ldarg.0
0x6b28  ldsfld   string [mscorlib]System.String::Empty
0x6b2d  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_attributeSchemaName
0x6b32  ldarg.0
0x6b33  ldstr    aNocascade// "NoCascade"
0x6b38  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_assignCascade
0x6b3d  ldarg.0
0x6b3e  ldstr    aNocascade// "NoCascade"
0x6b43  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_shareCascade
0x6b48  ldarg.0
0x6b49  ldstr    aNocascade// "NoCascade"
0x6b4e  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_unshareCascade
0x6b53  ldarg.0
0x6b54  ldstr    aNocascade// "NoCascade"
0x6b59  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_reparentCascade
0x6b5e  ldarg.0
0x6b5f  ldstr    aRemovelink// "RemoveLink"
0x6b64  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_deleteCascade
0x6b69  ldarg.0
0x6b6a  ldsfld   string [mscorlib]System.String::Empty
0x6b6f  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_description
0x6b74  ldarg.0
0x6b75  ldstr    aUsecollectionn// "UseCollectionName"
0x6b7a  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_displayOption
0x6b7f  ldarg.0
0x6b80  ldstr    aDetails// "Details"
0x6b85  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_displayArea
0x6b8a  ldarg.0
0x6b8b  ldc.i4   0x2710
0x6b90  stfld    int32 Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_navPaneOrder
0x6b95  ldarg.0
0x6b96  call     instance void [mscorlib]System.Object::.ctor()
0x6b9b  ret
```
