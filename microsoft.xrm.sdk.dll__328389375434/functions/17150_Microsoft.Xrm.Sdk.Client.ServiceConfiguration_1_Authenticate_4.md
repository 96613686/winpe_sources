# Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::Authenticate_4

- ea: `0x17150`
- end: `0x17171`
- name: `Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::Authenticate_4`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7ca0`

## string_xrefs

- `0x17166`: `Authentication to MSA services is not supported.`
- `0x1715c`: `deviceTokenResponse`

## pseudocode

```c

```

## disassembly

```asm
0x17150  ldarg.1
0x17151  ldstr    aClientcredenti_0// "clientCredentials"
0x17156  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x1715b  ldarg.2
0x1715c  ldstr    aDevicetokenres// "deviceTokenResponse"
0x17161  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x17166  ldstr    aAuthentication_3// "Authentication to MSA services is not s"...
0x1716b  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x17170  throw
```
