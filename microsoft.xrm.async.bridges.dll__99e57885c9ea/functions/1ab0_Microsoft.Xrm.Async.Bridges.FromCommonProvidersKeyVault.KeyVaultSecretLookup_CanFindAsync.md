# Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup::CanFindAsync

- ea: `0x1ab0`
- end: `0x1ad7`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup::CanFindAsync`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x3bc0`

## string_xrefs

- `0x1ab1`: `secretUri`

## pseudocode

```c

```

## disassembly

```asm
0x1ab0  ldarg.1
0x1ab1  ldstr    aSecreturi// "secretUri"
0x1ab6  call     T0x2B00000F
0x1abb  call     T0x2B000010
0x1ac0  pop
0x1ac1  ldsfld   class [System]System.Text.RegularExpressions.Regex Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup::SecretUriExpression
0x1ac6  ldarg.1
0x1ac7  callvirt instance string [mscorlib]System.Object::ToString()
0x1acc  callvirt instance bool [System]System.Text.RegularExpressions.Regex::IsMatch(string)
0x1ad1  call     T0x2B00002D
0x1ad6  ret
```
