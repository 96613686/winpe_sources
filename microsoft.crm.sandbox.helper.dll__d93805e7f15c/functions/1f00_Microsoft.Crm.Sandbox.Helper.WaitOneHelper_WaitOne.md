# Microsoft.Crm.Sandbox.Helper.WaitOneHelper::WaitOne

- ea: `0x1f00`
- end: `0x1f7c`
- name: `Microsoft.Crm.Sandbox.Helper.WaitOneHelper::WaitOne`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x7b0`

## callees

- `0x1f00`

## pseudocode

```c

```

## disassembly

```asm
0x1f00  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x1f05  stloc.0
0x1f06  ldloc.0
0x1f07  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x1f0c  ldloc.0
0x1f0d  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x1f12  stloc.1
0x1f13  br.s     loc_1F6D
0x1f15  ldarg.1
0x1f16  ldloc.1
0x1f17  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::op_Subtraction(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x1f1c  stloc.2
0x1f1d  ldloca.s 2
0x1f1f  call     instance int32 [mscorlib]System.TimeSpan::get_Seconds()
0x1f24  ldc.i4.1
0x1f25  bge.s    loc_1F36
0x1f27  ldarg.0
0x1f28  ldfld    class [mscorlib]System.Threading.WaitHandle[] Microsoft.Crm.Sandbox.Helper.WaitOneHelper::_resetEvents
0x1f2d  ldloc.2
0x1f2e  call     int32 [mscorlib]System.Threading.WaitHandle::WaitAny(class [mscorlib]System.Threading.WaitHandle[], valuetype [mscorlib]System.TimeSpan)
0x1f33  stloc.3
0x1f34  br.s     loc_1F58
0x1f36  ldarg.0
0x1f37  ldfld    class [mscorlib]System.Threading.WaitHandle[] Microsoft.Crm.Sandbox.Helper.WaitOneHelper::_resetEvents
0x1f3c  ldloca.s 2
0x1f3e  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x1f43  ldc.r8   2.0
0x1f4c  div
0x1f4d  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMilliseconds(float64)
0x1f52  call     int32 [mscorlib]System.Threading.WaitHandle::WaitAny(class [mscorlib]System.Threading.WaitHandle[], valuetype [mscorlib]System.TimeSpan)
0x1f57  stloc.3
0x1f58  ldloc.3
0x1f59  ldc.i4.0
0x1f5a  blt.s    loc_1F66
0x1f5c  ldloc.3
0x1f5d  ldc.i4   0x102
0x1f62  beq.s    loc_1F66
0x1f64  ldloc.3
0x1f65  ret
0x1f66  ldloc.0
0x1f67  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x1f6c  stloc.1
0x1f6d  ldloc.1
0x1f6e  ldarg.1
0x1f6f  call     bool [mscorlib]System.TimeSpan::op_LessThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x1f74  brtrue.s loc_1F15
0x1f76  ldc.i4   0x102
0x1f7b  ret
```
