# Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::Authenticate_5

- ea: `0x17180`
- end: `0x171ac`
- name: `Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::Authenticate_5`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7ca0`
- `0x7cb0`

## string_xrefs

- `0x171a1`: `Authentication to MSA services is not supported.`
- `0x1718c`: `deviceTokenResponse`

## pseudocode

```c

```

## disassembly

```asm
0x17180  ldarg.1
0x17181  ldstr    aClientcredenti_0// "clientCredentials"
0x17186  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x1718b  ldarg.2
0x1718c  ldstr    aDevicetokenres// "deviceTokenResponse"
0x17191  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x17196  ldarg.3
0x17197  ldstr    aKeytype// "keyType"
0x1719c  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNullOrEmpty(string parameter, string name)
0x171a1  ldstr    aAuthentication_3// "Authentication to MSA services is not s"...
0x171a6  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x171ab  throw
```
