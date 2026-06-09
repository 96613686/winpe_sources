# CDllCacheItem::`vector deleting destructor'(uint)

- ea: `0x18000c270`
- end: `0x18000c2a0`
- name: `??_ECDllCacheItem@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(CDllCacheItem *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x18000c1b4`
- `0x18000c270`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000c28c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c28c`

## pseudocode

```c
CDllCacheItem *__fastcall CDllCacheItem::`vector deleting destructor'(CDllCacheItem *this, char a2)
{
  CDllCacheItem::~CDllCacheItem(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000c270  mov     [rsp+arg_0], rbx
0x18000c275  push    rdi
0x18000c276  sub     rsp, 20h
0x18000c27a  mov     ebx, edx
0x18000c27c  mov     rdi, rcx
0x18000c27f  call    ??1CDllCacheItem@@UEAA@XZ; CDllCacheItem::~CDllCacheItem(void)
0x18000c284  test    bl, 1
0x18000c287  jz      short loc_18000C292
0x18000c289  mov     rcx, rdi
0x18000c28c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c292  mov     rbx, [rsp+28h+arg_0]
0x18000c297  mov     rax, rdi
0x18000c29a  add     rsp, 20h
0x18000c29e  pop     rdi
0x18000c29f  retn
```
