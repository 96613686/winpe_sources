# UL_RESPONSE_CACHE_ENTRY::`scalar deleting destructor'(uint)

- ea: `0x180001010`
- end: `0x18000103f`
- name: `??_GUL_RESPONSE_CACHE_ENTRY@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(UL_RESPONSE_CACHE_ENTRY *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001010`
- `0x180001048`
- `0x180005a4c`

## pseudocode

```c
UL_RESPONSE_CACHE_ENTRY *__fastcall UL_RESPONSE_CACHE_ENTRY::`scalar deleting destructor'(
        UL_RESPONSE_CACHE_ENTRY *this,
        char a2)
{
  UL_RESPONSE_CACHE_ENTRY::~UL_RESPONSE_CACHE_ENTRY(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180001010  mov     [rsp+arg_0], rbx
0x180001015  push    rdi
0x180001016  sub     rsp, 20h
0x18000101a  mov     ebx, edx
0x18000101c  mov     rdi, rcx
0x18000101f  call    ??1UL_RESPONSE_CACHE_ENTRY@@UEAA@XZ; UL_RESPONSE_CACHE_ENTRY::~UL_RESPONSE_CACHE_ENTRY(void)
0x180001024  test    bl, 1
0x180001027  jz      short loc_180001031
0x180001029  mov     rcx, rdi; Block
0x18000102c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001031  mov     rbx, [rsp+28h+arg_0]
0x180001036  mov     rax, rdi
0x180001039  add     rsp, 20h
0x18000103d  pop     rdi
0x18000103e  retn
```
