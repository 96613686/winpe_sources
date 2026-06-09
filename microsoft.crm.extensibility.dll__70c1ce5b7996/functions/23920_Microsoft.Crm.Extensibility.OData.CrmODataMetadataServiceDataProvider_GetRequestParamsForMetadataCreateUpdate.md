# Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::GetRequestParamsForMetadataCreateUpdate

- ea: `0x23920`
- end: `0x23b2f`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::GetRequestParamsForMetadataCreateUpdate`
- size: `527`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x236c0`

## callees

- `0x15c50`
- `0x15cb0`
- `0x15db0`
- `0x192a0`
- `0x23920`
- `0x24e10`
- `0x29180`

## pseudocode

```c

```

## disassembly

```asm
0x23920  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection::.ctor()
0x23925  stloc.0
0x23926  ldarg.s  4
0x23928  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Request()
0x2392d  call     class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataRequestHeader(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x23932  stloc.1
0x23933  ldarg.2
0x23934  ldc.i4.3
0x23935  beq.s    loc_2393B
0x23937  ldarg.2
0x23938  ldc.i4.2
0x23939  bne.un.s loc_2397B
0x2393b  ldloc.1
0x2393c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_ODataOptionalParameters()
0x23941  ldstr    aMergelabels// "MergeLabels"
0x23946  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x2394b  brfalse.s loc_2396A
0x2394d  ldloc.0
0x2394e  ldstr    aMergelabels// "MergeLabels"
0x23953  ldloc.1
0x23954  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_ODataOptionalParameters()
0x23959  ldstr    aMergelabels// "MergeLabels"
0x2395e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x23963  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0x23968  br.s     loc_2397B
0x2396a  ldloc.0
0x2396b  ldstr    aMergelabels// "MergeLabels"
0x23970  ldc.i4.0
0x23971  box      [mscorlib]System.Boolean
0x23976  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0x2397b  ldloc.1
0x2397c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_ODataOptionalParameters()
0x23981  ldstr    aSolutionunique// "SolutionUniqueName"
0x23986  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x2398b  brfalse.s loc_239A8
0x2398d  ldloc.0
0x2398e  ldstr    aSolutionunique// "SolutionUniqueName"
0x23993  ldloc.1
0x23994  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_ODataOptionalParameters()
0x23999  ldstr    aSolutionunique// "SolutionUniqueName"
0x2399e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x239a3  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0x239a8  ldarg.3
0x239a9  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestFieldDescription>::get_Keys()
0x239ae  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestFieldDescription>::GetEnumerator()
0x239b3  stloc.2
0x239b4  br       loc_23B11
0x239b9  ldloca.s 2
0x239bb  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestFieldDescription>::get_Current()
0x239c0  stloc.3
0x239c1  ldnull
0x239c2  stloc.s  4
0x239c4  ldarg.3
0x239c5  ldloc.3
0x239c6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestFieldDescription>::get_Item(void)
0x239cb  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestFieldDescription::get_BindingParameters()
0x239d0  ldstr    aBindingattribu// "BindingAttributeName"
0x239d5  ldloca.s 4
0x239d7  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::TryGetValue(var<u1>, !!T0)
0x239dc  brfalse  loc_23B11
0x239e1  ldnull
0x239e2  stloc.s  5
0x239e4  ldarg.1
0x239e5  ldloc.s  4
0x239e7  ldloca.s 5
0x239e9  callvirt instance bool [System.Web.OData]System.Web.OData.Delta::TryGetPropertyValue(string, object&)
0x239ee  pop
0x239ef  ldloc.s  5
0x239f1  brfalse  loc_23B11
0x239f6  ldarg.1
0x239f7  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType [System.Web.OData]System.Web.OData.EdmStructuredObject::get_ActualEdmType()
0x239fc  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType
0x23a01  ldloc.s  4
0x23a03  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmStructuredType::FindProperty(string)
0x23a08  stloc.s  6
0x23a0a  ldloc.s  6
0x23a0c  callvirt instance valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPropertyKind [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty::get_PropertyKind()
0x23a11  ldc.i4.2
0x23a12  bne.un   loc_23AF1
0x23a17  ldloc.s  6
0x23a19  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty::get_Type()
0x23a1e  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference::get_Definition()
0x23a23  callvirt instance valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeKind [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType::get_TypeKind()
0x23a28  stloc.s  7
0x23a2a  ldloca.s 7
0x23a2c  ldc.i4.4
0x23a2d  box      [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeKind
0x23a32  constrained. [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeKind
0x23a38  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x23a3d  brfalse  loc_23ACF
0x23a42  ldnull
0x23a43  stloc.s  8
0x23a45  ldloc.s  5
0x23a47  castclass [System.Web.OData]System.Web.OData.EdmEntityObjectCollection
0x23a4c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Web.OData]System.Web.OData.IEdmEntityObject>::GetEnumerator()
0x23a51  stloc.s  9
0x23a53  br.s     loc_23AB8
0x23a55  ldloc.s  9
0x23a57  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Web.OData]System.Web.OData.IEdmEntityObject>::get_Current()
0x23a5c  castclass [System.Web.OData]System.Web.OData.EdmEntityObject
0x23a61  stloc.s  0xA
0x23a63  ldloc.s  0xA
0x23a65  ldstr    aIsprimaryname// "IsPrimaryName"
0x23a6a  ldloca.s 8
0x23a6c  callvirt instance bool [System.Web.OData]System.Web.OData.Delta::TryGetPropertyValue(string, object&)
0x23a71  brfalse.s loc_23AB8
0x23a73  ldloc.s  8
0x23a75  brfalse.s loc_23AB8
0x23a77  ldloc.s  8
0x23a79  unbox.any [mscorlib]System.Boolean
0x23a7e  brfalse.s loc_23AB8
0x23a80  ldloc.s  0xA
0x23a82  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType [System.Web.OData]System.Web.OData.EdmStructuredObject::get_ActualEdmType()
0x23a87  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType
0x23a8c  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType::get_Name()
0x23a91  ldstr    aStringattribut// "StringAttributeMetadata"
0x23a96  callvirt instance bool [mscorlib]System.String::Equals(string)
0x23a9b  brfalse.s loc_23AB8
0x23a9d  ldloc.0
0x23a9e  ldloc.3
0x23a9f  ldloc.s  0xA
0x23aa1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x23aa6  ldarg.0
0x23aa7  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x23aac  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase Microsoft.Crm.Extensibility.OData.EdmMetadataTypeConverter::ConvertToCrmEntity(class [System.Web.OData]System.Web.OData.EdmEntityObject edmEntity, valuetype [mscorlib]System.Guid entityId, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x23ab1  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0x23ab6  leave.s  loc_23B11
0x23ab8  ldloc.s  9
0x23aba  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x23abf  brtrue.s loc_23A55
0x23ac1  leave.s  loc_23B11
0x23ac3  ldloc.s  9
0x23ac5  brfalse.s loc_23ACE
0x23ac7  ldloc.s  9
0x23ac9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x23ace  endfinally
0x23acf  ldloc.0
0x23ad0  ldloc.3
0x23ad1  ldloc.s  6
0x23ad3  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty::get_Type()
0x23ad8  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference::get_Definition()
0x23add  ldloc.s  5
0x23adf  ldarg.0
0x23ae0  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x23ae5  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase Microsoft.Crm.Extensibility.OData.EdmMetadataTypeConverter::ConvertToCrmMetadataValue(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType edmType, object propertyValue, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x23aea  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0x23aef  br.s     loc_23B11
0x23af1  ldloc.s  6
0x23af3  callvirt instance valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPropertyKind [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty::get_PropertyKind()
0x23af8  ldc.i4.1
0x23af9  bne.un.s loc_23B11
0x23afb  ldloc.0
0x23afc  ldloc.3
0x23afd  ldloc.s  6
0x23aff  ldloc.s  5
0x23b01  ldarg.0
0x23b02  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x23b07  call     object Microsoft.Crm.Extensibility.OData.EdmMetadataTypeConverter::ConvertToCrmAttributeValue(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty edmProperty, object propertyValue, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x23b0c  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0x23b11  ldloca.s 2
0x23b13  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestFieldDescription>::MoveNext()
0x23b18  brtrue   loc_239B9
0x23b1d  leave.s  loc_23B2D
0x23b1f  ldloca.s 2
0x23b21  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestFieldDescription>
0x23b27  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x23b2c  endfinally
0x23b2d  ldloc.0
0x23b2e  ret
```
