# CONTENT_TYPE_ALLOWED_ENTRY::`scalar deleting destructor'(uint)

- ea: `0x180008088`
- end: `0x1800080b6`
- name: `??_GCONTENT_TYPE_ALLOWED_ENTRY@@QEAAPEAXI@Z`
- size: `46`
- prototype: `void *__fastcall(CONTENT_TYPE_ALLOWED_ENTRY *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800036d0`
- `0x1800088c0`

## callees

- `0x1800054a0`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x180008095`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000809f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008095`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000809f`

## pseudocode

```c
CONTENT_TYPE_ALLOWED_ENTRY *__fastcall CONTENT_TYPE_ALLOWED_ENTRY::`scalar deleting destructor'(
        CONTENT_TYPE_ALLOWED_ENTRY *this)
{
  STRA::~STRA((CONTENT_TYPE_ALLOWED_ENTRY *)((char *)this + 72));
  STRA::~STRA((CONTENT_TYPE_ALLOWED_ENTRY *)((char *)this + 16));
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180008088  push    rbx
0x18000808a  sub     rsp, 20h
0x18000808e  mov     rbx, rcx
0x180008091  add     rcx, 48h ; 'H'
0x180008095  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000809b  lea     rcx, [rbx+10h]
0x18000809f  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800080a5  mov     rcx, rbx; Block
0x1800080a8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800080ad  mov     rax, rbx
0x1800080b0  add     rsp, 20h
0x1800080b4  pop     rbx
0x1800080b5  retn
```
