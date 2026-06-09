# CIDsCache::`vector deleting destructor'(uint)

- ea: `0x18000c230`
- end: `0x18000c26a`
- name: `??_ECIDsCache@@UEAAPEAXI@Z`
- size: `58`
- prototype: `void *__fastcall(CIDsCache *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180002740`
- `0x18000c230`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000c256`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c256`

## pseudocode

```c
CIDsCache *__fastcall CIDsCache::`vector deleting destructor'(CIDsCache *this, char a2)
{
  *(_QWORD *)this = &CIDsCache::`vftable';
  CLruCache::~CLruCache(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000c230  mov     [rsp+arg_0], rbx
0x18000c235  push    rdi
0x18000c236  sub     rsp, 20h
0x18000c23a  lea     rax, ??_7CIDsCache@@6B@; const CIDsCache::`vftable'
0x18000c241  mov     ebx, edx
0x18000c243  mov     [rcx], rax
0x18000c246  mov     rdi, rcx
0x18000c249  call    ??1CLruCache@@UEAA@XZ; CLruCache::~CLruCache(void)
0x18000c24e  test    bl, 1
0x18000c251  jz      short loc_18000C25C
0x18000c253  mov     rcx, rdi
0x18000c256  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c25c  mov     rbx, [rsp+28h+arg_0]
0x18000c261  mov     rax, rdi
0x18000c264  add     rsp, 20h
0x18000c268  pop     rdi
0x18000c269  retn
```
