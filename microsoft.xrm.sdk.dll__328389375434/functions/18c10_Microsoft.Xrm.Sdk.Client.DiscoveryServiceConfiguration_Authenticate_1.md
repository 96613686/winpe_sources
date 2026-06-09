# Microsoft.Xrm.Sdk.Client.DiscoveryServiceConfiguration::Authenticate_1

- ea: `0x18c10`
- end: `0x18c1b`
- name: `Microsoft.Xrm.Sdk.Client.DiscoveryServiceConfiguration::Authenticate_1`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x18c10`: `Authentication to MSA services is not supported.`

## pseudocode

```c

```

## disassembly

```asm
0x18c10  ldstr    aAuthentication_3// "Authentication to MSA services is not s"...
0x18c15  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x18c1a  throw
```
