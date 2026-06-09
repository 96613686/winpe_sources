# Microsoft.Crm.Extensibility.CrmODataEntityDeserializer::ApplyStructuralProperties

- ea: `0x34c0`
- end: `0x36c3`
- name: `Microsoft.Crm.Extensibility.CrmODataEntityDeserializer::ApplyStructuralProperties`
- size: `515`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3380`
- `0x3390`
- `0x33a0`
- `0x34c0`
- `0x36d0`
- `0x3700`
- `0xf740`
- `0xfbf0`

## pseudocode

```c

```

## disassembly

```asm
0x34c0  ldarg.s  4
0x34c2  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerContext::get_Request()
0x34c7  brfalse.s loc_34D6
0x34c9  ldarg.0
0x34ca  ldarg.s  4
0x34cc  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerContext::get_Request()
0x34d1  call     instance void Microsoft.Crm.Extensibility.CrmODataEntityDeserializer::set_Request(class [System.Net.Http]System.Net.Http.HttpRequestMessage value)
0x34d6  ldarg.2
0x34d7  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.ODataResource [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataResourceWrapper::get_Resource()
0x34dc  callvirt instance class [System]System.Uri [Microsoft.OData.Core]Microsoft.OData.ODataResource::get_Id()
0x34e1  ldnull
0x34e2  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x34e7  brfalse  loc_36B7
0x34ec  ldarg.2
0x34ed  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.ODataResource [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataResourceWrapper::get_Resource()
0x34f2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Core]Microsoft.OData.ODataProperty> [Microsoft.OData.Core]Microsoft.OData.ODataResource::get_Properties()
0x34f7  call     T0x2B000021
0x34fc  brtrue   loc_36B7
0x3501  ldarg.0
0x3502  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.CrmODataEntityDeserializer::get_Request()
0x3507  call     class [System.Web.OData]System.Web.OData.Routing.IODataPathHandler [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageExtensions::GetPathHandler(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x350c  ldarg.0
0x350d  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.CrmODataEntityDeserializer::get_Request()
0x3512  call     class [System.Web.Http]System.Web.Http.Routing.UrlHelper [System.Web.Http]System.Net.Http.HttpRequestMessageExtensions::GetUrlHelper(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x3517  ldc.i4.0
0x3518  newarr   [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment
0x351d  call     string [System.Web.OData]System.Web.OData.Extensions.UrlHelperExtensions::CreateODataLink(class [System.Web.Http]System.Web.Http.Routing.UrlHelper, class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment[])
0x3522  ldarg.2
0x3523  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.ODataResource [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataResourceWrapper::get_Resource()
0x3528  callvirt instance class [System]System.Uri [Microsoft.OData.Core]Microsoft.OData.ODataResource::get_Id()
0x352d  callvirt instance string [mscorlib]System.Object::ToString()
0x3532  ldarg.0
0x3533  call     instance class [mscorlib]System.IServiceProvider Microsoft.Crm.Extensibility.CrmODataEntityDeserializer::get_RootContainer()
0x3538  callvirt instance class [System.Web.OData]System.Web.OData.Routing.ODataPath [System.Web.OData]System.Web.OData.Routing.IODataPathHandler::Parse(string, string, class [mscorlib]System.IServiceProvider)
0x353d  stloc.0
0x353e  ldarg.3
0x353f  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeSemantics::AsEntity(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x3544  stloc.1
0x3545  ldsfld   string [mscorlib]System.String::Empty
0x354a  stloc.2
0x354b  ldloc.1
0x354c  call     string [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::FullName(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x3551  ldstr    aCrmbaseentity// "crmbaseentity"
0x3556  callvirt instance bool [mscorlib]System.String::Contains(string)
0x355b  brfalse  loc_36C2
0x3560  ldarg.2
0x3561  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.ODataResource [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataResourceWrapper::get_Resource()
0x3566  callvirt instance class [System]System.Uri [Microsoft.OData.Core]Microsoft.OData.ODataResource::get_Id()
0x356b  callvirt instance string [mscorlib]System.Object::ToString()
0x3570  stloc.3
0x3571  ldloc.3
0x3572  ldstr    asc_36A40// ":"
0x3577  callvirt instance int32 [mscorlib]System.String::IndexOf(string)
0x357c  stloc.s  4
0x357e  ldloc.3
0x357f  ldloc.s  4
0x3581  ldc.i4.2
0x3582  add
0x3583  ldloc.3
0x3584  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3589  ldloc.s  4
0x358b  ldc.i4.4
0x358c  add
0x358d  sub
0x358e  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x3593  pop
0x3594  ldloc.0
0x3595  brfalse.s loc_35CB
0x3597  ldloc.0
0x3598  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationSource [System.Web.OData]System.Web.OData.Routing.ODataPath::get_NavigationSource()
0x359d  brfalse.s loc_35CB
0x359f  ldloc.0
0x35a0  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationSource [System.Web.OData]System.Web.OData.Routing.ODataPath::get_NavigationSource()
0x35a5  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x35aa  ldarg.s  4
0x35ac  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerContext::get_Model()
0x35b1  call     string Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityNameFromCollectionName(string entityCollectionName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x35b6  stloc.2
0x35b7  ldloc.2
0x35b8  ldarg.s  4
0x35ba  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerContext::get_Model()
0x35bf  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityType(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x35c4  ldc.i4.0
0x35c5  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityTypeReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType, bool)
0x35ca  stloc.1
0x35cb  ldarg.1
0x35cc  castclass [System.Web.OData]System.Web.OData.EdmEntityObject
0x35d1  ldarg.1
0x35d2  castclass [System.Web.OData]System.Web.OData.EdmEntityObject
0x35d7  ldloc.2
0x35d8  ldarg.s  4
0x35da  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerContext::get_Model()
0x35df  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityType(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x35e4  dup
0x35e5  stloc.s  7
0x35e7  callvirt instance void [System.Web.OData]System.Web.OData.EdmStructuredObject::set_ActualEdmType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType)
0x35ec  ldloc.s  7
0x35ee  callvirt instance void [System.Web.OData]System.Web.OData.EdmStructuredObject::set_ExpectedEdmType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType)
0x35f3  ldloc.1
0x35f4  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuralProperty> [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::Key(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityTypeReference)
0x35f9  call     T0x2B000022
0x35fe  stloc.s  5
0x3600  ldloc.0
0x3601  call     class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Extensibility.CrmODataEntityDeserializer::GetKeys(class [System.Web.OData]System.Web.OData.Routing.ODataPath odataPath)
0x3606  stloc.s  6
0x3608  ldloc.s  6
0x360a  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::get_Count()
0x360f  ldc.i4.1
0x3610  bne.un.s loc_3653
0x3612  ldloc.s  6
0x3614  call     T0x2B000023
0x3619  stloc.s  9
0x361b  ldloca.s 9
0x361d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x3622  ldc.i4.0
0x3623  ldarg.s  4
0x3625  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerContext::get_Model()
0x362a  ldloc.s  5
0x362c  ldc.i4.0
0x362d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuralProperty>::get_Item(!!T0)
0x3632  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty::get_Type()
0x3637  call     object [Microsoft.OData.Core]Microsoft.OData.ODataUriUtils::ConvertFromUriLiteral(string, valuetype [Microsoft.OData.Core]Microsoft.OData.ODataVersion, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x363c  stloc.s  8
0x363e  ldarg.1
0x363f  ldloc.s  5
0x3641  ldc.i4.0
0x3642  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuralProperty>::get_Item(!!T0)
0x3647  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x364c  ldloc.s  8
0x364e  call     void Microsoft.Crm.Extensibility.CrmODataEntityDeserializer::SetProperty(object resource, string propertyName, object propertyValue)
0x3653  ldloc.s  5
0x3655  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuralProperty>::GetEnumerator()
0x365a  stloc.s  0xA
0x365c  br.s     loc_36A0
0x365e  ldloc.s  0xA
0x3660  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuralProperty>::get_Current()
0x3665  stloc.s  0xB
0x3667  ldloc.s  6
0x3669  ldloc.s  0xB
0x366b  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x3670  ldloca.s 0xC
0x3672  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::TryGetValue(var<u1>, !!T0)
0x3677  brfalse.s loc_36A0
0x3679  ldloc.s  0xC
0x367b  ldc.i4.0
0x367c  ldarg.s  4
0x367e  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerContext::get_Model()
0x3683  ldloc.s  0xB
0x3685  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty::get_Type()
0x368a  call     object [Microsoft.OData.Core]Microsoft.OData.ODataUriUtils::ConvertFromUriLiteral(string, valuetype [Microsoft.OData.Core]Microsoft.OData.ODataVersion, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x368f  stloc.s  0xD
0x3691  ldarg.1
0x3692  ldloc.s  0xB
0x3694  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x3699  ldloc.s  0xD
0x369b  call     void Microsoft.Crm.Extensibility.CrmODataEntityDeserializer::SetProperty(object resource, string propertyName, object propertyValue)
0x36a0  ldloc.s  0xA
0x36a2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x36a7  brtrue.s loc_365E
0x36a9  leave.s  loc_36C2
0x36ab  ldloc.s  0xA
0x36ad  brfalse.s loc_36B6
0x36af  ldloc.s  0xA
0x36b1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36b6  endfinally
0x36b7  ldarg.0
0x36b8  ldarg.1
0x36b9  ldarg.2
0x36ba  ldarg.3
0x36bb  ldarg.s  4
0x36bd  call     instance void [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataResourceDeserializer::ApplyStructuralProperties(object, class [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataResourceWrapper, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredTypeReference, class [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerContext)
0x36c2  ret
```
