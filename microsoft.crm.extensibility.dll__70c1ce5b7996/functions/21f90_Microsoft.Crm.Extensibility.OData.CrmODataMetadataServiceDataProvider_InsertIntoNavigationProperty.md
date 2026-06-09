# Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::InsertIntoNavigationProperty

- ea: `0x21f90`
- end: `0x22073`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::InsertIntoNavigationProperty`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x11730`

## callees

- `0xf880`
- `0x15db0`
- `0x18f80`
- `0x1f280`
- `0x214c0`
- `0x21f90`
- `0x22080`
- `0x22260`
- `0x236c0`
- `0x23d10`
- `0x23d50`
- `0x23ec0`
- `0x24e20`
- `0x24e60`

## pseudocode

```c

```

## disassembly

```asm
0x21f90  ldarg.2
0x21f91  ldarg.0
0x21f92  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x21f97  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::GetCrmMetadataEntityMetadataFromEdmEntityName(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x21f9c  dup
0x21f9d  callvirt instance class [mscorlib]System.Type [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_ClrType()
0x21fa2  stloc.0
0x21fa3  ldarg.s  4
0x21fa5  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::GetXrmEntityMetadataOfNavigationPropertyName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata xrmEntityMetadata, string edmNavigationPropertyName)
0x21faa  stloc.1
0x21fab  ldloc.1
0x21fac  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntitiesCache Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetMetadataForMetadataCache()
0x21fb1  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEdmEntityProvider::IsContainedEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntitiesCache)
0x21fb6  brtrue.s loc_21FC8
0x21fb8  ldstr    aPostOnNavigati// "Post on Navigation Property is only sup"...
0x21fbd  ldstr    aGet_0// "GET"
0x21fc2  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::CreateExceptionDataMethodNotAllowed(string exceptionMessage, string allowedMethods)
0x21fc7  throw
0x21fc8  ldarg.s  5
0x21fca  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x21fcf  ldarg.0
0x21fd0  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x21fd5  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase Microsoft.Crm.Extensibility.OData.EdmMetadataTypeConverter::ConvertToCrmEntity(class [System.Web.OData]System.Web.OData.EdmEntityObject edmEntity, valuetype [mscorlib]System.Guid entityId, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x21fda  stloc.2
0x21fdb  ldloc.2
0x21fdc  ldarg.s  5
0x21fde  call     void Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::ValidateCreateLocalOptionSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase navigationEntity, class [System.Web.OData]System.Web.OData.EdmEntityObject navigationEntityObject)
0x21fe3  ldarg.3
0x21fe4  stloc.3
0x21fe5  ldarg.3
0x21fe6  ldloca.s 4
0x21fe8  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x21fed  brtrue.s loc_22000
0x21fef  ldarg.3
0x21ff0  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ParseAlternateKeys(string key)
0x21ff5  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Values()
0x21ffa  call     T0x2B00008E
0x21fff  stloc.3
0x22000  ldarg.0
0x22001  ldarg.1
0x22002  ldloc.1
0x22003  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ODataV4NameFormatter::GetEdmEntityNameForMetadataEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata)
0x22008  ldloc.2
0x22009  ldarg.s  5
0x2200b  ldc.i4.0
0x2200c  ldloc.0
0x2200d  ldloc.3
0x2200e  ldloc.1
0x2200f  callvirt instance class [mscorlib]System.Type [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_ClrType()
0x22014  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::GetBoundParametersForCreateUpdate(class [mscorlib]System.Type entityCrmType, string entityIdValue, class [mscorlib]System.Type navigationPropertyCrmType)
0x22019  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::ExecuteMetadataCreateUpdate(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string edmEntityName, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase entity, class [System.Web.OData]System.Web.OData.EdmEntityObject entityObject, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrimitiveOperationType operationMethod, [opt] class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection boundParameterCollection)
0x2201e  stloc.s  5
0x22020  ldarg.1
0x22021  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x22026  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x2202b  ldstr    a01234// "{0}/{1}({2})/{3}({4})"
0x22030  ldc.i4.5
0x22031  newarr   [mscorlib]System.Object
0x22036  dup
0x22037  ldc.i4.0
0x22038  ldarg.1
0x22039  callvirt instance class [System]System.Uri Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_ServiceRootUri()
0x2203e  stelem.ref
0x2203f  dup
0x22040  ldc.i4.1
0x22041  ldarg.2
0x22042  ldarg.0
0x22043  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x22048  call     string Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityCollectionName(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x2204d  stelem.ref
0x2204e  dup
0x2204f  ldc.i4.2
0x22050  ldarg.3
0x22051  stelem.ref
0x22052  dup
0x22053  ldc.i4.3
0x22054  ldarg.s  4
0x22056  stelem.ref
0x22057  dup
0x22058  ldc.i4.4
0x22059  ldloc.s  5
0x2205b  box      [mscorlib]System.Guid
0x22060  stelem.ref
0x22061  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x22066  newobj   instance void [System]System.Uri::.ctor(string)
0x2206b  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataHeaders::SetODataEntityIdInResponse(class [System]System.Uri oDataEntityId)
0x22070  ldloc.s  5
0x22072  ret
```
