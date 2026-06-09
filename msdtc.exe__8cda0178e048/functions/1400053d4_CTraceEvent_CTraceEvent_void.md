# CTraceEvent::~CTraceEvent(void)

- ea: `0x1400053d4`
- end: `0x1400053df`
- name: `??1CTraceEvent@@UEAA@XZ`
- size: `11`
- prototype: `void __fastcall(CTraceEvent *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x14000711a`
- `0x140007150`

## pseudocode

```c
void __fastcall CTraceEvent::~CTraceEvent(CTraceEvent *this)
{
  *(_QWORD *)this = &CTraceEvent::`vftable';
}

```

## disassembly

```asm
0x1400053d4  lea     rax, ??_7CTraceEvent@@6B@; const CTraceEvent::`vftable'
0x1400053db  mov     [rcx], rax
0x1400053de  retn
```
