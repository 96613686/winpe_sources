# PdrSyncUtils::GetCollectionIdsImpl<Windows::Data::Security::Passkey::RecoveryItemPdr>(std::shared_ptr<wil::ProfileDataStore>,NgcPasskeys::SyncStore::PropertyType const &,std::basic_string_view<ushort,std::char_traits<ushort>>,std::basic_string_view<char,std::char_traits<char>>,std::basic_string_view<ushort,std::char_traits<ushort>>)

- ea: `0x18003206c`
- end: `0x180032754`
- name: `??$GetCollectionIdsImpl@URecoveryItemPdr@Passkey@Security@Data@Windows@@@PdrSyncUtils@@YA?AUCollectionIdsResult@SyncStore@NgcPasskeys@@V?$shared_ptr@VProfileDataStore@wil@@@std@@AEBW4PropertyType@23@V?$basic_string_view@GU?$char_traits@G@std@@@5@V?$basic_string_view@DU?$char_traits@D@std@@@5@2@Z`
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
- `0x18003206c`
- `0x1800334a0`
- `0x180040d10`
- `0x18004ead4`
- `0x18004f554`
- `0x180054c40`
- `0x180054ecc`
- `0x180061010`

## import_xrefs

- `webauthn!WebAuthNWriteEventCloudStoreOperationFailure` at `0x1800325ba`
- `webauthn!WebAuthNWriteEventCloudStoreOperationFailure` at `0x1800325ba`
- `webauthn!WebAuthNWriteEventCloudStoreOperationSuccess` at `0x18003262f`
- `webauthn!WebAuthNWriteEventCloudStoreOperationSuccess` at `0x18003262f`

## string_xrefs

- `0x1800325ce`: `onecore\ds\security\ngc\utils\pdr\lib\pdrsyncstore.cpp`
- `0x180032643`: `onecore\ds\security\ngc\utils\pdr\lib\pdrsyncstore.cpp`

## pseudocode

