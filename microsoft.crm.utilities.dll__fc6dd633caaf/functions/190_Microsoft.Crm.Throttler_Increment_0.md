# Microsoft.Crm.Throttler::Increment_0

- ea: `0x190`
- end: `0x1da`
- name: `Microsoft.Crm.Throttler::Increment_0`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x170`

## callees

- `0x190`
- `0x1f0`

## pseudocode

```c

```

## disassembly

```asm
0x190  ldarg.2
0x191  brtrue.s loc_19E
0x193  ldstr    aOnthresholdexc// "onThresholdExceeded"
0x198  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x19d  throw
0x19e  call     void Microsoft.Crm.Throttler::StartTimers()
0x1a3  volatile.
0x1a5  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, int32> Microsoft.Crm.Throttler::_counters
0x1aa  ldarg.0
0x1ab  ldc.i4.1
0x1ac  ldsfld   class [mscorlib]System.Func`3<string, int32, int32> <>c::<>9__4_0
0x1b1  dup
0x1b2  brtrue.s loc_1CB
0x1b4  pop
0x1b5  ldsfld   class <>c <>c::<>9
0x1ba  ldftn    instance int32 <>c::<Increment>b__4_0(string k, int32 counter)
0x1c0  newobj   instance void class [mscorlib]System.Func`3<string, int32, int32>::.ctor(object, native int)
0x1c5  dup
0x1c6  stsfld   class [mscorlib]System.Func`3<string, int32, int32> <>c::<>9__4_0
0x1cb  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, int32>::AddOrUpdate(void, var<u1>, !!T0)
0x1d0  ldarg.1
0x1d1  ble.s    loc_1D9
0x1d3  ldarg.2
0x1d4  callvirt instance void [mscorlib]System.Action::Invoke()
0x1d9  ret
```
