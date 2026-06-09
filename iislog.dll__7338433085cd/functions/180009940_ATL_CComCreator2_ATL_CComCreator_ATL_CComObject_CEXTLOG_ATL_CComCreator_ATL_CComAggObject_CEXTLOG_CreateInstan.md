# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CEXTLOG>>,ATL::CComCreator<ATL::CComAggObject<CEXTLOG>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180009940`
- end: `0x180009a9e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCEXTLOG@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCEXTLOG@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `350`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001008`
- `0x180001048`
- `0x18000373c`
- `0x180003984`
- `0x180009940`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CEXTLOG>>,ATL::CComCreator<ATL::CComAggObject<CEXTLOG>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // ebx
  CEXTLOG *v7; // rax
  CEXTLOG *v8; // rdi
  char *v9; // rax
  _QWORD *v10; // rdi

  if ( a1 )
  {
    if ( !a3 )
      return (unsigned int)-2147467261;
    *a3 = 0;
    v6 = -2147024882;
    v9 = (char *)operator new(0xD28u);
    v10 = v9;
    if ( v9 )
    {
      *((_DWORD *)v9 + 2) = 0;
      *(_QWORD *)v9 = &ATL::CComAggObject<CEXTLOG>::`vftable';
      CEXTLOG::CEXTLOG((CEXTLOG *)(v9 + 24));
      v10[4] = a1;
      v10[3] = &ATL::CComContainedObject<CEXTLOG>::`vftable'{for `CLogFileCtrl'};
      v10[54] = &ATL::CComContainedObject<CEXTLOG>::`vftable'{for `CLogScript'};
      _InterlockedIncrement(&dword_180017A78);
      v6 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v10)(v10, a2, a3);
      if ( v6 )
      {
        *v10 = &ATL::CComAggObject<CEXTLOG>::`vftable';
        *((_DWORD *)v10 + 2) = 1;
        _InterlockedDecrement(&dword_180017A78);
        CEXTLOG::~CEXTLOG((CEXTLOG *)(v10 + 3));
        operator delete(v10);
      }
    }
  }
  else
  {
    if ( !a3 )
      return (unsigned int)-2147467261;
    *a3 = 0;
    v6 = -2147024882;
    v7 = (CEXTLOG *)operator new(0xD10u);
    v8 = v7;
    if ( v7 )
    {
      CEXTLOG::CEXTLOG(v7);
      *(_QWORD *)v8 = &ATL::CComObject<CEXTLOG>::`vftable'{for `CLogFileCtrl'};
      *((_QWORD *)v8 + 51) = &ATL::CComObject<CEXTLOG>::`vftable'{for `CLogScript'};
      _InterlockedIncrement(&dword_180017A78);
      v6 = (**(__int64 (__fastcall ***)(CEXTLOG *, __int64, _QWORD *))v8)(v8, a2, a3);
      if ( v6 )
        (*(void (__fastcall **)(CEXTLOG *, __int64))(*(_QWORD *)v8 + 80LL))(v8, 1);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180009940  push    rbx
