# ATL::CComCreator<ATL::CComObject<CRasDiagHelper>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800063dc`
- end: `0x1800065cf`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCRasDiagHelper@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `499`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800063b0`

## callees

- `0x1800011dc`
- `0x18000447c`
- `0x1800063dc`
- `0x18000b824`
- `0x18000ded2`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CRasDiagHelper>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v6; // esi
  char *v7; // rax
  char *v8; // rbx
  signed __int32 v9; // eax
  int v10; // ecx
  int v11; // eax
  signed __int32 v12; // eax
  char *v15; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = (char *)operator new(0x4C0u);
    v8 = v7;
    if ( v7 )
    {
      *((_DWORD *)v7 + 14) = 0;
      *((_OWORD *)v7 + 4) = 0;
      *((_OWORD *)v7 + 5) = 0;
      *((_QWORD *)v7 + 12) = 0;
      v7[104] = 0;
      *(_QWORD *)v7 = &CNetDiagHelperImpl::`vftable'{for `INetDiagHelper'};
      *((_QWORD *)v7 + 1) = &CNetDiagHelperImpl::`vftable'{for `INetDiagHelperInfo'};
      *(_QWORD *)(v7 + 20) = 0;
      *((_QWORD *)v7 + 4) = 0;
      *((_DWORD *)v7 + 4) = 0;
      *((_DWORD *)v7 + 32) = -1;
      *((_DWORD *)v7 + 33) = 0;
      *((_DWORD *)v7 + 293) = 0;
      v7[1176] = 0;
      *((_QWORD *)v7 + 148) = 0;
      CRasLogger::CRasLogger((LPVOID *)v7 + 151);
      memset_0(v8 + 136, 0, 0x202u);
      memset_0(v8 + 650, 0, 0x20Au);
      *(_OWORD *)(v8 + 1192) = 0;
      *(_QWORD *)v8 = &ATL::CComObject<CRasDiagHelper>::`vftable'{for `INetDiagHelper'};
      *((_QWORD *)v8 + 1) = &ATL::CComObject<CRasDiagHelper>::`vftable'{for `INetDiagHelperInfo'};
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v15 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v15;
  }
  if ( v8 )
  {
    do
      v9 = *((_DWORD *)v8 + 14);
    while ( v9 != 0x7FFFFFFF && v9 != _InterlockedCompareExchange((volatile signed __int32 *)v8 + 14, v9 + 1, v9) );
    v10 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 64));
    if ( v10 >= 0 )
      v8[104] = 1;
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v6 = 0;
    if ( v11 < 0 )
      v6 = v11;
    do
      v12 = *((_DWORD *)v8 + 14);
    while ( v12 != 0x7FFFFFFF && v12 != _InterlockedCompareExchange((volatile signed __int32 *)v8 + 14, v12 - 1, v12) );
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(char *, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v8 + 168LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x1800063dc  mov     [rsp+arg_10], r8
0x1800063e1  mov     [rsp+arg_8], rdx
0x1800063e6  mov     [rsp+arg_0], rcx
0x1800063eb  push    rbx
0x1800063ec  push    rsi
0x1800063ed  push    r12
0x1800063ef  push    r14
0x1800063f1  push    r15
0x1800063f3  sub     rsp, 20h
0x1800063f7  mov     r14, r8
0x1800063fa  mov     r15, rdx
0x1800063fd  test    r8, r8
0x180006400  jnz     short loc_18000640C
0x180006402  mov     eax, 80004003h
0x180006407  jmp     loc_1800065C1
0x18000640c  mov     qword ptr [r8], 0
0x180006413  mov     esi, 8007000Eh
0x180006418  mov     dword ptr [rsp+48h+arg_0], esi
0x18000641c  mov     [rsp+48h+arg_18], 0
0x180006425  mov     ecx, 4C0h; Size
0x18000642a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000642f  mov     rbx, rax
0x180006432  test    rbx, rbx
0x180006435  jz      loc_180006518
0x18000643b  mov     dword ptr [rax+38h], 0
0x180006442  xorps   xmm0, xmm0
0x180006445  xor     eax, eax
0x180006447  movups  xmmword ptr [rbx+40h], xmm0
0x18000644b  movups  xmmword ptr [rbx+50h], xmm0
0x18000644f  mov     [rbx+60h], rax
0x180006453  mov     [rbx+68h], al
0x180006456  lea     rax, ??_7CNetDiagHelperImpl@@6BINetDiagHelper@@@; const CNetDiagHelperImpl::`vftable'{for `INetDiagHelper'}
0x18000645d  mov     [rbx], rax
0x180006460  lea     rax, ??_7CNetDiagHelperImpl@@6BINetDiagHelperInfo@@@; const CNetDiagHelperImpl::`vftable'{for `INetDiagHelperInfo'}
0x180006467  mov     [rbx+8], rax
0x18000646b  mov     qword ptr [rbx+14h], 0
0x180006473  mov     qword ptr [rbx+20h], 0
0x18000647b  mov     dword ptr [rbx+10h], 0
0x180006482  mov     dword ptr [rbx+80h], 0FFFFFFFFh
0x18000648c  mov     dword ptr [rbx+84h], 0
0x180006496  mov     dword ptr [rbx+494h], 0
0x1800064a0  mov     byte ptr [rbx+498h], 0
0x1800064a7  mov     qword ptr [rbx+4A0h], 0
0x1800064b2  lea     rcx, [rbx+4B8h]; ppv
0x1800064b9  call    ??0CRasLogger@@QEAA@XZ; CRasLogger::CRasLogger(void)
0x1800064be  lea     rcx, [rbx+88h]; void *
0x1800064c5  xor     edx, edx; Val
0x1800064c7  mov     r8d, 202h; Size
0x1800064cd  call    memset_0
0x1800064d2  lea     rcx, [rbx+28Ah]; void *
0x1800064d9  xor     edx, edx; Val
0x1800064db  mov     r8d, 20Ah; Size
0x1800064e1  call    memset_0
0x1800064e6  xorps   xmm0, xmm0
0x1800064e9  movups  xmmword ptr [rbx+4A8h], xmm0
0x1800064f0  lea     rax, ??_7?$CComObject@VCRasDiagHelper@@@ATL@@6BINetDiagHelper@@@; const ATL::CComObject<CRasDiagHelper>::`vftable'{for `INetDiagHelper'}
0x1800064f7  mov     [rbx], rax
0x1800064fa  lea     rax, ??_7?$CComObject@VCRasDiagHelper@@@ATL@@6BINetDiagHelperInfo@@@; const ATL::CComObject<CRasDiagHelper>::`vftable'{for `INetDiagHelperInfo'}
0x180006501  mov     [rbx+8], rax
0x180006505  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000650c  mov     rax, [rcx]
0x18000650f  mov     rax, [rax+8]
0x180006513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006518  mov     [rsp+48h+arg_18], rbx
0x18000651d  jmp     short loc_180006532
0x18000651f  mov     r14, [rsp+48h+arg_10]
0x180006524  mov     r15, [rsp+48h+arg_8]
0x180006529  mov     esi, dword ptr [rsp+48h+arg_0]
0x18000652d  mov     rbx, [rsp+48h+arg_18]
0x180006532  test    rbx, rbx
0x180006535  jz      loc_1800065BF
0x18000653b  mov     r12d, 7FFFFFFFh
0x180006541  jmp     short loc_18000654D
0x180006543  lea     ecx, [rax+1]
0x180006546  lock cmpxchg [rbx+38h], ecx
0x18000654b  jz      short loc_180006555
0x18000654d  mov     eax, [rbx+38h]
0x180006550  cmp     eax, r12d
0x180006553  jnz     short loc_180006543
0x180006555  lea     rcx, [rbx+40h]; this
0x180006559  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000655e  mov     ecx, eax
0x180006560  test    eax, eax
0x180006562  js      short loc_180006568
0x180006564  mov     byte ptr [rbx+68h], 1
0x180006568  xor     eax, eax
0x18000656a  test    ecx, ecx
0x18000656c  cmovs   eax, ecx
0x18000656f  xor     esi, esi
0x180006571  test    eax, eax
0x180006573  cmovs   esi, eax
0x180006576  jmp     short loc_180006582
0x180006578  lea     ecx, [rax-1]
0x18000657b  lock cmpxchg [rbx+38h], ecx
0x180006580  jz      short loc_18000658A
0x180006582  mov     eax, [rbx+38h]
0x180006585  cmp     eax, r12d
0x180006588  jnz     short loc_180006578
0x18000658a  test    esi, esi
0x18000658c  jnz     short loc_1800065A8
0x18000658e  mov     rax, [rbx]
0x180006591  mov     r8, r14
0x180006594  mov     rdx, r15
0x180006597  mov     rcx, rbx
0x18000659a  mov     rax, [rax]
0x18000659d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065a2  mov     esi, eax
0x1800065a4  test    eax, eax
0x1800065a6  jz      short loc_1800065BF
0x1800065a8  mov     r8, [rbx]
0x1800065ab  mov     edx, 1
0x1800065b0  mov     rcx, rbx
0x1800065b3  mov     rax, [r8+0A8h]
0x1800065ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065bf  mov     eax, esi
0x1800065c1  add     rsp, 20h
0x1800065c5  pop     r15
0x1800065c7  pop     r14
0x1800065c9  pop     r12
0x1800065cb  pop     rsi
0x1800065cc  pop     rbx
0x1800065cd  retn
```
