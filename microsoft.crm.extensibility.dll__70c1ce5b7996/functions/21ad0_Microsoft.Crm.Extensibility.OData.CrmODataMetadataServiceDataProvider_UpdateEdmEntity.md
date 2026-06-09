# Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::UpdateEdmEntity

- ea: `0x21ad0`
- end: `0x21b8f`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::UpdateEdmEntity`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x11e10`

## callees

- `0xf880`
- `0x15db0`
- `0x179c0`
- `0x17a10`
- `0x18f80`
- `0x214c0`
- `0x21ad0`
- `0x236c0`
- `0x24e60`
- `0x26e90`

## pseudocode

```c

```

## disassembly

```asm
0x21ad0  ldarg.2
0x21ad1  ldarg.0
0x21ad2  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x21ad7  call     string Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityCollectionName(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x21adc  stloc.0
0x21add  ldnull
0x21ade  stloc.1
0x21adf  ldarg.3
0x21ae0  stloc.2
0x21ae1  ldarg.3
0x21ae2  ldloca.s 3
0x21ae4  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x21ae9  brfalse.s loc_21AFC
0x21aeb  ldarg.s  4
0x21aed  ldloc.3
0x21aee  ldarg.0
0x21aef  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x21af4  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase Microsoft.Crm.Extensibility.OData.EdmMetadataTypeConverter::ConvertToCrmEntity(class [System.Web.OData]System.Web.OData.EdmEntityObject edmEntity, valuetype [mscorlib]System.Guid entityId, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x21af9  stloc.1
0x21afa  br.s     loc_21B59
0x21afc  ldarg.s  4
0x21afe  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType [System.Web.OData]System.Web.OData.EdmStructuredObject::get_ActualEdmType()
0x21b03  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType
0x21b08  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType::get_Name()
0x21b0d  ldarg.0
0x21b0e  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x21b13  newobj   instance void Microsoft.Crm.Extensibility.OData.TypeConverters.EdmMetadataEntityTypeConverter::.ctor(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x21b18  ldarg.s  4
0x21b1a  callvirt instance object class Microsoft.Crm.Extensibility.OData.TypeConverters.EdmTypeConverterBase`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase, class [System.Web.OData]System.Web.OData.EdmEntityObject>::ConvertToCrmType(object)
0x21b1f  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase
0x21b24  stloc.1
0x21b25  ldarg.3
0x21b26  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ParseAlternateKeys(string key)
0x21b2b  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Values()
0x21b30  call     T0x2B00008E
0x21b35  stloc.2
0x21b36  ldloc.1
0x21b37  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x21b3c  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata
0x21b41  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x21b46  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x21b4b  brfalse.s loc_21B59
0x21b4d  ldloc.1
0x21b4e  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata
0x21b53  ldloc.2
0x21b54  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_LogicalName(string)
0x21b59  ldarg.0
0x21b5a  ldarg.1
0x21b5b  ldarg.2
0x21b5c  ldloc.1
0x21b5d  ldarg.s  4
0x21b5f  ldc.i4.2
0x21b60  ldnull
0x21b61  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::ExecuteMetadataCreateUpdate(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string edmEntityName, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase entity, class [System.Web.OData]System.Web.OData.EdmEntityObject entityObject, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrimitiveOperationType operationMethod, [opt] class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection boundParameterCollection)
0x21b66  pop
0x21b67  ldarg.1
0x21b68  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x21b6d  ldloc.0
0x21b6e  ldarg.3
0x21b6f  ldarg.1
0x21b70  call     class Microsoft.Crm.Extensibility.OData.CrmEdmEntityReference Microsoft.Crm.Extensibility.OData.CrmEdmEntityReference::CreateCrmEdmEntityReference(string edmEntityName, string edmEntityKey, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x21b75  callvirt instance class [System]System.Uri Microsoft.Crm.Extensibility.OData.CrmEdmEntityReference::get_Link()
0x21b7a  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataHeaders::SetODataEntityIdInResponse(class [System]System.Uri oDataEntityId)
0x21b7f  ldloc.1
0x21b80  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase::get_MetadataId()
0x21b85  stloc.s  4
0x21b87  ldloca.s 4
0x21b89  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x21b8e  ret
```
