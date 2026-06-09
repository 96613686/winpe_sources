# MIME_MAP_ENTRY::`scalar deleting destructor'(uint)

- ea: `0x180008bf4`
- end: `0x180008c22`
- name: `??_GMIME_MAP_ENTRY@@QEAAPEAXI@Z`
- size: `46`
- prototype: `void *__fastcall(MIME_MAP_ENTRY *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003a50`
- `0x180008b90`

## callees

- `0x1800054a0`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x180008c01`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008c01`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008c0b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008c0b`

## pseudocode

```c
MIME_MAP_ENTRY *__fastcall MIME_MAP_ENTRY::`scalar deleting destructor'(MIME_MAP_ENTRY *this)
{
  STRA::~STRA((MIME_MAP_ENTRY *)((char *)this + 80));
  STRU::~STRU((MIME_MAP_ENTRY *)((char *)this + 24));
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180008bf4  push    rbx
0x180008bf6  sub     rsp, 20h
0x180008bfa  mov     rbx, rcx
0x180008bfd  add     rcx, 50h ; 'P'
0x180008c01  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180008c07  lea     rcx, [rbx+18h]
0x180008c0b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180008c11  mov     rcx, rbx; Block
0x180008c14  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008c19  mov     rax, rbx
0x180008c1c  add     rsp, 20h
0x180008c20  pop     rbx
0x180008c21  retn
```
