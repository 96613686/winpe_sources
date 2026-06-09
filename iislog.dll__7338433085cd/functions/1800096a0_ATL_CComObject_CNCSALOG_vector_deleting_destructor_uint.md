# ATL::CComObject<CNCSALOG>::`vector deleting destructor'(uint)

- ea: `0x1800096a0`
- end: `0x1800096f5`
- name: `??_E?$CComObject@VCNCSALOG@@@ATL@@UEAAPEAXI@Z`
- size: `85`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009580`

## callees

- `0x180001048`
- `0x1800075f4`
- `0x1800096a0`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<CNCSALOG>::`vector deleting destructor'(_DWORD *Block, char a2)
{
  Block[2] = 1;
  *(_QWORD *)Block = &ATL::CComObject<CNCSALOG>::`vftable'{for `CLogFileCtrl'};
  *((_QWORD *)Block + 51) = &ATL::CComObject<CNCSALOG>::`vftable'{for `CLogScript'};
  _InterlockedDecrement(&dword_180017A78);
  CNCSALOG::~CNCSALOG((CNCSALOG *)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800096a0  mov     [rsp+arg_0], rbx
0x1800096a5  push    rdi
0x1800096a6  sub     rsp, 20h
0x1800096aa  lea     rax, ??_7?$CComObject@VCNCSALOG@@@ATL@@6BCLogFileCtrl@@@; const ATL::CComObject<CNCSALOG>::`vftable'{for `CLogFileCtrl'}
0x1800096b1  mov     dword ptr [rcx+8], 1
0x1800096b8  mov     [rcx], rax
0x1800096bb  mov     ebx, edx
0x1800096bd  lea     rax, ??_7?$CComObject@VCNCSALOG@@@ATL@@6BCLogScript@@@; const ATL::CComObject<CNCSALOG>::`vftable'{for `CLogScript'}
0x1800096c4  mov     rdi, rcx
0x1800096c7  mov     [rcx+198h], rax
0x1800096ce  lock dec cs:dword_180017A78
0x1800096d5  call    ??1CNCSALOG@@MEAA@XZ; CNCSALOG::~CNCSALOG(void)
0x1800096da  test    bl, 1
0x1800096dd  jz      short loc_1800096E7
0x1800096df  mov     rcx, rdi; Block
0x1800096e2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800096e7  mov     rbx, [rsp+28h+arg_0]
0x1800096ec  mov     rax, rdi
0x1800096ef  add     rsp, 20h
0x1800096f3  pop     rdi
0x1800096f4  retn
```
