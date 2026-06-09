# Microsoft.Crm.Extensibility.CrmODataResourceSerializer::CreateResource

- ea: `0x2e80`
- end: `0x3096`
- name: `Microsoft.Crm.Extensibility.CrmODataResourceSerializer::CreateResource`
- size: `534`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x2a40`
- `0x2e80`
- `0x30a0`
- `0x3120`
- `0xf8f0`
- `0xff60`
- `0x17ac0`
- `0x191b0`
- `0x24e60`
- `0x28b60`

## string_xrefs

- `0x2efb`: `OData.Community.Display.V1.FormattedValue`

## pseudocode

```c

```

## disassembly

```asm
0x2e80  ldarg.0
0x2e81  ldarg.1
0x2e82  ldarg.2
0x2e83  call     instance class [Microsoft.OData.Core]Microsoft.OData.ODataResource [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataResourceSerializer::CreateResource(class [System.Web.OData]System.Web.OData.Formatter.Serialization.SelectExpandNode, class [System.Web.OData]System.Web.OData.ResourceContext)
0x2e88  stloc.0
0x2e89  ldarg.2
0x2e8a  brtrue.s loc_2E8E
0x2e8c  ldloc.0
0x2e8d  ret
0x2e8e  ldarg.2
0x2e8f  callvirt instance class [System.Web.OData]System.Web.OData.IEdmStructuredObject [System.Web.OData]System.Web.OData.ResourceContext::get_EdmObject()
0x2e94  isinst   Microsoft.Crm.Extensibility.OData.CrmEdmEntityObject
0x2e99  stloc.1
0x2e9a  ldloc.1
0x2e9b  brfalse  loc_3094
0x2ea0  ldloc.0
0x2ea1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Core]Microsoft.OData.ODataProperty> [Microsoft.OData.Core]Microsoft.OData.ODataResource::get_Properties()
0x2ea6  call     T0x2B00001B
0x2eab  stloc.2
0x2eac  ldarg.2
0x2ead  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.OData]System.Web.OData.ResourceContext::get_Request()
0x2eb2  call     class [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageExtensions::ODataProperties(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x2eb7  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties::get_SelectExpandClause()
0x2ebc  call     bool Microsoft.Crm.Extensibility.OData.EdmUtilities::IsReferenceQueryCall(class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause selectExpandClause)
0x2ec1  stloc.3
0x2ec2  ldloc.3
0x2ec3  brfalse.s loc_2F20
0x2ec5  ldloc.1
0x2ec6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Extensibility.OData.CrmEdmEntityObject::_extraSetContainer
0x2ecb  ldstr    aIsreferencedqu// "IsReferencedQueryCall"
0x2ed0  ldloca.s 5
0x2ed2  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x2ed7  brfalse.s loc_2F20
0x2ed9  ldloc.s  5
0x2edb  unbox.any [mscorlib]System.Boolean
0x2ee0  brfalse.s loc_2F20
0x2ee2  ldloc.1
0x2ee3  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Extensibility.OData.CrmEdmEntityObject::_extraSetContainer
0x2ee8  ldstr    aDisplayname// "__DisplayName__"
0x2eed  ldloca.s 6
0x2eef  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x2ef4  pop
0x2ef5  ldloc.0
0x2ef6  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.OData.Core]Microsoft.OData.ODataInstanceAnnotation> [Microsoft.OData.Core]Microsoft.OData.ODataResource::get_InstanceAnnotations()
0x2efb  ldstr    aOdataCommunity// "OData.Community.Display.V1.FormattedVal"...
0x2f00  ldloc.s  6
0x2f02  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataPrimitiveValue::.ctor(object)
0x2f07  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataInstanceAnnotation::.ctor(string, class [Microsoft.OData.Core]Microsoft.OData.ODataValue)
0x2f0c  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.OData.Core]Microsoft.OData.ODataInstanceAnnotation>::Add(var<u1>)
0x2f11  ldarg.0
0x2f12  ldarg.2
0x2f13  ldloc.0
0x2f14  ldloc.1
0x2f15  call     instance void Microsoft.Crm.Extensibility.CrmODataResourceSerializer::AddODataIdAnnotation(class [System.Web.OData]System.Web.OData.ResourceContext resourceContext, class [Microsoft.OData.Core]Microsoft.OData.ODataResource entry, class Microsoft.Crm.Extensibility.OData.CrmEdmEntityObject edmObject)
0x2f1a  ldloc.2
0x2f1b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.OData.Core]Microsoft.OData.ODataProperty>::Clear()
0x2f20  ldloc.1
0x2f21  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Extensibility.OData.CrmEdmEntityObject::_extraSetContainer
0x2f26  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::GetEnumerator()
0x2f2b  stloc.s  7
0x2f2d  br       loc_2FF0
0x2f32  ldloca.s 7
0x2f34  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, object>::get_Current()
0x2f39  stloc.s  8
0x2f3b  ldloca.s 8
0x2f3d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x2f42  isinst   [System.Web.OData]System.Web.OData.EdmEntityObject
0x2f47  brtrue   loc_2FF0
0x2f4c  ldloca.s 8
0x2f4e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x2f53  isinst   [System.Web.OData]System.Web.OData.EdmEntityObjectCollection
0x2f58  brtrue   loc_2FF0
0x2f5d  ldloca.s 8
0x2f5f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x2f64  stloc.s  9
0x2f66  ldloca.s 8
0x2f68  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x2f6d  isinst   [System.Web.OData]System.Web.OData.IEdmObject
0x2f72  brfalse.s loc_2FAA
0x2f74  ldloca.s 8
0x2f76  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x2f7b  castclass [System.Web.OData]System.Web.OData.IEdmObject
0x2f80  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [System.Web.OData]System.Web.OData.IEdmObject::GetEdmType()
0x2f85  stloc.s  0xA
0x2f87  ldarg.0
0x2f88  call     instance class [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerProvider [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataEdmTypeSerializer::get_SerializerProvider()
0x2f8d  ldloc.s  0xA
0x2f8f  callvirt instance class [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataEdmTypeSerializer [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerProvider::GetEdmTypeSerializer(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x2f94  ldloca.s 8
0x2f96  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x2f9b  ldloc.s  0xA
0x2f9d  ldarg.2
0x2f9e  callvirt instance class [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerContext [System.Web.OData]System.Web.OData.ResourceContext::get_SerializerContext()
0x2fa3  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.ODataValue [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataEdmTypeSerializer::CreateODataValue(object, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference, class [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerContext)
0x2fa8  stloc.s  9
0x2faa  ldloc.3
0x2fab  brtrue.s loc_2FF0
0x2fad  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataProperty::.ctor()
0x2fb2  dup
0x2fb3  ldarg.0
0x2fb4  ldloca.s 8
0x2fb6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x2fbb  call     instance string Microsoft.Crm.Extensibility.CrmODataResourceSerializer::GetODataAllowedPropertyName(string prop)
0x2fc0  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataProperty::set_Name(string)
0x2fc5  dup
0x2fc6  ldloc.s  9
0x2fc8  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataProperty::set_Value(object)
0x2fcd  stloc.s  0xB
0x2fcf  ldloc.2
0x2fd0  ldloc.s  0xB
0x2fd2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.OData.Core]Microsoft.OData.ODataProperty>::Add(var<u1>)
0x2fd7  ldloc.1
0x2fd8  ldloca.s 8
0x2fda  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x2fdf  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Extensibility.OData.CrmEdmEntityObject::GetVocabularyAnnotations(string edmPropertyName)
0x2fe4  stloc.s  0xC
0x2fe6  ldloc.s  0xB
0x2fe8  ldloc.s  0xC
0x2fea  ldarg.2
0x2feb  call     void Microsoft.Crm.Extensibility.OData.EdmUtilities::AddInstanceAnnotations(class [Microsoft.OData.Core]Microsoft.OData.ODataProperty property, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> formattedValueAnnotations, class [System.Web.OData]System.Web.OData.ResourceContext entityInstanceContext)
0x2ff0  ldloca.s 7
0x2ff2  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, object>::MoveNext()
0x2ff7  brtrue   loc_2F32
0x2ffc  leave.s  loc_300C
0x2ffe  ldloca.s 7
0x3000  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, object>
0x3006  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x300b  endfinally
0x300c  ldarg.0
0x300d  ldarg.2
0x300e  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.OData]System.Web.OData.ResourceContext::get_Request()
0x3013  call     instance bool Microsoft.Crm.Extensibility.CrmODataResourceSerializer::IsCustomQueryOptionPresent(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x3018  brfalse.s loc_3047
0x301a  ldloc.0
0x301b  ldloc.2
0x301c  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.OData.Core]Microsoft.OData.ODataProperty, bool> <>c::<>9__13_0
0x3021  dup
0x3022  brtrue.s loc_303B
0x3024  pop
0x3025  ldsfld   class <>c <>c::<>9
0x302a  ldftn    instance bool <>c::<CreateResource>b__13_0(class [Microsoft.OData.Core]Microsoft.OData.ODataProperty x)
0x3030  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.OData.Core]Microsoft.OData.ODataProperty, bool>::.ctor(object, native int)
0x3035  dup
0x3036  stsfld   class [mscorlib]System.Func`2<class [Microsoft.OData.Core]Microsoft.OData.ODataProperty, bool> <>c::<>9__13_0
0x303b  call     T0x2B00001C
0x3040  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataResource::set_Properties(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Core]Microsoft.OData.ODataProperty>)
0x3045  br.s     loc_304E
0x3047  ldloc.0
0x3048  ldloc.2
0x3049  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataResource::set_Properties(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Core]Microsoft.OData.ODataProperty>)
0x304e  ldarg.2
0x304f  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.OData]System.Web.OData.ResourceContext::get_Request()
0x3054  call     class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x3059  stloc.s  4
0x305b  ldloc.s  4
0x305d  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x3062  callvirt instance string Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_ServerNotifications()
0x3067  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x306c  brtrue.s loc_3094
0x306e  ldloc.0
0x306f  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.OData.Core]Microsoft.OData.ODataInstanceAnnotation> [Microsoft.OData.Core]Microsoft.OData.ODataResource::get_InstanceAnnotations()
0x3074  ldstr    aMicrosoftDynam// "Microsoft.Dynamics.CRM.servernotificati"...
0x3079  ldloc.s  4
0x307b  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x3080  callvirt instance string Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_ServerNotifications()
0x3085  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataPrimitiveValue::.ctor(object)
0x308a  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataInstanceAnnotation::.ctor(string, class [Microsoft.OData.Core]Microsoft.OData.ODataValue)
0x308f  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.OData.Core]Microsoft.OData.ODataInstanceAnnotation>::Add(var<u1>)
0x3094  ldloc.0
0x3095  ret
```
