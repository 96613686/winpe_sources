# OAuthResponse::ParseResponse(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x1400251d4`
- end: `0x140025a07`
- name: `?ParseResponse@OAuthResponse@@AEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `2099`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140024ee8`

## callees

- `0x140001b60`
- `0x1400028ac`
- `0x140003044`
- `0x1400032ec`
- `0x140005c80`
- `0x1400061dc`
- `0x140007bf8`
- `0x14000baf8`
- `0x14000caac`
- `0x14000df44`
- `0x1400234fc`
- `0x1400239a4`
- `0x140025110`
- `0x1400251d4`
- `0x14002c3e8`
- `0x140030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x14002550d`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x1400256db`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x14002550d`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x1400256db`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x140025517`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x140025517`

## string_xrefs

- `0x140025349`: `refresh_token`
- `0x140025363`: `refresh_token`
- `0x140025271`: `access_token`
- `0x140025289`: `access_token`
- `0x140025542`: `id_token`
- `0x14002555c`: `id_token`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
void __fastcall OAuthResponse::ParseResponse(__int64 a1, _WORD **a2)
{
  _QWORD *v4; // rax
  JsonObject *v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // r8
  volatile signed __int32 *v8; // rdx
  volatile signed __int32 *v9; // rdx
  __int64 (__fastcall *v10)(void ***); // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  _QWORD *v13; // rdx
  volatile signed __int32 *v14; // rdx
  volatile signed __int32 *v15; // rdx
  volatile signed __int32 *v16; // rdx
  int v17; // esi
  volatile signed __int32 *v18; // rdx
  _QWORD *JsonDataAsString; // rax
  _QWORD *v20; // rdx
  volatile signed __int32 *v21; // rdx
  volatile signed __int32 *v22; // rdx
  unsigned int v23; // ecx
  unsigned int v24; // edx
  _QWORD *v25; // rdx
  _QWORD *v26; // rdx
  _QWORD *v27; // rdx
  volatile signed __int32 *v28; // rdx
  _QWORD *v29; // rax
  _QWORD *v30; // rdx
  volatile signed __int32 *v31; // rdx
  _QWORD *v32; // rax
  _QWORD *v33; // rdx
  volatile signed __int32 *v34; // rdx
  _QWORD *v35; // rax
  _QWORD *v36; // rdx
  volatile signed __int32 *v37; // rdx
  void *v38; // rcx
  volatile signed __int32 *v39; // [rsp+20h] [rbp-69h] BYREF
  _QWORD pExceptionObject[2]; // [rsp+28h] [rbp-61h] BYREF
  volatile signed __int32 *v41; // [rsp+38h] [rbp-51h] BYREF
  __int64 v42; // [rsp+40h] [rbp-49h] BYREF
  __int64 v43; // [rsp+48h] [rbp-41h] BYREF
  _QWORD v44[2]; // [rsp+50h] [rbp-39h] BYREF
  void *Block[7]; // [rsp+60h] [rbp-29h] BYREF
  char *v46[4]; // [rsp+98h] [rbp+Fh] BYREF

  JsonReader::JsonReader((JsonReader *)Block);
  v4 = std::wstring::wstring(v46, *a2);
  v5 = JsonReader::Parse(Block, v4);
  v44[1] = v5;
  std::wstring::~wstring(v46);
  if ( !v5 || *((_DWORD *)v5 + 2) != 1 )
  {
    Exception::Exception((Exception *)pExceptionObject, -894894059);
    throw (Exception *)pExceptionObject;
  }
  v39 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v39,
          (__int64)L"access_token") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v39, L"access_token", 12);
  v6 = *Utils::GetJsonDataAsString(&v41, (__int64)v5, (_WORD **)&v39);
  if ( v6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)(v6 + 2 * v7) );
  }
  else
  {
    v7 = 0;
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(a1 + 40, v6, v7);
  v8 = v41 - 6;
  if ( _InterlockedDecrement(v41 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v8 + 8LL))(*(_QWORD *)v8);
  v9 = v39 - 6;
  if ( _InterlockedDecrement(v39 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v9 + 8LL))(*(_QWORD *)v9);
  v10 = (__int64 (__fastcall *)(void ***))ATL::g_strmgr[3];
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 40) - 16LL) )
  {
    v39 = (volatile signed __int32 *)(v10(&ATL::g_strmgr) + 24);
    if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
            (void *const *)&v39,
            (__int64)L"refresh_token") )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v39, L"refresh_token", 13);
    v11 = *Utils::GetJsonDataAsString(pExceptionObject, (__int64)v5, (_WORD **)&v39);
    if ( v11 )
    {
      v12 = -1;
      do
        ++v12;
      while ( *(_WORD *)(v11 + 2 * v12) );
    }
    else
    {
      v12 = 0;
    }
    ATL::CSimpleStringT<unsigned short,0>::SetString(a1 + 48, v11, v12);
    v13 = (_QWORD *)(pExceptionObject[0] - 24LL);
    if ( _InterlockedDecrement((volatile signed __int32 *)(pExceptionObject[0] - 24LL + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 8LL))(*v13);
    v14 = v39 - 6;
    if ( _InterlockedDecrement(v39 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v14 + 8LL))(*(_QWORD *)v14);
    v39 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
            (void *const *)&v39,
            (__int64)L"expires_in") )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v39, L"expires_in", 10);
    Utils::GetJsonDataAsString(&v41, (__int64)v5, (_WORD **)&v39);
    v15 = v39 - 6;
    if ( _InterlockedDecrement(v39 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v15 + 8LL))(*(_QWORD *)v15);
    v39 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
            (void *const *)&v39,
            (__int64)L"resource") )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v39, L"resource", 8);
    Utils::GetJsonDataAsString(v44, (__int64)v5, (_WORD **)&v39);
    v16 = v39 - 6;
    if ( _InterlockedDecrement(v39 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 8LL))(*(_QWORD *)v16);
    *(_BYTE *)(a1 + 88) = *(_DWORD *)(v44[0] - 16LL) != 0;
    if ( *((_DWORD *)v41 - 4) )
      v17 = _o__wtol();
    else
      v17 = 0;
    *(_QWORD *)(a1 + 56) = v17 + _time64(0);
    v39 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
            (void *const *)&v39,
            (__int64)L"id_token") )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v39, L"id_token", 8);
    Utils::GetJsonDataAsString(&v43, (__int64)v5, (_WORD **)&v39);
    v18 = v39 - 6;
    if ( _InterlockedDecrement(v39 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v18 + 8LL))(*(_QWORD *)v18);
    v39 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
            (void *const *)&v39,
            (__int64)L"pwd_url") )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v39, L"pwd_url", 7);
    JsonDataAsString = Utils::GetJsonDataAsString(pExceptionObject, (__int64)v5, (_WORD **)&v39);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      (_QWORD *)(a1 + 104),
      JsonDataAsString);
    v20 = (_QWORD *)(pExceptionObject[0] - 24LL);
    if ( _InterlockedDecrement((volatile signed __int32 *)(pExceptionObject[0] - 24LL + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v20 + 8LL))(*v20);
    v21 = v39 - 6;
    if ( _InterlockedDecrement(v39 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v21 + 8LL))(*(_QWORD *)v21);
    v39 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
            (void *const *)&v39,
            (__int64)L"pwd_exp") )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v39, L"pwd_exp", 7);
    Utils::GetJsonDataAsString(&v42, (__int64)v5, (_WORD **)&v39);
    v22 = v39 - 6;
    if ( _InterlockedDecrement(v39 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v22 + 8LL))(*(_QWORD *)v22);
    if ( *(_DWORD *)(v42 - 16) )
    {
      v23 = _o__wtol();
      v24 = -1;
      if ( v23 != -1 )
        v24 = v23 / 0x15180;
      *(_DWORD *)(a1 + 92) = v24;
      *(_BYTE *)(a1 + 96) = 1;
    }
    OAuthResponse::ParseIdTokenResponse(a1, &v43);
    v25 = (_QWORD *)(v42 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v42 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v25 + 8LL))(*v25);
    v26 = (_QWORD *)(v43 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v43 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v26 + 8LL))(*v26);
    v27 = (_QWORD *)(v44[0] - 24LL);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v44[0] - 24LL + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v27 + 8LL))(*v27);
    v28 = v41;
  }
  else
  {
    v39 = (volatile signed __int32 *)(v10(&ATL::g_strmgr) + 24);
    if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
            (void *const *)&v39,
            (__int64)L"error") )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v39, L"error", 5);
    v29 = Utils::GetJsonDataAsString(pExceptionObject, (__int64)v5, (_WORD **)&v39);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      (_QWORD *)(a1 + 64),
      v29);
    v30 = (_QWORD *)(pExceptionObject[0] - 24LL);
    if ( _InterlockedDecrement((volatile signed __int32 *)(pExceptionObject[0] - 24LL + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v30 + 8LL))(*v30);
    v31 = v39 - 6;
    if ( _InterlockedDecrement(v39 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v31 + 8LL))(*(_QWORD *)v31);
    v39 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
            (void *const *)&v39,
            (__int64)L"error_description") )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v39, L"error_description", 17);
    v32 = Utils::GetJsonDataAsString(pExceptionObject, (__int64)v5, (_WORD **)&v39);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      (_QWORD *)(a1 + 72),
      v32);
    v33 = (_QWORD *)(pExceptionObject[0] - 24LL);
    if ( _InterlockedDecrement((volatile signed __int32 *)(pExceptionObject[0] - 24LL + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v33 + 8LL))(*v33);
    v34 = v39 - 6;
    if ( _InterlockedDecrement(v39 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v34 + 8LL))(*(_QWORD *)v34);
    v39 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
            (void *const *)&v39,
            (__int64)L"correlation_id") )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v39, L"correlation_id", 14);
    v35 = Utils::GetJsonDataAsString(pExceptionObject, (__int64)v5, (_WORD **)&v39);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      (_QWORD *)(a1 + 80),
      v35);
    v36 = (_QWORD *)(pExceptionObject[0] - 24LL);
    if ( _InterlockedDecrement((volatile signed __int32 *)(pExceptionObject[0] - 24LL + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v36 + 8LL))(*v36);
    v28 = v39;
  }
  v37 = v28 - 6;
  if ( _InterlockedDecrement(v37 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v37 + 8LL))(*(_QWORD *)v37);
  (**(void (__fastcall ***)(JsonObject *, __int64))v5)(v5, 1);
  std::deque<JsonValue *>::_Tidy(Block);
  v38 = Block[0];
  Block[0] = 0;
  operator delete(v38);
}

```

