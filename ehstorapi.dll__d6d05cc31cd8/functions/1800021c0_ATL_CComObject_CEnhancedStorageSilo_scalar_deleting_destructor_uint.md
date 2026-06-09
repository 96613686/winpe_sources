# ATL::CComObject<CEnhancedStorageSilo>::`scalar deleting destructor'(uint)

- ea: `0x1800021c0`
- end: `0x1800021ef`
- name: `??_G?$CComObject@VCEnhancedStorageSilo@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001240`
- `0x1800020e8`
- `0x1800021c0`

## pseudocode

```c
CEnhancedStorageSilo *__fastcall ATL::CComObject<CEnhancedStorageSilo>::`scalar deleting destructor'(
        CEnhancedStorageSilo *Block,
        char a2)
{
  ATL::CComObject<CEnhancedStorageSilo>::~CComObject<CEnhancedStorageSilo>(Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800021c0  mov     [rsp+arg_0], rbx
0x1800021c5  push    rdi
0x1800021c6  sub     rsp, 20h
0x1800021ca  mov     ebx, edx
0x1800021cc  mov     rdi, rcx
0x1800021cf  call    ??1?$CComObject@VCEnhancedStorageSilo@@@ATL@@UEAA@XZ; ATL::CComObject<CEnhancedStorageSilo>::~CComObject<CEnhancedStorageSilo>(void)
0x1800021d4  test    bl, 1
0x1800021d7  jz      short loc_1800021E1
0x1800021d9  mov     rcx, rdi; Block
0x1800021dc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800021e1  mov     rbx, [rsp+28h+arg_0]
0x1800021e6  mov     rax, rdi
0x1800021e9  add     rsp, 20h
0x1800021ed  pop     rdi
0x1800021ee  retn
```
