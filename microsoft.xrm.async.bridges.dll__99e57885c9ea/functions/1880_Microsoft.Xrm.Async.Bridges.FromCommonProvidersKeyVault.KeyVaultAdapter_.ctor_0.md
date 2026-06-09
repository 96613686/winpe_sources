# Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultAdapter::.ctor_0

- ea: `0x1880`
- end: `0x18c7`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultAdapter::.ctor_0`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xab0`

## string_xrefs

- `0x189f`: `https://login.microsoftonline.com/`

## pseudocode

```c

```

## disassembly

```asm
0x1880  ldarg.0
0x1881  call     instance void [mscorlib]System.Object::.ctor()
0x1886  ldarg.1
0x1887  ldstr    aVaulturl// "vaultUrl"
0x188c  call     T0x2B000024
0x1891  call     class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string> Microsoft.Xrm.Async.Bridges.FromCommon.Args::IsNotNullOrEmpty(class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string> arg)
0x1896  pop
0x1897  ldarg.0
0x1898  ldarg.1
0x1899  stfld    string Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultAdapter::vaultUrl
0x189e  ldnull
0x189f  ldstr    aHttpsLoginMicr// "https://login.microsoftonline.com/"
0x18a4  newobj   instance void [Microsoft.Azure.Services.AppAuthentication]Microsoft.Azure.Services.AppAuthentication.AzureServiceTokenProvider::.ctor(string, string)
0x18a9  stloc.0
0x18aa  ldarg.0
0x18ab  ldloc.0
0x18ac  callvirt instance class [Microsoft.Azure.Services.AppAuthentication]Microsoft.Azure.Services.AppAuthentication.AzureServiceTokenProvider/TokenCallback [Microsoft.Azure.Services.AppAuthentication]Microsoft.Azure.Services.AppAuthentication.AzureServiceTokenProvider::get_KeyVaultTokenCallback()
0x18b1  ldftn    instance class [mscorlib]System.Threading.Tasks.Task`1<string> [Microsoft.Azure.Services.AppAuthentication]Microsoft.Azure.Services.AppAuthentication.AzureServiceTokenProvider/TokenCallback::Invoke(string, string, string)
0x18b7  newobj   instance void [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.KeyVaultClient/AuthenticationCallback::.ctor(object, native int)
0x18bc  newobj   instance void [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.KeyVaultClient::.ctor(class [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.KeyVaultClient/AuthenticationCallback)
0x18c1  stfld    class [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.KeyVaultClient Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultAdapter::keyVaultClient
0x18c6  ret
```