```c
int *__fastcall PdrSyncUtils::GetCollectionIdsImpl<Windows::Data::Security::Passkey::RecoveryItemPdr>(
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
      (unsigned int)word_18006919A,
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
    v25[14] = wil::ProfileDataStore::GetCollectionItemIdsAsync__ResumeCoro_1_Windows::Data::Security::Passkey::RecoveryItemPdr_;
    *((_DWORD *)v25 + 30) = 65538;
    memset_0(v25, 0, 0x68u);
    v62 = (const char *)v25;
    *((_BYTE *)v25 + 336) = 0;
    wil::ProfileDataStore::GetCollectionItemIdsAsync__ResumeCoro_1_Windows::Data::Security::Passkey::RecoveryItemPdr_(v25 + 14);
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
        (unsigned int)word_18006904A,
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
        (unsigned int)word_1800690BA,
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
0x18003206c  mov     rax, rsp
0x18003206f  push    rbp
0x180032070  push    rbx
0x180032071  push    rsi
0x180032072  push    rdi
0x180032073  push    r12
0x180032075  push    r13
0x180032077  push    r14
0x180032079  push    r15
0x18003207b  lea     rbp, [rax-168h]
0x180032082  sub     rsp, 228h
0x180032089  movaps  xmmword ptr [rax-58h], xmm6
0x18003208d  mov     rax, cs:__security_cookie
0x180032094  xor     rax, rsp
0x180032097  mov     [rbp+160h+var_60], rax
0x18003209e  mov     rdi, r9
0x1800320a1  mov     [rsp+260h+var_1E8], r8
0x1800320a6  mov     rsi, rdx
0x1800320a9  mov     [rbp+160h+var_1E0], rdx
0x1800320ad  mov     [rbp+160h+var_1D0], rcx
0x1800320b1  mov     [rbp+160h+var_1C8], rcx
0x1800320b5  mov     [rbp+160h+var_1C0], rdx
0x1800320b9  mov     rax, [rbp+160h+arg_20]
0x1800320c0  mov     [rsp+260h+var_1F0], rax
0x1800320c5  mov     rbx, [rbp+160h+arg_28]
0x1800320cc  xor     r14d, r14d
0x1800320cf  mov     [rbp+160h+var_1D8], r14d
0x1800320d3  mov     rcx, [rax]
0x1800320d6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800320da  inc     rax
0x1800320dd  cmp     [rcx+rax], r14b
0x1800320e1  jnz     short loc_1800320DA
0x1800320e3  mov     qword ptr [rbp+160h+var_1B0], rcx
0x1800320e7  mov     qword ptr [rbp+160h+var_1B0+8], rax
0x1800320eb  lea     rdx, [rbp+160h+var_1B0]
0x1800320ef  lea     rcx, [rbp+160h+var_170]
0x1800320f3  call    ?ExtendCorrelationVector@FidoUtils@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_zstring_view@D@wil@@@Z; FidoUtils::ExtendCorrelationVector(wil::basic_zstring_view<char>)
0x1800320f8  nop
0x1800320f9  mov     eax, cs:dword_180075000
0x1800320ff  cmp     eax, 4
0x180032102  jbe     short loc_18003212D
0x180032104  lea     rax, [rbp+160h+var_170]
0x180032108  cmp     [rbp+160h+var_158], 0Fh
0x18003210d  cmova   rax, [rbp+160h+var_170]
0x180032112  mov     [rsp+260h+var_218], rax
0x180032117  lea     rax, [rsp+260h+var_218]
0x18003211c  mov     qword ptr [rsp+260h+var_240], rax
0x180032121  lea     rdx, word_18006919A
0x180032128  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003212d  xorps   xmm0, xmm0
0x180032130  movups  [rbp+160h+var_E0], xmm0
0x180032137  xorps   xmm1, xmm1
0x18003213a  movdqu  [rbp+160h+var_D0], xmm1
0x180032142  mov     r8, [rdi+8]
0x180032146  mov     rdx, [rdi]
0x180032149  lea     rcx, [rbp+160h+var_E0]
0x180032150  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180032155  nop
0x180032156  xorps   xmm0, xmm0
0x180032159  movdqa  [rbp+160h+var_150], xmm0
0x18003215e  mov     [rbp+160h+var_140], r14
0x180032162  xorps   xmm1, xmm1
0x180032165  movups  [rbp+160h+var_138], xmm1
0x180032169  mov     [rbp+160h+var_128], r14
0x18003216d  mov     [rbp+160h+var_120], 7
0x180032175  mov     word ptr [rbp+160h+var_138], r14w
0x18003217a  mov     [rbp+160h+var_118], r14d
0x18003217e  mov     [rbp+160h+var_110], r14
0x180032182  mov     r8, [rbx+8]
0x180032186  test    r8, r8
0x180032189  jnz     short loc_1800321B0
0x18003218b  movups  [rbp+160h+var_1B0], xmm0
0x18003218f  movdqu  [rbp+160h+var_1A0], xmm1
0x180032194  lea     rdx, String1
0x18003219b  lea     rcx, [rbp+160h+var_1B0]
0x18003219f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800321a4  lea     rcx, [rbp+160h+var_1B0]
0x1800321a8  mov     r13d, 1
0x1800321ae  jmp     short loc_1800321CF
0x1800321b0  movups  [rbp+160h+var_190], xmm0
0x1800321b4  movdqu  [rbp+160h+var_180], xmm1
0x1800321b9  mov     rdx, [rbx]
0x1800321bc  lea     rcx, [rbp+160h+var_190]
0x1800321c0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800321c5  lea     rcx, [rbp+160h+var_190]
0x1800321c9  mov     r13d, 2
0x1800321cf  movups  xmm0, xmmword ptr [rcx]
0x1800321d2  movups  [rbp+160h+var_100], xmm0
0x1800321d6  movups  xmm1, xmmword ptr [rcx+10h]
0x1800321da  movups  [rbp+160h+var_F0], xmm1
0x1800321de  mov     [rcx+10h], r14
0x1800321e2  mov     qword ptr [rcx+18h], 7
0x1800321ea  mov     [rcx], r14w
0x1800321ee  test    r13b, 2
0x1800321f2  jz      short loc_180032202
0x1800321f4  and     r13d, 0FFFFFFFDh
0x1800321f8  lea     rcx, [rbp+160h+var_190]
0x1800321fc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180032201  nop
0x180032202  test    r13b, 1
0x180032206  jz      short loc_180032215
0x180032208  and     r13d, 0FFFFFFFEh
0x18003220c  lea     rcx, [rbp+160h+var_1B0]
0x180032210  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180032215  xorps   xmm0, xmm0
0x180032218  movdqu  [rsp+260h+var_210+8], xmm0
0x18003221e  mov     [rsp+260h+var_1F8], r14
0x180032223  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18003222b  mov     rcx, [rbp+160h+var_160]
0x18003222f  lea     rax, [rbp+160h+var_170]
0x180032233  cmp     [rbp+160h+var_158], 0Fh
0x180032238  cmova   rax, [rbp+160h+var_170]
0x18003223d  mov     qword ptr [rbp+160h+var_190], rax
0x180032241  mov     qword ptr [rbp+160h+var_190+8], rcx
0x180032245  lea     rdx, [rbp+160h+var_190]
0x180032249  lea     rcx, [rbp+160h+var_1B0]
0x18003224d  call    ?IncrementCorrelationVector@FidoUtils@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_zstring_view@D@wil@@@Z; FidoUtils::IncrementCorrelationVector(wil::basic_zstring_view<char>)
0x180032252  mov     rdx, rax
0x180032255  lea     rcx, [rbp+160h+var_170]
0x180032259  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18003225e  lea     rcx, [rbp+160h+var_1B0]
0x180032262  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180032267  mov     r15, [rsi]
0x18003226a  lea     r12, [rbp+160h+var_100]
0x18003226e  cmp     qword ptr [rbp+160h+var_F0+8], 7
0x180032273  cmova   r12, qword ptr [rbp+160h+var_100]
0x180032278  lea     rsi, [rbp+160h+var_E0]
0x18003227f  cmp     qword ptr [rbp+160h+var_D0+8], 7
0x180032287  cmova   rsi, qword ptr [rbp+160h+var_E0]
0x18003228f  mov     [rsp+260h+var_220], r14
0x180032294  lea     rax, [rsp+260h+var_220]
0x180032299  mov     qword ptr [rbp+160h+var_1B0], rax
0x18003229d  lea     rbx, [rbp+160h+var_170]
0x1800322a1  cmp     [rbp+160h+var_158], 0Fh
0x1800322a6  cmova   rbx, [rbp+160h+var_170]
0x1800322ab  mov     ecx, 190h; Size
0x1800322b0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800322b5  mov     rdi, rax
0x1800322b8  mov     qword ptr [rsp+260h+var_210], rax
0x1800322bd  lea     r14, [rax+70h]
0x1800322c1  mov     qword ptr [rsp+260h+var_210], r14
0x1800322c6  mov     [r14+0E8h], r15
0x1800322cd  mov     [r14+0F0h], rbx
0x1800322d4  mov     rcx, [rsp+260h+var_220]
0x1800322d9  mov     [r14+0F8h], rcx
0x1800322e0  mov     [rsp+260h+var_220], 0
0x1800322e9  mov     [r14+100h], rsi
0x1800322f0  mov     qword ptr [r14+108h], 22h ; '"'
0x1800322fb  mov     [r14+110h], r12
0x180032302  lea     rax, wil__ProfileDataStore__GetCollectionItemIdsAsync$_ResumeCoro$1_Windows__Data__Security__Passkey__RecoveryItemPdr_
0x180032309  mov     [r14], rax
0x18003230c  mov     dword ptr [r14+8], 10002h
0x180032314  xor     edx, edx; Val
0x180032316  lea     r8d, [rdx+68h]; Size
0x18003231a  mov     rcx, rdi; void *
0x18003231d  call    memset_0
0x180032322  nop
0x180032323  mov     [rsp+260h+var_218], rdi
0x180032328  xor     eax, eax
0x18003232a  mov     [r14+0E0h], al
0x180032331  mov     rcx, r14
0x180032334  call    wil__ProfileDataStore__GetCollectionItemIdsAsync$_ResumeCoro$1_Windows__Data__Security__Passkey__RecoveryItemPdr_
0x180032339  nop
0x18003233a  mov     rcx, [rsp+260h+var_220]
0x18003233f  xor     r14d, r14d
0x180032342  test    rcx, rcx
0x180032345  jz      short loc_180032360
0x180032347  or      eax, 0FFFFFFFFh
0x18003234a  lock xadd [rcx+8], eax
0x18003234f  cmp     eax, 1
0x180032352  jnz     short loc_180032360
0x180032354  mov     rax, [rcx]
0x180032357  mov     rax, [rax+8]
0x18003235b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032360  mov     [rsp+260h+var_220], r14
0x180032365  lea     rdx, [rbp+160h+var_C0]
0x18003236c  lea     rcx, [rsp+260h+var_218]
0x180032371  call    ?get@?$task_base@V?$GetCollectionItemIdsResult@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@coro@details@wil@@QEHAA@XZ; wil::details::coro::task_base<wil::GetCollectionItemIdsResult<Windows::Data::Security::Passkey::PasskeyItemPdr>>::get(void)
0x180032376  mov     rbx, rax
0x180032379  lea     rax, [rbp+160h+var_150]
0x18003237d  cmp     rax, rbx
0x180032380  jz      short loc_1800323AD
0x180032382  lea     rcx, [rbp+160h+var_150]
0x180032386  call    ?_Tidy@?$vector@V?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@V?$allocator@V?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@std@@AEAAXXZ; std::vector<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr>>::_Tidy(void)
0x18003238b  mov     rcx, [rbx]
0x18003238e  mov     qword ptr [rbp+160h+var_150], rcx
0x180032392  mov     rcx, [rbx+8]
0x180032396  mov     qword ptr [rbp+160h+var_150+8], rcx
0x18003239a  mov     rcx, [rbx+10h]
0x18003239e  mov     [rbp+160h+var_140], rcx
0x1800323a2  mov     [rbx], r14
0x1800323a5  mov     [rbx+8], r14
0x1800323a9  mov     [rbx+10h], r14
0x1800323ad  lea     rdx, [rbx+18h]
0x1800323b1  lea     rcx, [rbp+160h+var_138]
0x1800323b5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800323ba  mov     edi, [rbx+38h]
0x1800323bd  mov     [rbp+160h+var_118], edi
0x1800323c0  mov     rax, [rbx+40h]
0x1800323c4  mov     [rbp+160h+var_110], rax
0x1800323c8  lea     rcx, [rbp+160h+var_A8]
0x1800323cf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800323d4  lea     rcx, [rbp+160h+var_C0]
0x1800323db  call    ?_Tidy@?$vector@V?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@V?$allocator@V?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@std@@AEAAXXZ; std::vector<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr>>::_Tidy(void)
0x1800323e0  nop
0x1800323e1  mov     rcx, [rsp+260h+var_218]
0x1800323e6  test    rcx, rcx
0x1800323e9  jz      short loc_18003240D
0x1800323eb  mov     eax, 2
0x1800323f0  xchg    rax, [rcx+8]
0x1800323f4  test    rax, rax
0x1800323f7  jz      short loc_18003240D
0x1800323f9  lea     rax, [rcx+70h]
0x1800323fd  or      qword ptr [rax+8], 1
0x180032402  mov     rcx, rax
0x180032405  mov     rax, [rax]
0x180032408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003240d  test    edi, edi
0x18003240f  jns     short loc_180032469
0x180032411  mov     eax, cs:dword_180075000
0x180032417  cmp     eax, 4
0x18003241a  jbe     short loc_180032469
0x18003241c  lea     rax, aProfiledatasto_3; "ProfileDataStore::GetCollectionItemIdsA"...
0x180032423  mov     [rsp+260h+var_218], rax
0x180032428  lea     rax, [rbp+160h+var_170]
0x18003242c  cmp     [rbp+160h+var_158], 0Fh
0x180032431  cmova   rax, [rbp+160h+var_170]
0x180032436  mov     [rsp+260h+var_220], rax
0x18003243b  mov     dword ptr [rsp+260h+var_210], edi
0x18003243f  lea     rax, [rsp+260h+var_218]
0x180032444  mov     [rsp+30h], rax
0x180032449  lea     rax, [rsp+260h+var_220]
0x18003244e  mov     [rsp+260h+var_238], rax
0x180032453  lea     rax, [rsp+260h+var_210]
0x180032458  mov     qword ptr [rsp+260h+var_240], rax
0x18003245d  lea     rdx, word_18006904A
0x180032464  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180032469  mov     rbx, qword ptr [rbp+160h+var_150]
0x18003246d  jmp     short loc_1800324C4
0x18003246f  mov     rdx, rbx
0x180032472  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180032477  or      r13d, 38h
0x18003247b  mov     rdx, [rsp+260h+var_200]
0x180032480  cmp     rdx, [rsp+260h+var_1F8]
0x180032485  jz      short loc_1800324A8
0x180032487  movups  xmm0, [rbp+160h+var_1B0]
0x18003248b  movups  xmmword ptr [rdx], xmm0
0x18003248e  movups  xmm1, [rbp+160h+var_1A0]
0x180032492  movups  xmmword ptr [rdx+10h], xmm1
0x180032496  movdqu  [rbp+160h+var_1A0], xmm6
0x18003249b  mov     word ptr [rbp+160h+var_1B0], r14w
0x1800324a0  add     [rsp+260h+var_200], 20h ; ' '
0x1800324a6  jmp     short loc_1800324B7
0x1800324a8  lea     r8, [rbp+160h+var_1B0]
0x1800324ac  lea     rcx, [rsp+260h+var_210+8]
0x1800324b1  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x1800324b6  nop
0x1800324b7  lea     rcx, [rbp+160h+var_1B0]
0x1800324bb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800324c0  add     rbx, 60h ; '`'
0x1800324c4  lea     rcx, [rbp+160h+var_1B0]
0x1800324c8  cmp     rbx, qword ptr [rbp+160h+var_150+8]
0x1800324cc  jnz     short loc_18003246F
0x1800324ce  lea     rdx, [rbp+160h+var_138]
0x1800324d2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800324d7  or      r13d, 40h
0x1800324db  lea     rdx, [rbp+160h+var_1B0]
0x1800324df  lea     rcx, [rbp+160h+var_100]
0x1800324e3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800324e8  lea     rcx, [rbp+160h+var_1B0]
0x1800324ec  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800324f1  test    [rbp+160h+var_118], 80000000h
0x1800324f8  jnz     short loc_180032511
0x1800324fa  cmp     [rbp+160h+var_118], 190130h
0x180032501  jz      short loc_180032511
0x180032503  cmp     [rbp+160h+var_110], r14
0x180032507  mov     rsi, [rbp+160h+var_1E0]
0x18003250b  jz      loc_18003222B
0x180032511  test    edi, edi
0x180032513  jns     loc_1800325EA
0x180032519  mov     eax, cs:dword_180075000
0x18003251f  cmp     eax, 4
0x180032522  jbe     short loc_180032571
0x180032524  lea     rax, aProfiledatasto_3; "ProfileDataStore::GetCollectionItemIdsA"...
0x18003252b  mov     [rsp+260h+var_218], rax
0x180032530  lea     rax, [rbp+160h+var_170]
0x180032534  cmp     [rbp+160h+var_158], 0Fh
0x180032539  cmova   rax, [rbp+160h+var_170]
0x18003253e  mov     [rsp+260h+var_220], rax
0x180032543  mov     dword ptr [rsp+260h+var_210], edi
0x180032547  lea     rax, [rsp+260h+var_218]
0x18003254c  mov     [rsp+30h], rax
0x180032551  lea     rax, [rsp+260h+var_220]
0x180032556  mov     [rsp+260h+var_238], rax
0x18003255b  lea     rax, [rsp+260h+var_210]
0x180032560  mov     qword ptr [rsp+260h+var_240], rax
0x180032565  lea     rdx, word_1800690BA
0x18003256c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180032571  xorps   xmm0, xmm0
0x180032574  movups  [rbp+160h+var_190], xmm0
  ... truncated ...
```
