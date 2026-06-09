# Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.HttpClientExtensions::GetWithRetry

- ea: `0x970`
- end: `0x9a4`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.HttpClientExtensions::GetWithRetry`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x970`

## pseudocode

```c

```

## disassembly

```asm
0x970  ldc.i4.1
0x971  stloc.0
0x972  nop
0x973  ldarg.0
0x974  ldarg.1
0x975  call     T0x2B00000C
0x97a  stloc.1
0x97b  leave.s  loc_9A2
0x97d  isinst   [mscorlib]System.Threading.Tasks.TaskCanceledException
0x982  dup
0x983  brtrue.s loc_989
0x985  pop
0x986  ldc.i4.0
0x987  br.s     loc_991
0x989  pop
0x98a  ldloc.0
0x98b  ldarg.2
0x98c  clt
0x98e  ldc.i4.0
0x98f  cgt.un
0x991  endfilter
0x993  pop
0x994  ldarg.3
0x995  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x99a  leave.s  loc_99C
0x99c  ldloc.0
0x99d  ldc.i4.1
0x99e  add
0x99f  stloc.0
0x9a0  br.s     loc_972
0x9a2  ldloc.1
0x9a3  ret
```
