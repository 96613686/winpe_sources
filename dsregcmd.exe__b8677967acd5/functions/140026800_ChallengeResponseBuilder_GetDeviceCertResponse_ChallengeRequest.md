# ChallengeResponseBuilder::GetDeviceCertResponse(ChallengeRequest)

- ea: `0x140026800`
- end: `0x140026b40`
- name: `?GetDeviceCertResponse@ChallengeResponseBuilder@@AEAA?AVChallengeResponse@@VChallengeRequest@@@Z`
- size: `832`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140025ccc`

## callees

- `0x140005458`
- `0x140007bf8`
- `0x140008644`
- `0x14000c7d8`
- `0x14001943c`
- `0x140025adc`
- `0x140025c1c`
- `0x140026800`
- `0x140029d48`
- `0x140030010`

## string_xrefs

- `0x140026a4c`: `%s AuthToken="%s",Context="%s",Version="%s"`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall ChallengeResponseBuilder::GetDeviceCertResponse(__int64 a1, _QWORD *a2, __int64 *a3)
{
  __int64 *v3; // r15
  _QWORD *v4; // r12
  __int64 v5; // r14
  _QWORD *v6; // r13
  _QWORD *v7; // rsi
  __int64 v8; // rax
  volatile signed __int32 *v9; // rdi
  __int64 v10; // rcx
  __int64 *v11; // rdx
  unsigned __int16 *v12; // rdx
  __int64 v14; // [rsp+20h] [rbp-A8h]
  __int64 v15; // [rsp+28h] [rbp-A0h]
  int v16; // [rsp+30h] [rbp-98h]
  __int64 v17; // [rsp+38h] [rbp-90h] BYREF
  __int64 v18; // [rsp+40h] [rbp-88h] BYREF
  __int128 v19; // [rsp+48h] [rbp-80h] BYREF
  __int64 v20; // [rsp+58h] [rbp-70h] BYREF
  __int64 v21; // [rsp+60h] [rbp-68h] BYREF
  unsigned __int16 *v22; // [rsp+68h] [rbp-60h] BYREF
  _QWORD *v23; // [rsp+70h] [rbp-58h]
  volatile signed __int32 *v24; // [rsp+78h] [rbp-50h]
  __int64 v25; // [rsp+80h] [rbp-48h]
  __int64 *v32; // [rsp+E8h] [rbp+20h] BYREF

  v3 = a3;
  v4 = a2;
  v5 = a1;
  v16 = 0;
  v32 = &v17;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v17,
    a3);
  v6 = v3 + 1;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v18,
    v3 + 1);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v19,
    v3 + 2);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (_QWORD *)&v19 + 1,
    v3 + 3);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v20,
    v3 + 4);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v21,
    v3 + 5);
  v32 = &v17;
  *v4 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v7 = v4 + 1;
  v23 = v4 + 1;
  v4[1] = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(v4, &v21);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    (__int64)(v4 + 1),
    (__int64)L"%s Context=\"%s\",Version=\"%s\"",
    L"PKeyAuth",
    v18,
    v20);
  ChallengeRequest::~ChallengeRequest((ChallengeRequest *)&v17);
  v16 = 1;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(v4, v3 + 5);
  v17 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v18 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v19 = 0;
  LODWORD(v20) = 0x10000;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    &v18,
    v3 + 2);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    &v17,
    v3 + 3);
  v8 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
  try
  {
    v9 = (volatile signed __int32 *)v8;
    v24 = (volatile signed __int32 *)v8;
    v25 = v8 + 24;
    JWSBuilder::GenerateSignedJWT(
      *(_QWORD *)v5,
      (unsigned int)&v32,
      (_DWORD)v3,
      (_DWORD)v3 + 40,
      *(_QWORD *)(v5 + 8),
      (__int64)&v17);
    v10 = (__int64)(v4 + 1);
    if ( *((_DWORD *)v32 - 4) )
    {
      v15 = v3[4];
      v14 = *v6;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        v10,
        (__int64)L"%s AuthToken=\"%s\",Context=\"%s\",Version=\"%s\"",
        L"PKeyAuth");
    }
    else
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        v10,
        (__int64)L"%s Context=\"%s\",Version=\"%s\"",
        L"PKeyAuth",
        *v6,
        v3[4]);
    }
    v11 = v32 - 3;
    if ( _InterlockedDecrement((volatile signed __int32 *)v32 - 2) <= 0 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)*v11 + 8LL))(*v11);
  }
  catch ( ... )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      (__int64)(a2 + 1),
      (__int64)L"%s Context=\"%s\",Version=\"%s\"",
      L"PKeyAuth",
      a3[1],
      a3[4]);
    v5 = a1;
    v3 = a3;
    v4 = a2;
    v7 = v23;
    v9 = v24;
  }
  ATL::operator+(&v22, L"Challenge Response: ", v7);
  Log::Verbose(*(const struct ILogContext **)(v5 + 16), v22);
  v12 = v22 - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)v22 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v12 + 8LL))(*(_QWORD *)v12);
  if ( _InterlockedDecrement(v9 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v9 + 8LL))(*(_QWORD *)v9, v9);
  DeviceCert::~DeviceCert((DeviceCert *)&v17);
  ChallengeRequest::~ChallengeRequest((ChallengeRequest *)v3);
  return v4;
}

```

