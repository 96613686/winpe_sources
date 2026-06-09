# Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.HttpClientExtensions::PostWithRetry

- ea: `0x9b0`
- end: `0x9e6`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.HttpClientExtensions::PostWithRetry`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x9b0`

## pseudocode

```c

```

## disassembly

```asm
0x9b0  ldc.i4.1
0x9b1  stloc.0
0x9b2  nop
0x9b3  ldarg.0
0x9b4  ldarg.1
0x9b5  ldarg.2
0x9b6  call     T0x2B00000D
0x9bb  stloc.1
0x9bc  leave.s  loc_9E4
0x9be  isinst   [mscorlib]System.Threading.Tasks.TaskCanceledException
0x9c3  dup
0x9c4  brtrue.s loc_9CA
0x9c6  pop
0x9c7  ldc.i4.0
0x9c8  br.s     loc_9D2
0x9ca  pop
0x9cb  ldloc.0
0x9cc  ldarg.3
0x9cd  clt
0x9cf  ldc.i4.0
0x9d0  cgt.un
0x9d2  endfilter
0x9d4  pop
0x9d5  ldarg.s  4
0x9d7  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x9dc  leave.s  loc_9DE
0x9de  ldloc.0
0x9df  ldc.i4.1
0x9e0  add
0x9e1  stloc.0
0x9e2  br.s     loc_9B2
0x9e4  ldloc.1
0x9e5  ret
```
