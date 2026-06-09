# Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2::TryKill

- ea: `0x620`
- end: `0x64d`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2::TryKill`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x620`

## pseudocode

```c

```

## disassembly

```asm
0x620  ldarg.0
0x621  brtrue.s loc_625
0x623  ldc.i4.0
0x624  ret
0x625  nop
0x626  ldarg.0
0x627  callvirt instance void [System]System.Diagnostics.Process::Kill()
0x62c  ldc.i4.1
0x62d  stloc.0
0x62e  leave.s  loc_64B
0x630  isinst   [mscorlib]System.Exception
0x635  dup
0x636  brtrue.s loc_63C
0x638  pop
0x639  ldc.i4.0
0x63a  br.s     loc_644
0x63c  call     bool class Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2<var<u1>, !!T0>::IsIgnorableProcessKillException(class [mscorlib]System.Exception)
0x641  ldc.i4.0
0x642  cgt.un
0x644  endfilter
0x646  pop
0x647  ldc.i4.0
0x648  stloc.0
0x649  leave.s  loc_64B
0x64b  ldloc.0
0x64c  ret
```
