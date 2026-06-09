# CUSTOM_ERROR_ENTRY::`scalar deleting destructor'(uint)

- ea: `0x180002b1c`
- end: `0x180002b3b`
- name: `??_GCUSTOM_ERROR_ENTRY@@QEAAPEAXI@Z`
- size: `31`
- prototype: `void *__fastcall(CUSTOM_ERROR_ENTRY *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002a14`
- `0x1800065f0`

## callees

- `0x180002030`
- `0x18000298c`

## pseudocode

```c
CUSTOM_ERROR_ENTRY *__fastcall CUSTOM_ERROR_ENTRY::`scalar deleting destructor'(CUSTOM_ERROR_ENTRY *this)
{
  CUSTOM_ERROR_ENTRY::~CUSTOM_ERROR_ENTRY(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002b1c  push    rbx
0x180002b1e  sub     rsp, 20h
0x180002b22  mov     rbx, rcx
0x180002b25  call    ??1CUSTOM_ERROR_ENTRY@@QEAA@XZ; CUSTOM_ERROR_ENTRY::~CUSTOM_ERROR_ENTRY(void)
0x180002b2a  mov     rcx, rbx; Block
0x180002b2d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002b32  mov     rax, rbx
0x180002b35  add     rsp, 20h
0x180002b39  pop     rbx
0x180002b3a  retn
```
