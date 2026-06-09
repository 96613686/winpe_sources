# PdrSyncUtils::DeleteImpl<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>(std::shared_ptr<wil::ProfileDataStore>,NgcPasskeys::SyncStore::PropertyType const &,wil::ProfileDataItemReference<Windows::Data::Security::Passkey::ScenarioKeysItemPdr> const &,wil::basic_zstring_view<ushort>,std::basic_string_view<char,std::char_traits<char>>,std::basic_string_view<ushort,std::char_traits<ushort>>)

- ea: `0x18002f964`
- end: `0x18002ff03`
- name: `??$DeleteImpl@UScenarioKeysItemPdr@Passkey@Security@Data@Windows@@@PdrSyncUtils@@YA?AUSaveResult@SyncStore@NgcPasskeys@@V?$shared_ptr@VProfileDataStore@wil@@@std@@AEBW4PropertyType@23@AEBV?$ProfileDataItemReference@UScenarioKeysItemPdr@Passkey@Security@Data@Windows@@@wil@@V?$basic_zstring_view@G@8@V?$basic_string_view@DU?$char_traits@D@std@@@5@V?$basic_string_view@GU?$char_traits@G@std@@@5@@Z`
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
- `0x18002f964`
- `0x180030b30`
- `0x180038f38`
- `0x180040d10`
- `0x18004f6ac`
- `0x18004f8fc`
- `0x180054c40`
- `0x180054ecc`
- `0x180061010`

## import_xrefs

- `webauthn!WebAuthNWriteEventCloudStoreOperationFailure` at `0x18002fdd1`
- `webauthn!WebAuthNWriteEventCloudStoreOperationFailure` at `0x18002fdd1`
- `webauthn!WebAuthNWriteEventCloudStoreOperationSuccess` at `0x18002fe2f`
- `webauthn!WebAuthNWriteEventCloudStoreOperationSuccess` at `0x18002fe2f`

## string_xrefs

- `0x18002fe48`: `onecore\ds\security\ngc\utils\pdr\lib\pdrsyncstore.cpp`
- `0x18002fd3a`: `ProfileDataStore::DeleteItemAsync`

## pseudocode

