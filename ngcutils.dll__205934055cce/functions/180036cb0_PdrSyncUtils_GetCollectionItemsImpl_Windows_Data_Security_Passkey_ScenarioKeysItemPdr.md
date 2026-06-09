# PdrSyncUtils::GetCollectionItemsImpl_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_

- ea: `0x180036cb0`
- end: `0x1800378eb`
- name: `PdrSyncUtils::GetCollectionItemsImpl_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_`
- size: `3131`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180049500`

## callees

- `0x1800012e4`
- `0x180001374`
- `0x180003080`
- `0x180003568`
- `0x180003bc8`
- `0x18000c95c`
- `0x18000ce74`
- `0x18000cfcc`
- `0x1800129f4`
- `0x18001354c`
- `0x18001361c`
- `0x1800137a0`
- `0x180013834`
- `0x180013b94`
- `0x18001addc`
- `0x18001b59c`
- `0x18001b60c`
- `0x180034de0`
- `0x180036cb0`
- `0x180040d10`
- `0x180042448`
- `0x180042630`
- `0x18004eba0`
- `0x18004f554`
- `0x180054c40`
- `0x180054ecc`
- `0x180061010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800375db`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800375db`
- `webauthn!WebAuthNWriteEventCloudStoreOperationFailure` at `0x180037687`
- `webauthn!WebAuthNWriteEventCloudStoreOperationFailure` at `0x180037687`
- `webauthn!WebAuthNWriteEventCloudStoreOperationSuccess` at `0x180037709`
- `webauthn!WebAuthNWriteEventCloudStoreOperationSuccess` at `0x180037709`

## string_xrefs

- `0x18003769b`: `onecore\ds\security\ngc\utils\pdr\lib\pdrsyncstore.cpp`
- `0x18003771d`: `onecore\ds\security\ngc\utils\pdr\lib\pdrsyncstore.cpp`

## pseudocode

