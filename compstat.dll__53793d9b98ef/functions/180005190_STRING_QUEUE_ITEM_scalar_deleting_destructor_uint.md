# STRING_QUEUE_ITEM::`scalar deleting destructor'(uint)

- ea: `0x180005190`
- end: `0x1800051b4`
- name: `??_GSTRING_QUEUE_ITEM@@QEAAPEAXI@Z`
- size: `36`
- prototype: `void *__fastcall(STRING_QUEUE_ITEM *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004d40`
- `0x180004d70`
- `0x1800051c0`
- `0x180008120`

## callees

- `0x1800054a0`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000519d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000519d`

## pseudocode

```c
STRING_QUEUE_ITEM *__fastcall STRING_QUEUE_ITEM::`scalar deleting destructor'(STRING_QUEUE_ITEM *this)
{
  STRU::~STRU((STRING_QUEUE_ITEM *)((char *)this + 16));
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180005190  push    rbx
0x180005192  sub     rsp, 20h
0x180005196  mov     rbx, rcx
0x180005199  add     rcx, 10h
0x18000519d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800051a3  mov     rcx, rbx; Block
0x1800051a6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800051ab  mov     rax, rbx
0x1800051ae  add     rsp, 20h
0x1800051b2  pop     rbx
0x1800051b3  retn
```
