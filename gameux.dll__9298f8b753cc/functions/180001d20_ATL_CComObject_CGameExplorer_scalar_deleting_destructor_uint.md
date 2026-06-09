# ATL::CComObject<CGameExplorer>::`scalar deleting destructor'(uint)

- ea: `0x180001d20`
- end: `0x180001d4f`
- name: `??_G?$CComObject@VCGameExplorer@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000125c`
- `0x180001c38`
- `0x180001d20`

## pseudocode

```c
void *__fastcall ATL::CComObject<CGameExplorer>::`scalar deleting destructor'(void *Block, char a2)
{
  ATL::CComObject<CGameExplorer>::~CComObject<CGameExplorer>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180001d20  mov     [rsp+arg_0], rbx
0x180001d25  push    rdi
0x180001d26  sub     rsp, 20h
0x180001d2a  mov     ebx, edx
0x180001d2c  mov     rdi, rcx
0x180001d2f  call    ??1?$CComObject@VCGameExplorer@@@ATL@@UEAA@XZ; ATL::CComObject<CGameExplorer>::~CComObject<CGameExplorer>(void)
0x180001d34  test    bl, 1
0x180001d37  jz      short loc_180001D41
0x180001d39  mov     rcx, rdi; Block
0x180001d3c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001d41  mov     rbx, [rsp+28h+arg_0]
0x180001d46  mov     rax, rdi
0x180001d49  add     rsp, 20h
0x180001d4d  pop     rdi
0x180001d4e  retn
```
