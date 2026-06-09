# W3_RESTRICTION_LIST::`scalar deleting destructor'(uint)

- ea: `0x180001d8c`
- end: `0x180001dac`
- name: `??_GW3_RESTRICTION_LIST@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(W3_RESTRICTION_LIST *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001e7c`
- `0x180001f2c`
- `0x1800032c0`
- `0x180012068`

## callees

- `0x180001060`

## import_xrefs

- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180001d95`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180001d95`

## pseudocode

```c
W3_RESTRICTION_LIST *__fastcall W3_RESTRICTION_LIST::`scalar deleting destructor'(W3_RESTRICTION_LIST *this)
{
  CLKRHashTable::~CLKRHashTable(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180001d8c  push    rbx
0x180001d8e  sub     rsp, 20h
0x180001d92  mov     rbx, rcx
0x180001d95  call    cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
0x180001d9b  mov     rcx, rbx; Block
0x180001d9e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001da3  mov     rax, rbx
0x180001da6  add     rsp, 20h
0x180001daa  pop     rbx
0x180001dab  retn
```
