# Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultAdapter::GetSecretAsync

- ea: `0x18d0`
- end: `0x18f0`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultAdapter::GetSecretAsync`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xab0`
- `0x18f0`
- `0x1990`

## pseudocode

```c

```

## disassembly

```asm
0x18d0  ldarg.1
0x18d1  ldstr    aSecretname// "secretName"
0x18d6  call     T0x2B000024
0x18db  call     class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string> Microsoft.Xrm.Async.Bridges.FromCommon.Args::IsNotNullOrEmpty(class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string> arg)
0x18e0  pop
0x18e1  ldarg.0
0x18e2  ldarg.0
0x18e3  ldarg.1
0x18e4  call     instance class [System]System.Uri Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultAdapter::GetVaultUrl(string secretName)
0x18e9  ldarg.2
0x18ea  call     instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultAdapter::GetSecretAsync(class [System]System.Uri secretUri, [opt] valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x18ef  ret
```
