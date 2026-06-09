# Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRouteDataProvider::FillNavigationElementData

- ea: `0x2cf80`
- end: `0x2d054`
- name: `Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRouteDataProvider::FillNavigationElementData`
- size: `212`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2c690`
- `0x2c800`

## callees

- `0x2cf80`

## string_xrefs

- `0x2cfcc`: `odatapath`

## pseudocode

```c

```

## disassembly

```asm
0x2cf80  ldarg.2
0x2cf81  callvirt instance class [System.Web.Http]System.Web.Http.Routing.IHttpRouteData [System.Web.Http]System.Web.Http.Controllers.HttpControllerContext::get_RouteData()
0x2cf86  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.Web.Http]System.Web.Http.Routing.IHttpRouteData::get_Values()
0x2cf8b  ldsfld   string Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRouteConstants::Navigation
0x2cf90  ldarg.0
0x2cf91  isinst   [Microsoft.OData.Core]Microsoft.OData.UriParser.NavigationPropertyLinkSegment
0x2cf96  brtrue.s loc_2CFAA
0x2cf98  ldarg.0
0x2cf99  castclass [Microsoft.OData.Core]Microsoft.OData.UriParser.NavigationPropertySegment
0x2cf9e  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty [Microsoft.OData.Core]Microsoft.OData.UriParser.NavigationPropertySegment::get_NavigationProperty()
0x2cfa3  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x2cfa8  br.s     loc_2CFBA
0x2cfaa  ldarg.0
0x2cfab  castclass [Microsoft.OData.Core]Microsoft.OData.UriParser.NavigationPropertyLinkSegment
0x2cfb0  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty [Microsoft.OData.Core]Microsoft.OData.UriParser.NavigationPropertyLinkSegment::get_NavigationProperty()
0x2cfb5  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x2cfba  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2cfbf  ldnull
0x2cfc0  stloc.0
0x2cfc1  ldarg.2
0x2cfc2  callvirt instance class [System.Web.Http]System.Web.Http.Routing.IHttpRouteData [System.Web.Http]System.Web.Http.Controllers.HttpControllerContext::get_RouteData()
0x2cfc7  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.Web.Http]System.Web.Http.Routing.IHttpRouteData::get_Values()
0x2cfcc  ldstr    aOdatapath// "odatapath"
0x2cfd1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::get_Item(void)
0x2cfd6  callvirt instance string [mscorlib]System.Object::ToString()
0x2cfdb  ldc.i4.1
0x2cfdc  newarr   [mscorlib]System.String
0x2cfe1  dup
0x2cfe2  ldc.i4.0
0x2cfe3  ldstr    asc_422BE// "/"
0x2cfe8  stelem.ref
0x2cfe9  ldc.i4.0
0x2cfea  callvirt instance string[] [mscorlib]System.String::Split(string[], valuetype [mscorlib]System.StringSplitOptions)
0x2cfef  stloc.1
0x2cff0  ldloc.1
0x2cff1  ldc.i4.1
0x2cff2  ldelem.ref
0x2cff3  ldstr    asc_3B90E// "("
0x2cff8  ldc.i4.4
0x2cff9  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x2cffe  ldc.i4.1
0x2cfff  add
0x2d000  stloc.2
0x2d001  ldloc.1
0x2d002  ldc.i4.1
0x2d003  ldelem.ref
0x2d004  ldstr    asc_36900// ")"
0x2d009  ldc.i4.4
0x2d00a  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string, valuetype [mscorlib]System.StringComparison)
0x2d00f  ldloc.2
0x2d010  sub
0x2d011  stloc.3
0x2d012  ldloc.3
0x2d013  ldc.i4.m1
0x2d014  beq.s    loc_2D023
0x2d016  ldloc.1
0x2d017  ldc.i4.1
0x2d018  ldelem.ref
0x2d019  ldloc.2
0x2d01a  ldloc.3
0x2d01b  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x2d020  stloc.0
0x2d021  br.s     loc_2D03D
0x2d023  ldarg.1
0x2d024  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>> [Microsoft.OData.Core]Microsoft.OData.UriParser.KeySegment::get_Keys()
0x2d029  call     T0x2B000026
0x2d02e  stloc.s  4
0x2d030  ldloca.s 4
0x2d032  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x2d037  callvirt instance string [mscorlib]System.Object::ToString()
0x2d03c  stloc.0
0x2d03d  ldarg.2
0x2d03e  callvirt instance class [System.Web.Http]System.Web.Http.Routing.IHttpRouteData [System.Web.Http]System.Web.Http.Controllers.HttpControllerContext::get_RouteData()
0x2d043  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.Web.Http]System.Web.Http.Routing.IHttpRouteData::get_Values()
0x2d048  ldsfld   string Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRouteConstants::NavigationKey
0x2d04d  ldloc.0
0x2d04e  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2d053  ret
```
