# CHashTable<CTagEntry *>::`scalar deleting destructor'(uint)

- ea: `0x1800217f0`
- end: `0x180021824`
- name: `??_G?$CHashTable@PEAVCTagEntry@@@@UEAAPEAXI@Z`
- size: `52`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x180011ef4`
- `0x180014544`
- `0x1800217f0`

## pseudocode

```c
_QWORD *__fastcall CHashTable<CTagEntry *>::`scalar deleting destructor'(_QWORD *Block, char a2)
{
  CHashTable<CTagEntry *>::~CHashTable<CTagEntry *>(Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800217f0  mov     [rsp+arg_0], rbx
0x1800217f5  push    rdi
0x1800217f6  sub     rsp, 20h
0x1800217fa  mov     ebx, edx
0x1800217fc  mov     rdi, rcx
0x1800217ff  call    ??1?$CHashTable@PEAVCTagEntry@@@@UEAA@XZ; CHashTable<CTagEntry *>::~CHashTable<CTagEntry *>(void)
0x180021804  test    bl, 1
0x180021807  jz      short loc_180021816
0x180021809  mov     edx, 640h
0x18002180e  mov     rcx, rdi; Block
0x180021811  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180021816  mov     rbx, [rsp+28h+arg_0]
0x18002181b  mov     rax, rdi
0x18002181e  add     rsp, 20h
0x180021822  pop     rdi
0x180021823  retn
```
