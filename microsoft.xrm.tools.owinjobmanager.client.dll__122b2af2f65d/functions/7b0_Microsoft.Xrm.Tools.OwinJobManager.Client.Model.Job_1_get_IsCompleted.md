# Microsoft.Xrm.Tools.OwinJobManager.Client.Model.Job`1::get_IsCompleted

- ea: `0x7b0`
- end: `0x7c7`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.Model.Job`1::get_IsCompleted`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x7b0`

## pseudocode

```c

```

## disassembly

```asm
0x7b0  ldarg.0
0x7b1  call     instance valuetype Microsoft.Xrm.Tools.OwinJobManager.Client.Model.JobStatus class Microsoft.Xrm.Tools.OwinJobManager.Client.Model.Job`1<var<u1>>::get_Status()
0x7b6  brfalse.s loc_7C5
0x7b8  ldarg.0
0x7b9  call     instance valuetype Microsoft.Xrm.Tools.OwinJobManager.Client.Model.JobStatus class Microsoft.Xrm.Tools.OwinJobManager.Client.Model.Job`1<var<u1>>::get_Status()
0x7be  ldc.i4.1
0x7bf  ceq
0x7c1  ldc.i4.0
0x7c2  ceq
0x7c4  ret
0x7c5  ldc.i4.0
0x7c6  ret
```
