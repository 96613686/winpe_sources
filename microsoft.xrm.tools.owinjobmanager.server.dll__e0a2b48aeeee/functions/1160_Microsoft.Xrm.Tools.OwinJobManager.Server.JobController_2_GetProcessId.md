# Microsoft.Xrm.Tools.OwinJobManager.Server.JobController`2::GetProcessId

- ea: `0x1160`
- end: `0x1176`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.JobController`2::GetProcessId`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1160  ldarg.0
0x1161  ldc.i4   0xC8
0x1166  ldsfld   class [mscorlib]System.Lazy`1<int32> class Microsoft.Xrm.Tools.OwinJobManager.Server.JobController`2<var<u1>, !!T0>::PID
0x116b  callvirt instance var<u1> class [mscorlib]System.Lazy`1<int32>::get_Value()
0x1170  callvirt T0x2B000009
0x1175  ret
```
