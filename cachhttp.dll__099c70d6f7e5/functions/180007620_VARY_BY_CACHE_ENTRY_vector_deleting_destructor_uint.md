# VARY_BY_CACHE_ENTRY::`vector deleting destructor'(uint)

- ea: `0x180007620`
- end: `0x18000764f`
- name: `??_EVARY_BY_CACHE_ENTRY@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(VARY_BY_CACHE_ENTRY *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180005a4c`
- `0x18000759c`
- `0x180007620`

## pseudocode

```c
VARY_BY_CACHE_ENTRY *__fastcall VARY_BY_CACHE_ENTRY::`vector deleting destructor'(VARY_BY_CACHE_ENTRY *this, char a2)
{
  VARY_BY_CACHE_ENTRY::~VARY_BY_CACHE_ENTRY(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180007620  mov     [rsp+arg_0], rbx
0x180007625  push    rdi
0x180007626  sub     rsp, 20h
0x18000762a  mov     ebx, edx
0x18000762c  mov     rdi, rcx
0x18000762f  call    ??1VARY_BY_CACHE_ENTRY@@UEAA@XZ; VARY_BY_CACHE_ENTRY::~VARY_BY_CACHE_ENTRY(void)
0x180007634  test    bl, 1
0x180007637  jz      short loc_180007641
0x180007639  mov     rcx, rdi; Block
0x18000763c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007641  mov     rbx, [rsp+28h+arg_0]
0x180007646  mov     rax, rdi
0x180007649  add     rsp, 20h
0x18000764d  pop     rdi
0x18000764e  retn
```
