# Microsoft.Crm.Authentication.Claims.CrmFederatedAuthenticationModule::UpdateRedirectingEventArgsNonPathBasedUrl

- ea: `0xcf40`
- end: `0xd250`
- name: `Microsoft.Crm.Authentication.Claims.CrmFederatedAuthenticationModule::UpdateRedirectingEventArgsNonPathBasedUrl`
- size: `784`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0xd2d0`

## callees

- `0x990`
- `0xcc0`
- `0x1070`
- `0x7d40`
- `0xc0d0`
- `0xc160`
- `0xcf40`
- `0xd470`
- `0xdb00`
- `0xdb20`
- `0xdb40`
- `0xdb50`
- `0xdbc0`
- `0xdbe0`

## string_xrefs

- `0xd023`: `common`
- `0xcff3`: `AzureActiveDirectoryFederationProvider Passive Endpoint returned empty string`

## pseudocode

```c

```

## disassembly

```asm
0xcf40  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xcf45  stloc.0
0xcf46  ldarg.0
0xcf47  callvirt instance string Microsoft.Crm.Authentication.Claims.RedirectLocation::get_Location()
0xcf4c  newobj   instance void [System]System.UriBuilder::.ctor(string)
0xcf51  stloc.1
0xcf52  ldloc.1
0xcf53  callvirt instance string [System]System.UriBuilder::get_Query()
0xcf58  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xcf5d  ldc.i4.0
0xcf5e  ceq
0xcf60  stloc.2
0xcf61  ldloc.1
0xcf62  ldsfld   string [mscorlib]System.String::Empty
0xcf67  callvirt instance void [System]System.UriBuilder::set_Path(string)
0xcf6c  ldloc.1
0xcf6d  ldsfld   string [mscorlib]System.String::Empty
0xcf72  callvirt instance void [System]System.UriBuilder::set_Query(string)
0xcf77  ldarg.0
0xcf78  ldloc.1
0xcf79  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0xcf7e  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0xcf83  callvirt instance void Microsoft.Crm.Authentication.Claims.RedirectLocation::set_Realm(string value)
0xcf88  ldarg.1
0xcf89  callvirt instance class [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage [System.IdentityModel.Services]System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs::get_SignInRequestMessage()
0xcf8e  ldarg.0
0xcf8f  callvirt instance string Microsoft.Crm.Authentication.Claims.RedirectLocation::get_Realm()
0xcf94  callvirt instance void [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage::set_Realm(string)
0xcf99  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xcf9e  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xcfa3  ldc.i4.2
0xcfa4  bne.un   loc_D1E5
0xcfa9  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_OrgIdFederationProvider()
0xcfae  brfalse  loc_D24F
0xcfb3  ldloc.0
0xcfb4  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xcfb9  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmAuthorizationUtility::GetRequestedOrganization(class [System.Web]System.Web.HttpRequest request)
0xcfbe  stloc.3
0xcfbf  ldloc.3
0xcfc0  call     bool Microsoft.Crm.Authentication.CrmAuthorizationUtility::GetEvoStsSettingForOrganization(valuetype [mscorlib]System.Guid orgId)
0xcfc5  brfalse  loc_D09A
0xcfca  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_AzureActiveDirectoryFederationProvider()
0xcfcf  brfalse  loc_D09A
0xcfd4  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_AzureActiveDirectoryFederationProvider()
0xcfd9  ldstr    aPassiveendpoin// "PassiveEndpoint"
0xcfde  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::GetFederationProviderProperty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, string)
0xcfe3  castclass [mscorlib]System.String
0xcfe8  stloc.s  6
0xcfea  ldloc.s  6
0xcfec  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xcff1  brfalse.s loc_CFFE
0xcff3  ldstr    aAzureactivedir// "AzureActiveDirectoryFederationProvider "...
0xcff8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0xcffd  throw
0xcffe  ldloc.3
0xcfff  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xd004  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xd009  brfalse.s loc_D03C
0xd00b  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::.ctor()
0xd010  ldloc.3
0xd011  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::RetrieveOrganizationContextId(valuetype [mscorlib]System.Guid)
0xd016  stloc.s  7
0xd018  ldloca.s 7
0xd01a  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0xd01f  brfalse.s loc_D03C
0xd021  ldloc.s  6
0xd023  ldstr    aCommon// "common"
0xd028  ldloca.s 7
0xd02a  constrained. valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xd030  callvirt instance string [mscorlib]System.Object::ToString()
0xd035  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xd03a  stloc.s  6
0xd03c  ldarg.1
0xd03d  callvirt instance class [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage [System.IdentityModel.Services]System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs::get_SignInRequestMessage()
0xd042  ldloc.s  6
0xd044  newobj   instance void [System]System.Uri::.ctor(string)
0xd049  callvirt instance void [System.IdentityModel.Services]System.IdentityModel.Services.FederationMessage::set_BaseUri(class [System]System.Uri)
0xd04e  ldarg.1
0xd04f  callvirt instance class [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage [System.IdentityModel.Services]System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs::get_SignInRequestMessage()
0xd054  ldarg.0
0xd055  callvirt instance string Microsoft.Crm.Authentication.Claims.RedirectLocation::get_Realm()
0xd05a  callvirt instance void [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage::set_Realm(string)
0xd05f  ldarg.1
0xd060  callvirt instance class [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage [System.IdentityModel.Services]System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs::get_SignInRequestMessage()
0xd065  ldarg.0
0xd066  callvirt instance string Microsoft.Crm.Authentication.Claims.RedirectLocation::get_Location()
0xd06b  call     string Microsoft.Crm.Authentication.AuthRedirectUrlBuilder::BuildReturnUrl(string redirectLocation)
0xd070  callvirt instance void [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage::set_Reply(string)
0xd075  ldarg.0
0xd076  callvirt instance string Microsoft.Crm.Authentication.Claims.RedirectLocation::get_LoginHint()
0xd07b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd080  brtrue.s loc_D0ED
0xd082  ldarg.1
0xd083  callvirt instance class [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage [System.IdentityModel.Services]System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs::get_SignInRequestMessage()
0xd088  ldstr    aLoginHint// "login_hint"
0xd08d  ldarg.0
0xd08e  callvirt instance string Microsoft.Crm.Authentication.Claims.RedirectLocation::get_LoginHint()
0xd093  callvirt instance void [System.IdentityModel.Services]System.IdentityModel.Services.FederationMessage::SetParameter(string, string)
0xd098  br.s     loc_D0ED
0xd09a  ldarg.1
0xd09b  callvirt instance class [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage [System.IdentityModel.Services]System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs::get_SignInRequestMessage()
0xd0a0  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_OrgIdFederationProvider()
0xd0a5  ldstr    aPassiveendpoin// "PassiveEndpoint"
0xd0aa  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::GetFederationProviderProperty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, string)
0xd0af  castclass [mscorlib]System.String
0xd0b4  newobj   instance void [System]System.Uri::.ctor(string)
0xd0b9  callvirt instance void [System.IdentityModel.Services]System.IdentityModel.Services.FederationMessage::set_BaseUri(class [System]System.Uri)
0xd0be  ldarg.1
0xd0bf  callvirt instance class [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage [System.IdentityModel.Services]System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs::get_SignInRequestMessage()
0xd0c4  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_FederationProvider()
0xd0c9  ldstr    aName// "Name"
0xd0ce  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::GetFederationProviderProperty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, string)
0xd0d3  castclass [mscorlib]System.String
0xd0d8  callvirt instance void [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage::set_Realm(string)
0xd0dd  ldarg.1
0xd0de  callvirt instance class [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage [System.IdentityModel.Services]System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs::get_SignInRequestMessage()
0xd0e3  call     string Microsoft.Crm.Authentication.Claims.ClaimsUtility::get_FederationProviderPassiveEndpoint()
0xd0e8  callvirt instance void [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage::set_Reply(string)
0xd0ed  ldstr    aPrWsfederation// "pr=wsfederation"
0xd0f2  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0xd0f7  stloc.s  4
0xd0f9  ldloc.s  4
0xd0fb  ldstr    aRm// "&rm="
0xd100  ldarg.0
0xd101  callvirt instance string Microsoft.Crm.Authentication.Claims.RedirectLocation::get_Realm()
0xd106  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0xd10b  call     string [mscorlib]System.String::Concat(string, string)
0xd110  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd115  pop
0xd116  ldarg.0
0xd117  callvirt instance string Microsoft.Crm.Authentication.Claims.RedirectLocation::get_Location()
0xd11c  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0xd121  stloc.s  5
0xd123  ldarg.0
0xd124  callvirt instance string Microsoft.Crm.Authentication.Claims.RedirectLocation::get_ClientId()
0xd129  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xd12e  brtrue.s loc_D16F
0xd130  ldloc.s  5
0xd132  ldloc.2
0xd133  brtrue.s loc_D13C
0xd135  ldstr    asc_1941E// "?"
0xd13a  br.s     loc_D141
0xd13c  ldstr    asc_1941A// "&"
0xd141  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd146  pop
0xd147  ldloc.s  5
0xd149  ldstr    aWctx_0// "wctx="
0xd14e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd153  pop
0xd154  ldarg.0
0xd155  callvirt instance string Microsoft.Crm.Authentication.Claims.RedirectLocation::get_ClientId()
0xd15a  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xd15f  brtrue.s loc_D16F
0xd161  ldloc.s  5
0xd163  ldarg.0
0xd164  callvirt instance string Microsoft.Crm.Authentication.Claims.RedirectLocation::get_ClientId()
0xd169  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd16e  pop
0xd16f  ldloc.s  4
0xd171  ldstr    aRu// "&ru="
0xd176  ldloc.s  5
0xd178  callvirt instance string [mscorlib]System.Object::ToString()
0xd17d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0xd182  call     string [mscorlib]System.String::Concat(string, string)
0xd187  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd18c  pop
0xd18d  ldloc.s  4
0xd18f  ldstr    aRy// "&ry="
0xd194  ldloc.s  5
0xd196  callvirt instance string [mscorlib]System.Object::ToString()
0xd19b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0xd1a0  call     string [mscorlib]System.String::Concat(string, string)
0xd1a5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xd1aa  pop
0xd1ab  ldarg.1
0xd1ac  callvirt instance class [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage [System.IdentityModel.Services]System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs::get_SignInRequestMessage()
0xd1b1  ldloc.s  4
0xd1b3  callvirt instance string [mscorlib]System.Object::ToString()
0xd1b8  callvirt instance void [System.IdentityModel.Services]System.IdentityModel.Services.WSFederationMessage::set_Context(string)
0xd1bd  call     bool [Microsoft.Crm.Core.Extensions]Microsoft.Crm.MobileUtility::IsMobileDevice()
0xd1c2  brtrue.s loc_D1CF
0xd1c4  ldloc.0
0xd1c5  call     bool Microsoft.Crm.Authentication.Common.AuthenticationContextExtensions::IsOAuthDevice(class [System.Web]System.Web.HttpContext context)
0xd1ca  brfalse  loc_D24F
0xd1cf  ldarg.1
0xd1d0  callvirt instance class [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage [System.IdentityModel.Services]System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs::get_SignInRequestMessage()
0xd1d5  ldstr    aPopupui// "Popupui"
0xd1da  ldstr    a1// "1"
0xd1df  callvirt instance void [System.IdentityModel.Services]System.IdentityModel.Services.FederationMessage::SetParameter(string, string)
0xd1e4  ret
0xd1e5  ldarg.0
0xd1e6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.Claims.RedirectLocation::get_OrganizationId()
0xd1eb  ldstr    aIfdauthenticat// "IfdAuthenticationMethod"
0xd1f0  call     string Microsoft.Crm.Authentication.Claims.ClaimsUtility::GetAuthenticationMethod(valuetype [mscorlib]System.Guid organizationId, string method)
0xd1f5  stloc.s  8
0xd1f7  ldloc.s  8
0xd1f9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd1fe  brtrue.s loc_D20D
0xd200  ldarg.1
0xd201  callvirt instance class [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage [System.IdentityModel.Services]System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs::get_SignInRequestMessage()
0xd206  ldloc.s  8
0xd208  callvirt instance void [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage::set_AuthenticationType(string)
0xd20d  ldarg.0
0xd20e  call     string Microsoft.Crm.Authentication.Claims.CrmFederatedAuthenticationModule::SetSignOnRedirectContext(class Microsoft.Crm.Authentication.Claims.RedirectLocation redirectLocation)
0xd213  stloc.s  9
0xd215  ldloc.s  9
0xd217  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd21c  brtrue.s loc_D22B
0xd21e  ldarg.1
0xd21f  callvirt instance class [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage [System.IdentityModel.Services]System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs::get_SignInRequestMessage()
0xd224  ldloc.s  9
0xd226  callvirt instance void [System.IdentityModel.Services]System.IdentityModel.Services.WSFederationMessage::set_Context(string)
0xd22b  ldarg.1
0xd22c  callvirt instance class [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage [System.IdentityModel.Services]System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs::get_SignInRequestMessage()
0xd231  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_FederationProvider()
0xd236  ldstr    aPassiveendpoin// "PassiveEndpoint"
0xd23b  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::GetFederationProviderProperty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, string)
0xd240  isinst   [mscorlib]System.String
0xd245  newobj   instance void [System]System.Uri::.ctor(string)
0xd24a  callvirt instance void [System.IdentityModel.Services]System.IdentityModel.Services.FederationMessage::set_BaseUri(class [System]System.Uri)
0xd24f  ret
```
