# Microsoft.Crm.Extensibility.CrmODataResourceSerializer::CreateSelectExpandNode

- ea: `0x23e0`
- end: `0x2a33`
- name: `Microsoft.Crm.Extensibility.CrmODataResourceSerializer::CreateSelectExpandNode`
- size: `1619`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x23e0`
- `0x2a40`
- `0x2a80`
- `0x2ae0`
- `0x2b10`
- `0xff60`
- `0x247c0`
- `0x28bc0`
- `0x28f20`

## pseudocode

```c

```

## disassembly

```asm
0x23e0  ldarg.1
0x23e1  callvirt instance class [System.Web.OData]System.Web.OData.IEdmStructuredObject [System.Web.OData]System.Web.OData.ResourceContext::get_EdmObject()
0x23e6  isinst   [System.Web.OData]System.Web.OData.EdmComplexObject
0x23eb  brfalse  loc_2514
0x23f0  ldarg.1
0x23f1  callvirt instance class [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerContext [System.Web.OData]System.Web.OData.ResourceContext::get_SerializerContext()
0x23f6  stloc.s  8
0x23f8  ldarg.1
0x23f9  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType [System.Web.OData]System.Web.OData.ResourceContext::get_StructuredType()
0x23fe  isinst   [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmComplexType
0x2403  stloc.s  9
0x2405  ldloc.s  8
0x2407  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerContext::get_SelectExpandClause()
0x240c  stloc.s  0xA
0x240e  ldarg.0
0x240f  ldarg.1
0x2410  call     instance class [System.Web.OData]System.Web.OData.Formatter.Serialization.SelectExpandNode [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataResourceSerializer::CreateSelectExpandNode(class [System.Web.OData]System.Web.OData.ResourceContext)
0x2415  stloc.s  0xB
0x2417  ldloc.s  9
0x2419  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty> [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType::get_DeclaredProperties()
0x241e  ldloc.s  0xB
0x2420  callvirt instance class [System]System.Collections.Generic.ISet`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuralProperty> [System.Web.OData]System.Web.OData.Formatter.Serialization.SelectExpandNode::get_SelectedStructuralProperties()
0x2425  call     T0x2B000001
0x242a  call     T0x2B000002
0x242f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty>::GetEnumerator()
0x2434  stloc.s  0xC
0x2436  br.s     loc_24A5
0x2438  ldloc.s  0xC
0x243a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty>::get_Current()
0x243f  stloc.s  0xD
0x2441  ldloc.s  8
0x2443  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationSource [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerContext::get_NavigationSource()
0x2448  brtrue.s loc_2480
0x244a  ldloc.s  8
0x244c  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerContext::get_Model()
0x2451  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityContainer [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel::get_EntityContainer()
0x2456  ldstr    aTemp// "temp"
0x245b  ldarg.1
0x245c  callvirt instance class [System.Web.OData]System.Web.OData.IEdmStructuredObject [System.Web.OData]System.Web.OData.ResourceContext::get_EdmObject()
0x2461  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [System.Web.OData]System.Web.OData.IEdmObject::GetEdmType()
0x2466  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeSemantics::AsEntity(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x246b  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::EntityDefinition(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityTypeReference)
0x2470  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntitySet::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityContainer, string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType)
0x2475  stloc.s  0xE
0x2477  ldloc.s  8
0x2479  ldloc.s  0xE
0x247b  callvirt instance void [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerContext::set_NavigationSource(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationSource)
0x2480  ldloc.s  0xB
0x2482  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty, class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause> [System.Web.OData]System.Web.OData.Formatter.Serialization.SelectExpandNode::get_ExpandedNavigationProperties()
0x2487  ldloc.s  0xD
0x2489  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty, class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause>::ContainsKey(var<u1>)
0x248e  brtrue.s loc_24A5
0x2490  ldloc.s  0xB
0x2492  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty, class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause> [System.Web.OData]System.Web.OData.Formatter.Serialization.SelectExpandNode::get_ExpandedNavigationProperties()
0x2497  ldloc.s  0xD
0x2499  ldloc.s  0xA
0x249b  newobj   instance void valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty, class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause>::.ctor(var<u1>, !!T0)
0x24a0  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty, class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause>>::Add(var<u1>)
0x24a5  ldloc.s  0xC
0x24a7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x24ac  brtrue.s loc_2438
0x24ae  leave.s  loc_24BC
0x24b0  ldloc.s  0xC
0x24b2  brfalse.s loc_24BB
0x24b4  ldloc.s  0xC
0x24b6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x24bb  endfinally
0x24bc  ldloc.s  9
0x24be  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty> [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType::get_DeclaredProperties()
0x24c3  ldloc.s  0xB
0x24c5  callvirt instance class [System]System.Collections.Generic.ISet`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuralProperty> [System.Web.OData]System.Web.OData.Formatter.Serialization.SelectExpandNode::get_SelectedStructuralProperties()
0x24ca  call     T0x2B000001
0x24cf  call     T0x2B000003
0x24d4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmComplexType>::GetEnumerator()
0x24d9  stloc.s  0xF
0x24db  br.s     loc_24FA
0x24dd  ldloc.s  0xF
0x24df  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmComplexType>::get_Current()
0x24e4  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuralProperty
0x24e9  stloc.s  0x10
0x24eb  ldloc.s  0xB
0x24ed  callvirt instance class [System]System.Collections.Generic.ISet`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuralProperty> [System.Web.OData]System.Web.OData.Formatter.Serialization.SelectExpandNode::get_SelectedComplexProperties()
0x24f2  ldloc.s  0x10
0x24f4  callvirt instance bool class [System]System.Collections.Generic.ISet`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuralProperty>::Add(var<u1>)
0x24f9  pop
0x24fa  ldloc.s  0xF
0x24fc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2501  brtrue.s loc_24DD
0x2503  leave.s  loc_2511
0x2505  ldloc.s  0xF
0x2507  brfalse.s loc_2510
0x2509  ldloc.s  0xF
0x250b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2510  endfinally
0x2511  ldloc.s  0xB
0x2513  ret
0x2514  ldarg.1
0x2515  callvirt instance class [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerContext [System.Web.OData]System.Web.OData.ResourceContext::get_SerializerContext()
0x251a  stloc.0
0x251b  ldarg.1
0x251c  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType [System.Web.OData]System.Web.OData.ResourceContext::get_StructuredType()
0x2521  isinst   [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType
0x2526  stloc.1
0x2527  ldnull
0x2528  stloc.2
0x2529  ldloc.0
0x252a  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerContext::get_SelectExpandClause()
0x252f  stloc.3
0x2530  ldloc.3
0x2531  brtrue.s loc_254F
0x2533  ldarg.0
0x2534  ldarg.1
0x2535  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.OData]System.Web.OData.ResourceContext::get_Request()
0x253a  call     instance bool Microsoft.Crm.Extensibility.CrmODataResourceSerializer::IsCustomQueryOptionPresent(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x253f  brfalse.s loc_254F
0x2541  ldloc.3
0x2542  ldloc.1
0x2543  ldloc.0
0x2544  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerContext::get_Model()
0x2549  newobj   instance void [System.Web.OData]System.Web.OData.Formatter.Serialization.SelectExpandNode::.ctor(class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel)
0x254e  ret
0x254f  ldloc.3
0x2550  ldloc.1
0x2551  call     T0x2B000004
0x2556  stloc.s  5
0x2558  ldarg.1
0x2559  callvirt instance class [System.Web.OData]System.Web.OData.IEdmStructuredObject [System.Web.OData]System.Web.OData.ResourceContext::get_EdmObject()
0x255e  isinst   [System.Web.OData]System.Web.OData.EdmEntityObject
0x2563  stloc.s  6
0x2565  ldloc.s  6
0x2567  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [System.Web.OData]System.Web.OData.Delta::GetChangedPropertyNames()
0x256c  stloc.s  7
0x256e  ldloc.0
0x256f  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<object, object> [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerContext::get_Items()
0x2574  ldloc.s  5
0x2576  ldloca.s 0x11
0x2578  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<object, object>::TryGetValue(var<u1>, !!T0)
0x257d  dup
0x257e  brtrue.s loc_2583
0x2580  ldnull
0x2581  br.s     loc_258A
0x2583  ldloc.s  0x11
0x2585  castclass class [mscorlib]System.Tuple`2<class [System.Web.OData]System.Web.OData.Formatter.Serialization.SelectExpandNode, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>
0x258a  stloc.s  4
0x258c  ldloc.s  4
0x258e  brtrue.s loc_259B
0x2590  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x2595  stloc.s  0x13
0x2597  ldloc.s  0x13
0x2599  br.s     loc_25A2
0x259b  ldloc.s  4
0x259d  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [System.Web.OData]System.Web.OData.Formatter.Serialization.SelectExpandNode, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::get_Item2()
0x25a2  stloc.s  0x12
0x25a4  ldloc.3
0x25a5  call     bool Microsoft.Crm.Extensibility.OData.EdmUtilities::IsReferenceQueryCall(class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause selectExpandClause)
0x25aa  brfalse.s loc_25F8
0x25ac  ldloc.3
0x25ad  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectItem> [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause::get_SelectedItems()
0x25b2  call     T0x2B000005
0x25b7  call     T0x2B000006
0x25bc  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataExpandPath [Microsoft.OData.Core]Microsoft.OData.UriParser.ExpandedReferenceSelectItem::get_PathToNavigationProperty()
0x25c1  call     T0x2B000007
0x25c6  castclass [Microsoft.OData.Core]Microsoft.OData.UriParser.NavigationPropertySegment
0x25cb  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty [Microsoft.OData.Core]Microsoft.OData.UriParser.NavigationPropertySegment::get_NavigationProperty()
0x25d0  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x25d5  stloc.s  0x15
0x25d7  ldloc.s  6
0x25d9  ldloc.s  0x15
0x25db  ldloca.s 0x14
0x25dd  callvirt instance bool [System.Web.OData]System.Web.OData.Delta::TryGetPropertyValue(string, object&)
0x25e2  brfalse.s loc_25F8
0x25e4  ldloc.s  0x14
0x25e6  isinst   Microsoft.Crm.Extensibility.OData.CrmEdmEntityObject
0x25eb  brtrue.s loc_25F8
0x25ed  ldloc.s  6
0x25ef  ldloc.s  0x15
0x25f1  ldnull
0x25f2  callvirt instance bool [System.Web.OData]System.Web.OData.Delta::TrySetPropertyValue(string, object)
0x25f7  pop
0x25f8  brfalse.s loc_260F
0x25fa  ldarg.0
0x25fb  ldarg.1
0x25fc  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.OData]System.Web.OData.ResourceContext::get_Request()
0x2601  ldloc.s  0x12
0x2603  ldloc.s  7
0x2605  call     instance bool Microsoft.Crm.Extensibility.CrmODataResourceSerializer::ShouldRecalculateSelectExpandNode(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> prevChangedProps, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> changePropertyNames)
0x260a  brfalse  loc_29EF
0x260f  ldarg.0
0x2610  ldloc.3
0x2611  ldarg.1
0x2612  callvirt instance class [System.Web.OData]System.Web.OData.IEdmStructuredObject [System.Web.OData]System.Web.OData.ResourceContext::get_EdmObject()
0x2617  castclass [System.Web.OData]System.Web.OData.EdmEntityObject
0x261c  call     instance string Microsoft.Crm.Extensibility.CrmODataResourceSerializer::GetSelectClause(class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause selectExpandClause, class [System.Web.OData]System.Web.OData.EdmEntityObject edmEntityObject)
0x2621  stloc.s  0x16
0x2623  ldloc.s  0x16
0x2625  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x262a  brfalse.s loc_2638
0x262c  newobj   instance void [System.Web.OData]System.Web.OData.Formatter.Serialization.SelectExpandNode::.ctor()
0x2631  stloc.s  0x1B
0x2633  leave    loc_2A30
0x2638  ldloc.0
0x2639  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerContext::get_Request()
0x263e  ldloc.s  6
0x2640  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType [System.Web.OData]System.Web.OData.EdmStructuredObject::get_ActualEdmType()
0x2645  ldarg.1
0x2646  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel [System.Web.OData]System.Web.OData.ResourceContext::get_EdmModel()
0x264b  call     class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetQueryOptions(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType edmType, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x2650  callvirt instance class [System.Web.OData]System.Web.OData.ODataQueryContext [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_Context()
0x2655  stloc.s  0x17
0x2657  ldloc.s  0x17
0x2659  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel [System.Web.OData]System.Web.OData.ODataQueryContext::get_Model()
0x265e  ldloc.s  0x17
0x2660  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType [System.Web.OData]System.Web.OData.ODataQueryContext::get_ElementType()
0x2665  ldloc.s  0x17
0x2667  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationSource [System.Web.OData]System.Web.OData.ODataQueryContext::get_NavigationSource()
0x266c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x2671  dup
0x2672  ldstr    aSelect// "$select"
0x2677  ldloc.s  0x16
0x2679  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x267e  dup
0x267f  ldstr    aExpand// "$expand"
0x2684  ldsfld   string [mscorlib]System.String::Empty
0x2689  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x268e  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataQueryOptionParser::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationSource, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>)
0x2693  stloc.s  0x18
0x2695  ldloc.s  0x16
0x2697  ldsfld   string [mscorlib]System.String::Empty
0x269c  ldloc.s  0x17
0x269e  ldloc.s  0x18
0x26a0  newobj   instance void [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::.ctor(string, string, class [System.Web.OData]System.Web.OData.ODataQueryContext, class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataQueryOptionParser)
0x26a5  stloc.s  0x19
0x26a7  ldloc.s  0x19
0x26a9  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x26ae  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectItem> [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause::get_SelectedItems()
0x26b3  stloc.s  0x1A
0x26b5  ldloc.3
0x26b6  brfalse  loc_29BB
0x26bb  ldloc.0
0x26bc  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerContext::get_Request()
0x26c1  ldloc.1
0x26c2  ldarg.1
0x26c3  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel [System.Web.OData]System.Web.OData.ResourceContext::get_EdmModel()
0x26c8  call     class Microsoft.Crm.Extensibility.OData.CustomQueryOptions Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCustomQueryOption(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType edmType, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x26cd  stloc.s  0x1C
0x26cf  ldloc.3
0x26d0  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectItem> [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause::get_SelectedItems()
0x26d5  call     T0x2B000008
0x26da  call     T0x2B000009
0x26df  brtrue.s loc_2705
0x26e1  ldloc.3
0x26e2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectItem> [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause::get_SelectedItems()
0x26e7  call     T0x2B000005
0x26ec  call     T0x2B00000A
0x26f1  brtrue.s loc_2705
0x26f3  ldloc.s  0x1C
0x26f5  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Extensibility.OData.CustomQueryOptions::get_QueryParameters()
0x26fa  ldstr    aExpand// "$expand"
0x26ff  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Remove(var<u1>)
0x2704  pop
0x2705  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectItem>::.ctor()
0x270a  stloc.s  0x1D
0x270c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty>::.ctor()
0x2711  stloc.s  0x1E
0x2713  ldloc.s  0x1A
0x2715  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectItem>::GetEnumerator()
0x271a  stloc.s  0x1F
0x271c  br       loc_27BA
0x2721  ldloc.s  0x1F
0x2723  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectItem>::get_Current()
0x2728  stloc.s  0x20
0x272a  ldloc.s  0x20
0x272c  isinst   [Microsoft.OData.Core]Microsoft.OData.UriParser.ExpandedNavigationSelectItem
0x2731  brtrue   loc_27BA
0x2736  ldloc.s  0x20
0x2738  isinst   [Microsoft.OData.Core]Microsoft.OData.UriParser.PathSelectItem
0x273d  stloc.s  0x21
0x273f  ldloc.s  0x21
0x2741  brfalse.s loc_27B1
0x2743  ldloc.s  0x21
0x2745  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataSelectPath [Microsoft.OData.Core]Microsoft.OData.UriParser.PathSelectItem::get_SelectedPath()
0x274a  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPath::get_FirstSegment()
0x274f  isinst   [Microsoft.OData.Core]Microsoft.OData.UriParser.NavigationPropertySegment
0x2754  stloc.s  0x22
0x2756  ldloc.s  0x22
0x2758  brfalse.s loc_27B1
0x275a  ldloc.s  0x22
0x275c  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty [Microsoft.OData.Core]Microsoft.OData.UriParser.NavigationPropertySegment::get_NavigationProperty()
0x2761  stloc.s  0x23
0x2763  ldloc.s  0x23
0x2765  brfalse.s loc_27B1
0x2767  ldloc.s  0x23
0x2769  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty::get_Type()
0x276e  call     bool [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeSemantics::IsCollection(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x2773  brfalse.s loc_27B1
0x2775  ldloc.s  0x23
0x2777  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty::get_Type()
0x277c  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmCollectionTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeSemantics::AsCollection(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x2781  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::ElementType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmCollectionTypeReference)
0x2786  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference::get_Definition()
  ... truncated ...
```
