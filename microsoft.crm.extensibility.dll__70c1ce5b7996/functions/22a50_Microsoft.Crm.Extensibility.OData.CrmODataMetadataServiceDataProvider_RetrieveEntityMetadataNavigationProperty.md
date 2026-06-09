# Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveEntityMetadataNavigationProperty

- ea: `0x22a50`
- end: `0x22b7c`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveEntityMetadataNavigationProperty`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x12fe0`

## callees

- `0xf740`
- `0x15c70`
- `0x15e70`
- `0x16fd0`
- `0x1fa70`
- `0x22a50`
- `0x22b80`
- `0x230b0`
- `0x23d50`

## pseudocode

```c

```

## disassembly

```asm
0x22a50  ldarg.2
0x22a51  ldarg.0
0x22a52  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x22a57  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::GetCrmMetadataEntityMetadataFromEdmEntityName(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x22a5c  stloc.0
0x22a5d  ldarg.0
0x22a5e  ldarg.s  4
0x22a60  ldarg.s  6
0x22a62  ldloc.0
0x22a63  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::GetXrmMetatadataEntityMetadataForNavigationProperty(string navigationPropertyName, string derivedAttributeName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata xrmEntityMetadata)
0x22a68  stloc.1
0x22a69  ldloc.1
0x22a6a  callvirt instance class [mscorlib]System.Type [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_ClrType()
0x22a6f  stloc.2
0x22a70  ldarg.0
0x22a71  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x22a76  newobj   instance void Microsoft.Crm.Extensibility.OData.MetadataQueryOptionsConverter::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x22a7b  ldloc.0
0x22a7c  ldarg.3
0x22a7d  ldarg.s  4
0x22a7f  ldloc.1
0x22a80  callvirt instance class [mscorlib]System.Type [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_ClrType()
0x22a85  ldarg.s  7
0x22a87  ldarg.s  5
0x22a89  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression Microsoft.Crm.Extensibility.OData.MetadataQueryOptionsConverter::GetEntityQueryExpressionForEntityNavigationProperty(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata xrmEntityMetadata, string entityIdValue, string edmNavigationPropertyName, class [mscorlib]System.Type navigationPropertyCrmType, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions, [opt] string navigationIdValue)
0x22a8e  stloc.3
0x22a8f  ldarg.1
0x22a90  ldloc.2
0x22a91  ldloc.3
0x22a92  ldarg.3
0x22a93  ldnull
0x22a94  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase[] Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveMetadataForEntityType(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, class [mscorlib]System.Type crmType, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression entityQuery, [opt] string entityId, [opt] string crmPropertyName)
0x22a99  stloc.s  4
0x22a9b  ldloc.s  4
0x22a9d  brfalse  loc_22B58
0x22aa2  ldloc.s  4
0x22aa4  call     T0x2B0000C6
0x22aa9  brfalse  loc_22B58
0x22aae  ldloc.s  4
0x22ab0  call     T0x2B0000C7
0x22ab5  stloc.s  5
0x22ab7  ldloc.1
0x22ab8  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntitySet [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_EdmEntitySet()
0x22abd  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::EntityType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationSource)
0x22ac2  ldloc.s  5
0x22ac4  ldarg.0
0x22ac5  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x22aca  ldnull
0x22acb  call     class [System.Web.OData]System.Web.OData.EdmEntityObject Microsoft.Crm.Extensibility.OData.EdmMetadataTypeConverter::ConvertToEdmMetadataValue(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType edmType, object propertyValue, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, [opt] class [mscorlib]System.Collections.Generic.IEnumerable`1<string> selectedProps)
0x22ad0  stloc.s  6
0x22ad2  ldnull
0x22ad3  stloc.s  7
0x22ad5  ldloc.s  6
0x22ad7  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType [System.Web.OData]System.Web.OData.EdmStructuredObject::get_ActualEdmType()
0x22adc  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType
0x22ae1  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType::get_Name()
0x22ae6  ldarg.0
0x22ae7  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x22aec  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityType(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x22af1  ldarg.s  8
0x22af3  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmStructuredType::FindProperty(string)
0x22af8  brtrue.s loc_22B1A
0x22afa  ldc.i4   0x194
0x22aff  ldstr    aPropertyWithNa// "Property with name {0} does Not Exist o"...
0x22b04  ldc.i4.2
0x22b05  newarr   [mscorlib]System.Object
0x22b0a  dup
0x22b0b  ldc.i4.0
0x22b0c  ldarg.s  8
0x22b0e  stelem.ref
0x22b0f  dup
0x22b10  ldc.i4.1
0x22b11  ldarg.s  5
0x22b13  stelem.ref
0x22b14  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x22b19  throw
0x22b1a  ldloc.s  6
0x22b1c  ldarg.s  8
0x22b1e  ldloca.s 7
0x22b20  callvirt instance bool [System.Web.OData]System.Web.OData.Delta::TryGetPropertyValue(string, object&)
0x22b25  pop
0x22b26  ldloc.s  7
0x22b28  brfalse.s loc_22B55
0x22b2a  ldloc.s  7
0x22b2c  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x22b31  ldtoken  [mscorlib]System.DateTimeOffset
0x22b36  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x22b3b  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x22b40  brfalse.s loc_22B55
0x22b42  ldloc.s  7
0x22b44  callvirt instance string [mscorlib]System.Object::ToString()
0x22b49  call     valuetype [mscorlib]System.DateTimeOffset Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ConvertToDateTimeOffset(object propertyValue)
0x22b4e  box      [mscorlib]System.DateTimeOffset
0x22b53  stloc.s  7
0x22b55  ldloc.s  7
0x22b57  ret
0x22b58  ldc.i4   0x194
0x22b5d  ldstr    aNavigationProp_0// "Navigation property {0} With Id = {1} d"...
0x22b62  ldc.i4.3
0x22b63  newarr   [mscorlib]System.Object
0x22b68  dup
0x22b69  ldc.i4.0
0x22b6a  ldarg.s  4
0x22b6c  stelem.ref
0x22b6d  dup
0x22b6e  ldc.i4.1
0x22b6f  ldarg.s  5
0x22b71  stelem.ref
0x22b72  dup
0x22b73  ldc.i4.2
0x22b74  ldarg.3
0x22b75  stelem.ref
0x22b76  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x22b7b  throw
```
