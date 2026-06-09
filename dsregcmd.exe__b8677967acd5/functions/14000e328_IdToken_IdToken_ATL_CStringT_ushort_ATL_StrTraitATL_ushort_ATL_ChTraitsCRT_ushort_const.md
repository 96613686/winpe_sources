# IdToken::IdToken(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x14000e328`
- end: `0x14000e53f`
- name: `??0IdToken@@QEAA@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `535`
- prototype: `IdToken *__fastcall(IdToken *this, const wchar_t **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140025110`

## callees

- `0x140007bf8`
- `0x14000e194`
- `0x14000e328`
- `0x14000e6a0`
- `0x14000e8cc`
- `0x14000ea0c`
- `0x140012850`
- `0x140030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14000e446`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14000e446`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
IdToken *__fastcall IdToken::IdToken(IdToken *this, const wchar_t **a2)
{
  int v4; // eax
  wchar_t *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rax
  _QWORD *v8; // rdx
  _QWORD *v9; // rdx
  __int128 v11; // [rsp+20h] [rbp-20h] BYREF
  __int64 v12; // [rsp+30h] [rbp-10h]
  __int64 v13; // [rsp+70h] [rbp+30h] BYREF
  __int64 v14; // [rsp+78h] [rbp+38h] BYREF

  *(_QWORD *)this = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 4) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 5) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 6) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 7) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 8) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 9) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v4 = *((_DWORD *)*a2 - 4);
  if ( v4 )
  {
    if ( v4 <= 0 || (v5 = wcschr(*a2, 0x7Bu)) == 0 || (unsigned int)(v5 - *a2) == -1 )
    {
      v13 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      IdToken::GetJwtPayload(v6, a2, &v13);
      v11 = 0;
      v12 = 0;
      StringUtility::Base64UrlDecode(&v13, &v11);
      v7 = StringUtility::DecodeBytes<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(
             &v14,
             v11,
             (unsigned int)(DWORD2(v11) - v11));
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        this,
        v7);
      v8 = (_QWORD *)(v14 - 24);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v14 - 24 + 16), 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 8LL))(*v8);
      std::vector<unsigned char>::~vector<unsigned char>(&v11);
      v9 = (_QWORD *)(v13 - 24);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v13 - 24 + 16), 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 8LL))(*v9);
    }
    else
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        this,
        a2);
    }
    IdToken::ParseIdTokenPayload(this);
  }
  return this;
}

