# ATL::CComObject<CEnhancedStorageAct>::`vector deleting destructor'(uint)

- ea: `0x180004030`
- end: `0x18000405f`
- name: `??_E?$CComObject@VCEnhancedStorageAct@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001240`
- `0x180003e88`
- `0x180004030`

## pseudocode

```c
CEnhancedStorageAct *__fastcall ATL::CComObject<CEnhancedStorageAct>::`vector deleting destructor'(
        CEnhancedStorageAct *Block,
        char a2)
{
  ATL::CComObject<CEnhancedStorageAct>::~CComObject<CEnhancedStorageAct>(Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180004030  mov     [rsp+arg_0], rbx
0x180004035  push    rdi
0x180004036  sub     rsp, 20h
0x18000403a  mov     ebx, edx
0x18000403c  mov     rdi, rcx
0x18000403f  call    ??1?$CComObject@VCEnhancedStorageAct@@@ATL@@UEAA@XZ; ATL::CComObject<CEnhancedStorageAct>::~CComObject<CEnhancedStorageAct>(void)
0x180004044  test    bl, 1
0x180004047  jz      short loc_180004051
0x180004049  mov     rcx, rdi; Block
0x18000404c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004051  mov     rbx, [rsp+28h+arg_0]
0x180004056  mov     rax, rdi
0x180004059  add     rsp, 20h
0x18000405d  pop     rdi
0x18000405e  retn
```
