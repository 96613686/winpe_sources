# Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveEdmEntityProperty

- ea: `0x21ec0`
- end: `0x21f8c`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveEdmEntityProperty`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x11600`

## callees

- `0x15c90`
- `0x15f30`
- `0x21ec0`
- `0x22fd0`
- `0x23060`
- `0x230b0`
- `0x23d50`
- `0x23e00`
- `0x24570`
- `0x24640`

## pseudocode

```c

```

## disassembly

```asm
0x21ec0  ldnull
0x21ec1  stloc.0
0x21ec2  ldarg.2
0x21ec3  ldarg.0
0x21ec4  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x21ec9  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::GetCrmMetadataEntityMetadataFromEdmEntityName(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x21ece  dup
0x21ecf  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntitySet [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_EdmEntitySet()
0x21ed4  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::EntityType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationSource)
0x21ed9  ldarg.s  4
0x21edb  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType::FindProperty(string)
0x21ee0  stloc.1
0x21ee1  ldloc.1
0x21ee2  call     string Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::GetCrmMetadataAttributeNameFromMetadataEdmAttributeName(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty edmProperty)
0x21ee7  stloc.2
0x21ee8  callvirt instance class [mscorlib]System.Type [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_ClrType()
0x21eed  stloc.3
0x21eee  ldnull
0x21eef  stloc.s  4
0x21ef1  ldloc.3
0x21ef2  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsManagedPropertyMetadata(class [mscorlib]System.Type xrmType)
0x21ef7  brfalse.s loc_21F04
0x21ef9  ldarg.1
0x21efa  ldarg.3
0x21efb  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManagedPropertyMetadata Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveManagedProeprtyMetadata(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string entityIdValue)
0x21f00  stloc.s  4
0x21f02  br.s     loc_21F4A
0x21f04  ldloc.3
0x21f05  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsOptionSetMetadata(class [mscorlib]System.Type crmType)
0x21f0a  brfalse.s loc_21F17
0x21f0c  ldarg.1
0x21f0d  ldarg.3
0x21f0e  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OptionSetMetadataBase Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveOptionSetMetadata(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string entityIdValue)
0x21f13  stloc.s  4
0x21f15  br.s     loc_21F4A
0x21f17  ldarg.2
0x21f18  ldarg.3
0x21f19  ldloc.2
0x21f1a  ldarg.0
0x21f1b  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x21f20  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression Microsoft.Crm.Extensibility.OData.MetadataQueryOptionsConverter::GetEntityQueryExpressionForEdmEntityProperty(string edmEntityName, string key, string crmPropetyName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x21f25  stloc.s  5
0x21f27  ldarg.1
0x21f28  ldloc.3
0x21f29  ldloc.s  5
0x21f2b  ldnull
0x21f2c  ldnull
0x21f2d  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase[] Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveMetadataForEntityType(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, class [mscorlib]System.Type crmType, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression entityQuery, [opt] string entityId, [opt] string crmPropertyName)
0x21f32  stloc.s  6
0x21f34  ldloc.s  6
0x21f36  brfalse.s loc_21F4A
0x21f38  ldloc.s  6
0x21f3a  call     T0x2B0000C6
0x21f3f  brfalse.s loc_21F4A
0x21f41  ldloc.s  6
0x21f43  call     T0x2B0000C7
0x21f48  stloc.s  4
0x21f4a  ldloc.s  4
0x21f4c  brfalse.s loc_21F60
0x21f4e  ldloc.3
0x21f4f  ldloc.2
0x21f50  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string)
0x21f55  ldloc.s  4
0x21f57  ldnull
0x21f58  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object, object[])
0x21f5d  stloc.0
0x21f5e  br.s     loc_21F7E
0x21f60  ldc.i4   0x194
0x21f65  ldstr    a0WithId1DoesNo// "{0} With Id = {1} does not exist."
0x21f6a  ldc.i4.2
0x21f6b  newarr   [mscorlib]System.Object
0x21f70  dup
0x21f71  ldc.i4.0
0x21f72  ldarg.2
0x21f73  stelem.ref
0x21f74  dup
0x21f75  ldc.i4.1
0x21f76  ldarg.3
0x21f77  stelem.ref
0x21f78  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x21f7d  throw
0x21f7e  ldloc.1
0x21f7f  ldloc.0
0x21f80  ldarg.0
0x21f81  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x21f86  call     object Microsoft.Crm.Extensibility.OData.EdmMetadataTypeConverter::ConvertToEdmPropertyValue(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty edmProperty, object propertyValue, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x21f8b  ret
```
