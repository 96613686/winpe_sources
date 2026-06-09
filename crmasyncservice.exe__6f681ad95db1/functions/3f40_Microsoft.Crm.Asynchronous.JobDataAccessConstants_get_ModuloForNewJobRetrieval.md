# Microsoft.Crm.Asynchronous.JobDataAccessConstants::get_ModuloForNewJobRetrieval

- ea: `0x3f40`
- end: `0x3f51`
- name: `Microsoft.Crm.Asynchronous.JobDataAccessConstants::get_ModuloForNewJobRetrieval`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x47b0`

## pseudocode

```c

```

## disassembly

```asm
0x3f40  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x3f45  ldstr    aAsyncjobsmodul// "AsyncJobsModuloForNewJobRetrieval"
0x3f4a  ldc.i4.8
0x3f4b  callvirt T0x2B00000C
0x3f50  ret
```
