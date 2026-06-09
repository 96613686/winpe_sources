# Microsoft.Crm.Application.Controls.D365CertManager::GetSecretManagementClient

- ea: `0xa2830`
- end: `0xa2948`
- name: `Microsoft.Crm.Application.Controls.D365CertManager::GetSecretManagementClient`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xa2980`

## callees

- `0xa2830`

## string_xrefs

- `0xa2878`: `KeyVault URL not configured`
- `0xa288c`: `S2S PrincipalId not configured`
- `0xa2897`: `S2STokenIssuer`
- `0xa28c1`: `O365 waffle keyvault settings - uri = {0} appid =  {1} cert = {2} has key = {3}`
- `0xa2927`: `O365 waffle certificate read failure - cannot create Keyvault client: {0}`

## pseudocode

```c

```

## disassembly

```asm
0xa2830  ldnull
0xa2831  stloc.0
0xa2832  ldsfld   object Microsoft.Crm.Application.Controls.D365CertManager::_vaultLock
0xa2837  stloc.1
0xa2838  ldc.i4.0
0xa2839  stloc.2
0xa283a  ldloc.1
0xa283b  ldloca.s 2
0xa283d  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xa2842  ldloc.0
0xa2843  brfalse.s loc_A284D
0xa2845  ldloc.0
0xa2846  stloc.s  6
0xa2848  leave    loc_A2945
0xa284d  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0xa2852  ldstr    aGeokeyvaulturl// "GeoKeyVaultUrl"
0xa2857  ldc.i4.1
0xa2858  callvirt T0x2B00000B
0xa285d  stloc.3
0xa285e  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0xa2863  ldstr    aS2scrmprincipa// "S2SCrmPrincipalId"
0xa2868  ldc.i4.1
0xa2869  callvirt T0x2B00000B
0xa286e  stloc.s  4
0xa2870  ldloc.3
0xa2871  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa2876  brfalse.s loc_A2883
0xa2878  ldstr    aKeyvaultUrlNot// "KeyVault URL not configured"
0xa287d  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0xa2882  throw
0xa2883  ldloc.s  4
0xa2885  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa288a  brfalse.s loc_A2897
0xa288c  ldstr    aS2sPrincipalid// "S2S PrincipalId not configured"
0xa2891  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0xa2896  throw
0xa2897  ldstr    aS2stokenissuer// "S2STokenIssuer"
0xa289c  call     class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.Claims.CertificateUtility::GetCertificate(string)
0xa28a1  stloc.s  5
0xa28a3  ldloc.s  5
0xa28a5  brtrue.s loc_A28B2
0xa28a7  ldstr    aS2sIssuerCerti// "S2S Issuer certificate could not be loa"...
0xa28ac  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0xa28b1  throw
0xa28b2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa28b7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xa28bc  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0xa28c1  ldstr    aO365WaffleKeyv// "O365 waffle keyvault settings - uri = {"...
0xa28c6  ldc.i4.4
0xa28c7  newarr   [mscorlib]System.Object
0xa28cc  dup
0xa28cd  ldc.i4.0
0xa28ce  ldloc.3
0xa28cf  stelem.ref
0xa28d0  dup
0xa28d1  ldc.i4.1
0xa28d2  ldloc.s  4
0xa28d4  stelem.ref
0xa28d5  dup
0xa28d6  ldc.i4.2
0xa28d7  ldloc.s  5
0xa28d9  callvirt instance string [mscorlib]System.Security.Cryptography.X509Certificates.X509Certificate::get_Subject()
0xa28de  stelem.ref
0xa28df  dup
0xa28e0  ldc.i4.3
0xa28e1  ldloc.s  5
0xa28e3  callvirt instance bool [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_HasPrivateKey()
0xa28e8  box      [mscorlib]System.Boolean
0xa28ed  stelem.ref
0xa28ee  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa28f3  ldloc.3
0xa28f4  newobj   instance void [System]System.Uri::.ctor(string)
0xa28f9  ldloc.s  4
0xa28fb  ldloc.s  5
0xa28fd  newobj   instance void [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.ClientAssertionCertificate::.ctor(string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0xa2902  newobj   instance void [SecretManagement]SecretManagementShared.SecretManagementClientReader::.ctor(class [System]System.Uri, class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.ClientAssertionCertificate)
0xa2907  stloc.0
0xa2908  leave.s  loc_A2914
0xa290a  ldloc.2
0xa290b  brfalse.s loc_A2913
0xa290d  ldloc.1
0xa290e  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xa2913  endfinally
0xa2914  leave.s  loc_A2943
0xa2916  stloc.s  7
0xa2918  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa291d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xa2922  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0xa2927  ldstr    aO365WaffleCert_0// "O365 waffle certificate read failure - "...
0xa292c  ldc.i4.1
0xa292d  newarr   [mscorlib]System.Object
0xa2932  dup
0xa2933  ldc.i4.0
0xa2934  ldloc.s  7
0xa2936  callvirt instance string [mscorlib]System.Exception::get_Message()
0xa293b  stelem.ref
0xa293c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa2941  leave.s  loc_A2943
0xa2943  ldloc.0
0xa2944  ret
0xa2945  ldloc.s  6
0xa2947  ret
```
