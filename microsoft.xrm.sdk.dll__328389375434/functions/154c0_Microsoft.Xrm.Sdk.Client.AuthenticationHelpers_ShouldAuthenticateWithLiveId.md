# Microsoft.Xrm.Sdk.Client.AuthenticationHelpers::ShouldAuthenticateWithLiveId

- ea: `0x154c0`
- end: `0x154d8`
- name: `Microsoft.Xrm.Sdk.Client.AuthenticationHelpers::ShouldAuthenticateWithLiveId`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x7ca0`

## string_xrefs

- `0x154c1`: `serviceManagement`

## pseudocode

```c

```

## disassembly

```asm
0x154c0  ldarg.0
0x154c1  ldstr    aServicemanagem// "serviceManagement"
0x154c6  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x154cb  ldarg.1
0x154cc  ldstr    aClientcredenti_0// "clientCredentials"
0x154d1  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x154d6  ldc.i4.0
0x154d7  ret
```
