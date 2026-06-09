# Microsoft.Xrm.Sdk.Client.AuthenticationHelpers::ShouldAuthenticateWithLiveId_0

- ea: `0x154e0`
- end: `0x154f8`
- name: `Microsoft.Xrm.Sdk.Client.AuthenticationHelpers::ShouldAuthenticateWithLiveId_0`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7ca0`

## string_xrefs

- `0x154e1`: `serviceConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x154e0  ldarg.0
0x154e1  ldstr    aServiceconfigu// "serviceConfiguration"
0x154e6  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x154eb  ldarg.1
0x154ec  ldstr    aClientcredenti_0// "clientCredentials"
0x154f1  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x154f6  ldc.i4.0
0x154f7  ret
```
