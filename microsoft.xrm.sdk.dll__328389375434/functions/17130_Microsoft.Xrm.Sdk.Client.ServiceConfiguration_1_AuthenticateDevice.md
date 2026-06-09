# Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::AuthenticateDevice

- ea: `0x17130`
- end: `0x17146`
- name: `Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::AuthenticateDevice`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7ca0`

## string_xrefs

- `0x1713b`: `Authentication to MSA services is not supported.`

## pseudocode

```c

```

## disassembly

```asm
0x17130  ldarg.1
0x17131  ldstr    aClientcredenti_0// "clientCredentials"
0x17136  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x1713b  ldstr    aAuthentication_3// "Authentication to MSA services is not s"...
0x17140  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x17145  throw
```
