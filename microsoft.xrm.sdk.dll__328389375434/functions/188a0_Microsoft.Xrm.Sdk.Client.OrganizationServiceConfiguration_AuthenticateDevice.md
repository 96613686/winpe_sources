# Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration::AuthenticateDevice

- ea: `0x188a0`
- end: `0x188ab`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration::AuthenticateDevice`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x188a0`: `Authentication to MSA services is not supported.`

## pseudocode

```c

```

## disassembly

```asm
0x188a0  ldstr    aAuthentication_3// "Authentication to MSA services is not s"...
0x188a5  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x188aa  throw
```
