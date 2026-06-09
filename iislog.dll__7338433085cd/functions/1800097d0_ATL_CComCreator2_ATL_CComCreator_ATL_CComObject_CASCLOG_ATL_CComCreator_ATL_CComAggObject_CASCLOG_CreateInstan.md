# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CASCLOG>>,ATL::CComCreator<ATL::CComAggObject<CASCLOG>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800097d0`
- end: `0x18000992e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCASCLOG@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCASCLOG@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `350`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001008`
- `0x180001048`
- `0x1800097d0`
- `0x18000bed8`
- `0x18000bf30`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CASCLOG>>,ATL::CComCreator<ATL::CComAggObject<CASCLOG>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // ebx
  CASCLOG *v7; // rax
  CASCLOG *v8; // rdi
  char *v9; // rax
  _QWORD *v10; // rdi

  if ( a1 )
  {
    if ( !a3 )
      return (unsigned int)-2147467261;
    *a3 = 0;
    v6 = -2147024882;
    v9 = (char *)operator new(0xA70u);
    v10 = v9;
    if ( v9 )
    {
      *((_DWORD *)v9 + 2) = 0;
      *(_QWORD *)v9 = &ATL::CComAggObject<CASCLOG>::`vftable';
      CASCLOG::CASCLOG((CASCLOG *)(v9 + 24));
      v10[4] = a1;
      v10[3] = &ATL::CComContainedObject<CASCLOG>::`vftable'{for `CLogFileCtrl'};
      v10[54] = &ATL::CComContainedObject<CASCLOG>::`vftable'{for `CLogScript'};
      _InterlockedIncrement(&dword_180017A78);
      v6 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v10)(v10, a2, a3);
      if ( v6 )
      {
        *v10 = &ATL::CComAggObject<CASCLOG>::`vftable';
        *((_DWORD *)v10 + 2) = 1;
        _InterlockedDecrement(&dword_180017A78);
        CASCLOG::~CASCLOG((CASCLOG *)(v10 + 3));
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
    v7 = (CASCLOG *)operator new(0xA58u);
    v8 = v7;
    if ( v7 )
    {
      CASCLOG::CASCLOG(v7);
      *(_QWORD *)v8 = &ATL::CComObject<CASCLOG>::`vftable'{for `CLogFileCtrl'};
      *((_QWORD *)v8 + 51) = &ATL::CComObject<CASCLOG>::`vftable'{for `CLogScript'};
      _InterlockedIncrement(&dword_180017A78);
      v6 = (**(__int64 (__fastcall ***)(CASCLOG *, __int64, _QWORD *))v8)(v8, a2, a3);
      if ( v6 )
        (*(void (__fastcall **)(CASCLOG *, __int64))(*(_QWORD *)v8 + 80LL))(v8, 1);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800097d0  push    rbx
