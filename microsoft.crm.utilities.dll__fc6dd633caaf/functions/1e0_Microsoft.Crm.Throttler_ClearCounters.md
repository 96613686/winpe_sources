# Microsoft.Crm.Throttler::ClearCounters

- ea: `0x1e0`
- end: `0x1ed`
- name: `Microsoft.Crm.Throttler::ClearCounters`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x280`

## pseudocode

```c

```

## disassembly

```asm
0x1e0  volatile.
0x1e2  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, int32> Microsoft.Crm.Throttler::_counters
0x1e7  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, int32>::Clear()
0x1ec  ret
```
