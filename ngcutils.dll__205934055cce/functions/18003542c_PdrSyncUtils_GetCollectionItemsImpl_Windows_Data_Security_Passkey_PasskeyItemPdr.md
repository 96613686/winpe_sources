# PdrSyncUtils::GetCollectionItemsImpl_Windows::Data::Security::Passkey::PasskeyItemPdr_

- ea: `0x18003542c`
- end: `0x180036067`
- name: `PdrSyncUtils::GetCollectionItemsImpl_Windows::Data::Security::Passkey::PasskeyItemPdr_`
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
- `0x180034140`
- `0x18003542c`
- `0x180040d10`
- `0x180042448`
- `0x180042630`
- `0x18004eba0`
- `0x18004f554`
- `0x180054c40`
- `0x180054ecc`
- `0x180061010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180035d57`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180035d57`
- `webauthn!WebAuthNWriteEventCloudStoreOperationFailure` at `0x180035e03`
- `webauthn!WebAuthNWriteEventCloudStoreOperationFailure` at `0x180035e03`
- `webauthn!WebAuthNWriteEventCloudStoreOperationSuccess` at `0x180035e85`
- `webauthn!WebAuthNWriteEventCloudStoreOperationSuccess` at `0x180035e85`

## string_xrefs

- `0x180035e17`: `onecore\ds\security\ngc\utils\pdr\lib\pdrsyncstore.cpp`
- `0x180035e99`: `onecore\ds\security\ngc\utils\pdr\lib\pdrsyncstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=33
int *__fastcall PdrSyncUtils::GetCollectionItemsImpl_Windows::Data::Security::Passkey::PasskeyItemPdr_(
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
      (unsigned int)&word_180068E66,
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
    v27[14] = wil::ProfileDataStore::GetCollectionItemsAsync__ResumeCoro_1_Windows::Data::Security::Passkey::PasskeyItemPdr_;
    *((_DWORD *)v27 + 30) = 65538;
    memset_0(v27, 0, 0x68u);
    *(_QWORD *)&v125 = v27;
    *((_BYTE *)v27 + 336) = 0;
    wil::ProfileDataStore::GetCollectionItemsAsync__ResumeCoro_1_Windows::Data::Security::Passkey::PasskeyItemPdr_(v27 + 14);
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
        (unsigned int)&unk_180068EB0,
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
      (unsigned int)word_180068DAA,
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
0x18003542c  push    rbp
0x18003542e  push    rbx
0x18003542f  push    rsi
0x180035430  push    rdi
0x180035431  push    r12
0x180035433  push    r13
0x180035435  push    r14
0x180035437  push    r15
0x180035439  lea     rbp, [rsp-208h]
0x180035441  sub     rsp, 308h
0x180035448  mov     rax, cs:__security_cookie
0x18003544f  xor     rax, rsp
0x180035452  mov     [rbp+240h+var_50], rax
0x180035459  mov     rdi, r9
0x18003545c  mov     [rbp+240h+var_2A0], r8
0x180035460  mov     rsi, rdx
0x180035463  mov     [rbp+240h+var_298], rdx
0x180035467  mov     [rbp+240h+var_290], rcx
0x18003546b  mov     [rbp+240h+var_270], rcx
0x18003546f  mov     [rbp+240h+var_268], rdx
0x180035473  mov     rcx, [rbp+240h+arg_20]
0x18003547a  mov     [rbp+240h+var_2A8], rcx
0x18003547e  mov     rbx, [rbp+240h+arg_28]
0x180035485  mov     rax, [rbp+240h+arg_30]
0x18003548c  mov     [rsp+340h+var_2E8], rax
0x180035491  mov     [rbp+240h+var_260], rax
0x180035495  xor     r14d, r14d
0x180035498  mov     [rsp+340h+var_2F8], r14d
0x18003549d  mov     rcx, [rcx]
0x1800354a0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800354a4  inc     rax
0x1800354a7  cmp     [rcx+rax], r14b
0x1800354ab  jnz     short loc_1800354A4
0x1800354ad  mov     qword ptr [rbp+240h+var_240], rcx
0x1800354b1  mov     qword ptr [rbp+240h+var_240+8], rax
0x1800354b5  lea     rdx, [rbp+240h+var_240]
0x1800354b9  lea     rcx, [rbp+240h+var_1E0]
0x1800354bd  call    ?ExtendCorrelationVector@FidoUtils@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_zstring_view@D@wil@@@Z; FidoUtils::ExtendCorrelationVector(wil::basic_zstring_view<char>)
0x1800354c2  nop
0x1800354c3  mov     eax, cs:dword_180075000
0x1800354c9  cmp     eax, 4
0x1800354cc  jbe     short loc_1800354F5
0x1800354ce  lea     rax, [rbp+240h+var_1E0]
0x1800354d2  cmp     [rbp+240h+var_1C8], 0Fh
0x1800354d7  cmova   rax, [rbp+240h+var_1E0]
0x1800354dc  mov     qword ptr [rbp+240h+var_200], rax
0x1800354e0  lea     rax, [rbp+240h+var_200]
0x1800354e4  mov     qword ptr [rsp+340h+var_320], rax
0x1800354e9  lea     rdx, word_180068E66
0x1800354f0  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800354f5  xorps   xmm0, xmm0
0x1800354f8  movups  [rbp+240h+var_120], xmm0
0x1800354ff  mov     [rbp+240h+var_110], r14
0x180035506  mov     [rbp+240h+var_108], r14
0x18003550d  mov     r8, [rdi+8]
0x180035511  mov     rdx, [rdi]
0x180035514  lea     rcx, [rbp+240h+var_120]
0x18003551b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180035520  nop
0x180035521  xorps   xmm0, xmm0
0x180035524  movdqa  [rbp+240h+var_170], xmm0
0x18003552c  mov     [rbp+240h+var_160], r14
0x180035533  xorps   xmm1, xmm1
0x180035536  movups  [rbp+240h+var_158], xmm1
0x18003553d  mov     [rbp+240h+var_148], r14
0x180035544  mov     [rbp+240h+var_140], 7
0x18003554f  mov     word ptr [rbp+240h+var_158], r14w
0x180035557  mov     [rbp+240h+var_138], r14d
0x18003555e  mov     [rbp+240h+var_130], r14
0x180035565  mov     r8, [rbx+8]
0x180035569  test    r8, r8
0x18003556c  jnz     short loc_1800355A5
0x18003556e  movups  [rbp+240h+var_100], xmm0
0x180035575  mov     [rbp+240h+var_F0], r14
0x18003557c  mov     [rbp+240h+var_E8], r14
0x180035583  lea     rdx, String1
0x18003558a  lea     rcx, [rbp+240h+var_100]
0x180035591  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180035596  lea     rcx, [rbp+240h+var_100]
0x18003559d  mov     r13d, 1
0x1800355a3  jmp     short loc_1800355C7
0x1800355a5  movups  [rbp+240h+var_220], xmm0
0x1800355a9  mov     [rbp+240h+var_210], r14
0x1800355ad  mov     [rbp+240h+var_208], r14
0x1800355b1  mov     rdx, [rbx]
0x1800355b4  lea     rcx, [rbp+240h+var_220]
0x1800355b8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800355bd  lea     rcx, [rbp+240h+var_220]
0x1800355c1  mov     r13d, 2
0x1800355c7  movups  xmm0, xmmword ptr [rcx]
0x1800355ca  movups  [rbp+240h+var_E0], xmm0
0x1800355d1  movups  xmm1, xmmword ptr [rcx+10h]
0x1800355d5  movups  [rbp+240h+var_D0], xmm1
0x1800355dc  mov     [rcx+10h], r14
0x1800355e0  mov     qword ptr [rcx+18h], 7
0x1800355e8  mov     [rcx], r14w
0x1800355ec  test    r13b, 2
0x1800355f0  jz      short loc_180035600
0x1800355f2  and     r13d, 0FFFFFFFDh
0x1800355f6  lea     rcx, [rbp+240h+var_220]
0x1800355fa  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800355ff  nop
0x180035600  test    r13b, 1
0x180035604  jz      short loc_180035616
0x180035606  and     r13d, 0FFFFFFFEh
0x18003560a  lea     rcx, [rbp+240h+var_100]
0x180035611  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180035616  mov     [rbp+240h+var_2B8], r14
0x18003561a  mov     [rbp+240h+var_2B0], r14
0x18003561e  mov     ecx, 58h ; 'X'; Size
0x180035623  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180035628  mov     [rax], rax
0x18003562b  mov     [rax+8], rax
0x18003562f  mov     [rax+10h], rax
0x180035633  mov     word ptr [rax+18h], 101h
0x180035639  mov     [rbp+240h+var_2B8], rax
0x18003563d  xorps   xmm0, xmm0
0x180035640  movdqu  [rsp+340h+var_2E0], xmm0
0x180035646  mov     [rsp+340h+var_2D0], r14
0x18003564b  mov     [rsp+340h+var_2C8], r14
0x180035650  mov     [rbp+240h+var_2C0], r14
0x180035654  mov     ecx, 60h ; '`'; Size
0x180035659  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003565e  mov     [rax], rax
0x180035661  mov     [rax+8], rax
0x180035665  mov     [rax+10h], rax
0x180035669  mov     word ptr [rax+18h], 101h
0x18003566f  mov     [rsp+340h+var_2C8], rax
0x180035674  mov     rcx, [rbp+240h+var_1D0]
0x180035678  lea     rax, [rbp+240h+var_1E0]
0x18003567c  cmp     [rbp+240h+var_1C8], 0Fh
0x180035681  cmova   rax, [rbp+240h+var_1E0]
0x180035686  mov     [rbp+240h+var_280], rax
0x18003568a  mov     [rbp+240h+var_278], rcx
0x18003568e  lea     rdx, [rbp+240h+var_280]
0x180035692  lea     rcx, [rbp+240h+var_220]
0x180035696  call    ?IncrementCorrelationVector@FidoUtils@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_zstring_view@D@wil@@@Z; FidoUtils::IncrementCorrelationVector(wil::basic_zstring_view<char>)
0x18003569b  mov     rdx, rax
0x18003569e  lea     rcx, [rbp+240h+var_1E0]
0x1800356a2  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800356a7  lea     rcx, [rbp+240h+var_220]
0x1800356ab  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800356b0  mov     r15, [rsi]
0x1800356b3  lea     r12, [rbp+240h+var_E0]
0x1800356ba  cmp     qword ptr [rbp+240h+var_D0+8], 7
0x1800356c2  cmova   r12, qword ptr [rbp+240h+var_E0]
0x1800356ca  lea     rsi, [rbp+240h+var_120]
0x1800356d1  cmp     [rbp+240h+var_108], 7
0x1800356d9  cmova   rsi, qword ptr [rbp+240h+var_120]
0x1800356e1  mov     [rsp+340h+var_300], r14
0x1800356e6  lea     rax, [rsp+340h+var_300]
0x1800356eb  mov     qword ptr [rbp+240h+var_240], rax
0x1800356ef  lea     rbx, [rbp+240h+var_1E0]
0x1800356f3  cmp     [rbp+240h+var_1C8], 0Fh
0x1800356f8  cmova   rbx, [rbp+240h+var_1E0]
0x1800356fd  mov     ecx, 190h; Size
0x180035702  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180035707  mov     rdi, rax
0x18003570a  mov     qword ptr [rsp+340h+var_2F0], rax
0x18003570f  lea     r14, [rax+70h]
0x180035713  mov     qword ptr [rsp+340h+var_2F0], r14
0x180035718  mov     [r14+0E8h], r15
0x18003571f  mov     [r14+0F0h], rbx
0x180035726  mov     rax, [rsp+340h+var_300]
0x18003572b  mov     [r14+0F8h], rax
0x180035732  mov     [rsp+340h+var_300], 0
0x18003573b  mov     [r14+100h], rsi
0x180035742  mov     dword ptr [r14+108h], 22h ; '"'
0x18003574d  mov     dword ptr [r14+10Ch], 1
0x180035758  mov     [r14+110h], r12
0x18003575f  lea     rax, wil__ProfileDataStore__GetCollectionItemsAsync$_ResumeCoro$1_Windows__Data__Security__Passkey__PasskeyItemPdr_
0x180035766  mov     [r14], rax
0x180035769  mov     dword ptr [r14+8], 10002h
0x180035771  xor     edx, edx; Val
0x180035773  lea     r8d, [rdx+68h]; Size
0x180035777  mov     rcx, rdi; void *
0x18003577a  call    memset_0
0x18003577f  nop
0x180035780  mov     qword ptr [rbp+240h+var_200], rdi
0x180035784  xor     eax, eax
0x180035786  mov     [r14+0E0h], al
0x18003578d  mov     rcx, r14
0x180035790  call    wil__ProfileDataStore__GetCollectionItemsAsync$_ResumeCoro$1_Windows__Data__Security__Passkey__PasskeyItemPdr_
0x180035795  nop
0x180035796  mov     rcx, [rsp+340h+var_300]
0x18003579b  xor     r12d, r12d
0x18003579e  test    rcx, rcx
0x1800357a1  jz      short loc_1800357BC
0x1800357a3  or      eax, 0FFFFFFFFh
0x1800357a6  lock xadd [rcx+8], eax
0x1800357ab  cmp     eax, 1
0x1800357ae  jnz     short loc_1800357BC
0x1800357b0  mov     rax, [rcx]
0x1800357b3  mov     rax, [rax+8]
0x1800357b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800357bc  mov     [rsp+340h+var_300], r12
0x1800357c1  lea     rdx, [rbp+240h+var_1C0]
0x1800357c8  lea     rcx, [rbp+240h+var_200]
0x1800357cc  call    ?get@?$task_base@V?$GetCollectionItemIdsResult@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@coro@details@wil@@QEHAA@XZ; wil::details::coro::task_base<wil::GetCollectionItemIdsResult<Windows::Data::Security::Passkey::PasskeyItemPdr>>::get(void)
0x1800357d1  mov     rbx, rax
0x1800357d4  lea     rax, [rbp+240h+var_170]
0x1800357db  cmp     rax, rbx
0x1800357de  jz      short loc_180035817
0x1800357e0  lea     rcx, [rbp+240h+var_170]
0x1800357e7  call    ?_Tidy@?$vector@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@V?$allocator@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::_Tidy(void)
0x1800357ec  mov     rax, [rbx]
0x1800357ef  mov     qword ptr [rbp+240h+var_170], rax
0x1800357f6  mov     rax, [rbx+8]
0x1800357fa  mov     qword ptr [rbp+240h+var_170+8], rax
0x180035801  mov     rax, [rbx+10h]
0x180035805  mov     [rbp+240h+var_160], rax
0x18003580c  mov     [rbx], r12
0x18003580f  mov     [rbx+8], r12
0x180035813  mov     [rbx+10h], r12
0x180035817  lea     rdx, [rbx+18h]
0x18003581b  lea     rcx, [rbp+240h+var_158]
0x180035822  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180035827  mov     esi, [rbx+38h]
0x18003582a  mov     [rbp+240h+var_138], esi
0x180035830  mov     rax, [rbx+40h]
0x180035834  mov     [rbp+240h+var_130], rax
0x18003583b  lea     rcx, [rbp+240h+var_1B0+8]
0x180035842  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180035847  lea     rcx, [rbp+240h+var_1C0]
0x18003584e  call    ?_Tidy@?$vector@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@V?$allocator@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::_Tidy(void)
0x180035853  nop
0x180035854  mov     rcx, qword ptr [rbp+240h+var_200]
0x180035858  test    rcx, rcx
0x18003585b  jz      short loc_18003587F
0x18003585d  mov     eax, 2
0x180035862  xchg    rax, [rcx+8]
0x180035866  test    rax, rax
0x180035869  jz      short loc_18003587F
0x18003586b  lea     rax, [rcx+70h]
0x18003586f  or      qword ptr [rax+8], 1
0x180035874  mov     rcx, rax
0x180035877  mov     rax, [rax]
0x18003587a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003587f  test    esi, esi
0x180035881  jns     short loc_1800358D9
0x180035883  mov     eax, cs:dword_180075000
0x180035889  cmp     eax, 4
0x18003588c  jbe     short loc_1800358D9
0x18003588e  lea     rax, aProfiledatasto_3; "ProfileDataStore::GetCollectionItemIdsA"...
0x180035895  mov     qword ptr [rbp+240h+var_200], rax
0x180035899  lea     rax, [rbp+240h+var_1E0]
0x18003589d  cmp     [rbp+240h+var_1C8], 0Fh
0x1800358a2  cmova   rax, [rbp+240h+var_1E0]
0x1800358a7  mov     [rsp+340h+var_300], rax
0x1800358ac  mov     [rsp+340h+var_2F0], esi
0x1800358b0  lea     rax, [rbp+240h+var_200]
0x1800358b4  mov     [rsp+340h+var_310], rax
0x1800358b9  lea     rax, [rsp+340h+var_300]
0x1800358be  mov     [rsp+340h+var_318], rax
0x1800358c3  lea     rax, [rsp+340h+var_2F0]
0x1800358c8  mov     qword ptr [rsp+340h+var_320], rax; int
0x1800358cd  lea     rdx, unk_180068EB0
0x1800358d4  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800358d9  mov     rdi, qword ptr [rbp+240h+var_170]
0x1800358e0  mov     r14, [rsp+340h+var_2E8]
0x1800358e5  cmp     rdi, qword ptr [rbp+240h+var_170+8]
0x1800358ec  jz      loc_180035CFB
0x1800358f2  xorps   xmm0, xmm0
0x1800358f5  movdqu  [rbp+240h+var_200], xmm0
0x1800358fa  mov     rax, [rdi+8]
0x1800358fe  test    rax, rax
0x180035901  jz      short loc_180035907
0x180035903  lock inc dword ptr [rax+8]
0x180035907  mov     rax, [rdi]
0x18003590a  mov     qword ptr [rbp+240h+var_200], rax
0x18003590e  mov     rax, [rdi+8]
0x180035912  mov     qword ptr [rbp+240h+var_200+8], rax
0x180035916  lea     rax, [rbp+240h+var_200]
0x18003591a  mov     qword ptr [rbp+240h+var_240], rax
0x18003591e  mov     rcx, [r14+38h]
0x180035922  test    rcx, rcx
0x180035925  jz      loc_180035D57
0x18003592b  mov     rax, [rcx]
0x18003592e  lea     r8, [rbp+240h+var_200]
0x180035932  lea     rdx, [rbp+240h+var_220]
0x180035936  mov     rax, [rax+10h]
0x18003593a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003593f  or      r13d, 8
0x180035943  mov     rbx, qword ptr [rbp+240h+var_200+8]
0x180035947  test    rbx, rbx
0x18003594a  jz      short loc_180035984
0x18003594c  or      eax, 0FFFFFFFFh
0x18003594f  lock xadd [rbx+8], eax
0x180035954  cmp     eax, 1
0x180035957  jnz     short loc_180035984
0x180035959  mov     rax, [rbx]
0x18003595c  mov     rcx, rbx
0x18003595f  mov     rax, [rax]
0x180035962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035967  or      eax, 0FFFFFFFFh
0x18003596a  lock xadd [rbx+0Ch], eax
0x18003596f  cmp     eax, 1
0x180035972  jnz     short loc_180035984
0x180035974  mov     rax, [rbx]
0x180035977  mov     rcx, rbx
  ... truncated ...
```
