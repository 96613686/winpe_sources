# Microsoft.Crm.Asynchronous.Settings::get_MaxThreadPercentForThrottledOrganizations

- ea: `0x10100`
- end: `0x10112`
- name: `Microsoft.Crm.Asynchronous.Settings::get_MaxThreadPercentForThrottledOrganizations`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x67d0`

## string_xrefs

- `0x10105`: `AsyncMaxThreadPercentForThrottledOrganizations`

## pseudocode

```c

```

## disassembly

```asm
0x10100  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x10105  ldstr    aAsyncmaxthread// "AsyncMaxThreadPercentForThrottledOrgani"...
0x1010a  ldc.i4.s 0x19
0x1010c  callvirt T0x2B00001D
0x10111  ret
```