```c
int *__fastcall PdrSyncUtils::GetCollectionItemsImpl_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_(
        int *a1,
        __int64 *a2,
        unsigned int *a3,
        _QWORD *a4,
        _QWORD *a5,
        _QWORD *a6,
        const char *a7)
{
  __int64 *v8; // rsi
  __int64 v9; // rax
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  _QWORD *v13; // rax
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r8
  __int128 *v17; // rcx
  int v18; // r13d
  _QWORD *v19; // rax
  _QWORD *v20; // rax
  _QWORD *v21; // rax
  __int64 v22; // rax
  __int64 v23; // r15
  __int128 *v24; // r12
  __int128 *v25; // rsi
  _QWORD *v26; // rbx
  _QWORD *v27; // rdi
  volatile signed __int32 *v28; // rcx
  __int64 v29; // rbx
  int v30; // esi
  __int64 v31; // rdx
  __int64 v32; // r8
  int v33; // r8d
  int v34; // r9d
  __int64 v35; // rcx
  volatile signed __int32 *v36; // rax
  _QWORD *v37; // rdi
  const char *v38; // r14
  __int64 v39; // rax
  __int64 v40; // rcx
  int v41; // r13d
  volatile signed __int32 *v42; // rbx
  __int64 v43; // rbx
  int v44; // r13d
  __int64 v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // rax
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // rdx
  __int64 v55; // r8
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 v58; // rdx
  __int64 v59; // r15
  __int64 v60; // r8
  __int64 v61; // rdx
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 v64; // rdx
  __int64 v65; // r8
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 v70; // rdx
  __int64 v71; // r8
  __int64 v72; // rdx
  __int64 v73; // r8
  __int64 v74; // rdx
  __int64 v75; // r8
  __int64 v76; // rdx
  __int64 v77; // r8
  int v78; // ecx
  int v79; // r8d
  int v80; // r9d
  _QWORD *v81; // rax
  __int128 *v82; // r9
  int v83; // eax
  __int128 *v84; // r9
  int v85; // eax
  int *v86; // rdi
  _QWORD *v87; // rax
  __int64 v88; // rcx
  __int64 v89; // r8
  __int128 v90; // rax
  _QWORD *v91; // rax
  __int64 v92; // rcx
  __int64 v93; // rdx
  __int64 v94; // r8
  __int64 v95; // rdx
  __int64 v96; // r8
  __int64 v97; // rdx
  __int64 v98; // r8
  volatile signed __int32 *v99; // rbx
  const char *v100; // rcx
  __int64 v101; // rdx
  int v103; // [rsp+20h] [rbp-E0h]
  volatile signed __int32 *v104; // [rsp+40h] [rbp-C0h] BYREF
  int v105; // [rsp+48h] [rbp-B8h]
  int v106[2]; // [rsp+50h] [rbp-B0h] BYREF
  const char *v107; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v108; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v109; // [rsp+70h] [rbp-90h]
  _QWORD *v110; // [rsp+78h] [rbp-88h] BYREF
  __int64 v111; // [rsp+80h] [rbp-80h]
  _QWORD *v112; // [rsp+88h] [rbp-78h] BYREF
  __int64 v113; // [rsp+90h] [rbp-70h]
  _QWORD *v114; // [rsp+98h] [rbp-68h]
  unsigned int *v115; // [rsp+A0h] [rbp-60h]
  __int64 *v116; // [rsp+A8h] [rbp-58h]
  int *v117; // [rsp+B0h] [rbp-50h]
  _QWORD v118[5]; // [rsp+C0h] [rbp-40h] BYREF
  char v119[24]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v120; // [rsp+100h] [rbp+0h] BYREF
  __int128 v121; // [rsp+110h] [rbp+10h]
  __int128 v122; // [rsp+120h] [rbp+20h] BYREF
  __int64 v123; // [rsp+130h] [rbp+30h]
  unsigned __int64 v124; // [rsp+138h] [rbp+38h]
  __int128 v125; // [rsp+140h] [rbp+40h] BYREF
  __int128 v126; // [rsp+150h] [rbp+50h]
  _QWORD v127[3]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int64 v128; // [rsp+178h] [rbp+78h]
  __int128 v129; // [rsp+180h] [rbp+80h] BYREF
  __int128 v130; // [rsp+190h] [rbp+90h] BYREF
  __int128 v131; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v132; // [rsp+1B0h] [rbp+B0h]
  __int128 v133; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v134; // [rsp+1E0h] [rbp+E0h]
  __int128 v135; // [rsp+1E8h] [rbp+E8h] BYREF
  __int64 v136; // [rsp+1F8h] [rbp+F8h]
  __int64 v137; // [rsp+200h] [rbp+100h]
  int v138; // [rsp+208h] [rbp+108h]
  __int64 v139; // [rsp+210h] [rbp+110h]
  __int128 v140; // [rsp+220h] [rbp+120h] BYREF
  __int64 v141; // [rsp+230h] [rbp+130h]
  unsigned __int64 v142; // [rsp+238h] [rbp+138h]
  __int128 v143; // [rsp+240h] [rbp+140h] BYREF
  __int64 v144; // [rsp+250h] [rbp+150h]
  __int64 v145; // [rsp+258h] [rbp+158h]
  __int128 v146; // [rsp+260h] [rbp+160h] BYREF
  __int128 v147; // [rsp+270h] [rbp+170h]
  _BYTE v148[32]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v149[32]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v150[48]; // [rsp+2C0h] [rbp+1C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+248h]

  v115 = a3;
  v8 = a2;
  v116 = a2;
  v117 = a1;
  v118[2] = a1;
  v118[3] = a2;
  v114 = a5;
  v107 = a7;
  v118[4] = a7;
  v105 = 0;
  v9 = -1;
  do
    ++v9;
  while ( *(_BYTE *)(*a5 + v9) );
  *(_QWORD *)&v120 = *a5;
  *((_QWORD *)&v120 + 1) = v9;
  FidoUtils::ExtendCorrelationVector(v127, &v120);
  if ( (unsigned int)dword_180075000 > 4 )
  {
    v13 = v127;
    if ( v128 > 0xF )
      v13 = (_QWORD *)v127[0];
    *(_QWORD *)&v125 = v13;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v10,
      (unsigned int)word_180068C0A,
      v11,
      v12,
      (__int64)&v125);
  }
  v140 = 0;
  v141 = 0;
  v142 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v140, *a4, a4[1]);
  v133 = 0;
  v134 = 0;
  v135 = 0;
  v136 = 0;
  v137 = 7;
  LOWORD(v135) = 0;
  v138 = 0;
  v139 = 0;
  v14 = a6[1];
  if ( v14 )
  {
    v122 = 0;
    v123 = 0;
    v124 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v122, *a6, v14);
    v17 = &v122;
    v18 = 2;
  }
  else
  {
    v143 = 0;
    v144 = 0;
    v145 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v143, &String1, 0);
    v17 = &v143;
    v18 = 1;
  }
  v146 = *v17;
  v147 = v17[1];
  *((_QWORD *)v17 + 2) = 0;
  *((_QWORD *)v17 + 3) = 7;
  *(_WORD *)v17 = 0;
  if ( (v18 & 2) != 0 )
  {
    v18 &= ~2u;
    std::wstring::~wstring(&v122, v15, v16);
  }
  if ( (v18 & 1) != 0 )
  {
    v18 &= ~1u;
    std::wstring::~wstring(&v143, v15, v16);
  }
  v113 = 0;
  v19 = operator new(0x58u);
  *v19 = v19;
  v19[1] = v19;
  v19[2] = v19;
  *((_WORD *)v19 + 12) = 257;
  v112 = v19;
  v108 = 0;
  v109 = 0;
  v111 = 0;
  v20 = operator new(0x60u);
  *v20 = v20;
  v20[1] = v20;
  v20[2] = v20;
  *((_WORD *)v20 + 12) = 257;
  v110 = v20;
  while ( 2 )
  {
    v21 = v127;
    if ( v128 > 0xF )
      v21 = (_QWORD *)v127[0];
    v118[0] = v21;
    v118[1] = v127[2];
    v22 = FidoUtils::IncrementCorrelationVector(&v122, v118);
    std::string::operator=(v127, v22);
    std::string::~string(&v122);
    v23 = *v8;
    v24 = &v146;
    if ( *((_QWORD *)&v147 + 1) > 7u )
      v24 = (__int128 *)v146;
    v25 = &v140;
    if ( v142 > 7 )
      v25 = (__int128 *)v140;
    v104 = 0;
    *(_QWORD *)&v120 = &v104;
    v26 = v127;
    if ( v128 > 0xF )
      v26 = (_QWORD *)v127[0];
    v27 = operator new(0x190u);
    *(_QWORD *)v106 = v27 + 14;
    v27[43] = v23;
    v27[44] = v26;
    v27[45] = v104;
    v104 = 0;
    v27[46] = v25;
    *((_DWORD *)v27 + 94) = 34;
    *((_DWORD *)v27 + 95) = 1;
    v27[48] = v24;
    v27[14] = wil::ProfileDataStore::GetCollectionItemsAsync__ResumeCoro_1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_;
    *((_DWORD *)v27 + 30) = 65538;
    memset_0(v27, 0, 0x68u);
    *(_QWORD *)&v125 = v27;
    *((_BYTE *)v27 + 336) = 0;
    wil::ProfileDataStore::GetCollectionItemsAsync__ResumeCoro_1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_(v27 + 14);
    v28 = v104;
    if ( v104 && _InterlockedExchangeAdd(v104 + 2, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
    v104 = 0;
    v29 = wil::details::coro::task_base<wil::GetCollectionItemIdsResult<Windows::Data::Security::Passkey::PasskeyItemPdr>>::get(
            &v125,
            &v129);
    if ( &v133 != (__int128 *)v29 )
    {
      std::vector<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::_Tidy(&v133);
      v133 = *(_OWORD *)v29;
      v134 = *(_QWORD *)(v29 + 16);
      *(_QWORD *)v29 = 0;
      *(_QWORD *)(v29 + 8) = 0;
      *(_QWORD *)(v29 + 16) = 0;
    }
    std::wstring::operator=(&v135, v29 + 24);
    v30 = *(_DWORD *)(v29 + 56);
    v138 = v30;
    v139 = *(_QWORD *)(v29 + 64);
    std::wstring::~wstring((char *)&v130 + 8, v31, v32);
    std::vector<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::_Tidy(&v129);
    v35 = v125;
    if ( (_QWORD)v125 && _InterlockedExchange64((volatile __int64 *)(v125 + 8), 2) )
    {
      *(_QWORD *)(v35 + 120) |= 1uLL;
      (*(void (__fastcall **)(__int64))(v35 + 112))(v35 + 112);
    }
    if ( v30 < 0 && (unsigned int)dword_180075000 > 4 )
    {
      *(_QWORD *)&v125 = "ProfileDataStore::GetCollectionItemIdsAsync";
      v36 = (volatile signed __int32 *)v127;
      if ( v128 > 0xF )
        v36 = (volatile signed __int32 *)v127[0];
      v104 = v36;
      v106[0] = v30;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v35,
        (unsigned int)&dword_180068C54,
        v33,
        v34,
        (__int64)v106,
        (__int64)&v104,
        (__int64)&v125);
    }
    v37 = (_QWORD *)v133;
    v38 = v107;
    while ( v37 != *((_QWORD **)&v133 + 1) )
    {
      v125 = 0;
      v39 = v37[1];
      if ( v39 )
        _InterlockedIncrement((volatile signed __int32 *)(v39 + 8));
      v125 = *(_OWORD *)v37;
      *(_QWORD *)&v120 = &v125;
      v40 = *((_QWORD *)v38 + 7);
      if ( !v40 )
      {
        std::_Xbad_function_call();
        goto LABEL_57;
      }
      (*(void (__fastcall **)(__int64, __int128 *, __int128 *))(*(_QWORD *)v40 + 16LL))(v40, &v122, &v125);
      v41 = v18 | 8;
      v42 = (volatile signed __int32 *)*((_QWORD *)&v125 + 1);
      if ( *((_QWORD *)&v125 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v125 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v42)(v42);
          if ( _InterlockedExchangeAdd(v42 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v42 + 8LL))(v42);
        }
      }
      v43 = *v37;
      std::wstring::wstring(v148, *v37 + 88LL);
      std::wstring::wstring(v149, v43 + 120);
      std::wstring::wstring(v150, v43 + 152);
      std::wstring::wstring(&v120, v148);
      v44 = v41 | 0x30;
      v129 = v120;
      v130 = v121;
      *(_QWORD *)&v121 = 0;
      *((_QWORD *)&v121 + 1) = 7;
      LOWORD(v120) = 0;
      v45 = v123;
      v123 = 0;
      v46 = *((_QWORD *)&v122 + 1);
      v47 = v122;
      v122 = 0u;
      *(_QWORD *)&v131 = v47;
      *((_QWORD *)&v131 + 1) = v46;
      *(_QWORD *)&v132 = v45;
      std::_Tree<std::_Tmap_traits<std::wstring,std::vector<unsigned char>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::vector<unsigned char>>>,0>>::insert<0,0>(
        &v112,
        v119,
        &v129);
      std::vector<unsigned char>::~vector<unsigned char>(&v131);
      std::wstring::~wstring(&v129, v48, v49);
      std::wstring::~wstring(&v120, v50, v51);
      std::wstring::~wstring(v150, v52, v53);
      std::wstring::~wstring(v149, v54, v55);
      std::wstring::~wstring(v148, v56, v57);
      v58 = *v37 + 88LL;
      v29 = *v37 + 120LL;
      v59 = *v37 + 152LL;
      if ( (*(_BYTE *)(*v37 + 240LL) & 2) != 0 )
      {
        std::wstring::wstring(v148, v58);
        std::wstring::wstring(v149, v29);
        std::wstring::wstring(v150, v59);
        std::wstring::wstring(&v120, v148);
        v18 = v44 | 0xC0;
        v61 = *((_QWORD *)&v108 + 1);
        if ( *((_QWORD *)&v108 + 1) == v109 )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v108, *((_QWORD *)&v108 + 1), &v120);
        }
        else
        {
          **((_OWORD **)&v108 + 1) = v120;
          *(_OWORD *)(v61 + 16) = v121;
          *(_QWORD *)&v121 = 0;
          *((_QWORD *)&v121 + 1) = 7;
          LOWORD(v120) = 0;
          *((_QWORD *)&v108 + 1) += 32LL;
        }
        std::wstring::~wstring(&v120, v61, v60);
      }
      else
      {
        std::wstring::wstring(v148, v58);
        std::wstring::wstring(v149, v29);
        std::wstring::wstring(v150, v59);
        std::wstring::wstring(&v125, v148);
        std::wstring::wstring(&v120, *v37 + 184LL);
        v18 = v44 | 0x700;
        v129 = v125;
        v130 = v126;
        *(_QWORD *)&v126 = 0;
        *((_QWORD *)&v126 + 1) = 7;
        LOWORD(v125) = 0;
        v131 = v120;
        v132 = v121;
        *(_QWORD *)&v121 = 0;
        *((_QWORD *)&v121 + 1) = 7;
        LOWORD(v120) = 0;
        std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::insert<0,0>(
          &v110,
          &v143,
          &v129);
        std::wstring::~wstring(&v131, v64, v65);
        std::wstring::~wstring(&v129, v66, v67);
        std::wstring::~wstring(&v120, v68, v69);
        std::wstring::~wstring(&v125, v70, v71);
      }
      std::wstring::~wstring(v150, v62, v63);
      std::wstring::~wstring(v149, v72, v73);
      std::wstring::~wstring(v148, v74, v75);
      std::vector<unsigned char>::~vector<unsigned char>(&v122);
      v37 += 2;
    }
    std::wstring::wstring(&v122, &v135);
    v18 |= 0x800u;
    std::wstring::operator=(&v146, &v122);
    std::wstring::~wstring(&v122, v76, v77);
    LODWORD(v29) = 0x80000000;
    if ( v138 >= 0 && v138 != 1638704 && !v139 )
    {
      v8 = v116;
      continue;
    }
    break;
  }
LABEL_57:
  if ( v30 >= 0 )
  {
    v122 = 0;
    v123 = 0;
    v124 = 0;
    std::string::_Construct<1,char const *>(&v122, *v114, v114[1]);
    v84 = &v122;
    if ( v124 > 0xF )
      v84 = (__int128 *)v122;
    v85 = WebAuthNWriteEventCloudStoreOperationSuccess(4, *v115, &String1, v84);
    if ( v85 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x31B,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\pdr\\lib\\pdrsyncstore.cpp",
        (const char *)(unsigned int)v85,
        v103);
    std::string::~string(&v122);
    goto LABEL_74;
  }
  if ( (unsigned int)dword_180075000 > 4 )
  {
    v107 = "ProfileDataStore::GetCollectionItemsAsync";
    v81 = v127;
    if ( v128 > 0xF )
      v81 = (_QWORD *)v127[0];
    *(_QWORD *)&v125 = v81;
    v106[0] = v30;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v78,
      (unsigned int)&unk_180068B98,
      v79,
      v80,
      (__int64)v106,
      (__int64)&v125,
      (__int64)&v107);
  }
  v122 = 0;
  v123 = 0;
  v124 = 0;
  std::string::_Construct<1,char const *>(&v122, *v114, v114[1]);
  v82 = &v122;
  if ( v124 > 0xF )
    v82 = (__int128 *)v122;
  v83 = WebAuthNWriteEventCloudStoreOperationFailure(4, *v115, &String1, v82);
  if ( v83 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x313,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\pdr\\lib\\pdrsyncstore.cpp",
      (const char *)(unsigned int)v83,
      v30);
  std::string::~string(&v122);
  if ( ((v30 + (_DWORD)v29) & (unsigned int)v29) != 0 || v30 == -2145844944 )
LABEL_74:
    v30 = 0;
  v86 = v117;
  *v117 = v30;
  v86[1] = 0;
  *((_QWORD *)v86 + 1) = 0;
  *((_QWORD *)v86 + 2) = 0;
  v87 = operator new(0x58u);
  *v87 = v87;
  v87[1] = v87;
  v87[2] = v87;
  *((_WORD *)v87 + 12) = 257;
  *((_QWORD *)v86 + 1) = v112;
  v112 = v87;
  v88 = *((_QWORD *)v86 + 2);
  *((_QWORD *)v86 + 2) = v113;
  v113 = v88;
  std::wstring::wstring(v86 + 6, &v135);
  v89 = v109;
  v109 = 0;
  v90 = v108;
  v108 = 0u;
  *(_OWORD *)(v86 + 14) = v90;
  *((_QWORD *)v86 + 9) = v89;
  *((_QWORD *)v86 + 10) = 0;
  *((_QWORD *)v86 + 11) = 0;
  v91 = operator new(0x60u);
  *v91 = v91;
  v91[1] = v91;
  v91[2] = v91;
  *((_WORD *)v91 + 12) = 257;
  *((_QWORD *)v86 + 10) = v110;
  v110 = v91;
  v92 = *((_QWORD *)v86 + 11);
  *((_QWORD *)v86 + 11) = v111;
  v111 = v92;
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v110);
  std::vector<std::wstring>::_Tidy(&v108);
  std::_Tree<std::_Tmap_traits<std::wstring,std::vector<unsigned char>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::vector<unsigned char>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::vector<unsigned char>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::vector<unsigned char>>>,0>>(&v112);
  std::wstring::~wstring(&v146, v93, v94);
  std::wstring::~wstring(&v135, v95, v96);
  std::vector<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::_Tidy(&v133);
  std::wstring::~wstring(&v140, v97, v98);
  std::string::~string(v127);
  v99 = (volatile signed __int32 *)v116[1];
  if ( v99 )
  {
    if ( _InterlockedExchangeAdd(v99 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v99)(v99);
      if ( _InterlockedExchangeAdd(v99 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v99 + 8LL))(v99);
    }
  }
  v100 = (const char *)*((_QWORD *)v38 + 7);
  if ( v100 )
  {
    v101 = *(_QWORD *)v100;
    LOBYTE(v101) = v100 != v38;
    (*(void (__fastcall **)(const char *, __int64))(*(_QWORD *)v100 + 32LL))(v100, v101);
    *((_QWORD *)v38 + 7) = 0;
  }
  return v86;
}

```

