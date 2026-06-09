# Microsoft.Xrm.Sdk.Client.AuthenticationHelpers::ShouldAuthenticateWithLiveId_1

- ea: `0x15500`
- end: `0x15518`
- name: `Microsoft.Xrm.Sdk.Client.AuthenticationHelpers::ShouldAuthenticateWithLiveId_1`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7ca0`

## string_xrefs

- `0x15501`: `serviceConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x15500  ldarg.0
0x15501  ldstr    aServiceconfigu// "serviceConfiguration"
0x15506  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x1550b  ldarg.1
0x1550c  ldstr    aClientcredenti_0// "clientCredentials"
0x15511  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x15516  ldc.i4.0
0x15517  ret
```
