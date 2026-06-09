# Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration::Authenticate_1

- ea: `0x18890`
- end: `0x1889b`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration::Authenticate_1`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x18890`: `Authentication to MSA services is not supported.`

## pseudocode

```c

```

## disassembly

```asm
0x18890  ldstr    aAuthentication_3// "Authentication to MSA services is not s"...
0x18895  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1889a  throw
```
