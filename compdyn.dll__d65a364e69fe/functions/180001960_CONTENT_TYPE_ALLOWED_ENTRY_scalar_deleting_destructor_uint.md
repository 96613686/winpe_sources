# CONTENT_TYPE_ALLOWED_ENTRY::`scalar deleting destructor'(uint)

- ea: `0x180001960`
- end: `0x18000198e`
- name: `??_GCONTENT_TYPE_ALLOWED_ENTRY@@QEAAPEAXI@Z`
- size: `46`
- prototype: `void *__fastcall(CONTENT_TYPE_ALLOWED_ENTRY *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001910`
- `0x180003850`

## callees

- `0x180004250`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x18000196d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001977`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000196d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001977`

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
0x180001960  push    rbx
0x180001962  sub     rsp, 20h
0x180001966  mov     rbx, rcx
0x180001969  add     rcx, 48h ; 'H'
0x18000196d  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180001973  lea     rcx, [rbx+10h]
0x180001977  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000197d  mov     rcx, rbx; Block
0x180001980  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001985  mov     rax, rbx
0x180001988  add     rsp, 20h
0x18000198c  pop     rbx
0x18000198d  retn
```