## disassembly

```asm
0x1400251d4  mov     [rsp-8+arg_10], rbx
0x1400251d9  mov     [rsp-8+arg_18], rsi
0x1400251de  push    rbp
0x1400251df  push    rdi
0x1400251e0  push    r13
0x1400251e2  push    r14
0x1400251e4  push    r15
0x1400251e6  lea     rbp, [rsp-37h]
0x1400251eb  sub     rsp, 0C0h
0x1400251f2  mov     rax, cs:__security_cookie
0x1400251f9  xor     rax, rsp
0x1400251fc  mov     [rbp+57h+var_28], rax
0x140025200  mov     rbx, rdx
0x140025203  mov     rdi, rcx
0x140025206  lea     rcx, [rbp+57h+Block]; this
0x14002520a  call    ??0JsonReader@@QEAA@XZ; JsonReader::JsonReader(void)
0x14002520f  nop
0x140025210  mov     rdx, [rbx]
0x140025213  lea     rcx, [rbp+57h+var_48]
0x140025217  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14002521c  nop
0x14002521d  mov     rdx, rax
0x140025220  lea     rcx, [rbp+57h+Block]; this
0x140025224  call    ?Parse@JsonReader@@QEAAPEAVJsonValue@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; JsonReader::Parse(std::wstring const &)
0x140025229  mov     rbx, rax
0x14002522c  mov     [rbp+57h+var_88], rax
0x140025230  lea     rcx, [rbp+57h+var_48]
0x140025234  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025239  xor     r14d, r14d
0x14002523c  test    rbx, rbx
0x14002523f  jz      loc_1400259E8
0x140025245  cmp     dword ptr [rbx+8], 1
0x140025249  jnz     loc_1400259E8
0x14002524f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140025256  lea     r13, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14002525d  mov     rcx, r13
0x140025260  mov     rax, [rax+18h]
0x140025264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025269  add     rax, 18h
0x14002526d  mov     [rbp+57h+var_C0], rax
0x140025271  lea     rdx, aAccessToken; "access_token"
0x140025278  lea     rcx, [rbp+57h+var_C0]
0x14002527c  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140025281  test    al, al
0x140025283  jnz     short loc_14002529A
0x140025285  lea     r8d, [r14+0Ch]
0x140025289  lea     rdx, aAccessToken; "access_token"
0x140025290  lea     rcx, [rbp+57h+var_C0]
0x140025294  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140025299  nop
0x14002529a  lea     r8, [rbp+57h+var_C0]
0x14002529e  mov     rdx, rbx
0x1400252a1  lea     rcx, [rbp+57h+var_A8]
0x1400252a5  call    ?GetJsonDataAsString@Utils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBVJsonObject@@AEBV23@@Z; Utils::GetJsonDataAsString(JsonObject const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400252aa  nop
0x1400252ab  mov     rdx, [rax]
0x1400252ae  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400252b2  test    rdx, rdx
0x1400252b5  jnz     short loc_1400252BC
0x1400252b7  mov     r8d, r14d
0x1400252ba  jmp     short loc_1400252C9
0x1400252bc  mov     r8, r15
0x1400252bf  inc     r8
0x1400252c2  cmp     [rdx+r8*2], r14w
0x1400252c7  jnz     short loc_1400252BF
0x1400252c9  lea     rcx, [rdi+28h]
0x1400252cd  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400252d2  nop
0x1400252d3  mov     rdx, [rbp+57h+var_A8]
0x1400252d7  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400252db  mov     eax, r15d
0x1400252de  lock xadd [rdx+10h], eax
0x1400252e3  add     eax, r15d
0x1400252e6  test    eax, eax
0x1400252e8  jg      short loc_1400252FA
0x1400252ea  mov     rcx, [rdx]
0x1400252ed  mov     rax, [rcx]
0x1400252f0  mov     rax, [rax+8]
0x1400252f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400252f9  nop
0x1400252fa  mov     rdx, [rbp+57h+var_C0]
0x1400252fe  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140025302  mov     eax, r15d
0x140025305  lock xadd [rdx+10h], eax
0x14002530a  add     eax, r15d
0x14002530d  test    eax, eax
0x14002530f  jg      short loc_140025320
0x140025311  mov     rcx, [rdx]
0x140025314  mov     rax, [rcx]
0x140025317  mov     rax, [rax+8]
0x14002531b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025320  mov     rax, [rdi+28h]
0x140025324  mov     rcx, r13
0x140025327  cmp     [rax-10h], r14d
0x14002532b  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140025332  mov     rax, [rax+18h]
0x140025336  jz      loc_140025786
0x14002533c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025341  add     rax, 18h
0x140025345  mov     [rbp+57h+var_C0], rax
0x140025349  lea     rdx, aRefreshToken; "refresh_token"
0x140025350  lea     rcx, [rbp+57h+var_C0]
0x140025354  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140025359  test    al, al
0x14002535b  jnz     short loc_140025374
0x14002535d  mov     r8d, 0Dh
0x140025363  lea     rdx, aRefreshToken; "refresh_token"
0x14002536a  lea     rcx, [rbp+57h+var_C0]
0x14002536e  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140025373  nop
0x140025374  lea     r8, [rbp+57h+var_C0]
0x140025378  mov     rdx, rbx
0x14002537b  lea     rcx, [rbp+57h+pExceptionObject]
0x14002537f  call    ?GetJsonDataAsString@Utils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBVJsonObject@@AEBV23@@Z; Utils::GetJsonDataAsString(JsonObject const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140025384  nop
0x140025385  mov     rdx, [rax]
0x140025388  lea     rcx, [rdi+30h]
0x14002538c  test    rdx, rdx
0x14002538f  jnz     short loc_140025396
0x140025391  mov     r8d, r14d
0x140025394  jmp     short loc_1400253A3
0x140025396  mov     r8, r15
0x140025399  inc     r8
0x14002539c  cmp     [rdx+r8*2], r14w
0x1400253a1  jnz     short loc_140025399
0x1400253a3  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400253a8  nop
0x1400253a9  mov     rdx, [rbp+57h+pExceptionObject]
0x1400253ad  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400253b1  mov     eax, r15d
0x1400253b4  lock xadd [rdx+10h], eax
0x1400253b9  add     eax, r15d
0x1400253bc  test    eax, eax
0x1400253be  jg      short loc_1400253D0
0x1400253c0  mov     rcx, [rdx]
0x1400253c3  mov     rax, [rcx]
0x1400253c6  mov     rax, [rax+8]
0x1400253ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400253cf  nop
0x1400253d0  mov     rdx, [rbp+57h+var_C0]
0x1400253d4  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400253d8  mov     eax, r15d
0x1400253db  lock xadd [rdx+10h], eax
0x1400253e0  add     eax, r15d
0x1400253e3  test    eax, eax
0x1400253e5  jg      short loc_1400253F6
0x1400253e7  mov     rcx, [rdx]
0x1400253ea  mov     rax, [rcx]
0x1400253ed  mov     rax, [rax+8]
0x1400253f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400253f6  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400253fd  mov     rcx, r13
0x140025400  mov     rax, [rax+18h]
0x140025404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025409  add     rax, 18h
0x14002540d  mov     [rbp+57h+var_C0], rax
0x140025411  lea     rdx, aExpiresIn; "expires_in"
0x140025418  lea     rcx, [rbp+57h+var_C0]
0x14002541c  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140025421  test    al, al
0x140025423  jnz     short loc_14002543C
0x140025425  mov     r8d, 0Ah
0x14002542b  lea     rdx, aExpiresIn; "expires_in"
0x140025432  lea     rcx, [rbp+57h+var_C0]
0x140025436  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14002543b  nop
0x14002543c  lea     r8, [rbp+57h+var_C0]
0x140025440  mov     rdx, rbx
0x140025443  lea     rcx, [rbp+57h+var_A8]
0x140025447  call    ?GetJsonDataAsString@Utils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBVJsonObject@@AEBV23@@Z; Utils::GetJsonDataAsString(JsonObject const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14002544c  nop
0x14002544d  mov     rdx, [rbp+57h+var_C0]
0x140025451  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140025455  mov     eax, r15d
0x140025458  lock xadd [rdx+10h], eax
0x14002545d  add     eax, r15d
0x140025460  test    eax, eax
0x140025462  jg      short loc_140025473
0x140025464  mov     rcx, [rdx]
0x140025467  mov     rax, [rcx]
0x14002546a  mov     rax, [rax+8]
0x14002546e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025473  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14002547a  mov     rcx, r13
0x14002547d  mov     rax, [rax+18h]
0x140025481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025486  add     rax, 18h
0x14002548a  mov     [rbp+57h+var_C0], rax
0x14002548e  lea     rdx, aResource; "resource"
0x140025495  lea     rcx, [rbp+57h+var_C0]
0x140025499  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14002549e  test    al, al
0x1400254a0  jnz     short loc_1400254B9
0x1400254a2  mov     r8d, 8
0x1400254a8  lea     rdx, aResource; "resource"
0x1400254af  lea     rcx, [rbp+57h+var_C0]
0x1400254b3  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400254b8  nop
0x1400254b9  lea     r8, [rbp+57h+var_C0]
0x1400254bd  mov     rdx, rbx
0x1400254c0  lea     rcx, [rbp+57h+var_90]
0x1400254c4  call    ?GetJsonDataAsString@Utils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBVJsonObject@@AEBV23@@Z; Utils::GetJsonDataAsString(JsonObject const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400254c9  nop
0x1400254ca  mov     rdx, [rbp+57h+var_C0]
0x1400254ce  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400254d2  mov     eax, r15d
0x1400254d5  lock xadd [rdx+10h], eax
0x1400254da  add     eax, r15d
0x1400254dd  test    eax, eax
0x1400254df  jg      short loc_1400254F0
0x1400254e1  mov     rcx, [rdx]
0x1400254e4  mov     rax, [rcx]
0x1400254e7  mov     rax, [rax+8]
0x1400254eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400254f0  mov     rax, [rbp+57h+var_90]
0x1400254f4  cmp     [rax-10h], r14d
0x1400254f8  setnz   al
0x1400254fb  mov     [rdi+58h], al
0x1400254fe  mov     rcx, [rbp+57h+var_A8]
0x140025502  cmp     [rcx-10h], r14d
0x140025506  jnz     short loc_14002550D
0x140025508  mov     esi, r14d
0x14002550b  jmp     short loc_140025515
0x14002550d  call    cs:__imp__o__wtol
0x140025513  mov     esi, eax
0x140025515  xor     ecx, ecx; Time
0x140025517  call    cs:__imp__time64
0x14002551d  movsxd  rcx, esi
0x140025520  add     rax, rcx
0x140025523  mov     [rdi+38h], rax
0x140025527  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14002552e  mov     rcx, r13
0x140025531  mov     rax, [rax+18h]
0x140025535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002553a  add     rax, 18h
0x14002553e  mov     [rbp+57h+var_C0], rax
0x140025542  lea     rdx, aIdToken; "id_token"
0x140025549  lea     rcx, [rbp+57h+var_C0]
0x14002554d  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140025552  test    al, al
0x140025554  jnz     short loc_14002556D
0x140025556  mov     r8d, 8
0x14002555c  lea     rdx, aIdToken; "id_token"
0x140025563  lea     rcx, [rbp+57h+var_C0]
0x140025567  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14002556c  nop
0x14002556d  lea     r8, [rbp+57h+var_C0]
0x140025571  mov     rdx, rbx
0x140025574  lea     rcx, [rbp+57h+var_98]
0x140025578  call    ?GetJsonDataAsString@Utils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBVJsonObject@@AEBV23@@Z; Utils::GetJsonDataAsString(JsonObject const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14002557d  nop
0x14002557e  mov     rdx, [rbp+57h+var_C0]
0x140025582  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140025586  mov     eax, r15d
0x140025589  lock xadd [rdx+10h], eax
0x14002558e  add     eax, r15d
0x140025591  test    eax, eax
0x140025593  jg      short loc_1400255A4
0x140025595  mov     rcx, [rdx]
0x140025598  mov     rax, [rcx]
0x14002559b  mov     rax, [rax+8]
0x14002559f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400255a4  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400255ab  mov     rcx, r13
0x1400255ae  mov     rax, [rax+18h]
0x1400255b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400255b7  add     rax, 18h
0x1400255bb  mov     [rbp+57h+var_C0], rax
0x1400255bf  lea     rdx, aPwdUrl; "pwd_url"
0x1400255c6  lea     rcx, [rbp+57h+var_C0]
0x1400255ca  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x1400255cf  mov     esi, 7
0x1400255d4  test    al, al
0x1400255d6  jnz     short loc_1400255EC
0x1400255d8  mov     r8d, esi
0x1400255db  lea     rdx, aPwdUrl; "pwd_url"
0x1400255e2  lea     rcx, [rbp+57h+var_C0]
0x1400255e6  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400255eb  nop
0x1400255ec  lea     r8, [rbp+57h+var_C0]
0x1400255f0  mov     rdx, rbx
0x1400255f3  lea     rcx, [rbp+57h+pExceptionObject]
0x1400255f7  call    ?GetJsonDataAsString@Utils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBVJsonObject@@AEBV23@@Z; Utils::GetJsonDataAsString(JsonObject const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400255fc  nop
0x1400255fd  lea     rcx, [rdi+68h]
0x140025601  mov     rdx, rax
0x140025604  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140025609  nop
0x14002560a  mov     rdx, [rbp+57h+pExceptionObject]
0x14002560e  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140025612  mov     eax, r15d
0x140025615  lock xadd [rdx+10h], eax
0x14002561a  add     eax, r15d
0x14002561d  test    eax, eax
0x14002561f  jg      short loc_140025631
0x140025621  mov     rcx, [rdx]
0x140025624  mov     rax, [rcx]
0x140025627  mov     rax, [rax+8]
0x14002562b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025630  nop
  ... truncated ...
```
