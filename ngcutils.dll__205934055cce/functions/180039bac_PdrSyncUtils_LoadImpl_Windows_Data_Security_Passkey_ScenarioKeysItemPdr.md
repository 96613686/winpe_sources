# PdrSyncUtils::LoadImpl_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_

- ea: `0x180039bac`
- end: `0x18003a164`
- name: `PdrSyncUtils::LoadImpl_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_`
- size: `1464`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004a8c0`

## callees

- `0x1800012e4`
- `0x180001374`
- `0x180003080`
- `0x18000c95c`
- `0x18000ce74`
- `0x18000cfcc`
- `0x18001354c`
- `0x18001361c`
- `0x1800137a0`
- `0x18001addc`
- `0x180038f38`
- `0x180039bac`
- `0x180040d10`
- `0x180043f84`
- `0x18004f6ac`
- `0x180054c40`
- `0x180054ecc`
- `0x180061010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180039df4`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180039df4`
- `webauthn!WebAuthNWriteEventCloudStoreOperationFailure` at `0x180039f35`
- `webauthn!WebAuthNWriteEventCloudStoreOperationFailure` at `0x180039f35`
- `webauthn!WebAuthNWriteEventCloudStoreOperationSuccess` at `0x180039fde`
- `webauthn!WebAuthNWriteEventCloudStoreOperationSuccess` at `0x180039fde`

## string_xrefs

- `0x180039f49`: `onecore\ds\security\ngc\utils\pdr\lib\pdrsyncstore.cpp`
- `0x180039ff2`: `onecore\ds\security\ngc\utils\pdr\lib\pdrsyncstore.cpp`

## pseudocode

