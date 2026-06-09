# ATL::CComObject<CEnhancedStorageSiloAction>::`vector deleting destructor'(uint)

- ea: `0x1800064f0`
- end: `0x18000651f`
- name: `??_E?$CComObject@VCEnhancedStorageSiloAction@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001240`
- `0x18000637c`
- `0x1800064f0`

## pseudocode

```c
CEnhancedStorageSiloAction *__fastcall ATL::CComObject<CEnhancedStorageSiloAction>::`vector deleting destructor'(
        CEnhancedStorageSiloAction *Block,
        char a2)
{
  ATL::CComObject<CEnhancedStorageSiloAction>::~CComObject<CEnhancedStorageSiloAction>(Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800064f0  mov     [rsp+arg_0], rbx
0x1800064f5  push    rdi
0x1800064f6  sub     rsp, 20h
0x1800064fa  mov     ebx, edx
0x1800064fc  mov     rdi, rcx
0x1800064ff  call    ??1?$CComObject@VCEnhancedStorageSiloAction@@@ATL@@UEAA@XZ; ATL::CComObject<CEnhancedStorageSiloAction>::~CComObject<CEnhancedStorageSiloAction>(void)
0x180006504  test    bl, 1
0x180006507  jz      short loc_180006511
0x180006509  mov     rcx, rdi; Block
0x18000650c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006511  mov     rbx, [rsp+28h+arg_0]
0x180006516  mov     rax, rdi
0x180006519  add     rsp, 20h
0x18000651d  pop     rdi
0x18000651e  retn
```
