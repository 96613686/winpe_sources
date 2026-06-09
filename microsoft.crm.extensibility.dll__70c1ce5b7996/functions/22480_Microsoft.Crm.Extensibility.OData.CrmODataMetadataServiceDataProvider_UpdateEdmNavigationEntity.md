# Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::UpdateEdmNavigationEntity

- ea: `0x22480`
- end: `0x225ea`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::UpdateEdmNavigationEntity`
- size: `362`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x127d0`

## callees

- `0xf880`
- `0x15db0`
- `0x18f80`
- `0x1f280`
- `0x214c0`
- `0x22260`
- `0x22480`
- `0x236c0`
- `0x23d10`
- `0x23d50`
- `0x23ec0`
- `0x24e20`
- `0x24e60`
- `0x26e90`

## pseudocode

```c

```

## disassembly

```asm
0x22480  ldarg.2
0x22481  ldarg.0
0x22482  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x22487  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::GetCrmMetadataEntityMetadataFromEdmEntityName(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x2248c  dup
0x2248d  callvirt instance class [mscorlib]System.Type [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_ClrType()
0x22492  stloc.0
0x22493  ldarg.s  4
0x22495  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::GetXrmEntityMetadataOfNavigationPropertyName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata xrmEntityMetadata, string edmNavigationPropertyName)
0x2249a  stloc.1
0x2249b  ldloc.1
0x2249c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntitiesCache Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetMetadataForMetadataCache()
0x224a1  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEdmEntityProvider::IsContainedEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntitiesCache)
0x224a6  brtrue.s loc_224B8
0x224a8  ldstr    aPutOnNavigatio// "Put on Navigation Property is only supp"...
0x224ad  ldstr    aGet_0// "GET"
0x224b2  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::CreateExceptionDataMethodNotAllowed(string exceptionMessage, string allowedMethods)
0x224b7  throw
0x224b8  ldnull
0x224b9  stloc.2
0x224ba  ldarg.3
0x224bb  stloc.3
0x224bc  ldarg.s  5
0x224be  stloc.s  4
0x224c0  ldarg.3
0x224c1  ldloca.s 5
0x224c3  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x224c8  brtrue.s loc_224DB
0x224ca  ldarg.3
0x224cb  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ParseAlternateKeys(string key)
0x224d0  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Values()
0x224d5  call     T0x2B00008E
0x224da  stloc.3
0x224db  ldarg.s  5
0x224dd  ldloca.s 6
0x224df  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x224e4  brfalse.s loc_224F8
0x224e6  ldarg.s  6
0x224e8  ldloc.s  6
0x224ea  ldarg.0
0x224eb  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x224f0  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase Microsoft.Crm.Extensibility.OData.EdmMetadataTypeConverter::ConvertToCrmEntity(class [System.Web.OData]System.Web.OData.EdmEntityObject edmEntity, valuetype [mscorlib]System.Guid entityId, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x224f5  stloc.2
0x224f6  br.s     loc_22570
0x224f8  ldarg.s  6
0x224fa  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType [System.Web.OData]System.Web.OData.EdmStructuredObject::get_ActualEdmType()
0x224ff  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType
0x22504  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType::get_Name()
0x22509  ldarg.0
0x2250a  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x2250f  newobj   instance void Microsoft.Crm.Extensibility.OData.TypeConverters.EdmMetadataEntityTypeConverter::.ctor(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x22514  ldarg.s  6
0x22516  callvirt instance object class Microsoft.Crm.Extensibility.OData.TypeConverters.EdmTypeConverterBase`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase, class [System.Web.OData]System.Web.OData.EdmEntityObject>::ConvertToCrmType(object)
0x2251b  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase
0x22520  stloc.2
0x22521  ldarg.s  5
0x22523  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ParseAlternateKeys(string key)
0x22528  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Values()
0x2252d  call     T0x2B00008E
0x22532  stloc.s  4
0x22534  ldloc.2
0x22535  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2253a  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::get_BaseType()
0x2253f  ldnull
0x22540  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x22545  brfalse.s loc_22570
0x22547  ldloc.2
0x22548  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2254d  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::get_BaseType()
0x22552  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata
0x22557  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2255c  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x22561  brfalse.s loc_22570
0x22563  ldloc.2
0x22564  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata
0x22569  ldloc.s  4
0x2256b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_LogicalName(string)
0x22570  ldarg.0
0x22571  ldarg.1
0x22572  ldloc.1
0x22573  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ODataV4NameFormatter::GetEdmEntityNameForMetadataEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata)
0x22578  ldloc.2
0x22579  ldarg.s  6
0x2257b  ldc.i4.2
0x2257c  ldloc.0
0x2257d  ldloc.3
0x2257e  ldloc.1
0x2257f  callvirt instance class [mscorlib]System.Type [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_ClrType()
0x22584  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::GetBoundParametersForCreateUpdate(class [mscorlib]System.Type entityCrmType, string entityIdValue, class [mscorlib]System.Type navigationPropertyCrmType)
0x22589  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::ExecuteMetadataCreateUpdate(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string edmEntityName, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase entity, class [System.Web.OData]System.Web.OData.EdmEntityObject entityObject, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrimitiveOperationType operationMethod, [opt] class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection boundParameterCollection)
0x2258e  pop
0x2258f  ldarg.1
0x22590  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x22595  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x2259a  ldstr    a01234// "{0}/{1}({2})/{3}({4})"
0x2259f  ldc.i4.5
0x225a0  newarr   [mscorlib]System.Object
0x225a5  dup
0x225a6  ldc.i4.0
0x225a7  ldarg.1
0x225a8  callvirt instance class [System]System.Uri Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_ServiceRootUri()
0x225ad  stelem.ref
0x225ae  dup
0x225af  ldc.i4.1
0x225b0  ldarg.2
0x225b1  ldarg.0
0x225b2  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x225b7  call     string Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityCollectionName(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x225bc  stelem.ref
0x225bd  dup
0x225be  ldc.i4.2
0x225bf  ldarg.3
0x225c0  stelem.ref
0x225c1  dup
0x225c2  ldc.i4.3
0x225c3  ldarg.s  4
0x225c5  stelem.ref
0x225c6  dup
0x225c7  ldc.i4.4
0x225c8  ldarg.s  5
0x225ca  stelem.ref
0x225cb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x225d0  newobj   instance void [System]System.Uri::.ctor(string)
0x225d5  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataHeaders::SetODataEntityIdInResponse(class [System]System.Uri oDataEntityId)
0x225da  ldloc.2
0x225db  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase::get_MetadataId()
0x225e0  stloc.s  7
0x225e2  ldloca.s 7
0x225e4  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x225e9  ret
```
