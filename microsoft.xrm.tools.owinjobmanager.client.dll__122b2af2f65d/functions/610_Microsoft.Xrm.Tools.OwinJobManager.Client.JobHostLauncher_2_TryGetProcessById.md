# Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2::TryGetProcessById

- ea: `0x610`
- end: `0x620`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2::TryGetProcessById`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x610`

## pseudocode

```c

```

## disassembly

```asm
0x610  ldarg.0
0x611  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::GetProcessById(int32)
0x616  stloc.0
0x617  leave.s  loc_61E
0x619  pop
0x61a  ldnull
0x61b  stloc.0
0x61c  leave.s  loc_61E
0x61e  ldloc.0
0x61f  ret
```
