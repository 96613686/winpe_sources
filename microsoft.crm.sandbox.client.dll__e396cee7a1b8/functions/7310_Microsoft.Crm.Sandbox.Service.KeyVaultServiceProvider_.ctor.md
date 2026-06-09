# Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::.ctor

- ea: `0x7310`
- end: `0x7342`
- name: `Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::.ctor`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x3910`

## pseudocode

```c

```

## disassembly

```asm
0x7310  ldarg.0
0x7311  ldc.i4.3
0x7312  newarr   [mscorlib]System.String
0x7317  dup
0x7318  ldc.i4.0
0x7319  ldstr    aVaultUsgovclou// "vault.usgovcloudapi.net"
0x731e  stelem.ref
0x731f  dup
0x7320  ldc.i4.1
0x7321  ldstr    aVaultAzureNet// "vault.azure.net"
0x7326  stelem.ref
0x7327  dup
0x7328  ldc.i4.2
0x7329  ldstr    aVaultAzureCn// "vault.azure.cn"
0x732e  stelem.ref
0x732f  stfld    string[] Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::ValidKeyVaultSuffix
0x7334  ldarg.0
0x7335  call     instance void [mscorlib]System.Object::.ctor()
0x733a  ldarg.0
0x733b  ldarg.1
0x733c  stfld    class Microsoft.Crm.Sandbox.Service.IKeyVaultClientFactory Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::keyVaultClientFactory
0x7341  ret
```
