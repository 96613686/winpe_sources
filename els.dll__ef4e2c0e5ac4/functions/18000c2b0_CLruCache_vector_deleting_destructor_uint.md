# CLruCache::`vector deleting destructor'(uint)

- ea: `0x18000c2b0`
- end: `0x18000c2e0`
- name: `??_ECLruCache@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(CLruCache *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180002740`
- `0x18000c2b0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000c2cc`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c2cc`

## pseudocode

```c
CLruCache *__fastcall CLruCache::`vector deleting destructor'(CLruCache *this, char a2)
{
  CLruCache::~CLruCache(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000c2b0  mov     [rsp+arg_0], rbx
0x18000c2b5  push    rdi
0x18000c2b6  sub     rsp, 20h
0x18000c2ba  mov     ebx, edx
0x18000c2bc  mov     rdi, rcx
0x18000c2bf  call    ??1CLruCache@@UEAA@XZ; CLruCache::~CLruCache(void)
0x18000c2c4  test    bl, 1
0x18000c2c7  jz      short loc_18000C2D2
0x18000c2c9  mov     rcx, rdi
0x18000c2cc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c2d2  mov     rbx, [rsp+28h+arg_0]
0x18000c2d7  mov     rax, rdi
0x18000c2da  add     rsp, 20h
0x18000c2de  pop     rdi
0x18000c2df  retn
```
