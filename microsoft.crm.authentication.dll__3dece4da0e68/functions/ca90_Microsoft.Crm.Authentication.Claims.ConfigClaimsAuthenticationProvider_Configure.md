# Microsoft.Crm.Authentication.Claims.ConfigClaimsAuthenticationProvider::Configure

- ea: `0xca90`
- end: `0xcaab`
- name: `Microsoft.Crm.Authentication.Claims.ConfigClaimsAuthenticationProvider::Configure`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4610`
- `0x4650`
- `0xca90`

## string_xrefs

- `0xcaa0`: `ClaimsAuthenticationAttemptsInTheLastMinute`

## pseudocode

```c

```

## disassembly

```asm
0xca90  ldarg.1
0xca91  brfalse.s loc_CA9A
0xca93  ldarg.0
0xca94  ldarg.1
0xca95  call     instance void Microsoft.Crm.Authentication.BaseAuthenticationProvider::Configure(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> configuration)
0xca9a  ldarg.0
0xca9b  ldstr    aClaimsauthenti// "ClaimsAuthenticationFailuresInTheLastMi"...
0xcaa0  ldstr    aClaimsauthenti_0// "ClaimsAuthenticationAttemptsInTheLastMi"...
0xcaa5  call     instance void Microsoft.Crm.Authentication.BaseAuthenticationProvider::CreateAuthenticationFailureCounter(string failuresName, string attemptsName)
0xcaaa  ret
```
