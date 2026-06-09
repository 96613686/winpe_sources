# Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingStateExtensions::ToThrottlingState

- ea: `0x2bde0`
- end: `0x2be24`
- name: `Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingStateExtensions::ToThrottlingState`
- size: `68`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x2b770`
- `0x2b830`

## callees

- `0x2b060`
- `0x2b080`
- `0x2b230`
- `0x2bd30`
- `0x2bd50`
- `0x2bd70`
- `0x2bd90`
- `0x2bdb0`
- `0x2bdc0`

## pseudocode

```c

```

## disassembly

```asm
0x2bde0  newobj   instance void Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::.ctor()
0x2bde5  dup
0x2bde6  ldarg.s  4
0x2bde8  callvirt instance void Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::set_Attempted(valuetype [mscorlib]System.Nullable`1<int64> value)
0x2bded  dup
0x2bdee  ldarg.0
0x2bdef  ldarg.1
0x2bdf0  ldarg.2
0x2bdf1  ldloca.s 0
0x2bdf3  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.TimeSpan>
0x2bdf9  ldloc.0
0x2bdfa  callvirt instance int64 Microsoft.Crm.Extensibility.ODataV4.Throttling.SlidingWindowCounter::GetCount(valuetype [mscorlib]System.DateTime now, string key, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.TimeSpan> dynamicWindowSize)
0x2bdff  callvirt instance void Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::set_Passed(int64 value)
0x2be04  dup
0x2be05  ldarg.0
0x2be06  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Extensibility.ODataV4.Throttling.SlidingWindowCounter::get_WindowSize()
0x2be0b  callvirt instance void Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::set_Window(valuetype [mscorlib]System.TimeSpan value)
0x2be10  dup
0x2be11  ldarg.0
0x2be12  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Extensibility.ODataV4.Throttling.SlidingWindowCounter::get_BucketSize()
0x2be17  callvirt instance void Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::set_Bucket(valuetype [mscorlib]System.TimeSpan value)
0x2be1c  dup
0x2be1d  ldarg.3
0x2be1e  callvirt instance void Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingState::set_Threshold(int64 value)
0x2be23  ret
```
