# PdrSyncUtils::GetCollectionIdsImpl<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>(std::shared_ptr<wil::ProfileDataStore>,NgcPasskeys::SyncStore::PropertyType const &,std::basic_string_view<ushort,std::char_traits<ushort>>,std::basic_string_view<char,std::char_traits<char>>,std::basic_string_view<ushort,std::char_traits<ushort>>)

- ea: `0x18003275c`
- end: `0x180032e44`
- name: `??$GetCollectionIdsImpl@UScenarioKeysItemPdr@Passkey@Security@Data@Windows@@@PdrSyncUtils@@YA?AUCollectionIdsResult@SyncStore@NgcPasskeys@@V?$shared_ptr@VProfileDataStore@wil@@@std@@AEBW4PropertyType@23@V?$basic_string_view@GU?$char_traits@G@std@@@5@V?$basic_string_view@DU?$char_traits@D@std@@@5@2@Z`
- size: `1768`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callers

- `0x180049330`

## callees

- `0x1800012e4`
- `0x180001374`
- `0x180003080`
- `0x180003568`
- `0x180003bc8`
- `0x18000c95c`
- `0x18000ce74`
- `0x1800129f4`
- `0x18001354c`
- `0x18001361c`
- `0x1800137a0`
- `0x180013834`
- `0x180013b94`
- `0x18001addc`
- `0x18003275c`
- `0x180033af0`
- `0x180040d10`
- `0x18004ead4`
- `0x18004f554`
- `0x180054c40`
- `0x180054ecc`
- `0x180061010`

## import_xrefs

- `webauthn!WebAuthNWriteEventCloudStoreOperationFailure` at `0x180032caa`
- `webauthn!WebAuthNWriteEventCloudStoreOperationFailure` at `0x180032caa`
- `webauthn!WebAuthNWriteEventCloudStoreOperationSuccess` at `0x180032d1f`
- `webauthn!WebAuthNWriteEventCloudStoreOperationSuccess` at `0x180032d1f`

## string_xrefs

- `0x180032cbe`: `onecore\ds\security\ngc\utils\pdr\lib\pdrsyncstore.cpp`
- `0x180032d33`: `onecore\ds\security\ngc\utils\pdr\lib\pdrsyncstore.cpp`

## pseudocode

