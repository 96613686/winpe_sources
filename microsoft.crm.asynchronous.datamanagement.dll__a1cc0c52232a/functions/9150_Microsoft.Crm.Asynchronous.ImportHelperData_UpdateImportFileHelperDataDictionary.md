# Microsoft.Crm.Asynchronous.ImportHelperData::UpdateImportFileHelperDataDictionary

- ea: `0x9150`
- end: `0x918c`
- name: `Microsoft.Crm.Asynchronous.ImportHelperData::UpdateImportFileHelperDataDictionary`
- size: `60`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0xd1c0`
- `0xe130`
- `0xe9b0`
- `0x14370`
- `0x165d0`
- `0x19ee0`
- `0x1a360`

## callees

- `0x6200`

## pseudocode

```c

```

## disassembly

```asm
0x9150  ldarg.0
0x9151  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData> Microsoft.Crm.Asynchronous.ImportHelperData::_importFileIdToImportFileHelperDataDictionary
0x9156  ldarg.1
0x9157  ldarg.0
0x9158  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Asynchronous.ImportHelperData::_importFileIdToImportFileObjectDictionary
0x915d  ldarg.1
0x915e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(void)
0x9163  ldarg.0
0x9164  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.ImportHelperData::_crmService
0x9169  ldarg.0
0x916a  ldfld    bool Microsoft.Crm.Asynchronous.ImportHelperData::_isImportFromApp
0x916f  ldarg.0
0x9170  ldfld    int32 Microsoft.Crm.Asynchronous.ImportHelperData::_importMode
0x9175  ldarg.0
0x9176  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportHelperData::_organizationId
0x917b  ldarg.0
0x917c  ldfld    int32 Microsoft.Crm.Asynchronous.ImportHelperData::_languageCode
0x9181  newobj   instance void Microsoft.Crm.Asynchronous.ImportFileHelperData::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity impfile, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService crmService, bool isImportFromApp, int32 importMode, valuetype [mscorlib]System.Guid organizationId, int32 languageCode)
0x9186  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData>::set_Item(var<u1>, !!T0)
0x918b  ret
```
