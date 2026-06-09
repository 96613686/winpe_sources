# PdrSyncUtils::SaveImpl_Windows::Data::Security::Passkey::PasskeyItemPdr_

- ea: `0x18003d07c`
- end: `0x18003d9f6`
- name: `PdrSyncUtils::SaveImpl_Windows::Data::Security::Passkey::PasskeyItemPdr_`
- size: `2426`
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
- `0x180038d50`
- `0x18003cba8`
- `0x18003d07c`
- `0x180040d10`
- `0x18004f6ac`
- `0x18004f8fc`
- `0x180054c40`
- `0x180054ecc`
- `0x180061010`

## import_xrefs

- `webauthn!WebAuthNWriteEventCloudStoreOperationFailure` at `0x18003d51a`
- `webauthn!WebAuthNWriteEventCloudStoreOperationFailure` at `0x18003d51a`
- `webauthn!WebAuthNWriteEventCloudStoreOperationSuccess` at `0x18003d573`
- `webauthn!WebAuthNWriteEventCloudStoreOperationSuccess` at `0x18003d573`

## string_xrefs

- `0x18003d58c`: `onecore\ds\security\ngc\utils\pdr\lib\pdrsyncstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
char *__fastcall PdrSyncUtils::SaveImpl_Windows::Data::Security::Passkey::PasskeyItemPdr_(
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
      (unsigned int)byte_180069AF3,
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
    std::wstring::wstring(v117, *a7 + 88);
    std::wstring::wstring(v118, v19 + 120);
    std::wstring::wstring(v119, v19 + 152);
    v98 = 0;
    v20 = a7[1];
    if ( v20 )
      _InterlockedIncrement((volatile signed __int32 *)(v20 + 8));
    v98 = *(_OWORD *)a7;
    v21 = wil::ProfileDataStore::SaveAsync<Windows::Data::Security::Passkey::PasskeyItemPdr>(
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
    std::wstring::wstring(v117, *a7 + 88);
    std::wstring::wstring(v118, v36 + 120);
    std::wstring::wstring(v119, v36 + 152);
    v98 = 0;
    v37 = a7[1];
    if ( v37 )
      _InterlockedIncrement((volatile signed __int32 *)(v37 + 8));
    v98 = *(_OWORD *)a7;
    v38 = wil::ProfileDataStore::SaveAsync<Windows::Data::Security::Passkey::PasskeyItemPdr>(
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
        (unsigned int)&byte_1800699C7,
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
    std::wstring::wstring(v122, *a7 + 88);
    std::wstring::wstring(v123, v56 + 120);
    std::wstring::wstring(v124, v56 + 152);
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
    v60 = wil::ProfileDataStore::LoadAsync<Windows::Data::Security::Passkey::PasskeyItemPdr>(
            *(_QWORD *)a2,
            (unsigned int)&v101,
            (unsigned int)v122,
            (_DWORD)v59,
            (__int64)&v102,
            34);
    v61 = (_QWORD *)wil::details::coro::task_base<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::get(
                      v60,
                      &v115);
    std::wstring::wstring(&v108, *v61 + 184LL);
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
    std::wstring::wstring(v117, *a7 + 88);
    std::wstring::wstring(v118, v67 + 120);
    std::wstring::wstring(v119, v67 + 152);
    v98 = 0;
    v68 = a7[1];
    if ( v68 )
      _InterlockedIncrement((volatile signed __int32 *)(v68 + 8));
    v98 = *(_OWORD *)a7;
    v69 = wil::ProfileDataStore::SaveAsync<Windows::Data::Security::Passkey::PasskeyItemPdr>(
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
        (unsigned int)byte_180069A2B,
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
0x18003d07c  push    rbp
0x18003d07e  push    rbx
0x18003d07f  push    rsi
0x18003d080  push    rdi
0x18003d081  push    r12
0x18003d083  push    r13
0x18003d085  push    r14
0x18003d087  push    r15
0x18003d089  lea     rbp, [rsp-158h]
0x18003d091  sub     rsp, 258h
0x18003d098  mov     rax, cs:__security_cookie
0x18003d09f  xor     rax, rsp
0x18003d0a2  mov     [rbp+190h+var_50], rax
0x18003d0a9  mov     [rsp+290h+var_220], r9
0x18003d0ae  mov     [rsp+290h+var_218], r8
0x18003d0b3  mov     r12, rdx
0x18003d0b6  mov     r14, rcx
0x18003d0b9  mov     [rsp+290h+var_230], rcx
0x18003d0be  mov     [rbp+190h+var_1F8], rdx
0x18003d0c2  mov     r13, [rbp+190h+arg_20]
0x18003d0c9  mov     rbx, [rbp+190h+arg_28]
0x18003d0d0  mov     rdi, [rbp+190h+arg_30]
0x18003d0d7  mov     [rbp+190h+var_1F0], rdi
0x18003d0db  xor     esi, esi
0x18003d0dd  mov     r15, [r13+0]
0x18003d0e1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003d0e5  inc     rax
0x18003d0e8  cmp     [r15+rax], sil
0x18003d0ec  jnz     short loc_18003D0E5
0x18003d0ee  mov     qword ptr [rsp+290h+var_240], r15
0x18003d0f3  mov     qword ptr [rsp+290h+var_240+8], rax
0x18003d0f8  lea     rdx, [rsp+290h+var_240]
0x18003d0fd  lea     rcx, [rbp+190h+var_1E8]
0x18003d101  call    ?ExtendCorrelationVector@FidoUtils@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_zstring_view@D@wil@@@Z; FidoUtils::ExtendCorrelationVector(wil::basic_zstring_view<char>)
0x18003d106  nop
0x18003d107  mov     eax, cs:dword_180075000
0x18003d10d  cmp     eax, 4
0x18003d110  jbe     short loc_18003D139
0x18003d112  lea     rax, [rbp+190h+var_1E8]
0x18003d116  cmp     [rbp+190h+var_1D0], 0Fh
0x18003d11b  cmova   rax, qword ptr [rbp+190h+var_1E8]
0x18003d120  mov     [rbp+190h+var_210], rax
0x18003d124  lea     rax, [rbp+190h+var_210]
0x18003d128  mov     qword ptr [rsp+290h+var_270], rax
0x18003d12d  lea     rdx, byte_180069AF3
0x18003d134  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003d139  mov     [rbp+190h+var_1A8], rsi
0x18003d13d  xorps   xmm0, xmm0
0x18003d140  movups  [rbp+190h+var_198], xmm0
0x18003d144  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18003d14c  movdqu  [rbp+190h+var_188], xmm1
0x18003d151  mov     word ptr [rbp+190h+var_198], si
0x18003d155  mov     rcx, [rbp+190h+var_1D8]
0x18003d159  lea     rax, [rbp+190h+var_1E8]
0x18003d15d  cmp     [rbp+190h+var_1D0], 0Fh
0x18003d162  cmova   rax, qword ptr [rbp+190h+var_1E8]
0x18003d167  mov     qword ptr [rsp+290h+var_240], rax
0x18003d16c  mov     qword ptr [rsp+290h+var_240+8], rcx
0x18003d171  lea     rdx, [rsp+290h+var_240]
0x18003d176  lea     rcx, [rbp+190h+var_1C8]
0x18003d17a  call    ?IncrementCorrelationVector@FidoUtils@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_zstring_view@D@wil@@@Z; FidoUtils::IncrementCorrelationVector(wil::basic_zstring_view<char>)
0x18003d17f  mov     rdx, rax
0x18003d182  lea     rcx, [rbp+190h+var_1E8]
0x18003d186  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18003d18b  lea     rcx, [rbp+190h+var_1C8]
0x18003d18f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18003d194  mov     r8, [rbx+8]
0x18003d198  test    r8, r8
0x18003d19b  jz      loc_18003D327
0x18003d1a1  xorps   xmm0, xmm0
0x18003d1a4  movups  [rbp+190h+var_1C8], xmm0
0x18003d1a8  xorps   xmm1, xmm1
0x18003d1ab  movdqu  [rbp+190h+var_1B8], xmm1
0x18003d1b0  mov     rdx, [rbx]
0x18003d1b3  lea     rcx, [rbp+190h+var_1C8]
0x18003d1b7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003d1bc  nop
0x18003d1bd  mov     rax, [r12]
0x18003d1c1  mov     [rsp+290h+var_230], rax
0x18003d1c6  lea     rsi, [rbp+190h+var_1C8]
0x18003d1ca  cmp     qword ptr [rbp+190h+var_1B8+8], 7
0x18003d1cf  cmova   rsi, qword ptr [rbp+190h+var_1C8]
0x18003d1d4  lea     rax, [rsp+290h+var_228]
0x18003d1d9  mov     [rbp+190h+var_170], rax
0x18003d1dd  mov     [rsp+290h+var_228], 0
0x18003d1e6  lea     rax, [rbp+190h+var_1E8]
0x18003d1ea  cmp     [rbp+190h+var_1D0], 0Fh
0x18003d1ef  cmova   rax, qword ptr [rbp+190h+var_1E8]
0x18003d1f4  mov     [rbp+190h+var_208], rax
0x18003d1f8  mov     rbx, [rdi]
0x18003d1fb  lea     rdx, [rbx+58h]
0x18003d1ff  lea     rcx, [rbp+190h+var_150]
0x18003d203  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003d208  nop
0x18003d209  lea     rdx, [rbx+78h]
0x18003d20d  lea     rcx, [rbp+190h+var_130]
0x18003d211  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003d216  nop
0x18003d217  lea     rdx, [rbx+98h]
0x18003d21e  lea     rcx, [rbp+190h+var_110]
0x18003d225  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003d22a  nop
0x18003d22b  xorps   xmm0, xmm0
0x18003d22e  movdqu  [rsp+290h+var_240], xmm0
0x18003d234  mov     rax, [rdi+8]
0x18003d238  test    rax, rax
0x18003d23b  jz      short loc_18003D241
0x18003d23d  lock inc dword ptr [rax+8]
0x18003d241  mov     rax, [rdi]
0x18003d244  mov     qword ptr [rsp+290h+var_240], rax
0x18003d249  mov     rax, [rdi+8]
0x18003d24d  mov     qword ptr [rsp+290h+var_240+8], rax
0x18003d252  mov     [rsp+290h+var_250], rsi
0x18003d257  lea     rax, [rsp+290h+var_228]
0x18003d25c  mov     [rsp+290h+var_268], rax
0x18003d261  mov     rax, [rbp+190h+var_208]
0x18003d265  mov     qword ptr [rsp+290h+var_270], rax
0x18003d26a  lea     r9, [rbp+190h+var_150]
0x18003d26e  lea     r8, [rsp+290h+var_240]
0x18003d273  lea     rdx, [rbp+190h+var_210]
0x18003d277  mov     rcx, [rsp+290h+var_230]
0x18003d27c  call    ??$SaveAsync@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@QEAA?AU?$task@VProfileDataStoreSaveResult@wil@@@1@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@AEBV?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@1@PEBDVcancellation_token@Concurrency@@W4ProfileDataStoreSaveOptions@1@_KPEBG@Z; wil::ProfileDataStore::SaveAsync<Windows::Data::Security::Passkey::PasskeyItemPdr>(std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>,wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> const &,char const *,Concurrency::cancellation_token,wil::ProfileDataStoreSaveOptions,unsigned __int64,ushort const *)
0x18003d281  nop
0x18003d282  lea     rdx, [rbp+190h+var_F0]
0x18003d289  mov     rcx, rax
0x18003d28c  call    ?get@?$task_base@VProfileDataStoreSaveResult@wil@@@coro@details@wil@@QEHAA@XZ; wil::details::coro::task_base<wil::ProfileDataStoreSaveResult>::get(void)
0x18003d291  mov     rbx, rax
0x18003d294  mov     rcx, [rax]
0x18003d297  mov     [rbp+190h+var_1A8], rcx
0x18003d29b  mov     ecx, [rax+8]
0x18003d29e  mov     [rbp+190h+var_1A0], ecx
0x18003d2a1  mov     ecx, [rax+0Ch]
0x18003d2a4  mov     [rbp+190h+var_19C], ecx
0x18003d2a7  lea     rdx, [rax+10h]
0x18003d2ab  lea     rcx, [rbp+190h+var_198]
0x18003d2af  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003d2b4  mov     rax, [rbx+30h]
0x18003d2b8  mov     [rbp+190h+var_178], rax
0x18003d2bc  lea     rcx, [rbp+190h+var_E0]
0x18003d2c3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d2c8  nop
0x18003d2c9  mov     rcx, [rbp+190h+var_210]
0x18003d2cd  mov     [rbp+190h+var_210], 0
0x18003d2d5  mov     esi, 2
0x18003d2da  test    rcx, rcx
0x18003d2dd  jz      short loc_18003D2FF
0x18003d2df  mov     eax, esi
0x18003d2e1  xchg    rax, [rcx+8]
0x18003d2e5  test    rax, rax
0x18003d2e8  jz      short loc_18003D2FF
0x18003d2ea  lea     rax, [rcx+60h]
0x18003d2ee  or      qword ptr [rax+8], 1
0x18003d2f3  mov     rcx, rax
0x18003d2f6  mov     rax, [rax]
0x18003d2f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d2fe  nop
0x18003d2ff  lea     rcx, [rbp+190h+var_110]
0x18003d306  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d30b  lea     rcx, [rbp+190h+var_130]
0x18003d30f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d314  lea     rcx, [rbp+190h+var_150]
0x18003d318  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d31d  nop
0x18003d31e  lea     rcx, [rbp+190h+var_1C8]
0x18003d322  jmp     loc_18003D46F
0x18003d327  mov     rax, [r12]
0x18003d32b  mov     [rsp+290h+var_230], rax
0x18003d330  lea     rcx, [rbp+190h+var_210]
0x18003d334  mov     [rbp+190h+var_170], rcx
0x18003d338  mov     [rbp+190h+var_210], rsi
0x18003d33c  lea     rsi, [rbp+190h+var_1E8]
0x18003d340  cmp     [rbp+190h+var_1D0], 0Fh
0x18003d345  cmova   rsi, qword ptr [rbp+190h+var_1E8]
0x18003d34a  mov     rbx, [rdi]
0x18003d34d  lea     rdx, [rbx+58h]
0x18003d351  lea     rcx, [rbp+190h+var_150]
0x18003d355  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003d35a  nop
0x18003d35b  lea     rdx, [rbx+78h]
0x18003d35f  lea     rcx, [rbp+190h+var_130]
0x18003d363  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003d368  nop
0x18003d369  lea     rdx, [rbx+98h]
0x18003d370  lea     rcx, [rbp+190h+var_110]
0x18003d377  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003d37c  nop
0x18003d37d  xorps   xmm0, xmm0
0x18003d380  movdqu  [rsp+290h+var_240], xmm0
0x18003d386  mov     rax, [rdi+8]
0x18003d38a  test    rax, rax
0x18003d38d  jz      short loc_18003D393
0x18003d38f  lock inc dword ptr [rax+8]
0x18003d393  mov     rax, [rdi]
0x18003d396  mov     qword ptr [rsp+290h+var_240], rax
0x18003d39b  mov     rax, [rdi+8]
0x18003d39f  mov     qword ptr [rsp+290h+var_240+8], rax
0x18003d3a4  lea     rax, String1
0x18003d3ab  mov     [rsp+290h+var_250], rax
0x18003d3b0  lea     rax, [rbp+190h+var_210]
0x18003d3b4  mov     [rsp+290h+var_268], rax
0x18003d3b9  mov     qword ptr [rsp+290h+var_270], rsi; int
0x18003d3be  lea     r9, [rbp+190h+var_150]
0x18003d3c2  lea     r8, [rsp+290h+var_240]
0x18003d3c7  lea     rdx, [rsp+290h+var_228]
0x18003d3cc  mov     rcx, [rsp+290h+var_230]
0x18003d3d1  call    ??$SaveAsync@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@QEAA?AU?$task@VProfileDataStoreSaveResult@wil@@@1@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@AEBV?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@1@PEBDVcancellation_token@Concurrency@@W4ProfileDataStoreSaveOptions@1@_KPEBG@Z; wil::ProfileDataStore::SaveAsync<Windows::Data::Security::Passkey::PasskeyItemPdr>(std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>,wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> const &,char const *,Concurrency::cancellation_token,wil::ProfileDataStoreSaveOptions,unsigned __int64,ushort const *)
0x18003d3d6  nop
0x18003d3d7  lea     rdx, [rbp+190h+var_F0]
0x18003d3de  mov     rcx, rax
0x18003d3e1  call    ?get@?$task_base@VProfileDataStoreSaveResult@wil@@@coro@details@wil@@QEHAA@XZ; wil::details::coro::task_base<wil::ProfileDataStoreSaveResult>::get(void)
0x18003d3e6  mov     rbx, rax
0x18003d3e9  mov     rcx, [rax]
0x18003d3ec  mov     [rbp+190h+var_1A8], rcx
0x18003d3f0  mov     ecx, [rax+8]
0x18003d3f3  mov     [rbp+190h+var_1A0], ecx
0x18003d3f6  mov     ecx, [rax+0Ch]
0x18003d3f9  mov     [rbp+190h+var_19C], ecx
0x18003d3fc  lea     rdx, [rax+10h]
0x18003d400  lea     rcx, [rbp+190h+var_198]
0x18003d404  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003d409  mov     rax, [rbx+30h]
0x18003d40d  mov     [rbp+190h+var_178], rax
0x18003d411  lea     rcx, [rbp+190h+var_E0]
0x18003d418  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d41d  nop
0x18003d41e  mov     rcx, [rsp+290h+var_228]
0x18003d423  mov     [rsp+290h+var_228], 0
0x18003d42c  mov     esi, 2
0x18003d431  test    rcx, rcx
0x18003d434  jz      short loc_18003D456
0x18003d436  mov     eax, esi
0x18003d438  xchg    rax, [rcx+8]
0x18003d43c  test    rax, rax
0x18003d43f  jz      short loc_18003D456
0x18003d441  lea     rax, [rcx+60h]
0x18003d445  or      qword ptr [rax+8], 1
0x18003d44a  mov     rcx, rax
0x18003d44d  mov     rax, [rax]
0x18003d450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d455  nop
0x18003d456  lea     rcx, [rbp+190h+var_110]
0x18003d45d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d462  lea     rcx, [rbp+190h+var_130]
0x18003d466  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d46b  lea     rcx, [rbp+190h+var_150]
0x18003d46f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d474  mov     ebx, [rbp+190h+var_19C]
0x18003d477  lea     rcx, aProfiledatasto_2; "ProfileDataStore::SaveAsync"
0x18003d47e  test    ebx, ebx
0x18003d480  jns     loc_18003D532
0x18003d486  mov     eax, cs:dword_180075000
0x18003d48c  cmp     eax, 4
0x18003d48f  jbe     short loc_18003D4D5
0x18003d491  mov     [rsp+290h+var_230], rcx
0x18003d496  lea     rax, [rbp+190h+var_1E8]
0x18003d49a  cmp     [rbp+190h+var_1D0], 0Fh
0x18003d49f  cmova   rax, qword ptr [rbp+190h+var_1E8]
0x18003d4a4  mov     [rbp+190h+var_208], rax
0x18003d4a8  mov     dword ptr [rsp+290h+var_228], ebx
0x18003d4ac  lea     rax, [rsp+290h+var_230]
0x18003d4b1  mov     [rsp+290h+var_260], rax
0x18003d4b6  lea     rax, [rbp+190h+var_208]
0x18003d4ba  mov     [rsp+290h+var_268], rax
0x18003d4bf  lea     rax, [rsp+290h+var_228]
0x18003d4c4  mov     qword ptr [rsp+290h+var_270], rax
0x18003d4c9  lea     rdx, byte_1800699C7
0x18003d4d0  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18003d4d5  xorps   xmm0, xmm0
0x18003d4d8  movups  [rbp+190h+var_1C8], xmm0
0x18003d4dc  xorps   xmm1, xmm1
0x18003d4df  movdqu  [rbp+190h+var_1B8], xmm1
0x18003d4e4  mov     r8, [r13+8]
0x18003d4e8  mov     rdx, r15
0x18003d4eb  lea     rcx, [rbp+190h+var_1C8]
0x18003d4ef  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18003d4f4  lea     r9, [rbp+190h+var_1C8]
0x18003d4f8  cmp     qword ptr [rbp+190h+var_1B8+8], 0Fh
0x18003d4fd  cmova   r9, qword ptr [rbp+190h+var_1C8]
0x18003d502  mov     [rsp+290h+var_270], ebx
0x18003d506  mov     r8, [rsp+290h+var_220]
0x18003d50b  mov     r8, [r8]
0x18003d50e  mov     rdx, [rsp+290h+var_218]
0x18003d513  mov     edx, [rdx]
0x18003d515  mov     ecx, 1
0x18003d51a  call    cs:__imp_WebAuthNWriteEventCloudStoreOperationFailure
0x18003d520  mov     rcx, [rbp+198h]
0x18003d527  test    eax, eax
0x18003d529  jns     short loc_18003D598
0x18003d52b  mov     edx, 0C3h
0x18003d530  jmp     short loc_18003D589
0x18003d532  xorps   xmm0, xmm0
0x18003d535  movups  [rbp+190h+var_1C8], xmm0
0x18003d539  xorps   xmm1, xmm1
0x18003d53c  movdqu  [rbp+190h+var_1B8], xmm1
0x18003d541  mov     r8, [r13+8]
0x18003d545  mov     rdx, r15
0x18003d548  lea     rcx, [rbp+190h+var_1C8]
0x18003d54c  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18003d551  lea     r9, [rbp+190h+var_1C8]
0x18003d555  cmp     qword ptr [rbp+190h+var_1B8+8], 0Fh
  ... truncated ...
```
