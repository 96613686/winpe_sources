# ATL::CComObject<CASCLOG>::`scalar deleting destructor'(uint)

- ea: `0x1800095e0`
- end: `0x180009635`
- name: `??_G?$CComObject@VCASCLOG@@@ATL@@UEAAPEAXI@Z`
- size: `85`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009540`

## callees

- `0x180001048`
- `0x1800095e0`
- `0x18000bf30`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<CASCLOG>::`scalar deleting destructor'(_DWORD *Block, char a2)
{
  Block[2] = 1;
  *(_QWORD *)Block = &ATL::CComObject<CASCLOG>::`vftable'{for `CLogFileCtrl'};
  *((_QWORD *)Block + 51) = &ATL::CComObject<CASCLOG>::`vftable'{for `CLogScript'};
  _InterlockedDecrement(&dword_180017A78);
  CASCLOG::~CASCLOG((CASCLOG *)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800095e0  mov     [rsp+arg_0], rbx
0x1800095e5  push    rdi
0x1800095e6  sub     rsp, 20h
0x1800095ea  lea     rax, ??_7?$CComObject@VCASCLOG@@@ATL@@6BCLogFileCtrl@@@; const ATL::CComObject<CASCLOG>::`vftable'{for `CLogFileCtrl'}
0x1800095f1  mov     dword ptr [rcx+8], 1
0x1800095f8  mov     [rcx], rax
0x1800095fb  mov     ebx, edx
0x1800095fd  lea     rax, ??_7?$CComObject@VCASCLOG@@@ATL@@6BCLogScript@@@; const ATL::CComObject<CASCLOG>::`vftable'{for `CLogScript'}
0x180009604  mov     rdi, rcx
0x180009607  mov     [rcx+198h], rax
0x18000960e  lock dec cs:dword_180017A78
0x180009615  call    ??1CASCLOG@@MEAA@XZ; CASCLOG::~CASCLOG(void)
0x18000961a  test    bl, 1
0x18000961d  jz      short loc_180009627
0x18000961f  mov     rcx, rdi; Block
0x180009622  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009627  mov     rbx, [rsp+28h+arg_0]
0x18000962c  mov     rax, rdi
0x18000962f  add     rsp, 20h
0x180009633  pop     rdi
0x180009634  retn
```
