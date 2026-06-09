# AsyncOperationPerformanceCounters::UpdateTimeBasedCounter

- ea: `0x16080`
- end: `0x160db`
- name: `AsyncOperationPerformanceCounters::UpdateTimeBasedCounter`
- size: `91`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x15f50`
- `0x16010`
- `0x16040`

## callees

- `0x16080`

## pseudocode

```c

```

## disassembly

```asm
0x16080  ldc.i4.0
0x16081  conv.i8
0x16082  stloc.0
0x16083  ldarg.s  4
0x16085  ldsfld   valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::MinValue
0x1608a  call     bool [mscorlib]System.TimeSpan::op_Inequality(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x1608f  brfalse.s loc_160DA
0x16091  ldarga.s 4
0x16093  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x16098  call     int64 [mscorlib]System.Convert::ToInt64(float64)
0x1609d  stloc.0
0x1609e  ldarg.3
0x1609f  ldloc.0
0x160a0  call     int64 [mscorlib]System.Threading.Interlocked::Add(int64&, int64)
0x160a5  stloc.1
0x160a6  ldarg.2
0x160a7  call     int64 [mscorlib]System.Threading.Interlocked::Increment(int64&)
0x160ac  stloc.2
0x160ad  ldloc.1
0x160ae  ldc.i4.0
0x160af  conv.i8
0x160b0  blt.s    loc_160B7
0x160b2  ldloc.2
0x160b3  ldc.i4.0
0x160b4  conv.i8
0x160b5  bgt.s    loc_160D1
0x160b7  ldc.i4.1
0x160b8  conv.i8
0x160b9  stloc.2
0x160ba  ldarg.1
0x160bb  callvirt instance int64 [System]System.Diagnostics.PerformanceCounter::get_RawValue()
0x160c0  stloc.1
0x160c1  ldarg.2
0x160c2  ldloc.2
0x160c3  call     int64 [mscorlib]System.Threading.Interlocked::Exchange(int64&, int64)
0x160c8  pop
0x160c9  ldarg.3
0x160ca  ldloc.1
0x160cb  call     int64 [mscorlib]System.Threading.Interlocked::Exchange(int64&, int64)
0x160d0  pop
0x160d1  ldarg.1
0x160d2  ldloc.1
0x160d3  ldloc.2
0x160d4  div
0x160d5  callvirt instance void [System]System.Diagnostics.PerformanceCounter::set_RawValue(int64)
0x160da  ret
```
