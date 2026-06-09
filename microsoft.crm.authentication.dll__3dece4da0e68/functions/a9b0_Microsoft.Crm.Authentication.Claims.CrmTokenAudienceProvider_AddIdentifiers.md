# Microsoft.Crm.Authentication.Claims.CrmTokenAudienceProvider::AddIdentifiers

- ea: `0xa9b0`
- end: `0xaa41`
- name: `Microsoft.Crm.Authentication.Claims.CrmTokenAudienceProvider::AddIdentifiers`
- size: `145`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0xa9b0`
- `0xaa50`
- `0xaaa0`
- `0xab40`
- `0xc050`
- `0xc080`

## pseudocode

```c

```

## disassembly

```asm
0xa9b0  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System]System.Uri>::.ctor()
0xa9b5  stloc.0
0xa9b6  call     class [System]System.Uri Microsoft.Crm.Authentication.Claims.ClaimsUtility::get_RelyingPartyUrl()
0xa9bb  ldnull
0xa9bc  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0xa9c1  brfalse.s loc_A9CE
0xa9c3  ldloc.0
0xa9c4  call     class [System]System.Uri Microsoft.Crm.Authentication.Claims.ClaimsUtility::get_RelyingPartyUrl()
0xa9c9  call     void Microsoft.Crm.Authentication.Claims.CrmTokenAudienceProvider::AddAudienceUri(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System]System.Uri> audiences, class [System]System.Uri uri)
0xa9ce  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xa9d3  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xa9d8  ldc.i4.1
0xa9d9  bne.un.s loc_A9F2
0xa9db  ldc.i4.0
0xa9dc  ldc.i4.1
0xa9dd  call     class [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider [Microsoft.Crm.Core]Microsoft.Crm.WebServices.OrganizationEndpointProviderFactory::Create(int32, bool)
0xa9e2  stloc.1
0xa9e3  ldloc.1
0xa9e4  brfalse.s loc_A9F2
0xa9e6  ldloc.0
0xa9e7  ldloc.1
0xa9e8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.WebServices.EndpointConfiguration [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider::get_EndpointConfiguration()
0xa9ed  call     void Microsoft.Crm.Authentication.Claims.CrmTokenAudienceProvider::AddOnPremiseRealm(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System]System.Uri> audiences, class [Microsoft.Crm.Core]Microsoft.Crm.WebServices.EndpointConfiguration endpointConfiguration)
0xa9f2  call     class [System]System.Uri Microsoft.Crm.Authentication.Claims.ClaimsUtility::get_ExternalRelyingPartyUrl()
0xa9f7  ldnull
0xa9f8  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0xa9fd  brfalse.s loc_AA0A
0xa9ff  ldloc.0
0xaa00  call     class [System]System.Uri Microsoft.Crm.Authentication.Claims.ClaimsUtility::get_ExternalRelyingPartyUrl()
0xaa05  call     void Microsoft.Crm.Authentication.Claims.CrmTokenAudienceProvider::AddAudienceUri(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System]System.Uri> audiences, class [System]System.Uri uri)
0xaa0a  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xaa0f  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xaa14  ldc.i4.2
0xaa15  bne.un.s loc_AA22
0xaa17  ldloc.0
0xaa18  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_OrgIdFederationProvider()
0xaa1d  call     void Microsoft.Crm.Authentication.Claims.CrmTokenAudienceProvider::AddProviderIdentifiers(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System]System.Uri> audiences, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag federationProvider)
0xaa22  ldloc.0
0xaa23  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_AzureActiveDirectoryFederationProvider()
0xaa28  call     void Microsoft.Crm.Authentication.Claims.CrmTokenAudienceProvider::AddProviderIdentifiers(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System]System.Uri> audiences, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag federationProvider)
0xaa2d  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_ExchangeTokenServerFederationProvider()
0xaa32  brfalse.s loc_AA3F
0xaa34  ldloc.0
0xaa35  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_ExchangeTokenServerFederationProvider()
0xaa3a  call     void Microsoft.Crm.Authentication.Claims.CrmTokenAudienceProvider::AddProviderIdentifiers(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System]System.Uri> audiences, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag federationProvider)
0xaa3f  ldloc.0
0xaa40  ret
```
