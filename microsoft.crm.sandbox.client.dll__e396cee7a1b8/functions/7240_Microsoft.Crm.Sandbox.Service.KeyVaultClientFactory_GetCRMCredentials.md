# Microsoft.Crm.Sandbox.Service.KeyVaultClientFactory::GetCRMCredentials

- ea: `0x7240`
- end: `0x7297`
- name: `Microsoft.Crm.Sandbox.Service.KeyVaultClientFactory::GetCRMCredentials`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x72b0`

## callees

- `0x7240`

## string_xrefs

- `0x7250`: `S2STokenIssuer`
- `0x7263`: `App Id for {0} not defined in config db`

## pseudocode

```c

```

## disassembly

```asm
0x7240  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x7245  ldstr    aS2scrmprincipa// "S2SCrmPrincipalId"
0x724a  ldc.i4.0
0x724b  callvirt T0x2B000016
0x7250  ldstr    aS2stokenissuer// "S2STokenIssuer"
0x7255  call     class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.Claims.CertificateUtility::GetCertificate(string)
0x725a  stloc.0
0x725b  dup
0x725c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7261  brfalse.s loc_727D
0x7263  ldstr    aAppIdFor0NotDe// "App Id for {0} not defined in config db"
0x7268  ldstr    aS2scrmprincipa// "S2SCrmPrincipalId"
0x726d  call     string [mscorlib]System.String::Format(string, object)
0x7272  ldc.i4   0x80091008
0x7277  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.CrmExceptions.CrmKeyVaultException::.ctor(string, int32)
0x727c  throw
0x727d  ldloc.0
0x727e  brtrue.s loc_7290
0x7280  ldstr    aCouldNotFindS2// "Could not find S2S cert"
0x7285  ldc.i4   0x80091008
0x728a  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.CrmExceptions.CrmKeyVaultException::.ctor(string, int32)
0x728f  throw
0x7290  ldloc.0
0x7291  newobj   instance void [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.ClientAssertionCertificate::.ctor(string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x7296  ret
```
