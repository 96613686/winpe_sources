# Microsoft.Xrm.Sdk.Utility.ConfigurationProviderFactory::CreateConfigurationProviderInternal

- ea: `0x4f0`
- end: `0x503`
- name: `Microsoft.Xrm.Sdk.Utility.ConfigurationProviderFactory::CreateConfigurationProviderInternal`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4a0`

## callees

- `0x430`
- `0x460`
- `0x4f0`

## pseudocode

```c

```

## disassembly

```asm
0x4f0  ldarg.0
0x4f1  brfalse.s loc_4FD
0x4f3  ldarg.0
0x4f4  ldc.i4.1
0x4f5  bne.un.s loc_4FD
0x4f7  newobj   instance void Microsoft.Xrm.Sdk.Utility.OrganizationProvider::.ctor()
0x4fc  ret
0x4fd  newobj   instance void Microsoft.Xrm.Sdk.Utility.DiscoveryProvider::.ctor()
0x502  ret
```
