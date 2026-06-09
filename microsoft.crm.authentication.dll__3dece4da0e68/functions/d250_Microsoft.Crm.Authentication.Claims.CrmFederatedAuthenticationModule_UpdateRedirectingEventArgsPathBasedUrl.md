# Microsoft.Crm.Authentication.Claims.CrmFederatedAuthenticationModule::UpdateRedirectingEventArgsPathBasedUrl

- ea: `0xd250`
- end: `0xd2ca`
- name: `Microsoft.Crm.Authentication.Claims.CrmFederatedAuthenticationModule::UpdateRedirectingEventArgsPathBasedUrl`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0xd2d0`

## callees

- `0xc050`
- `0xc0d0`
- `0xd250`
- `0xd470`
- `0xdb00`

## pseudocode

```c

```

## disassembly

```asm
0xd250  ldarg.0
0xd251  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.Claims.RedirectLocation::get_OrganizationId()
0xd256  ldstr    aIntegratedauth// "IntegratedAuthenticationMethod"
0xd25b  call     string Microsoft.Crm.Authentication.Claims.ClaimsUtility::GetAuthenticationMethod(valuetype [mscorlib]System.Guid organizationId, string method)
0xd260  stloc.0
0xd261  ldloc.0
0xd262  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd267  brtrue.s loc_D275
0xd269  ldarg.1
0xd26a  callvirt instance class [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage [System.IdentityModel.Services]System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs::get_SignInRequestMessage()
0xd26f  ldloc.0
0xd270  callvirt instance void [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage::set_AuthenticationType(string)
0xd275  ldarg.0
0xd276  call     string Microsoft.Crm.Authentication.Claims.CrmFederatedAuthenticationModule::SetSignOnRedirectContext(class Microsoft.Crm.Authentication.Claims.RedirectLocation redirectLocation)
0xd27b  stloc.1
0xd27c  ldloc.1
0xd27d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd282  brtrue.s loc_D290
0xd284  ldarg.1
0xd285  callvirt instance class [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage [System.IdentityModel.Services]System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs::get_SignInRequestMessage()
0xd28a  ldloc.1
0xd28b  callvirt instance void [System.IdentityModel.Services]System.IdentityModel.Services.WSFederationMessage::set_Context(string)
0xd290  ldarg.1
0xd291  callvirt instance class [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage [System.IdentityModel.Services]System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs::get_SignInRequestMessage()
0xd296  call     class [System]System.Uri Microsoft.Crm.Authentication.Claims.ClaimsUtility::get_RelyingPartyUrl()
0xd29b  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0xd2a0  callvirt instance void [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage::set_Realm(string)
0xd2a5  ldarg.1
0xd2a6  callvirt instance class [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage [System.IdentityModel.Services]System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs::get_SignInRequestMessage()
0xd2ab  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_FederationProvider()
0xd2b0  ldstr    aPassiveendpoin// "PassiveEndpoint"
0xd2b5  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::GetFederationProviderProperty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, string)
0xd2ba  isinst   [mscorlib]System.String
0xd2bf  newobj   instance void [System]System.Uri::.ctor(string)
0xd2c4  callvirt instance void [System.IdentityModel.Services]System.IdentityModel.Services.FederationMessage::set_BaseUri(class [System]System.Uri)
0xd2c9  ret
```
