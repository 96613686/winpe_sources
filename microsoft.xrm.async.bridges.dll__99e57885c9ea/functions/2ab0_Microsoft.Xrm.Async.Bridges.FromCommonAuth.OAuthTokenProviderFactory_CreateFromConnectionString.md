# Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::CreateFromConnectionString

- ea: `0x2ab0`
- end: `0x2b68`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::CreateFromConnectionString`
- size: `184`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x4310`
- `0x4400`

## callees

- `0x14d0`
- `0x2130`
- `0x2150`
- `0x2170`
- `0x2190`
- `0x21b0`
- `0x22f0`
- `0x28d0`
- `0x2a90`
- `0x2ab0`
- `0x2b70`
- `0x2bb0`

## pseudocode

```c

```

## disassembly

```asm
0x2ab0  ldarg.1
0x2ab1  brtrue.s loc_2AD4
0x2ab3  ldstr    aTheConnectionS_0// "The connection string at '{0}' could no"...
0x2ab8  ldarg.2
0x2ab9  ldarg.0
0x2aba  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookup Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::secretLookup
0x2abf  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2ac4  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x2ac9  call     string [mscorlib]System.String::Format(string, object, object)
0x2ace  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string)
0x2ad3  throw
0x2ad4  ldarg.0
0x2ad5  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IConnectionStringConfigParser Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::connectionStringConfigParser
0x2ada  ldarg.1
0x2adb  callvirt T0x2B00006F
0x2ae0  stloc.0
0x2ae1  ldarg.0
0x2ae2  ldarg.3
0x2ae3  ldloc.0
0x2ae4  call     instance void Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::ReplaceAudienceUri(class [System]System.Uri audienceUri, class Microsoft.Xrm.Async.Bridges.FromCommonAuth.AadAuthConnectionString aadAuthConnectionString)
0x2ae9  ldarg.0
0x2aea  ldloc.0
0x2aeb  ldarg.2
0x2aec  call     instance void Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::ValidateConnectionString(class Microsoft.Xrm.Async.Bridges.FromCommonAuth.AadAuthConnectionString connectionString, string connectionStringIdentifier)
0x2af1  ldloc.0
0x2af2  callvirt instance string Microsoft.Xrm.Async.Bridges.FromCommonAuth.AadAuthConnectionString::get_ClientId()
0x2af7  ldloc.0
0x2af8  callvirt instance string Microsoft.Xrm.Async.Bridges.FromCommonAuth.AadAuthConnectionString::get_AuthorityUrl()
0x2afd  ldloc.0
0x2afe  callvirt instance string Microsoft.Xrm.Async.Bridges.FromCommonAuth.AadAuthConnectionString::get_AppUri()
0x2b03  newobj   instance void Microsoft.Xrm.Async.Bridges.FromCommonAuth.ApplicationInfo::.ctor(string clientId, string authorityUrl, string appUri)
0x2b08  stloc.1
0x2b09  ldloc.0
0x2b0a  callvirt instance string Microsoft.Xrm.Async.Bridges.FromCommonAuth.AadAuthConnectionString::get_CertThumbprint()
0x2b0f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2b14  brtrue.s loc_2B31
0x2b16  ldarg.0
0x2b17  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ICertificateLookup Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::certificateLookup
0x2b1c  ldloc.0
0x2b1d  callvirt instance string Microsoft.Xrm.Async.Bridges.FromCommonAuth.AadAuthConnectionString::get_CertThumbprint()
0x2b22  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 Microsoft.Xrm.Async.Bridges.FromCommon.ICertificateLookup::FindByThumbprint(string thumbprint)
0x2b27  stloc.2
0x2b28  ldarg.0
0x2b29  ldloc.1
0x2b2a  ldloc.2
0x2b2b  callvirt instance class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::CreateCertificateOAuthTokenProvider(class Microsoft.Xrm.Async.Bridges.FromCommonAuth.ApplicationInfo applicationInfo, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 cert)
0x2b30  ret
0x2b31  ldloc.0
0x2b32  callvirt instance string Microsoft.Xrm.Async.Bridges.FromCommonAuth.AadAuthConnectionString::get_AppKey()
0x2b37  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2b3c  brtrue.s loc_2B57
0x2b3e  ldarg.0
0x2b3f  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProviderFactory Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::authProviderFactory
0x2b44  ldloc.1
0x2b45  ldloc.0
0x2b46  callvirt instance string Microsoft.Xrm.Async.Bridges.FromCommonAuth.AadAuthConnectionString::get_AppKey()
0x2b4b  ldarg.0
0x2b4c  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthenticationContextFactory Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::contextFactory
0x2b51  callvirt instance class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProviderFactory::Create(class Microsoft.Xrm.Async.Bridges.FromCommonAuth.ApplicationInfo applicationInfo, string appKey, class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthenticationContextFactory contextFactory)
0x2b56  ret
0x2b57  ldstr    aTheConnectionS_1// "The connection string at '{0}' has neit"...
0x2b5c  ldarg.2
0x2b5d  call     string [mscorlib]System.String::Format(string, object)
0x2b62  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string)
0x2b67  throw
```
