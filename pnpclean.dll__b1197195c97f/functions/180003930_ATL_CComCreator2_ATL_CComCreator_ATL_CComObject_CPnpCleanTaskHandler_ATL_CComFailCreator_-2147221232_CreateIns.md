# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CPnpCleanTaskHandler>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003930`
- end: `0x180003a29`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCPnpCleanTaskHandler@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `249`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000116c`
- `0x180003930`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CPnpCleanTaskHandler>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // ebx
  _DWORD *v6; // rax
  _DWORD *v7; // rdi
  struct ATL::CAtlModule *v8; // rcx

  if ( a1 )
  {
    if ( a3 )
    {
      *a3 = 0;
      return (unsigned int)-2147221232;
    }
    return (unsigned int)-2147467261;
  }
  if ( !a3 )
    return (unsigned int)-2147467261;
  *a3 = 0;
  v5 = -2147024882;
  v6 = operator new(0x48u);
  v7 = v6;
  if ( v6 )
  {
    v6[14] = 0;
    *((_QWORD *)v6 + 1) = 0;
    v6[4] = 0;
    *((_QWORD *)v6 + 3) = -1;
    v6[8] = 1;
    v6[9] = 0;
    *((_QWORD *)v6 + 5) = 0;
    *((_QWORD *)v6 + 6) = 0;
    _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
    v8 = ATL::_pAtlModule;
    v6[16] = 0;
    *(_QWORD *)v6 = &ATL::CComObject<CPnpCleanTaskHandler>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v8 + 8LL))(v8);
    v5 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v7)(v7, a2, a3);
    if ( v5 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v7 + 56LL))(v7, 1);
  }
  return v5;
}

```

## disassembly

```asm
0x180003930  push    rbx
0x180003932  push    rbp
0x180003933  push    rsi
0x180003934  push    rdi
0x180003935  sub     rsp, 28h
0x180003939  mov     rsi, r8
0x18000393c  mov     rbp, rdx
0x18000393f  test    rcx, rcx
0x180003942  jnz     loc_180003A06
0x180003948  test    r8, r8
0x18000394b  jz      loc_180003A0B
0x180003951  mov     [r8], rcx
0x180003954  mov     ebx, 8007000Eh
0x180003959  mov     ecx, 48h ; 'H'; Size
0x18000395e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003963  mov     rdi, rax
0x180003966  test    rax, rax
0x180003969  jz      loc_180003A1E
0x18000396f  mov     dword ptr [rax+38h], 0
0x180003976  mov     qword ptr [rax+8], 0
0x18000397e  mov     dword ptr [rax+10h], 0
0x180003985  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x18000398d  mov     dword ptr [rax+20h], 1
0x180003994  mov     dword ptr [rax+24h], 0
0x18000399b  mov     qword ptr [rax+28h], 0
0x1800039a3  mov     qword ptr [rax+30h], 0
0x1800039ab  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x1800039b2  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800039b9  mov     dword ptr [rax+40h], 0
0x1800039c0  lea     rax, ??_7?$CComObject@VCPnpCleanTaskHandler@@@ATL@@6B@; const ATL::CComObject<CPnpCleanTaskHandler>::`vftable'
0x1800039c7  mov     [rdi], rax
0x1800039ca  mov     rax, [rcx]
0x1800039cd  mov     rax, [rax+8]
0x1800039d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039d6  mov     rax, [rdi]
0x1800039d9  mov     r8, rsi
0x1800039dc  mov     rdx, rbp
0x1800039df  mov     rcx, rdi
0x1800039e2  mov     rax, [rax]
0x1800039e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039ea  mov     ebx, eax
0x1800039ec  test    eax, eax
0x1800039ee  jz      short loc_180003A1E
0x1800039f0  mov     rcx, [rdi]
0x1800039f3  mov     edx, 1
0x1800039f8  mov     rax, [rcx+38h]
0x1800039fc  mov     rcx, rdi
0x1800039ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a04  jmp     short loc_180003A1E
0x180003a06  test    rsi, rsi
0x180003a09  jnz     short loc_180003A12
0x180003a0b  mov     ebx, 80004003h
0x180003a10  jmp     short loc_180003A1E
0x180003a12  mov     qword ptr [r8], 0
0x180003a19  mov     ebx, 80040110h
0x180003a1e  mov     eax, ebx
0x180003a20  add     rsp, 28h
0x180003a24  pop     rdi
0x180003a25  pop     rsi
0x180003a26  pop     rbp
0x180003a27  pop     rbx
0x180003a28  retn
```