## disassembly

```asm
0x140026800  mov     r11, rsp
0x140026803  mov     [r11+18h], r8
0x140026807  mov     [r11+10h], rdx
0x14002680b  mov     [r11+8], rcx
0x14002680f  push    rbx
0x140026810  push    rsi
0x140026811  push    rdi
0x140026812  push    r12
0x140026814  push    r13
0x140026816  push    r14
0x140026818  push    r15
0x14002681a  sub     rsp, 90h
0x140026821  mov     r15, r8
0x140026824  mov     r12, rdx
0x140026827  mov     r14, rcx
0x14002682a  mov     [rsp+0C8h+var_98], 0
0x140026832  lea     rax, [rsp+0C8h+var_90]
0x140026837  mov     [r11+20h], rax
0x14002683b  mov     rdx, r8
0x14002683e  lea     rcx, [rsp+0C8h+var_90]
0x140026843  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140026848  nop
0x140026849  lea     r13, [r15+8]
0x14002684d  mov     rdx, r13
0x140026850  lea     rcx, [rsp+0C8h+var_88]
0x140026855  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14002685a  nop
0x14002685b  lea     rdx, [r15+10h]
0x14002685f  lea     rcx, [rsp+0C8h+var_80]
0x140026864  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140026869  nop
0x14002686a  lea     rdx, [r15+18h]
0x14002686e  lea     rcx, [rsp+0C8h+var_80+8]
0x140026873  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140026878  nop
0x140026879  lea     rdx, [r15+20h]
0x14002687d  lea     rcx, [rsp+0C8h+var_70]
0x140026882  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140026887  nop
0x140026888  lea     rdx, [r15+28h]
0x14002688c  lea     rcx, [rsp+0C8h+var_68]
0x140026891  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140026896  nop
0x140026897  lea     rax, [rsp+0C8h+var_90]
0x14002689c  mov     [rsp+0C8h+arg_18], rax
0x1400268a4  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400268ab  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400268b2  mov     rax, [rax+18h]
0x1400268b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400268bb  add     rax, 18h
0x1400268bf  mov     [r12], rax
0x1400268c3  lea     rsi, [r12+8]
0x1400268c8  mov     [rsp+0C8h+var_58], rsi
0x1400268cd  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400268d4  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400268db  mov     rax, [rax+18h]
0x1400268df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400268e4  add     rax, 18h
0x1400268e8  mov     [rsi], rax
0x1400268eb  mov     [rsp+0C8h+var_98], 2
0x1400268f3  lea     rdx, [rsp+0C8h+var_68]
0x1400268f8  mov     rcx, r12
0x1400268fb  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140026900  mov     rax, [rsp+0C8h+var_70]
0x140026905  mov     [rsp+0C8h+var_A8], rax
0x14002690a  mov     r9, [rsp+0C8h+var_88]
0x14002690f  lea     r8, aPkeyauth; "PKeyAuth"
0x140026916  lea     rdx, aSContextSVersi; "%s Context=\"%s\",Version=\"%s\""
0x14002691d  mov     rcx, rsi
0x140026920  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x140026925  nop
0x140026926  lea     rcx, [rsp+0C8h+var_90]; this
0x14002692b  call    ??1ChallengeRequest@@QEAA@XZ; ChallengeRequest::~ChallengeRequest(void)
0x140026930  nop
0x140026931  mov     [rsp+0C8h+var_98], 1
0x140026939  lea     rdx, [r15+28h]
0x14002693d  mov     rcx, r12
0x140026940  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140026945  nop
0x140026946  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14002694d  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140026954  mov     rax, [rax+18h]
0x140026958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002695d  add     rax, 18h
0x140026961  mov     [rsp+0C8h+var_90], rax
0x140026966  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14002696d  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140026974  mov     rax, [rax+18h]
0x140026978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002697d  add     rax, 18h
0x140026981  mov     [rsp+0C8h+var_88], rax
0x140026986  xorps   xmm0, xmm0
0x140026989  movdqu  [rsp+0C8h+var_80], xmm0
0x14002698f  mov     dword ptr [rsp+0C8h+var_70], 10000h
0x140026997  lea     rdx, [r15+10h]
0x14002699b  lea     rcx, [rsp+0C8h+var_88]
0x1400269a0  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400269a5  lea     rdx, [r15+18h]
0x1400269a9  lea     rcx, [rsp+0C8h+var_90]
0x1400269ae  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400269b3  nop
0x1400269b4  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400269bb  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400269c2  mov     rax, [rax+18h]
0x1400269c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400269cb  mov     rdi, rax
0x1400269ce  mov     [rsp+0C8h+var_50], rax
0x1400269d3  lea     rcx, [rax+18h]
0x1400269d7  mov     [rsp+0C8h+var_48], rcx
0x1400269df  lea     rax, [rsp+0C8h+var_90]
0x1400269e4  mov     [rsp+0C8h+var_A0], rax
0x1400269e9  mov     rcx, [r14+8]
0x1400269ed  mov     [rsp+0C8h+var_A8], rcx
0x1400269f2  lea     r9, [r15+28h]
0x1400269f6  mov     r8, r15
0x1400269f9  lea     rdx, [rsp+0C8h+arg_18]
0x140026a01  mov     rcx, [r14]
0x140026a04  call    ?GenerateSignedJWT@JWSBuilder@@QEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV23@0PEBGAEAVDeviceCert@@@Z; JWSBuilder::GenerateSignedJWT(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *,DeviceCert &)
0x140026a09  nop
0x140026a0a  mov     r9, [rsp+0C8h+arg_18]
0x140026a12  mov     rax, [r15+20h]
0x140026a16  lea     r8, aPkeyauth; "PKeyAuth"
0x140026a1d  mov     rcx, rsi
0x140026a20  cmp     dword ptr [r9-10h], 0
0x140026a25  jnz     short loc_140026A3E
0x140026a27  mov     [rsp+0C8h+var_A8], rax
0x140026a2c  mov     r9, [r13+0]
0x140026a30  lea     rdx, aSContextSVersi; "%s Context=\"%s\",Version=\"%s\""
0x140026a37  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x140026a3c  jmp     short loc_140026A59
0x140026a3e  mov     [rsp+0C8h+var_A0], rax
0x140026a43  mov     rax, [r13+0]
0x140026a47  mov     [rsp+0C8h+var_A8], rax
0x140026a4c  lea     rdx, aSAuthtokenSCon; "%s AuthToken=\"%s\",Context=\"%s\",Vers"...
0x140026a53  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x140026a58  nop
0x140026a59  mov     rdx, [rsp+0C8h+arg_18]
0x140026a61  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140026a65  or      ebx, 0FFFFFFFFh
0x140026a68  mov     eax, ebx
0x140026a6a  lock xadd [rdx+10h], eax
0x140026a6f  add     eax, ebx
0x140026a71  test    eax, eax
0x140026a73  jg      short loc_140026A85
0x140026a75  mov     rcx, [rdx]
0x140026a78  mov     rax, [rcx]
0x140026a7b  mov     rax, [rax+8]
0x140026a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026a84  nop
0x140026a85  jmp     short loc_140026AAC
0x140026a87  or      ebx, 0FFFFFFFFh
0x140026a8a  mov     r14, [rsp+0C8h+arg_0]
0x140026a92  mov     r15, [rsp+0C8h+arg_10]
0x140026a9a  mov     r12, [rsp+0C8h+arg_8]
0x140026aa2  mov     rsi, [rsp+0C8h+var_58]
0x140026aa7  mov     rdi, [rsp+0C8h+var_50]
0x140026aac  mov     r8, rsi
0x140026aaf  lea     rdx, aChallengeRespo; "Challenge Response: "
0x140026ab6  lea     rcx, [rsp+0C8h+var_60]
0x140026abb  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@PEBGAEBV10@@Z; ATL::operator+(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140026ac0  nop
0x140026ac1  mov     rdx, [rsp+0C8h+var_60]; unsigned __int16 *
0x140026ac6  mov     rcx, [r14+10h]; struct ILogContext *
0x140026aca  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x140026acf  nop
0x140026ad0  mov     rdx, [rsp+0C8h+var_60]
0x140026ad5  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140026ad9  mov     eax, ebx
0x140026adb  lock xadd [rdx+10h], eax
0x140026ae0  add     eax, ebx
0x140026ae2  test    eax, eax
0x140026ae4  jg      short loc_140026AF6
0x140026ae6  mov     rcx, [rdx]
0x140026ae9  mov     rax, [rcx]
0x140026aec  mov     rax, [rax+8]
0x140026af0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026af5  nop
0x140026af6  mov     eax, ebx
0x140026af8  lock xadd [rdi+10h], eax
0x140026afd  add     eax, ebx
0x140026aff  test    eax, eax
0x140026b01  jg      short loc_140026B16
0x140026b03  mov     rcx, [rdi]
0x140026b06  mov     rax, [rcx]
0x140026b09  mov     rdx, rdi
0x140026b0c  mov     rax, [rax+8]
0x140026b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026b15  nop
0x140026b16  lea     rcx, [rsp+0C8h+var_90]; this
0x140026b1b  call    ??1DeviceCert@@QEAA@XZ; DeviceCert::~DeviceCert(void)
0x140026b20  nop
0x140026b21  mov     rcx, r15; this
0x140026b24  call    ??1ChallengeRequest@@QEAA@XZ; ChallengeRequest::~ChallengeRequest(void)
0x140026b29  mov     rax, r12
0x140026b2c  add     rsp, 90h
0x140026b33  pop     r15
0x140026b35  pop     r14
0x140026b37  pop     r13
0x140026b39  pop     r12
0x140026b3b  pop     rdi
0x140026b3c  pop     rsi
0x140026b3d  pop     rbx
0x140026b3e  retn
```