```c
int *__fastcall PdrSyncUtils::GetCollectionIdsImpl<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>(
        int *a1,
        __int64 *a2,
        unsigned int *a3,
        _QWORD *a4,
        _QWORD *a5,
        _QWORD *a6)
{
  __int64 *v7; // rsi
  __int64 v8; // rax
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  const char *v12; // rax
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  __int128 *v16; // rcx
  int v17; // r13d
  __m128i si128; // xmm6
  _QWORD *v19; // rax
  __int64 v20; // rax
  __int64 v21; // r15
  __int128 *v22; // r12
  __int128 *v23; // rsi
  _QWORD *v24; // rbx
  _QWORD *v25; // rdi
  volatile signed __int32 *v26; // rcx
  __int64 v27; // rbx
  int v28; // edi
  __int64 v29; // rdx
  __int64 v30; // r8
  int v31; // r8d
  int v32; // r9d
  const char *v33; // rcx
  volatile signed __int32 *v34; // rax
  __int64 i; // rbx
  __int64 v36; // r8
  __m128i *v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // r8
  int v40; // ecx
  int v41; // r8d
  int v42; // r9d
  volatile signed __int32 *v43; // rax
  __int128 *v44; // r9
  int v45; // eax
  __int128 *v46; // r9
  int v47; // eax
  int *v48; // rsi
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // rax
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // rdx
  __int64 v55; // r8
  __int64 v56; // rdx
  __int64 v57; // r8
  volatile signed __int32 *v58; // rbx
  int v60; // [rsp+28h] [rbp-E0h]
  volatile signed __int32 *v61; // [rsp+48h] [rbp-C0h] BYREF
  const char *v62; // [rsp+50h] [rbp-B8h] BYREF
  char *v63; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v64; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v65; // [rsp+70h] [rbp-98h]
  _QWORD *v66; // [rsp+78h] [rbp-90h]
  unsigned int *v67; // [rsp+80h] [rbp-88h]
  __int64 *v68; // [rsp+88h] [rbp-80h]
  int v69; // [rsp+90h] [rbp-78h]
  int *v70; // [rsp+98h] [rbp-70h]
  int *v71; // [rsp+A0h] [rbp-68h]
  __int64 *v72; // [rsp+A8h] [rbp-60h]
  __int128 v73; // [rsp+B8h] [rbp-50h] BYREF
  __m128i v74; // [rsp+C8h] [rbp-40h]
  __int128 v75; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v76; // [rsp+E8h] [rbp-20h]
  _QWORD v77[3]; // [rsp+F8h] [rbp-10h] BYREF
  unsigned __int64 v78; // [rsp+110h] [rbp+8h]
  __int128 v79; // [rsp+118h] [rbp+10h] BYREF
  __int64 v80; // [rsp+128h] [rbp+20h]
  __int128 v81; // [rsp+130h] [rbp+28h] BYREF
  __int64 v82; // [rsp+140h] [rbp+38h]
  __int64 v83; // [rsp+148h] [rbp+40h]
  int v84; // [rsp+150h] [rbp+48h]
  __int64 v85; // [rsp+158h] [rbp+50h]
  __int128 v86; // [rsp+168h] [rbp+60h] BYREF
  __int128 v87; // [rsp+178h] [rbp+70h]
  __int128 v88; // [rsp+188h] [rbp+80h] BYREF
  __int128 v89; // [rsp+198h] [rbp+90h]
  _BYTE v90[24]; // [rsp+1A8h] [rbp+A0h] BYREF
  char v91[72]; // [rsp+1C0h] [rbp+B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+270h] [rbp+168h]

  v67 = a3;
  v7 = a2;
  v68 = a2;
  v70 = a1;
  v71 = a1;
  v72 = a2;
  v66 = a5;
  v69 = 0;
  v8 = -1;
  do
    ++v8;
  while ( *(_BYTE *)(*a5 + v8) );
  *(_QWORD *)&v73 = *a5;
  *((_QWORD *)&v73 + 1) = v8;
  FidoUtils::ExtendCorrelationVector(v77, &v73);
  if ( (unsigned int)dword_180075000 > 4 )
  {
    v12 = (const char *)v77;
    if ( v78 > 0xF )
      v12 = (const char *)v77[0];
    v62 = v12;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v9,
      (unsigned int)word_180069002,
      v10,
      v11,
      (__int64)&v62);
  }
  v88 = 0;
  v89 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v88, *a4, a4[1]);
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 7;
  LOWORD(v81) = 0;
  v84 = 0;
  v85 = 0;
  v13 = a6[1];
  if ( v13 )
  {
    v75 = 0;
    v76 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v75, *a6, v13);
    v16 = &v75;
    v17 = 2;
  }
  else
  {
    v73 = 0;
    v74 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v73, &String1, 0);
    v16 = &v73;
    v17 = 1;
  }
  v86 = *v16;
  v87 = v16[1];
  *((_QWORD *)v16 + 2) = 0;
  *((_QWORD *)v16 + 3) = 7;
  *(_WORD *)v16 = 0;
  if ( (v17 & 2) != 0 )
  {
    v17 &= ~2u;
    std::wstring::~wstring(&v75, v14, v15);
  }
  if ( (v17 & 1) != 0 )
  {
    v17 &= ~1u;
    std::wstring::~wstring(&v73, v14, v15);
  }
  v64 = 0;
  v65 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  do
  {
    v19 = v77;
    if ( v78 > 0xF )
      v19 = (_QWORD *)v77[0];
    *(_QWORD *)&v75 = v19;
    *((_QWORD *)&v75 + 1) = v77[2];
    v20 = FidoUtils::IncrementCorrelationVector(&v73, &v75);
    std::string::operator=(v77, v20);
    std::string::~string(&v73);
    v21 = *v7;
    v22 = &v86;
    if ( *((_QWORD *)&v87 + 1) > 7u )
      v22 = (__int128 *)v86;
    v23 = &v88;
    if ( *((_QWORD *)&v89 + 1) > 7u )
      v23 = (__int128 *)v88;
    v61 = 0;
    *(_QWORD *)&v73 = &v61;
    v24 = v77;
    if ( v78 > 0xF )
      v24 = (_QWORD *)v77[0];
    v25 = operator new(0x190u);
    v63 = (char *)(v25 + 14);
    v25[43] = v21;
    v25[44] = v24;
    v25[45] = v61;
    v61 = 0;
    v25[46] = v23;
    v25[47] = 34;
    v25[48] = v22;
    v25[14] = wil::ProfileDataStore::GetCollectionItemIdsAsync__ResumeCoro_1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_;
    *((_DWORD *)v25 + 30) = 65538;
    memset_0(v25, 0, 0x68u);
    v62 = (const char *)v25;
    *((_BYTE *)v25 + 336) = 0;
    wil::ProfileDataStore::GetCollectionItemIdsAsync__ResumeCoro_1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_(v25 + 14);
    v26 = v61;
    if ( v61 && _InterlockedExchangeAdd(v61 + 2, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
    v61 = 0;
    v27 = wil::details::coro::task_base<wil::GetCollectionItemIdsResult<Windows::Data::Security::Passkey::PasskeyItemPdr>>::get(
            &v62,
            v90);
    if ( &v79 != (__int128 *)v27 )
    {
      std::vector<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr>>::_Tidy(&v79);
      v79 = *(_OWORD *)v27;
      v80 = *(_QWORD *)(v27 + 16);
      *(_QWORD *)v27 = 0;
      *(_QWORD *)(v27 + 8) = 0;
      *(_QWORD *)(v27 + 16) = 0;
    }
    std::wstring::operator=(&v81, v27 + 24);
    v28 = *(_DWORD *)(v27 + 56);
    v84 = v28;
    v85 = *(_QWORD *)(v27 + 64);
    std::wstring::~wstring(v91, v29, v30);
    std::vector<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr>>::_Tidy(v90);
    v33 = v62;
    if ( v62 && _InterlockedExchange64((volatile __int64 *)v62 + 1, 2) )
    {
      *((_QWORD *)v33 + 15) |= 1uLL;
      (*((void (__fastcall **)(const char *))v33 + 14))(v33 + 112);
    }
    if ( v28 < 0 && (unsigned int)dword_180075000 > 4 )
    {
      v62 = "ProfileDataStore::GetCollectionItemIdsAsync";
      v34 = (volatile signed __int32 *)v77;
      if ( v78 > 0xF )
        v34 = (volatile signed __int32 *)v77[0];
      v61 = v34;
      LODWORD(v63) = v28;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)v33,
        (unsigned int)word_180068F22,
        v31,
        v32,
        (__int64)&v63,
        (__int64)&v61,
        (__int64)&v62);
    }
    for ( i = v79; i != *((_QWORD *)&v79 + 1); i += 96 )
    {
      std::wstring::wstring(&v73, i);
      v17 |= 0x38u;
      v37 = (__m128i *)*((_QWORD *)&v64 + 1);
      if ( *((_QWORD *)&v64 + 1) == v65 )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v64, *((_QWORD *)&v64 + 1), &v73);
      }
      else
      {
        **((_OWORD **)&v64 + 1) = v73;
        v37[1] = v74;
        v74 = si128;
        LOWORD(v73) = 0;
        *((_QWORD *)&v64 + 1) += 32LL;
      }
      std::wstring::~wstring(&v73, v37, v36);
    }
    std::wstring::wstring(&v73, &v81);
    v17 |= 0x40u;
    std::wstring::operator=(&v86, &v73);
    std::wstring::~wstring(&v73, v38, v39);
    if ( v84 < 0 )
      break;
    if ( v84 == 1638704 )
      break;
    v7 = v68;
  }
  while ( !v85 );
  if ( v28 >= 0 )
  {
    v75 = 0;
    v76 = 0;
    std::string::_Construct<1,char const *>(&v75, *v66, v66[1]);
    v46 = &v75;
    if ( *((_QWORD *)&v76 + 1) > 0xFu )
      v46 = (__int128 *)v75;
    v47 = WebAuthNWriteEventCloudStoreOperationSuccess(3, *v67, &String1, v46);
    if ( v47 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\pdr\\lib\\pdrsyncstore.cpp",
        (const char *)(unsigned int)v47,
        v60);
    std::string::~string(&v75);
    v28 = 0;
  }
  else
  {
    if ( (unsigned int)dword_180075000 > 4 )
    {
      v62 = "ProfileDataStore::GetCollectionItemIdsAsync";
      v43 = (volatile signed __int32 *)v77;
      if ( v78 > 0xF )
        v43 = (volatile signed __int32 *)v77[0];
      v61 = v43;
      LODWORD(v63) = v28;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v40,
        (unsigned int)word_180068F92,
        v41,
        v42,
        (__int64)&v63,
        (__int64)&v61,
        (__int64)&v62);
    }
    v75 = 0;
    v76 = 0;
    std::string::_Construct<1,char const *>(&v75, *v66, v66[1]);
    v44 = &v75;
    if ( *((_QWORD *)&v76 + 1) > 0xFu )
      v44 = (__int128 *)v75;
    v45 = WebAuthNWriteEventCloudStoreOperationFailure(3, *v67, &String1, v44);
    if ( v45 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x29E,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\pdr\\lib\\pdrsyncstore.cpp",
        (const char *)(unsigned int)v45,
        v28);
    std::string::~string(&v75);
  }
  v48 = v70;
  *v70 = v28;
  v48[1] = 0;
  v49 = v65;
  v65 = 0;
  v50 = *((_QWORD *)&v64 + 1);
  v51 = v64;
  v64 = 0u;
  *((_QWORD *)v48 + 1) = v51;
  *((_QWORD *)v48 + 2) = v50;
  *((_QWORD *)v48 + 3) = v49;
  std::wstring::wstring(v48 + 8, &v81);
  std::vector<std::wstring>::_Tidy(&v64);
  std::wstring::~wstring(&v86, v52, v53);
  std::wstring::~wstring(&v81, v54, v55);
  std::vector<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr>>::_Tidy(&v79);
  std::wstring::~wstring(&v88, v56, v57);
  std::string::~string(v77);
  v58 = (volatile signed __int32 *)v68[1];
  if ( v58 )
  {
    if ( _InterlockedExchangeAdd(v58 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v58)(v58);
      if ( _InterlockedExchangeAdd(v58 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v58 + 8LL))(v58);
    }
  }
  return v48;
}

```

