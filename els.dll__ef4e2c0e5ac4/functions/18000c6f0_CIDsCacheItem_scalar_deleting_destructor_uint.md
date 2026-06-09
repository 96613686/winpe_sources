# CIDsCacheItem::`scalar deleting destructor'(uint)

- ea: `0x18000c6f0`
- end: `0x18000c720`
- name: `??_GCIDsCacheItem@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(CIDsCacheItem *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x18000c628`
- `0x18000c6f0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000c70c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c70c`

## pseudocode

```c
CIDsCacheItem *__fastcall CIDsCacheItem::`scalar deleting destructor'(CIDsCacheItem *this, char a2)
{
  CIDsCacheItem::~CIDsCacheItem(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000c6f0  mov     [rsp+arg_0], rbx
0x18000c6f5  push    rdi
0x18000c6f6  sub     rsp, 20h
0x18000c6fa  mov     ebx, edx
0x18000c6fc  mov     rdi, rcx
0x18000c6ff  call    ??1CIDsCacheItem@@UEAA@XZ; CIDsCacheItem::~CIDsCacheItem(void)
0x18000c704  test    bl, 1
0x18000c707  jz      short loc_18000C712
0x18000c709  mov     rcx, rdi
0x18000c70c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c712  mov     rbx, [rsp+28h+arg_0]
0x18000c717  mov     rax, rdi
0x18000c71a  add     rsp, 20h
0x18000c71e  pop     rdi
0x18000c71f  retn
```
