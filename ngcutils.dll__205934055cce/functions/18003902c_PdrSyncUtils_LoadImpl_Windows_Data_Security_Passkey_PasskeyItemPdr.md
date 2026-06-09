# PdrSyncUtils::LoadImpl_Windows::Data::Security::Passkey::PasskeyItemPdr_

- ea: `0x18003902c`
- end: `0x1800395e4`
- name: `PdrSyncUtils::LoadImpl_Windows::Data::Security::Passkey::PasskeyItemPdr_`
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
- `0x180038d50`
- `0x18003902c`
- `0x180040d10`
- `0x180043f84`
- `0x18004f6ac`
- `0x180054c40`
- `0x180054ecc`
- `0x180061010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180039274`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180039274`
- `webauthn!WebAuthNWriteEventCloudStoreOperationFailure` at `0x1800393b5`
- `webauthn!WebAuthNWriteEventCloudStoreOperationFailure` at `0x1800393b5`
- `webauthn!WebAuthNWriteEventCloudStoreOperationSuccess` at `0x18003945e`
- `webauthn!WebAuthNWriteEventCloudStoreOperationSuccess` at `0x18003945e`

## string_xrefs

- `0x1800393c9`: `onecore\ds\security\ngc\utils\pdr\lib\pdrsyncstore.cpp`
- `0x180039472`: `onecore\ds\security\ngc\utils\pdr\lib\pdrsyncstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall PdrSyncUtils::LoadImpl_Windows::Data::Security::Passkey::PasskeyItemPdr_(
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
      (unsigned int)&byte_180069C6F,
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
  v19 = wil::ProfileDataStore::LoadAsync<Windows::Data::Security::Passkey::PasskeyItemPdr>(
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
        (unsigned int)byte_180069C0B,
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
0x18003902c  mov     rax, rsp
0x18003902f  push    rbp
0x180039030  push    rbx
0x180039031  push    rsi
0x180039032  push    rdi
0x180039033  push    r12
0x180039035  push    r13
0x180039037  push    r14
0x180039039  push    r15
0x18003903b  lea     rbp, [rax-128h]
0x180039042  sub     rsp, 1E8h
0x180039049  movaps  xmmword ptr [rax-58h], xmm6
0x18003904d  mov     rax, cs:__security_cookie
0x180039054  xor     rax, rsp
0x180039057  mov     [rbp+120h+var_60], rax
0x18003905e  mov     rbx, r9
0x180039061  mov     [rbp+120h+var_188], r8
0x180039065  mov     r13, rdx
0x180039068  mov     rsi, rcx
0x18003906b  mov     [rbp+120h+var_160], rcx
0x18003906f  mov     [rbp+120h+var_158], rdx
0x180039073  mov     rdi, [rbp+120h+arg_20]
0x18003907a  mov     rax, [rbp+120h+arg_28]
0x180039081  mov     [rbp+120h+var_198], rax
0x180039085  mov     r15, [rbp+120h+arg_30]
0x18003908c  mov     [rbp+120h+var_150], r15
0x180039090  xor     r14d, r14d
0x180039093  mov     r12, [rax]
0x180039096  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003909a  inc     rax
0x18003909d  cmp     [r12+rax], r14b
0x1800390a1  jnz     short loc_18003909A
0x1800390a3  mov     qword ptr [rsp+220h+var_1C8+8], r12
0x1800390a8  mov     [rsp+220h+var_1B8], rax
0x1800390ad  lea     rdx, [rsp+220h+var_1C8+8]
0x1800390b2  lea     rcx, [rbp+120h+var_108]
0x1800390b6  call    ?ExtendCorrelationVector@FidoUtils@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_zstring_view@D@wil@@@Z; FidoUtils::ExtendCorrelationVector(wil::basic_zstring_view<char>)
0x1800390bb  nop
0x1800390bc  mov     eax, cs:dword_180075000
0x1800390c2  cmp     eax, 4
0x1800390c5  jbe     short loc_1800390F0
0x1800390c7  lea     rax, [rbp+120h+var_108]
0x1800390cb  cmp     [rbp+120h+var_F0], 0Fh
0x1800390d0  cmova   rax, [rbp+120h+var_108]
0x1800390d5  mov     [rsp+220h+var_1E0], rax
0x1800390da  lea     rax, [rsp+220h+var_1E0]
0x1800390df  mov     qword ptr [rsp+220h+var_200], rax
0x1800390e4  lea     rdx, byte_180069C6F
0x1800390eb  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800390f0  lea     rax, [rbp+120h+var_128]
0x1800390f4  mov     [rsp+220h+var_1D0], rax
0x1800390f9  xorps   xmm0, xmm0
0x1800390fc  movups  [rbp+120h+var_128], xmm0
0x180039100  mov     qword ptr [rbp+120h+var_118], r14
0x180039104  mov     qword ptr [rbp+120h+var_118+8], r14
0x180039108  mov     r8d, 7
0x18003910e  lea     rdx, sourceString; "default"
0x180039115  lea     rcx, [rbp+120h+var_128]
0x180039119  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003911e  nop
0x18003911f  lea     rax, [rbp+120h+var_148]
0x180039123  mov     [rbp+120h+var_1A0], rax
0x180039127  xorps   xmm0, xmm0
0x18003912a  movups  [rbp+120h+var_148], xmm0
0x18003912e  mov     qword ptr [rbp+120h+var_138], r14
0x180039132  mov     qword ptr [rbp+120h+var_138+8], r14
0x180039136  mov     r8, [rbx+8]
0x18003913a  mov     rdx, [rbx]
0x18003913d  lea     rcx, [rbp+120h+var_148]
0x180039141  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180039146  nop
0x180039147  xorps   xmm0, xmm0
0x18003914a  movups  [rbp+120h+var_E0], xmm0
0x18003914e  mov     [rbp+120h+var_D0], r14
0x180039152  mov     [rbp+120h+var_C8], r14
0x180039156  mov     rax, [rdi]
0x180039159  mov     [rsp+220h+var_1E0], rax
0x18003915e  mov     rcx, [rdi+8]
0x180039162  mov     [rbp+120h+var_190], rcx
0x180039166  mov     r8, rcx
0x180039169  mov     rdx, rax
0x18003916c  lea     rcx, [rbp+120h+var_E0]
0x180039170  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180039175  nop
0x180039176  lea     r9, [rbp+120h+var_128]
0x18003917a  lea     r8, [rbp+120h+var_148]
0x18003917e  lea     rdx, [rbp+120h+var_E0]
0x180039182  lea     rcx, [rbp+120h+var_C0]
0x180039186  call    ??0?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z; wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>(std::wstring,std::wstring,std::wstring)
0x18003918b  nop
0x18003918c  mov     rcx, [rbp+120h+var_F8]
0x180039190  lea     rax, [rbp+120h+var_108]
0x180039194  cmp     [rbp+120h+var_F0], 0Fh
0x180039199  cmova   rax, [rbp+120h+var_108]
0x18003919e  mov     qword ptr [rsp+220h+var_1C8+8], rax
0x1800391a3  mov     [rsp+220h+var_1B8], rcx
0x1800391a8  lea     rdx, [rsp+220h+var_1C8+8]
0x1800391ad  lea     rcx, [rbp+120h+var_E0]
0x1800391b1  call    ?IncrementCorrelationVector@FidoUtils@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_zstring_view@D@wil@@@Z; FidoUtils::IncrementCorrelationVector(wil::basic_zstring_view<char>)
0x1800391b6  mov     rdx, rax
0x1800391b9  lea     rcx, [rbp+120h+var_108]
0x1800391bd  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800391c2  lea     rcx, [rbp+120h+var_E0]
0x1800391c6  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800391cb  mov     qword ptr [rsp+220h+var_1B0], r14
0x1800391d0  lea     r9, [rbp+120h+var_108]
0x1800391d4  cmp     [rbp+120h+var_F0], 0Fh
0x1800391d9  cmova   r9, [rbp+120h+var_108]
0x1800391de  mov     dword ptr [rsp+220h+var_1F8], 22h ; '"'
0x1800391e6  lea     rax, [rsp+220h+var_1B0]
0x1800391eb  mov     qword ptr [rsp+220h+var_200], rax; int
0x1800391f0  lea     r8, [rbp+120h+var_C0]
0x1800391f4  lea     rdx, [rsp+220h+var_1A8]
0x1800391f9  mov     rcx, [r13+0]
0x1800391fd  call    ??$LoadAsync@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@QEAA?AU?$task@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@1@AEBV?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@1@PEBDVcancellation_token@Concurrency@@W4ProfileDataStoreLoadOptions@1@PEBG@Z; wil::ProfileDataStore::LoadAsync<Windows::Data::Security::Passkey::PasskeyItemPdr>(wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> const &,char const *,Concurrency::cancellation_token,wil::ProfileDataStoreLoadOptions,ushort const *)
0x180039202  nop
0x180039203  lea     rdx, [rbp+120h+var_E0]
0x180039207  mov     rcx, rax
0x18003920a  call    ?get@?$task_base@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@coro@details@wil@@QEHAA@XZ; wil::details::coro::task_base<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::get(void)
0x18003920f  nop
0x180039210  mov     rcx, [rsp+220h+var_1A8]
0x180039215  mov     [rsp+220h+var_1A8], r14
0x18003921a  test    rcx, rcx
0x18003921d  jz      short loc_180039241
0x18003921f  mov     eax, 2
0x180039224  xchg    rax, [rcx+8]
0x180039228  test    rax, rax
0x18003922b  jz      short loc_180039241
0x18003922d  lea     rax, [rcx+30h]
0x180039231  or      qword ptr [rax+8], 1
0x180039236  mov     rcx, rax
0x180039239  mov     rax, [rax]
0x18003923c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039241  xorps   xmm0, xmm0
0x180039244  movdqa  [rsp+220h+var_1C8+8], xmm0
0x18003924a  mov     rdi, qword ptr [rbp+120h+var_E0+8]
0x18003924e  test    rdi, rdi
0x180039251  jz      short loc_180039257
0x180039253  lock inc dword ptr [rdi+8]
0x180039257  movaps  xmm6, [rbp+120h+var_E0]
0x18003925b  movdqa  [rsp+220h+var_1C8+8], xmm6
0x180039261  lea     rax, [rsp+220h+var_1C8+8]
0x180039266  mov     [rsp+220h+var_1D0], rax
0x18003926b  mov     rcx, [r15+38h]
0x18003926f  test    rcx, rcx
0x180039272  jnz     short loc_18003927B
0x180039274  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18003927a  int     3; Trap to Debugger
0x18003927b  mov     rax, [rcx]
0x18003927e  lea     r8, [rsp+220h+var_1C8+8]
0x180039283  lea     rdx, [rbp+120h+var_180]
0x180039287  mov     rax, [rax+10h]
0x18003928b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039290  nop
0x180039291  mov     rbx, [rsp+220h+var_1B8]
0x180039296  test    rbx, rbx
0x180039299  jz      short loc_1800392D3
0x18003929b  or      eax, 0FFFFFFFFh
0x18003929e  lock xadd [rbx+8], eax
0x1800392a3  cmp     eax, 1
0x1800392a6  jnz     short loc_1800392D3
0x1800392a8  mov     rax, [rbx]
0x1800392ab  mov     rcx, rbx
0x1800392ae  mov     rax, [rax]
0x1800392b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800392b6  or      eax, 0FFFFFFFFh
0x1800392b9  lock xadd [rbx+0Ch], eax
0x1800392be  cmp     eax, 1
0x1800392c1  jnz     short loc_1800392D3
0x1800392c3  mov     rax, [rbx]
0x1800392c6  mov     rcx, rbx
0x1800392c9  mov     rax, [rax+8]
0x1800392cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800392d2  nop
0x1800392d3  movq    rax, xmm6
0x1800392d8  mov     [rsp+220h+var_1D0], rax
0x1800392dd  mov     r14d, [rax+0D8h]
0x1800392e4  test    r14d, r14d
0x1800392e7  jns     loc_1800393F2
0x1800392ed  mov     eax, cs:dword_180075000
0x1800392f3  cmp     eax, 4
0x1800392f6  jbe     short loc_180039344
0x1800392f8  lea     rax, aProfiledatasto; "ProfileDataStore::LoadAsync"
0x1800392ff  mov     [rsp+220h+var_1A8], rax
0x180039304  lea     rax, [rbp+120h+var_108]
0x180039308  cmp     [rbp+120h+var_F0], 0Fh
0x18003930d  cmova   rax, [rbp+120h+var_108]
0x180039312  mov     [rbp+120h+var_1A0], rax
0x180039316  mov     [rsp+220h+var_1B0], r14d
0x18003931b  lea     rax, [rsp+220h+var_1A8]
0x180039320  mov     [rsp+30h], rax
0x180039325  lea     rax, [rbp+120h+var_1A0]
0x180039329  mov     [rsp+220h+var_1F8], rax
0x18003932e  lea     rax, [rsp+220h+var_1B0]
0x180039333  mov     qword ptr [rsp+220h+var_200], rax
0x180039338  lea     rdx, byte_180069C0B
0x18003933f  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180039344  xorps   xmm0, xmm0
0x180039347  movups  [rbp+120h+var_128], xmm0
0x18003934b  xorps   xmm1, xmm1
0x18003934e  movdqu  [rbp+120h+var_118], xmm1
0x180039353  mov     r8, [rbp+120h+var_198]
0x180039357  mov     r8, [r8+8]
0x18003935b  mov     rdx, r12
0x18003935e  lea     rcx, [rbp+120h+var_128]
0x180039362  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180039367  nop
0x180039368  lea     rbx, [rbp+120h+var_128]
0x18003936c  cmp     qword ptr [rbp+120h+var_118+8], 0Fh
0x180039371  cmova   rbx, qword ptr [rbp+120h+var_128]
0x180039376  xorps   xmm0, xmm0
0x180039379  movups  [rbp+120h+var_148], xmm0
0x18003937d  xorps   xmm1, xmm1
0x180039380  movdqu  [rbp+120h+var_138], xmm1
0x180039385  mov     r8, [rbp+120h+var_190]
0x180039389  mov     rdx, [rsp+220h+var_1E0]
0x18003938e  lea     rcx, [rbp+120h+var_148]
0x180039392  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180039397  lea     r8, [rbp+120h+var_148]
0x18003939b  cmp     qword ptr [rbp+120h+var_138+8], 7
0x1800393a0  cmova   r8, qword ptr [rbp+120h+var_148]
0x1800393a5  mov     [rsp+220h+var_200], r14d; int
0x1800393aa  mov     r9, rbx
0x1800393ad  mov     rdx, [rbp+120h+var_188]
0x1800393b1  mov     edx, [rdx]
0x1800393b3  xor     ecx, ecx
0x1800393b5  call    cs:__imp_WebAuthNWriteEventCloudStoreOperationFailure
0x1800393bb  mov     rcx, [rbp+128h]; this
0x1800393c2  test    eax, eax
0x1800393c4  jns     short loc_1800393DA
0x1800393c6  mov     r9d, eax; char *
0x1800393c9  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\ngc\\utils\\pdr"...
0x1800393d0  mov     edx, 5Fh ; '_'; void *
0x1800393d5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800393da  lea     rcx, [rbp+120h+var_148]
0x1800393de  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800393e3  nop
0x1800393e4  lea     rcx, [rbp+120h+var_128]
0x1800393e8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800393ed  jmp     loc_180039499
0x1800393f2  xorps   xmm0, xmm0
0x1800393f5  movups  [rbp+120h+var_148], xmm0
0x1800393f9  xorps   xmm1, xmm1
0x1800393fc  movdqu  [rbp+120h+var_138], xmm1
0x180039401  mov     r8, [rbp+120h+var_198]
0x180039405  mov     r8, [r8+8]
0x180039409  mov     rdx, r12
0x18003940c  lea     rcx, [rbp+120h+var_148]
0x180039410  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180039415  nop
0x180039416  lea     rbx, [rbp+120h+var_148]
0x18003941a  cmp     qword ptr [rbp+120h+var_138+8], 0Fh
0x18003941f  cmova   rbx, qword ptr [rbp+120h+var_148]
0x180039424  xorps   xmm0, xmm0
0x180039427  movups  [rbp+120h+var_128], xmm0
0x18003942b  xorps   xmm1, xmm1
0x18003942e  movdqu  [rbp+120h+var_118], xmm1
0x180039433  mov     r8, [rbp+120h+var_190]
0x180039437  mov     rdx, [rsp+220h+var_1E0]
0x18003943c  lea     rcx, [rbp+120h+var_128]
0x180039440  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180039445  lea     r8, [rbp+120h+var_128]
0x180039449  cmp     qword ptr [rbp+120h+var_118+8], 7
0x18003944e  cmova   r8, qword ptr [rbp+120h+var_128]
0x180039453  mov     r9, rbx
0x180039456  mov     rdx, [rbp+120h+var_188]
0x18003945a  mov     edx, [rdx]
0x18003945c  xor     ecx, ecx
0x18003945e  call    cs:__imp_WebAuthNWriteEventCloudStoreOperationSuccess
0x180039464  mov     rcx, [rbp+128h]; this
0x18003946b  test    eax, eax
0x18003946d  jns     short loc_180039483
0x18003946f  mov     r9d, eax; char *
0x180039472  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\ngc\\utils\\pdr"...
0x180039479  mov     edx, 67h ; 'g'; void *
0x18003947e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180039483  lea     rcx, [rbp+120h+var_128]
0x180039487  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003948c  nop
0x18003948d  lea     rcx, [rbp+120h+var_148]
0x180039491  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180039496  xor     r14d, r14d
0x180039499  mov     [rsi], r14d
0x18003949c  xor     eax, eax
0x18003949e  mov     [rsi+4], eax
0x1800394a1  mov     rdx, [rbp+120h+var_170]
0x1800394a5  mov     [rbp+120h+var_170], rax
0x1800394a9  mov     rcx, [rbp+120h+var_178]
0x1800394ad  mov     [rbp+120h+var_178], rax
0x1800394b1  mov     rax, [rbp+120h+var_180]
0x1800394b5  mov     [rbp+120h+var_180], 0
0x1800394bd  mov     [rsi+8], rax
0x1800394c1  mov     [rsi+10h], rcx
0x1800394c5  mov     [rsi+18h], rdx
0x1800394c9  lea     rcx, [rsi+20h]
0x1800394cd  mov     rdx, [rsp+220h+var_1D0]
0x1800394d2  add     rdx, 0B8h
0x1800394d9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800394de  nop
0x1800394df  lea     rcx, [rbp+120h+var_180]
  ... truncated ...
```