0x180009942  push    rbp
0x180009943  push    rsi
0x180009944  push    rdi
0x180009945  push    r12
0x180009947  push    r14
0x180009949  sub     rsp, 28h
0x18000994d  mov     rsi, r8
0x180009950  mov     r14, rdx
0x180009953  mov     rbp, rcx
0x180009956  test    rcx, rcx
0x180009959  jnz     loc_1800099EE
0x18000995f  test    r8, r8
0x180009962  jnz     short loc_18000996E
0x180009964  mov     ebx, 80004003h
0x180009969  jmp     loc_180009A8F
0x18000996e  mov     ecx, 0D10h; Size
0x180009973  mov     qword ptr [r8], 0
0x18000997a  mov     ebx, 8007000Eh
0x18000997f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009984  mov     rdi, rax
0x180009987  test    rax, rax
0x18000998a  jz      loc_180009A8F
0x180009990  mov     rcx, rax; this
0x180009993  call    ??0CEXTLOG@@QEAA@XZ; CEXTLOG::CEXTLOG(void)
0x180009998  lea     rax, ??_7?$CComObject@VCEXTLOG@@@ATL@@6BCLogFileCtrl@@@; const ATL::CComObject<CEXTLOG>::`vftable'{for `CLogFileCtrl'}
0x18000999f  mov     [rdi], rax
0x1800099a2  lea     rax, ??_7?$CComObject@VCEXTLOG@@@ATL@@6BCLogScript@@@; const ATL::CComObject<CEXTLOG>::`vftable'{for `CLogScript'}
0x1800099a9  mov     [rdi+198h], rax
0x1800099b0  lock inc cs:dword_180017A78
0x1800099b7  mov     rcx, [rdi]
0x1800099ba  mov     r8, rsi
0x1800099bd  mov     rdx, r14
0x1800099c0  mov     rax, [rcx]
0x1800099c3  mov     rcx, rdi
0x1800099c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099cb  mov     ebx, eax
0x1800099cd  test    eax, eax
0x1800099cf  jz      loc_180009A8F
0x1800099d5  mov     rax, [rdi]
0x1800099d8  mov     edx, 1
0x1800099dd  mov     rcx, rdi
0x1800099e0  mov     rax, [rax+50h]
0x1800099e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099e9  jmp     loc_180009A8F
0x1800099ee  test    rsi, rsi
0x1800099f1  jz      loc_180009964
0x1800099f7  mov     ecx, 0D28h; Size
0x1800099fc  mov     qword ptr [r8], 0
0x180009a03  mov     ebx, 8007000Eh
0x180009a08  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009a0d  mov     rdi, rax
0x180009a10  test    rax, rax
0x180009a13  jz      short loc_180009A8F
0x180009a15  lea     r12, ??_7?$CComAggObject@VCEXTLOG@@@ATL@@6B@; const ATL::CComAggObject<CEXTLOG>::`vftable'
0x180009a1c  mov     dword ptr [rax+8], 0
0x180009a23  lea     rcx, [rax+18h]; this
0x180009a27  mov     [rax], r12
0x180009a2a  call    ??0CEXTLOG@@QEAA@XZ; CEXTLOG::CEXTLOG(void)
0x180009a2f  lea     rax, ??_7?$CComContainedObject@VCEXTLOG@@@ATL@@6BCLogFileCtrl@@@; const ATL::CComContainedObject<CEXTLOG>::`vftable'{for `CLogFileCtrl'}
0x180009a36  mov     [rdi+20h], rbp
0x180009a3a  mov     [rdi+18h], rax
0x180009a3e  lea     rax, ??_7?$CComContainedObject@VCEXTLOG@@@ATL@@6BCLogScript@@@; const ATL::CComContainedObject<CEXTLOG>::`vftable'{for `CLogScript'}
0x180009a45  mov     [rdi+1B0h], rax
0x180009a4c  lock inc cs:dword_180017A78
0x180009a53  mov     rax, [rdi]
0x180009a56  mov     r8, rsi
0x180009a59  mov     rdx, r14
0x180009a5c  mov     rcx, rdi
0x180009a5f  mov     rax, [rax]
0x180009a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a67  mov     ebx, eax
0x180009a69  test    eax, eax
0x180009a6b  jz      short loc_180009A8F
0x180009a6d  mov     [rdi], r12
0x180009a70  lea     rcx, [rdi+18h]; this
0x180009a74  mov     dword ptr [rdi+8], 1
0x180009a7b  lock dec cs:dword_180017A78
0x180009a82  call    ??1CEXTLOG@@MEAA@XZ; CEXTLOG::~CEXTLOG(void)
0x180009a87  mov     rcx, rdi; Block
0x180009a8a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009a8f  mov     eax, ebx
0x180009a91  add     rsp, 28h
0x180009a95  pop     r14
0x180009a97  pop     r12
0x180009a99  pop     rdi
0x180009a9a  pop     rsi
0x180009a9b  pop     rbp
0x180009a9c  pop     rbx
0x180009a9d  retn
```
