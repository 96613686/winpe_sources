# Microsoft.Crm.Asynchronous.JobDataAccessConstants::get_JobsToProcessAtOnce

- ea: `0x3f00`
- end: `0x3f12`
- name: `Microsoft.Crm.Asynchronous.JobDataAccessConstants::get_JobsToProcessAtOnce`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x4480`

## pseudocode

```c

```

## disassembly

```asm
0x3f00  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x3f05  ldstr    aAsyncjobstopro// "AsyncJobsToProcessAtOnce"
0x3f0a  ldc.i4.s 0xA
0x3f0c  callvirt T0x2B00000C
0x3f11  ret
```
