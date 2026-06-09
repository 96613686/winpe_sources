# Microsoft.Crm.Asynchronous.BulkDeleteOperation::TryResumingPausedJobs

- ea: `0x2930`
- end: `0x2968`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperation::TryResumingPausedJobs`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1f350`

## callees

- `0x2930`
- `0x2970`

## pseudocode

```c

```

## disassembly

```asm
0x2930  ldarg.0
0x2931  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_pausedJobs
0x2936  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x293b  stloc.0
0x293c  br.s     loc_294E
0x293e  ldloca.s 0
0x2940  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::get_Current()
0x2945  stloc.1
0x2946  ldarg.0
0x2947  ldloc.1
0x2948  call     instance bool Microsoft.Crm.Asynchronous.BulkDeleteOperation::MoveAsyncJobToReadyState(valuetype [mscorlib]System.Guid asyncOpId)
0x294d  pop
0x294e  ldloca.s 0
0x2950  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::MoveNext()
0x2955  brtrue.s loc_293E
0x2957  leave.s  loc_2967
0x2959  ldloca.s 0
0x295b  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>
0x2961  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2966  endfinally
0x2967  ret
```
