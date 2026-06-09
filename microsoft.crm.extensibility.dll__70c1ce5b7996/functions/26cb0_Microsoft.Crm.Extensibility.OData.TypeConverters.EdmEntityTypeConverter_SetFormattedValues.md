# Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::SetFormattedValues

- ea: `0x26cb0`
- end: `0x26ce1`
- name: `Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::SetFormattedValues`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x26b80`

## callees

- `0x17720`
- `0x17ae0`
- `0x26cb0`
- `0x2be50`

## string_xrefs

- `0x26cb0`: `OData.Community.Display.V1.FormattedValue`

## pseudocode

```c

```

## disassembly

```asm
0x26cb0  ldstr    aOdataCommunity// "OData.Community.Display.V1.FormattedVal"...
0x26cb5  stloc.0
0x26cb6  ldarg.0
0x26cb7  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::edmEntityConversionContext
0x26cbc  callvirt instance bool Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_IsDeltaEntity()
0x26cc1  brtrue.s loc_26CD2
0x26cc3  ldarg.1
0x26cc4  isinst   Microsoft.Crm.Extensibility.OData.CrmEdmEntityObject
0x26cc9  ldarg.2
0x26cca  ldloc.0
0x26ccb  ldarg.3
0x26ccc  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmEdmEntityObject::AddVocabularyAnnotation(string edmPropertyName, string annotationTerm, object annotationValue)
0x26cd1  ret
0x26cd2  ldarg.1
0x26cd3  isinst   Microsoft.Crm.Extensibility.OData.CrmEdmChangedEntityObject
0x26cd8  ldarg.2
0x26cd9  ldloc.0
0x26cda  ldarg.3
0x26cdb  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmEdmChangedEntityObject::AddVocabularyAnnotation(string edmPropertyName, string annotationTerm, object annotationValue)
0x26ce0  ret
```
