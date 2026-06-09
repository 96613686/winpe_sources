# Microsoft.Crm.Extensibility.OData.TypeConverters.EdmComplexTypeConverter::SetOrAddToCrmPropertyType

- ea: `0x25db0`
- end: `0x25e5e`
- name: `Microsoft.Crm.Extensibility.OData.TypeConverters.EdmComplexTypeConverter::SetOrAddToCrmPropertyType`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x257f0`

## callees

- `0x13a00`
- `0x25490`
- `0x25b60`
- `0x25db0`
- `0x27ec0`

## string_xrefs

- `0x25e3b`: `edm Value should be complex type for Generic Collection of Dictionary Types.`

## pseudocode

```c

```

## disassembly

```asm
0x25db0  ldarg.2
0x25db1  ldarg.3
0x25db2  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string)
0x25db7  stloc.0
0x25db8  ldloc.0
0x25db9  callvirt instance bool [mscorlib]System.Reflection.PropertyInfo::get_CanWrite()
0x25dbe  brfalse.s loc_25DE7
0x25dc0  ldarg.s  5
0x25dc2  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty::get_Type()
0x25dc7  ldarg.0
0x25dc8  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.TypeConverters.EdmComplexTypeConverter::edmModel
0x25dcd  ldarg.2
0x25dce  ldarg.3
0x25dcf  ldnull
0x25dd0  call     class Microsoft.Crm.Extensibility.OData.TypeConverters.IEdmTypeConverter Microsoft.Crm.Extensibility.OData.EdmTypeConverter::GetEdmTypeConverter(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference edmTypeReference, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, [opt] object clrOrComplexObjectType, [opt] string propertyName, [opt] object propertyValue)
0x25dd5  ldarg.s  4
0x25dd7  callvirt instance object Microsoft.Crm.Extensibility.OData.TypeConverters.IEdmTypeConverter::ConvertToCrmType(object edmTypeValue)
0x25ddc  stloc.1
0x25ddd  ldloc.0
0x25dde  ldarg.1
0x25ddf  ldloc.1
0x25de0  ldnull
0x25de1  callvirt instance void [mscorlib]System.Reflection.PropertyInfo::SetValue(object, object, object[])
0x25de6  ret
0x25de7  ldloc.0
0x25de8  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.PropertyInfo::get_PropertyType()
0x25ded  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EdmCollectionProvider::IsCollection(class [mscorlib]System.Type)
0x25df2  brfalse.s loc_25E1E
0x25df4  ldloc.0
0x25df5  ldarg.1
0x25df6  ldnull
0x25df7  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object, object[])
0x25dfc  stloc.1
0x25dfd  ldarg.s  5
0x25dff  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty::get_Type()
0x25e04  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmCollectionTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeSemantics::AsCollection(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x25e09  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::ElementType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmCollectionTypeReference)
0x25e0e  ldloc.1
0x25e0f  ldarg.s  4
0x25e11  ldarg.0
0x25e12  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.TypeConverters.EdmComplexTypeConverter::edmModel
0x25e17  call     object Microsoft.Crm.Extensibility.OData.TypeConverters.EdmCollectionTypeConverter::PopulateCollection(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference elementTypeReference, object collectionObject, object edmCollectionObject, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x25e1c  pop
0x25e1d  ret
0x25e1e  ldloc.0
0x25e1f  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.PropertyInfo::get_PropertyType()
0x25e24  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EdmCollectionProvider::IsGenericCollectionOfDictionaryType(class [mscorlib]System.Type)
0x25e29  brfalse.s loc_25E5D
0x25e2b  ldarg.s  4
0x25e2d  isinst   [System.Web.OData]System.Web.OData.EdmComplexObject
0x25e32  stloc.2
0x25e33  ldloc.2
0x25e34  brtrue.s loc_25E4C
0x25e36  ldc.i4   0x190
0x25e3b  ldstr    aEdmValueShould// "edm Value should be complex type for Ge"...
0x25e40  ldc.i4.0
0x25e41  newarr   [mscorlib]System.Object
0x25e46  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x25e4b  throw
0x25e4c  ldloc.0
0x25e4d  ldarg.1
0x25e4e  ldnull
0x25e4f  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object, object[])
0x25e54  stloc.1
0x25e55  ldarg.0
0x25e56  ldloc.2
0x25e57  ldloc.1
0x25e58  call     instance void Microsoft.Crm.Extensibility.OData.TypeConverters.EdmComplexTypeConverter::PopulateGenericCollectionOfDictionaryCrmType(class [System.Web.OData]System.Web.OData.EdmComplexObject edmTypeValue, object crmTypeObject)
0x25e5d  ret
```
