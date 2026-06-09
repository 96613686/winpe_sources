# Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2::get_CancellationToken

- ea: `0x15f0`
- end: `0x15fc`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2::get_CancellationToken`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x15f0  ldarg.0
0x15f1  ldfld    class [mscorlib]System.Threading.CancellationTokenSource class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::cts
0x15f6  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationTokenSource::get_Token()
0x15fb  ret
```
