# WSTrustTokenRequest::AcquireToken(CSecureString const &,CSecureString const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,bool)

- ea: `0x140016a04`
- end: `0x1400170fe`
- name: `?AcquireToken@WSTrustTokenRequest@@QEAA_NAEBVCSecureString@@0V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1_N@Z`
- size: `1786`
- prototype: `char __fastcall(__int64, _QWORD *, _QWORD *, _QWORD *, __int64 *, char)`
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops`

## callers

- `0x14000b4f4`
- `0x14000b7e0`

## callees

- `0x1400028ac`
- `0x140005458`
- `0x1400054e8`
- `0x14000579c`
- `0x1400061dc`
- `0x140007bf8`
- `0x14000813c`
- `0x140008ce8`
- `0x14000c13c`
- `0x14000c384`
- `0x140016920`
- `0x140016a04`
- `0x140017340`
- `0x14001749c`
- `0x1400175f8`
- `0x1400176b4`
- `0x140017c20`
- `0x140018000`
- `0x140027d80`
- `0x14002c3d0`
- `0x140030010`

## string_xrefs

- `0x140016a55`: `urn:ietf:params:oauth:token-type:jwt`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
char __fastcall WSTrustTokenRequest::AcquireToken(__int64 a1, _QWORD *a2, _QWORD *a3, _QWORD *a4, __int64 *a5, char a6)
{
  int v10; // ebx
  int *v11; // rdx
  __int64 *v12; // rdx
  bool v13; // r13
  const wchar_t **v14; // rax
  int v15; // esi
  _QWORD *v16; // rdx
  int v17; // ecx
  _QWORD *v18; // rdx
  const wchar_t **v19; // rax
  int v20; // esi
  _QWORD *v21; // rdx
  int v22; // ecx
  _QWORD *v23; // rdx
  char v24; // si
  __int64 *v25; // rax
  int v26; // ebx
  int v27; // r8d
  __int64 *v28; // rbx
  __int64 *v29; // rsi
  int v30; // r14d
  __int64 *v31; // rdx
  const wchar_t **ErrorCode; // rax
  int v33; // r14d
  __int64 *v34; // rdx
  _QWORD *v35; // rdx
  _QWORD *v36; // rdx
  const wchar_t *v37; // rdx
  __int64 v38; // r8
  _QWORD *v39; // rdx
  _QWORD *v40; // rdx
  __int64 v41; // r9
  _QWORD *v42; // rdx
  _QWORD *v43; // rdx
  _QWORD *v44; // rdx
  volatile signed __int32 *v45; // rdx
  volatile signed __int32 *v46; // rdx
  _QWORD *v48; // rdx
  _QWORD *v49; // rdx
  _QWORD *v50; // rdx
  volatile signed __int32 *v51; // rdx
  volatile signed __int32 *v52; // rdx
  __int64 v53; // [rsp+40h] [rbp-39h] BYREF
  __int64 v54; // [rsp+48h] [rbp-31h] BYREF
  __int64 v55; // [rsp+50h] [rbp-29h] BYREF
  __int64 *v56; // [rsp+58h] [rbp-21h] BYREF
  __int64 v57; // [rsp+60h] [rbp-19h] BYREF
  __int64 v58; // [rsp+68h] [rbp-11h] BYREF
  __int64 v59; // [rsp+70h] [rbp-9h] BYREF
  void *Block; // [rsp+78h] [rbp-1h] BYREF

  v10 = 0;
  LODWORD(v54) = 0;
  v55 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v11 = &dword_14003353C;
  if ( !a6 )
    v11 = (int *)L"urn:ietf:params:oauth:token-type:jwt";
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v58,
    (__int64)v11);
  v12 = a5;
  if ( !a6 )
    v12 = (__int64 *)(a1 + 16);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v57,
    v12);
  v13 = !*(_DWORD *)(*a2 - 16LL) && !*(_DWORD *)(*a3 - 16LL);
  v14 = (const wchar_t **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                            a4,
                            &v53,
                            4);
  v15 = wcscmp_0(*v14, L"v13:");
  v16 = (_QWORD *)(v53 - 24);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v53 - 24 + 16), 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v16 + 8LL))(*v16);
  if ( !v15 )
  {
    v10 = 4;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
      a4,
      &v53,
      4,
      (unsigned int)(*(_DWORD *)(*a4 - 16LL) - 4));
    LODWORD(v54) = 4;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      &v55,
      &v53);
    v18 = (_QWORD *)(v53 - 24);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v53 - 24 + 16), 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 8LL))(*v18);
    goto LABEL_21;
  }
  v19 = (const wchar_t **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                            a4,
                            &v53,
                            6);
  v20 = wcscmp_0(*v19, L"v2005:");
  v21 = (_QWORD *)(v53 - 24);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v53 - 24 + 16), 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v21 + 8LL))(*v21);
  if ( v20 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(&v55, a4);
LABEL_21:
    v24 = 0;
    v25 = (__int64 *)WSTrustTokenRequest::BuildWSTrustTokenRequestMessage13(
                       v17,
                       (unsigned int)&v53,
                       (unsigned int)&v57,
                       (unsigned int)&v55,
                       (__int64)a2,
                       (__int64)a3,
                       (__int64)&v58);
    v26 = v10 | 2;
    goto LABEL_22;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
    a4,
    &v53,
    6,
    (unsigned int)(*(_DWORD *)(*a4 - 16LL) - 6));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(&v55, &v53);
  v23 = (_QWORD *)(v53 - 24);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v53 - 24 + 16), 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v23 + 8LL))(*v23);
  v24 = 1;
  v25 = (__int64 *)WSTrustTokenRequest::BuildWSTrustTokenRequestMessage2005(
                     v22,
                     (unsigned int)&v56,
                     (unsigned int)&v57,
                     (unsigned int)&v55,
                     (__int64)a2,
                     (__int64)a3,
                     (__int64)&v58);
  v26 = 9;
LABEL_22:
  LODWORD(v54) = v26;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v59,
    v25);
  if ( (v26 & 2) != 0 )
  {
    LOBYTE(v26) = v26 & 0xFD;
    CSecureString::~CSecureString((CSecureString *)&v53);
  }
  if ( (v26 & 1) != 0 )
    CSecureString::~CSecureString((CSecureString *)&v56);
  LOBYTE(v27) = v13;
  WSTrustTokenRequest::GetWSTrustResponse(a1, (unsigned int)&Block, v27, (unsigned int)&v59, (__int64)&v55, v24);
  v28 = (__int64 *)Block;
  v29 = (__int64 *)((char *)Block + 40);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v56,
    (__int64 *)Block + 5);
  v30 = *((_DWORD *)v56 - 4);
  v31 = v56 - 3;
  if ( _InterlockedDecrement((volatile signed __int32 *)v56 - 2) <= 0 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)*v31 + 8LL))(*v31);
  if ( v30 )
  {
    ErrorCode = (const wchar_t **)WSTrustResponse::GetErrorCode(v28, &v56);
    v33 = wcscmp_0(*ErrorCode, L"FailedAuthentication");
    v34 = v56 - 3;
    if ( _InterlockedDecrement((volatile signed __int32 *)v56 - 2) <= 0 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)*v34 + 8LL))(*v34);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v54,
      v29);
    v56 = &v54;
    if ( v33 )
    {
      Log::ErrorInternal(a1, 3400073236LL, 1252917258, v54);
      v39 = (_QWORD *)(v54 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v54 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v39 + 8LL))(*v39);
      *(_DWORD *)(a1 + 60) = -894894060;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v53,
        v29);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        (_QWORD *)(a1 + 72),
        &v53);
      v40 = (_QWORD *)(v53 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v53 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v40 + 8LL))(*v40);
      v37 = L"authentication_failed";
      v38 = 21;
    }
    else
    {
      Log::ErrorInternal(a1, 3399614467LL, 1252917258, v54);
      v35 = (_QWORD *)(v54 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v54 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v35 + 8LL))(*v35);
      *(_DWORD *)(a1 + 60) = -895352829;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v53,
        v29);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        (_QWORD *)(a1 + 72),
        &v53);
      v36 = (_QWORD *)(v53 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v53 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v36 + 8LL))(*v36);
      v37 = L"invalid_grant";
      v38 = 13;
    }
    ATL::CSimpleStringT<unsigned short,0>::SetString(a1 + 64, v37, v38);
    goto LABEL_46;
  }
  if ( a6 )
  {
    LODWORD(v54) = 0;
    WSTrustTokenRequest::GetAssertionInfo(&v53, v28, &v54);
    if ( !SAMLAssertionTokenRequest::AcquireToken((struct OAuthTokenRequestBase *)a1, (__int64)&v53, v54) )
    {
      Log::ErrorInternal(a1, 3400073222LL, 0, v41);
      CSecureString::~CSecureString((CSecureString *)&v53);
      if ( !v28 )
      {
LABEL_48:
        CSecureString::~CSecureString((CSecureString *)&v59);
        v42 = (_QWORD *)(v57 - 24);
        if ( _InterlockedDecrement((volatile signed __int32 *)(v57 - 24 + 16)) <= 0 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v42 + 8LL))(*v42);
        v43 = (_QWORD *)(v58 - 24);
        if ( _InterlockedDecrement((volatile signed __int32 *)(v58 - 24 + 16)) <= 0 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v43 + 8LL))(*v43);
        v44 = (_QWORD *)(v55 - 24);
        if ( _InterlockedDecrement((volatile signed __int32 *)(v55 - 24 + 16)) <= 0 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v44 + 8LL))(*v44);
        v45 = (volatile signed __int32 *)(*a4 - 24LL);
        if ( _InterlockedDecrement(v45 + 4) <= 0 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v45 + 8LL))(*(_QWORD *)v45);
        v46 = (volatile signed __int32 *)(*a5 - 24);
        if ( _InterlockedDecrement(v46 + 4) <= 0 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v46 + 8LL))(*(_QWORD *)v46);
        return 0;
      }
LABEL_46:
      if ( v28 )
      {
        WSTrustResponse::~WSTrustResponse((WSTrustResponse *)v28);
        operator delete(v28);
      }
      goto LABEL_48;
    }
  }
  else
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v53,
      v28 + 4);
    ATL::CSimpleStringT<unsigned short,0>::Append(a1 + 32, v53, *(unsigned int *)(v53 - 16));
  }
  CSecureString::~CSecureString((CSecureString *)&v53);
  Log::InfoInternal(a1, 1252589581, 0);
  if ( v28 )
  {
    WSTrustResponse::~WSTrustResponse((WSTrustResponse *)v28);
    operator delete(v28);
  }
  CSecureString::~CSecureString((CSecureString *)&v59);
  v48 = (_QWORD *)(v57 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v57 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v48 + 8LL))(*v48);
  v49 = (_QWORD *)(v58 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v58 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v49 + 8LL))(*v49);
  v50 = (_QWORD *)(v55 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v55 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v50 + 8LL))(*v50);
  v51 = (volatile signed __int32 *)(*a4 - 24LL);
  if ( _InterlockedDecrement(v51 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v51 + 8LL))(*(_QWORD *)v51);
  v52 = (volatile signed __int32 *)(*a5 - 24);
  if ( _InterlockedDecrement(v52 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v52 + 8LL))(*(_QWORD *)v52);
  return 1;
}

```

