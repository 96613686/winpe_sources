# Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::SetRelatedEntitiesInEdmMetadataEntity

- ea: `0x23430`
- end: `0x2356b`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::SetRelatedEntitiesInEdmMetadataEntity`
- size: `315`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x22bb0`
- `0x22e60`

## callees

- `0x15c70`
- `0x15e10`
- `0x233d0`
- `0x23430`
- `0x23570`
- `0x24570`
- `0x29240`

## string_xrefs

- `0x23469`: ` as it is either write only or not valid`

## pseudocode

```c

```

## disassembly

```asm
0x23430  ldarg.3
0x23431  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetNavigationProperty(class [Microsoft.OData.Core]Microsoft.OData.UriParser.ExpandedNavigationSelectItem navigationItem)
0x23436  stloc.0
0x23437  ldloc.0
0x23438  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::ToEntityType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty)
0x2343d  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType
0x23442  stloc.1
0x23443  ldarg.3
0x23444  ldloc.1
0x23445  call     class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::GetSelectedPropertiesFromExpandNavigationSelectionItem(class [Microsoft.OData.Core]Microsoft.OData.UriParser.ExpandedNavigationSelectItem navigation, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType navigationEntityType)
0x2344a  stloc.2
0x2344b  ldarg.1
0x2344c  ldarg.s  4
0x2344e  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string)
0x23453  stloc.3
0x23454  ldloc.3
0x23455  ldnull
0x23456  call     bool [mscorlib]System.Reflection.PropertyInfo::op_Equality(class [mscorlib]System.Reflection.PropertyInfo, class [mscorlib]System.Reflection.PropertyInfo)
0x2345b  brfalse.s loc_2347F
0x2345d  ldc.i4   0x190
0x23462  ldstr    aCannotQueryOnT// "Cannot query on the Property "
0x23467  ldarg.s  4
0x23469  ldstr    aAsItIsEitherWr// " as it is either write only or not vali"...
0x2346e  call     string [mscorlib]System.String::Concat(string, string, string)
0x23473  ldc.i4.0
0x23474  newarr   [mscorlib]System.Object
0x23479  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x2347e  throw
0x2347f  ldloc.0
0x23480  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty::get_Type()
0x23485  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference::get_Definition()
0x2348a  isinst   [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCollectionType
0x2348f  brfalse.s loc_234E6
0x23491  ldnull
0x23492  stloc.s  4
0x23494  ldloc.3
0x23495  ldarg.2
0x23496  ldnull
0x23497  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object, object[])
0x2349c  stloc.s  5
0x2349e  ldloc.s  4
0x234a0  ldloc.s  5
0x234a2  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase[] Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::GetArrayOfMetadataBaseFromResult(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase[] relatedEntities, object result)
0x234a7  stloc.s  4
0x234a9  ldloc.s  4
0x234ab  brfalse  loc_2356A
0x234b0  ldloc.s  4
0x234b2  ldlen
0x234b3  brfalse  loc_2356A
0x234b8  ldloc.s  4
0x234ba  ldloc.1
0x234bb  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType::get_Name()
0x234c0  ldarg.0
0x234c1  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x234c6  ldloc.2
0x234c7  call     class Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection Microsoft.Crm.Extensibility.OData.EdmMetadataTypeConverter::ConvertToCrmEdmEntityObjectCollection(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase[] entitySetCollection, string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, [opt] class [mscorlib]System.Collections.Generic.IEnumerable`1<string> selectedProps)
0x234cc  stloc.s  6
0x234ce  ldloc.s  6
0x234d0  brfalse  loc_2356A
0x234d5  ldarg.s  5
0x234d7  ldloc.0
0x234d8  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x234dd  ldloc.s  6
0x234df  callvirt instance bool [System.Web.OData]System.Web.OData.Delta::TrySetPropertyValue(string, object)
0x234e4  pop
0x234e5  ret
0x234e6  ldloc.0
0x234e7  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty::get_Type()
0x234ec  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference::get_Definition()
0x234f1  isinst   [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType
0x234f6  brfalse.s loc_2356A
0x234f8  ldloc.3
0x234f9  ldarg.2
0x234fa  ldnull
0x234fb  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object, object[])
0x23500  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase
0x23505  stloc.s  7
0x23507  ldloc.s  7
0x23509  brfalse.s loc_2355B
0x2350b  ldloc.s  7
0x2350d  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x23512  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsOptionSetMetadata(class [mscorlib]System.Type crmType)
0x23517  brfalse.s loc_2353D
0x23519  ldloc.0
0x2351a  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x2351f  ldstr    aOptionset// "OptionSet"
0x23524  call     bool [mscorlib]System.String::op_Equality(string, string)
0x23529  brtrue.s loc_2353D
0x2352b  ldloc.0
0x2352c  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x23531  ldstr    aGlobaloptionse_0// "GlobalOptionSet"
0x23536  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2353b  brfalse.s loc_2355B
0x2353d  ldarg.s  5
0x2353f  ldloc.0
0x23540  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x23545  ldloc.1
0x23546  ldloc.s  7
0x23548  ldarg.0
0x23549  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x2354e  ldloc.2
0x2354f  call     class [System.Web.OData]System.Web.OData.EdmEntityObject Microsoft.Crm.Extensibility.OData.EdmMetadataTypeConverter::ConvertToEdmMetadataValue(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType edmType, object propertyValue, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, [opt] class [mscorlib]System.Collections.Generic.IEnumerable`1<string> selectedProps)
0x23554  callvirt instance bool [System.Web.OData]System.Web.OData.Delta::TrySetPropertyValue(string, object)
0x23559  pop
0x2355a  ret
0x2355b  ldarg.s  5
0x2355d  ldloc.0
0x2355e  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x23563  ldnull
0x23564  callvirt instance bool [System.Web.OData]System.Web.OData.Delta::TrySetPropertyValue(string, object)
0x23569  pop
0x2356a  ret
```
