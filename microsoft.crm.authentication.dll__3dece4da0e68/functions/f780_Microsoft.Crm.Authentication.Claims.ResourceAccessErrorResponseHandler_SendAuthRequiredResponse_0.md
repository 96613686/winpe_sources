# Microsoft.Crm.Authentication.Claims.ResourceAccessErrorResponseHandler::SendAuthRequiredResponse_0

- ea: `0xf780`
- end: `0xf92b`
- name: `Microsoft.Crm.Authentication.Claims.ResourceAccessErrorResponseHandler::SendAuthRequiredResponse_0`
- size: `427`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xf770`
- `0xf940`

## callees

- `0xcc0`
- `0x1a00`
- `0x1b30`
- `0xf780`
- `0xf9f0`
- `0xfa80`
- `0xfb50`
- `0xfbd0`

## pseudocode

```c

```

## disassembly

```asm
0xf780  ldarg.0
0xf781  ldstr    aContext// "context"
0xf786  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xf78b  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xf790  stloc.0
0xf791  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_AzureActiveDirectoryFederationProvider()
0xf796  brfalse  loc_F91D
0xf79b  ldc.i4.1
0xf79c  stloc.1
0xf79d  ldc.i4.1
0xf79e  stloc.2
0xf79f  ldarg.0
0xf7a0  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xf7a5  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Params()
0xf7aa  callvirt instance string[] [System]System.Collections.Specialized.NameValueCollection::get_AllKeys()
0xf7af  ldstr    aSdkclientversi// "SdkClientVersion"
0xf7b4  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0xf7b9  call     T0x2B000024
0xf7be  brfalse.s loc_F822
0xf7c0  ldarg.0
0xf7c1  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xf7c6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Params()
0xf7cb  callvirt instance string[] [System]System.Collections.Specialized.NameValueCollection::get_AllKeys()
0xf7d0  ldsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__4_0
0xf7d5  dup
0xf7d6  brtrue.s loc_F7EF
0xf7d8  pop
0xf7d9  ldsfld   class <>c <>c::<>9
0xf7de  ldftn    instance bool <>c::<SendAuthRequiredResponse>b__4_0(string k)
0xf7e4  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0xf7e9  dup
0xf7ea  stsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__4_0
0xf7ef  call     T0x2B00001E
0xf7f4  stloc.s  6
0xf7f6  ldloc.s  6
0xf7f8  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xf7fd  brtrue.s loc_F822
0xf7ff  ldarg.0
0xf800  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xf805  ldloc.s  6
0xf807  callvirt instance string [System.Web]System.Web.HttpRequest::get_Item(string)
0xf80c  ldloca.s 5
0xf80e  call     bool [mscorlib]System.Version::TryParse(string, class [mscorlib]System.Version&)
0xf813  brfalse.s loc_F822
0xf815  ldloc.s  5
0xf817  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Authentication.Claims.ResourceAccessErrorResponseHandler::UR2Version
0xf81c  call     bool [mscorlib]System.Version::op_LessThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0xf821  stloc.2
0xf822  ldarg.0
0xf823  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xf828  call     bool Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::IsODataV4Request(class [System.Web]System.Web.HttpRequest request)
0xf82d  brtrue.s loc_F83C
0xf82f  ldarg.0
0xf830  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xf835  call     bool Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::IsSearchRestEndpointRequest(class [System.Web]System.Web.HttpRequest request)
0xf83a  brfalse.s loc_F83E
0xf83c  ldc.i4.0
0xf83d  stloc.2
0xf83e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xf843  stloc.3
0xf844  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xf849  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xf84e  stloc.s  4
0xf850  ldc.i4.2
0xf851  ldloc.s  4
0xf853  bne.un.s loc_F897
0xf855  call     bool [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_IsDiscoveryRequest()
0xf85a  brtrue.s loc_F879
0xf85c  ldarg.0
0xf85d  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xf862  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0xf867  callvirt instance string [System]System.Uri::get_AbsolutePath()
0xf86c  ldstr    aDiscoverySvcWe// "Discovery.svc/web"
0xf871  ldc.i4.5
0xf872  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0xf877  brfalse.s loc_F884
0xf879  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.DiscoveryRole [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_ServerRole()
0xf87e  ldc.i4.1
0xf87f  ceq
0xf881  stloc.1
0xf882  br.s     loc_F897
0xf884  ldarg.0
0xf885  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xf88a  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmAuthorizationUtility::GetRequestedOrganization(class [System.Web]System.Web.HttpRequest request)
0xf88f  stloc.3
0xf890  ldloc.3
0xf891  call     bool [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::IsOrganizationFederationEnabled(valuetype [mscorlib]System.Guid)
0xf896  stloc.1
0xf897  ldloc.1
0xf898  brfalse  loc_F91D
0xf89d  ldloc.0
0xf89e  ldstr    aBearer_0// "Bearer "
0xf8a3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf8a8  pop
0xf8a9  ldarg.2
0xf8aa  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xf8af  brtrue.s loc_F8C5
0xf8b1  ldloc.0
0xf8b2  ldarg.2
0xf8b3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf8b8  pop
0xf8b9  ldloc.0
0xf8ba  ldstr    asc_21C6A// ", "
0xf8bf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf8c4  pop
0xf8c5  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_AzureActiveDirectoryFederationProvider()
0xf8ca  ldstr    aPassiveendpoin// "PassiveEndpoint"
0xf8cf  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::GetFederationProviderProperty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, string)
0xf8d4  isinst   [mscorlib]System.String
0xf8d9  stloc.s  7
0xf8db  ldloc.s  7
0xf8dd  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xf8e2  brfalse.s loc_F8EB
0xf8e4  ldsfld   string [mscorlib]System.String::Empty
0xf8e9  stloc.s  7
0xf8eb  ldloc.2
0xf8ec  brfalse.s loc_F8F8
0xf8ee  ldloc.0
0xf8ef  ldloc.s  7
0xf8f1  call     void Microsoft.Crm.Authentication.Claims.ResourceAccessErrorResponseHandler::BuildLegacyAuthRequiredResponse(class [mscorlib]System.Text.StringBuilder stringBuilder, string relyingPartyUrl)
0xf8f6  br.s     loc_F90F
0xf8f8  ldloc.0
0xf8f9  ldloc.s  7
0xf8fb  ldloc.3
0xf8fc  ldloc.s  4
0xf8fe  call     void Microsoft.Crm.Authentication.Claims.ResourceAccessErrorResponseHandler::BuildStandardAuthRequiredResponse(class [mscorlib]System.Text.StringBuilder stringBuilder, string relyingPartyUrl, valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku configSku)
0xf903  ldloc.0
0xf904  ldarg.0
0xf905  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xf90a  call     void Microsoft.Crm.Authentication.Claims.ResourceAccessErrorResponseHandler::AddResourceIdToAuthChallenge(class [mscorlib]System.Text.StringBuilder stringBuilder, class [System.Web]System.Web.HttpRequest request)
0xf90f  ldarg.0
0xf910  ldarg.1
0xf911  ldloc.0
0xf912  callvirt instance string [mscorlib]System.Object::ToString()
0xf917  call     void Microsoft.Crm.Authentication.Claims.ResourceAccessErrorResponseHandler::SendResponse(class [System.Web]System.Web.HttpContext context, valuetype [System]System.Net.HttpStatusCode statusCode, string responseDescription)
0xf91c  ret
0xf91d  ldarg.0
0xf91e  ldarg.1
0xf91f  ldloc.0
0xf920  callvirt instance string [mscorlib]System.Object::ToString()
0xf925  call     void Microsoft.Crm.Authentication.Claims.ResourceAccessErrorResponseHandler::SendResponse(class [System.Web]System.Web.HttpContext context, valuetype [System]System.Net.HttpStatusCode statusCode, string responseDescription)
0xf92a  ret
```
