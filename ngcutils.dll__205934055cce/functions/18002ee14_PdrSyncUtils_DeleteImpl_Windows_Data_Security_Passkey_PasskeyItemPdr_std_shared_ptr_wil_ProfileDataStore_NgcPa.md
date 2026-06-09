# PdrSyncUtils::DeleteImpl<Windows::Data::Security::Passkey::PasskeyItemPdr>(std::shared_ptr<wil::ProfileDataStore>,NgcPasskeys::SyncStore::PropertyType const &,wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> const &,wil::basic_zstring_view<ushort>,std::basic_string_view<char,std::char_traits<char>>,std::basic_string_view<ushort,std::char_traits<ushort>>)

- ea: `0x18002ee14`
- end: `0x18002f3b3`
- name: `??$DeleteImpl@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@PdrSyncUtils@@YA?AUSaveResult@SyncStore@NgcPasskeys@@V?$shared_ptr@VProfileDataStore@wil@@@std@@AEBW4PropertyType@23@AEBV?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@V?$basic_zstring_view@G@8@V?$basic_string_view@DU?$char_traits@D@std@@@5@V?$basic_string_view@GU?$char_traits@G@std@@@5@@Z`
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
- `0x18002ee14`
- `0x18002ff10`
- `0x180038d50`
- `0x180040d10`
- `0x18004f6ac`
- `0x18004f8fc`
- `0x180054c40`
- `0x180054ecc`
- `0x180061010`

## import_xrefs

- `webauthn!WebAuthNWriteEventCloudStoreOperationFailure` at `0x18002f281`
- `webauthn!WebAuthNWriteEventCloudStoreOperationFailure` at `0x18002f281`
- `webauthn!WebAuthNWriteEventCloudStoreOperationSuccess` at `0x18002f2df`
- `webauthn!WebAuthNWriteEventCloudStoreOperationSuccess` at `0x18002f2df`

## string_xrefs

