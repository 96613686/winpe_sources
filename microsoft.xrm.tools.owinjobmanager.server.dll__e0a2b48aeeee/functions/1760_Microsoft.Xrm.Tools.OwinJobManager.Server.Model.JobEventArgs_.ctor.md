# Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobEventArgs::.ctor

- ea: `0x1760`
- end: `0x177c`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobEventArgs::.ctor`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xdc0`

## callees

- `0x1760`

## pseudocode

```c

```

## disassembly

```asm
0x1760  ldarg.0
0x1761  call     instance void [mscorlib]System.EventArgs::.ctor()
0x1766  ldarg.1
0x1767  brtrue.s loc_1774
0x1769  ldstr    aJob// "job"
0x176e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1773  throw
0x1774  ldarg.0
0x1775  ldarg.1
0x1776  stfld    class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.IJob Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobEventArgs::<Job>k__BackingField
0x177b  ret
```
