# Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultAdapter::.ctor

- ea: `0x1810`
- end: `0x1875`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultAdapter::.ctor`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xab0`

## pseudocode

```c

```

## disassembly

```asm
0x1810  ldarg.0
0x1811  call     instance void [mscorlib]System.Object::.ctor()
0x1816  ldarg.1
0x1817  ldstr    aVaulturl// "vaultUrl"
0x181c  call     T0x2B000024
0x1821  call     class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string> Microsoft.Xrm.Async.Bridges.FromCommon.Args::IsNotNullOrEmpty(class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string> arg)
0x1826  pop
0x1827  ldarg.2
0x1828  ldstr    aAadclientid// "aadClientId"
0x182d  call     T0x2B000024
0x1832  call     class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string> Microsoft.Xrm.Async.Bridges.FromCommon.Args::IsNotNullOrEmpty(class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string> arg)
0x1837  pop
0x1838  ldarg.3
0x1839  ldstr    aCertificate// "certificate"
0x183e  call     T0x2B000028
0x1843  call     T0x2B000029
0x1848  pop
0x1849  ldarg.0
0x184a  ldarg.1
0x184b  stfld    string Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultAdapter::vaultUrl
0x1850  ldarg.0
0x1851  ldarg.2
0x1852  ldarg.3
0x1853  newobj   instance void [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.ClientAssertionCertificate::.ctor(string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x1858  stfld    class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.ClientAssertionCertificate Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultAdapter::assertionCertificate
0x185d  ldarg.0
0x185e  ldarg.0
0x185f  ldftn    instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultAdapter::GetAccessToken(string authority, string resource, string scope)
0x1865  newobj   instance void [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.KeyVaultClient/AuthenticationCallback::.ctor(object, native int)
0x186a  newobj   instance void [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.KeyVaultClient::.ctor(class [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.KeyVaultClient/AuthenticationCallback)
0x186f  stfld    class [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.KeyVaultClient Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultAdapter::keyVaultClient
0x1874  ret
```
