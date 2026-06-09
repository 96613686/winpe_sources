# Microsoft.Xrm.Sdk.Client.DiscoveryServiceConfiguration::AuthenticateDevice

- ea: `0x18c20`
- end: `0x18c2b`
- name: `Microsoft.Xrm.Sdk.Client.DiscoveryServiceConfiguration::AuthenticateDevice`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x18c20`: `Authentication to MSA services is not supported.`

## pseudocode

```c

```

## disassembly

```asm
0x18c20  ldstr    aAuthentication_3// "Authentication to MSA services is not s"...
0x18c25  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x18c2a  throw
```