0x1800097d2  push    rbp
0x1800097d3  push    rsi
0x1800097d4  push    rdi
0x1800097d5  push    r12
0x1800097d7  push    r14
0x1800097d9  sub     rsp, 28h
0x1800097dd  mov     rsi, r8
0x1800097e0  mov     r14, rdx
0x1800097e3  mov     rbp, rcx
0x1800097e6  test    rcx, rcx
0x1800097e9  jnz     loc_18000987E
0x1800097ef  test    r8, r8
0x1800097f2  jnz     short loc_1800097FE
0x1800097f4  mov     ebx, 80004003h
0x1800097f9  jmp     loc_18000991F
0x1800097fe  mov     ecx, 0A58h; Size
0x180009803  mov     qword ptr [r8], 0
0x18000980a  mov     ebx, 8007000Eh
0x18000980f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009814  mov     rdi, rax
0x180009817  test    rax, rax
0x18000981a  jz      loc_18000991F
0x180009820  mov     rcx, rax; this
0x180009823  call    ??0CASCLOG@@QEAA@XZ; CASCLOG::CASCLOG(void)
0x180009828  lea     rax, ??_7?$CComObject@VCASCLOG@@@ATL@@6BCLogFileCtrl@@@; const ATL::CComObject<CASCLOG>::`vftable'{for `CLogFileCtrl'}
0x18000982f  mov     [rdi], rax
0x180009832  lea     rax, ??_7?$CComObject@VCASCLOG@@@ATL@@6BCLogScript@@@; const ATL::CComObject<CASCLOG>::`vftable'{for `CLogScript'}
0x180009839  mov     [rdi+198h], rax
0x180009840  lock inc cs:dword_180017A78
0x180009847  mov     rcx, [rdi]
0x18000984a  mov     r8, rsi
0x18000984d  mov     rdx, r14
0x180009850  mov     rax, [rcx]
0x180009853  mov     rcx, rdi
0x180009856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000985b  mov     ebx, eax
0x18000985d  test    eax, eax
0x18000985f  jz      loc_18000991F
0x180009865  mov     rax, [rdi]
0x180009868  mov     edx, 1
0x18000986d  mov     rcx, rdi
0x180009870  mov     rax, [rax+50h]
0x180009874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009879  jmp     loc_18000991F
0x18000987e  test    rsi, rsi
0x180009881  jz      loc_1800097F4
0x180009887  mov     ecx, 0A70h; Size
0x18000988c  mov     qword ptr [r8], 0
0x180009893  mov     ebx, 8007000Eh
0x180009898  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000989d  mov     rdi, rax
0x1800098a0  test    rax, rax
0x1800098a3  jz      short loc_18000991F
0x1800098a5  lea     r12, ??_7?$CComAggObject@VCASCLOG@@@ATL@@6B@; const ATL::CComAggObject<CASCLOG>::`vftable'
0x1800098ac  mov     dword ptr [rax+8], 0
0x1800098b3  lea     rcx, [rax+18h]; this
0x1800098b7  mov     [rax], r12
0x1800098ba  call    ??0CASCLOG@@QEAA@XZ; CASCLOG::CASCLOG(void)
0x1800098bf  lea     rax, ??_7?$CComContainedObject@VCASCLOG@@@ATL@@6BCLogFileCtrl@@@; const ATL::CComContainedObject<CASCLOG>::`vftable'{for `CLogFileCtrl'}
0x1800098c6  mov     [rdi+20h], rbp
0x1800098ca  mov     [rdi+18h], rax
0x1800098ce  lea     rax, ??_7?$CComContainedObject@VCASCLOG@@@ATL@@6BCLogScript@@@; const ATL::CComContainedObject<CASCLOG>::`vftable'{for `CLogScript'}
0x1800098d5  mov     [rdi+1B0h], rax
0x1800098dc  lock inc cs:dword_180017A78
0x1800098e3  mov     rax, [rdi]
0x1800098e6  mov     r8, rsi
0x1800098e9  mov     rdx, r14
0x1800098ec  mov     rcx, rdi
0x1800098ef  mov     rax, [rax]
0x1800098f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098f7  mov     ebx, eax
0x1800098f9  test    eax, eax
0x1800098fb  jz      short loc_18000991F
0x1800098fd  mov     [rdi], r12
0x180009900  lea     rcx, [rdi+18h]; this
0x180009904  mov     dword ptr [rdi+8], 1
0x18000990b  lock dec cs:dword_180017A78
0x180009912  call    ??1CASCLOG@@MEAA@XZ; CASCLOG::~CASCLOG(void)
0x180009917  mov     rcx, rdi; Block
0x18000991a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000991f  mov     eax, ebx
0x180009921  add     rsp, 28h
0x180009925  pop     r14
0x180009927  pop     r12
0x180009929  pop     rdi
0x18000992a  pop     rsi
0x18000992b  pop     rbp
0x18000992c  pop     rbx
0x18000992d  retn
```
