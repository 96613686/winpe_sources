# Microsoft.Crm.Extensibility.Throttling.SdkThrottlingConfigurationFactory::.ctor

- ea: `0xede0`
- end: `0xedf1`
- name: `Microsoft.Crm.Extensibility.Throttling.SdkThrottlingConfigurationFactory::.ctor`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xf4f0`

## callees

- `0x2b550`

## string_xrefs

- `0xede1`: `SdkServiceThrottlingSettings`
- `0xede6`: `OrgSdkServiceThrottlingSettings`

## pseudocode

```c

```

## disassembly

```asm
0xede0  ldarg.0
0xede1  ldstr    aSdkservicethro// "SdkServiceThrottlingSettings"
0xede6  ldstr    aOrgsdkservicet// "OrgSdkServiceThrottlingSettings"
0xedeb  call     instance void Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfigurationFactory::.ctor(string deploymentConfigKey, string orgConfigKey)
0xedf0  ret
```
