# Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::ExecuteMetadataCreateUpdate

- ea: `0x236c0`
- end: `0x238a3`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::ExecuteMetadataCreateUpdate`
- size: `483`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x21a70`
- `0x21ad0`
- `0x21f90`
- `0x22480`

## callees

- `0x7040`
- `0x21670`
- `0x21860`
- `0x236c0`
- `0x238b0`
- `0x23920`
- `0x23d50`
- `0x245a0`
- `0x24c40`

## pseudocode

```c

```

## disassembly

```asm
0x236c0  ldarg.2
0x236c1  ldarg.0
0x236c2  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x236c7  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::GetCrmMetadataEntityMetadataFromEdmEntityName(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x236cc  stloc.0
0x236cd  ldloc.0
0x236ce  stloc.1
0x236cf  ldloc.0
0x236d0  callvirt instance class [mscorlib]System.Type [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_ClrType()
0x236d5  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsRelationshipMetadata(class [mscorlib]System.Type xrmType)
0x236da  brfalse.s loc_236F9
0x236dc  ldarg.s  4
0x236de  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType [System.Web.OData]System.Web.OData.EdmStructuredObject::get_ActualEdmType()
0x236e3  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType
0x236e8  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType::get_Name()
0x236ed  ldarg.0
0x236ee  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x236f3  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::GetCrmMetadataEntityMetadataFromEdmEntityName(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x236f8  stloc.0
0x236f9  ldsfld   string [mscorlib]System.String::Empty
0x236fe  stloc.2
0x236ff  ldloc.0
0x23700  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrimitiveOperationDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_PrimitiveOperations()
0x23705  ldarg.s  5
0x23707  ldloca.s 2
0x23709  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrimitiveOperationType, string>::TryGetValue(var<u1>, !!T0)
0x2370e  brfalse.s loc_23713
0x23710  ldloc.2
0x23711  brtrue.s loc_2375A
0x23713  ldloc.1
0x23714  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrimitiveOperationDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_PrimitiveOperations()
0x23719  ldarg.s  5
0x2371b  ldloca.s 2
0x2371d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrimitiveOperationType, string>::TryGetValue(var<u1>, !!T0)
0x23722  brfalse.s loc_2372B
0x23724  ldloc.2
0x23725  brfalse.s loc_2372B
0x23727  ldloc.1
0x23728  stloc.0
0x23729  br.s     loc_2375A
0x2372b  ldc.i4   0x195
0x23730  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x23735  ldstr    aMetadataEntity// "Metadata Entity {0} does not support op"...
0x2373a  ldc.i4.1
0x2373b  newarr   [mscorlib]System.Object
0x23740  dup
0x23741  ldc.i4.0
0x23742  ldloc.0
0x23743  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_Name()
0x23748  stelem.ref
0x23749  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2374e  ldc.i4.0
0x2374f  newarr   [mscorlib]System.Object
0x23754  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x23759  throw
0x2375a  ldloc.2
0x2375b  call     class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Extensibility.OrganizationDataService::GetOrganizationContext()
0x23760  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestDescription Microsoft.Crm.Extensibility.OData.CrmSdkRequestResponseProvider::GetRequestDescription(string requestName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x23765  stloc.3
0x23766  ldloc.3
0x23767  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestDescription::get_RequestId()
0x2376c  call     class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Extensibility.OrganizationDataService::GetOrganizationContext()
0x23771  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseDescription Microsoft.Crm.Extensibility.OData.CrmSdkRequestResponseProvider::GetResponseDescription(valuetype [mscorlib]System.Guid requestId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x23776  stloc.s  4
0x23778  ldloc.3
0x23779  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestDescription::get_RequestName()
0x2377e  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor(string)
0x23783  stloc.s  5
0x23785  ldloc.s  5
0x23787  ldarg.0
0x23788  ldarg.s  4
0x2378a  ldarg.s  5
0x2378c  ldloc.3
0x2378d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestFieldDescription> [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestDescription::get_Fields()
0x23792  ldarg.1
0x23793  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::GetRequestParamsForMetadataCreateUpdate(class [System.Web.OData]System.Web.OData.EdmEntityObject entityObject, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrimitiveOperationType operationMethod, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestFieldDescription> fields, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x23798  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_Parameters(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection)
0x2379d  ldloc.3
0x2379e  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestFieldDescription> [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestDescription::get_Fields()
0x237a3  ldloc.0
0x237a4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_LogicalName()
0x237a9  call     string Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::GetActualParameterNameFromRequestDescrition(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestFieldDescription> fields, string entityLogicalName)
0x237ae  stloc.s  6
0x237b0  ldloc.s  5
0x237b2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x237b7  ldloc.s  6
0x237b9  ldarg.3
0x237ba  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x237bf  ldarg.s  6
0x237c1  brfalse.s loc_23811
0x237c3  ldarg.s  6
0x237c5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::GetEnumerator()
0x237ca  stloc.s  9
0x237cc  br.s     loc_237FA
0x237ce  ldloc.s  9
0x237d0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>>::get_Current()
0x237d5  stloc.s  0xA
0x237d7  ldloc.s  5
0x237d9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x237de  ldloca.s 0xA
0x237e0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x237e5  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0x237ea  brtrue.s loc_237FA
0x237ec  ldloc.s  5
0x237ee  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x237f3  ldloc.s  0xA
0x237f5  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>)
0x237fa  ldloc.s  9
0x237fc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x23801  brtrue.s loc_237CE
0x23803  leave.s  loc_23811
0x23805  ldloc.s  9
0x23807  brfalse.s loc_23810
0x23809  ldloc.s  9
0x2380b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x23810  endfinally
0x23811  ldarg.1
0x23812  ldloc.s  5
0x23814  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest request)
0x23819  stloc.s  7
0x2381b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x23820  stloc.s  8
0x23822  ldloc.s  4
0x23824  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseFieldDescription> [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseDescription::get_Fields()
0x23829  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseFieldDescription>::GetEnumerator()
0x2382e  stloc.s  0xB
0x23830  br.s     loc_23887
0x23832  ldloca.s 0xB
0x23834  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseFieldDescription>::get_Current()
0x23839  stloc.s  0xC
0x2383b  ldloc.s  0xC
0x2383d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseFieldDescription::get_BindingParameters()
0x23842  ldstr    aBindingattribu// "BindingAttributeName"
0x23847  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x2384c  brfalse.s loc_23887
0x2384e  ldloc.s  0xC
0x23850  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseFieldDescription::get_BindingParameters()
0x23855  ldstr    aBindingattribu// "BindingAttributeName"
0x2385a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x2385f  ldstr    aMetadataid// "MetadataId"
0x23864  callvirt instance bool [mscorlib]System.String::Equals(string)
0x23869  brfalse.s loc_23887
0x2386b  ldloc.s  7
0x2386d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x23872  ldloc.s  0xC
0x23874  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseFieldDescription::get_Name()
0x23879  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x2387e  unbox.any [mscorlib]System.Guid
0x23883  stloc.s  8
0x23885  leave.s  loc_238A0
0x23887  ldloca.s 0xB
0x23889  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseFieldDescription>::MoveNext()
0x2388e  brtrue.s loc_23832
0x23890  leave.s  loc_238A0
0x23892  ldloca.s 0xB
0x23894  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseFieldDescription>
0x2389a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2389f  endfinally
0x238a0  ldloc.s  8
0x238a2  ret
```
