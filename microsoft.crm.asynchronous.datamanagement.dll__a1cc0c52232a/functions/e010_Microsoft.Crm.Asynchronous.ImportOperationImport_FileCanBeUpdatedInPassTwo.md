# Microsoft.Crm.Asynchronous.ImportOperationImport::FileCanBeUpdatedInPassTwo

- ea: `0xe010`
- end: `0xe0a9`
- name: `Microsoft.Crm.Asynchronous.ImportOperationImport::FileCanBeUpdatedInPassTwo`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0xc5a0`

## callees

- `0x3b80`
- `0x6060`
- `0x6090`
- `0x61d0`
- `0x8f70`
- `0xe010`

## pseudocode

```c

```

## disassembly

```asm
0xe010  ldarg.0
0xe011  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0xe016  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileHelperDataDictionary()
0xe01b  ldarg.1
0xe01c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData>::get_Item(void)
0xe021  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>> Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ColumnMappingIdToLookupMappingCollectionDictionary()
0xe026  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>>::get_Count()
0xe02b  ldc.i4.0
0xe02c  ble.s    loc_E0A4
0xe02e  ldarg.0
0xe02f  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0xe034  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileHelperDataDictionary()
0xe039  ldarg.1
0xe03a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData>::get_Item(void)
0xe03f  stloc.0
0xe040  ldloc.0
0xe041  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>> Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ColumnMappingIdToLookupMappingCollectionDictionary()
0xe046  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>>::GetEnumerator()
0xe04b  stloc.1
0xe04c  br.s     loc_E08B
0xe04e  ldloca.s 1
0xe050  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>>::get_Current()
0xe055  stloc.2
0xe056  ldloc.0
0xe057  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ColumnMappingIdToColumnMappingObjectDictionary()
0xe05c  ldloca.s 2
0xe05e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>>::get_Key()
0xe063  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(void)
0xe068  ldstr    aTargetattribut// "targetattributename"
0xe06d  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0xe072  stloc.3
0xe073  ldloc.0
0xe074  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata> Microsoft.Crm.Asynchronous.ImportFileHelperData::get_SchemaColumnNameToAttributeMetadataDictionary()
0xe079  ldloc.3
0xe07a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(void)
0xe07f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForUpdate()
0xe084  brtrue.s loc_E08B
0xe086  ldc.i4.0
0xe087  stloc.s  4
0xe089  leave.s  loc_E0A6
0xe08b  ldloca.s 1
0xe08d  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>>::MoveNext()
0xe092  brtrue.s loc_E04E
0xe094  leave.s  loc_E0A4
0xe096  ldloca.s 1
0xe098  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>>
0xe09e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe0a3  endfinally
0xe0a4  ldc.i4.1
0xe0a5  ret
0xe0a6  ldloc.s  4
0xe0a8  ret
```
