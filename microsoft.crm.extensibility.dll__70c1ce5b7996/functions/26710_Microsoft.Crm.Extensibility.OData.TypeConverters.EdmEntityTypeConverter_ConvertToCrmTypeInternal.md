# Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::ConvertToCrmTypeInternal

- ea: `0x26710`
- end: `0x26886`
- name: `Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::ConvertToCrmTypeInternal`
- size: `374`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0xfb80`
- `0x1f840`
- `0x1ff90`
- `0x26710`
- `0x26890`
- `0x26a70`
- `0x2be70`
- `0x2bed0`

## string_xrefs

- `0x267a0`: `value should be an EdmEntityObject or EdmEntityObjectCollection or Uri`

## pseudocode

```c

```

## disassembly

```asm
0x26710  ldarg.1
0x26711  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType [System.Web.OData]System.Web.OData.EdmStructuredObject::get_ActualEdmType()
0x26716  call     string [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::FullTypeName(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType)
0x2671b  ldstr    aMicrosoftDynam_16// "Microsoft.Dynamics.CRM.crmbaseentity"
0x26720  call     bool [mscorlib]System.String::op_Equality(string, string)
0x26725  brfalse.s loc_26729
0x26727  ldnull
0x26728  ret
0x26729  ldarg.0
0x2672a  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::edmEntityConversionContext
0x2672f  callvirt instance string Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_LogicalName()
0x26734  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x26739  stloc.0
0x2673a  ldarg.1
0x2673b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [System.Web.OData]System.Web.OData.Delta::GetChangedPropertyNames()
0x26740  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x26745  stloc.1
0x26746  br       loc_2685C
0x2674b  ldloc.1
0x2674c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x26751  stloc.2
0x26752  ldarg.1
0x26753  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType [System.Web.OData]System.Web.OData.EdmStructuredObject::get_ActualEdmType()
0x26758  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType
0x2675d  ldloc.2
0x2675e  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmStructuredType::FindProperty(string)
0x26763  stloc.3
0x26764  ldnull
0x26765  stloc.s  4
0x26767  ldloc.3
0x26768  callvirt instance valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPropertyKind [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty::get_PropertyKind()
0x2676d  ldc.i4.2
0x2676e  bne.un   loc_26804
0x26773  ldarg.1
0x26774  ldloc.2
0x26775  ldloca.s 4
0x26777  callvirt instance bool [System.Web.OData]System.Web.OData.Delta::TryGetPropertyValue(string, object&)
0x2677c  brfalse  loc_2685C
0x26781  ldloc.s  4
0x26783  isinst   [System.Web.OData]System.Web.OData.EdmEntityObject
0x26788  brtrue.s loc_2679F
0x2678a  ldloc.s  4
0x2678c  isinst   [System.Web.OData]System.Web.OData.EdmEntityObjectCollection
0x26791  brtrue.s loc_2679F
0x26793  ldloc.s  4
0x26795  isinst   [System]System.Uri
0x2679a  ldnull
0x2679b  cgt.un
0x2679d  br.s     loc_267A0
0x2679f  ldc.i4.1
0x267a0  ldstr    aValueShouldBeA// "value should be an EdmEntityObject or E"...
0x267a5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x267aa  ldloca.s 5
0x267ac  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityRole>
0x267b2  ldarg.1
0x267b3  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType [System.Web.OData]System.Web.OData.EdmStructuredObject::get_ActualEdmType()
0x267b8  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType
0x267bd  ldloc.2
0x267be  ldloca.s 5
0x267c0  call     class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmNavigationProperty, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship> Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetRelationshipInformation(class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType edmEntityType, string propertyName, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityRole>& role)
0x267c5  stloc.s  6
0x267c7  ldloc.s  6
0x267c9  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmNavigationProperty, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship>::get_Item1()
0x267ce  ldnull
0x267cf  cgt.un
0x267d1  ldstr    aEdmnavigationp// "EdmNavigationProperty should exist"
0x267d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x267db  ldloc.s  6
0x267dd  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmNavigationProperty, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship>::get_Item2()
0x267e2  ldnull
0x267e3  cgt.un
0x267e5  ldstr    aEntityrelation// "EntityRelationship should exist"
0x267ea  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x267ef  ldarg.0
0x267f0  ldloc.0
0x267f1  ldloc.3
0x267f2  ldloc.s  6
0x267f4  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmNavigationProperty, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship>::get_Item2()
0x267f9  ldloc.s  4
0x267fb  ldloc.s  5
0x267fd  call     instance void Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::SetNavigationPropertyToXrmEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty edmProperty, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship entityRelationship, object propertyValue, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityRole> role)
0x26802  br.s     loc_2685C
0x26804  ldloc.3
0x26805  callvirt instance valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPropertyKind [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty::get_PropertyKind()
0x2680a  ldc.i4.1
0x2680b  bne.un.s loc_26851
0x2680d  ldloc.3
0x2680e  call     string Microsoft.Crm.Extensibility.OData.EdmUtilities::GetCrmAttributeNameFromEdmAttributeName(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty edmProperty)
0x26813  stloc.s  7
0x26815  ldarg.1
0x26816  ldloc.2
0x26817  ldloca.s 4
0x26819  callvirt instance bool [System.Web.OData]System.Web.OData.Delta::TryGetPropertyValue(string, object&)
0x2681e  brfalse.s loc_26839
0x26820  ldarg.0
0x26821  ldloc.0
0x26822  ldarg.0
0x26823  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::edmEntityConversionContext
0x26828  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_EntityMetadata()
0x2682d  ldloc.s  7
0x2682f  ldloc.3
0x26830  ldloc.s  4
0x26832  call     instance void Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::SetStructuralPropertyToXrmEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, string crmAttributeName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty edmProperty, object propertyValue)
0x26837  br.s     loc_2685C
0x26839  ldarg.0
0x2683a  ldloc.0
0x2683b  ldarg.0
0x2683c  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::edmEntityConversionContext
0x26841  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_EntityMetadata()
0x26846  ldloc.s  7
0x26848  ldloc.3
0x26849  ldnull
0x2684a  call     instance void Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::SetStructuralPropertyToXrmEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, string crmAttributeName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty edmProperty, object propertyValue)
0x2684f  br.s     loc_2685C
0x26851  ldstr    aInvalidPropert// "Invalid PropertyKind"
0x26856  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x2685b  throw
0x2685c  ldloc.1
0x2685d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x26862  brtrue   loc_2674B
0x26867  leave.s  loc_26873
0x26869  ldloc.1
0x2686a  brfalse.s loc_26872
0x2686c  ldloc.1
0x2686d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26872  endfinally
0x26873  ldloc.0
0x26874  ldarg.0
0x26875  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::edmEntityConversionContext
0x2687a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_EntityMetadata()
0x2687f  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::SetNavigationPropertyCollectonForCreate(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity crmEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata)
0x26884  ldloc.0
0x26885  ret
```
