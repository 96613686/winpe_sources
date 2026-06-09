# Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRouteDataProvider::FillEntityData

- ea: `0x2cd20`
- end: `0x2cdd4`
- name: `Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRouteDataProvider::FillEntityData`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2c560`

## callees

- `0x2cd20`

## string_xrefs

- `0x2cd6c`: `odatapath`

## pseudocode

```c

```

## disassembly

```asm
0x2cd20  ldarg.0
0x2cd21  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment::get_EdmType()
0x2cd26  stloc.0
0x2cd27  ldloc.0
0x2cd28  callvirt instance valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeKind [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType::get_TypeKind()
0x2cd2d  ldc.i4.4
0x2cd2e  bne.un.s loc_2CD41
0x2cd30  ldloc.0
0x2cd31  isinst   [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmCollectionType
0x2cd36  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmCollectionType::get_ElementType()
0x2cd3b  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference::get_Definition()
0x2cd40  stloc.0
0x2cd41  ldarg.1
0x2cd42  callvirt instance class [System.Web.Http]System.Web.Http.Routing.IHttpRouteData [System.Web.Http]System.Web.Http.Controllers.HttpControllerContext::get_RouteData()
0x2cd47  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.Web.Http]System.Web.Http.Routing.IHttpRouteData::get_Values()
0x2cd4c  ldsfld   string Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRouteConstants::EntityName
0x2cd51  ldloc.0
0x2cd52  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType
0x2cd57  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType::get_Name()
0x2cd5c  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2cd61  ldarg.1
0x2cd62  callvirt instance class [System.Web.Http]System.Web.Http.Routing.IHttpRouteData [System.Web.Http]System.Web.Http.Controllers.HttpControllerContext::get_RouteData()
0x2cd67  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.Web.Http]System.Web.Http.Routing.IHttpRouteData::get_Values()
0x2cd6c  ldstr    aOdatapath// "odatapath"
0x2cd71  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::get_Item(void)
0x2cd76  callvirt instance string [mscorlib]System.Object::ToString()
0x2cd7b  stloc.1
0x2cd7c  ldloc.1
0x2cd7d  ldc.i4.1
0x2cd7e  newarr   [mscorlib]System.String
0x2cd83  dup
0x2cd84  ldc.i4.0
0x2cd85  ldstr    asc_422BE// "/"
0x2cd8a  stelem.ref
0x2cd8b  ldc.i4.0
0x2cd8c  callvirt instance string[] [mscorlib]System.String::Split(string[], valuetype [mscorlib]System.StringSplitOptions)
0x2cd91  dup
0x2cd92  ldc.i4.0
0x2cd93  ldelem.ref
0x2cd94  ldstr    asc_3B90E// "("
0x2cd99  ldc.i4.4
0x2cd9a  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x2cd9f  ldc.i4.1
0x2cda0  add
0x2cda1  stloc.2
0x2cda2  ldc.i4.0
0x2cda3  ldelem.ref
0x2cda4  ldstr    asc_36900// ")"
0x2cda9  ldc.i4.4
0x2cdaa  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string, valuetype [mscorlib]System.StringComparison)
0x2cdaf  ldloc.2
0x2cdb0  sub
0x2cdb1  stloc.3
0x2cdb2  ldloc.1
0x2cdb3  ldloc.2
0x2cdb4  ldloc.3
0x2cdb5  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x2cdba  stloc.s  4
0x2cdbc  ldarg.1
0x2cdbd  callvirt instance class [System.Web.Http]System.Web.Http.Routing.IHttpRouteData [System.Web.Http]System.Web.Http.Controllers.HttpControllerContext::get_RouteData()
0x2cdc2  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.Web.Http]System.Web.Http.Routing.IHttpRouteData::get_Values()
0x2cdc7  ldsfld   string Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRouteConstants::Key
0x2cdcc  ldloc.s  4
0x2cdce  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2cdd3  ret
```