## disassembly

```asm
0x140016a04  mov     [rsp-8+arg_18], r9
0x140016a09  push    rbp
0x140016a0a  push    rbx
0x140016a0b  push    rsi
0x140016a0c  push    rdi
0x140016a0d  push    r12
0x140016a0f  push    r13
0x140016a11  push    r14
0x140016a13  push    r15
0x140016a15  lea     rbp, [rsp-0Fh]
0x140016a1a  sub     rsp, 88h
0x140016a21  mov     r15, r9
0x140016a24  mov     r14, r8
0x140016a27  mov     r12, rdx
0x140016a2a  mov     rdi, rcx
0x140016a2d  xor     ebx, ebx
0x140016a2f  mov     dword ptr [rbp+47h+var_78], ebx
0x140016a32  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140016a39  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140016a40  mov     rax, [rax+18h]
0x140016a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016a49  add     rax, 18h
0x140016a4d  mov     [rbp+47h+var_70], rax
0x140016a51  mov     sil, [rbp+47h+arg_28]
0x140016a55  lea     rax, aUrnIetfParamsO_0; "urn:ietf:params:oauth:token-type:jwt"
0x140016a5c  lea     rdx, dword_14003353C
0x140016a63  test    sil, sil
0x140016a66  cmovz   rdx, rax
0x140016a6a  lea     rcx, [rbp+47h+var_58]
0x140016a6e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140016a73  nop
0x140016a74  test    sil, sil
0x140016a77  mov     rdx, [rbp+47h+arg_20]
0x140016a7b  jnz     short loc_140016A81
0x140016a7d  lea     rdx, [rdi+10h]
0x140016a81  lea     rcx, [rbp+47h+var_60]
0x140016a85  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140016a8a  nop
0x140016a8b  mov     rax, [r12]
0x140016a8f  cmp     dword ptr [rax-10h], 0
0x140016a93  jnz     short loc_140016AA3
0x140016a95  mov     rax, [r14]
0x140016a98  cmp     dword ptr [rax-10h], 0
0x140016a9c  jnz     short loc_140016AA3
0x140016a9e  mov     r13b, 1
0x140016aa1  jmp     short loc_140016AA6
0x140016aa3  xor     r13b, r13b
0x140016aa6  mov     r8d, 4
0x140016aac  lea     rdx, [rbp+47h+var_80]
0x140016ab0  mov     rcx, r15
0x140016ab3  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x140016ab8  nop
0x140016ab9  lea     rdx, aV13; "v13:"
0x140016ac0  mov     rcx, [rax]; String1
0x140016ac3  call    wcscmp_0
0x140016ac8  mov     esi, eax
0x140016aca  mov     rdx, [rbp+47h+var_80]
0x140016ace  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140016ad2  or      ecx, 0FFFFFFFFh
0x140016ad5  lock xadd [rdx+10h], ecx
0x140016ada  sub     ecx, 1
0x140016add  jg      short loc_140016AEE
0x140016adf  mov     rcx, [rdx]
0x140016ae2  mov     r8, [rcx]
0x140016ae5  mov     rax, [r8+8]
0x140016ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016aee  lea     rdx, [rbp+47h+var_80]
0x140016af2  mov     rcx, r15
0x140016af5  test    esi, esi
0x140016af7  jnz     short loc_140016B4C
0x140016af9  mov     rax, [r15]
0x140016afc  mov     r9d, [rax-10h]
0x140016b00  lea     ebx, [rsi+4]
0x140016b03  sub     r9d, ebx
0x140016b06  mov     r8d, ebx
0x140016b09  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x140016b0e  mov     dword ptr [rbp+47h+var_78], ebx
0x140016b11  lea     rdx, [rbp+47h+var_80]
0x140016b15  lea     rcx, [rbp+47h+var_70]
0x140016b19  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140016b1e  nop
0x140016b1f  mov     rdx, [rbp+47h+var_80]
0x140016b23  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140016b27  or      eax, 0FFFFFFFFh
0x140016b2a  lock xadd [rdx+10h], eax
0x140016b2f  sub     eax, 1
0x140016b32  jg      loc_140016C1A
0x140016b38  mov     rcx, [rdx]
0x140016b3b  mov     rax, [rcx]
0x140016b3e  mov     rax, [rax+8]
0x140016b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016b47  jmp     loc_140016C1A
0x140016b4c  mov     r8d, 6
0x140016b52  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x140016b57  nop
0x140016b58  lea     rdx, aV2005; "v2005:"
0x140016b5f  mov     rcx, [rax]; String1
0x140016b62  call    wcscmp_0
0x140016b67  mov     esi, eax
0x140016b69  mov     rdx, [rbp+47h+var_80]
0x140016b6d  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140016b71  or      ecx, 0FFFFFFFFh
0x140016b74  lock xadd [rdx+10h], ecx
0x140016b79  sub     ecx, 1
0x140016b7c  jg      short loc_140016B8D
0x140016b7e  mov     rcx, [rdx]
0x140016b81  mov     r8, [rcx]
0x140016b84  mov     rax, [r8+8]
0x140016b88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016b8d  test    esi, esi
0x140016b8f  jnz     short loc_140016C0E
0x140016b91  mov     rax, [r15]
0x140016b94  mov     r9d, [rax-10h]
0x140016b98  sub     r9d, 6
0x140016b9c  lea     r8d, [rsi+6]
0x140016ba0  lea     rdx, [rbp+47h+var_80]
0x140016ba4  mov     rcx, r15
0x140016ba7  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x140016bac  nop
0x140016bad  lea     rdx, [rbp+47h+var_80]
0x140016bb1  lea     rcx, [rbp+47h+var_70]
0x140016bb5  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140016bba  nop
0x140016bbb  mov     rdx, [rbp+47h+var_80]
0x140016bbf  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140016bc3  or      eax, 0FFFFFFFFh
0x140016bc6  lock xadd [rdx+10h], eax
0x140016bcb  sub     eax, 1
0x140016bce  jg      short loc_140016BDF
0x140016bd0  mov     rcx, [rdx]
0x140016bd3  mov     rax, [rcx]
0x140016bd6  mov     rax, [rax+8]
0x140016bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016bdf  mov     sil, 1
0x140016be2  lea     rax, [rbp+47h+var_58]
0x140016be6  mov     [rsp+0C0h+var_90], rax
0x140016beb  mov     [rsp+0C0h+var_98], r14
0x140016bf0  mov     [rsp+0C0h+var_A0], r12
0x140016bf5  lea     r9, [rbp+47h+var_70]
0x140016bf9  lea     r8, [rbp+47h+var_60]
0x140016bfd  lea     rdx, [rbp+47h+var_68]
0x140016c01  call    ?BuildWSTrustTokenRequestMessage2005@WSTrustTokenRequest@@AEAA?AVCSecureString@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0AEBV2@10@Z; WSTrustTokenRequest::BuildWSTrustTokenRequestMessage2005(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,CSecureString const &,CSecureString const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140016c06  nop
0x140016c07  mov     ebx, 9
0x140016c0c  jmp     short loc_140016C45
0x140016c0e  mov     rdx, r15
0x140016c11  lea     rcx, [rbp+47h+var_70]
0x140016c15  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140016c1a  xor     sil, sil
0x140016c1d  lea     rax, [rbp+47h+var_58]
0x140016c21  mov     [rsp+0C0h+var_90], rax
0x140016c26  mov     [rsp+0C0h+var_98], r14
0x140016c2b  mov     [rsp+0C0h+var_A0], r12
0x140016c30  lea     r9, [rbp+47h+var_70]
0x140016c34  lea     r8, [rbp+47h+var_60]
0x140016c38  lea     rdx, [rbp+47h+var_80]
0x140016c3c  call    ?BuildWSTrustTokenRequestMessage13@WSTrustTokenRequest@@AEAA?AVCSecureString@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0AEBV2@10@Z; WSTrustTokenRequest::BuildWSTrustTokenRequestMessage13(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,CSecureString const &,CSecureString const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140016c41  nop
0x140016c42  or      ebx, 2
0x140016c45  mov     dword ptr [rbp+47h+var_78], ebx
0x140016c48  mov     rdx, rax
0x140016c4b  lea     rcx, [rbp+47h+var_50]
0x140016c4f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140016c54  nop
0x140016c55  test    bl, 2
0x140016c58  jz      short loc_140016C67
0x140016c5a  and     ebx, 0FFFFFFFDh
0x140016c5d  lea     rcx, [rbp+47h+var_80]; this
0x140016c61  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x140016c66  nop
0x140016c67  test    bl, 1
0x140016c6a  jz      short loc_140016C75
0x140016c6c  lea     rcx, [rbp+47h+var_68]; this
0x140016c70  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x140016c75  mov     byte ptr [rsp+0C0h+var_98], sil
0x140016c7a  lea     rax, [rbp+47h+var_70]
0x140016c7e  mov     [rsp+0C0h+var_A0], rax
0x140016c83  lea     r9, [rbp+47h+var_50]
0x140016c87  mov     r8b, r13b
0x140016c8a  lea     rdx, [rbp+47h+Block]
0x140016c8e  mov     rcx, rdi
0x140016c91  call    ?GetWSTrustResponse@WSTrustTokenRequest@@AEAA?AV?$unique_ptr@VWSTrustResponse@@U?$default_delete@VWSTrustResponse@@@std@@@std@@_NAEBVCSecureString@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; WSTrustTokenRequest::GetWSTrustResponse(bool,CSecureString const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool)
0x140016c96  nop
0x140016c97  mov     rbx, [rbp+47h+Block]
0x140016c9b  lea     rsi, [rbx+28h]
0x140016c9f  mov     rdx, rsi
0x140016ca2  lea     rcx, [rbp+47h+var_68]
0x140016ca6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140016cab  mov     rax, [rbp+47h+var_68]
0x140016caf  mov     r14d, [rax-10h]
0x140016cb3  lea     rdx, [rax-18h]
0x140016cb7  or      r12d, 0FFFFFFFFh
0x140016cbb  mov     eax, r12d
0x140016cbe  lock xadd [rdx+10h], eax
0x140016cc3  add     eax, r12d
0x140016cc6  test    eax, eax
0x140016cc8  jg      short loc_140016CD9
0x140016cca  mov     rcx, [rdx]
0x140016ccd  mov     rax, [rcx]
0x140016cd0  mov     rax, [rax+8]
0x140016cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016cd9  test    r14d, r14d
0x140016cdc  jz      loc_140016E7D
0x140016ce2  lea     rdx, [rbp+47h+var_68]
0x140016ce6  mov     rcx, rbx
0x140016ce9  call    ?GetErrorCode@WSTrustResponse@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; WSTrustResponse::GetErrorCode(void)
0x140016cee  nop
0x140016cef  lea     rdx, aFailedauthenti; "FailedAuthentication"
0x140016cf6  mov     rcx, [rax]; String1
0x140016cf9  call    wcscmp_0
0x140016cfe  mov     r14d, eax
0x140016d01  mov     rdx, [rbp+47h+var_68]
0x140016d05  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140016d09  mov     ecx, r12d
0x140016d0c  lock xadd [rdx+10h], ecx
0x140016d11  add     ecx, r12d
0x140016d14  test    ecx, ecx
0x140016d16  jg      short loc_140016D27
0x140016d18  mov     rcx, [rdx]
0x140016d1b  mov     r8, [rcx]
0x140016d1e  mov     rax, [r8+8]
0x140016d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016d27  mov     rdx, rsi
0x140016d2a  lea     rcx, [rbp+47h+var_78]
0x140016d2e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140016d33  lea     rax, [rbp+47h+var_78]
0x140016d37  mov     [rbp+47h+var_68], rax
0x140016d3b  test    r14d, r14d
0x140016d3e  jnz     loc_140016DDD
0x140016d44  mov     r9, [rbp+47h+var_78]
0x140016d48  mov     r8d, 4AAE000Ah
0x140016d4e  mov     r14d, 0CAA20003h
0x140016d54  mov     edx, r14d
0x140016d57  mov     rcx, rdi
0x140016d5a  call    ?ErrorInternal@Log@@CAXPEBVILogContext@@KVResourceId@@ZZ; Log::ErrorInternal(ILogContext const *,ulong,ResourceId,...)
0x140016d5f  nop
0x140016d60  mov     rdx, [rbp+47h+var_78]
0x140016d64  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140016d68  mov     eax, r12d
0x140016d6b  lock xadd [rdx+10h], eax
0x140016d70  add     eax, r12d
0x140016d73  test    eax, eax
0x140016d75  jg      short loc_140016D86
0x140016d77  mov     rcx, [rdx]
0x140016d7a  mov     rax, [rcx]
0x140016d7d  mov     rax, [rax+8]
0x140016d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016d86  mov     [rdi+3Ch], r14d
0x140016d8a  mov     rdx, rsi
0x140016d8d  lea     rcx, [rbp+47h+var_80]
0x140016d91  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140016d96  nop
0x140016d97  lea     rcx, [rdi+48h]
0x140016d9b  lea     rdx, [rbp+47h+var_80]
0x140016d9f  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140016da4  nop
0x140016da5  mov     rdx, [rbp+47h+var_80]
0x140016da9  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140016dad  mov     eax, r12d
0x140016db0  lock xadd [rdx+10h], eax
0x140016db5  add     eax, r12d
0x140016db8  test    eax, eax
0x140016dba  jg      short loc_140016DCB
0x140016dbc  mov     rcx, [rdx]
0x140016dbf  mov     rax, [rcx]
0x140016dc2  mov     rax, [rax+8]
0x140016dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016dcb  lea     rdx, aInvalidGrant; "invalid_grant"
0x140016dd2  mov     r8d, 0Dh
0x140016dd8  jmp     loc_140016E71
0x140016ddd  mov     r9, [rbp+47h+var_78]
0x140016de1  mov     r8d, 4AAE000Ah
0x140016de7  mov     r14d, 0CAA90014h
0x140016ded  mov     edx, r14d
0x140016df0  mov     rcx, rdi
0x140016df3  call    ?ErrorInternal@Log@@CAXPEBVILogContext@@KVResourceId@@ZZ; Log::ErrorInternal(ILogContext const *,ulong,ResourceId,...)
0x140016df8  nop
0x140016df9  mov     rdx, [rbp+47h+var_78]
0x140016dfd  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140016e01  mov     eax, r12d
0x140016e04  lock xadd [rdx+10h], eax
0x140016e09  add     eax, r12d
0x140016e0c  test    eax, eax
0x140016e0e  jg      short loc_140016E1F
0x140016e10  mov     rcx, [rdx]
0x140016e13  mov     rax, [rcx]
0x140016e16  mov     rax, [rax+8]
0x140016e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016e1f  mov     [rdi+3Ch], r14d
0x140016e23  mov     rdx, rsi
0x140016e26  lea     rcx, [rbp+47h+var_80]
0x140016e2a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140016e2f  nop
0x140016e30  lea     rcx, [rdi+48h]
0x140016e34  lea     rdx, [rbp+47h+var_80]
0x140016e38  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140016e3d  nop
0x140016e3e  mov     rdx, [rbp+47h+var_80]
0x140016e42  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140016e46  mov     eax, r12d
  ... truncated ...
```