## disassembly

```asm
0x18003275c  mov     rax, rsp
0x18003275f  push    rbp
0x180032760  push    rbx
0x180032761  push    rsi
0x180032762  push    rdi
0x180032763  push    r12
0x180032765  push    r13
0x180032767  push    r14
0x180032769  push    r15
0x18003276b  lea     rbp, [rax-168h]
0x180032772  sub     rsp, 228h
0x180032779  movaps  xmmword ptr [rax-58h], xmm6
0x18003277d  mov     rax, cs:__security_cookie
0x180032784  xor     rax, rsp
0x180032787  mov     [rbp+160h+var_60], rax
0x18003278e  mov     rdi, r9
0x180032791  mov     [rsp+260h+var_1E8], r8
0x180032796  mov     rsi, rdx
0x180032799  mov     [rbp+160h+var_1E0], rdx
0x18003279d  mov     [rbp+160h+var_1D0], rcx
0x1800327a1  mov     [rbp+160h+var_1C8], rcx
0x1800327a5  mov     [rbp+160h+var_1C0], rdx
0x1800327a9  mov     rax, [rbp+160h+arg_20]
0x1800327b0  mov     [rsp+260h+var_1F0], rax
0x1800327b5  mov     rbx, [rbp+160h+arg_28]
0x1800327bc  xor     r14d, r14d
0x1800327bf  mov     [rbp+160h+var_1D8], r14d
0x1800327c3  mov     rcx, [rax]
0x1800327c6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800327ca  inc     rax
0x1800327cd  cmp     [rcx+rax], r14b
0x1800327d1  jnz     short loc_1800327CA
0x1800327d3  mov     qword ptr [rbp+160h+var_1B0], rcx
0x1800327d7  mov     qword ptr [rbp+160h+var_1B0+8], rax
0x1800327db  lea     rdx, [rbp+160h+var_1B0]
0x1800327df  lea     rcx, [rbp+160h+var_170]
0x1800327e3  call    ?ExtendCorrelationVector@FidoUtils@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_zstring_view@D@wil@@@Z; FidoUtils::ExtendCorrelationVector(wil::basic_zstring_view<char>)
0x1800327e8  nop
0x1800327e9  mov     eax, cs:dword_180075000
0x1800327ef  cmp     eax, 4
0x1800327f2  jbe     short loc_18003281D
0x1800327f4  lea     rax, [rbp+160h+var_170]
0x1800327f8  cmp     [rbp+160h+var_158], 0Fh
0x1800327fd  cmova   rax, [rbp+160h+var_170]
0x180032802  mov     [rsp+260h+var_218], rax
0x180032807  lea     rax, [rsp+260h+var_218]
0x18003280c  mov     qword ptr [rsp+260h+var_240], rax
0x180032811  lea     rdx, word_180069002
0x180032818  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003281d  xorps   xmm0, xmm0
0x180032820  movups  [rbp+160h+var_E0], xmm0
0x180032827  xorps   xmm1, xmm1
0x18003282a  movdqu  [rbp+160h+var_D0], xmm1
0x180032832  mov     r8, [rdi+8]
0x180032836  mov     rdx, [rdi]
0x180032839  lea     rcx, [rbp+160h+var_E0]
0x180032840  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180032845  nop
0x180032846  xorps   xmm0, xmm0
0x180032849  movdqa  [rbp+160h+var_150], xmm0
0x18003284e  mov     [rbp+160h+var_140], r14
0x180032852  xorps   xmm1, xmm1
0x180032855  movups  [rbp+160h+var_138], xmm1
0x180032859  mov     [rbp+160h+var_128], r14
0x18003285d  mov     [rbp+160h+var_120], 7
0x180032865  mov     word ptr [rbp+160h+var_138], r14w
0x18003286a  mov     [rbp+160h+var_118], r14d
0x18003286e  mov     [rbp+160h+var_110], r14
0x180032872  mov     r8, [rbx+8]
0x180032876  test    r8, r8
0x180032879  jnz     short loc_1800328A0
0x18003287b  movups  [rbp+160h+var_1B0], xmm0
0x18003287f  movdqu  [rbp+160h+var_1A0], xmm1
0x180032884  lea     rdx, String1
0x18003288b  lea     rcx, [rbp+160h+var_1B0]
0x18003288f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180032894  lea     rcx, [rbp+160h+var_1B0]
0x180032898  mov     r13d, 1
0x18003289e  jmp     short loc_1800328BF
0x1800328a0  movups  [rbp+160h+var_190], xmm0
0x1800328a4  movdqu  [rbp+160h+var_180], xmm1
0x1800328a9  mov     rdx, [rbx]
0x1800328ac  lea     rcx, [rbp+160h+var_190]
0x1800328b0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800328b5  lea     rcx, [rbp+160h+var_190]
0x1800328b9  mov     r13d, 2
0x1800328bf  movups  xmm0, xmmword ptr [rcx]
0x1800328c2  movups  [rbp+160h+var_100], xmm0
0x1800328c6  movups  xmm1, xmmword ptr [rcx+10h]
0x1800328ca  movups  [rbp+160h+var_F0], xmm1
0x1800328ce  mov     [rcx+10h], r14
0x1800328d2  mov     qword ptr [rcx+18h], 7
0x1800328da  mov     [rcx], r14w
0x1800328de  test    r13b, 2
0x1800328e2  jz      short loc_1800328F2
0x1800328e4  and     r13d, 0FFFFFFFDh
0x1800328e8  lea     rcx, [rbp+160h+var_190]
0x1800328ec  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800328f1  nop
0x1800328f2  test    r13b, 1
0x1800328f6  jz      short loc_180032905
0x1800328f8  and     r13d, 0FFFFFFFEh
0x1800328fc  lea     rcx, [rbp+160h+var_1B0]
0x180032900  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180032905  xorps   xmm0, xmm0
0x180032908  movdqu  [rsp+260h+var_210+8], xmm0
0x18003290e  mov     [rsp+260h+var_1F8], r14
0x180032913  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18003291b  mov     rcx, [rbp+160h+var_160]
0x18003291f  lea     rax, [rbp+160h+var_170]
0x180032923  cmp     [rbp+160h+var_158], 0Fh
0x180032928  cmova   rax, [rbp+160h+var_170]
0x18003292d  mov     qword ptr [rbp+160h+var_190], rax
0x180032931  mov     qword ptr [rbp+160h+var_190+8], rcx
0x180032935  lea     rdx, [rbp+160h+var_190]
0x180032939  lea     rcx, [rbp+160h+var_1B0]
0x18003293d  call    ?IncrementCorrelationVector@FidoUtils@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_zstring_view@D@wil@@@Z; FidoUtils::IncrementCorrelationVector(wil::basic_zstring_view<char>)
0x180032942  mov     rdx, rax
0x180032945  lea     rcx, [rbp+160h+var_170]
0x180032949  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18003294e  lea     rcx, [rbp+160h+var_1B0]
0x180032952  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180032957  mov     r15, [rsi]
0x18003295a  lea     r12, [rbp+160h+var_100]
0x18003295e  cmp     qword ptr [rbp+160h+var_F0+8], 7
0x180032963  cmova   r12, qword ptr [rbp+160h+var_100]
0x180032968  lea     rsi, [rbp+160h+var_E0]
0x18003296f  cmp     qword ptr [rbp+160h+var_D0+8], 7
0x180032977  cmova   rsi, qword ptr [rbp+160h+var_E0]
0x18003297f  mov     [rsp+260h+var_220], r14
0x180032984  lea     rax, [rsp+260h+var_220]
0x180032989  mov     qword ptr [rbp+160h+var_1B0], rax
0x18003298d  lea     rbx, [rbp+160h+var_170]
0x180032991  cmp     [rbp+160h+var_158], 0Fh
0x180032996  cmova   rbx, [rbp+160h+var_170]
0x18003299b  mov     ecx, 190h; Size
0x1800329a0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800329a5  mov     rdi, rax
0x1800329a8  mov     qword ptr [rsp+260h+var_210], rax
0x1800329ad  lea     r14, [rax+70h]
0x1800329b1  mov     qword ptr [rsp+260h+var_210], r14
0x1800329b6  mov     [r14+0E8h], r15
0x1800329bd  mov     [r14+0F0h], rbx
0x1800329c4  mov     rcx, [rsp+260h+var_220]
0x1800329c9  mov     [r14+0F8h], rcx
0x1800329d0  mov     [rsp+260h+var_220], 0
0x1800329d9  mov     [r14+100h], rsi
0x1800329e0  mov     qword ptr [r14+108h], 22h ; '"'
0x1800329eb  mov     [r14+110h], r12
0x1800329f2  lea     rax, wil__ProfileDataStore__GetCollectionItemIdsAsync$_ResumeCoro$1_Windows__Data__Security__Passkey__ScenarioKeysItemPdr_
0x1800329f9  mov     [r14], rax
0x1800329fc  mov     dword ptr [r14+8], 10002h
0x180032a04  xor     edx, edx; Val
0x180032a06  lea     r8d, [rdx+68h]; Size
0x180032a0a  mov     rcx, rdi; void *
0x180032a0d  call    memset_0
0x180032a12  nop
0x180032a13  mov     [rsp+260h+var_218], rdi
0x180032a18  xor     eax, eax
0x180032a1a  mov     [r14+0E0h], al
0x180032a21  mov     rcx, r14
0x180032a24  call    wil__ProfileDataStore__GetCollectionItemIdsAsync$_ResumeCoro$1_Windows__Data__Security__Passkey__ScenarioKeysItemPdr_
0x180032a29  nop
0x180032a2a  mov     rcx, [rsp+260h+var_220]
0x180032a2f  xor     r14d, r14d
0x180032a32  test    rcx, rcx
0x180032a35  jz      short loc_180032A50
0x180032a37  or      eax, 0FFFFFFFFh
0x180032a3a  lock xadd [rcx+8], eax
0x180032a3f  cmp     eax, 1
0x180032a42  jnz     short loc_180032A50
0x180032a44  mov     rax, [rcx]
0x180032a47  mov     rax, [rax+8]
0x180032a4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a50  mov     [rsp+260h+var_220], r14
0x180032a55  lea     rdx, [rbp+160h+var_C0]
0x180032a5c  lea     rcx, [rsp+260h+var_218]
0x180032a61  call    ?get@?$task_base@V?$GetCollectionItemIdsResult@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@coro@details@wil@@QEHAA@XZ; wil::details::coro::task_base<wil::GetCollectionItemIdsResult<Windows::Data::Security::Passkey::PasskeyItemPdr>>::get(void)
0x180032a66  mov     rbx, rax
0x180032a69  lea     rax, [rbp+160h+var_150]
0x180032a6d  cmp     rax, rbx
0x180032a70  jz      short loc_180032A9D
0x180032a72  lea     rcx, [rbp+160h+var_150]
0x180032a76  call    ?_Tidy@?$vector@V?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@V?$allocator@V?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@std@@AEAAXXZ; std::vector<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr>>::_Tidy(void)
0x180032a7b  mov     rcx, [rbx]
0x180032a7e  mov     qword ptr [rbp+160h+var_150], rcx
0x180032a82  mov     rcx, [rbx+8]
0x180032a86  mov     qword ptr [rbp+160h+var_150+8], rcx
0x180032a8a  mov     rcx, [rbx+10h]
0x180032a8e  mov     [rbp+160h+var_140], rcx
0x180032a92  mov     [rbx], r14
0x180032a95  mov     [rbx+8], r14
0x180032a99  mov     [rbx+10h], r14
0x180032a9d  lea     rdx, [rbx+18h]
0x180032aa1  lea     rcx, [rbp+160h+var_138]
0x180032aa5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180032aaa  mov     edi, [rbx+38h]
0x180032aad  mov     [rbp+160h+var_118], edi
0x180032ab0  mov     rax, [rbx+40h]
0x180032ab4  mov     [rbp+160h+var_110], rax
0x180032ab8  lea     rcx, [rbp+160h+var_A8]
0x180032abf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180032ac4  lea     rcx, [rbp+160h+var_C0]
0x180032acb  call    ?_Tidy@?$vector@V?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@V?$allocator@V?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@std@@AEAAXXZ; std::vector<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr>>::_Tidy(void)
0x180032ad0  nop
0x180032ad1  mov     rcx, [rsp+260h+var_218]
0x180032ad6  test    rcx, rcx
0x180032ad9  jz      short loc_180032AFD
0x180032adb  mov     eax, 2
0x180032ae0  xchg    rax, [rcx+8]
0x180032ae4  test    rax, rax
0x180032ae7  jz      short loc_180032AFD
0x180032ae9  lea     rax, [rcx+70h]
0x180032aed  or      qword ptr [rax+8], 1
0x180032af2  mov     rcx, rax
0x180032af5  mov     rax, [rax]
0x180032af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032afd  test    edi, edi
0x180032aff  jns     short loc_180032B59
0x180032b01  mov     eax, cs:dword_180075000
0x180032b07  cmp     eax, 4
0x180032b0a  jbe     short loc_180032B59
0x180032b0c  lea     rax, aProfiledatasto_3; "ProfileDataStore::GetCollectionItemIdsA"...
0x180032b13  mov     [rsp+260h+var_218], rax
0x180032b18  lea     rax, [rbp+160h+var_170]
0x180032b1c  cmp     [rbp+160h+var_158], 0Fh
0x180032b21  cmova   rax, [rbp+160h+var_170]
0x180032b26  mov     [rsp+260h+var_220], rax
0x180032b2b  mov     dword ptr [rsp+260h+var_210], edi
0x180032b2f  lea     rax, [rsp+260h+var_218]
0x180032b34  mov     [rsp+30h], rax
0x180032b39  lea     rax, [rsp+260h+var_220]
0x180032b3e  mov     [rsp+260h+var_238], rax
0x180032b43  lea     rax, [rsp+260h+var_210]
0x180032b48  mov     qword ptr [rsp+260h+var_240], rax
0x180032b4d  lea     rdx, word_180068F22
0x180032b54  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180032b59  mov     rbx, qword ptr [rbp+160h+var_150]
0x180032b5d  jmp     short loc_180032BB4
0x180032b5f  mov     rdx, rbx
0x180032b62  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180032b67  or      r13d, 38h
0x180032b6b  mov     rdx, [rsp+260h+var_200]
0x180032b70  cmp     rdx, [rsp+260h+var_1F8]
0x180032b75  jz      short loc_180032B98
0x180032b77  movups  xmm0, [rbp+160h+var_1B0]
0x180032b7b  movups  xmmword ptr [rdx], xmm0
0x180032b7e  movups  xmm1, [rbp+160h+var_1A0]
0x180032b82  movups  xmmword ptr [rdx+10h], xmm1
0x180032b86  movdqu  [rbp+160h+var_1A0], xmm6
0x180032b8b  mov     word ptr [rbp+160h+var_1B0], r14w
0x180032b90  add     [rsp+260h+var_200], 20h ; ' '
0x180032b96  jmp     short loc_180032BA7
0x180032b98  lea     r8, [rbp+160h+var_1B0]
0x180032b9c  lea     rcx, [rsp+260h+var_210+8]
0x180032ba1  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180032ba6  nop
0x180032ba7  lea     rcx, [rbp+160h+var_1B0]
0x180032bab  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180032bb0  add     rbx, 60h ; '`'
0x180032bb4  lea     rcx, [rbp+160h+var_1B0]
0x180032bb8  cmp     rbx, qword ptr [rbp+160h+var_150+8]
0x180032bbc  jnz     short loc_180032B5F
0x180032bbe  lea     rdx, [rbp+160h+var_138]
0x180032bc2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180032bc7  or      r13d, 40h
0x180032bcb  lea     rdx, [rbp+160h+var_1B0]
0x180032bcf  lea     rcx, [rbp+160h+var_100]
0x180032bd3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180032bd8  lea     rcx, [rbp+160h+var_1B0]
0x180032bdc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180032be1  test    [rbp+160h+var_118], 80000000h
0x180032be8  jnz     short loc_180032C01
0x180032bea  cmp     [rbp+160h+var_118], 190130h
0x180032bf1  jz      short loc_180032C01
0x180032bf3  cmp     [rbp+160h+var_110], r14
0x180032bf7  mov     rsi, [rbp+160h+var_1E0]
0x180032bfb  jz      loc_18003291B
0x180032c01  test    edi, edi
0x180032c03  jns     loc_180032CDA
0x180032c09  mov     eax, cs:dword_180075000
0x180032c0f  cmp     eax, 4
0x180032c12  jbe     short loc_180032C61
0x180032c14  lea     rax, aProfiledatasto_3; "ProfileDataStore::GetCollectionItemIdsA"...
0x180032c1b  mov     [rsp+260h+var_218], rax
0x180032c20  lea     rax, [rbp+160h+var_170]
0x180032c24  cmp     [rbp+160h+var_158], 0Fh
0x180032c29  cmova   rax, [rbp+160h+var_170]
0x180032c2e  mov     [rsp+260h+var_220], rax
0x180032c33  mov     dword ptr [rsp+260h+var_210], edi
0x180032c37  lea     rax, [rsp+260h+var_218]
0x180032c3c  mov     [rsp+30h], rax
0x180032c41  lea     rax, [rsp+260h+var_220]
0x180032c46  mov     [rsp+260h+var_238], rax
0x180032c4b  lea     rax, [rsp+260h+var_210]
0x180032c50  mov     qword ptr [rsp+260h+var_240], rax
0x180032c55  lea     rdx, word_180068F92
0x180032c5c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180032c61  xorps   xmm0, xmm0
0x180032c64  movups  [rbp+160h+var_190], xmm0
  ... truncated ...
```