```c
__int64 __fastcall PdrSyncUtils::LoadImpl_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_(
        __int64 a1,
        _QWORD *a2,
        unsigned int *a3,
        _QWORD *a4,
        _QWORD *a5,
        _QWORD *a6,
        __int64 *a7)
{
  __int64 v10; // r12
  __int64 v11; // rax
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  _QWORD *v15; // rax
  _QWORD *v16; // rax
  __int64 v17; // rax
  _QWORD *v18; // r9
  __int64 v19; // rax
  const char *v20; // rcx
  volatile signed __int32 *v21; // rdi
  __int64 v22; // xmm6_8
  __int64 v23; // rcx
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  volatile signed __int32 *v27; // rbx
  int v28; // r14d
  __int128 *v29; // rax
  __int128 *v30; // rbx
  __int128 *v31; // r8
  int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int128 *v35; // rbx
  __int128 *v36; // r8
  int v37; // eax
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // rdx
  __int64 v48; // r8
  volatile signed __int32 *v49; // rbx
  __int64 *v50; // rcx
  __int64 v51; // rdx
  int v53; // [rsp+28h] [rbp-E0h]
  _QWORD *v54; // [rsp+48h] [rbp-C0h] BYREF
  __int128 *v55; // [rsp+58h] [rbp-B0h]
  __int128 v56; // [rsp+68h] [rbp-A0h] BYREF
  int v57[2]; // [rsp+78h] [rbp-90h] BYREF
  const char *v58; // [rsp+80h] [rbp-88h] BYREF
  __int128 *v59; // [rsp+88h] [rbp-80h] BYREF
  _QWORD *v60; // [rsp+90h] [rbp-78h]
  __int64 v61; // [rsp+98h] [rbp-70h]
  unsigned int *v62; // [rsp+A0h] [rbp-68h]
  __int64 v63; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v64; // [rsp+B0h] [rbp-58h]
  __int64 v65; // [rsp+B8h] [rbp-50h]
  __int64 v66; // [rsp+C8h] [rbp-40h]
  _QWORD *v67; // [rsp+D0h] [rbp-38h]
  __int64 v68; // [rsp+D8h] [rbp-30h]
  __int128 v69; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v70; // [rsp+F0h] [rbp-18h]
  __int128 v71; // [rsp+100h] [rbp-8h] BYREF
  __int128 v72; // [rsp+110h] [rbp+8h]
  _QWORD v73[3]; // [rsp+120h] [rbp+18h] BYREF
  unsigned __int64 v74; // [rsp+138h] [rbp+30h]
  __int128 v75; // [rsp+148h] [rbp+40h] BYREF
  __int64 v76; // [rsp+158h] [rbp+50h]
  __int64 v77; // [rsp+160h] [rbp+58h]
  _BYTE v78[32]; // [rsp+168h] [rbp+60h] BYREF
  char v79[32]; // [rsp+188h] [rbp+80h] BYREF
  char v80[32]; // [rsp+1A8h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+230h] [rbp+128h]

  v62 = a3;
  v66 = a1;
  v67 = a2;
  v60 = a6;
  v68 = (__int64)a7;
  v10 = *a6;
  v11 = -1;
  do
    ++v11;
  while ( *(_BYTE *)(v10 + v11) );
  *(_QWORD *)&v56 = *a6;
  *((_QWORD *)&v56 + 1) = v11;
  FidoUtils::ExtendCorrelationVector(v73, &v56);
  if ( (unsigned int)dword_180075000 > 4 )
  {
    v15 = v73;
    if ( v74 > 0xF )
      v15 = (_QWORD *)v73[0];
    v54 = v15;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v12,
      (unsigned int)byte_180069B93,
      v13,
      v14,
      (__int64)&v54);
  }
  v55 = &v71;
  v71 = 0;
  v72 = 0u;
  std::wstring::_Construct<1,unsigned short const *>(&v71, L"default", 7);
  v59 = &v69;
  v69 = 0;
  v70 = 0u;
  std::wstring::_Construct<1,unsigned short const *>(&v69, *a4, a4[1]);
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v54 = (_QWORD *)*a5;
  v61 = a5[1];
  std::wstring::_Construct<1,unsigned short const *>(&v75, v54, v61);
  wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>(
    v78,
    &v75,
    &v69,
    &v71);
  v16 = v73;
  if ( v74 > 0xF )
    v16 = (_QWORD *)v73[0];
  *(_QWORD *)&v56 = v16;
  *((_QWORD *)&v56 + 1) = v73[2];
  v17 = FidoUtils::IncrementCorrelationVector(&v75, &v56);
  std::string::operator=(v73, v17);
  std::string::~string(&v75);
  *(_QWORD *)v57 = 0;
  v18 = v73;
  if ( v74 > 0xF )
    LODWORD(v18) = v73[0];
  v19 = wil::ProfileDataStore::LoadAsync<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>(
          *a2,
          (unsigned int)&v58,
          (unsigned int)v78,
          (_DWORD)v18,
          (__int64)v57,
          34);
  wil::details::coro::task_base<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::get(
    v19,
    &v75);
  v20 = v58;
  v58 = 0;
  if ( v20 && _InterlockedExchange64((volatile __int64 *)v20 + 1, 2) )
  {
    *((_QWORD *)v20 + 7) |= 1uLL;
    (*((void (__fastcall **)(const char *))v20 + 6))(v20 + 48);
  }
  v56 = 0;
  v21 = (volatile signed __int32 *)*((_QWORD *)&v75 + 1);
  if ( *((_QWORD *)&v75 + 1) )
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v75 + 1) + 8LL));
  v22 = v75;
  v56 = v75;
  v55 = &v56;
  v23 = a7[7];
  if ( !v23 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(__int64, __int64 *, __int128 *))(*(_QWORD *)v23 + 16LL))(v23, &v63, &v56);
  v27 = (volatile signed __int32 *)*((_QWORD *)&v56 + 1);
  if ( *((_QWORD *)&v56 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v56 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
      if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
    }
  }
  v55 = (__int128 *)v22;
  v28 = *(_DWORD *)(v22 + 216);
  if ( v28 >= 0 )
  {
    v69 = 0;
    v70 = 0;
    std::string::_Construct<1,char const *>(&v69, v10, v60[1]);
    v35 = &v69;
    if ( *((_QWORD *)&v70 + 1) > 0xFu )
      v35 = (__int128 *)v69;
    v71 = 0;
    v72 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v71, v54, v61);
    v36 = &v71;
    if ( *((_QWORD *)&v72 + 1) > 7u )
      v36 = (__int128 *)v71;
    v37 = WebAuthNWriteEventCloudStoreOperationSuccess(0, *v62, v36, v35);
    if ( v37 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x67,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\pdr\\lib\\pdrsyncstore.cpp",
        (const char *)(unsigned int)v37,
        v53);
    std::wstring::~wstring(&v71, v38, v39);
    std::string::~string(&v69);
    v28 = 0;
  }
  else
  {
    if ( (unsigned int)dword_180075000 > 4 )
    {
      v58 = "ProfileDataStore::LoadAsync";
      v29 = (__int128 *)v73;
      if ( v74 > 0xF )
        v29 = (__int128 *)v73[0];
      v59 = v29;
      v57[0] = v28;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v24,
        (unsigned int)&byte_180069A8F,
        v25,
        v26,
        (__int64)v57,
        (__int64)&v59,
        (__int64)&v58);
    }
    v71 = 0;
    v72 = 0;
    std::string::_Construct<1,char const *>(&v71, v10, v60[1]);
    v30 = &v71;
    if ( *((_QWORD *)&v72 + 1) > 0xFu )
      v30 = (__int128 *)v71;
    v69 = 0;
    v70 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v69, v54, v61);
    v31 = &v69;
    if ( *((_QWORD *)&v70 + 1) > 7u )
      v31 = (__int128 *)v69;
    v32 = WebAuthNWriteEventCloudStoreOperationFailure(0, *v62, v31, v30);
    if ( v32 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5F,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\pdr\\lib\\pdrsyncstore.cpp",
        (const char *)(unsigned int)v32,
        v28);
    std::wstring::~wstring(&v69, v33, v34);
    std::string::~string(&v71);
  }
  *(_DWORD *)a1 = v28;
  *(_DWORD *)(a1 + 4) = 0;
  v40 = v65;
  v65 = 0;
  v41 = v64;
  v64 = 0;
  v42 = v63;
  v63 = 0;
  *(_QWORD *)(a1 + 8) = v42;
  *(_QWORD *)(a1 + 16) = v41;
  *(_QWORD *)(a1 + 24) = v40;
  std::wstring::wstring(a1 + 32, (char *)v55 + 184);
  std::vector<unsigned char>::~vector<unsigned char>(&v63);
  if ( v21 )
  {
    if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
      if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
    }
  }
  std::wstring::~wstring(v80, v43, v44);
  std::wstring::~wstring(v79, v45, v46);
  std::wstring::~wstring(v78, v47, v48);
  std::string::~string(v73);
  v49 = (volatile signed __int32 *)a2[1];
  if ( v49 )
  {
    if ( _InterlockedExchangeAdd(v49 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v49)(v49);
      if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
    }
  }
  v50 = (__int64 *)a7[7];
  if ( v50 )
  {
    v51 = *v50;
    LOBYTE(v51) = v50 != a7;
    (*(void (__fastcall **)(__int64 *, __int64))(*v50 + 32))(v50, v51);
    a7[7] = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180039bac  mov     rax, rsp
0x180039baf  push    rbp
0x180039bb0  push    rbx
0x180039bb1  push    rsi
0x180039bb2  push    rdi
0x180039bb3  push    r12
0x180039bb5  push    r13
0x180039bb7  push    r14
0x180039bb9  push    r15
0x180039bbb  lea     rbp, [rax-128h]
0x180039bc2  sub     rsp, 1E8h
0x180039bc9  movaps  xmmword ptr [rax-58h], xmm6
0x180039bcd  mov     rax, cs:__security_cookie
0x180039bd4  xor     rax, rsp
0x180039bd7  mov     [rbp+120h+var_60], rax
0x180039bde  mov     rbx, r9
0x180039be1  mov     [rbp+120h+var_188], r8
0x180039be5  mov     r13, rdx
0x180039be8  mov     rsi, rcx
0x180039beb  mov     [rbp+120h+var_160], rcx
0x180039bef  mov     [rbp+120h+var_158], rdx
0x180039bf3  mov     rdi, [rbp+120h+arg_20]
0x180039bfa  mov     rax, [rbp+120h+arg_28]
0x180039c01  mov     [rbp+120h+var_198], rax
0x180039c05  mov     r15, [rbp+120h+arg_30]
0x180039c0c  mov     [rbp+120h+var_150], r15
0x180039c10  xor     r14d, r14d
0x180039c13  mov     r12, [rax]
0x180039c16  or      rax, 0FFFFFFFFFFFFFFFFh
0x180039c1a  inc     rax
0x180039c1d  cmp     [r12+rax], r14b
0x180039c21  jnz     short loc_180039C1A
0x180039c23  mov     qword ptr [rsp+220h+var_1C8+8], r12
0x180039c28  mov     [rsp+220h+var_1B8], rax
0x180039c2d  lea     rdx, [rsp+220h+var_1C8+8]
0x180039c32  lea     rcx, [rbp+120h+var_108]
0x180039c36  call    ?ExtendCorrelationVector@FidoUtils@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_zstring_view@D@wil@@@Z; FidoUtils::ExtendCorrelationVector(wil::basic_zstring_view<char>)
0x180039c3b  nop
0x180039c3c  mov     eax, cs:dword_180075000
0x180039c42  cmp     eax, 4
0x180039c45  jbe     short loc_180039C70
0x180039c47  lea     rax, [rbp+120h+var_108]
0x180039c4b  cmp     [rbp+120h+var_F0], 0Fh
0x180039c50  cmova   rax, [rbp+120h+var_108]
0x180039c55  mov     [rsp+220h+var_1E0], rax
0x180039c5a  lea     rax, [rsp+220h+var_1E0]
0x180039c5f  mov     qword ptr [rsp+220h+var_200], rax
0x180039c64  lea     rdx, byte_180069B93
0x180039c6b  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180039c70  lea     rax, [rbp+120h+var_128]
0x180039c74  mov     [rsp+220h+var_1D0], rax
0x180039c79  xorps   xmm0, xmm0
0x180039c7c  movups  [rbp+120h+var_128], xmm0
0x180039c80  mov     qword ptr [rbp+120h+var_118], r14
0x180039c84  mov     qword ptr [rbp+120h+var_118+8], r14
0x180039c88  mov     r8d, 7
0x180039c8e  lea     rdx, sourceString; "default"
0x180039c95  lea     rcx, [rbp+120h+var_128]
0x180039c99  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180039c9e  nop
0x180039c9f  lea     rax, [rbp+120h+var_148]
0x180039ca3  mov     [rbp+120h+var_1A0], rax
0x180039ca7  xorps   xmm0, xmm0
0x180039caa  movups  [rbp+120h+var_148], xmm0
0x180039cae  mov     qword ptr [rbp+120h+var_138], r14
0x180039cb2  mov     qword ptr [rbp+120h+var_138+8], r14
0x180039cb6  mov     r8, [rbx+8]
0x180039cba  mov     rdx, [rbx]
0x180039cbd  lea     rcx, [rbp+120h+var_148]
0x180039cc1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180039cc6  nop
0x180039cc7  xorps   xmm0, xmm0
0x180039cca  movups  [rbp+120h+var_E0], xmm0
0x180039cce  mov     [rbp+120h+var_D0], r14
0x180039cd2  mov     [rbp+120h+var_C8], r14
0x180039cd6  mov     rax, [rdi]
0x180039cd9  mov     [rsp+220h+var_1E0], rax
0x180039cde  mov     rcx, [rdi+8]
0x180039ce2  mov     [rbp+120h+var_190], rcx
0x180039ce6  mov     r8, rcx
0x180039ce9  mov     rdx, rax
0x180039cec  lea     rcx, [rbp+120h+var_E0]
0x180039cf0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180039cf5  nop
0x180039cf6  lea     r9, [rbp+120h+var_128]
0x180039cfa  lea     r8, [rbp+120h+var_148]
0x180039cfe  lea     rdx, [rbp+120h+var_E0]
0x180039d02  lea     rcx, [rbp+120h+var_C0]
0x180039d06  call    ??0?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z; wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>(std::wstring,std::wstring,std::wstring)
0x180039d0b  nop
0x180039d0c  mov     rcx, [rbp+120h+var_F8]
0x180039d10  lea     rax, [rbp+120h+var_108]
0x180039d14  cmp     [rbp+120h+var_F0], 0Fh
0x180039d19  cmova   rax, [rbp+120h+var_108]
0x180039d1e  mov     qword ptr [rsp+220h+var_1C8+8], rax
0x180039d23  mov     [rsp+220h+var_1B8], rcx
0x180039d28  lea     rdx, [rsp+220h+var_1C8+8]
0x180039d2d  lea     rcx, [rbp+120h+var_E0]
0x180039d31  call    ?IncrementCorrelationVector@FidoUtils@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_zstring_view@D@wil@@@Z; FidoUtils::IncrementCorrelationVector(wil::basic_zstring_view<char>)
0x180039d36  mov     rdx, rax
0x180039d39  lea     rcx, [rbp+120h+var_108]
0x180039d3d  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180039d42  lea     rcx, [rbp+120h+var_E0]
0x180039d46  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180039d4b  mov     qword ptr [rsp+220h+var_1B0], r14
0x180039d50  lea     r9, [rbp+120h+var_108]
0x180039d54  cmp     [rbp+120h+var_F0], 0Fh
0x180039d59  cmova   r9, [rbp+120h+var_108]
0x180039d5e  mov     dword ptr [rsp+220h+var_1F8], 22h ; '"'
0x180039d66  lea     rax, [rsp+220h+var_1B0]
0x180039d6b  mov     qword ptr [rsp+220h+var_200], rax; int
0x180039d70  lea     r8, [rbp+120h+var_C0]
0x180039d74  lea     rdx, [rsp+220h+var_1A8]
0x180039d79  mov     rcx, [r13+0]
0x180039d7d  call    ??$LoadAsync@UScenarioKeysItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@QEAA?AU?$task@V?$shared_ptr@V?$ProfileDataItem@UScenarioKeysItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@1@AEBV?$ProfileDataItemReference@UScenarioKeysItemPdr@Passkey@Security@Data@Windows@@@1@PEBDVcancellation_token@Concurrency@@W4ProfileDataStoreLoadOptions@1@PEBG@Z; wil::ProfileDataStore::LoadAsync<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>(wil::ProfileDataItemReference<Windows::Data::Security::Passkey::ScenarioKeysItemPdr> const &,char const *,Concurrency::cancellation_token,wil::ProfileDataStoreLoadOptions,ushort const *)
0x180039d82  nop
0x180039d83  lea     rdx, [rbp+120h+var_E0]
0x180039d87  mov     rcx, rax
0x180039d8a  call    ?get@?$task_base@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@coro@details@wil@@QEHAA@XZ; wil::details::coro::task_base<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::get(void)
0x180039d8f  nop
0x180039d90  mov     rcx, [rsp+220h+var_1A8]
0x180039d95  mov     [rsp+220h+var_1A8], r14
0x180039d9a  test    rcx, rcx
0x180039d9d  jz      short loc_180039DC1
0x180039d9f  mov     eax, 2
0x180039da4  xchg    rax, [rcx+8]
0x180039da8  test    rax, rax
0x180039dab  jz      short loc_180039DC1
0x180039dad  lea     rax, [rcx+30h]
0x180039db1  or      qword ptr [rax+8], 1
0x180039db6  mov     rcx, rax
0x180039db9  mov     rax, [rax]
0x180039dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039dc1  xorps   xmm0, xmm0
0x180039dc4  movdqa  [rsp+220h+var_1C8+8], xmm0
0x180039dca  mov     rdi, qword ptr [rbp+120h+var_E0+8]
0x180039dce  test    rdi, rdi
0x180039dd1  jz      short loc_180039DD7
0x180039dd3  lock inc dword ptr [rdi+8]
0x180039dd7  movaps  xmm6, [rbp+120h+var_E0]
0x180039ddb  movdqa  [rsp+220h+var_1C8+8], xmm6
0x180039de1  lea     rax, [rsp+220h+var_1C8+8]
0x180039de6  mov     [rsp+220h+var_1D0], rax
0x180039deb  mov     rcx, [r15+38h]
0x180039def  test    rcx, rcx
0x180039df2  jnz     short loc_180039DFB
0x180039df4  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180039dfa  int     3; Trap to Debugger
0x180039dfb  mov     rax, [rcx]
0x180039dfe  lea     r8, [rsp+220h+var_1C8+8]
0x180039e03  lea     rdx, [rbp+120h+var_180]
0x180039e07  mov     rax, [rax+10h]
0x180039e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e10  nop
0x180039e11  mov     rbx, [rsp+220h+var_1B8]
0x180039e16  test    rbx, rbx
0x180039e19  jz      short loc_180039E53
0x180039e1b  or      eax, 0FFFFFFFFh
0x180039e1e  lock xadd [rbx+8], eax
0x180039e23  cmp     eax, 1
0x180039e26  jnz     short loc_180039E53
0x180039e28  mov     rax, [rbx]
0x180039e2b  mov     rcx, rbx
0x180039e2e  mov     rax, [rax]
0x180039e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e36  or      eax, 0FFFFFFFFh
0x180039e39  lock xadd [rbx+0Ch], eax
0x180039e3e  cmp     eax, 1
0x180039e41  jnz     short loc_180039E53
0x180039e43  mov     rax, [rbx]
0x180039e46  mov     rcx, rbx
0x180039e49  mov     rax, [rax+8]
0x180039e4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e52  nop
0x180039e53  movq    rax, xmm6
0x180039e58  mov     [rsp+220h+var_1D0], rax
0x180039e5d  mov     r14d, [rax+0D8h]
0x180039e64  test    r14d, r14d
0x180039e67  jns     loc_180039F72
0x180039e6d  mov     eax, cs:dword_180075000
0x180039e73  cmp     eax, 4
0x180039e76  jbe     short loc_180039EC4
0x180039e78  lea     rax, aProfiledatasto; "ProfileDataStore::LoadAsync"
0x180039e7f  mov     [rsp+220h+var_1A8], rax
0x180039e84  lea     rax, [rbp+120h+var_108]
0x180039e88  cmp     [rbp+120h+var_F0], 0Fh
0x180039e8d  cmova   rax, [rbp+120h+var_108]
0x180039e92  mov     [rbp+120h+var_1A0], rax
0x180039e96  mov     [rsp+220h+var_1B0], r14d
0x180039e9b  lea     rax, [rsp+220h+var_1A8]
0x180039ea0  mov     [rsp+30h], rax
0x180039ea5  lea     rax, [rbp+120h+var_1A0]
0x180039ea9  mov     [rsp+220h+var_1F8], rax
0x180039eae  lea     rax, [rsp+220h+var_1B0]
0x180039eb3  mov     qword ptr [rsp+220h+var_200], rax
0x180039eb8  lea     rdx, byte_180069A8F
0x180039ebf  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180039ec4  xorps   xmm0, xmm0
0x180039ec7  movups  [rbp+120h+var_128], xmm0
0x180039ecb  xorps   xmm1, xmm1
0x180039ece  movdqu  [rbp+120h+var_118], xmm1
0x180039ed3  mov     r8, [rbp+120h+var_198]
0x180039ed7  mov     r8, [r8+8]
0x180039edb  mov     rdx, r12
0x180039ede  lea     rcx, [rbp+120h+var_128]
0x180039ee2  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180039ee7  nop
0x180039ee8  lea     rbx, [rbp+120h+var_128]
0x180039eec  cmp     qword ptr [rbp+120h+var_118+8], 0Fh
0x180039ef1  cmova   rbx, qword ptr [rbp+120h+var_128]
0x180039ef6  xorps   xmm0, xmm0
0x180039ef9  movups  [rbp+120h+var_148], xmm0
0x180039efd  xorps   xmm1, xmm1
0x180039f00  movdqu  [rbp+120h+var_138], xmm1
0x180039f05  mov     r8, [rbp+120h+var_190]
0x180039f09  mov     rdx, [rsp+220h+var_1E0]
0x180039f0e  lea     rcx, [rbp+120h+var_148]
0x180039f12  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180039f17  lea     r8, [rbp+120h+var_148]
0x180039f1b  cmp     qword ptr [rbp+120h+var_138+8], 7
0x180039f20  cmova   r8, qword ptr [rbp+120h+var_148]
0x180039f25  mov     [rsp+220h+var_200], r14d; int
0x180039f2a  mov     r9, rbx
0x180039f2d  mov     rdx, [rbp+120h+var_188]
0x180039f31  mov     edx, [rdx]
0x180039f33  xor     ecx, ecx
0x180039f35  call    cs:__imp_WebAuthNWriteEventCloudStoreOperationFailure
0x180039f3b  mov     rcx, [rbp+128h]; this
0x180039f42  test    eax, eax
0x180039f44  jns     short loc_180039F5A
0x180039f46  mov     r9d, eax; char *
0x180039f49  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\ngc\\utils\\pdr"...
0x180039f50  mov     edx, 5Fh ; '_'; void *
0x180039f55  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180039f5a  lea     rcx, [rbp+120h+var_148]
0x180039f5e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180039f63  nop
0x180039f64  lea     rcx, [rbp+120h+var_128]
0x180039f68  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180039f6d  jmp     loc_18003A019
0x180039f72  xorps   xmm0, xmm0
0x180039f75  movups  [rbp+120h+var_148], xmm0
0x180039f79  xorps   xmm1, xmm1
0x180039f7c  movdqu  [rbp+120h+var_138], xmm1
0x180039f81  mov     r8, [rbp+120h+var_198]
0x180039f85  mov     r8, [r8+8]
0x180039f89  mov     rdx, r12
0x180039f8c  lea     rcx, [rbp+120h+var_148]
0x180039f90  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180039f95  nop
0x180039f96  lea     rbx, [rbp+120h+var_148]
0x180039f9a  cmp     qword ptr [rbp+120h+var_138+8], 0Fh
0x180039f9f  cmova   rbx, qword ptr [rbp+120h+var_148]
0x180039fa4  xorps   xmm0, xmm0
0x180039fa7  movups  [rbp+120h+var_128], xmm0
0x180039fab  xorps   xmm1, xmm1
0x180039fae  movdqu  [rbp+120h+var_118], xmm1
0x180039fb3  mov     r8, [rbp+120h+var_190]
0x180039fb7  mov     rdx, [rsp+220h+var_1E0]
0x180039fbc  lea     rcx, [rbp+120h+var_128]
0x180039fc0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180039fc5  lea     r8, [rbp+120h+var_128]
0x180039fc9  cmp     qword ptr [rbp+120h+var_118+8], 7
0x180039fce  cmova   r8, qword ptr [rbp+120h+var_128]
0x180039fd3  mov     r9, rbx
0x180039fd6  mov     rdx, [rbp+120h+var_188]
0x180039fda  mov     edx, [rdx]
0x180039fdc  xor     ecx, ecx
0x180039fde  call    cs:__imp_WebAuthNWriteEventCloudStoreOperationSuccess
0x180039fe4  mov     rcx, [rbp+128h]; this
0x180039feb  test    eax, eax
0x180039fed  jns     short loc_18003A003
0x180039fef  mov     r9d, eax; char *
0x180039ff2  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\ngc\\utils\\pdr"...
0x180039ff9  mov     edx, 67h ; 'g'; void *
0x180039ffe  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003a003  lea     rcx, [rbp+120h+var_128]
0x18003a007  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003a00c  nop
0x18003a00d  lea     rcx, [rbp+120h+var_148]
0x18003a011  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18003a016  xor     r14d, r14d
0x18003a019  mov     [rsi], r14d
0x18003a01c  xor     eax, eax
0x18003a01e  mov     [rsi+4], eax
0x18003a021  mov     rdx, [rbp+120h+var_170]
0x18003a025  mov     [rbp+120h+var_170], rax
0x18003a029  mov     rcx, [rbp+120h+var_178]
0x18003a02d  mov     [rbp+120h+var_178], rax
0x18003a031  mov     rax, [rbp+120h+var_180]
0x18003a035  mov     [rbp+120h+var_180], 0
0x18003a03d  mov     [rsi+8], rax
0x18003a041  mov     [rsi+10h], rcx
0x18003a045  mov     [rsi+18h], rdx
0x18003a049  lea     rcx, [rsi+20h]
0x18003a04d  mov     rdx, [rsp+220h+var_1D0]
0x18003a052  add     rdx, 0B8h
0x18003a059  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003a05e  nop
0x18003a05f  lea     rcx, [rbp+120h+var_180]
  ... truncated ...
```