- `0x18002f2f8`: `onecore\ds\security\ngc\utils\pdr\lib\pdrsyncstore.cpp`
- `0x18002f1ea`: `ProfileDataStore::DeleteItemAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
int *__fastcall PdrSyncUtils::DeleteImpl<Windows::Data::Security::Passkey::PasskeyItemPdr>(
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
      (unsigned int)&unk_180069448,
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
    v19 = wil::ProfileDataStore::LoadAsync<Windows::Data::Security::Passkey::PasskeyItemPdr>(
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
  v30[12] = wil::ProfileDataStore::DeleteItemAsync__ResumeCoro_1_Windows::Data::Security::Passkey::PasskeyItemPdr_;
  *((_DWORD *)v30 + 26) = 65538;
  memset_0(v30, 0, 0x58u);
  v54 = v30;
  *((_BYTE *)v30 + 304) = 0;
  wil::ProfileDataStore::DeleteItemAsync__ResumeCoro_1_Windows::Data::Security::Passkey::PasskeyItemPdr_(v30 + 12);
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
        (unsigned int)&dword_1800693A4,
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
0x18002ee14  push    rbp
0x18002ee16  push    rbx
0x18002ee17  push    rsi
0x18002ee18  push    rdi
0x18002ee19  push    r12
0x18002ee1b  push    r13
0x18002ee1d  push    r14
0x18002ee1f  push    r15
0x18002ee21  lea     rbp, [rsp-88h]
0x18002ee29  sub     rsp, 188h
0x18002ee30  mov     rax, cs:__security_cookie
0x18002ee37  xor     rax, rsp
0x18002ee3a  mov     [rbp+0C0h+var_50], rax
0x18002ee3e  mov     rsi, r9
0x18002ee41  mov     [rsp+1C0h+var_160], r9
0x18002ee46  mov     [rsp+1C0h+var_150], r8
0x18002ee4b  mov     rdi, rdx
0x18002ee4e  mov     [rbp+0C0h+var_140], rdx
0x18002ee52  mov     r12, rcx
0x18002ee55  mov     [rsp+1C0h+var_168], rcx
0x18002ee5a  mov     [rbp+0C0h+var_138], rdx
0x18002ee5e  mov     rax, [rbp+0C0h+arg_20]
0x18002ee65  mov     [rsp+1C0h+var_168], rax
0x18002ee6a  mov     rax, [rbp+0C0h+arg_28]
0x18002ee71  mov     [rsp+1C0h+var_158], rax
0x18002ee76  mov     rbx, [rbp+0C0h+arg_30]
0x18002ee7d  xor     r14d, r14d
0x18002ee80  mov     r13, [rax]
0x18002ee83  or      r15, 0FFFFFFFFFFFFFFFFh
0x18002ee87  mov     rax, r15
0x18002ee8a  inc     rax
0x18002ee8d  cmp     [rax+r13], r14b
0x18002ee91  jnz     short loc_18002EE8A
0x18002ee93  mov     qword ptr [rbp+0C0h+var_130], r13
0x18002ee97  mov     qword ptr [rbp+0C0h+var_130+8], rax
0x18002ee9b  lea     rdx, [rbp+0C0h+var_130]
0x18002ee9f  lea     rcx, [rbp+0C0h+var_110]
0x18002eea3  call    ?ExtendCorrelationVector@FidoUtils@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_zstring_view@D@wil@@@Z; FidoUtils::ExtendCorrelationVector(wil::basic_zstring_view<char>)
0x18002eea8  nop
0x18002eea9  mov     eax, cs:dword_180075000
0x18002eeaf  cmp     eax, 4
0x18002eeb2  jbe     short loc_18002EEDD
0x18002eeb4  lea     rax, [rbp+0C0h+var_110]
0x18002eeb8  cmp     [rbp+0C0h+var_F8], 0Fh
0x18002eebd  cmova   rax, [rbp+0C0h+var_110]
0x18002eec2  mov     [rsp+1C0h+var_178], rax
0x18002eec7  lea     rax, [rsp+1C0h+var_178]
0x18002eecc  mov     qword ptr [rsp+1C0h+var_1A0], rax
0x18002eed1  lea     rdx, unk_180069448
0x18002eed8  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18002eedd  mov     [rbp+0C0h+var_D0], r14
0x18002eee1  xorps   xmm0, xmm0
0x18002eee4  movups  [rbp+0C0h+var_C0], xmm0
0x18002eee8  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002eef0  movdqu  [rbp+0C0h+var_B0], xmm1
0x18002eef5  mov     word ptr [rbp+0C0h+var_C0], r14w
0x18002eefa  movups  [rbp+0C0h+var_F0], xmm0
0x18002eefe  xorps   xmm1, xmm1
0x18002ef01  movdqu  [rbp+0C0h+var_E0], xmm1
0x18002ef06  mov     r8, [rbx+8]
0x18002ef0a  mov     rdx, [rbx]
0x18002ef0d  lea     rcx, [rbp+0C0h+var_F0]
0x18002ef11  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002ef16  nop
0x18002ef17  cmp     qword ptr [rbp+0C0h+var_E0], r14
0x18002ef1b  jnz     loc_18002F03C
0x18002ef21  mov     rcx, [rbp+0C0h+var_100]
0x18002ef25  lea     rax, [rbp+0C0h+var_110]
0x18002ef29  cmp     [rbp+0C0h+var_F8], 0Fh
0x18002ef2e  cmova   rax, [rbp+0C0h+var_110]
0x18002ef33  mov     qword ptr [rbp+0C0h+var_130], rax
0x18002ef37  mov     qword ptr [rbp+0C0h+var_130+8], rcx
0x18002ef3b  lea     rdx, [rbp+0C0h+var_130]
0x18002ef3f  lea     rcx, [rbp+0C0h+var_98]
0x18002ef43  call    ?IncrementCorrelationVector@FidoUtils@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_zstring_view@D@wil@@@Z; FidoUtils::IncrementCorrelationVector(wil::basic_zstring_view<char>)
0x18002ef48  mov     rdx, rax
0x18002ef4b  lea     rcx, [rbp+0C0h+var_110]
0x18002ef4f  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18002ef54  lea     rcx, [rbp+0C0h+var_98]
0x18002ef58  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002ef5d  mov     qword ptr [rsp+1C0h+var_180], r14
0x18002ef62  lea     r9, [rbp+0C0h+var_110]
0x18002ef66  cmp     [rbp+0C0h+var_F8], 0Fh
0x18002ef6b  cmova   r9, [rbp+0C0h+var_110]
0x18002ef70  mov     dword ptr [rsp+1C0h+var_198], 22h ; '"'
0x18002ef78  lea     rax, [rsp+1C0h+var_180]
0x18002ef7d  mov     qword ptr [rsp+1C0h+var_1A0], rax; int
0x18002ef82  mov     r8, rsi
0x18002ef85  lea     rdx, [rsp+1C0h+var_170]
0x18002ef8a  mov     rcx, [rdi]
0x18002ef8d  call    ??$LoadAsync@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@QEAA?AU?$task@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@1@AEBV?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@1@PEBDVcancellation_token@Concurrency@@W4ProfileDataStoreLoadOptions@1@PEBG@Z; wil::ProfileDataStore::LoadAsync<Windows::Data::Security::Passkey::PasskeyItemPdr>(wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> const &,char const *,Concurrency::cancellation_token,wil::ProfileDataStoreLoadOptions,ushort const *)
0x18002ef92  nop
0x18002ef93  lea     rdx, [rbp+0C0h+var_130]
0x18002ef97  mov     rcx, rax
0x18002ef9a  call    ?get@?$task_base@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@coro@details@wil@@QEHAA@XZ; wil::details::coro::task_base<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::get(void)
0x18002ef9f  nop
0x18002efa0  mov     rdx, [rax]
0x18002efa3  add     rdx, 0B8h
0x18002efaa  lea     rcx, [rbp+0C0h+var_98]
0x18002efae  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002efb3  lea     rdx, [rbp+0C0h+var_98]
0x18002efb7  lea     rcx, [rbp+0C0h+var_F0]
0x18002efbb  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002efc0  lea     rcx, [rbp+0C0h+var_98]
0x18002efc4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002efc9  nop
0x18002efca  mov     rbx, qword ptr [rbp+0C0h+var_130+8]
0x18002efce  test    rbx, rbx
0x18002efd1  jz      short loc_18002F00B
0x18002efd3  mov     eax, r15d
0x18002efd6  lock xadd [rbx+8], eax
0x18002efdb  add     eax, r15d
0x18002efde  jnz     short loc_18002F00B
0x18002efe0  mov     rax, [rbx]
0x18002efe3  mov     rcx, rbx
0x18002efe6  mov     rax, [rax]
0x18002efe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efee  mov     eax, r15d
0x18002eff1  lock xadd [rbx+0Ch], eax
0x18002eff6  add     eax, r15d
0x18002eff9  jnz     short loc_18002F00B
0x18002effb  mov     rax, [rbx]
0x18002effe  mov     rcx, rbx
0x18002f001  mov     rax, [rax+8]
0x18002f005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f00a  nop
0x18002f00b  mov     rcx, [rsp+1C0h+var_170]
0x18002f010  mov     [rsp+1C0h+var_170], r14
0x18002f015  test    rcx, rcx
0x18002f018  jz      short loc_18002F03C
0x18002f01a  mov     eax, 2
0x18002f01f  xchg    rax, [rcx+8]
0x18002f023  test    rax, rax
0x18002f026  jz      short loc_18002F03C
0x18002f028  lea     rax, [rcx+30h]
0x18002f02c  or      qword ptr [rax+8], 1
0x18002f031  mov     rcx, rax
0x18002f034  mov     rax, [rax]
0x18002f037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f03c  mov     rcx, [rbp+0C0h+var_100]
0x18002f040  lea     rax, [rbp+0C0h+var_110]
0x18002f044  cmp     [rbp+0C0h+var_F8], 0Fh
0x18002f049  cmova   rax, [rbp+0C0h+var_110]
0x18002f04e  mov     qword ptr [rbp+0C0h+var_130], rax
0x18002f052  mov     qword ptr [rbp+0C0h+var_130+8], rcx
0x18002f056  lea     rdx, [rbp+0C0h+var_130]
0x18002f05a  lea     rcx, [rbp+0C0h+var_98]
0x18002f05e  call    ?IncrementCorrelationVector@FidoUtils@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_zstring_view@D@wil@@@Z; FidoUtils::IncrementCorrelationVector(wil::basic_zstring_view<char>)
0x18002f063  mov     rdx, rax
0x18002f066  lea     rcx, [rbp+0C0h+var_110]
0x18002f06a  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18002f06f  lea     rcx, [rbp+0C0h+var_98]
0x18002f073  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002f078  mov     rsi, [rdi]
0x18002f07b  lea     r15, [rbp+0C0h+var_F0]
0x18002f07f  cmp     qword ptr [rbp+0C0h+var_E0+8], 7
0x18002f084  cmova   r15, qword ptr [rbp+0C0h+var_F0]
0x18002f089  mov     qword ptr [rsp+1C0h+var_180], r14
0x18002f08e  lea     rax, [rsp+1C0h+var_180]
0x18002f093  mov     qword ptr [rbp+0C0h+var_130], rax
0x18002f097  lea     rbx, [rbp+0C0h+var_110]
0x18002f09b  cmp     [rbp+0C0h+var_F8], 0Fh
0x18002f0a0  cmova   rbx, [rbp+0C0h+var_110]
0x18002f0a5  mov     ecx, 170h; Size
0x18002f0aa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f0af  mov     rdi, rax
0x18002f0b2  mov     [rsp+1C0h+var_170], rax
0x18002f0b7  lea     r14, [rax+60h]
0x18002f0bb  mov     [rsp+1C0h+var_170], r14
0x18002f0c0  mov     [r14+0D8h], rsi
0x18002f0c7  mov     rax, [rsp+1C0h+var_160]
0x18002f0cc  mov     [r14+0E0h], rax
0x18002f0d3  mov     [r14+0E8h], rbx
0x18002f0da  mov     rcx, qword ptr [rsp+1C0h+var_180]
0x18002f0df  mov     [r14+0F0h], rcx
0x18002f0e6  mov     qword ptr [rsp+1C0h+var_180], 0
0x18002f0ef  mov     [r14+0F8h], r15
0x18002f0f6  mov     dword ptr [r14+100h], 1
0x18002f101  lea     rax, wil__ProfileDataStore__DeleteItemAsync$_ResumeCoro$1_Windows__Data__Security__Passkey__PasskeyItemPdr_
0x18002f108  mov     [r14], rax
0x18002f10b  mov     dword ptr [r14+8], 10002h
0x18002f113  xor     edx, edx; Val
0x18002f115  lea     r8d, [rdx+58h]; Size
0x18002f119  mov     rcx, rdi; void *
0x18002f11c  call    memset_0
0x18002f121  nop
0x18002f122  mov     [rsp+1C0h+var_178], rdi
0x18002f127  xor     eax, eax
0x18002f129  mov     [r14+0D0h], al
0x18002f130  mov     rcx, r14
0x18002f133  call    wil__ProfileDataStore__DeleteItemAsync$_ResumeCoro$1_Windows__Data__Security__Passkey__PasskeyItemPdr_
0x18002f138  nop
0x18002f139  mov     rcx, qword ptr [rsp+1C0h+var_180]
0x18002f13e  test    rcx, rcx
0x18002f141  jz      short loc_18002F15C
0x18002f143  or      eax, 0FFFFFFFFh
0x18002f146  lock xadd [rcx+8], eax
0x18002f14b  cmp     eax, 1
0x18002f14e  jnz     short loc_18002F15C
0x18002f150  mov     rax, [rcx]
0x18002f153  mov     rax, [rax+8]
0x18002f157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f15c  mov     qword ptr [rsp+1C0h+var_180], 0
0x18002f165  lea     rdx, [rbp+0C0h+var_98]
0x18002f169  lea     rcx, [rsp+1C0h+var_178]
0x18002f16e  call    ?get@?$task_base@VProfileDataStoreSaveResult@wil@@@coro@details@wil@@QEHAA@XZ; wil::details::coro::task_base<wil::ProfileDataStoreSaveResult>::get(void)
0x18002f173  mov     rbx, rax
0x18002f176  mov     rcx, [rax]
0x18002f179  mov     [rbp+0C0h+var_D0], rcx
0x18002f17d  mov     ecx, [rax+8]
0x18002f180  mov     [rbp+0C0h+var_C8], ecx
0x18002f183  mov     ecx, [rax+0Ch]
0x18002f186  mov     [rbp+0C0h+var_C4], ecx
0x18002f189  lea     rdx, [rax+10h]
0x18002f18d  lea     rcx, [rbp+0C0h+var_C0]
0x18002f191  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002f196  mov     rax, [rbx+30h]
0x18002f19a  mov     [rbp+0C0h+var_A0], rax
0x18002f19e  lea     rcx, [rbp+0C0h+var_88]
0x18002f1a2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002f1a7  nop
0x18002f1a8  mov     rcx, [rsp+1C0h+var_178]
0x18002f1ad  test    rcx, rcx
0x18002f1b0  jz      short loc_18002F1D4
0x18002f1b2  mov     eax, 2
0x18002f1b7  xchg    rax, [rcx+8]
0x18002f1bb  test    rax, rax
0x18002f1be  jz      short loc_18002F1D4
0x18002f1c0  lea     rax, [rcx+60h]
0x18002f1c4  or      qword ptr [rax+8], 1
0x18002f1c9  mov     rcx, rax
0x18002f1cc  mov     rax, [rax]
0x18002f1cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1d4  mov     ebx, [rbp+0C0h+var_C4]
0x18002f1d7  test    ebx, ebx
0x18002f1d9  jns     loc_18002F299
0x18002f1df  mov     eax, cs:dword_180075000
0x18002f1e5  cmp     eax, 4
0x18002f1e8  jbe     short loc_18002F237
0x18002f1ea  lea     rax, aProfiledatasto_1; "ProfileDataStore::DeleteItemAsync"
0x18002f1f1  mov     [rsp+1C0h+var_160], rax
0x18002f1f6  lea     rax, [rbp+0C0h+var_110]
0x18002f1fa  cmp     [rbp+0C0h+var_F8], 0Fh
0x18002f1ff  cmova   rax, [rbp+0C0h+var_110]
0x18002f204  mov     [rsp+1C0h+var_178], rax
0x18002f209  mov     dword ptr [rsp+1C0h+var_170], ebx
0x18002f20d  lea     rax, [rsp+1C0h+var_160]
0x18002f212  mov     [rsp+1C0h+var_190], rax
0x18002f217  lea     rax, [rsp+1C0h+var_178]
0x18002f21c  mov     [rsp+1C0h+var_198], rax
0x18002f221  lea     rax, [rsp+1C0h+var_170]
0x18002f226  mov     qword ptr [rsp+1C0h+var_1A0], rax
0x18002f22b  lea     rdx, dword_1800693A4
0x18002f232  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18002f237  xorps   xmm0, xmm0
0x18002f23a  movups  [rbp+0C0h+var_130], xmm0
0x18002f23e  xorps   xmm1, xmm1
0x18002f241  movdqu  [rbp+0C0h+var_120], xmm1
0x18002f246  mov     r8, [rsp+1C0h+var_158]
0x18002f24b  mov     r8, [r8+8]
0x18002f24f  mov     rdx, r13
0x18002f252  lea     rcx, [rbp+0C0h+var_130]
0x18002f256  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18002f25b  lea     r9, [rbp+0C0h+var_130]
0x18002f25f  cmp     qword ptr [rbp+0C0h+var_120+8], 0Fh
0x18002f264  cmova   r9, qword ptr [rbp+0C0h+var_130]
0x18002f269  mov     [rsp+1C0h+var_1A0], ebx
0x18002f26d  mov     r8, [rsp+1C0h+var_168]
0x18002f272  mov     r8, [r8]
0x18002f275  mov     rdx, [rsp+1C0h+var_150]
0x18002f27a  mov     edx, [rdx]
0x18002f27c  mov     ecx, 2
0x18002f281  call    cs:__imp_WebAuthNWriteEventCloudStoreOperationFailure
0x18002f287  mov     rcx, [rbp+0C8h]
0x18002f28e  test    eax, eax
0x18002f290  jns     short loc_18002F304
0x18002f292  mov     edx, 230h
0x18002f297  jmp     short loc_18002F2F5
0x18002f299  xorps   xmm0, xmm0
0x18002f29c  movups  [rbp+0C0h+var_130], xmm0
0x18002f2a0  xorps   xmm1, xmm1
0x18002f2a3  movdqu  [rbp+0C0h+var_120], xmm1
0x18002f2a8  mov     r8, [rsp+1C0h+var_158]
0x18002f2ad  mov     r8, [r8+8]
0x18002f2b1  mov     rdx, r13
0x18002f2b4  lea     rcx, [rbp+0C0h+var_130]
0x18002f2b8  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18002f2bd  lea     r9, [rbp+0C0h+var_130]
0x18002f2c1  cmp     qword ptr [rbp+0C0h+var_120+8], 0Fh
0x18002f2c6  cmova   r9, qword ptr [rbp+0C0h+var_130]
0x18002f2cb  mov     r8, [rsp+1C0h+var_168]
0x18002f2d0  mov     r8, [r8]
0x18002f2d3  mov     rdx, [rsp+1C0h+var_150]
0x18002f2d8  mov     edx, [rdx]
0x18002f2da  mov     ecx, 2
0x18002f2df  call    cs:__imp_WebAuthNWriteEventCloudStoreOperationSuccess
0x18002f2e5  mov     rcx, [rbp+0C8h]; this
0x18002f2ec  test    eax, eax
0x18002f2ee  jns     short loc_18002F304
0x18002f2f0  mov     edx, 238h; void *
  ... truncated ...
```
