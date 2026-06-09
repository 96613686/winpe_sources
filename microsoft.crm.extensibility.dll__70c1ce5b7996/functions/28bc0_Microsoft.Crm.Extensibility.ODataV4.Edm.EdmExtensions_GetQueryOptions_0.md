# Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetQueryOptions_0

- ea: `0x28bc0`
- end: `0x28c28`
- name: `Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetQueryOptions_0`
- size: `104`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x23e0`
- `0x28bb0`
- `0x28f20`

## callees

- `0x28bc0`
- `0x28c30`

## string_xrefs

- `0x28c08`: `query parameters not supported on complex type.`

## pseudocode

```c

```

## disassembly

```asm
0x28bc0  ldarg.0
0x28bc1  call     class [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageExtensions::ODataProperties(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x28bc6  callvirt instance class [System.Web.OData]System.Web.OData.Routing.ODataPath [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties::get_Path()
0x28bcb  stloc.0
0x28bcc  ldarg.1
0x28bcd  stloc.1
0x28bce  ldloc.1
0x28bcf  brtrue.s loc_28C19
0x28bd1  ldloc.0
0x28bd2  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType [System.Web.OData]System.Web.OData.Routing.ODataPath::get_EdmType()
0x28bd7  stloc.1
0x28bd8  ldloc.1
0x28bd9  callvirt instance valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeKind [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType::get_TypeKind()
0x28bde  ldc.i4.4
0x28bdf  bne.un.s loc_28BF2
0x28be1  ldloc.1
0x28be2  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmCollectionType
0x28be7  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmCollectionType::get_ElementType()
0x28bec  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference::get_Definition()
0x28bf1  stloc.1
0x28bf2  ldloc.1
0x28bf3  callvirt instance valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeKind [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType::get_TypeKind()
0x28bf8  ldc.i4.3
0x28bf9  bne.un.s loc_28C19
0x28bfb  ldarg.0
0x28bfc  call     bool Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::ValidateComplexTypeQueryParameters(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x28c01  brtrue.s loc_28C19
0x28c03  ldc.i4   0x190
0x28c08  ldstr    aQueryParameter// "query parameters not supported on compl"...
0x28c0d  ldc.i4.0
0x28c0e  newarr   [mscorlib]System.Object
0x28c13  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x28c18  throw
0x28c19  ldarg.2
0x28c1a  ldloc.1
0x28c1b  ldloc.0
0x28c1c  newobj   instance void [System.Web.OData]System.Web.OData.ODataQueryContext::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType, class [System.Web.OData]System.Web.OData.Routing.ODataPath)
0x28c21  ldarg.0
0x28c22  newobj   instance void [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::.ctor(class [System.Web.OData]System.Web.OData.ODataQueryContext, class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x28c27  ret
```
