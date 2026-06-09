# Microsoft.Crm.Sandbox.SandboxWorkerManager::LogExecutionTime

- ea: `0x7770`
- end: `0x77e2`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerManager::LogExecutionTime`
- size: `114`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x7370`
- `0x7610`
- `0x77f0`

## callees

- `0x7770`

## string_xrefs

- `0x7773`: `{0}:Thread[{1:d4}]: Spent {2} ms in {0}`
- `0x77b2`: `{0}:Thread[{1:d4}]: Spent more than 2 secs in {0}, Elapsed Time: {2} ms`

## pseudocode

```c

```

## disassembly

```asm
0x7770  ldarg.1
0x7771  ldc.i4.s 0x21
0x7773  ldstr    a0Thread1D4Spen// "{0}:Thread[{1:d4}]: Spent {2} ms in {0}"
0x7778  ldc.i4.3
0x7779  newarr   [mscorlib]System.Object
0x777e  dup
0x777f  ldc.i4.0
0x7780  ldarg.2
0x7781  stelem.ref
0x7782  dup
0x7783  ldc.i4.1
0x7784  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x7789  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x778e  box      [mscorlib]System.Int32
0x7793  stelem.ref
0x7794  dup
0x7795  ldc.i4.2
0x7796  ldarg.0
0x7797  box      [mscorlib]System.Double
0x779c  stelem.ref
0x779d  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x77a2  ldarg.0
0x77a3  ldc.r8   2000.0
0x77ac  ble.un.s loc_77E1
0x77ae  ldnull
0x77af  ldarg.1
0x77b0  ldc.i4.s 0x21
0x77b2  ldstr    a0Thread1D4Spen_0// "{0}:Thread[{1:d4}]: Spent more than 2 s"...
0x77b7  ldc.i4.3
0x77b8  newarr   [mscorlib]System.Object
0x77bd  dup
0x77be  ldc.i4.0
0x77bf  ldarg.2
0x77c0  stelem.ref
0x77c1  dup
0x77c2  ldc.i4.1
0x77c3  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x77c8  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x77cd  box      [mscorlib]System.Int32
0x77d2  stelem.ref
0x77d3  dup
0x77d4  ldc.i4.2
0x77d5  ldarg.0
0x77d6  box      [mscorlib]System.Double
0x77db  stelem.ref
0x77dc  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x77e1  ret
```