```c
int *__fastcall PdrSyncUtils::DeleteImpl<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>(
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
      (unsigned int)&word_180069366,
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
    v19 = wil::ProfileDataStore::LoadAsync<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>(
            *a2,
            (unsigned int)&v55,
            v7,
            (_DWORD)v18,
            (__int64)v53,
            34);
    v20 = (_QWORD *)wil::details::coro::task_base<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::get(
                      v19,
                      &v62);
    std::wstring::wstring(v74, *v20 + 184LL);
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
  v30[12] = wil::ProfileDataStore::DeleteItemAsync__ResumeCoro_1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_;
  *((_DWORD *)v30 + 26) = 65538;
  memset_0(v30, 0, 0x58u);
  v54 = v30;
  *((_BYTE *)v30 + 304) = 0;
  wil::ProfileDataStore::DeleteItemAsync__ResumeCoro_1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_(v30 + 12);
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
        (unsigned int)word_18006929A,
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
0x18002f964  push    rbp
0x18002f966  push    rbx
0x18002f967  push    rsi
0x18002f968  push    rdi
0x18002f969  push    r12
0x18002f96b  push    r13
0x18002f96d  push    r14
0x18002f96f  push    r15
0x18002f971  lea     rbp, [rsp-88h]
0x18002f979  sub     rsp, 188h
0x18002f980  mov     rax, cs:__security_cookie
0x18002f987  xor     rax, rsp
0x18002f98a  mov     [rbp+0C0h+var_50], rax
0x18002f98e  mov     rsi, r9
0x18002f991  mov     [rsp+1C0h+var_160], r9
0x18002f996  mov     [rsp+1C0h+var_150], r8
0x18002f99b  mov     rdi, rdx
0x18002f99e  mov     [rbp+0C0h+var_140], rdx
0x18002f9a2  mov     r12, rcx
0x18002f9a5  mov     [rsp+1C0h+var_168], rcx
0x18002f9aa  mov     [rbp+0C0h+var_138], rdx
0x18002f9ae  mov     rax, [rbp+0C0h+arg_20]
0x18002f9b5  mov     [rsp+1C0h+var_168], rax
0x18002f9ba  mov     rax, [rbp+0C0h+arg_28]
0x18002f9c1  mov     [rsp+1C0h+var_158], rax
0x18002f9c6  mov     rbx, [rbp+0C0h+arg_30]
0x18002f9cd  xor     r14d, r14d
0x18002f9d0  mov     r13, [rax]
0x18002f9d3  or      r15, 0FFFFFFFFFFFFFFFFh
0x18002f9d7  mov     rax, r15
0x18002f9da  inc     rax
0x18002f9dd  cmp     [rax+r13], r14b
0x18002f9e1  jnz     short loc_18002F9DA
0x18002f9e3  mov     qword ptr [rbp+0C0h+var_130], r13
0x18002f9e7  mov     qword ptr [rbp+0C0h+var_130+8], rax
0x18002f9eb  lea     rdx, [rbp+0C0h+var_130]
0x18002f9ef  lea     rcx, [rbp+0C0h+var_110]
0x18002f9f3  call    ?ExtendCorrelationVector@FidoUtils@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_zstring_view@D@wil@@@Z; FidoUtils::ExtendCorrelationVector(wil::basic_zstring_view<char>)
0x18002f9f8  nop
0x18002f9f9  mov     eax, cs:dword_180075000
0x18002f9ff  cmp     eax, 4
0x18002fa02  jbe     short loc_18002FA2D
0x18002fa04  lea     rax, [rbp+0C0h+var_110]
0x18002fa08  cmp     [rbp+0C0h+var_F8], 0Fh
0x18002fa0d  cmova   rax, [rbp+0C0h+var_110]
0x18002fa12  mov     [rsp+1C0h+var_178], rax
0x18002fa17  lea     rax, [rsp+1C0h+var_178]
0x18002fa1c  mov     qword ptr [rsp+1C0h+var_1A0], rax
0x18002fa21  lea     rdx, word_180069366
0x18002fa28  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18002fa2d  mov     [rbp+0C0h+var_D0], r14
0x18002fa31  xorps   xmm0, xmm0
0x18002fa34  movups  [rbp+0C0h+var_C0], xmm0
0x18002fa38  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002fa40  movdqu  [rbp+0C0h+var_B0], xmm1
0x18002fa45  mov     word ptr [rbp+0C0h+var_C0], r14w
0x18002fa4a  movups  [rbp+0C0h+var_F0], xmm0
0x18002fa4e  xorps   xmm1, xmm1
0x18002fa51  movdqu  [rbp+0C0h+var_E0], xmm1
0x18002fa56  mov     r8, [rbx+8]
0x18002fa5a  mov     rdx, [rbx]
0x18002fa5d  lea     rcx, [rbp+0C0h+var_F0]
0x18002fa61  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002fa66  nop
0x18002fa67  cmp     qword ptr [rbp+0C0h+var_E0], r14
0x18002fa6b  jnz     loc_18002FB8C
0x18002fa71  mov     rcx, [rbp+0C0h+var_100]
0x18002fa75  lea     rax, [rbp+0C0h+var_110]
0x18002fa79  cmp     [rbp+0C0h+var_F8], 0Fh
0x18002fa7e  cmova   rax, [rbp+0C0h+var_110]
0x18002fa83  mov     qword ptr [rbp+0C0h+var_130], rax
0x18002fa87  mov     qword ptr [rbp+0C0h+var_130+8], rcx
0x18002fa8b  lea     rdx, [rbp+0C0h+var_130]
0x18002fa8f  lea     rcx, [rbp+0C0h+var_98]
0x18002fa93  call    ?IncrementCorrelationVector@FidoUtils@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_zstring_view@D@wil@@@Z; FidoUtils::IncrementCorrelationVector(wil::basic_zstring_view<char>)
0x18002fa98  mov     rdx, rax
0x18002fa9b  lea     rcx, [rbp+0C0h+var_110]
0x18002fa9f  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18002faa4  lea     rcx, [rbp+0C0h+var_98]
0x18002faa8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002faad  mov     qword ptr [rsp+1C0h+var_180], r14
0x18002fab2  lea     r9, [rbp+0C0h+var_110]
0x18002fab6  cmp     [rbp+0C0h+var_F8], 0Fh
0x18002fabb  cmova   r9, [rbp+0C0h+var_110]
0x18002fac0  mov     dword ptr [rsp+1C0h+var_198], 22h ; '"'
0x18002fac8  lea     rax, [rsp+1C0h+var_180]
0x18002facd  mov     qword ptr [rsp+1C0h+var_1A0], rax; int
0x18002fad2  mov     r8, rsi
0x18002fad5  lea     rdx, [rsp+1C0h+var_170]
0x18002fada  mov     rcx, [rdi]
0x18002fadd  call    ??$LoadAsync@UScenarioKeysItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@QEAA?AU?$task@V?$shared_ptr@V?$ProfileDataItem@UScenarioKeysItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@1@AEBV?$ProfileDataItemReference@UScenarioKeysItemPdr@Passkey@Security@Data@Windows@@@1@PEBDVcancellation_token@Concurrency@@W4ProfileDataStoreLoadOptions@1@PEBG@Z; wil::ProfileDataStore::LoadAsync<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>(wil::ProfileDataItemReference<Windows::Data::Security::Passkey::ScenarioKeysItemPdr> const &,char const *,Concurrency::cancellation_token,wil::ProfileDataStoreLoadOptions,ushort const *)
0x18002fae2  nop
0x18002fae3  lea     rdx, [rbp+0C0h+var_130]
0x18002fae7  mov     rcx, rax
0x18002faea  call    ?get@?$task_base@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@coro@details@wil@@QEHAA@XZ; wil::details::coro::task_base<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::get(void)
0x18002faef  nop
0x18002faf0  mov     rdx, [rax]
0x18002faf3  add     rdx, 0B8h
0x18002fafa  lea     rcx, [rbp+0C0h+var_98]
0x18002fafe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002fb03  lea     rdx, [rbp+0C0h+var_98]
0x18002fb07  lea     rcx, [rbp+0C0h+var_F0]
0x18002fb0b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002fb10  lea     rcx, [rbp+0C0h+var_98]
0x18002fb14  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002fb19  nop
0x18002fb1a  mov     rbx, qword ptr [rbp+0C0h+var_130+8]
0x18002fb1e  test    rbx, rbx
0x18002fb21  jz      short loc_18002FB5B
0x18002fb23  mov     eax, r15d
0x18002fb26  lock xadd [rbx+8], eax
0x18002fb2b  add     eax, r15d
0x18002fb2e  jnz     short loc_18002FB5B
0x18002fb30  mov     rax, [rbx]
0x18002fb33  mov     rcx, rbx
0x18002fb36  mov     rax, [rax]
0x18002fb39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb3e  mov     eax, r15d
0x18002fb41  lock xadd [rbx+0Ch], eax
0x18002fb46  add     eax, r15d
0x18002fb49  jnz     short loc_18002FB5B
0x18002fb4b  mov     rax, [rbx]
0x18002fb4e  mov     rcx, rbx
0x18002fb51  mov     rax, [rax+8]
0x18002fb55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb5a  nop
0x18002fb5b  mov     rcx, [rsp+1C0h+var_170]
0x18002fb60  mov     [rsp+1C0h+var_170], r14
0x18002fb65  test    rcx, rcx
0x18002fb68  jz      short loc_18002FB8C
0x18002fb6a  mov     eax, 2
0x18002fb6f  xchg    rax, [rcx+8]
0x18002fb73  test    rax, rax
0x18002fb76  jz      short loc_18002FB8C
0x18002fb78  lea     rax, [rcx+30h]
0x18002fb7c  or      qword ptr [rax+8], 1
0x18002fb81  mov     rcx, rax
0x18002fb84  mov     rax, [rax]
0x18002fb87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb8c  mov     rcx, [rbp+0C0h+var_100]
0x18002fb90  lea     rax, [rbp+0C0h+var_110]
0x18002fb94  cmp     [rbp+0C0h+var_F8], 0Fh
0x18002fb99  cmova   rax, [rbp+0C0h+var_110]
0x18002fb9e  mov     qword ptr [rbp+0C0h+var_130], rax
0x18002fba2  mov     qword ptr [rbp+0C0h+var_130+8], rcx
0x18002fba6  lea     rdx, [rbp+0C0h+var_130]
0x18002fbaa  lea     rcx, [rbp+0C0h+var_98]
0x18002fbae  call    ?IncrementCorrelationVector@FidoUtils@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_zstring_view@D@wil@@@Z; FidoUtils::IncrementCorrelationVector(wil::basic_zstring_view<char>)
0x18002fbb3  mov     rdx, rax
0x18002fbb6  lea     rcx, [rbp+0C0h+var_110]
0x18002fbba  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18002fbbf  lea     rcx, [rbp+0C0h+var_98]
0x18002fbc3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002fbc8  mov     rsi, [rdi]
0x18002fbcb  lea     r15, [rbp+0C0h+var_F0]
0x18002fbcf  cmp     qword ptr [rbp+0C0h+var_E0+8], 7
0x18002fbd4  cmova   r15, qword ptr [rbp+0C0h+var_F0]
0x18002fbd9  mov     qword ptr [rsp+1C0h+var_180], r14
0x18002fbde  lea     rax, [rsp+1C0h+var_180]
0x18002fbe3  mov     qword ptr [rbp+0C0h+var_130], rax
0x18002fbe7  lea     rbx, [rbp+0C0h+var_110]
0x18002fbeb  cmp     [rbp+0C0h+var_F8], 0Fh
0x18002fbf0  cmova   rbx, [rbp+0C0h+var_110]
0x18002fbf5  mov     ecx, 170h; Size
0x18002fbfa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002fbff  mov     rdi, rax
0x18002fc02  mov     [rsp+1C0h+var_170], rax
0x18002fc07  lea     r14, [rax+60h]
0x18002fc0b  mov     [rsp+1C0h+var_170], r14
0x18002fc10  mov     [r14+0D8h], rsi
0x18002fc17  mov     rax, [rsp+1C0h+var_160]
0x18002fc1c  mov     [r14+0E0h], rax
0x18002fc23  mov     [r14+0E8h], rbx
0x18002fc2a  mov     rcx, qword ptr [rsp+1C0h+var_180]
0x18002fc2f  mov     [r14+0F0h], rcx
0x18002fc36  mov     qword ptr [rsp+1C0h+var_180], 0
0x18002fc3f  mov     [r14+0F8h], r15
0x18002fc46  mov     dword ptr [r14+100h], 1
0x18002fc51  lea     rax, wil__ProfileDataStore__DeleteItemAsync$_ResumeCoro$1_Windows__Data__Security__Passkey__ScenarioKeysItemPdr_
0x18002fc58  mov     [r14], rax
0x18002fc5b  mov     dword ptr [r14+8], 10002h
0x18002fc63  xor     edx, edx; Val
0x18002fc65  lea     r8d, [rdx+58h]; Size
0x18002fc69  mov     rcx, rdi; void *
0x18002fc6c  call    memset_0
0x18002fc71  nop
0x18002fc72  mov     [rsp+1C0h+var_178], rdi
0x18002fc77  xor     eax, eax
0x18002fc79  mov     [r14+0D0h], al
0x18002fc80  mov     rcx, r14
0x18002fc83  call    wil__ProfileDataStore__DeleteItemAsync$_ResumeCoro$1_Windows__Data__Security__Passkey__ScenarioKeysItemPdr_
0x18002fc88  nop
0x18002fc89  mov     rcx, qword ptr [rsp+1C0h+var_180]
0x18002fc8e  test    rcx, rcx
0x18002fc91  jz      short loc_18002FCAC
0x18002fc93  or      eax, 0FFFFFFFFh
0x18002fc96  lock xadd [rcx+8], eax
0x18002fc9b  cmp     eax, 1
0x18002fc9e  jnz     short loc_18002FCAC
0x18002fca0  mov     rax, [rcx]
0x18002fca3  mov     rax, [rax+8]
0x18002fca7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fcac  mov     qword ptr [rsp+1C0h+var_180], 0
0x18002fcb5  lea     rdx, [rbp+0C0h+var_98]
0x18002fcb9  lea     rcx, [rsp+1C0h+var_178]
0x18002fcbe  call    ?get@?$task_base@VProfileDataStoreSaveResult@wil@@@coro@details@wil@@QEHAA@XZ; wil::details::coro::task_base<wil::ProfileDataStoreSaveResult>::get(void)
0x18002fcc3  mov     rbx, rax
0x18002fcc6  mov     rcx, [rax]
0x18002fcc9  mov     [rbp+0C0h+var_D0], rcx
0x18002fccd  mov     ecx, [rax+8]
0x18002fcd0  mov     [rbp+0C0h+var_C8], ecx
0x18002fcd3  mov     ecx, [rax+0Ch]
0x18002fcd6  mov     [rbp+0C0h+var_C4], ecx
0x18002fcd9  lea     rdx, [rax+10h]
0x18002fcdd  lea     rcx, [rbp+0C0h+var_C0]
0x18002fce1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002fce6  mov     rax, [rbx+30h]
0x18002fcea  mov     [rbp+0C0h+var_A0], rax
0x18002fcee  lea     rcx, [rbp+0C0h+var_88]
0x18002fcf2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002fcf7  nop
0x18002fcf8  mov     rcx, [rsp+1C0h+var_178]
0x18002fcfd  test    rcx, rcx
0x18002fd00  jz      short loc_18002FD24
0x18002fd02  mov     eax, 2
0x18002fd07  xchg    rax, [rcx+8]
0x18002fd0b  test    rax, rax
0x18002fd0e  jz      short loc_18002FD24
0x18002fd10  lea     rax, [rcx+60h]
0x18002fd14  or      qword ptr [rax+8], 1
0x18002fd19  mov     rcx, rax
0x18002fd1c  mov     rax, [rax]
0x18002fd1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd24  mov     ebx, [rbp+0C0h+var_C4]
0x18002fd27  test    ebx, ebx
0x18002fd29  jns     loc_18002FDE9
0x18002fd2f  mov     eax, cs:dword_180075000
0x18002fd35  cmp     eax, 4
0x18002fd38  jbe     short loc_18002FD87
0x18002fd3a  lea     rax, aProfiledatasto_1; "ProfileDataStore::DeleteItemAsync"
0x18002fd41  mov     [rsp+1C0h+var_160], rax
0x18002fd46  lea     rax, [rbp+0C0h+var_110]
0x18002fd4a  cmp     [rbp+0C0h+var_F8], 0Fh
0x18002fd4f  cmova   rax, [rbp+0C0h+var_110]
0x18002fd54  mov     [rsp+1C0h+var_178], rax
0x18002fd59  mov     dword ptr [rsp+1C0h+var_170], ebx
0x18002fd5d  lea     rax, [rsp+1C0h+var_160]
0x18002fd62  mov     [rsp+1C0h+var_190], rax
0x18002fd67  lea     rax, [rsp+1C0h+var_178]
0x18002fd6c  mov     [rsp+1C0h+var_198], rax
0x18002fd71  lea     rax, [rsp+1C0h+var_170]
0x18002fd76  mov     qword ptr [rsp+1C0h+var_1A0], rax
0x18002fd7b  lea     rdx, word_18006929A
0x18002fd82  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18002fd87  xorps   xmm0, xmm0
0x18002fd8a  movups  [rbp+0C0h+var_130], xmm0
0x18002fd8e  xorps   xmm1, xmm1
0x18002fd91  movdqu  [rbp+0C0h+var_120], xmm1
0x18002fd96  mov     r8, [rsp+1C0h+var_158]
0x18002fd9b  mov     r8, [r8+8]
0x18002fd9f  mov     rdx, r13
0x18002fda2  lea     rcx, [rbp+0C0h+var_130]
0x18002fda6  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18002fdab  lea     r9, [rbp+0C0h+var_130]
0x18002fdaf  cmp     qword ptr [rbp+0C0h+var_120+8], 0Fh
0x18002fdb4  cmova   r9, qword ptr [rbp+0C0h+var_130]
0x18002fdb9  mov     [rsp+1C0h+var_1A0], ebx
0x18002fdbd  mov     r8, [rsp+1C0h+var_168]
0x18002fdc2  mov     r8, [r8]
0x18002fdc5  mov     rdx, [rsp+1C0h+var_150]
0x18002fdca  mov     edx, [rdx]
0x18002fdcc  mov     ecx, 2
0x18002fdd1  call    cs:__imp_WebAuthNWriteEventCloudStoreOperationFailure
0x18002fdd7  mov     rcx, [rbp+0C8h]
0x18002fdde  test    eax, eax
0x18002fde0  jns     short loc_18002FE54
0x18002fde2  mov     edx, 230h
0x18002fde7  jmp     short loc_18002FE45
0x18002fde9  xorps   xmm0, xmm0
0x18002fdec  movups  [rbp+0C0h+var_130], xmm0
0x18002fdf0  xorps   xmm1, xmm1
0x18002fdf3  movdqu  [rbp+0C0h+var_120], xmm1
0x18002fdf8  mov     r8, [rsp+1C0h+var_158]
0x18002fdfd  mov     r8, [r8+8]
0x18002fe01  mov     rdx, r13
0x18002fe04  lea     rcx, [rbp+0C0h+var_130]
0x18002fe08  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18002fe0d  lea     r9, [rbp+0C0h+var_130]
0x18002fe11  cmp     qword ptr [rbp+0C0h+var_120+8], 0Fh
0x18002fe16  cmova   r9, qword ptr [rbp+0C0h+var_130]
0x18002fe1b  mov     r8, [rsp+1C0h+var_168]
0x18002fe20  mov     r8, [r8]
0x18002fe23  mov     rdx, [rsp+1C0h+var_150]
0x18002fe28  mov     edx, [rdx]
0x18002fe2a  mov     ecx, 2
0x18002fe2f  call    cs:__imp_WebAuthNWriteEventCloudStoreOperationSuccess
0x18002fe35  mov     rcx, [rbp+0C8h]; this
0x18002fe3c  test    eax, eax
0x18002fe3e  jns     short loc_18002FE54
0x18002fe40  mov     edx, 238h; void *
  ... truncated ...
```
