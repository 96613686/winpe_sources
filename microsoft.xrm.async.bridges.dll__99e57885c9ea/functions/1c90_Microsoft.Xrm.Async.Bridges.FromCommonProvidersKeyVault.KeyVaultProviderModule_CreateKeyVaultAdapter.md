# Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultProviderModule::CreateKeyVaultAdapter

- ea: `0x1c90`
- end: `0x1ce1`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultProviderModule::CreateKeyVaultAdapter`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1030`
- `0x14d0`
- `0x19c0`
- `0x19e0`
- `0x1a00`
- `0x1c90`
- `0x3790`
- `0x37e0`

## pseudocode

```c

```

## disassembly

```asm
0x1c90  ldarg.1
0x1c91  call     T0x2B000047
0x1c96  ldarg.1
0x1c97  call     T0x2B000048
0x1c9c  stloc.0
0x1c9d  callvirt instance valuetype Microsoft.Xrm.Async.Bridges.FromCommon.EnvironmentKind Microsoft.Xrm.Async.Bridges.FromCommon.EnvironmentConfig::get_Kind()
0x1ca2  brtrue.s loc_1CCF
0x1ca4  ldarg.1
0x1ca5  call     T0x2B000049
0x1caa  ldloc.0
0x1cab  callvirt instance string Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultConfig::get_CertificateThumbprint()
0x1cb0  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 Microsoft.Xrm.Async.Bridges.FromCommon.ICertificateLookup::FindByThumbprint(string thumbprint)
0x1cb5  stloc.1
0x1cb6  ldarg.1
0x1cb7  call     T0x2B00004A
0x1cbc  ldloc.0
0x1cbd  callvirt instance string Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultConfig::get_VaultUrl()
0x1cc2  ldloc.0
0x1cc3  callvirt instance string Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultConfig::get_AadClientId()
0x1cc8  ldloc.1
0x1cc9  callvirt instance class Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultAdapter CertificateFactory::Invoke(string vaultUrl, string aadClientId, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 certificate)
0x1cce  ret
0x1ccf  ldarg.1
0x1cd0  call     T0x2B00004B
0x1cd5  ldloc.0
0x1cd6  callvirt instance string Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultConfig::get_VaultUrl()
0x1cdb  callvirt instance class Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultAdapter ManagedServiceIdentityFactory::Invoke(string vaultUrl)
0x1ce0  ret
```
