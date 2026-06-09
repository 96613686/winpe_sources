# Microsoft.Crm.Asynchronous.Settings::get_NoOfParallelThreadsForStatCollection

- ea: `0x10140`
- end: `0x10151`
- name: `Microsoft.Crm.Asynchronous.Settings::get_NoOfParallelThreadsForStatCollection`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0xf9a0`

## string_xrefs

- `0x10145`: `AsyncNoOfParallelThreadsForStatCollection`

## pseudocode

```c

```

## disassembly

```asm
0x10140  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x10145  ldstr    aAsyncnoofparal// "AsyncNoOfParallelThreadsForStatCollecti"...
0x1014a  ldc.i4.3
0x1014b  callvirt T0x2B00001D
0x10150  ret
```
