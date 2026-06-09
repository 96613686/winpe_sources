# CSidCacheItem::`scalar deleting destructor'(uint)

- ea: `0x18001b3c0`
- end: `0x18001b3f0`
- name: `??_GCSidCacheItem@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(CSidCacheItem *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, authz_impersonation`

## callees

- `0x18001b374`
- `0x18001b3c0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001b3dc`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b3dc`

## pseudocode

```c
CSidCacheItem *__fastcall CSidCacheItem::`scalar deleting destructor'(CSidCacheItem *this, char a2)
{
  CSidCacheItem::~CSidCacheItem(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18001b3c0  mov     [rsp+arg_0], rbx
0x18001b3c5  push    rdi
0x18001b3c6  sub     rsp, 20h
0x18001b3ca  mov     ebx, edx
0x18001b3cc  mov     rdi, rcx
0x18001b3cf  call    ??1CSidCacheItem@@UEAA@XZ; CSidCacheItem::~CSidCacheItem(void)
0x18001b3d4  test    bl, 1
0x18001b3d7  jz      short loc_18001B3E2
0x18001b3d9  mov     rcx, rdi
0x18001b3dc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001b3e2  mov     rbx, [rsp+28h+arg_0]
0x18001b3e7  mov     rax, rdi
0x18001b3ea  add     rsp, 20h
0x18001b3ee  pop     rdi
0x18001b3ef  retn
```
