# Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::GetXrmEntityMetadataOfNavigationPropertyName

- ea: `0x23ec0`
- end: `0x23f81`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::GetXrmEntityMetadataOfNavigationPropertyName`
- size: `193`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x16fd0`
- `0x21f90`
- `0x22480`
- `0x225f0`
- `0x22b80`
- `0x23610`

## callees

- `0x23ec0`
- `0x23f90`

## string_xrefs

- `0x23ef9`: ` as it is either write only or not valid`

## pseudocode

```c

```

## disassembly

```asm
0x23ec0  ldarg.0
0x23ec1  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntitySet [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_EdmEntitySet()
0x23ec6  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::EntityType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationSource)
0x23ecb  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType
0x23ed0  stloc.0
0x23ed1  ldarg.1
0x23ed2  ldarg.0
0x23ed3  ldloc.0
0x23ed4  call     string Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::GetCrmRelationshipNameFromEdmNavigationPropertyName(string edmNavigationPropertyName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata xrmEntityMetadata, class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType entityType)
0x23ed9  stloc.1
0x23eda  ldarg.0
0x23edb  callvirt instance class [mscorlib]System.Type [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_ClrType()
0x23ee0  ldloc.1
0x23ee1  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string)
0x23ee6  ldnull
0x23ee7  call     bool [mscorlib]System.Reflection.PropertyInfo::op_Equality(class [mscorlib]System.Reflection.PropertyInfo, class [mscorlib]System.Reflection.PropertyInfo)
0x23eec  brfalse.s loc_23F0F
0x23eee  ldc.i4   0x190
0x23ef3  ldstr    aCannotQueryOnT// "Cannot query on the Property "
0x23ef8  ldloc.1
0x23ef9  ldstr    aAsItIsEitherWr// " as it is either write only or not vali"...
0x23efe  call     string [mscorlib]System.String::Concat(string, string, string)
0x23f03  ldc.i4.0
0x23f04  newarr   [mscorlib]System.Object
0x23f09  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x23f0e  throw
0x23f0f  ldarg.0
0x23f10  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntitySet [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_EdmEntitySet()
0x23f15  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::EntityType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationSource)
0x23f1a  ldarg.1
0x23f1b  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType::FindProperty(string)
0x23f20  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmNavigationProperty
0x23f25  stloc.3
0x23f26  ldloc.3
0x23f27  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmProperty::get_Type()
0x23f2c  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference::get_Definition()
0x23f31  isinst   [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCollectionType
0x23f36  brfalse.s loc_23F64
0x23f38  ldloc.3
0x23f39  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmProperty::get_Type()
0x23f3e  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference::get_Definition()
0x23f43  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCollectionType
0x23f48  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCollectionType::get_ElementType()
0x23f4d  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference::get_Definition()
0x23f52  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType
0x23f57  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType::GetCustomState()
0x23f5c  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata
0x23f61  stloc.2
0x23f62  br.s     loc_23F7F
0x23f64  ldloc.3
0x23f65  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmProperty::get_Type()
0x23f6a  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference::get_Definition()
0x23f6f  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType
0x23f74  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType::GetCustomState()
0x23f79  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata
0x23f7e  stloc.2
0x23f7f  ldloc.2
0x23f80  ret
```
