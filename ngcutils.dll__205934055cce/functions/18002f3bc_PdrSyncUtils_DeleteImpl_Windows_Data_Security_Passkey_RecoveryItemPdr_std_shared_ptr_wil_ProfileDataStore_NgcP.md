# PdrSyncUtils::DeleteImpl<Windows::Data::Security::Passkey::RecoveryItemPdr>(std::shared_ptr<wil::ProfileDataStore>,NgcPasskeys::SyncStore::PropertyType const &,wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr> const &,wil::basic_zstring_view<ushort>,std::basic_string_view<char,std::char_traits<char>>,std::basic_string_view<ushort,std::char_traits<ushort>>)

- ea: `0x18002f3bc`
- end: `0x18002f95b`
- name: `??$DeleteImpl@URecoveryItemPdr@Passkey@Security@Data@Windows@@@PdrSyncUtils@@YA?AUSaveResult@SyncStore@NgcPasskeys@@V?$shared_ptr@VProfileDataStore@wil@@@std@@AEBW4PropertyType@23@AEBV?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@V?$basic_zstring_view@G@8@V?$basic_string_view@DU?$char_traits@D@std@@@5@V?$basic_string_view@GU?$char_traits@G@std@@@5@@Z`
- size: `1439`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0x180048660`

## callees

- `0x1800012e4`
- `0x180001374`
- `0x180003080`
- `0x180003568`
- `0x180003bc8`
- `0x18000c95c`
- `0x18000ce74`
- `0x18001354c`
- `0x18001361c`
- `0x1800137a0`
- `0x180013834`
- `0x18001addc`
- `0x18002f3bc`
- `0x180030520`
- `0x180038e44`
- `0x180040d10`
- `0x18004f6ac`
- `0x18004f8fc`
- `0x180054c40`
- `0x180054ecc`
- `0x180061010`

## import_xrefs

- `webauthn!WebAuthNWriteEventCloudStoreOperationFailure` at `0x18002f829`
- `webauthn!WebAuthNWriteEventCloudStoreOperationFailure` at `0x18002f829`
- `webauthn!WebAuthNWriteEventCloudStoreOperationSuccess` at `0x18002f887`
- `webauthn!WebAuthNWriteEventCloudStoreOperationSuccess` at `0x18002f887`

## string_xrefs

- `0x18002f8a0`: `onecore\ds\security\ngc\utils\pdr\lib\pdrsyncstore.cpp`
- `0x18002f792`: `ProfileDataStore::DeleteItemAsync`

## pseudocode

```c
int *__fastcall PdrSyncUtils::DeleteImpl<Windows::Data::Security::Passkey::RecoveryItemPdr>(
        int *a1,
        _QWORD *a2,
        unsigned int *a3,
        const char *a4,
        _QWORD *a5,
        _QWORD *a6,
        _QWORD *a7)
{
  int v7; // esi
  __int64 v10; // r13
  __int64 v11; // rax
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  _QWORD *v15; // rax
  _QWORD *v16; // rax
  __int64 v17; // rax
  _QWORD *v18; // r9
  __int64 v19; // rax
  _QWORD *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  volatile signed __int32 *v23; // rbx
  char *v24; // rcx
  _QWORD *v25; // rax
  __int64 v26; // rax
  __int64 v27; // rsi
  __int128 *v28; // r15
  _QWORD *v29; // rbx
  _QWORD *v30; // rdi
  __int64 v31; // rcx
  __int64 v32; // rbx
  __int64 v33; // rdx
  __int64 v34; // r8
  int v35; // r8d
  int v36; // r9d
  _QWORD *v37; // rcx
  int v38; // ebx
  _QWORD *v39; // rax
  __int128 *v40; // r9
  int v41; // eax
  wil::details::in1diag3 *v42; // rcx
  __int64 v43; // rdx
  __int128 *v44; // r9
  int v45; // eax
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // rdx
  __int64 v49; // r8
  volatile signed __int32 *v50; // rbx
  int v52; // [rsp+20h] [rbp-E0h]
  int v53[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v54; // [rsp+48h] [rbp-B8h] BYREF
  char *v55; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v56; // [rsp+58h] [rbp-A8h]
  const char *v57; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v58; // [rsp+68h] [rbp-98h]
  unsigned int *v59; // [rsp+70h] [rbp-90h]
  _QWORD *v60; // [rsp+80h] [rbp-80h]
  _QWORD *v61; // [rsp+88h] [rbp-78h]
  __int128 v62; // [rsp+90h] [rbp-70h] BYREF
  __int128 v63; // [rsp+A0h] [rbp-60h]
  _QWORD v64[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v65; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v66; // [rsp+C8h] [rbp-38h]
  __int128 v67; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v68; // [rsp+E0h] [rbp-20h]
  __int64 v69; // [rsp+F0h] [rbp-10h]
  int v70; // [rsp+F8h] [rbp-8h]
  int v71; // [rsp+FCh] [rbp-4h]
  _OWORD v72[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v73; // [rsp+120h] [rbp+20h]
  _BYTE v74[16]; // [rsp+128h] [rbp+28h] BYREF
  char v75[56]; // [rsp+138h] [rbp+38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v7 = (int)a4;
  v57 = a4;
  v59 = a3;
  v60 = a2;
  v61 = a2;
  v56 = a5;
  v58 = a6;
  v10 = *a6;
  v11 = -1;
  do
    ++v11;
  while ( *(_BYTE *)(v11 + v10) );
  *(_QWORD *)&v62 = *a6;
  *((_QWORD *)&v62 + 1) = v11;
  FidoUtils::ExtendCorrelationVector(v64, &v62);
  if ( (unsigned int)dword_180075000 > 4 )
  {
    v15 = v64;
    if ( v66 > 0xF )
      v15 = (_QWORD *)v64[0];
    v54 = v15;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v12,
      (unsigned int)word_18006940A,
      v13,
      v14,
      (__int64)&v54);
  }
  v69 = 0;
  v72[0] = 0;
  v72[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v72[0]) = 0;
  v67 = 0;
  v68 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v67, *a7, a7[1]);
  if ( !(_QWORD)v68 )
  {
    v16 = v64;
    if ( v66 > 0xF )
      v16 = (_QWORD *)v64[0];
    *(_QWORD *)&v62 = v16;
    *((_QWORD *)&v62 + 1) = v65;
    v17 = FidoUtils::IncrementCorrelationVector(v74, &v62);
    std::string::operator=(v64, v17);
    std::string::~string(v74);
    *(_QWORD *)v53 = 0;
    v18 = v64;
    if ( v66 > 0xF )
      LODWORD(v18) = v64[0];
    v19 = wil::ProfileDataStore::LoadAsync<Windows::Data::Security::Passkey::RecoveryItemPdr>(
            *a2,
            (unsigned int)&v55,
            v7,
            (_DWORD)v18,
            (__int64)v53,
            34);
    v20 = (_QWORD *)wil::details::coro::task_base<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::get(
                      v19,
                      &v62);
    std::wstring::wstring(v74, *v20 + 152LL);
    std::wstring::operator=(&v67, v74);
    std::wstring::~wstring(v74, v21, v22);
    v23 = (volatile signed __int32 *)*((_QWORD *)&v62 + 1);
    if ( *((_QWORD *)&v62 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v62 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
        if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
      }
    }
    v24 = v55;
    v55 = 0;
    if ( v24 && _InterlockedExchange64((volatile __int64 *)v24 + 1, 2) )
    {
      *((_QWORD *)v24 + 7) |= 1uLL;
      (*((void (__fastcall **)(char *))v24 + 6))(v24 + 48);
    }
  }
  v25 = v64;
  if ( v66 > 0xF )
    v25 = (_QWORD *)v64[0];
  *(_QWORD *)&v62 = v25;
  *((_QWORD *)&v62 + 1) = v65;
  v26 = FidoUtils::IncrementCorrelationVector(v74, &v62);
  std::string::operator=(v64, v26);
  std::string::~string(v74);
  v27 = *a2;
  v28 = &v67;
  if ( *((_QWORD *)&v68 + 1) > 7u )
    v28 = (__int128 *)v67;
  *(_QWORD *)v53 = 0;
  *(_QWORD *)&v62 = v53;
  v29 = v64;
  if ( v66 > 0xF )
    v29 = (_QWORD *)v64[0];
  v30 = operator new(0x170u);
  v55 = (char *)(v30 + 12);
  v30[39] = v27;
  v30[40] = v57;
  v30[41] = v29;
  v30[42] = *(_QWORD *)v53;
  *(_QWORD *)v53 = 0;
  v30[43] = v28;
  *((_DWORD *)v30 + 88) = 1;
  v30[12] = wil::ProfileDataStore::DeleteItemAsync__ResumeCoro_1_Windows::Data::Security::Passkey::RecoveryItemPdr_;
  *((_DWORD *)v30 + 26) = 65538;
  memset_0(v30, 0, 0x58u);
  v54 = v30;
  *((_BYTE *)v30 + 304) = 0;
  wil::ProfileDataStore::DeleteItemAsync__ResumeCoro_1_Windows::Data::Security::Passkey::RecoveryItemPdr_(v30 + 12);
  v31 = *(_QWORD *)v53;
  if ( *(_QWORD *)v53 && _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)v53 + 8LL), 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
  *(_QWORD *)v53 = 0;
  v32 = wil::details::coro::task_base<wil::ProfileDataStoreSaveResult>::get(&v54, v74);
  v69 = *(_QWORD *)v32;
  v70 = *(_DWORD *)(v32 + 8);
  v71 = *(_DWORD *)(v32 + 12);
  std::wstring::operator=(v72, v32 + 16);
  v73 = *(_QWORD *)(v32 + 48);
  std::wstring::~wstring(v75, v33, v34);
  v37 = v54;
  if ( v54 && _InterlockedExchange64(v54 + 1, 2) )
  {
    v37[13] |= 1uLL;
    ((void (__fastcall *)(_QWORD *))v37[12])(v37 + 12);
  }
  v38 = v71;
  if ( v71 >= 0 )
  {
    v62 = 0;
    v63 = 0;
    std::string::_Construct<1,char const *>(&v62, v10, v58[1]);
    v44 = &v62;
    if ( *((_QWORD *)&v63 + 1) > 0xFu )
      v44 = (__int128 *)v62;
    v41 = WebAuthNWriteEventCloudStoreOperationSuccess(2, *v59, *v56, v44);
    v42 = retaddr;
    if ( v41 < 0 )
    {
      v43 = 568;
      goto LABEL_44;
    }
  }
  else
  {
    if ( (unsigned int)dword_180075000 > 4 )
    {
      v57 = "ProfileDataStore::DeleteItemAsync";
      v39 = v64;
      if ( v66 > 0xF )
        v39 = (_QWORD *)v64[0];
      v54 = v39;
      LODWORD(v55) = v71;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)v37,
        (unsigned int)&unk_180069300,
        v35,
        v36,
        (__int64)&v55,
        (__int64)&v54,
        (__int64)&v57);
    }
    v62 = 0;
    v63 = 0;
    std::string::_Construct<1,char const *>(&v62, v10, v58[1]);
    v40 = &v62;
    if ( *((_QWORD *)&v63 + 1) > 0xFu )
      v40 = (__int128 *)v62;
    v52 = v38;
    v41 = WebAuthNWriteEventCloudStoreOperationFailure(2, *v59, *v56, v40);
    v42 = retaddr;
    if ( v41 < 0 )
    {
      v43 = 560;
LABEL_44:
      wil::details::in1diag3::_Log_Hr(
        v42,
        (void *)v43,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\pdr\\lib\\pdrsyncstore.cpp",
        (const char *)(unsigned int)v41,
        v52);
    }
  }
  std::string::~string(&v62);
  v45 = 0;
  if ( v38 < 0 )
    v45 = v38;
  *a1 = v45;
  a1[1] = 0;
  std::wstring::wstring(a1 + 2, v72);
  std::wstring::~wstring(&v67, v46, v47);
  std::wstring::~wstring(v72, v48, v49);
  std::string::~string(v64);
  v50 = (volatile signed __int32 *)v60[1];
  if ( v50 )
  {
    if ( _InterlockedExchangeAdd(v50 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v50)(v50);
      if ( _InterlockedExchangeAdd(v50 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v50 + 8LL))(v50);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18002f3bc  push    rbp
0x18002f3be  push    rbx
0x18002f3bf  push    rsi
0x18002f3c0  push    rdi
0x18002f3c1  push    r12
0x18002f3c3  push    r13
0x18002f3c5  push    r14
0x18002f3c7  push    r15
0x18002f3c9  lea     rbp, [rsp-88h]
0x18002f3d1  sub     rsp, 188h
0x18002f3d8  mov     rax, cs:__security_cookie
0x18002f3df  xor     rax, rsp
0x18002f3e2  mov     [rbp+0C0h+var_50], rax
0x18002f3e6  mov     rsi, r9
0x18002f3e9  mov     [rsp+1C0h+var_160], r9
0x18002f3ee  mov     [rsp+1C0h+var_150], r8
0x18002f3f3  mov     rdi, rdx
0x18002f3f6  mov     [rbp+0C0h+var_140], rdx
0x18002f3fa  mov     r12, rcx
0x18002f3fd  mov     [rsp+1C0h+var_168], rcx
0x18002f402  mov     [rbp+0C0h+var_138], rdx
0x18002f406  mov     rax, [rbp+0C0h+arg_20]
0x18002f40d  mov     [rsp+1C0h+var_168], rax
0x18002f412  mov     rax, [rbp+0C0h+arg_28]
0x18002f419  mov     [rsp+1C0h+var_158], rax
0x18002f41e  mov     rbx, [rbp+0C0h+arg_30]
0x18002f425  xor     r14d, r14d
0x18002f428  mov     r13, [rax]
0x18002f42b  or      r15, 0FFFFFFFFFFFFFFFFh
0x18002f42f  mov     rax, r15
0x18002f432  inc     rax
0x18002f435  cmp     [rax+r13], r14b
0x18002f439  jnz     short loc_18002F432
0x18002f43b  mov     qword ptr [rbp+0C0h+var_130], r13
0x18002f43f  mov     qword ptr [rbp+0C0h+var_130+8], rax
0x18002f443  lea     rdx, [rbp+0C0h+var_130]
0x18002f447  lea     rcx, [rbp+0C0h+var_110]
0x18002f44b  call    ?ExtendCorrelationVector@FidoUtils@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_zstring_view@D@wil@@@Z; FidoUtils::ExtendCorrelationVector(wil::basic_zstring_view<char>)
0x18002f450  nop
0x18002f451  mov     eax, cs:dword_180075000
0x18002f457  cmp     eax, 4
0x18002f45a  jbe     short loc_18002F485
0x18002f45c  lea     rax, [rbp+0C0h+var_110]
0x18002f460  cmp     [rbp+0C0h+var_F8], 0Fh
0x18002f465  cmova   rax, [rbp+0C0h+var_110]
0x18002f46a  mov     [rsp+1C0h+var_178], rax
0x18002f46f  lea     rax, [rsp+1C0h+var_178]
0x18002f474  mov     qword ptr [rsp+1C0h+var_1A0], rax
0x18002f479  lea     rdx, word_18006940A
0x18002f480  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18002f485  mov     [rbp+0C0h+var_D0], r14
0x18002f489  xorps   xmm0, xmm0
0x18002f48c  movups  [rbp+0C0h+var_C0], xmm0
0x18002f490  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002f498  movdqu  [rbp+0C0h+var_B0], xmm1
0x18002f49d  mov     word ptr [rbp+0C0h+var_C0], r14w
0x18002f4a2  movups  [rbp+0C0h+var_F0], xmm0
0x18002f4a6  xorps   xmm1, xmm1
0x18002f4a9  movdqu  [rbp+0C0h+var_E0], xmm1
0x18002f4ae  mov     r8, [rbx+8]
0x18002f4b2  mov     rdx, [rbx]
0x18002f4b5  lea     rcx, [rbp+0C0h+var_F0]
0x18002f4b9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002f4be  nop
0x18002f4bf  cmp     qword ptr [rbp+0C0h+var_E0], r14
0x18002f4c3  jnz     loc_18002F5E4
0x18002f4c9  mov     rcx, [rbp+0C0h+var_100]
0x18002f4cd  lea     rax, [rbp+0C0h+var_110]
0x18002f4d1  cmp     [rbp+0C0h+var_F8], 0Fh
0x18002f4d6  cmova   rax, [rbp+0C0h+var_110]
0x18002f4db  mov     qword ptr [rbp+0C0h+var_130], rax
0x18002f4df  mov     qword ptr [rbp+0C0h+var_130+8], rcx
0x18002f4e3  lea     rdx, [rbp+0C0h+var_130]
0x18002f4e7  lea     rcx, [rbp+0C0h+var_98]
0x18002f4eb  call    ?IncrementCorrelationVector@FidoUtils@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_zstring_view@D@wil@@@Z; FidoUtils::IncrementCorrelationVector(wil::basic_zstring_view<char>)
0x18002f4f0  mov     rdx, rax
0x18002f4f3  lea     rcx, [rbp+0C0h+var_110]
0x18002f4f7  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18002f4fc  lea     rcx, [rbp+0C0h+var_98]
0x18002f500  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002f505  mov     qword ptr [rsp+1C0h+var_180], r14
0x18002f50a  lea     r9, [rbp+0C0h+var_110]
0x18002f50e  cmp     [rbp+0C0h+var_F8], 0Fh
0x18002f513  cmova   r9, [rbp+0C0h+var_110]
0x18002f518  mov     dword ptr [rsp+1C0h+var_198], 22h ; '"'
0x18002f520  lea     rax, [rsp+1C0h+var_180]
0x18002f525  mov     qword ptr [rsp+1C0h+var_1A0], rax; int
0x18002f52a  mov     r8, rsi
0x18002f52d  lea     rdx, [rsp+1C0h+var_170]
0x18002f532  mov     rcx, [rdi]
0x18002f535  call    ??$LoadAsync@URecoveryItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@QEAA?AU?$task@V?$shared_ptr@V?$ProfileDataItem@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@1@AEBV?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@1@PEBDVcancellation_token@Concurrency@@W4ProfileDataStoreLoadOptions@1@PEBG@Z; wil::ProfileDataStore::LoadAsync<Windows::Data::Security::Passkey::RecoveryItemPdr>(wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr> const &,char const *,Concurrency::cancellation_token,wil::ProfileDataStoreLoadOptions,ushort const *)
0x18002f53a  nop
0x18002f53b  lea     rdx, [rbp+0C0h+var_130]
0x18002f53f  mov     rcx, rax
0x18002f542  call    ?get@?$task_base@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@coro@details@wil@@QEHAA@XZ; wil::details::coro::task_base<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::get(void)
0x18002f547  nop
0x18002f548  mov     rdx, [rax]
0x18002f54b  add     rdx, 98h
0x18002f552  lea     rcx, [rbp+0C0h+var_98]
0x18002f556  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002f55b  lea     rdx, [rbp+0C0h+var_98]
0x18002f55f  lea     rcx, [rbp+0C0h+var_F0]
0x18002f563  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002f568  lea     rcx, [rbp+0C0h+var_98]
0x18002f56c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002f571  nop
0x18002f572  mov     rbx, qword ptr [rbp+0C0h+var_130+8]
0x18002f576  test    rbx, rbx
0x18002f579  jz      short loc_18002F5B3
0x18002f57b  mov     eax, r15d
0x18002f57e  lock xadd [rbx+8], eax
0x18002f583  add     eax, r15d
0x18002f586  jnz     short loc_18002F5B3
0x18002f588  mov     rax, [rbx]
0x18002f58b  mov     rcx, rbx
0x18002f58e  mov     rax, [rax]
0x18002f591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f596  mov     eax, r15d
0x18002f599  lock xadd [rbx+0Ch], eax
0x18002f59e  add     eax, r15d
0x18002f5a1  jnz     short loc_18002F5B3
0x18002f5a3  mov     rax, [rbx]
0x18002f5a6  mov     rcx, rbx
0x18002f5a9  mov     rax, [rax+8]
0x18002f5ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5b2  nop
0x18002f5b3  mov     rcx, [rsp+1C0h+var_170]
0x18002f5b8  mov     [rsp+1C0h+var_170], r14
0x18002f5bd  test    rcx, rcx
0x18002f5c0  jz      short loc_18002F5E4
0x18002f5c2  mov     eax, 2
0x18002f5c7  xchg    rax, [rcx+8]
0x18002f5cb  test    rax, rax
0x18002f5ce  jz      short loc_18002F5E4
0x18002f5d0  lea     rax, [rcx+30h]
0x18002f5d4  or      qword ptr [rax+8], 1
0x18002f5d9  mov     rcx, rax
0x18002f5dc  mov     rax, [rax]
0x18002f5df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5e4  mov     rcx, [rbp+0C0h+var_100]
0x18002f5e8  lea     rax, [rbp+0C0h+var_110]
0x18002f5ec  cmp     [rbp+0C0h+var_F8], 0Fh
0x18002f5f1  cmova   rax, [rbp+0C0h+var_110]
0x18002f5f6  mov     qword ptr [rbp+0C0h+var_130], rax
0x18002f5fa  mov     qword ptr [rbp+0C0h+var_130+8], rcx
0x18002f5fe  lea     rdx, [rbp+0C0h+var_130]
0x18002f602  lea     rcx, [rbp+0C0h+var_98]
0x18002f606  call    ?IncrementCorrelationVector@FidoUtils@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_zstring_view@D@wil@@@Z; FidoUtils::IncrementCorrelationVector(wil::basic_zstring_view<char>)
0x18002f60b  mov     rdx, rax
0x18002f60e  lea     rcx, [rbp+0C0h+var_110]
0x18002f612  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18002f617  lea     rcx, [rbp+0C0h+var_98]
0x18002f61b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002f620  mov     rsi, [rdi]
0x18002f623  lea     r15, [rbp+0C0h+var_F0]
0x18002f627  cmp     qword ptr [rbp+0C0h+var_E0+8], 7
0x18002f62c  cmova   r15, qword ptr [rbp+0C0h+var_F0]
0x18002f631  mov     qword ptr [rsp+1C0h+var_180], r14
0x18002f636  lea     rax, [rsp+1C0h+var_180]
0x18002f63b  mov     qword ptr [rbp+0C0h+var_130], rax
0x18002f63f  lea     rbx, [rbp+0C0h+var_110]
0x18002f643  cmp     [rbp+0C0h+var_F8], 0Fh
0x18002f648  cmova   rbx, [rbp+0C0h+var_110]
0x18002f64d  mov     ecx, 170h; Size
0x18002f652  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f657  mov     rdi, rax
0x18002f65a  mov     [rsp+1C0h+var_170], rax
0x18002f65f  lea     r14, [rax+60h]
0x18002f663  mov     [rsp+1C0h+var_170], r14
0x18002f668  mov     [r14+0D8h], rsi
0x18002f66f  mov     rax, [rsp+1C0h+var_160]
0x18002f674  mov     [r14+0E0h], rax
0x18002f67b  mov     [r14+0E8h], rbx
0x18002f682  mov     rcx, qword ptr [rsp+1C0h+var_180]
0x18002f687  mov     [r14+0F0h], rcx
0x18002f68e  mov     qword ptr [rsp+1C0h+var_180], 0
0x18002f697  mov     [r14+0F8h], r15
0x18002f69e  mov     dword ptr [r14+100h], 1
0x18002f6a9  lea     rax, wil__ProfileDataStore__DeleteItemAsync$_ResumeCoro$1_Windows__Data__Security__Passkey__RecoveryItemPdr_
0x18002f6b0  mov     [r14], rax
0x18002f6b3  mov     dword ptr [r14+8], 10002h
0x18002f6bb  xor     edx, edx; Val
0x18002f6bd  lea     r8d, [rdx+58h]; Size
0x18002f6c1  mov     rcx, rdi; void *
0x18002f6c4  call    memset_0
0x18002f6c9  nop
0x18002f6ca  mov     [rsp+1C0h+var_178], rdi
0x18002f6cf  xor     eax, eax
0x18002f6d1  mov     [r14+0D0h], al
0x18002f6d8  mov     rcx, r14
0x18002f6db  call    wil__ProfileDataStore__DeleteItemAsync$_ResumeCoro$1_Windows__Data__Security__Passkey__RecoveryItemPdr_
0x18002f6e0  nop
0x18002f6e1  mov     rcx, qword ptr [rsp+1C0h+var_180]
0x18002f6e6  test    rcx, rcx
0x18002f6e9  jz      short loc_18002F704
0x18002f6eb  or      eax, 0FFFFFFFFh
0x18002f6ee  lock xadd [rcx+8], eax
0x18002f6f3  cmp     eax, 1
0x18002f6f6  jnz     short loc_18002F704
0x18002f6f8  mov     rax, [rcx]
0x18002f6fb  mov     rax, [rax+8]
0x18002f6ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f704  mov     qword ptr [rsp+1C0h+var_180], 0
0x18002f70d  lea     rdx, [rbp+0C0h+var_98]
0x18002f711  lea     rcx, [rsp+1C0h+var_178]
0x18002f716  call    ?get@?$task_base@VProfileDataStoreSaveResult@wil@@@coro@details@wil@@QEHAA@XZ; wil::details::coro::task_base<wil::ProfileDataStoreSaveResult>::get(void)
0x18002f71b  mov     rbx, rax
0x18002f71e  mov     rcx, [rax]
0x18002f721  mov     [rbp+0C0h+var_D0], rcx
0x18002f725  mov     ecx, [rax+8]
0x18002f728  mov     [rbp+0C0h+var_C8], ecx
0x18002f72b  mov     ecx, [rax+0Ch]
0x18002f72e  mov     [rbp+0C0h+var_C4], ecx
0x18002f731  lea     rdx, [rax+10h]
0x18002f735  lea     rcx, [rbp+0C0h+var_C0]
0x18002f739  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002f73e  mov     rax, [rbx+30h]
0x18002f742  mov     [rbp+0C0h+var_A0], rax
0x18002f746  lea     rcx, [rbp+0C0h+var_88]
0x18002f74a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002f74f  nop
0x18002f750  mov     rcx, [rsp+1C0h+var_178]
0x18002f755  test    rcx, rcx
0x18002f758  jz      short loc_18002F77C
0x18002f75a  mov     eax, 2
0x18002f75f  xchg    rax, [rcx+8]
0x18002f763  test    rax, rax
0x18002f766  jz      short loc_18002F77C
0x18002f768  lea     rax, [rcx+60h]
0x18002f76c  or      qword ptr [rax+8], 1
0x18002f771  mov     rcx, rax
0x18002f774  mov     rax, [rax]
0x18002f777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f77c  mov     ebx, [rbp+0C0h+var_C4]
0x18002f77f  test    ebx, ebx
0x18002f781  jns     loc_18002F841
0x18002f787  mov     eax, cs:dword_180075000
0x18002f78d  cmp     eax, 4
0x18002f790  jbe     short loc_18002F7DF
0x18002f792  lea     rax, aProfiledatasto_1; "ProfileDataStore::DeleteItemAsync"
0x18002f799  mov     [rsp+1C0h+var_160], rax
0x18002f79e  lea     rax, [rbp+0C0h+var_110]
0x18002f7a2  cmp     [rbp+0C0h+var_F8], 0Fh
0x18002f7a7  cmova   rax, [rbp+0C0h+var_110]
0x18002f7ac  mov     [rsp+1C0h+var_178], rax
0x18002f7b1  mov     dword ptr [rsp+1C0h+var_170], ebx
0x18002f7b5  lea     rax, [rsp+1C0h+var_160]
0x18002f7ba  mov     [rsp+1C0h+var_190], rax
0x18002f7bf  lea     rax, [rsp+1C0h+var_178]
0x18002f7c4  mov     [rsp+1C0h+var_198], rax
0x18002f7c9  lea     rax, [rsp+1C0h+var_170]
0x18002f7ce  mov     qword ptr [rsp+1C0h+var_1A0], rax
0x18002f7d3  lea     rdx, unk_180069300
0x18002f7da  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18002f7df  xorps   xmm0, xmm0
0x18002f7e2  movups  [rbp+0C0h+var_130], xmm0
0x18002f7e6  xorps   xmm1, xmm1
0x18002f7e9  movdqu  [rbp+0C0h+var_120], xmm1
0x18002f7ee  mov     r8, [rsp+1C0h+var_158]
0x18002f7f3  mov     r8, [r8+8]
0x18002f7f7  mov     rdx, r13
0x18002f7fa  lea     rcx, [rbp+0C0h+var_130]
0x18002f7fe  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18002f803  lea     r9, [rbp+0C0h+var_130]
0x18002f807  cmp     qword ptr [rbp+0C0h+var_120+8], 0Fh
0x18002f80c  cmova   r9, qword ptr [rbp+0C0h+var_130]
0x18002f811  mov     [rsp+1C0h+var_1A0], ebx
0x18002f815  mov     r8, [rsp+1C0h+var_168]
0x18002f81a  mov     r8, [r8]
0x18002f81d  mov     rdx, [rsp+1C0h+var_150]
0x18002f822  mov     edx, [rdx]
0x18002f824  mov     ecx, 2
0x18002f829  call    cs:__imp_WebAuthNWriteEventCloudStoreOperationFailure
0x18002f82f  mov     rcx, [rbp+0C8h]
0x18002f836  test    eax, eax
0x18002f838  jns     short loc_18002F8AC
0x18002f83a  mov     edx, 230h
0x18002f83f  jmp     short loc_18002F89D
0x18002f841  xorps   xmm0, xmm0
0x18002f844  movups  [rbp+0C0h+var_130], xmm0
0x18002f848  xorps   xmm1, xmm1
0x18002f84b  movdqu  [rbp+0C0h+var_120], xmm1
0x18002f850  mov     r8, [rsp+1C0h+var_158]
0x18002f855  mov     r8, [r8+8]
0x18002f859  mov     rdx, r13
0x18002f85c  lea     rcx, [rbp+0C0h+var_130]
0x18002f860  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18002f865  lea     r9, [rbp+0C0h+var_130]
0x18002f869  cmp     qword ptr [rbp+0C0h+var_120+8], 0Fh
0x18002f86e  cmova   r9, qword ptr [rbp+0C0h+var_130]
0x18002f873  mov     r8, [rsp+1C0h+var_168]
0x18002f878  mov     r8, [r8]
0x18002f87b  mov     rdx, [rsp+1C0h+var_150]
0x18002f880  mov     edx, [rdx]
0x18002f882  mov     ecx, 2
0x18002f887  call    cs:__imp_WebAuthNWriteEventCloudStoreOperationSuccess
0x18002f88d  mov     rcx, [rbp+0C8h]; this
0x18002f894  test    eax, eax
0x18002f896  jns     short loc_18002F8AC
0x18002f898  mov     edx, 238h; void *
  ... truncated ...
```