## disassembly

```asm
0x180036cb0  push    rbp
0x180036cb2  push    rbx
0x180036cb3  push    rsi
0x180036cb4  push    rdi
0x180036cb5  push    r12
0x180036cb7  push    r13
0x180036cb9  push    r14
0x180036cbb  push    r15
0x180036cbd  lea     rbp, [rsp-208h]
0x180036cc5  sub     rsp, 308h
0x180036ccc  mov     rax, cs:__security_cookie
0x180036cd3  xor     rax, rsp
0x180036cd6  mov     [rbp+240h+var_50], rax
0x180036cdd  mov     rdi, r9
0x180036ce0  mov     [rbp+240h+var_2A0], r8
0x180036ce4  mov     rsi, rdx
0x180036ce7  mov     [rbp+240h+var_298], rdx
0x180036ceb  mov     [rbp+240h+var_290], rcx
0x180036cef  mov     [rbp+240h+var_270], rcx
0x180036cf3  mov     [rbp+240h+var_268], rdx
0x180036cf7  mov     rcx, [rbp+240h+arg_20]
0x180036cfe  mov     [rbp+240h+var_2A8], rcx
0x180036d02  mov     rbx, [rbp+240h+arg_28]
0x180036d09  mov     rax, [rbp+240h+arg_30]
0x180036d10  mov     [rsp+340h+var_2E8], rax
0x180036d15  mov     [rbp+240h+var_260], rax
0x180036d19  xor     r14d, r14d
0x180036d1c  mov     [rsp+340h+var_2F8], r14d
0x180036d21  mov     rcx, [rcx]
0x180036d24  or      rax, 0FFFFFFFFFFFFFFFFh
0x180036d28  inc     rax
0x180036d2b  cmp     [rcx+rax], r14b
0x180036d2f  jnz     short loc_180036D28
0x180036d31  mov     qword ptr [rbp+240h+var_240], rcx
0x180036d35  mov     qword ptr [rbp+240h+var_240+8], rax
0x180036d39  lea     rdx, [rbp+240h+var_240]
0x180036d3d  lea     rcx, [rbp+240h+var_1E0]
0x180036d41  call    ?ExtendCorrelationVector@FidoUtils@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_zstring_view@D@wil@@@Z; FidoUtils::ExtendCorrelationVector(wil::basic_zstring_view<char>)
0x180036d46  nop
0x180036d47  mov     eax, cs:dword_180075000
0x180036d4d  cmp     eax, 4
0x180036d50  jbe     short loc_180036D79
0x180036d52  lea     rax, [rbp+240h+var_1E0]
0x180036d56  cmp     [rbp+240h+var_1C8], 0Fh
0x180036d5b  cmova   rax, [rbp+240h+var_1E0]
0x180036d60  mov     qword ptr [rbp+240h+var_200], rax
0x180036d64  lea     rax, [rbp+240h+var_200]
0x180036d68  mov     qword ptr [rsp+340h+var_320], rax
0x180036d6d  lea     rdx, word_180068C0A
0x180036d74  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180036d79  xorps   xmm0, xmm0
0x180036d7c  movups  [rbp+240h+var_120], xmm0
0x180036d83  mov     [rbp+240h+var_110], r14
0x180036d8a  mov     [rbp+240h+var_108], r14
0x180036d91  mov     r8, [rdi+8]
0x180036d95  mov     rdx, [rdi]
0x180036d98  lea     rcx, [rbp+240h+var_120]
0x180036d9f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180036da4  nop
0x180036da5  xorps   xmm0, xmm0
0x180036da8  movdqa  [rbp+240h+var_170], xmm0
0x180036db0  mov     [rbp+240h+var_160], r14
0x180036db7  xorps   xmm1, xmm1
0x180036dba  movups  [rbp+240h+var_158], xmm1
0x180036dc1  mov     [rbp+240h+var_148], r14
0x180036dc8  mov     [rbp+240h+var_140], 7
0x180036dd3  mov     word ptr [rbp+240h+var_158], r14w
0x180036ddb  mov     [rbp+240h+var_138], r14d
0x180036de2  mov     [rbp+240h+var_130], r14
0x180036de9  mov     r8, [rbx+8]
0x180036ded  test    r8, r8
0x180036df0  jnz     short loc_180036E29
0x180036df2  movups  [rbp+240h+var_100], xmm0
0x180036df9  mov     [rbp+240h+var_F0], r14
0x180036e00  mov     [rbp+240h+var_E8], r14
0x180036e07  lea     rdx, String1
0x180036e0e  lea     rcx, [rbp+240h+var_100]
0x180036e15  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180036e1a  lea     rcx, [rbp+240h+var_100]
0x180036e21  mov     r13d, 1
0x180036e27  jmp     short loc_180036E4B
0x180036e29  movups  [rbp+240h+var_220], xmm0
0x180036e2d  mov     [rbp+240h+var_210], r14
0x180036e31  mov     [rbp+240h+var_208], r14
0x180036e35  mov     rdx, [rbx]
0x180036e38  lea     rcx, [rbp+240h+var_220]
0x180036e3c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180036e41  lea     rcx, [rbp+240h+var_220]
0x180036e45  mov     r13d, 2
0x180036e4b  movups  xmm0, xmmword ptr [rcx]
0x180036e4e  movups  [rbp+240h+var_E0], xmm0
0x180036e55  movups  xmm1, xmmword ptr [rcx+10h]
0x180036e59  movups  [rbp+240h+var_D0], xmm1
0x180036e60  mov     [rcx+10h], r14
0x180036e64  mov     qword ptr [rcx+18h], 7
0x180036e6c  mov     [rcx], r14w
0x180036e70  test    r13b, 2
0x180036e74  jz      short loc_180036E84
0x180036e76  and     r13d, 0FFFFFFFDh
0x180036e7a  lea     rcx, [rbp+240h+var_220]
0x180036e7e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180036e83  nop
0x180036e84  test    r13b, 1
0x180036e88  jz      short loc_180036E9A
0x180036e8a  and     r13d, 0FFFFFFFEh
0x180036e8e  lea     rcx, [rbp+240h+var_100]
0x180036e95  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180036e9a  mov     [rbp+240h+var_2B8], r14
0x180036e9e  mov     [rbp+240h+var_2B0], r14
0x180036ea2  mov     ecx, 58h ; 'X'; Size
0x180036ea7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180036eac  mov     [rax], rax
0x180036eaf  mov     [rax+8], rax
0x180036eb3  mov     [rax+10h], rax
0x180036eb7  mov     word ptr [rax+18h], 101h
0x180036ebd  mov     [rbp+240h+var_2B8], rax
0x180036ec1  xorps   xmm0, xmm0
0x180036ec4  movdqu  [rsp+340h+var_2E0], xmm0
0x180036eca  mov     [rsp+340h+var_2D0], r14
0x180036ecf  mov     [rsp+340h+var_2C8], r14
0x180036ed4  mov     [rbp+240h+var_2C0], r14
0x180036ed8  mov     ecx, 60h ; '`'; Size
0x180036edd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180036ee2  mov     [rax], rax
0x180036ee5  mov     [rax+8], rax
0x180036ee9  mov     [rax+10h], rax
0x180036eed  mov     word ptr [rax+18h], 101h
0x180036ef3  mov     [rsp+340h+var_2C8], rax
0x180036ef8  mov     rcx, [rbp+240h+var_1D0]
0x180036efc  lea     rax, [rbp+240h+var_1E0]
0x180036f00  cmp     [rbp+240h+var_1C8], 0Fh
0x180036f05  cmova   rax, [rbp+240h+var_1E0]
0x180036f0a  mov     [rbp+240h+var_280], rax
0x180036f0e  mov     [rbp+240h+var_278], rcx
0x180036f12  lea     rdx, [rbp+240h+var_280]
0x180036f16  lea     rcx, [rbp+240h+var_220]
0x180036f1a  call    ?IncrementCorrelationVector@FidoUtils@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_zstring_view@D@wil@@@Z; FidoUtils::IncrementCorrelationVector(wil::basic_zstring_view<char>)
0x180036f1f  mov     rdx, rax
0x180036f22  lea     rcx, [rbp+240h+var_1E0]
0x180036f26  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180036f2b  lea     rcx, [rbp+240h+var_220]
0x180036f2f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180036f34  mov     r15, [rsi]
0x180036f37  lea     r12, [rbp+240h+var_E0]
0x180036f3e  cmp     qword ptr [rbp+240h+var_D0+8], 7
0x180036f46  cmova   r12, qword ptr [rbp+240h+var_E0]
0x180036f4e  lea     rsi, [rbp+240h+var_120]
0x180036f55  cmp     [rbp+240h+var_108], 7
0x180036f5d  cmova   rsi, qword ptr [rbp+240h+var_120]
0x180036f65  mov     [rsp+340h+var_300], r14
0x180036f6a  lea     rax, [rsp+340h+var_300]
0x180036f6f  mov     qword ptr [rbp+240h+var_240], rax
0x180036f73  lea     rbx, [rbp+240h+var_1E0]
0x180036f77  cmp     [rbp+240h+var_1C8], 0Fh
0x180036f7c  cmova   rbx, [rbp+240h+var_1E0]
0x180036f81  mov     ecx, 190h; Size
0x180036f86  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180036f8b  mov     rdi, rax
0x180036f8e  mov     qword ptr [rsp+340h+var_2F0], rax
0x180036f93  lea     r14, [rax+70h]
0x180036f97  mov     qword ptr [rsp+340h+var_2F0], r14
0x180036f9c  mov     [r14+0E8h], r15
0x180036fa3  mov     [r14+0F0h], rbx
0x180036faa  mov     rax, [rsp+340h+var_300]
0x180036faf  mov     [r14+0F8h], rax
0x180036fb6  mov     [rsp+340h+var_300], 0
0x180036fbf  mov     [r14+100h], rsi
0x180036fc6  mov     dword ptr [r14+108h], 22h ; '"'
0x180036fd1  mov     dword ptr [r14+10Ch], 1
0x180036fdc  mov     [r14+110h], r12
0x180036fe3  lea     rax, wil__ProfileDataStore__GetCollectionItemsAsync$_ResumeCoro$1_Windows__Data__Security__Passkey__ScenarioKeysItemPdr_
0x180036fea  mov     [r14], rax
0x180036fed  mov     dword ptr [r14+8], 10002h
0x180036ff5  xor     edx, edx; Val
0x180036ff7  lea     r8d, [rdx+68h]; Size
0x180036ffb  mov     rcx, rdi; void *
0x180036ffe  call    memset_0
0x180037003  nop
0x180037004  mov     qword ptr [rbp+240h+var_200], rdi
0x180037008  xor     eax, eax
0x18003700a  mov     [r14+0E0h], al
0x180037011  mov     rcx, r14
0x180037014  call    wil__ProfileDataStore__GetCollectionItemsAsync$_ResumeCoro$1_Windows__Data__Security__Passkey__ScenarioKeysItemPdr_
0x180037019  nop
0x18003701a  mov     rcx, [rsp+340h+var_300]
0x18003701f  xor     r12d, r12d
0x180037022  test    rcx, rcx
0x180037025  jz      short loc_180037040
0x180037027  or      eax, 0FFFFFFFFh
0x18003702a  lock xadd [rcx+8], eax
0x18003702f  cmp     eax, 1
0x180037032  jnz     short loc_180037040
0x180037034  mov     rax, [rcx]
0x180037037  mov     rax, [rax+8]
0x18003703b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037040  mov     [rsp+340h+var_300], r12
0x180037045  lea     rdx, [rbp+240h+var_1C0]
0x18003704c  lea     rcx, [rbp+240h+var_200]
0x180037050  call    ?get@?$task_base@V?$GetCollectionItemIdsResult@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@coro@details@wil@@QEHAA@XZ; wil::details::coro::task_base<wil::GetCollectionItemIdsResult<Windows::Data::Security::Passkey::PasskeyItemPdr>>::get(void)
0x180037055  mov     rbx, rax
0x180037058  lea     rax, [rbp+240h+var_170]
0x18003705f  cmp     rax, rbx
0x180037062  jz      short loc_18003709B
0x180037064  lea     rcx, [rbp+240h+var_170]
0x18003706b  call    ?_Tidy@?$vector@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@V?$allocator@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::_Tidy(void)
0x180037070  mov     rax, [rbx]
0x180037073  mov     qword ptr [rbp+240h+var_170], rax
0x18003707a  mov     rax, [rbx+8]
0x18003707e  mov     qword ptr [rbp+240h+var_170+8], rax
0x180037085  mov     rax, [rbx+10h]
0x180037089  mov     [rbp+240h+var_160], rax
0x180037090  mov     [rbx], r12
0x180037093  mov     [rbx+8], r12
0x180037097  mov     [rbx+10h], r12
0x18003709b  lea     rdx, [rbx+18h]
0x18003709f  lea     rcx, [rbp+240h+var_158]
0x1800370a6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800370ab  mov     esi, [rbx+38h]
0x1800370ae  mov     [rbp+240h+var_138], esi
0x1800370b4  mov     rax, [rbx+40h]
0x1800370b8  mov     [rbp+240h+var_130], rax
0x1800370bf  lea     rcx, [rbp+240h+var_1B0+8]
0x1800370c6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800370cb  lea     rcx, [rbp+240h+var_1C0]
0x1800370d2  call    ?_Tidy@?$vector@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@V?$allocator@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::_Tidy(void)
0x1800370d7  nop
0x1800370d8  mov     rcx, qword ptr [rbp+240h+var_200]
0x1800370dc  test    rcx, rcx
0x1800370df  jz      short loc_180037103
0x1800370e1  mov     eax, 2
0x1800370e6  xchg    rax, [rcx+8]
0x1800370ea  test    rax, rax
0x1800370ed  jz      short loc_180037103
0x1800370ef  lea     rax, [rcx+70h]
0x1800370f3  or      qword ptr [rax+8], 1
0x1800370f8  mov     rcx, rax
0x1800370fb  mov     rax, [rax]
0x1800370fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037103  test    esi, esi
0x180037105  jns     short loc_18003715D
0x180037107  mov     eax, cs:dword_180075000
0x18003710d  cmp     eax, 4
0x180037110  jbe     short loc_18003715D
0x180037112  lea     rax, aProfiledatasto_3; "ProfileDataStore::GetCollectionItemIdsA"...
0x180037119  mov     qword ptr [rbp+240h+var_200], rax
0x18003711d  lea     rax, [rbp+240h+var_1E0]
0x180037121  cmp     [rbp+240h+var_1C8], 0Fh
0x180037126  cmova   rax, [rbp+240h+var_1E0]
0x18003712b  mov     [rsp+340h+var_300], rax
0x180037130  mov     [rsp+340h+var_2F0], esi
0x180037134  lea     rax, [rbp+240h+var_200]
0x180037138  mov     [rsp+340h+var_310], rax
0x18003713d  lea     rax, [rsp+340h+var_300]
0x180037142  mov     [rsp+340h+var_318], rax
0x180037147  lea     rax, [rsp+340h+var_2F0]
0x18003714c  mov     qword ptr [rsp+340h+var_320], rax; int
0x180037151  lea     rdx, dword_180068C54
0x180037158  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18003715d  mov     rdi, qword ptr [rbp+240h+var_170]
0x180037164  mov     r14, [rsp+340h+var_2E8]
0x180037169  cmp     rdi, qword ptr [rbp+240h+var_170+8]
0x180037170  jz      loc_18003757F
0x180037176  xorps   xmm0, xmm0
0x180037179  movdqu  [rbp+240h+var_200], xmm0
0x18003717e  mov     rax, [rdi+8]
0x180037182  test    rax, rax
0x180037185  jz      short loc_18003718B
0x180037187  lock inc dword ptr [rax+8]
0x18003718b  mov     rax, [rdi]
0x18003718e  mov     qword ptr [rbp+240h+var_200], rax
0x180037192  mov     rax, [rdi+8]
0x180037196  mov     qword ptr [rbp+240h+var_200+8], rax
0x18003719a  lea     rax, [rbp+240h+var_200]
0x18003719e  mov     qword ptr [rbp+240h+var_240], rax
0x1800371a2  mov     rcx, [r14+38h]
0x1800371a6  test    rcx, rcx
0x1800371a9  jz      loc_1800375DB
0x1800371af  mov     rax, [rcx]
0x1800371b2  lea     r8, [rbp+240h+var_200]
0x1800371b6  lea     rdx, [rbp+240h+var_220]
0x1800371ba  mov     rax, [rax+10h]
0x1800371be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800371c3  or      r13d, 8
0x1800371c7  mov     rbx, qword ptr [rbp+240h+var_200+8]
0x1800371cb  test    rbx, rbx
0x1800371ce  jz      short loc_180037208
0x1800371d0  or      eax, 0FFFFFFFFh
0x1800371d3  lock xadd [rbx+8], eax
0x1800371d8  cmp     eax, 1
0x1800371db  jnz     short loc_180037208
0x1800371dd  mov     rax, [rbx]
0x1800371e0  mov     rcx, rbx
0x1800371e3  mov     rax, [rax]
0x1800371e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800371eb  or      eax, 0FFFFFFFFh
0x1800371ee  lock xadd [rbx+0Ch], eax
0x1800371f3  cmp     eax, 1
0x1800371f6  jnz     short loc_180037208
0x1800371f8  mov     rax, [rbx]
0x1800371fb  mov     rcx, rbx
  ... truncated ...
```
