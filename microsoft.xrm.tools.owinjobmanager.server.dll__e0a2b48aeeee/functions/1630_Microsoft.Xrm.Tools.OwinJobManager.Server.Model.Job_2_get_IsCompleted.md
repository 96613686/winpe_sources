# Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2::get_IsCompleted

- ea: `0x1630`
- end: `0x1647`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2::get_IsCompleted`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1630`

## pseudocode

```c

```

## disassembly

```asm
0x1630  ldarg.0
0x1631  call     instance valuetype Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobStatus class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::get_Status()
0x1636  brfalse.s loc_1645
0x1638  ldarg.0
0x1639  call     instance valuetype Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobStatus class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::get_Status()
0x163e  ldc.i4.1
0x163f  ceq
0x1641  ldc.i4.0
0x1642  ceq
0x1644  ret
0x1645  ldc.i4.0
0x1646  ret
```
