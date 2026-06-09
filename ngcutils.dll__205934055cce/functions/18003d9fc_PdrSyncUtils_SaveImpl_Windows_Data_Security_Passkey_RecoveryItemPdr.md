# PdrSyncUtils::SaveImpl_Windows::Data::Security::Passkey::RecoveryItemPdr_

- ea: `0x18003d9fc`
- end: `0x18003e36a`
- name: `PdrSyncUtils::SaveImpl_Windows::Data::Security::Passkey::RecoveryItemPdr_`
- size: `2414`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004c0a0`

## callees

- `0x1800012e4`
- `0x180001374`
- `0x180003080`
- `0x18000c95c`
- `0x18000ce74`
- `0x18001354c`
- `0x18001361c`
- `0x1800137a0`
- `0x180013834`
- `0x18001addc`
- `0x180038e44`
- `0x18003cd44`
- `0x18003d9fc`
- `0x180040d10`
- `0x18004f6ac`
- `0x18004f8fc`
- `0x180054c40`
- `0x180054ecc`
- `0x180061010`

## import_xrefs

- `webauthn!WebAuthNWriteEventCloudStoreOperationFailure` at `0x18003de94`
- `webauthn!WebAuthNWriteEventCloudStoreOperationFailure` at `0x18003de94`
- `webauthn!WebAuthNWriteEventCloudStoreOperationSuccess` at `0x18003deed`
- `webauthn!WebAuthNWriteEventCloudStoreOperationSuccess` at `0x18003deed`

## string_xrefs

- `0x18003df06`: `onecore\ds\security\ngc\utils\pdr\lib\pdrsyncstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
char *__fastcall PdrSyncUtils::SaveImpl_Windows::Data::Security::Passkey::RecoveryItemPdr_(
        char *a1,
        __int64 a2,
        unsigned int *a3,
        _QWORD *a4,
        __int64 *a5,
        _QWORD *a6,
        __int64 *a7)
{
  __int64 v9; // r15
  __int64 v10; // rax
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int *v14; // rax
  int *v15; // rax
  __int64 v16; // rax
  __int64 v17; // r8
  int *v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // r8
  int *v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // r8
  __int128 *v34; // rcx
  int *v35; // rsi
  __int64 v36; // rbx
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rbx
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // rcx
  __int64 v45; // rdx
  __int64 v46; // r8
  int v47; // r8d
  int v48; // r9d
  int v49; // ebx
  int *v50; // rax
  __int128 *v51; // r9
  int v52; // eax
  wil::details::in1diag3 *v53; // rcx
  __int64 v54; // rdx
  __int128 *v55; // r9
  __int64 v56; // rbx
  int *v57; // rax
  __int64 v58; // rax
  int *v59; // r9
  __int64 v60; // rax
  _QWORD *v61; // rax
  volatile signed __int32 *v62; // rbx
  _QWORD *v63; // rcx
  int *v64; // rax
  __int64 v65; // rax
  int *v66; // r13
  __int64 v67; // rbx
  __int64 v68; // rax
  __int64 v69; // rax
  __int64 v70; // rbx
  __int64 v71; // rdx
  __int64 v72; // r8
  __int64 v73; // rdx
  __int64 v74; // r8
  _QWORD *v75; // rax
  __int64 v76; // rdx
  __int64 v77; // r8
  __int64 v78; // rdx
  __int64 v79; // r8
  __int64 v80; // rdx
  int v81; // ecx
  __int64 v82; // r8
  int v83; // r9d
  int *v84; // rax
  __int64 v85; // rdx
  __int64 v86; // r8
  __int64 v87; // rdx
  __int64 v88; // r8
  __int64 v89; // rdx
  __int64 v90; // r8
  int v91; // eax
  __int64 v92; // rdx
  __int64 v93; // r8
  volatile signed __int32 *v94; // rbx
  volatile signed __int32 *v95; // rbx
  int v97; // [rsp+20h] [rbp-E0h]
  __int128 v98; // [rsp+50h] [rbp-B0h] BYREF
  const char *v99; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v100; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v101; // [rsp+70h] [rbp-90h] BYREF
  unsigned int *v102; // [rsp+78h] [rbp-88h] BYREF
  int *v103; // [rsp+80h] [rbp-80h] BYREF
  __int64 v104[4]; // [rsp+88h] [rbp-78h] BYREF
  int v105[4]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v106; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v107; // [rsp+C0h] [rbp-40h]
  __int128 v108; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v109; // [rsp+D8h] [rbp-28h]
  __int64 v110; // [rsp+E8h] [rbp-18h]
  int v111; // [rsp+F0h] [rbp-10h]
  int v112; // [rsp+F4h] [rbp-Ch]
  _OWORD v113[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v114; // [rsp+118h] [rbp+18h]
  int **v115; // [rsp+120h] [rbp+20h] BYREF
  volatile signed __int32 *v116; // [rsp+128h] [rbp+28h]
  _BYTE v117[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v118[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v119[32]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v120[16]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v121[48]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v122[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v123[32]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v124[32]; // [rsp+220h] [rbp+120h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v101 = a4;
  v102 = a3;
  v99 = a1;
  v104[2] = a2;
  v104[3] = (__int64)a7;
  v9 = *a5;
  v10 = -1;
  do
    ++v10;
  while ( *(_BYTE *)(v9 + v10) );
  *(_QWORD *)&v98 = *a5;
  *((_QWORD *)&v98 + 1) = v10;
  FidoUtils::ExtendCorrelationVector(v105, &v98);
  if ( (unsigned int)dword_180075000 > 4 )
  {
    v14 = v105;
    if ( v107 > 0xF )
      v14 = *(int **)v105;
    v103 = v14;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v11,
      (unsigned int)&byte_180069927,
      v12,
      v13,
      (__int64)&v103);
  }
  v110 = 0;
  v113[0] = 0;
  v113[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v113[0]) = 0;
  v15 = v105;
  if ( v107 > 0xF )
    v15 = *(int **)v105;
  *(_QWORD *)&v98 = v15;
  *((_QWORD *)&v98 + 1) = v106;
  v16 = FidoUtils::IncrementCorrelationVector(&v108, &v98);
  std::string::operator=(v105, v16);
  std::string::~string(&v108);
  v17 = a6[1];
  if ( v17 )
  {
    v108 = 0;
    v109 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v108, *a6, v17);
    v99 = *(const char **)a2;
    v115 = (int **)&v100;
    v100 = 0;
    v18 = v105;
    if ( v107 > 0xF )
      v18 = *(int **)v105;
    v104[0] = (__int64)v18;
    v19 = *a7;
    std::wstring::wstring(v117, *a7 + 56);
    std::wstring::wstring(v118, v19 + 88);
    std::wstring::wstring(v119, v19 + 120);
    v98 = 0;
    v20 = a7[1];
    if ( v20 )
      _InterlockedIncrement((volatile signed __int32 *)(v20 + 8));
    v98 = *(_OWORD *)a7;
    v21 = wil::ProfileDataStore::SaveAsync<Windows::Data::Security::Passkey::RecoveryItemPdr>(
            (_DWORD)v99,
            (unsigned int)&v103,
            (unsigned int)&v98,
            (unsigned int)v117,
            v104[0],
            (__int64)&v100);
    v22 = wil::details::coro::task_base<wil::ProfileDataStoreSaveResult>::get(v21, v120);
    v110 = *(_QWORD *)v22;
    v111 = *(_DWORD *)(v22 + 8);
    v112 = *(_DWORD *)(v22 + 12);
    std::wstring::operator=(v113, v22 + 16);
    v114 = *(_QWORD *)(v22 + 48);
    std::wstring::~wstring(v121, v23, v24);
    v27 = v103;
    v103 = 0;
    if ( v27 && _InterlockedExchange64((volatile __int64 *)v27 + 1, 2) )
    {
      *((_QWORD *)v27 + 13) |= 1uLL;
      (*((void (__fastcall **)(int *))v27 + 12))(v27 + 24);
    }
    std::wstring::~wstring(v119, v25, v26);
    std::wstring::~wstring(v118, v28, v29);
    std::wstring::~wstring(v117, v30, v31);
    v34 = &v108;
  }
  else
  {
    v99 = *(const char **)a2;
    v115 = &v103;
    v103 = 0;
    v35 = v105;
    if ( v107 > 0xF )
      v35 = *(int **)v105;
    v36 = *a7;
    std::wstring::wstring(v117, *a7 + 56);
    std::wstring::wstring(v118, v36 + 88);
    std::wstring::wstring(v119, v36 + 120);
    v98 = 0;
    v37 = a7[1];
    if ( v37 )
      _InterlockedIncrement((volatile signed __int32 *)(v37 + 8));
    v98 = *(_OWORD *)a7;
    v38 = wil::ProfileDataStore::SaveAsync<Windows::Data::Security::Passkey::RecoveryItemPdr>(
            (_DWORD)v99,
            (unsigned int)&v100,
            (unsigned int)&v98,
            (unsigned int)v117,
            (__int64)v35,
            (__int64)&v103);
    v39 = wil::details::coro::task_base<wil::ProfileDataStoreSaveResult>::get(v38, v120);
    v110 = *(_QWORD *)v39;
    v111 = *(_DWORD *)(v39 + 8);
    v112 = *(_DWORD *)(v39 + 12);
    std::wstring::operator=(v113, v39 + 16);
    v114 = *(_QWORD *)(v39 + 48);
    std::wstring::~wstring(v121, v40, v41);
    v44 = v100;
    v100 = 0;
    if ( v44 && _InterlockedExchange64((volatile __int64 *)(v44 + 8), 2) )
    {
      *(_QWORD *)(v44 + 104) |= 1uLL;
      (*(void (__fastcall **)(__int64))(v44 + 96))(v44 + 96);
    }
    std::wstring::~wstring(v119, v42, v43);
    std::wstring::~wstring(v118, v45, v46);
    v34 = (__int128 *)v117;
  }
  std::wstring::~wstring(v34, v32, v33);
  v49 = v112;
  if ( v112 >= 0 )
  {
    v108 = 0;
    v109 = 0;
    std::string::_Construct<1,char const *>(&v108, v9, a5[1]);
    v55 = &v108;
    if ( *((_QWORD *)&v109 + 1) > 0xFu )
      v55 = (__int128 *)v108;
    v52 = WebAuthNWriteEventCloudStoreOperationSuccess(1, *v102, *v101, v55);
    v53 = retaddr;
    if ( v52 < 0 )
    {
      v54 = 203;
      goto LABEL_39;
    }
  }
  else
  {
    if ( (unsigned int)dword_180075000 > 4 )
    {
      v99 = "ProfileDataStore::SaveAsync";
      v50 = v105;
      if ( v107 > 0xF )
        v50 = *(int **)v105;
      v104[0] = (__int64)v50;
      LODWORD(v100) = v112;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (unsigned int)"ProfileDataStore::SaveAsync",
        (unsigned int)byte_180069963,
        v47,
        v48,
        (__int64)&v100,
        (__int64)v104,
        (__int64)&v99);
    }
    v108 = 0;
    v109 = 0;
    std::string::_Construct<1,char const *>(&v108, v9, a5[1]);
    v51 = &v108;
    if ( *((_QWORD *)&v109 + 1) > 0xFu )
      v51 = (__int128 *)v108;
    v97 = v49;
    v52 = WebAuthNWriteEventCloudStoreOperationFailure(1, *v102, *v101, v51);
    v53 = retaddr;
    if ( v52 < 0 )
    {
      v54 = 195;
LABEL_39:
      wil::details::in1diag3::_Log_Hr(
        v53,
        (void *)v54,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\pdr\\lib\\pdrsyncstore.cpp",
        (const char *)(unsigned int)v52,
        v97);
    }
  }
  std::string::~string(&v108);
  if ( v49 == -2145844839 )
  {
    v56 = *a7;
    std::wstring::wstring(v122, *a7 + 56);
    std::wstring::wstring(v123, v56 + 88);
    std::wstring::wstring(v124, v56 + 120);
    v57 = v105;
    if ( v107 > 0xF )
      v57 = *(int **)v105;
    *(_QWORD *)&v98 = v57;
    *((_QWORD *)&v98 + 1) = v106;
    v58 = FidoUtils::IncrementCorrelationVector(&v115, &v98);
    std::string::operator=(v105, v58);
    std::string::~string(&v115);
    v102 = 0;
    v59 = v105;
    if ( v107 > 0xF )
      LODWORD(v59) = v105[0];
    v60 = wil::ProfileDataStore::LoadAsync<Windows::Data::Security::Passkey::RecoveryItemPdr>(
            *(_QWORD *)a2,
            (unsigned int)&v101,
            (unsigned int)v122,
            (_DWORD)v59,
            (__int64)&v102,
            34);
    v61 = (_QWORD *)wil::details::coro::task_base<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::get(
                      v60,
                      &v115);
    std::wstring::wstring(&v108, *v61 + 152LL);
    v62 = v116;
    if ( v116 )
    {
      if ( _InterlockedExchangeAdd(v116 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v62)(v62);
        if ( _InterlockedExchangeAdd(v62 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v62 + 8LL))(v62);
      }
    }
    v63 = v101;
    v101 = 0;
    if ( v63 && _InterlockedExchange64(v63 + 1, 2) )
    {
      v63[7] |= 1uLL;
      ((void (__fastcall *)(_QWORD *))v63[6])(v63 + 6);
    }
    v64 = v105;
    if ( v107 > 0xF )
      v64 = *(int **)v105;
    *(_QWORD *)&v98 = v64;
    *((_QWORD *)&v98 + 1) = v106;
    v65 = FidoUtils::IncrementCorrelationVector(v120, &v98);
    std::string::operator=(v105, v65);
    std::string::~string(v120);
    v99 = *(const char **)a2;
    v115 = (int **)&v102;
    v102 = 0;
    v66 = v105;
    if ( v107 > 0xF )
      v66 = *(int **)v105;
    v67 = *a7;
    std::wstring::wstring(v117, *a7 + 56);
    std::wstring::wstring(v118, v67 + 88);
    std::wstring::wstring(v119, v67 + 120);
    v98 = 0;
    v68 = a7[1];
    if ( v68 )
      _InterlockedIncrement((volatile signed __int32 *)(v68 + 8));
    v98 = *(_OWORD *)a7;
    v69 = wil::ProfileDataStore::SaveAsync<Windows::Data::Security::Passkey::RecoveryItemPdr>(
            (_DWORD)v99,
            (unsigned int)&v101,
            (unsigned int)&v98,
            (unsigned int)v117,
            (__int64)v66,
            (__int64)&v102);
    v70 = wil::details::coro::task_base<wil::ProfileDataStoreSaveResult>::get(v69, v120);
    v110 = *(_QWORD *)v70;
    v111 = *(_DWORD *)(v70 + 8);
    v112 = *(_DWORD *)(v70 + 12);
    std::wstring::operator=(v113, v70 + 16);
    v114 = *(_QWORD *)(v70 + 48);
    std::wstring::~wstring(v121, v71, v72);
    v75 = v101;
    v101 = 0;
    if ( v75 && _InterlockedExchange64(v75 + 1, 2) )
    {
      v75[13] |= 1uLL;
      ((void (__fastcall *)(_QWORD *))v75[12])(v75 + 12);
    }
    std::wstring::~wstring(v119, v73, v74);
    std::wstring::~wstring(v118, v76, v77);
    std::wstring::~wstring(v117, v78, v79);
    v49 = v112;
    if ( v112 < 0 && (unsigned int)dword_180075000 > 4 )
    {
      v99 = "ProfileDataStore::SaveAsync";
      v84 = v105;
      if ( v107 > 0xF )
        v84 = *(int **)v105;
      v104[0] = (__int64)v84;
      LODWORD(v100) = v112;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v81,
        (unsigned int)&byte_180069887,
        v82,
        v83,
        (__int64)&v100,
        (__int64)v104,
        (__int64)&v99);
    }
    std::wstring::~wstring(&v108, v80, v82);
    std::wstring::~wstring(v124, v85, v86);
    std::wstring::~wstring(v123, v87, v88);
    std::wstring::~wstring(v122, v89, v90);
  }
  v91 = 0;
  if ( v49 < 0 )
    v91 = v49;
  *(_DWORD *)a1 = v91;
  *((_DWORD *)a1 + 1) = 0;
  std::wstring::wstring(a1 + 8, v113);
  std::wstring::~wstring(v113, v92, v93);
  std::string::~string(v105);
  v94 = *(volatile signed __int32 **)(a2 + 8);
  if ( v94 )
  {
    if ( _InterlockedExchangeAdd(v94 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v94)(v94);
      if ( _InterlockedExchangeAdd(v94 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v94 + 8LL))(v94);
    }
  }
  v95 = (volatile signed __int32 *)a7[1];
  if ( v95 )
  {
    if ( _InterlockedExchangeAdd(v95 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v95)(v95);
      if ( _InterlockedExchangeAdd(v95 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v95 + 8LL))(v95);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18003d9fc  push    rbp
0x18003d9fe  push    rbx
0x18003d9ff  push    rsi
0x18003da00  push    rdi
0x18003da01  push    r12
0x18003da03  push    r13
0x18003da05  push    r14
0x18003da07  push    r15
0x18003da09  lea     rbp, [rsp-158h]
0x18003da11  sub     rsp, 258h
0x18003da18  mov     rax, cs:__security_cookie
0x18003da1f  xor     rax, rsp
0x18003da22  mov     [rbp+190h+var_50], rax
0x18003da29  mov     [rsp+290h+var_220], r9
0x18003da2e  mov     [rsp+290h+var_218], r8
0x18003da33  mov     r12, rdx
0x18003da36  mov     r14, rcx
0x18003da39  mov     [rsp+290h+var_230], rcx
0x18003da3e  mov     [rbp+190h+var_1F8], rdx
0x18003da42  mov     r13, [rbp+190h+arg_20]
0x18003da49  mov     rbx, [rbp+190h+arg_28]
0x18003da50  mov     rdi, [rbp+190h+arg_30]
0x18003da57  mov     [rbp+190h+var_1F0], rdi
0x18003da5b  xor     esi, esi
0x18003da5d  mov     r15, [r13+0]
0x18003da61  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003da65  inc     rax
0x18003da68  cmp     [r15+rax], sil
0x18003da6c  jnz     short loc_18003DA65
0x18003da6e  mov     qword ptr [rsp+290h+var_240], r15
0x18003da73  mov     qword ptr [rsp+290h+var_240+8], rax
0x18003da78  lea     rdx, [rsp+290h+var_240]
0x18003da7d  lea     rcx, [rbp+190h+var_1E8]
0x18003da81  call    ?ExtendCorrelationVector@FidoUtils@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_zstring_view@D@wil@@@Z; FidoUtils::ExtendCorrelationVector(wil::basic_zstring_view<char>)
0x18003da86  nop
0x18003da87  mov     eax, cs:dword_180075000
0x18003da8d  cmp     eax, 4
0x18003da90  jbe     short loc_18003DAB9
0x18003da92  lea     rax, [rbp+190h+var_1E8]
0x18003da96  cmp     [rbp+190h+var_1D0], 0Fh
0x18003da9b  cmova   rax, qword ptr [rbp+190h+var_1E8]
0x18003daa0  mov     [rbp+190h+var_210], rax
0x18003daa4  lea     rax, [rbp+190h+var_210]
0x18003daa8  mov     qword ptr [rsp+290h+var_270], rax
0x18003daad  lea     rdx, byte_180069927
0x18003dab4  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003dab9  mov     [rbp+190h+var_1A8], rsi
0x18003dabd  xorps   xmm0, xmm0
0x18003dac0  movups  [rbp+190h+var_198], xmm0
0x18003dac4  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18003dacc  movdqu  [rbp+190h+var_188], xmm1
0x18003dad1  mov     word ptr [rbp+190h+var_198], si
0x18003dad5  mov     rcx, [rbp+190h+var_1D8]
0x18003dad9  lea     rax, [rbp+190h+var_1E8]
0x18003dadd  cmp     [rbp+190h+var_1D0], 0Fh
0x18003dae2  cmova   rax, qword ptr [rbp+190h+var_1E8]
0x18003dae7  mov     qword ptr [rsp+290h+var_240], rax
0x18003daec  mov     qword ptr [rsp+290h+var_240+8], rcx
0x18003daf1  lea     rdx, [rsp+290h+var_240]
0x18003daf6  lea     rcx, [rbp+190h+var_1C8]
0x18003dafa  call    ?IncrementCorrelationVector@FidoUtils@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_zstring_view@D@wil@@@Z; FidoUtils::IncrementCorrelationVector(wil::basic_zstring_view<char>)
0x18003daff  mov     rdx, rax
0x18003db02  lea     rcx, [rbp+190h+var_1E8]
0x18003db06  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18003db0b  lea     rcx, [rbp+190h+var_1C8]
0x18003db0f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18003db14  mov     r8, [rbx+8]
0x18003db18  test    r8, r8
0x18003db1b  jz      loc_18003DCA4
0x18003db21  xorps   xmm0, xmm0
0x18003db24  movups  [rbp+190h+var_1C8], xmm0
0x18003db28  xorps   xmm1, xmm1
0x18003db2b  movdqu  [rbp+190h+var_1B8], xmm1
0x18003db30  mov     rdx, [rbx]
0x18003db33  lea     rcx, [rbp+190h+var_1C8]
0x18003db37  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003db3c  nop
0x18003db3d  mov     rax, [r12]
0x18003db41  mov     [rsp+290h+var_230], rax
0x18003db46  lea     rsi, [rbp+190h+var_1C8]
0x18003db4a  cmp     qword ptr [rbp+190h+var_1B8+8], 7
0x18003db4f  cmova   rsi, qword ptr [rbp+190h+var_1C8]
0x18003db54  lea     rax, [rsp+290h+var_228]
0x18003db59  mov     [rbp+190h+var_170], rax
0x18003db5d  mov     [rsp+290h+var_228], 0
0x18003db66  lea     rax, [rbp+190h+var_1E8]
0x18003db6a  cmp     [rbp+190h+var_1D0], 0Fh
0x18003db6f  cmova   rax, qword ptr [rbp+190h+var_1E8]
0x18003db74  mov     [rbp+190h+var_208], rax
0x18003db78  mov     rbx, [rdi]
0x18003db7b  lea     rdx, [rbx+38h]
0x18003db7f  lea     rcx, [rbp+190h+var_150]
0x18003db83  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003db88  nop
0x18003db89  lea     rdx, [rbx+58h]
0x18003db8d  lea     rcx, [rbp+190h+var_130]
0x18003db91  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003db96  nop
0x18003db97  lea     rdx, [rbx+78h]
0x18003db9b  lea     rcx, [rbp+190h+var_110]
0x18003dba2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003dba7  nop
0x18003dba8  xorps   xmm0, xmm0
0x18003dbab  movdqu  [rsp+290h+var_240], xmm0
0x18003dbb1  mov     rax, [rdi+8]
0x18003dbb5  test    rax, rax
0x18003dbb8  jz      short loc_18003DBBE
0x18003dbba  lock inc dword ptr [rax+8]
0x18003dbbe  mov     rax, [rdi]
0x18003dbc1  mov     qword ptr [rsp+290h+var_240], rax
0x18003dbc6  mov     rax, [rdi+8]
0x18003dbca  mov     qword ptr [rsp+290h+var_240+8], rax
0x18003dbcf  mov     [rsp+290h+var_250], rsi
0x18003dbd4  lea     rax, [rsp+290h+var_228]
0x18003dbd9  mov     [rsp+290h+var_268], rax
0x18003dbde  mov     rax, [rbp+190h+var_208]
0x18003dbe2  mov     qword ptr [rsp+290h+var_270], rax
0x18003dbe7  lea     r9, [rbp+190h+var_150]
0x18003dbeb  lea     r8, [rsp+290h+var_240]
0x18003dbf0  lea     rdx, [rbp+190h+var_210]
0x18003dbf4  mov     rcx, [rsp+290h+var_230]
0x18003dbf9  call    ??$SaveAsync@URecoveryItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@QEAA?AU?$task@VProfileDataStoreSaveResult@wil@@@1@V?$shared_ptr@V?$ProfileDataItem@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@AEBV?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@1@PEBDVcancellation_token@Concurrency@@W4ProfileDataStoreSaveOptions@1@_KPEBG@Z; wil::ProfileDataStore::SaveAsync<Windows::Data::Security::Passkey::RecoveryItemPdr>(std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::RecoveryItemPdr>>,wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr> const &,char const *,Concurrency::cancellation_token,wil::ProfileDataStoreSaveOptions,unsigned __int64,ushort const *)
0x18003dbfe  nop
0x18003dbff  lea     rdx, [rbp+190h+var_F0]
0x18003dc06  mov     rcx, rax
0x18003dc09  call    ?get@?$task_base@VProfileDataStoreSaveResult@wil@@@coro@details@wil@@QEHAA@XZ; wil::details::coro::task_base<wil::ProfileDataStoreSaveResult>::get(void)
0x18003dc0e  mov     rbx, rax
0x18003dc11  mov     rcx, [rax]
0x18003dc14  mov     [rbp+190h+var_1A8], rcx
0x18003dc18  mov     ecx, [rax+8]
0x18003dc1b  mov     [rbp+190h+var_1A0], ecx
0x18003dc1e  mov     ecx, [rax+0Ch]
0x18003dc21  mov     [rbp+190h+var_19C], ecx
0x18003dc24  lea     rdx, [rax+10h]
0x18003dc28  lea     rcx, [rbp+190h+var_198]
0x18003dc2c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003dc31  mov     rax, [rbx+30h]
0x18003dc35  mov     [rbp+190h+var_178], rax
0x18003dc39  lea     rcx, [rbp+190h+var_E0]
0x18003dc40  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003dc45  nop
0x18003dc46  mov     rcx, [rbp+190h+var_210]
0x18003dc4a  mov     [rbp+190h+var_210], 0
0x18003dc52  mov     esi, 2
0x18003dc57  test    rcx, rcx
0x18003dc5a  jz      short loc_18003DC7C
0x18003dc5c  mov     eax, esi
0x18003dc5e  xchg    rax, [rcx+8]
0x18003dc62  test    rax, rax
0x18003dc65  jz      short loc_18003DC7C
0x18003dc67  lea     rax, [rcx+60h]
0x18003dc6b  or      qword ptr [rax+8], 1
0x18003dc70  mov     rcx, rax
0x18003dc73  mov     rax, [rax]
0x18003dc76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc7b  nop
0x18003dc7c  lea     rcx, [rbp+190h+var_110]
0x18003dc83  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003dc88  lea     rcx, [rbp+190h+var_130]
0x18003dc8c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003dc91  lea     rcx, [rbp+190h+var_150]
0x18003dc95  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003dc9a  nop
0x18003dc9b  lea     rcx, [rbp+190h+var_1C8]
0x18003dc9f  jmp     loc_18003DDE9
0x18003dca4  mov     rax, [r12]
0x18003dca8  mov     [rsp+290h+var_230], rax
0x18003dcad  lea     rcx, [rbp+190h+var_210]
0x18003dcb1  mov     [rbp+190h+var_170], rcx
0x18003dcb5  mov     [rbp+190h+var_210], rsi
0x18003dcb9  lea     rsi, [rbp+190h+var_1E8]
0x18003dcbd  cmp     [rbp+190h+var_1D0], 0Fh
0x18003dcc2  cmova   rsi, qword ptr [rbp+190h+var_1E8]
0x18003dcc7  mov     rbx, [rdi]
0x18003dcca  lea     rdx, [rbx+38h]
0x18003dcce  lea     rcx, [rbp+190h+var_150]
0x18003dcd2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003dcd7  nop
0x18003dcd8  lea     rdx, [rbx+58h]
0x18003dcdc  lea     rcx, [rbp+190h+var_130]
0x18003dce0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003dce5  nop
0x18003dce6  lea     rdx, [rbx+78h]
0x18003dcea  lea     rcx, [rbp+190h+var_110]
0x18003dcf1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003dcf6  nop
0x18003dcf7  xorps   xmm0, xmm0
0x18003dcfa  movdqu  [rsp+290h+var_240], xmm0
0x18003dd00  mov     rax, [rdi+8]
0x18003dd04  test    rax, rax
0x18003dd07  jz      short loc_18003DD0D
0x18003dd09  lock inc dword ptr [rax+8]
0x18003dd0d  mov     rax, [rdi]
0x18003dd10  mov     qword ptr [rsp+290h+var_240], rax
0x18003dd15  mov     rax, [rdi+8]
0x18003dd19  mov     qword ptr [rsp+290h+var_240+8], rax
0x18003dd1e  lea     rax, String1
0x18003dd25  mov     [rsp+290h+var_250], rax
0x18003dd2a  lea     rax, [rbp+190h+var_210]
0x18003dd2e  mov     [rsp+290h+var_268], rax
0x18003dd33  mov     qword ptr [rsp+290h+var_270], rsi; int
0x18003dd38  lea     r9, [rbp+190h+var_150]
0x18003dd3c  lea     r8, [rsp+290h+var_240]
0x18003dd41  lea     rdx, [rsp+290h+var_228]
0x18003dd46  mov     rcx, [rsp+290h+var_230]
0x18003dd4b  call    ??$SaveAsync@URecoveryItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@QEAA?AU?$task@VProfileDataStoreSaveResult@wil@@@1@V?$shared_ptr@V?$ProfileDataItem@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@AEBV?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@1@PEBDVcancellation_token@Concurrency@@W4ProfileDataStoreSaveOptions@1@_KPEBG@Z; wil::ProfileDataStore::SaveAsync<Windows::Data::Security::Passkey::RecoveryItemPdr>(std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::RecoveryItemPdr>>,wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr> const &,char const *,Concurrency::cancellation_token,wil::ProfileDataStoreSaveOptions,unsigned __int64,ushort const *)
0x18003dd50  nop
0x18003dd51  lea     rdx, [rbp+190h+var_F0]
0x18003dd58  mov     rcx, rax
0x18003dd5b  call    ?get@?$task_base@VProfileDataStoreSaveResult@wil@@@coro@details@wil@@QEHAA@XZ; wil::details::coro::task_base<wil::ProfileDataStoreSaveResult>::get(void)
0x18003dd60  mov     rbx, rax
0x18003dd63  mov     rcx, [rax]
0x18003dd66  mov     [rbp+190h+var_1A8], rcx
0x18003dd6a  mov     ecx, [rax+8]
0x18003dd6d  mov     [rbp+190h+var_1A0], ecx
0x18003dd70  mov     ecx, [rax+0Ch]
0x18003dd73  mov     [rbp+190h+var_19C], ecx
0x18003dd76  lea     rdx, [rax+10h]
0x18003dd7a  lea     rcx, [rbp+190h+var_198]
0x18003dd7e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003dd83  mov     rax, [rbx+30h]
0x18003dd87  mov     [rbp+190h+var_178], rax
0x18003dd8b  lea     rcx, [rbp+190h+var_E0]
0x18003dd92  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003dd97  nop
0x18003dd98  mov     rcx, [rsp+290h+var_228]
0x18003dd9d  mov     [rsp+290h+var_228], 0
0x18003dda6  mov     esi, 2
0x18003ddab  test    rcx, rcx
0x18003ddae  jz      short loc_18003DDD0
0x18003ddb0  mov     eax, esi
0x18003ddb2  xchg    rax, [rcx+8]
0x18003ddb6  test    rax, rax
0x18003ddb9  jz      short loc_18003DDD0
0x18003ddbb  lea     rax, [rcx+60h]
0x18003ddbf  or      qword ptr [rax+8], 1
0x18003ddc4  mov     rcx, rax
0x18003ddc7  mov     rax, [rax]
0x18003ddca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ddcf  nop
0x18003ddd0  lea     rcx, [rbp+190h+var_110]
0x18003ddd7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003dddc  lea     rcx, [rbp+190h+var_130]
0x18003dde0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003dde5  lea     rcx, [rbp+190h+var_150]
0x18003dde9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003ddee  mov     ebx, [rbp+190h+var_19C]
0x18003ddf1  lea     rcx, aProfiledatasto_2; "ProfileDataStore::SaveAsync"
0x18003ddf8  test    ebx, ebx
0x18003ddfa  jns     loc_18003DEAC
0x18003de00  mov     eax, cs:dword_180075000
0x18003de06  cmp     eax, 4
0x18003de09  jbe     short loc_18003DE4F
0x18003de0b  mov     [rsp+290h+var_230], rcx
0x18003de10  lea     rax, [rbp+190h+var_1E8]
0x18003de14  cmp     [rbp+190h+var_1D0], 0Fh
0x18003de19  cmova   rax, qword ptr [rbp+190h+var_1E8]
0x18003de1e  mov     [rbp+190h+var_208], rax
0x18003de22  mov     dword ptr [rsp+290h+var_228], ebx
0x18003de26  lea     rax, [rsp+290h+var_230]
0x18003de2b  mov     [rsp+290h+var_260], rax
0x18003de30  lea     rax, [rbp+190h+var_208]
0x18003de34  mov     [rsp+290h+var_268], rax
0x18003de39  lea     rax, [rsp+290h+var_228]
0x18003de3e  mov     qword ptr [rsp+290h+var_270], rax
0x18003de43  lea     rdx, byte_180069963
0x18003de4a  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18003de4f  xorps   xmm0, xmm0
0x18003de52  movups  [rbp+190h+var_1C8], xmm0
0x18003de56  xorps   xmm1, xmm1
0x18003de59  movdqu  [rbp+190h+var_1B8], xmm1
0x18003de5e  mov     r8, [r13+8]
0x18003de62  mov     rdx, r15
0x18003de65  lea     rcx, [rbp+190h+var_1C8]
0x18003de69  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18003de6e  lea     r9, [rbp+190h+var_1C8]
0x18003de72  cmp     qword ptr [rbp+190h+var_1B8+8], 0Fh
0x18003de77  cmova   r9, qword ptr [rbp+190h+var_1C8]
0x18003de7c  mov     [rsp+290h+var_270], ebx
0x18003de80  mov     r8, [rsp+290h+var_220]
0x18003de85  mov     r8, [r8]
0x18003de88  mov     rdx, [rsp+290h+var_218]
0x18003de8d  mov     edx, [rdx]
0x18003de8f  mov     ecx, 1
0x18003de94  call    cs:__imp_WebAuthNWriteEventCloudStoreOperationFailure
0x18003de9a  mov     rcx, [rbp+198h]
0x18003dea1  test    eax, eax
0x18003dea3  jns     short loc_18003DF12
0x18003dea5  mov     edx, 0C3h
0x18003deaa  jmp     short loc_18003DF03
0x18003deac  xorps   xmm0, xmm0
0x18003deaf  movups  [rbp+190h+var_1C8], xmm0
0x18003deb3  xorps   xmm1, xmm1
0x18003deb6  movdqu  [rbp+190h+var_1B8], xmm1
0x18003debb  mov     r8, [r13+8]
0x18003debf  mov     rdx, r15
0x18003dec2  lea     rcx, [rbp+190h+var_1C8]
0x18003dec6  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18003decb  lea     r9, [rbp+190h+var_1C8]
0x18003decf  cmp     qword ptr [rbp+190h+var_1B8+8], 0Fh
  ... truncated ...
```
