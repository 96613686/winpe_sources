# Microsoft.Crm.Extensibility.CrmODataResourceSetSerializer::CreateResourceSet

- ea: `0x3c20`
- end: `0x3d89`
- name: `Microsoft.Crm.Extensibility.CrmODataResourceSetSerializer::CreateResourceSet`
- size: `361`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3c20`
- `0x13d10`
- `0x17630`
- `0x17640`
- `0x17650`
- `0x17660`
- `0x17670`
- `0x20290`
- `0x203a0`
- `0x20450`
- `0x20610`
- `0x20b80`

## string_xrefs

- `0x3d25`: `Microsoft.Dynamics.CRM.fetchxmlpagingcookie`

## pseudocode

```c

```

## disassembly

```asm
0x3c20  ldarg.3
0x3c21  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerContext::get_NavigationProperty()
0x3c26  brtrue.s loc_3C2F
0x3c28  ldsfld   string [mscorlib]System.String::Empty
0x3c2d  br.s     loc_3C3A
0x3c2f  ldarg.3
0x3c30  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerContext::get_NavigationProperty()
0x3c35  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x3c3a  stloc.0
0x3c3b  ldarg.0
0x3c3c  ldarg.1
0x3c3d  ldarg.2
0x3c3e  ldarg.3
0x3c3f  call     instance class [Microsoft.OData.Core]Microsoft.OData.ODataResourceSet [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataResourceSetSerializer::CreateResourceSet(class [mscorlib]System.Collections.IEnumerable, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmCollectionTypeReference, class [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerContext)
0x3c44  stloc.1
0x3c45  ldarg.1
0x3c46  isinst   Microsoft.Crm.Extensibility.OData.CrmEdmLinkEntityObjectCollection
0x3c4b  stloc.2
0x3c4c  ldloc.2
0x3c4d  brfalse.s loc_3C7E
0x3c4f  ldloc.0
0x3c50  ldsfld   string [mscorlib]System.String::Empty
0x3c55  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3c5a  brfalse.s loc_3C7E
0x3c5c  ldloc.1
0x3c5d  ldarg.3
0x3c5e  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerContext::get_Request()
0x3c63  ldsfld   string [mscorlib]System.String::Empty
0x3c68  ldloc.0
0x3c69  ldloc.2
0x3c6a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.CrmEdmLinkEntityObjectCollection::get_PrimaryKeyAttributeValue()
0x3c6f  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x3c74  call     class [System]System.Uri Microsoft.Crm.Extensibility.OData.CrmODataUtilities::CreateNextPageLink(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, string pagingCookie, string navigationPropertyName, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> primaryAttributeValue)
0x3c79  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataResourceSetBase::set_NextPageLink(class [System]System.Uri)
0x3c7e  ldarg.1
0x3c7f  isinst   Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection
0x3c84  stloc.3
0x3c85  ldloc.3
0x3c86  brfalse  loc_3D87
0x3c8b  ldarg.3
0x3c8c  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerContext::get_NavigationProperty()
0x3c91  brtrue.s loc_3CDD
0x3c93  ldloc.1
0x3c94  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.OData.Core]Microsoft.OData.ODataInstanceAnnotation> [Microsoft.OData.Core]Microsoft.OData.ODataResourceSetBase::get_InstanceAnnotations()
0x3c99  ldstr    aMicrosoftDynam_1// "Microsoft.Dynamics.CRM.totalrecordcount"
0x3c9e  ldloc.3
0x3c9f  callvirt instance int32 Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection::get_TotalRecordCount()
0x3ca4  box      [mscorlib]System.Int32
0x3ca9  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataPrimitiveValue::.ctor(object)
0x3cae  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataInstanceAnnotation::.ctor(string, class [Microsoft.OData.Core]Microsoft.OData.ODataValue)
0x3cb3  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.OData.Core]Microsoft.OData.ODataInstanceAnnotation>::Add(var<u1>)
0x3cb8  ldloc.1
0x3cb9  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.OData.Core]Microsoft.OData.ODataInstanceAnnotation> [Microsoft.OData.Core]Microsoft.OData.ODataResourceSetBase::get_InstanceAnnotations()
0x3cbe  ldstr    aMicrosoftDynam_2// "Microsoft.Dynamics.CRM.totalrecordcount"...
0x3cc3  ldloc.3
0x3cc4  callvirt instance bool Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection::get_TotalRecordCountLimitExceeded()
0x3cc9  box      [mscorlib]System.Boolean
0x3cce  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataPrimitiveValue::.ctor(object)
0x3cd3  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataInstanceAnnotation::.ctor(string, class [Microsoft.OData.Core]Microsoft.OData.ODataValue)
0x3cd8  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.OData.Core]Microsoft.OData.ODataInstanceAnnotation>::Add(var<u1>)
0x3cdd  ldloc.3
0x3cde  callvirt instance bool Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection::get_HasMoreRecords()
0x3ce3  brfalse.s loc_3D5B
0x3ce5  ldarg.3
0x3ce6  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerContext::get_Request()
0x3ceb  ldloc.0
0x3cec  ldloc.3
0x3ced  callvirt instance string Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection::get_PagingCookie()
0x3cf2  ldarg.3
0x3cf3  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerContext::get_Model()
0x3cf8  call     bool Microsoft.Crm.Extensibility.OData.CrmODataUtilities::IsTopCountNotExceeded(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, string edmNavigationProperty, string pagingCookie, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x3cfd  brfalse.s loc_3D5B
0x3cff  ldloc.3
0x3d00  callvirt instance string Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection::get_PagingCookie()
0x3d05  call     string Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetNextBatchingCookie(string batchingCookie)
0x3d0a  stloc.s  4
0x3d0c  ldarg.3
0x3d0d  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerContext::get_Request()
0x3d12  ldarg.3
0x3d13  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerContext::get_Model()
0x3d18  call     bool Microsoft.Crm.Extensibility.OData.CrmODataUtilities::IsFetchXmlQueryOption(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x3d1d  brfalse.s loc_3D3D
0x3d1f  ldloc.1
0x3d20  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.OData.Core]Microsoft.OData.ODataInstanceAnnotation> [Microsoft.OData.Core]Microsoft.OData.ODataResourceSetBase::get_InstanceAnnotations()
0x3d25  ldstr    aMicrosoftDynam_3// "Microsoft.Dynamics.CRM.fetchxmlpagingco"...
0x3d2a  ldloc.s  4
0x3d2c  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataPrimitiveValue::.ctor(object)
0x3d31  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataInstanceAnnotation::.ctor(string, class [Microsoft.OData.Core]Microsoft.OData.ODataValue)
0x3d36  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.OData.Core]Microsoft.OData.ODataInstanceAnnotation>::Add(var<u1>)
0x3d3b  br.s     loc_3D5B
0x3d3d  ldloc.1
0x3d3e  ldarg.3
0x3d3f  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerContext::get_Request()
0x3d44  ldloc.s  4
0x3d46  ldloc.0
0x3d47  ldloca.s 5
0x3d49  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x3d4f  ldloc.s  5
0x3d51  call     class [System]System.Uri Microsoft.Crm.Extensibility.OData.CrmODataUtilities::CreateNextPageLink(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, string pagingCookie, string navigationPropertyName, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> primaryAttributeValue)
0x3d56  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataResourceSetBase::set_NextPageLink(class [System]System.Uri)
0x3d5b  ldloc.3
0x3d5c  callvirt instance string Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection::get_DeltaToken()
0x3d61  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3d66  brtrue.s loc_3D87
0x3d68  ldloc.3
0x3d69  callvirt instance bool Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection::get_HasMoreRecords()
0x3d6e  brtrue.s loc_3D87
0x3d70  ldloc.1
0x3d71  ldarg.3
0x3d72  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerContext::get_Request()
0x3d77  ldloc.3
0x3d78  callvirt instance string Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection::get_DeltaToken()
0x3d7d  call     class [System]System.Uri Microsoft.Crm.Extensibility.OData.CrmODataUtilities::CreateDeltaLink(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, string dataToken)
0x3d82  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataResourceSetBase::set_DeltaLink(class [System]System.Uri)
0x3d87  ldloc.1
0x3d88  ret
```
