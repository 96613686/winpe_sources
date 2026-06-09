# Microsoft.Crm.Asynchronous.Rollups.RollupConfiguration::get_BootstrapRollupUpdateBatchSize

- ea: `0xc9b0`
- end: `0xc9c5`
- name: `Microsoft.Crm.Asynchronous.Rollups.RollupConfiguration::get_BootstrapRollupUpdateBatchSize`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0xe9c0`
- `0xed70`

## string_xrefs

- `0xc9b5`: `BootstrapRollupUpdateBatchSize`

## pseudocode

```c

```

## disassembly

```asm
0xc9b0  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0xc9b5  ldstr    aBootstraprollu_5// "BootstrapRollupUpdateBatchSize"
0xc9ba  ldc.i4   0x1388
0xc9bf  callvirt T0x2B00001C
0xc9c4  ret
```
