# TRACE_AREAS_STORED_ENTRY::TRACE_AREAS_STORED_ENTRY(void)

- ea: `0x180005974`
- end: `0x180005978`
- name: `??0TRACE_AREAS_STORED_ENTRY@@QEAA@XZ`
- size: `4`
- prototype: `TRACE_AREAS_STORED_ENTRY *__fastcall(TRACE_AREAS_STORED_ENTRY *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180005b28`
- `0x1800075d4`

## pseudocode

```c
TRACE_AREAS_STORED_ENTRY *__fastcall TRACE_AREAS_STORED_ENTRY::TRACE_AREAS_STORED_ENTRY(TRACE_AREAS_STORED_ENTRY *this)
{
  return this;
}

```

## disassembly

```asm
0x180005974  mov     rax, rcx
0x180005977  retn
```
