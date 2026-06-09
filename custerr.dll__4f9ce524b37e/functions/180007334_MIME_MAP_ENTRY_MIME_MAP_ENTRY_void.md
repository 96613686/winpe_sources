# MIME_MAP_ENTRY::~MIME_MAP_ENTRY(void)

- ea: `0x180007334`
- end: `0x180007357`
- name: `??1MIME_MAP_ENTRY@@QEAA@XZ`
- size: `35`
- prototype: `void __fastcall(MIME_MAP_ENTRY *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x1800073c4`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180007350`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007341`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007341`

## pseudocode

```c
void __fastcall MIME_MAP_ENTRY::~MIME_MAP_ENTRY(MIME_MAP_ENTRY *this)
{
  STRA::~STRA((MIME_MAP_ENTRY *)((char *)this + 80));
  STRU::~STRU((MIME_MAP_ENTRY *)((char *)this + 24));
}

```

## disassembly

```asm
0x180007334  push    rbx
0x180007336  sub     rsp, 20h
0x18000733a  mov     rbx, rcx
0x18000733d  add     rcx, 50h ; 'P'
0x180007341  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180007347  lea     rcx, [rbx+18h]
0x18000734b  add     rsp, 20h
0x18000734f  pop     rbx
0x180007350  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