```

## disassembly

```asm
0x14000e328  mov     [rsp-18h+arg_8], rbx
0x14000e32d  mov     [rsp-18h+arg_0], rcx
0x14000e332  push    rbp
0x14000e333  push    rdi
0x14000e334  push    r15
0x14000e336  mov     rbp, rsp
0x14000e339  sub     rsp, 40h
0x14000e33d  mov     rdi, rdx
0x14000e340  mov     rbx, rcx
0x14000e343  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000e34a  lea     r15, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000e351  mov     rcx, r15
0x14000e354  mov     rax, [rax+18h]
0x14000e358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e35d  add     rax, 18h
0x14000e361  mov     [rbx], rax
0x14000e364  mov     qword ptr [rbx+8], 0
0x14000e36c  mov     qword ptr [rbx+10h], 0
0x14000e374  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000e37b  mov     rcx, r15
0x14000e37e  mov     rax, [rax+18h]
0x14000e382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e387  add     rax, 18h
0x14000e38b  mov     [rbx+18h], rax
0x14000e38f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000e396  mov     rcx, r15
0x14000e399  mov     rax, [rax+18h]
0x14000e39d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e3a2  add     rax, 18h
0x14000e3a6  mov     [rbx+20h], rax
0x14000e3aa  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000e3b1  mov     rcx, r15
0x14000e3b4  mov     rax, [rax+18h]
0x14000e3b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e3bd  add     rax, 18h
0x14000e3c1  mov     [rbx+28h], rax
0x14000e3c5  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000e3cc  mov     rcx, r15
0x14000e3cf  mov     rax, [rax+18h]
0x14000e3d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e3d8  add     rax, 18h
0x14000e3dc  mov     [rbx+30h], rax
0x14000e3e0  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000e3e7  mov     rcx, r15
0x14000e3ea  mov     rax, [rax+18h]
0x14000e3ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e3f3  add     rax, 18h
0x14000e3f7  mov     [rbx+38h], rax
0x14000e3fb  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000e402  mov     rcx, r15
0x14000e405  mov     rax, [rax+18h]
0x14000e409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e40e  add     rax, 18h
0x14000e412  mov     [rbx+40h], rax
0x14000e416  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000e41d  mov     rcx, r15
0x14000e420  mov     rax, [rax+18h]
0x14000e424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e429  add     rax, 18h
0x14000e42d  mov     [rbx+48h], rax
0x14000e431  mov     rcx, [rdi]; Str
0x14000e434  mov     eax, [rcx-10h]
0x14000e437  test    eax, eax
0x14000e439  jz      loc_14000E52E
0x14000e43f  jle     short loc_14000E46D
0x14000e441  mov     edx, 7Bh ; '{'; Ch
0x14000e446  call    cs:__imp_wcschr
0x14000e44c  nop
0x14000e44d  test    rax, rax
0x14000e450  jz      short loc_14000E46D
0x14000e452  sub     rax, [rdi]
0x14000e455  sar     rax, 1
0x14000e458  cmp     eax, 0FFFFFFFFh
0x14000e45b  jz      short loc_14000E46D
0x14000e45d  mov     rdx, rdi
0x14000e460  mov     rcx, rbx
0x14000e463  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000e468  jmp     loc_14000E525
0x14000e46d  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000e474  mov     rcx, r15
0x14000e477  mov     rax, [rax+18h]
0x14000e47b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e480  add     rax, 18h
0x14000e484  mov     [rbp+arg_10], rax
0x14000e488  lea     r8, [rbp+arg_10]
0x14000e48c  mov     rdx, rdi
0x14000e48f  call    ?GetJwtPayload@IdToken@@AEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV23@@Z; IdToken::GetJwtPayload(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x14000e494  xorps   xmm0, xmm0
0x14000e497  movdqu  [rbp+var_20], xmm0
0x14000e49c  mov     [rbp+var_10], 0
0x14000e4a4  lea     rdx, [rbp+var_20]
0x14000e4a8  lea     rcx, [rbp+arg_10]
0x14000e4ac  call    ?Base64UrlDecode@StringUtility@@SAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$vector@EV?$allocator@E@std@@@std@@@Z; StringUtility::Base64UrlDecode(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,std::vector<uchar> &)
0x14000e4b1  mov     rdx, qword ptr [rbp+var_20]
0x14000e4b5  mov     r8d, dword ptr [rbp+var_20+8]
0x14000e4b9  sub     r8d, edx
0x14000e4bc  lea     rcx, [rbp+arg_18]
0x14000e4c0  call    ??$DecodeBytes@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@StringUtility@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBEHI@Z; StringUtility::DecodeBytes<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>(uchar const *,int,uint)
0x14000e4c5  nop
0x14000e4c6  mov     rdx, rax
0x14000e4c9  mov     rcx, rbx
0x14000e4cc  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000e4d1  nop
0x14000e4d2  mov     rdx, [rbp+arg_18]
0x14000e4d6  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000e4da  or      eax, 0FFFFFFFFh
0x14000e4dd  lock xadd [rdx+10h], eax
0x14000e4e2  sub     eax, 1
0x14000e4e5  jg      short loc_14000E4F7
0x14000e4e7  mov     rcx, [rdx]
0x14000e4ea  mov     rax, [rcx]
0x14000e4ed  mov     rax, [rax+8]
0x14000e4f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e4f6  nop
0x14000e4f7  lea     rcx, [rbp+var_20]
0x14000e4fb  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x14000e500  nop
0x14000e501  mov     rdx, [rbp+arg_10]
0x14000e505  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000e509  or      eax, 0FFFFFFFFh
0x14000e50c  lock xadd [rdx+10h], eax
0x14000e511  sub     eax, 1
0x14000e514  jg      short loc_14000E525
0x14000e516  mov     rcx, [rdx]
0x14000e519  mov     rax, [rcx]
0x14000e51c  mov     rax, [rax+8]
0x14000e520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e525  mov     rcx, rbx; this
0x14000e528  call    ?ParseIdTokenPayload@IdToken@@AEAAXXZ; IdToken::ParseIdTokenPayload(void)
0x14000e52d  nop
0x14000e52e  mov     rax, rbx
0x14000e531  mov     rbx, [rsp+40h+arg_8]
0x14000e536  add     rsp, 40h
0x14000e53a  pop     r15
0x14000e53c  pop     rdi
0x14000e53d  pop     rbp
0x14000e53e  retn
```
