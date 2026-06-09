# ATL::CComObject<CGameStatisticsMgr>::`scalar deleting destructor'(uint)

- ea: `0x180002710`
- end: `0x18000273f`
- name: `??_G?$CComObject@VCGameStatisticsMgr@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000125c`
- `0x180002640`
- `0x180002710`

## pseudocode

```c
void *__fastcall ATL::CComObject<CGameStatisticsMgr>::`scalar deleting destructor'(void *Block, char a2)
{
  ATL::CComObject<CGameStatisticsMgr>::~CComObject<CGameStatisticsMgr>();
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180002710  mov     [rsp+arg_0], rbx
0x180002715  push    rdi
0x180002716  sub     rsp, 20h
0x18000271a  mov     ebx, edx
0x18000271c  mov     rdi, rcx
0x18000271f  call    ??1?$CComObject@VCGameStatisticsMgr@@@ATL@@UEAA@XZ; ATL::CComObject<CGameStatisticsMgr>::~CComObject<CGameStatisticsMgr>(void)
0x180002724  test    bl, 1
0x180002727  jz      short loc_180002731
0x180002729  mov     rcx, rdi; Block
0x18000272c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002731  mov     rbx, [rsp+28h+arg_0]
0x180002736  mov     rax, rdi
0x180002739  add     rsp, 20h
0x18000273d  pop     rdi
0x18000273e  retn
```
