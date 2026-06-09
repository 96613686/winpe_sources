# Microsoft.Crm.Asynchronous.ImportOperation::IncrementPerfCounter

- ea: `0xaab0`
- end: `0xaabc`
- name: `Microsoft.Crm.Asynchronous.ImportOperation::IncrementPerfCounter`
- size: `12`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4f20`
- `0x11690`
- `0x11a20`
- `0x17420`
- `0x17910`
- `0x1a860`
- `0x1aa60`

## callees

- `0xaab0`

## pseudocode

```c

```

## disassembly

```asm
0xaab0  ldarg.0
0xaab1  brtrue.s loc_AAB4
0xaab3  ret
0xaab4  ldarg.0
0xaab5  callvirt instance int64 [System]System.Diagnostics.PerformanceCounter::Increment()
0xaaba  pop
0xaabb  ret
```
