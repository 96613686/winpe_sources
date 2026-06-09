# ATL::CComObject<CEXTLOG>::`vector deleting destructor'(uint)

- ea: `0x180009640`
- end: `0x180009695`
- name: `??_E?$CComObject@VCEXTLOG@@@ATL@@UEAAPEAXI@Z`
- size: `85`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009560`

## callees

- `0x180001048`
- `0x180003984`
- `0x180009640`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<CEXTLOG>::`vector deleting destructor'(_DWORD *Block, char a2)
{
  Block[2] = 1;
  *(_QWORD *)Block = &ATL::CComObject<CEXTLOG>::`vftable'{for `CLogFileCtrl'};
  *((_QWORD *)Block + 51) = &ATL::CComObject<CEXTLOG>::`vftable'{for `CLogScript'};
  _InterlockedDecrement(&dword_180017A78);
  CEXTLOG::~CEXTLOG((CEXTLOG *)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180009640  mov     [rsp+arg_0], rbx
0x180009645  push    rdi
0x180009646  sub     rsp, 20h
0x18000964a  lea     rax, ??_7?$CComObject@VCEXTLOG@@@ATL@@6BCLogFileCtrl@@@; const ATL::CComObject<CEXTLOG>::`vftable'{for `CLogFileCtrl'}
0x180009651  mov     dword ptr [rcx+8], 1
0x180009658  mov     [rcx], rax
0x18000965b  mov     ebx, edx
0x18000965d  lea     rax, ??_7?$CComObject@VCEXTLOG@@@ATL@@6BCLogScript@@@; const ATL::CComObject<CEXTLOG>::`vftable'{for `CLogScript'}
0x180009664  mov     rdi, rcx
0x180009667  mov     [rcx+198h], rax
0x18000966e  lock dec cs:dword_180017A78
0x180009675  call    ??1CEXTLOG@@MEAA@XZ; CEXTLOG::~CEXTLOG(void)
0x18000967a  test    bl, 1
0x18000967d  jz      short loc_180009687
0x18000967f  mov     rcx, rdi; Block
0x180009682  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009687  mov     rbx, [rsp+28h+arg_0]
0x18000968c  mov     rax, rdi
0x18000968f  add     rsp, 20h
0x180009693  pop     rdi
0x180009694  retn
```
