# Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultAdapter::GetVaultUrl

- ea: `0x1990`
- end: `0x19a7`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultAdapter::GetVaultUrl`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18d0`

## pseudocode

```c

```

## disassembly

```asm
0x1990  ldstr    a0Secrets1// "{0}/secrets/{1}"
0x1995  ldarg.0
0x1996  ldfld    string Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultAdapter::vaultUrl
0x199b  ldarg.1
0x199c  call     string [mscorlib]System.String::Format(string, object, object)
0x19a1  newobj   instance void [System]System.Uri::.ctor(string)
0x19a6  ret
```
