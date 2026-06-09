# ATL::CComAggObject<CGameExplorer>::`scalar deleting destructor'(uint)

- ea: `0x180001ce0`
- end: `0x180001d0f`
- name: `??_G?$CComAggObject@VCGameExplorer@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000125c`
- `0x180001be0`
- `0x180001ce0`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CGameExplorer>::`scalar deleting destructor'(void *Block, char a2)
{
  ATL::CComAggObject<CGameExplorer>::~CComAggObject<CGameExplorer>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180001ce0  mov     [rsp+arg_0], rbx
0x180001ce5  push    rdi
0x180001ce6  sub     rsp, 20h
0x180001cea  mov     ebx, edx
0x180001cec  mov     rdi, rcx
0x180001cef  call    ??1?$CComAggObject@VCGameExplorer@@@ATL@@UEAA@XZ; ATL::CComAggObject<CGameExplorer>::~CComAggObject<CGameExplorer>(void)
0x180001cf4  test    bl, 1
0x180001cf7  jz      short loc_180001D01
0x180001cf9  mov     rcx, rdi; Block
0x180001cfc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001d01  mov     rbx, [rsp+28h+arg_0]
0x180001d06  mov     rax, rdi
0x180001d09  add     rsp, 20h
0x180001d0d  pop     rdi
0x180001d0e  retn
```
