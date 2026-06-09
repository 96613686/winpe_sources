# ATL::CComObject<CGameStatistics>::`scalar deleting destructor'(uint)

- ea: `0x1800026d0`
- end: `0x1800026ff`
- name: `??_G?$CComObject@VCGameStatistics@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000125c`
- `0x1800025fc`
- `0x1800026d0`

## pseudocode

```c
void *__fastcall ATL::CComObject<CGameStatistics>::`scalar deleting destructor'(void *Block, char a2)
{
  ATL::CComObject<CGameStatistics>::~CComObject<CGameStatistics>();
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800026d0  mov     [rsp+arg_0], rbx
0x1800026d5  push    rdi
0x1800026d6  sub     rsp, 20h
0x1800026da  mov     ebx, edx
0x1800026dc  mov     rdi, rcx
0x1800026df  call    ??1?$CComObject@VCGameStatistics@@@ATL@@UEAA@XZ; ATL::CComObject<CGameStatistics>::~CComObject<CGameStatistics>(void)
0x1800026e4  test    bl, 1
0x1800026e7  jz      short loc_1800026F1
0x1800026e9  mov     rcx, rdi; Block
0x1800026ec  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800026f1  mov     rbx, [rsp+28h+arg_0]
0x1800026f6  mov     rax, rdi
0x1800026f9  add     rsp, 20h
0x1800026fd  pop     rdi
0x1800026fe  retn
```
