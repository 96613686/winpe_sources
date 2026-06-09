# Microsoft.Crm.Asynchronous.JobDataAccessConstants::get_JobsToReturnInSql

- ea: `0x3f20`
- end: `0x3f32`
- name: `Microsoft.Crm.Asynchronous.JobDataAccessConstants::get_JobsToReturnInSql`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x2b30`

## pseudocode

```c

```

## disassembly

```asm
0x3f20  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x3f25  ldstr    aAsyncjobstoret// "AsyncJobsToReturnInSql"
0x3f2a  ldc.i4.s 0x64
0x3f2c  callvirt T0x2B00000C
0x3f31  ret
```
