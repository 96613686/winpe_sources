# PdrSyncUtils::LoadImpl_Windows::Data::Security::Passkey::RecoveryItemPdr_

- ea: `0x1800395ec`
- end: `0x180039ba4`
- name: `PdrSyncUtils::LoadImpl_Windows::Data::Security::Passkey::RecoveryItemPdr_`
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
- `0x180038e44`
- `0x1800395ec`
- `0x180040d10`
- `0x180043f84`
- `0x18004f6ac`
- `0x180054c40`
- `0x180054ecc`
- `0x180061010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180039834`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180039834`
- `webauthn!WebAuthNWriteEventCloudStoreOperationFailure` at `0x180039975`
- `webauthn!WebAuthNWriteEventCloudStoreOperationFailure` at `0x180039975`
- `webauthn!WebAuthNWriteEventCloudStoreOperationSuccess` at `0x180039a1e`
- `webauthn!WebAuthNWriteEventCloudStoreOperationSuccess` at `0x180039a1e`

## string_xrefs

- `0x180039989`: `onecore\ds\security\ngc\utils\pdr\lib\pdrsyncstore.cpp`
- `0x180039a32`: `onecore\ds\security\ngc\utils\pdr\lib\pdrsyncstore.cpp`

## pseudocode

```c
__int64 __fastcall PdrSyncUtils::LoadImpl_Windows::Data::Security::Passkey::RecoveryItemPdr_(
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
      (unsigned int)&byte_180069BCF,
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
  v19 = wil::ProfileDataStore::LoadAsync<Windows::Data::Security::Passkey::RecoveryItemPdr>(
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
  v28 = *(_DWORD *)(v22 + 184);
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
        (unsigned int)&byte_180069B2F,
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
  std::wstring::wstring(a1 + 32, (char *)v55 + 152);
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
0x1800395ec  mov     rax, rsp
0x1800395ef  push    rbp
0x1800395f0  push    rbx
0x1800395f1  push    rsi
0x1800395f2  push    rdi
0x1800395f3  push    r12
0x1800395f5  push    r13
0x1800395f7  push    r14
0x1800395f9  push    r15
0x1800395fb  lea     rbp, [rax-128h]
0x180039602  sub     rsp, 1E8h
0x180039609  movaps  xmmword ptr [rax-58h], xmm6
0x18003960d  mov     rax, cs:__security_cookie
0x180039614  xor     rax, rsp
0x180039617  mov     [rbp+120h+var_60], rax
0x18003961e  mov     rbx, r9
0x180039621  mov     [rbp+120h+var_188], r8
0x180039625  mov     r13, rdx
0x180039628  mov     rsi, rcx
0x18003962b  mov     [rbp+120h+var_160], rcx
0x18003962f  mov     [rbp+120h+var_158], rdx
0x180039633  mov     rdi, [rbp+120h+arg_20]
0x18003963a  mov     rax, [rbp+120h+arg_28]
0x180039641  mov     [rbp+120h+var_198], rax
0x180039645  mov     r15, [rbp+120h+arg_30]
0x18003964c  mov     [rbp+120h+var_150], r15
0x180039650  xor     r14d, r14d
0x180039653  mov     r12, [rax]
0x180039656  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003965a  inc     rax
0x18003965d  cmp     [r12+rax], r14b
0x180039661  jnz     short loc_18003965A
0x180039663  mov     qword ptr [rsp+220h+var_1C8+8], r12
0x180039668  mov     [rsp+220h+var_1B8], rax
0x18003966d  lea     rdx, [rsp+220h+var_1C8+8]
0x180039672  lea     rcx, [rbp+120h+var_108]
0x180039676  call    ?ExtendCorrelationVector@FidoUtils@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_zstring_view@D@wil@@@Z; FidoUtils::ExtendCorrelationVector(wil::basic_zstring_view<char>)
0x18003967b  nop
0x18003967c  mov     eax, cs:dword_180075000
0x180039682  cmp     eax, 4
0x180039685  jbe     short loc_1800396B0
0x180039687  lea     rax, [rbp+120h+var_108]
0x18003968b  cmp     [rbp+120h+var_F0], 0Fh
0x180039690  cmova   rax, [rbp+120h+var_108]
0x180039695  mov     [rsp+220h+var_1E0], rax
0x18003969a  lea     rax, [rsp+220h+var_1E0]
0x18003969f  mov     qword ptr [rsp+220h+var_200], rax
0x1800396a4  lea     rdx, byte_180069BCF
0x1800396ab  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800396b0  lea     rax, [rbp+120h+var_128]
0x1800396b4  mov     [rsp+220h+var_1D0], rax
0x1800396b9  xorps   xmm0, xmm0
0x1800396bc  movups  [rbp+120h+var_128], xmm0
0x1800396c0  mov     qword ptr [rbp+120h+var_118], r14
0x1800396c4  mov     qword ptr [rbp+120h+var_118+8], r14
0x1800396c8  mov     r8d, 7
0x1800396ce  lea     rdx, sourceString; "default"
0x1800396d5  lea     rcx, [rbp+120h+var_128]
0x1800396d9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800396de  nop
0x1800396df  lea     rax, [rbp+120h+var_148]
0x1800396e3  mov     [rbp+120h+var_1A0], rax
0x1800396e7  xorps   xmm0, xmm0
0x1800396ea  movups  [rbp+120h+var_148], xmm0
0x1800396ee  mov     qword ptr [rbp+120h+var_138], r14
0x1800396f2  mov     qword ptr [rbp+120h+var_138+8], r14
0x1800396f6  mov     r8, [rbx+8]
0x1800396fa  mov     rdx, [rbx]
0x1800396fd  lea     rcx, [rbp+120h+var_148]
0x180039701  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180039706  nop
0x180039707  xorps   xmm0, xmm0
0x18003970a  movups  [rbp+120h+var_E0], xmm0
0x18003970e  mov     [rbp+120h+var_D0], r14
0x180039712  mov     [rbp+120h+var_C8], r14
0x180039716  mov     rax, [rdi]
0x180039719  mov     [rsp+220h+var_1E0], rax
0x18003971e  mov     rcx, [rdi+8]
0x180039722  mov     [rbp+120h+var_190], rcx
0x180039726  mov     r8, rcx
0x180039729  mov     rdx, rax
0x18003972c  lea     rcx, [rbp+120h+var_E0]
0x180039730  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180039735  nop
0x180039736  lea     r9, [rbp+120h+var_128]
0x18003973a  lea     r8, [rbp+120h+var_148]
0x18003973e  lea     rdx, [rbp+120h+var_E0]
0x180039742  lea     rcx, [rbp+120h+var_C0]
0x180039746  call    ??0?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z; wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>(std::wstring,std::wstring,std::wstring)
0x18003974b  nop
0x18003974c  mov     rcx, [rbp+120h+var_F8]
0x180039750  lea     rax, [rbp+120h+var_108]
0x180039754  cmp     [rbp+120h+var_F0], 0Fh
0x180039759  cmova   rax, [rbp+120h+var_108]
0x18003975e  mov     qword ptr [rsp+220h+var_1C8+8], rax
0x180039763  mov     [rsp+220h+var_1B8], rcx
0x180039768  lea     rdx, [rsp+220h+var_1C8+8]
0x18003976d  lea     rcx, [rbp+120h+var_E0]
0x180039771  call    ?IncrementCorrelationVector@FidoUtils@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_zstring_view@D@wil@@@Z; FidoUtils::IncrementCorrelationVector(wil::basic_zstring_view<char>)
0x180039776  mov     rdx, rax
0x180039779  lea     rcx, [rbp+120h+var_108]
0x18003977d  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180039782  lea     rcx, [rbp+120h+var_E0]
0x180039786  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18003978b  mov     qword ptr [rsp+220h+var_1B0], r14
0x180039790  lea     r9, [rbp+120h+var_108]
0x180039794  cmp     [rbp+120h+var_F0], 0Fh
0x180039799  cmova   r9, [rbp+120h+var_108]
0x18003979e  mov     dword ptr [rsp+220h+var_1F8], 22h ; '"'
0x1800397a6  lea     rax, [rsp+220h+var_1B0]
0x1800397ab  mov     qword ptr [rsp+220h+var_200], rax; int
0x1800397b0  lea     r8, [rbp+120h+var_C0]
0x1800397b4  lea     rdx, [rsp+220h+var_1A8]
0x1800397b9  mov     rcx, [r13+0]
0x1800397bd  call    ??$LoadAsync@URecoveryItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@QEAA?AU?$task@V?$shared_ptr@V?$ProfileDataItem@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@1@AEBV?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@1@PEBDVcancellation_token@Concurrency@@W4ProfileDataStoreLoadOptions@1@PEBG@Z; wil::ProfileDataStore::LoadAsync<Windows::Data::Security::Passkey::RecoveryItemPdr>(wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr> const &,char const *,Concurrency::cancellation_token,wil::ProfileDataStoreLoadOptions,ushort const *)
0x1800397c2  nop
0x1800397c3  lea     rdx, [rbp+120h+var_E0]
0x1800397c7  mov     rcx, rax
0x1800397ca  call    ?get@?$task_base@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@coro@details@wil@@QEHAA@XZ; wil::details::coro::task_base<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::get(void)
0x1800397cf  nop
0x1800397d0  mov     rcx, [rsp+220h+var_1A8]
0x1800397d5  mov     [rsp+220h+var_1A8], r14
0x1800397da  test    rcx, rcx
0x1800397dd  jz      short loc_180039801
0x1800397df  mov     eax, 2
0x1800397e4  xchg    rax, [rcx+8]
0x1800397e8  test    rax, rax
0x1800397eb  jz      short loc_180039801
0x1800397ed  lea     rax, [rcx+30h]
0x1800397f1  or      qword ptr [rax+8], 1
0x1800397f6  mov     rcx, rax
0x1800397f9  mov     rax, [rax]
0x1800397fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039801  xorps   xmm0, xmm0
0x180039804  movdqa  [rsp+220h+var_1C8+8], xmm0
0x18003980a  mov     rdi, qword ptr [rbp+120h+var_E0+8]
0x18003980e  test    rdi, rdi
0x180039811  jz      short loc_180039817
0x180039813  lock inc dword ptr [rdi+8]
0x180039817  movaps  xmm6, [rbp+120h+var_E0]
0x18003981b  movdqa  [rsp+220h+var_1C8+8], xmm6
0x180039821  lea     rax, [rsp+220h+var_1C8+8]
0x180039826  mov     [rsp+220h+var_1D0], rax
0x18003982b  mov     rcx, [r15+38h]
0x18003982f  test    rcx, rcx
0x180039832  jnz     short loc_18003983B
0x180039834  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18003983a  int     3; Trap to Debugger
0x18003983b  mov     rax, [rcx]
0x18003983e  lea     r8, [rsp+220h+var_1C8+8]
0x180039843  lea     rdx, [rbp+120h+var_180]
0x180039847  mov     rax, [rax+10h]
0x18003984b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039850  nop
0x180039851  mov     rbx, [rsp+220h+var_1B8]
0x180039856  test    rbx, rbx
0x180039859  jz      short loc_180039893
0x18003985b  or      eax, 0FFFFFFFFh
0x18003985e  lock xadd [rbx+8], eax
0x180039863  cmp     eax, 1
0x180039866  jnz     short loc_180039893
0x180039868  mov     rax, [rbx]
0x18003986b  mov     rcx, rbx
0x18003986e  mov     rax, [rax]
0x180039871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039876  or      eax, 0FFFFFFFFh
0x180039879  lock xadd [rbx+0Ch], eax
0x18003987e  cmp     eax, 1
0x180039881  jnz     short loc_180039893
0x180039883  mov     rax, [rbx]
0x180039886  mov     rcx, rbx
0x180039889  mov     rax, [rax+8]
0x18003988d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039892  nop
0x180039893  movq    rax, xmm6
0x180039898  mov     [rsp+220h+var_1D0], rax
0x18003989d  mov     r14d, [rax+0B8h]
0x1800398a4  test    r14d, r14d
0x1800398a7  jns     loc_1800399B2
0x1800398ad  mov     eax, cs:dword_180075000
0x1800398b3  cmp     eax, 4
0x1800398b6  jbe     short loc_180039904
0x1800398b8  lea     rax, aProfiledatasto; "ProfileDataStore::LoadAsync"
0x1800398bf  mov     [rsp+220h+var_1A8], rax
0x1800398c4  lea     rax, [rbp+120h+var_108]
0x1800398c8  cmp     [rbp+120h+var_F0], 0Fh
0x1800398cd  cmova   rax, [rbp+120h+var_108]
0x1800398d2  mov     [rbp+120h+var_1A0], rax
0x1800398d6  mov     [rsp+220h+var_1B0], r14d
0x1800398db  lea     rax, [rsp+220h+var_1A8]
0x1800398e0  mov     [rsp+30h], rax
0x1800398e5  lea     rax, [rbp+120h+var_1A0]
0x1800398e9  mov     [rsp+220h+var_1F8], rax
0x1800398ee  lea     rax, [rsp+220h+var_1B0]
0x1800398f3  mov     qword ptr [rsp+220h+var_200], rax
0x1800398f8  lea     rdx, byte_180069B2F
0x1800398ff  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180039904  xorps   xmm0, xmm0
0x180039907  movups  [rbp+120h+var_128], xmm0
0x18003990b  xorps   xmm1, xmm1
0x18003990e  movdqu  [rbp+120h+var_118], xmm1
0x180039913  mov     r8, [rbp+120h+var_198]
0x180039917  mov     r8, [r8+8]
0x18003991b  mov     rdx, r12
0x18003991e  lea     rcx, [rbp+120h+var_128]
0x180039922  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180039927  nop
0x180039928  lea     rbx, [rbp+120h+var_128]
0x18003992c  cmp     qword ptr [rbp+120h+var_118+8], 0Fh
0x180039931  cmova   rbx, qword ptr [rbp+120h+var_128]
0x180039936  xorps   xmm0, xmm0
0x180039939  movups  [rbp+120h+var_148], xmm0
0x18003993d  xorps   xmm1, xmm1
0x180039940  movdqu  [rbp+120h+var_138], xmm1
0x180039945  mov     r8, [rbp+120h+var_190]
0x180039949  mov     rdx, [rsp+220h+var_1E0]
0x18003994e  lea     rcx, [rbp+120h+var_148]
0x180039952  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180039957  lea     r8, [rbp+120h+var_148]
0x18003995b  cmp     qword ptr [rbp+120h+var_138+8], 7
0x180039960  cmova   r8, qword ptr [rbp+120h+var_148]
0x180039965  mov     [rsp+220h+var_200], r14d; int
0x18003996a  mov     r9, rbx
0x18003996d  mov     rdx, [rbp+120h+var_188]
0x180039971  mov     edx, [rdx]
0x180039973  xor     ecx, ecx
0x180039975  call    cs:__imp_WebAuthNWriteEventCloudStoreOperationFailure
0x18003997b  mov     rcx, [rbp+128h]; this
0x180039982  test    eax, eax
0x180039984  jns     short loc_18003999A
0x180039986  mov     r9d, eax; char *
0x180039989  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\ngc\\utils\\pdr"...
0x180039990  mov     edx, 5Fh ; '_'; void *
0x180039995  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003999a  lea     rcx, [rbp+120h+var_148]
0x18003999e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800399a3  nop
0x1800399a4  lea     rcx, [rbp+120h+var_128]
0x1800399a8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800399ad  jmp     loc_180039A59
0x1800399b2  xorps   xmm0, xmm0
0x1800399b5  movups  [rbp+120h+var_148], xmm0
0x1800399b9  xorps   xmm1, xmm1
0x1800399bc  movdqu  [rbp+120h+var_138], xmm1
0x1800399c1  mov     r8, [rbp+120h+var_198]
0x1800399c5  mov     r8, [r8+8]
0x1800399c9  mov     rdx, r12
0x1800399cc  lea     rcx, [rbp+120h+var_148]
0x1800399d0  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800399d5  nop
0x1800399d6  lea     rbx, [rbp+120h+var_148]
0x1800399da  cmp     qword ptr [rbp+120h+var_138+8], 0Fh
0x1800399df  cmova   rbx, qword ptr [rbp+120h+var_148]
0x1800399e4  xorps   xmm0, xmm0
0x1800399e7  movups  [rbp+120h+var_128], xmm0
0x1800399eb  xorps   xmm1, xmm1
0x1800399ee  movdqu  [rbp+120h+var_118], xmm1
0x1800399f3  mov     r8, [rbp+120h+var_190]
0x1800399f7  mov     rdx, [rsp+220h+var_1E0]
0x1800399fc  lea     rcx, [rbp+120h+var_128]
0x180039a00  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180039a05  lea     r8, [rbp+120h+var_128]
0x180039a09  cmp     qword ptr [rbp+120h+var_118+8], 7
0x180039a0e  cmova   r8, qword ptr [rbp+120h+var_128]
0x180039a13  mov     r9, rbx
0x180039a16  mov     rdx, [rbp+120h+var_188]
0x180039a1a  mov     edx, [rdx]
0x180039a1c  xor     ecx, ecx
0x180039a1e  call    cs:__imp_WebAuthNWriteEventCloudStoreOperationSuccess
0x180039a24  mov     rcx, [rbp+128h]; this
0x180039a2b  test    eax, eax
0x180039a2d  jns     short loc_180039A43
0x180039a2f  mov     r9d, eax; char *
0x180039a32  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\ngc\\utils\\pdr"...
0x180039a39  mov     edx, 67h ; 'g'; void *
0x180039a3e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180039a43  lea     rcx, [rbp+120h+var_128]
0x180039a47  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180039a4c  nop
0x180039a4d  lea     rcx, [rbp+120h+var_148]
0x180039a51  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180039a56  xor     r14d, r14d
0x180039a59  mov     [rsi], r14d
0x180039a5c  xor     eax, eax
0x180039a5e  mov     [rsi+4], eax
0x180039a61  mov     rdx, [rbp+120h+var_170]
0x180039a65  mov     [rbp+120h+var_170], rax
0x180039a69  mov     rcx, [rbp+120h+var_178]
0x180039a6d  mov     [rbp+120h+var_178], rax
0x180039a71  mov     rax, [rbp+120h+var_180]
0x180039a75  mov     [rbp+120h+var_180], 0
0x180039a7d  mov     [rsi+8], rax
0x180039a81  mov     [rsi+10h], rcx
0x180039a85  mov     [rsi+18h], rdx
0x180039a89  lea     rcx, [rsi+20h]
0x180039a8d  mov     rdx, [rsp+220h+var_1D0]
0x180039a92  add     rdx, 98h
0x180039a99  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180039a9e  nop
0x180039a9f  lea     rcx, [rbp+120h+var_180]
  ... truncated ...
```
