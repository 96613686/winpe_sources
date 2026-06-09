# Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2::IsIgnorableProcessKillException

- ea: `0x650`
- end: `0x673`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2::IsIgnorableProcessKillException`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x650`

## pseudocode

```c

```

## disassembly

```asm
0x650  ldarg.0
0x651  isinst   [mscorlib]System.InvalidOperationException
0x656  brtrue.s loc_671
0x658  ldarg.0
0x659  isinst   [System]System.ComponentModel.Win32Exception
0x65e  brfalse.s loc_66F
0x660  ldarg.0
0x661  castclass [System]System.ComponentModel.Win32Exception
0x666  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0x66b  ldc.i4.5
0x66c  ceq
0x66e  ret
0x66f  ldc.i4.0
0x670  ret
0x671  ldc.i4.1
0x672  ret
```
