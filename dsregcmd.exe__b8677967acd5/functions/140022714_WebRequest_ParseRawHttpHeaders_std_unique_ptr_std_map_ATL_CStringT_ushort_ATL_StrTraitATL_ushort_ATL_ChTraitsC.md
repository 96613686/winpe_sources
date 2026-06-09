# WebRequest::ParseRawHttpHeaders(std::unique_ptr<std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>,std::default_delete<std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x140022714`
- end: `0x140022990`
- name: `?ParseRawHttpHeaders@WebRequest@@SAXAEBV?$unique_ptr@V?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@U?$default_delete@V?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@@2@@std@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `636`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x140022998`
- `0x140022f3c`

## callees

- `0x140007bf8`
- `0x140008ce8`
- `0x140009228`
- `0x140009398`
- `0x140009470`
- `0x14000d310`
- `0x140014730`
- `0x140022714`
- `0x140030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall WebRequest::ParseRawHttpHeaders(__int64 *a1, __int64 *a2)
{
  __int64 result; // rax
  _QWORD *v5; // rax
  __int64 i; // rdx
  volatile signed __int32 *v7; // rdx
  volatile signed __int32 *v8; // rbx
  _QWORD *v9; // rax
  _QWORD *v10; // rdx
  _QWORD *v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rbx
  __int64 Lower; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // rax
  _QWORD *v18; // rdx
  _QWORD *v19; // rdx
  volatile signed __int32 *v20; // rdx
  __int64 v21; // [rsp+20h] [rbp-30h] BYREF
  __int64 v22; // [rsp+28h] [rbp-28h] BYREF
  __int64 v23; // [rsp+30h] [rbp-20h] BYREF
  __int64 v24; // [rsp+38h] [rbp-18h] BYREF
  __int64 v25; // [rsp+40h] [rbp-10h] BYREF
  __int64 v26; // [rsp+88h] [rbp+38h] BYREF
  int v27; // [rsp+90h] [rbp+40h] BYREF
  volatile signed __int32 *v28; // [rsp+98h] [rbp+48h] BYREF

  result = *a2;
  if ( *(_DWORD *)(*a2 - 16) )
  {
    v28 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    v27 = 0;
    v5 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                     a2,
                     &v26,
                     L"\r\n",
                     &v27);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(&v28, v5);
    for ( i = v26; ; i = v21 )
    {
      v7 = (volatile signed __int32 *)(i - 24);
      if ( _InterlockedDecrement(v7 + 4) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v7 + 8LL))(*(_QWORD *)v7);
      v8 = v28;
      if ( !*(_WORD *)v28 )
        break;
      v21 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      v22 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      LODWORD(v26) = 0;
      v9 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                       &v28,
                       &v24,
                       L":",
                       &v26);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        &v21,
        v9);
      v10 = (_QWORD *)(v24 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v24 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 8LL))(*v10);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
        &v28,
        &v23,
        (unsigned int)v26,
        (unsigned int)(*((_DWORD *)v8 - 4) - v26));
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        &v22,
        &v23);
      v11 = (_QWORD *)(v23 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v23 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 8LL))(*v11);
      v12 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::TrimRight(&v21);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::TrimLeft(v12);
      v13 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::TrimRight(&v22);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::TrimLeft(v13);
      if ( *(_DWORD *)(v21 - 16) )
      {
        v14 = *a1;
        Lower = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(&v21);
        v16 = (_QWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::operator[](
                          v14,
                          Lower);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
          v16,
          &v22);
      }
      v17 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                        a2,
                        &v25,
                        L"\r\n",
                        &v27);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        &v28,
        v17);
      v18 = (_QWORD *)(v25 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v25 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 8LL))(*v18);
      v19 = (_QWORD *)(v22 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v22 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v19 + 8LL))(*v19);
    }
    v20 = v28 - 6;
    result = (unsigned int)_InterlockedDecrement(v28 - 2);
    if ( (int)result <= 0 )
      return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v20 + 8LL))(*(_QWORD *)v20);
  }
  return result;
}

```

## disassembly

