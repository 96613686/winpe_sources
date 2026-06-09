# <>c__DisplayClass9_0::<GetIdentityConfiguration>b__1

- ea: `0x149c0`
- end: `0x14b30`
- name: `<>c__DisplayClass9_0::<GetIdentityConfiguration>b__1`
- size: `368`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config`

## callees

- `0x3cc0`
- `0x3ce0`
- `0xa2a0`
- `0xa2e0`
- `0xa470`
- `0xa600`
- `0xa650`
- `0xa6c0`
- `0xa740`
- `0xa870`
- `0xb010`
- `0xfca0`
- `0x10bc0`
- `0x10ce0`
- `0x149c0`

## pseudocode

```c

```

## disassembly

```asm
0x149c0  call     bool [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_ClaimsEnabled()
0x149c5  brtrue.s loc_149C9
0x149c7  ldnull
0x149c8  ret
0x149c9  ldsfld   valuetype [mscorlib]System.TimeSpan [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::DefaultMaxClockSkew
0x149ce  stloc.0
0x149cf  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_FederationProvider()
0x149d4  ldstr    aMaxclockskew// "MaxClockSkew"
0x149d9  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::GetFederationProviderProperty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, string)
0x149de  stloc.1
0x149df  ldloc.1
0x149e0  brfalse.s loc_149E9
0x149e2  ldloc.1
0x149e3  unbox.any [mscorlib]System.TimeSpan
0x149e8  stloc.0
0x149e9  call     void Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::RegisterNotificationHandlers()
0x149ee  ldc.i4.0
0x149ef  newobj   instance void [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::.ctor(bool)
0x149f4  stloc.2
0x149f5  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x149fa  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x149ff  ldc.i4.2
0x14a00  beq.s    loc_14A3A
0x14a02  ldtoken  [System.IdentityModel]System.ServiceModel.Security.X509CertificateValidationMode
0x14a07  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14a0c  ldstr    aTrustedissuerc// "TrustedIssuerCertificateValidation"
0x14a11  ldstr    aNone// "None"
0x14a16  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x14a1b  castclass [mscorlib]System.String
0x14a20  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x14a25  unbox.any [System.IdentityModel]System.ServiceModel.Security.X509CertificateValidationMode
0x14a2a  stloc.s  7
0x14a2c  ldloc.2
0x14a2d  ldloc.s  7
0x14a2f  callvirt instance void [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::set_CertificateValidationMode(valuetype [System.IdentityModel]System.ServiceModel.Security.X509CertificateValidationMode)
0x14a34  ldloc.2
0x14a35  callvirt instance void [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::Initialize()
0x14a3a  ldloc.2
0x14a3b  ldloc.0
0x14a3c  callvirt instance void [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::set_MaxClockSkew(valuetype [mscorlib]System.TimeSpan)
0x14a41  ldloc.2
0x14a42  newobj   instance void Microsoft.Crm.Authentication.Claims.TrustedIssuerRegistry::.ctor()
0x14a47  callvirt instance void [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::set_IssuerNameRegistry(class [System.IdentityModel]System.IdentityModel.Tokens.IssuerNameRegistry)
0x14a4c  call     class [System]System.Security.Cryptography.X509Certificates.X509Certificate2Collection Microsoft.Crm.Authentication.Claims.CertificateUtility::TryGetSecondaryDecryptionCertificates()
0x14a51  stloc.3
0x14a52  call     class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::get_DecryptionCertificate()
0x14a57  stloc.s  4
0x14a59  ldloc.s  4
0x14a5b  brfalse.s loc_14A6E
0x14a5d  ldloc.2
0x14a5e  ldloc.s  4
0x14a60  callvirt instance void [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::set_ServiceCertificate(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x14a65  ldloc.3
0x14a66  ldloc.s  4
0x14a68  callvirt instance int32 [System]System.Security.Cryptography.X509Certificates.X509Certificate2Collection::Add(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x14a6d  pop
0x14a6e  ldloc.3
0x14a6f  call     class [System.IdentityModel]System.IdentityModel.Selectors.SecurityTokenResolver Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::CreateAggregateTokenResolver(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2Collection certificates)
0x14a74  stloc.s  5
0x14a76  ldloc.2
0x14a77  ldloc.s  5
0x14a79  callvirt instance void [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::set_ServiceTokenResolver(class [System.IdentityModel]System.IdentityModel.Selectors.SecurityTokenResolver)
0x14a7e  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x14a83  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x14a88  ldc.i4.2
0x14a89  bne.un.s loc_14AAE
0x14a8b  ldloc.2
0x14a8c  ldc.i4.2
0x14a8d  newarr   [System.IdentityModel]System.IdentityModel.Selectors.SecurityTokenResolver
0x14a92  dup
0x14a93  ldc.i4.0
0x14a94  newobj   instance void Microsoft.Crm.Authentication.Claims.LiveIdIssuerTokenResolver::.ctor()
0x14a99  stelem.ref
0x14a9a  dup
0x14a9b  ldc.i4.1
0x14a9c  ldsfld   class [System.IdentityModel]System.IdentityModel.Selectors.SecurityTokenResolver [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration::DefaultIssuerTokenResolver
0x14aa1  stelem.ref
0x14aa2  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.AggregateTokenResolver::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.IdentityModel]System.IdentityModel.Selectors.SecurityTokenResolver>)
0x14aa7  callvirt instance void [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::set_IssuerTokenResolver(class [System.IdentityModel]System.IdentityModel.Selectors.SecurityTokenResolver)
0x14aac  br.s     loc_14AB9
0x14aae  ldloc.2
0x14aaf  newobj   instance void Microsoft.Crm.Authentication.Claims.CrmIssuerTokenResolver::.ctor()
0x14ab4  callvirt instance void [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::set_IssuerTokenResolver(class [System.IdentityModel]System.IdentityModel.Selectors.SecurityTokenResolver)
0x14ab9  ldarg.0
0x14aba  ldfld    class [mscorlib]System.Text.StringBuilder <>c__DisplayClass9_0::messageBuilder
0x14abf  call     void Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::LogFederationProviders(class [mscorlib]System.Text.StringBuilder messageBuilder)
0x14ac4  call     class Microsoft.Crm.Authentication.Claims.ITokenAudienceProvider Microsoft.Crm.Authentication.Claims.TokenAudienceProvider::get_Instance()
0x14ac9  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System]System.Uri> Microsoft.Crm.Authentication.Claims.ITokenAudienceProvider::get_DefaultAudiences()
0x14ace  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System]System.Uri>::GetEnumerator()
0x14ad3  stloc.s  8
0x14ad5  br.s     loc_14AF2
0x14ad7  ldloc.s  8
0x14ad9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System]System.Uri>::get_Current()
0x14ade  stloc.s  9
0x14ae0  ldloc.2
0x14ae1  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.AudienceRestriction [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::get_AudienceRestriction()
0x14ae6  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System]System.Uri> [System.IdentityModel]System.IdentityModel.Tokens.AudienceRestriction::get_AllowedAudienceUris()
0x14aeb  ldloc.s  9
0x14aed  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System]System.Uri>::Add(var<u1>)
0x14af2  ldloc.s  8
0x14af4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x14af9  brtrue.s loc_14AD7
0x14afb  leave.s  loc_14B09
0x14afd  ldloc.s  8
0x14aff  brfalse.s loc_14B08
0x14b01  ldloc.s  8
0x14b03  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14b08  endfinally
0x14b09  newobj   instance void Microsoft.Crm.Authentication.AuthorizationManagerFactory::.ctor()
0x14b0e  stloc.s  6
0x14b10  ldloc.2
0x14b11  ldloc.s  6
0x14b13  callvirt instance class [System.IdentityModel]System.Security.Claims.ClaimsAuthorizationManager Microsoft.Crm.Authentication.AuthorizationManagerFactory::CreateInstance()
0x14b18  callvirt instance void [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::set_ClaimsAuthorizationManager(class [System.IdentityModel]System.Security.Claims.ClaimsAuthorizationManager)
0x14b1d  ldloc.2
0x14b1e  call     void Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::UpdateTokenHandlers(class [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration identityConfiguration)
0x14b23  ldarg.0
0x14b24  ldfld    class [mscorlib]System.Text.StringBuilder <>c__DisplayClass9_0::messageBuilder
0x14b29  call     void Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::WriteSuccessfulInitializeToEventLog(class [mscorlib]System.Text.StringBuilder eventLogInfoStringBuilder)
0x14b2e  ldloc.2
0x14b2f  ret
```
