# Microsoft.Crm.Extensibility.CrmODataEntityDeserializer::ApplyNestedProperty

- ea: `0x33e0`
- end: `0x34b7`
- name: `Microsoft.Crm.Extensibility.CrmODataEntityDeserializer::ApplyNestedProperty`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x3380`
- `0x3390`
- `0x33e0`
- `0x1fd40`
- `0x29060`

## string_xrefs

- `0x3449`: `EntityResource should not already contain navigationProperty`
- `0x3474`: `Associate of 1:N navigation property with Create of Update is not supported in CRM`

## pseudocode

```c

```

## disassembly

```asm
0x33e0  ldarg.s  4
0x33e2  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerContext::get_Request()
0x33e7  brfalse.s loc_33F6
0x33e9  ldarg.0
0x33ea  ldarg.s  4
0x33ec  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerContext::get_Request()
0x33f1  call     instance void Microsoft.Crm.Extensibility.CrmODataEntityDeserializer::set_Request(class [System.Net.Http]System.Net.Http.HttpRequestMessage value)
0x33f6  ldarg.1
0x33f7  isinst   [System.Web.OData]System.Web.OData.EdmEntityObject
0x33fc  brfalse  loc_34AB
0x3401  ldarg.2
0x3402  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataItemBase> [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataNestedResourceInfoWrapper::get_NestedItems()
0x3407  call     T0x2B00001D
0x340c  call     T0x2B00001E
0x3411  brfalse  loc_34AB
0x3416  ldarg.2
0x3417  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.ODataNestedResourceInfo [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataNestedResourceInfoWrapper::get_NestedResourceInfo()
0x341c  callvirt instance string [Microsoft.OData.Core]Microsoft.OData.ODataNestedResourceInfo::get_Name()
0x3421  stloc.0
0x3422  ldarg.3
0x3423  ldloc.0
0x3424  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::FindNavigationProperty(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredTypeReference, string)
0x3429  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmNavigationProperty
0x342e  stloc.1
0x342f  ldarg.1
0x3430  castclass [System.Web.OData]System.Web.OData.EdmEntityObject
0x3435  stloc.2
0x3436  ldloc.2
0x3437  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [System.Web.OData]System.Web.OData.Delta::GetChangedPropertyNames()
0x343c  ldloc.0
0x343d  call     T0x2B00001F
0x3442  brfalse.s loc_345A
0x3444  ldc.i4   0x190
0x3449  ldstr    aEntityresource// "EntityResource should not already conta"...
0x344e  ldc.i4.0
0x344f  newarr   [mscorlib]System.Object
0x3454  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x3459  throw
0x345a  ldarg.0
0x345b  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.CrmODataEntityDeserializer::get_Request()
0x3460  call     class [System]System.Uri Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetServiceRouteUri(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x3465  stloc.s  4
0x3467  ldloc.1
0x3468  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmProperty::get_Type()
0x346d  call     bool [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeSemantics::IsCollection(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x3472  brfalse.s loc_347F
0x3474  ldstr    aAssociateOf1NN// "Associate of 1:N navigation property wi"...
0x3479  newobj   instance void [mscorlib]System.NotImplementedException::.ctor(string)
0x347e  throw
0x347f  ldarg.2
0x3480  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataItemBase> [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataNestedResourceInfoWrapper::get_NestedItems()
0x3485  call     T0x2B00001D
0x348a  call     T0x2B000020
0x348f  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.ODataEntityReferenceLink [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataEntityReferenceLinkBase::get_EntityReferenceLink()
0x3494  callvirt instance class [System]System.Uri [Microsoft.OData.Core]Microsoft.OData.ODataEntityReferenceLink::get_Url()
0x3499  ldloc.s  4
0x349b  call     class [System]System.Uri Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetRelativeUri(class [System]System.Uri absoluteUri, class [System]System.Uri serviceRouteUri)
0x34a0  stloc.3
0x34a1  ldloc.2
0x34a2  ldloc.0
0x34a3  ldloc.3
0x34a4  callvirt instance bool [System.Web.OData]System.Web.OData.Delta::TrySetPropertyValue(string, object)
0x34a9  pop
0x34aa  ret
0x34ab  ldarg.0
0x34ac  ldarg.1
0x34ad  ldarg.2
0x34ae  ldarg.3
0x34af  ldarg.s  4
0x34b1  call     instance void [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataResourceDeserializer::ApplyNestedProperty(object, class [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataNestedResourceInfoWrapper, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredTypeReference, class [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerContext)
0x34b6  ret
```
