# Microsoft.Crm.Authentication.ConfigDBWindowsAuthenticationProvider::Configure

- ea: `0x66b0`
- end: `0x66c8`
- name: `Microsoft.Crm.Authentication.ConfigDBWindowsAuthenticationProvider::Configure`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4610`
- `0x4650`

## string_xrefs

- `0x66b8`: `ConfigDBWindowsAuthenticationFailuresInTheLastMinute`
- `0x66bd`: `ConfigDBWindowsAuthenticationAttemptsInTheLastMinute`

## pseudocode

```c

```

## disassembly

```asm
0x66b0  ldarg.0
0x66b1  ldarg.1
0x66b2  call     instance void Microsoft.Crm.Authentication.BaseAuthenticationProvider::Configure(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> configuration)
0x66b7  ldarg.0
0x66b8  ldstr    aConfigdbwindow_4// "ConfigDBWindowsAuthenticationFailuresIn"...
0x66bd  ldstr    aConfigdbwindow_5// "ConfigDBWindowsAuthenticationAttemptsIn"...
0x66c2  call     instance void Microsoft.Crm.Authentication.BaseAuthenticationProvider::CreateAuthenticationFailureCounter(string failuresName, string attemptsName)
0x66c7  ret
```
