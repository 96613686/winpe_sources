# ATL::CComAggObject<CGameStatisticsMgr>::`scalar deleting destructor'(uint)

- ea: `0x180002690`
- end: `0x1800026bf`
- name: `??_G?$CComAggObject@VCGameStatisticsMgr@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000125c`
- `0x1800025b8`
- `0x180002690`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CGameStatisticsMgr>::`scalar deleting destructor'(void *Block, char a2)
{
  ATL::CComAggObject<CGameStatisticsMgr>::~CComAggObject<CGameStatisticsMgr>();
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180002690  mov     [rsp+arg_0], rbx
0x180002695  push    rdi
0x180002696  sub     rsp, 20h
0x18000269a  mov     ebx, edx
0x18000269c  mov     rdi, rcx
0x18000269f  call    ??1?$CComAggObject@VCGameStatisticsMgr@@@ATL@@UEAA@XZ; ATL::CComAggObject<CGameStatisticsMgr>::~CComAggObject<CGameStatisticsMgr>(void)
0x1800026a4  test    bl, 1
0x1800026a7  jz      short loc_1800026B1
0x1800026a9  mov     rcx, rdi; Block
0x1800026ac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800026b1  mov     rbx, [rsp+28h+arg_0]
0x1800026b6  mov     rax, rdi
0x1800026b9  add     rsp, 20h
0x1800026bd  pop     rdi
0x1800026be  retn
```
