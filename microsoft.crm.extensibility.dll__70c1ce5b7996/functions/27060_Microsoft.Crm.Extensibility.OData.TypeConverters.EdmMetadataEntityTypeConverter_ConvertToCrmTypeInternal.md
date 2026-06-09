# Microsoft.Crm.Extensibility.OData.TypeConverters.EdmMetadataEntityTypeConverter::ConvertToCrmTypeInternal

- ea: `0x27060`
- end: `0x271e0`
- name: `Microsoft.Crm.Extensibility.OData.TypeConverters.EdmMetadataEntityTypeConverter::ConvertToCrmTypeInternal`
- size: `384`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x23d50`
- `0x23d90`
- `0x23e00`
- `0x27060`
- `0x271e0`
- `0x27410`

## string_xrefs

- `0x2710e`: `value should be an EdmEntityObject or EdmEntityObjectCollection or Uri`

## pseudocode

```c

```

## disassembly

```asm
0x27060  ldnull
0x27061  stloc.1
0x27062  ldarg.1
0x27063  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType [System.Web.OData]System.Web.OData.EdmStructuredObject::get_ActualEdmType()
0x27068  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType
0x2706d  stloc.2
0x2706e  ldarg.0
0x2706f  ldfld    bool Microsoft.Crm.Extensibility.OData.TypeConverters.EdmMetadataEntityTypeConverter::_isCollection
0x27074  brfalse.s loc_2708A
0x27076  ldloc.2
0x27077  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType::get_Name()
0x2707c  ldarg.0
0x2707d  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.TypeConverters.EdmMetadataEntityTypeConverter::edmModel
0x27082  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::GetCrmMetadataEntityMetadataFromEdmEntityName(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x27087  stloc.1
0x27088  br.s     loc_2709C
0x2708a  ldarg.0
0x2708b  ldfld    string Microsoft.Crm.Extensibility.OData.TypeConverters.EdmMetadataEntityTypeConverter::_edmEntityName
0x27090  ldarg.0
0x27091  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.TypeConverters.EdmMetadataEntityTypeConverter::edmModel
0x27096  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::GetCrmMetadataEntityMetadataFromEdmEntityName(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x2709b  stloc.1
0x2709c  ldloc.1
0x2709d  callvirt instance class [mscorlib]System.Type [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_ClrType()
0x270a2  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x270a7  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase
0x270ac  stloc.0
0x270ad  ldarg.1
0x270ae  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [System.Web.OData]System.Web.OData.Delta::GetChangedPropertyNames()
0x270b3  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x270b8  stloc.3
0x270b9  br       loc_271C7
0x270be  ldloc.3
0x270bf  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x270c4  stloc.s  4
0x270c6  ldloc.2
0x270c7  ldloc.s  4
0x270c9  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmStructuredType::FindProperty(string)
0x270ce  stloc.s  5
0x270d0  ldnull
0x270d1  stloc.s  6
0x270d3  ldloc.s  5
0x270d5  callvirt instance valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPropertyKind [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty::get_PropertyKind()
0x270da  ldc.i4.2
0x270db  bne.un   loc_27180
0x270e0  ldarg.1
0x270e1  ldloc.s  4
0x270e3  ldloca.s 6
0x270e5  callvirt instance bool [System.Web.OData]System.Web.OData.Delta::TryGetPropertyValue(string, object&)
0x270ea  brfalse  loc_271C7
0x270ef  ldloc.s  6
0x270f1  isinst   [System.Web.OData]System.Web.OData.EdmEntityObject
0x270f6  brtrue.s loc_2710D
0x270f8  ldloc.s  6
0x270fa  isinst   [System.Web.OData]System.Web.OData.EdmEntityObjectCollection
0x270ff  brtrue.s loc_2710D
0x27101  ldloc.s  6
0x27103  isinst   [System]System.Uri
0x27108  ldnull
0x27109  cgt.un
0x2710b  br.s     loc_2710E
0x2710d  ldc.i4.1
0x2710e  ldstr    aValueShouldBeA// "value should be an EdmEntityObject or E"...
0x27113  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x27118  ldnull
0x27119  stloc.s  7
0x2711b  ldloc.s  4
0x2711d  ldstr    aGlobaloptionse_0// "GlobalOptionSet"
0x27122  call     bool [mscorlib]System.String::op_Equality(string, string)
0x27127  brfalse.s loc_27139
0x27129  ldloc.2
0x2712a  ldstr    aOptionset// "OptionSet"
0x2712f  ldloc.1
0x27130  call     class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmNavigationProperty, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataRelationshipMetadata> Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::GetMetadataRelationshipInformation(class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmStructuredType edmEntityType, string propertyName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata crmMetadataEntityMetadata)
0x27135  stloc.s  7
0x27137  br.s     loc_27144
0x27139  ldloc.2
0x2713a  ldloc.s  4
0x2713c  ldloc.1
0x2713d  call     class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmNavigationProperty, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataRelationshipMetadata> Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::GetMetadataRelationshipInformation(class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmStructuredType edmEntityType, string propertyName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata crmMetadataEntityMetadata)
0x27142  stloc.s  7
0x27144  ldloc.s  7
0x27146  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmNavigationProperty, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataRelationshipMetadata>::get_Item1()
0x2714b  ldnull
0x2714c  cgt.un
0x2714e  ldstr    aEdmnavigationp// "EdmNavigationProperty should exist"
0x27153  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x27158  ldloc.s  7
0x2715a  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmNavigationProperty, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataRelationshipMetadata>::get_Item2()
0x2715f  ldnull
0x27160  cgt.un
0x27162  ldstr    aEntityrelation// "EntityRelationship should exist"
0x27167  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x2716c  ldarg.0
0x2716d  ldloc.0
0x2716e  ldloc.s  5
0x27170  ldloc.s  7
0x27172  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmNavigationProperty, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataRelationshipMetadata>::get_Item2()
0x27177  ldloc.s  6
0x27179  call     instance void Microsoft.Crm.Extensibility.OData.TypeConverters.EdmMetadataEntityTypeConverter::SetMetadataNavigationPropertyToXrmEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase entity, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty edmProperty, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataRelationshipMetadata entityRelationship, object propertyValue)
0x2717e  br.s     loc_271C7
0x27180  ldloc.s  5
0x27182  callvirt instance valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPropertyKind [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty::get_PropertyKind()
0x27187  ldc.i4.1
0x27188  bne.un.s loc_271BC
0x2718a  ldloc.s  5
0x2718c  call     string Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::GetCrmMetadataAttributeNameFromMetadataEdmAttributeName(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty edmProperty)
0x27191  stloc.s  8
0x27193  ldarg.1
0x27194  ldloc.s  4
0x27196  ldloca.s 6
0x27198  callvirt instance bool [System.Web.OData]System.Web.OData.Delta::TryGetPropertyValue(string, object&)
0x2719d  brfalse.s loc_271AE
0x2719f  ldarg.0
0x271a0  ldloc.0
0x271a1  ldloc.s  8
0x271a3  ldloc.s  5
0x271a5  ldloc.s  6
0x271a7  call     instance void Microsoft.Crm.Extensibility.OData.TypeConverters.EdmMetadataEntityTypeConverter::SetStructuralPropertyToXrmEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase entity, string crmAttributeName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty edmProperty, object propertyValue)
0x271ac  br.s     loc_271C7
0x271ae  ldarg.0
0x271af  ldloc.0
0x271b0  ldloc.s  8
0x271b2  ldloc.s  5
0x271b4  ldnull
0x271b5  call     instance void Microsoft.Crm.Extensibility.OData.TypeConverters.EdmMetadataEntityTypeConverter::SetStructuralPropertyToXrmEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase entity, string crmAttributeName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty edmProperty, object propertyValue)
0x271ba  br.s     loc_271C7
0x271bc  ldstr    aInvalidPropert// "Invalid PropertyKind"
0x271c1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x271c6  throw
0x271c7  ldloc.3
0x271c8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x271cd  brtrue   loc_270BE
0x271d2  leave.s  loc_271DE
0x271d4  ldloc.3
0x271d5  brfalse.s loc_271DD
0x271d7  ldloc.3
0x271d8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x271dd  endfinally
0x271de  ldloc.0
0x271df  ret
```
