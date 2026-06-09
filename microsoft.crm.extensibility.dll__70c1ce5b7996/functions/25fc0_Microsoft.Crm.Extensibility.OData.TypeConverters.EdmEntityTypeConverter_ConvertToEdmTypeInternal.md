# Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::ConvertToEdmTypeInternal

- ea: `0x25fc0`
- end: `0x2653a`
- name: `Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::ConvertToEdmTypeInternal`
- size: `1402`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: `broker_com_uri`

## callees

- `0xf690`
- `0xf740`
- `0xfe00`
- `0x176a0`
- `0x17720`
- `0x17a30`
- `0x17ae0`
- `0x1f210`
- `0x1f290`
- `0x1f2c0`
- `0x1f330`
- `0x1fe00`
- `0x246f0`
- `0x25fc0`
- `0x26540`
- `0x265f0`
- `0x26630`
- `0x26b80`
- `0x2be50`
- `0x2be70`
- `0x2beb0`
- `0x2bed0`
- `0x2bf10`
- `0x2bf30`
- `0x2bf50`
- `0x2bf70`

## string_xrefs

- `0x260c1`: `_LinkEntityAliasPrefix_`

## pseudocode

```c

```

## disassembly

```asm
0x25fc0  ldarg.0
0x25fc1  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::edmEntityConversionContext
0x25fc6  callvirt instance bool Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_IsDeltaEntity()
0x25fcb  brfalse.s loc_25FE0
0x25fcd  ldarg.0
0x25fce  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::edmEntityConversionContext
0x25fd3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_EntityType()
0x25fd8  newobj   instance void Microsoft.Crm.Extensibility.OData.CrmEdmChangedEntityObject::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType edmType)
0x25fdd  stloc.0
0x25fde  br.s     loc_25FF1
0x25fe0  ldarg.0
0x25fe1  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::edmEntityConversionContext
0x25fe6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_EntityType()
0x25feb  newobj   instance void Microsoft.Crm.Extensibility.OData.CrmEdmEntityObject::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType edmType)
0x25ff0  stloc.0
0x25ff1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Web.OData]System.Web.OData.EdmEntityObject>::.ctor()
0x25ff6  stloc.1
0x25ff7  ldarg.1
0x25ff8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x25ffd  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::GetEnumerator()
0x26002  stloc.2
0x26003  br       loc_26313
0x26008  ldloc.2
0x26009  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>>::get_Current()
0x2600e  stloc.3
0x2600f  ldarg.0
0x26010  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::edmEntityConversionContext
0x26015  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_EntityType()
0x2601a  ldloca.s 3
0x2601c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x26021  ldarg.0
0x26022  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::edmEntityConversionContext
0x26027  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVersion Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_ModelVersion()
0x2602c  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType::GetEdmProperty(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVersion)
0x26031  stloc.s  4
0x26033  ldloca.s 3
0x26035  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x2603a  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x2603f  stloc.s  5
0x26041  ldc.i4.0
0x26042  stloc.s  6
0x26044  ldloca.s 3
0x26046  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x2604b  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue
0x26050  brfalse  loc_261D2
0x26055  ldloca.s 3
0x26057  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x2605c  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue
0x26061  stloc.s  7
0x26063  ldloc.s  7
0x26065  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue::get_Value()
0x2606a  brtrue.s loc_2606F
0x2606c  ldnull
0x2606d  br.s     loc_2607B
0x2606f  ldloc.s  7
0x26071  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue::get_Value()
0x26076  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x2607b  stloc.s  5
0x2607d  ldc.i4.1
0x2607e  stloc.s  6
0x26080  ldarg.0
0x26081  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::edmEntityConversionContext
0x26086  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_EntityType()
0x2608b  ldloc.s  7
0x2608d  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue::get_AttributeLogicalName()
0x26092  ldarg.0
0x26093  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::edmEntityConversionContext
0x26098  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVersion Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_ModelVersion()
0x2609d  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType::GetEdmProperty(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVersion)
0x260a2  stloc.s  4
0x260a4  ldloca.s 3
0x260a6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x260ab  ldc.i4.1
0x260ac  newarr   [mscorlib]System.Char
0x260b1  dup
0x260b2  ldc.i4.0
0x260b3  ldc.i4.s 0x2E
0x260b5  stelem.i2
0x260b6  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x260bb  ldc.i4.0
0x260bc  ldelem.ref
0x260bd  stloc.s  8
0x260bf  ldloc.s  8
0x260c1  ldstr    aLinkentityalia// "_LinkEntityAliasPrefix_"
0x260c6  callvirt instance bool [mscorlib]System.String::Contains(string)
0x260cb  brfalse.s loc_260DF
0x260cd  ldarg.0
0x260ce  ldarg.1
0x260cf  ldloc.1
0x260d0  ldloc.3
0x260d1  ldloc.s  7
0x260d3  ldloc.s  8
0x260d5  call     instance void Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::FillLinkEntityAliasedValues(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity crmTypeValue, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Web.OData]System.Web.OData.EdmEntityObject> entityReferenceMap, valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object> kvp, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue aliasValue, string aliasName)
0x260da  br       loc_2623D
0x260df  ldloc.s  4
0x260e1  brfalse.s loc_2612B
0x260e3  ldloc.s  7
0x260e5  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue::get_EntityLogicalName()
0x260ea  ldarg.0
0x260eb  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::edmEntityConversionContext
0x260f0  callvirt instance string Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_LogicalName()
0x260f5  callvirt instance bool [mscorlib]System.String::Equals(string)
0x260fa  brfalse.s loc_2612B
0x260fc  ldarg.0
0x260fd  ldarg.1
0x260fe  ldloc.s  7
0x26100  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue::get_AttributeLogicalName()
0x26105  ldloc.s  4
0x26107  ldloc.0
0x26108  ldloca.s 3
0x2610a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x2610f  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue
0x26114  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue::get_Value()
0x26119  ldloca.s 3
0x2611b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x26120  ldnull
0x26121  call     instance void Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::SetValueForEdmProperty(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, string attributeName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty edmProperty, class [System.Web.OData]System.Web.OData.EdmEntityObject edmEntity, object value, [opt] string overrideAttributeName, [opt] string aliasName)
0x26126  br       loc_2623D
0x2612b  ldloc.s  7
0x2612d  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue::get_EntityLogicalName()
0x26132  call     string Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityNameFromCrmEntityName(string entityName)
0x26137  stloc.s  9
0x26139  ldloc.s  9
0x2613b  ldarg.0
0x2613c  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::edmEntityConversionContext
0x26141  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_EdmModel()
0x26146  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Extensibility.OData.EdmUtilities::GetXrmEntityMetadataFromEdmEntityName(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x2614b  stloc.s  0xA
0x2614d  ldloc.s  9
0x2614f  ldarg.0
0x26150  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::edmEntityConversionContext
0x26155  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_EdmModel()
0x2615a  call     bool Microsoft.Crm.Extensibility.OData.CrmODataUtilities::IsEntityBaseEntity(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x2615f  brfalse.s loc_2617B
0x26161  ldloc.s  0xA
0x26163  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetDerivedEntityIdentificationAttributeName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata)
0x26168  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x2616d  stloc.s  0xC
0x2616f  ldarg.1
0x26170  ldloc.s  0xC
0x26172  ldloc.s  9
0x26174  call     string Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetDerivedEdmEntityName(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, string derivedEntityIdentificationAttributeName, string edmEntityName)
0x26179  stloc.s  9
0x2617b  ldloc.s  9
0x2617d  ldarg.0
0x2617e  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::edmEntityConversionContext
0x26183  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_EdmModel()
0x26188  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityType(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x2618d  ldloc.s  7
0x2618f  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue::get_AttributeLogicalName()
0x26194  ldarg.0
0x26195  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::edmEntityConversionContext
0x2619a  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVersion Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_ModelVersion()
0x2619f  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType::GetEdmProperty(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVersion)
0x261a4  stloc.s  0xB
0x261a6  ldarg.0
0x261a7  ldarg.1
0x261a8  ldloc.s  7
0x261aa  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue::get_AttributeLogicalName()
0x261af  ldloc.s  0xB
0x261b1  ldloc.0
0x261b2  ldloca.s 3
0x261b4  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x261b9  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue
0x261be  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue::get_Value()
0x261c3  ldloca.s 3
0x261c5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x261ca  ldnull
0x261cb  call     instance void Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::SetValueForEdmProperty(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, string attributeName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty edmProperty, class [System.Web.OData]System.Web.OData.EdmEntityObject edmEntity, object value, [opt] string overrideAttributeName, [opt] string aliasName)
0x261d0  br.s     loc_2623D
0x261d2  ldloc.s  4
0x261d4  brfalse.s loc_261F2
0x261d6  ldarg.0
0x261d7  ldarg.1
0x261d8  ldloca.s 3
0x261da  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x261df  ldloc.s  4
0x261e1  ldloc.0
0x261e2  ldloca.s 3
0x261e4  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x261e9  ldnull
0x261ea  ldnull
0x261eb  call     instance void Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::SetValueForEdmProperty(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, string attributeName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty edmProperty, class [System.Web.OData]System.Web.OData.EdmEntityObject edmEntity, object value, [opt] string overrideAttributeName, [opt] string aliasName)
0x261f0  br.s     loc_2623D
0x261f2  ldarg.0
0x261f3  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::edmEntityConversionContext
0x261f8  callvirt instance bool Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_IsCommunicationActivity()
0x261fd  brfalse.s loc_2623D
0x261ff  ldarg.0
0x26200  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::edmEntityConversionContext
0x26205  callvirt instance bool Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_IsDeltaEntity()
0x2620a  brtrue.s loc_2623D
0x2620c  ldarg.1
0x2620d  ldarg.0
0x2620e  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::edmEntityConversionContext
0x26213  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_EntityMetadata()
0x26218  ldloca.s 3
0x2621a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x2621f  ldloc.0
0x26220  isinst   Microsoft.Crm.Extensibility.OData.CrmEdmEntityObject
0x26225  ldloca.s 3
0x26227  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x2622c  ldc.i4.0
0x2622d  ldarg.0
0x2622e  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::edmEntityConversionContext
0x26233  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_EdmModel()
0x26238  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::SetValueForPartyListAttribute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity crmEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, string attributeName, class Microsoft.Crm.Extensibility.OData.CrmEdmEntityObject edmEntity, object value, bool fillAllProperties, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x2623d  ldloc.s  5
0x2623f  brfalse  loc_26313
0x26244  ldloc.0
0x26245  isinst   Microsoft.Crm.Extensibility.OData.ICrmEntityObject
0x2624a  stloc.s  0xD
0x2624c  ldloc.s  6
0x2624e  brtrue.s loc_26279
0x26250  ldarg.0
0x26251  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::edmEntityConversionContext
0x26256  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_EntityType()
0x2625b  ldloca.s 3
0x2625d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x26262  ldarg.0
0x26263  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::edmEntityConversionContext
0x26268  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVersion Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_ModelVersion()
0x2626d  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType::GetEdmProperty(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVersion)
0x26272  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x26277  br.s     loc_26280
0x26279  ldloca.s 3
0x2627b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x26280  stloc.s  0xE
0x26282  ldarg.0
0x26283  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::edmEntityConversionContext
0x26288  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyDictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship>> Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_RelationshipsLookupMap()
0x2628d  ldloca.s 3
0x2628f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x26294  ldloc.s  5
0x26296  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::GetOneToManyRelationshipByAttributeNameAndReferencedEntity(class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship>> relationshipsLookupMap, string key, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference value)
0x2629b  stloc.s  0xF
0x2629d  ldnull
0x2629e  stloc.s  0x10
0x262a0  ldloc.s  0xF
0x262a2  brfalse.s loc_262CC
0x262a4  ldloc.s  0xF
0x262a6  ldc.i4.0
0x262a7  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityRole>::.ctor(var<u1>)
0x262ac  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetMetadataCache()
0x262b1  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ODataV4NameFormatter::GetEdmNavigationPropertyNameForEntityRelationship(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityRole>, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache)
0x262b6  stloc.s  0x11
0x262b8  ldloc.s  0x11
0x262ba  stloc.s  0x10
0x262bc  ldloc.s  0xD
0x262be  ldloc.s  0xE
0x262c0  ldsfld   string Microsoft.Crm.Extensibility.OData.AnnotationsConstants::LookupEntityAssociatedNavigationPropertyAnnotation
0x262c5  ldloc.s  0x11
0x262c7  callvirt instance void Microsoft.Crm.Extensibility.OData.ICrmEntityObject::AddVocabularyAnnotation(string edmPropertyName, string annotationTerm, object annotationValue)
0x262cc  ldloc.s  0xD
0x262ce  ldloc.s  0xE
0x262d0  ldsfld   string Microsoft.Crm.Extensibility.OData.AnnotationsConstants::LookupEntityLogicalNameAnnotation
0x262d5  ldloc.s  5
0x262d7  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x262dc  callvirt instance void Microsoft.Crm.Extensibility.OData.ICrmEntityObject::AddVocabularyAnnotation(string edmPropertyName, string annotationTerm, object annotationValue)
0x262e1  ldloc.s  5
0x262e3  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Name()
0x262e8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x262ed  brtrue.s loc_26304
0x262ef  ldloc.s  0xD
0x262f1  ldloc.s  0xE
0x262f3  ldsfld   string Microsoft.Crm.Extensibility.OData.AnnotationsConstants::LookupEntityDisplayNameAnnotation
0x262f8  ldloc.s  5
0x262fa  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Name()
0x262ff  callvirt instance void Microsoft.Crm.Extensibility.OData.ICrmEntityObject::AddVocabularyAnnotation(string edmPropertyName, string annotationTerm, object annotationValue)
0x26304  ldloc.s  0x10
0x26306  brfalse.s loc_26313
0x26308  ldarg.0
0x26309  ldloc.0
0x2630a  ldloc.s  0x10
0x2630c  ldloc.s  5
0x2630e  call     instance void Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::AddReferencedEntity(class [System.Web.OData]System.Web.OData.EdmEntityObject edmEntity, string key, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference value)
0x26313  ldloc.2
0x26314  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x26319  brtrue   loc_26008
0x2631e  leave.s  loc_2632A
0x26320  ldloc.2
0x26321  brfalse.s loc_26329
0x26323  ldloc.2
0x26324  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26329  endfinally
0x2632a  ldarg.1
0x2632b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x26330  ldstr    aVersionnumber// "versionnumber"
0x26335  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0x2633a  brtrue.s loc_26389
0x2633c  ldarg.1
0x2633d  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_RowVersion()
0x26342  brfalse.s loc_26389
0x26344  ldarg.0
0x26345  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::edmEntityConversionContext
0x2634a  callvirt instance bool Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_IsDeltaEntity()
0x2634f  brtrue.s loc_2636E
0x26351  ldloc.0
0x26352  isinst   Microsoft.Crm.Extensibility.OData.CrmEdmEntityObject
0x26357  ldstr    aVersionnumber// "versionnumber"
  ... truncated ...
```