```asm
0x140022714  push    rbp
0x140022716  push    rbx
0x140022717  push    rsi
0x140022718  push    rdi
0x140022719  push    r15
0x14002271b  mov     rbp, rsp
0x14002271e  sub     rsp, 50h
0x140022722  mov     rdi, rdx
0x140022725  mov     rsi, rcx
0x140022728  mov     rax, [rdx]
0x14002272b  cmp     dword ptr [rax-10h], 0
0x14002272f  jz      loc_140022985
0x140022735  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14002273c  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140022743  mov     rax, [rax+18h]
0x140022747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002274c  add     rax, 18h
0x140022750  mov     [rbp+arg_18], rax
0x140022754  mov     [rbp+arg_10], 0
0x14002275b  lea     r9, [rbp+arg_10]
0x14002275f  lea     r8, asc_140034428; "\r\n"
0x140022766  lea     rdx, [rbp+arg_8]
0x14002276a  mov     rcx, rdi
0x14002276d  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x140022772  nop
0x140022773  mov     rdx, rax
0x140022776  lea     rcx, [rbp+arg_18]
0x14002277a  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14002277f  nop
0x140022780  mov     rdx, [rbp+arg_8]
0x140022784  or      r15d, 0FFFFFFFFh
0x140022788  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14002278c  mov     eax, r15d
0x14002278f  lock xadd [rdx+10h], eax
0x140022794  add     eax, r15d
0x140022797  test    eax, eax
0x140022799  jg      short loc_1400227AB
0x14002279b  mov     rcx, [rdx]
0x14002279e  mov     rax, [rcx]
0x1400227a1  mov     rax, [rax+8]
0x1400227a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400227aa  nop
0x1400227ab  mov     rbx, [rbp+arg_18]
0x1400227af  xor     eax, eax
0x1400227b1  cmp     [rbx], ax
0x1400227b4  jz      loc_140022963
0x1400227ba  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400227c1  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400227c8  mov     rax, [rax+18h]
0x1400227cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400227d1  add     rax, 18h
0x1400227d5  mov     [rbp+var_30], rax
0x1400227d9  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400227e0  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400227e7  mov     rax, [rax+18h]
0x1400227eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400227f0  add     rax, 18h
0x1400227f4  mov     [rbp+var_28], rax
0x1400227f8  mov     dword ptr [rbp+arg_8], 0
0x1400227ff  lea     r9, [rbp+arg_8]
0x140022803  lea     r8, asc_1400374A4; ":"
0x14002280a  lea     rdx, [rbp+var_18]
0x14002280e  lea     rcx, [rbp+arg_18]
0x140022812  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x140022817  nop
0x140022818  mov     rdx, rax
0x14002281b  lea     rcx, [rbp+var_30]
0x14002281f  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140022824  nop
0x140022825  mov     rdx, [rbp+var_18]
0x140022829  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14002282d  mov     eax, r15d
0x140022830  lock xadd [rdx+10h], eax
0x140022835  add     eax, r15d
0x140022838  test    eax, eax
0x14002283a  jg      short loc_14002284B
0x14002283c  mov     rcx, [rdx]
0x14002283f  mov     rax, [rcx]
0x140022842  mov     rax, [rax+8]
0x140022846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002284b  mov     r8d, dword ptr [rbp+arg_8]
0x14002284f  mov     r9d, [rbx-10h]
0x140022853  sub     r9d, r8d
0x140022856  lea     rdx, [rbp+var_20]
0x14002285a  lea     rcx, [rbp+arg_18]
0x14002285e  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x140022863  nop
0x140022864  lea     rdx, [rbp+var_20]
0x140022868  lea     rcx, [rbp+var_28]
0x14002286c  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140022871  nop
0x140022872  mov     rdx, [rbp+var_20]
0x140022876  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14002287a  mov     eax, r15d
0x14002287d  lock xadd [rdx+10h], eax
0x140022882  add     eax, r15d
0x140022885  test    eax, eax
0x140022887  jg      short loc_140022898
0x140022889  mov     rcx, [rdx]
0x14002288c  mov     rax, [rcx]
0x14002288f  mov     rax, [rax+8]
0x140022893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022898  lea     rcx, [rbp+var_30]
0x14002289c  call    ?TrimRight@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::TrimRight(void)
0x1400228a1  mov     rcx, rax
0x1400228a4  call    ?TrimLeft@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::TrimLeft(void)
0x1400228a9  lea     rcx, [rbp+var_28]
0x1400228ad  call    ?TrimRight@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::TrimRight(void)
0x1400228b2  mov     rcx, rax
0x1400228b5  call    ?TrimLeft@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::TrimLeft(void)
0x1400228ba  mov     rax, [rbp+var_30]
0x1400228be  cmp     dword ptr [rax-10h], 0
0x1400228c2  jz      short loc_1400228E7
0x1400228c4  mov     rbx, [rsi]
0x1400228c7  lea     rcx, [rbp+var_30]
0x1400228cb  call    ?MakeLower@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::MakeLower(void)
0x1400228d0  mov     rdx, rax
0x1400228d3  mov     rcx, rbx
0x1400228d6  call    ??A?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@QEAAAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@$$QEAV23@@Z; std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::operator[](ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &&)
0x1400228db  mov     rcx, rax
0x1400228de  lea     rdx, [rbp+var_28]
0x1400228e2  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400228e7  lea     r9, [rbp+arg_10]
0x1400228eb  lea     r8, asc_140034428; "\r\n"
0x1400228f2  lea     rdx, [rbp+var_10]
0x1400228f6  mov     rcx, rdi
0x1400228f9  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x1400228fe  nop
0x1400228ff  mov     rdx, rax
0x140022902  lea     rcx, [rbp+arg_18]
0x140022906  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14002290b  nop
0x14002290c  mov     rdx, [rbp+var_10]
0x140022910  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140022914  mov     eax, r15d
0x140022917  lock xadd [rdx+10h], eax
0x14002291c  add     eax, r15d
0x14002291f  test    eax, eax
0x140022921  jg      short loc_140022933
0x140022923  mov     rcx, [rdx]
0x140022926  mov     rax, [rcx]
0x140022929  mov     rax, [rax+8]
0x14002292d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022932  nop
0x140022933  mov     rdx, [rbp+var_28]
0x140022937  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14002293b  mov     eax, r15d
0x14002293e  lock xadd [rdx+10h], eax
0x140022943  add     eax, r15d
0x140022946  test    eax, eax
0x140022948  jg      short loc_14002295A
0x14002294a  mov     rcx, [rdx]
0x14002294d  mov     rax, [rcx]
0x140022950  mov     rax, [rax+8]
0x140022954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022959  nop
0x14002295a  mov     rdx, [rbp+var_30]
0x14002295e  jmp     loc_140022788
0x140022963  lea     rdx, [rbx-18h]
0x140022967  mov     eax, r15d
0x14002296a  lock xadd [rdx+10h], eax
0x14002296f  add     eax, r15d
0x140022972  test    eax, eax
0x140022974  jg      short loc_140022985
0x140022976  mov     rcx, [rdx]
0x140022979  mov     rax, [rcx]
0x14002297c  mov     rax, [rax+8]
0x140022980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022985  add     rsp, 50h
0x140022989  pop     r15
0x14002298b  pop     rdi
0x14002298c  pop     rsi
0x14002298d  pop     rbx
0x14002298e  pop     rbp
0x14002298f  retn
```
