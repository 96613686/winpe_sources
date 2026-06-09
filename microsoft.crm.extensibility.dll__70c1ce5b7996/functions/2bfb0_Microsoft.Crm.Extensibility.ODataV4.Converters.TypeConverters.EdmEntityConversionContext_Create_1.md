# Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::Create_1

- ea: `0x2bfb0`
- end: `0x2c06e`
- name: `Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::Create_1`
- size: `190`
- prototype: ``
- caller_count: `3`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x13460`
- `0x2bf90`
- `0x2bfa0`

## callees

- `0xf690`
- `0xf740`
- `0xfe00`
- `0x10050`
- `0x1f290`
- `0x1f2c0`
- `0x1f330`
- `0x1fd90`
- `0x20ec0`
- `0x2be60`
- `0x2be80`
- `0x2be90`
- `0x2bea0`
- `0x2bec0`
- `0x2bed0`
- `0x2bee0`
- `0x2bef0`
- `0x2bf00`
- `0x2bf20`
- `0x2bf40`
- `0x2bf60`
- `0x2bf80`
- `0x2bfb0`
- `0x2c070`

## pseudocode

```c

```

## disassembly

```asm
0x2bfb0  newobj   instance void Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::.ctor()
0x2bfb5  stloc.0
0x2bfb6  ldloc.0
0x2bfb7  ldarg.1
0x2bfb8  callvirt instance void Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::set_EdmModel(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel value)
0x2bfbd  ldloc.0
0x2bfbe  ldarg.3
0x2bfbf  callvirt instance void Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::set_IsDeltaEntity(bool value)
0x2bfc4  ldloc.0
0x2bfc5  ldarg.0
0x2bfc6  callvirt instance void Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::set_LogicalName(string value)
0x2bfcb  ldloc.0
0x2bfcc  ldarg.0
0x2bfcd  call     string Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityNameFromCrmEntityName(string entityName)
0x2bfd2  callvirt instance void Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::set_EdmEntityName(string value)
0x2bfd7  ldloc.0
0x2bfd8  ldloc.0
0x2bfd9  callvirt instance string Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_EdmEntityName()
0x2bfde  ldarg.1
0x2bfdf  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Extensibility.OData.EdmUtilities::GetXrmEntityMetadataFromEdmEntityName(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x2bfe4  callvirt instance void Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::set_EntityMetadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata value)
0x2bfe9  ldloc.0
0x2bfea  callvirt instance string Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_EdmEntityName()
0x2bfef  ldarg.1
0x2bff0  call     bool Microsoft.Crm.Extensibility.OData.CrmODataUtilities::IsEntityBaseEntity(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x2bff5  brfalse.s loc_2C02D
0x2bff7  ldloc.0
0x2bff8  ldloc.0
0x2bff9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_EntityMetadata()
0x2bffe  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetDerivedEntityIdentificationAttributeName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata)
0x2c003  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x2c008  callvirt instance void Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::set_InheritanceTypeAttributeName(string value)
0x2c00d  ldloc.0
0x2c00e  callvirt instance string Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_InheritanceTypeAttributeName()
0x2c013  brfalse.s loc_2C02D
0x2c015  ldloc.0
0x2c016  ldarg.2
0x2c017  ldloc.0
0x2c018  callvirt instance string Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_InheritanceTypeAttributeName()
0x2c01d  ldloc.0
0x2c01e  callvirt instance string Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_EdmEntityName()
0x2c023  call     string Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetDerivedEdmEntityName(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, string derivedEntityIdentificationAttributeName, string edmEntityName)
0x2c028  callvirt instance void Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::set_EdmEntityName(string value)
0x2c02d  ldloc.0
0x2c02e  ldloc.0
0x2c02f  callvirt instance string Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_EdmEntityName()
0x2c034  ldarg.1
0x2c035  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityType(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x2c03a  callvirt instance void Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::set_EntityType(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType value)
0x2c03f  ldloc.0
0x2c040  call     valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVersion Microsoft.Crm.Extensibility.OData.ModelUtilities::GetModelVersion()
0x2c045  callvirt instance void Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::set_ModelVersion(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVersion value)
0x2c04a  ldloc.0
0x2c04b  ldloc.0
0x2c04c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_EntityMetadata()
0x2c051  call     bool Microsoft.Crm.Extensibility.OData.CrmODataUtilities::IsCommunicationActivity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata)
0x2c056  callvirt instance void Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::set_IsCommunicationActivity(bool value)
0x2c05b  ldloc.0
0x2c05c  ldloc.0
0x2c05d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_EntityMetadata()
0x2c062  call     class [mscorlib]System.Collections.ObjectModel.ReadOnlyDictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship>> Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetOneToManyRelationshipsMap(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata metadata)
0x2c067  callvirt instance void Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::set_RelationshipsLookupMap(class [mscorlib]System.Collections.ObjectModel.ReadOnlyDictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship>> value)
0x2c06c  ldloc.0
0x2c06d  ret
```
