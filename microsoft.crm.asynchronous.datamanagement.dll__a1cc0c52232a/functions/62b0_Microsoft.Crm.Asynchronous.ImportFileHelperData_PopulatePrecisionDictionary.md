# Microsoft.Crm.Asynchronous.ImportFileHelperData::PopulatePrecisionDictionary

- ea: `0x62b0`
- end: `0x63ed`
- name: `Microsoft.Crm.Asynchronous.ImportFileHelperData::PopulatePrecisionDictionary`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x14cb0`

## callees

- `0x3b80`
- `0x6220`
- `0x62b0`
- `0x63f0`
- `0x6490`
- `0x6e60`

## string_xrefs

- `0x62b1`: `parameter crmServiceInSystemUserContext should not be null`

## pseudocode

```c

```

## disassembly

```asm
0x62b0  ldarg.1
0x62b1  ldstr    aParameterCrmse// "parameter crmServiceInSystemUserContext"...
0x62b6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x62bb  ldarg.0
0x62bc  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Asynchronous.ImportFileHelperData::_columnMappingIdToColumnMappingObjectDictionary
0x62c1  brfalse.s loc_62FA
0x62c3  ldarg.0
0x62c4  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Asynchronous.ImportFileHelperData::_columnMappingIdToColumnMappingObjectDictionary
0x62c9  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x62ce  brfalse.s loc_62FA
0x62d0  ldarg.0
0x62d1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Asynchronous.ImportFileHelperData::_headerColumnToParsedTableColumnIndexDictionary
0x62d6  brfalse.s loc_62FA
0x62d8  ldarg.0
0x62d9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Asynchronous.ImportFileHelperData::_headerColumnToParsedTableColumnIndexDictionary
0x62de  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Count()
0x62e3  brfalse.s loc_62FA
0x62e5  ldarg.0
0x62e6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata> Microsoft.Crm.Asynchronous.ImportFileHelperData::_schemaColumnNameToAttributeMetadataDictionary
0x62eb  brfalse.s loc_62FA
0x62ed  ldarg.0
0x62ee  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata> Microsoft.Crm.Asynchronous.ImportFileHelperData::_schemaColumnNameToAttributeMetadataDictionary
0x62f3  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Count()
0x62f8  brtrue.s loc_6306
0x62fa  ldarg.0
0x62fb  call     instance void Microsoft.Crm.Asynchronous.ImportFileHelperData::PopulateDictionaries()
0x6300  ldarg.0
0x6301  call     instance void Microsoft.Crm.Asynchronous.ImportFileHelperData::PopulateAttributeMetadata()
0x6306  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x630b  ldarg.0
0x630c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportFileHelperData::_organizationId
0x6311  ldarg.0
0x6312  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportFileHelperData::_organizationId
0x6317  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x631c  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x6321  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_PricingDecimalPrecision()
0x6326  stloc.0
0x6327  ldarg.0
0x6328  ldarg.1
0x6329  call     instance int32 Microsoft.Crm.Asynchronous.ImportFileHelperData::GetMaximumPrecisionAcrossCurrencies(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService crmServiceInSystemUserContext)
0x632e  stloc.1
0x632f  ldarg.0
0x6330  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Tuple`2<int32, class [mscorlib]System.Type>>::.ctor()
0x6335  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Tuple`2<int32, class [mscorlib]System.Type>> Microsoft.Crm.Asynchronous.ImportFileHelperData::_columnIndexToAttributePrecisionDictionary
0x633a  ldarg.0
0x633b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Asynchronous.ImportFileHelperData::_columnMappingIdToColumnMappingObjectDictionary
0x6340  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x6345  stloc.2
0x6346  br       loc_63D0
0x634b  ldloca.s 2
0x634d  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x6352  stloc.3
0x6353  ldloca.s 3
0x6355  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Value()
0x635a  dup
0x635b  ldstr    aTargetattribut// "targetattributename"
0x6360  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0x6365  stloc.s  4
0x6367  ldstr    aSourceattribut// "sourceattributename"
0x636c  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0x6371  stloc.s  5
0x6373  ldarg.0
0x6374  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Asynchronous.ImportFileHelperData::_headerColumnToParsedTableColumnIndexDictionary
0x6379  ldloc.s  5
0x637b  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::ContainsKey(var<u1>)
0x6380  brfalse.s loc_63D0
0x6382  ldarg.0
0x6383  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Asynchronous.ImportFileHelperData::_headerColumnToParsedTableColumnIndexDictionary
0x6388  ldloc.s  5
0x638a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0x638f  ldc.i4.5
0x6390  sub
0x6391  stloc.s  6
0x6393  ldarg.0
0x6394  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata> Microsoft.Crm.Asynchronous.ImportFileHelperData::_schemaColumnNameToAttributeMetadataDictionary
0x6399  ldloc.s  4
0x639b  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::ContainsKey(var<u1>)
0x63a0  brfalse.s loc_63D0
0x63a2  ldarg.0
0x63a3  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata> Microsoft.Crm.Asynchronous.ImportFileHelperData::_schemaColumnNameToAttributeMetadataDictionary
0x63a8  ldloc.s  4
0x63aa  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(void)
0x63af  stloc.s  7
0x63b1  ldarg.0
0x63b2  ldloc.s  7
0x63b4  ldloc.1
0x63b5  ldloc.0
0x63b6  call     instance class [mscorlib]System.Tuple`2<int32, class [mscorlib]System.Type> Microsoft.Crm.Asynchronous.ImportFileHelperData::GetPrecisionAndType(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMetadata, int32 maxPrecisionAcrossCurrencies, int32 pricingDecimalPrecision)
0x63bb  stloc.s  8
0x63bd  ldloc.s  8
0x63bf  brfalse.s loc_63D0
0x63c1  ldarg.0
0x63c2  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Tuple`2<int32, class [mscorlib]System.Type>> Microsoft.Crm.Asynchronous.ImportFileHelperData::_columnIndexToAttributePrecisionDictionary
0x63c7  ldloc.s  6
0x63c9  ldloc.s  8
0x63cb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Tuple`2<int32, class [mscorlib]System.Type>>::Add(var<u1>, !!T0)
0x63d0  ldloca.s 2
0x63d2  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::MoveNext()
0x63d7  brtrue   loc_634B
0x63dc  leave.s  loc_63EC
0x63de  ldloca.s 2
0x63e0  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>
0x63e6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x63eb  endfinally
0x63ec  ret
```
