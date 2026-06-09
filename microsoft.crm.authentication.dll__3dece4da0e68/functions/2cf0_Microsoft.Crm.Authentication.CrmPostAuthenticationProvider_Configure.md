# Microsoft.Crm.Authentication.CrmPostAuthenticationProvider::Configure

- ea: `0x2cf0`
- end: `0x2d08`
- name: `Microsoft.Crm.Authentication.CrmPostAuthenticationProvider::Configure`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4610`
- `0x4650`

## string_xrefs

- `0x2cfd`: `CrmPostAuthenticationAttemptsInTheLastMinute`

## pseudocode

```c

```

## disassembly

```asm
0x2cf0  ldarg.0
0x2cf1  ldarg.1
0x2cf2  call     instance void Microsoft.Crm.Authentication.BaseAuthenticationProvider::Configure(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> configuration)
0x2cf7  ldarg.0
0x2cf8  ldstr    aCrmpostauthent_1// "CrmPostAuthenticationFailuresInTheLastM"...
0x2cfd  ldstr    aCrmpostauthent_2// "CrmPostAuthenticationAttemptsInTheLastM"...
0x2d02  call     instance void Microsoft.Crm.Authentication.BaseAuthenticationProvider::CreateAuthenticationFailureCounter(string failuresName, string attemptsName)
0x2d07  ret
```
