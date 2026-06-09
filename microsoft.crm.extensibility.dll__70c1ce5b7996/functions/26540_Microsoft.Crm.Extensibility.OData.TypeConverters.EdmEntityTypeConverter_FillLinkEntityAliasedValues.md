# Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::FillLinkEntityAliasedValues

- ea: `0x26540`
- end: `0x265e1`
- name: `Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::FillLinkEntityAliasedValues`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x25fc0`

## callees

- `0xf740`
- `0x10050`
- `0x17a30`
- `0x26540`
- `0x26b80`
- `0x2bf50`

## string_xrefs

- `0x26545`: `_LinkEntityAliasPrefix_`

## pseudocode

```c

```

## disassembly

```asm
0x26540  ldarg.s  5
0x26542  stloc.0
0x26543  ldarg.s  5
0x26545  ldstr    aLinkentityalia// "_LinkEntityAliasPrefix_"
0x2654a  call     instance int32 [mscorlib]System.String::get_Length()
0x2654f  callvirt instance string [mscorlib]System.String::Substring(int32)
0x26554  starg.s  5
0x26556  ldarg.s  4
0x26558  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue::get_EntityLogicalName()
0x2655d  ldstr    aOwner// "owner"
0x26562  callvirt instance bool [mscorlib]System.String::Equals(string)
0x26567  brtrue.s loc_26572
0x26569  ldarg.s  4
0x2656b  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue::get_EntityLogicalName()
0x26570  br.s     loc_26577
0x26572  ldstr    aPrincipal// "principal"
0x26577  ldarg.0
0x26578  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::edmEntityConversionContext
0x2657d  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_EdmModel()
0x26582  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityType(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x26587  stloc.1
0x26588  ldloc.1
0x26589  ldarg.s  4
0x2658b  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue::get_AttributeLogicalName()
0x26590  call     valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVersion Microsoft.Crm.Extensibility.OData.ModelUtilities::GetModelVersion()
0x26595  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType::GetEdmProperty(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVersion)
0x2659a  stloc.2
0x2659b  ldloc.2
0x2659c  brfalse.s loc_265E0
0x2659e  ldarg.2
0x2659f  ldarg.s  5
0x265a1  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Web.OData]System.Web.OData.EdmEntityObject>::ContainsKey(var<u1>)
0x265a6  brtrue.s loc_265B6
0x265a8  ldarg.2
0x265a9  ldarg.s  5
0x265ab  ldloc.1
0x265ac  newobj   instance void Microsoft.Crm.Extensibility.OData.CrmEdmEntityObject::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType edmType)
0x265b1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Web.OData]System.Web.OData.EdmEntityObject>::Add(var<u1>, !!T0)
0x265b6  ldarg.0
0x265b7  ldarg.1
0x265b8  ldarg.s  4
0x265ba  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue::get_AttributeLogicalName()
0x265bf  ldloc.2
0x265c0  ldarg.2
0x265c1  ldarg.s  5
0x265c3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Web.OData]System.Web.OData.EdmEntityObject>::get_Item(void)
0x265c8  ldarga.s 3
0x265ca  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x265cf  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue
0x265d4  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue::get_Value()
0x265d9  ldnull
0x265da  ldloc.0
0x265db  call     instance void Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::SetValueForEdmProperty(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, string attributeName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty edmProperty, class [System.Web.OData]System.Web.OData.EdmEntityObject edmEntity, object value, [opt] string overrideAttributeName, [opt] string aliasName)
0x265e0  ret
```
