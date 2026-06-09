# LPA::EsimManager::OnLpdProfileAvailableForInstall(_GUID const &,std::unique_ptr<LPA_PROFILE_AVAILABLE_FOR_INSTALL,void (*)(void *)> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> const &,ulong)

- ea: `0x18008f0a0`
- end: `0x18008f8bd`
- name: `?OnLpdProfileAvailableForInstall@EsimManager@LPA@@EEAAXAEBU_GUID@@AEBV?$unique_ptr@ULPA_PROFILE_AVAILABLE_FOR_INSTALL@@P6AXPEAX@Z@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@AEBV?$vector@EV?$allocator@E@std@@@5@3K@Z`
- size: `2077`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800018b4`
- `0x180003d5c`
- `0x180004a7c`
- `0x18000df90`
- `0x18005cd20`
- `0x1800602e0`
- `0x1800709e4`
- `0x180071840`
- `0x180071a8c`
- `0x180081678`
- `0x1800817c8`
- `0x18008215c`
- `0x180083a2c`
- `0x180083f60`
- `0x180084bbc`
- `0x180085904`
- `0x18008aee4`
- `0x18008b53c`
- `0x18008c370`
- `0x18008f0a0`
- `0x1800925e4`
- `0x180094190`
- `0x180094bb4`
- `0x180095fd0`
- `0x18009733c`
- `0x180101010`

## string_xrefs

- `0x18008f143`: `LpaServiceEsimManager`
- `0x18008f1b7`: `LpaServiceLpd`
- `0x18008f6ea`: `LpaServiceLpd`
- `0x18008f10d`: `LPA::EsimManager::OnLpdProfileAvailableForInstall`
- `0x18008f1fe`: `LPA::EsimManager::OnLpdProfileAvailableForInstall`
- `0x18008f6df`: `LPA::EsimManager::OnLpdProfileAvailableForInstall`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall LPA::EsimManager::OnLpdProfileAvailableForInstall(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        void *a4,
        __int64 a5,
        __int64 a6,
        int a7)
{
  BOOL v7; // esi
  int v10; // r12d
  int v11; // r14d
  _QWORD *v12; // r15
  int v13; // r8d
  int v14; // r9d
  __int64 v15; // rdi
  unsigned int v16; // r15d
  __int64 v17; // rax
  int v18; // r8d
  int v19; // r9d
  const char *v20; // rbx
  int v21; // r15d
  const struct LPA_ESIM_INFO *EsimInfo; // r11
  __int64 v23; // rax
  __int64 v24; // r14
  __int64 v25; // rcx
  __int64 v26; // rsi
  int v27; // r14d
  __int64 v28; // rax
  _QWORD *i; // rax
  __int64 v30; // rcx
  __int64 v31; // r12
  __int64 (__fastcall *v32)(__int64, const char *, __int64 *, __int64, __int64, int, int, _QWORD, const char **, int *); // r15
  int v33; // edx
  int v34; // r14d
  __int64 v35; // rsi
  __int64 v36; // rax
  int v37; // esi
  int v38; // eax
  __int64 *v39; // rsi
  __int64 v40; // rax
  __int64 (__fastcall ***v41)(_QWORD, const char *, __int64 *, __int64, int *); // r14
  __int64 (__fastcall *v42)(_QWORD, const char *, __int64 *, __int64, int *); // rsi
  __int64 v43; // rax
  int v44; // esi
  int v45; // eax
  __int64 *v46; // rsi
  __int64 v47; // rax
  __int64 v48; // rcx
  __int64 v49; // rsi
  int v50; // r14d
  __int64 v51; // r15
  int v52; // r14d
  __int64 v53; // rsi
  __int64 v54; // rax
  int v55; // ebx
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // [rsp+20h] [rbp-D1h]
  int v59; // [rsp+28h] [rbp-C9h]
  char v60; // [rsp+60h] [rbp-91h]
  int v61; // [rsp+64h] [rbp-8Dh] BYREF
  BOOL v62; // [rsp+68h] [rbp-89h]
  __int64 v63; // [rsp+70h] [rbp-81h] BYREF
  int v64; // [rsp+78h] [rbp-79h]
  unsigned int v65; // [rsp+7Ch] [rbp-75h] BYREF
  int v66; // [rsp+80h] [rbp-71h] BYREF
  void *v67[2]; // [rsp+88h] [rbp-69h] BYREF
  const char *v68; // [rsp+98h] [rbp-59h] BYREF
  char v69[8]; // [rsp+A0h] [rbp-51h] BYREF
  __int64 v70; // [rsp+A8h] [rbp-49h]
  const char *v71; // [rsp+B0h] [rbp-41h] BYREF
  std::_Ref_count_base *v72; // [rsp+B8h] [rbp-39h]
  const char *v73; // [rsp+C0h] [rbp-31h] BYREF
  std::_Ref_count_base *v74; // [rsp+C8h] [rbp-29h]
  const char *v75; // [rsp+D0h] [rbp-21h] BYREF
  std::_Ref_count_base *v76; // [rsp+D8h] [rbp-19h]

  v67[0] = a4;
  v70 = a3;
  v68 = (const char *)a2;
  v10 = 0;
  v64 = 0;
  LOBYTE(v7) = 0;
  v62 = v7;
  v60 = 0;
  v11 = -1;
  v61 = -1;
  v12 = (_QWORD *)(a1 + 184);
  std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<LPA::Lpd::DownloadInstance>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<LPA::Lpd::DownloadInstance>>>,0>>::find(
    a1 + 184,
    &v63,
    &a7);
  v15 = v63;
  if ( *v12 == v63 )
  {
    v16 = 0;
    v65 = 0;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v71 = (const char *)a2;
      v66 = a7;
      LODWORD(v63) = 0;
      v75 = "LPA::EsimManager::OnLpdProfileAvailableForInstall";
      v73 = "LpaServiceEsimManager";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
        (unsigned int)"LPA::EsimManager::OnLpdProfileAvailableForInstall",
        (unsigned int)&word_18012CFBE,
        v13,
        v14,
        (__int64)&v73,
        (__int64)&v75,
        (__int64)&v63,
        (__int64)&v66,
        (__int64)&v71);
    }
  }
  else
  {
    v17 = *(_QWORD *)(v63 + 40);
    v11 = *(_DWORD *)(v17 + 224);
    v61 = v11;
    v16 = *(_DWORD *)(v17 + 84);
    v65 = v16;
  }
  LPA::EsimManager::TryFindEsimRecordBySlotId(a1 - 56, &v73, &v61, a2);
  v20 = v73;
  if ( v73 == *(const char **)(a1 + 152) )
  {
    v21 = -2147023728;
    if ( (unsigned int)CallbackContext > 3 )
    {
      LODWORD(v63) = v11;
      v66 = a7;
      v65 = -2147023728;
      v73 = v68;
      v75 = "LPA::EsimManager::OnLpdProfileAvailableForInstall";
      v71 = "LpaServiceLpd";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)"LpaServiceLpd",
        (unsigned int)&dword_18012CF5C,
        v18,
        (_DWORD)v68,
        (__int64)&v71,
        (__int64)&v75,
        (__int64)&v73,
        (__int64)&v65,
        (__int64)&v66,
        (__int64)&v63);
    }
    goto LABEL_48;
  }
  EsimInfo = LPA::EsimManager::EsimRecord::GetEsimInfo(*((LPA::EsimManager::EsimRecord **)v73 + 6));
  if ( *(_QWORD *)(a1 + 184) == v15
    || (v23 = *(_QWORD *)(v15 + 40), v7 = *(_DWORD *)(v23 + 80) == 2, v62 = v7, *(_QWORD *)(a1 + 184) == v15) )
  {
    v24 = v70;
  }
  else
  {
    v24 = v70;
    if ( *(_DWORD *)(v23 + 80) == 10 && v16 == 2 )
    {
      StringCchCopyW((unsigned __int16 *)(a1 + 280), 0x15u, (const unsigned __int16 *)(*(_QWORD *)(v70 + 8) + 36LL));
      LOBYTE(v7) = 1;
      v62 = v7;
      v60 = 1;
    }
  }
  if ( !EsimInfo )
  {
    v21 = -2147418113;
    goto LABEL_48;
  }
  v21 = 0;
  if ( (*(_BYTE *)EsimInfo & 1) != 0 )
  {
    v21 = StringCchCopyW(
            (unsigned __int16 *)(*(_QWORD *)(v24 + 8) + 84LL),
            0x21u,
            (const unsigned __int16 *)EsimInfo + 2);
    if ( v21 >= 0 )
    {
      *(_DWORD *)(*(_QWORD *)(v24 + 8) + 28LL) |= 1u;
      *(_DWORD *)(*(_QWORD *)(v24 + 8) + 32LL) |= 4u;
      goto LABEL_18;
    }
LABEL_48:
    if ( v20 != *(const char **)(a1 + 152) )
    {
      if ( !v7 )
      {
        v61 = 0;
        v41 = *(__int64 (__fastcall ****)(_QWORD, const char *, __int64 *, __int64, int *))(a1 + 104);
        v42 = **v41;
        std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this(a1 + 32, &v73);
        v43 = std::weak_ptr<LPA::LpdCompletionHandler>::weak_ptr<LPA::LpdCompletionHandler>(v67);
        LODWORD(v63) = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v20 + 6) + 32LL) + 108LL);
        v44 = v42(v41, v68, &v63, v43, &v61);
        if ( v74 )
          std::_Ref_count_base::_Decref(v74);
        if ( v44 == -2147483638 )
        {
          LODWORD(v63) = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v20 + 6) + 32LL) + 108LL);
          v45 = std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this(a1 + 32, &v73);
          v46 = (__int64 *)std::make_unique<LPA::EsimManager::OperationEntry,std::shared_ptr<LPA::EsimManager>,unsigned long &,_GUID const &,unsigned long,0>(
                             (unsigned int)v67,
                             v45,
                             (unsigned int)&v61,
                             (_DWORD)v68,
                             (__int64)&v63);
          v47 = std::map<unsigned long,std::unique_ptr<LPA::EsimManager::OperationEntry>>::_Try_emplace<unsigned long const &,>(
                  a1 + 184,
                  &v75,
                  &v61);
          std::unique_ptr<LPA::EsimManager::OperationEntry>::operator=<std::default_delete<LPA::EsimManager::OperationEntry>,0>(
            (__int64 *)(*(_QWORD *)v47 + 40LL),
            v46);
          std::unique_ptr<LPA::EsimManager::OperationEntry>::~unique_ptr<LPA::EsimManager::OperationEntry>(v67);
          if ( v74 )
            std::_Ref_count_base::_Decref(v74);
        }
        LOBYTE(v7) = v62;
      }
      if ( (unsigned int)CallbackContext > 3 )
      {
        v48 = *(_QWORD *)(*((_QWORD *)v20 + 6) + 32LL);
        LODWORD(v63) = *(_DWORD *)(v48 + 108);
        v66 = v21;
        v67[0] = "LPA::EsimManager::OnLpdProfileAvailableForInstall";
        v73 = "LpaServiceLpd";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v48,
          (unsigned int)byte_18012CF1B,
          v18,
          v19,
          (__int64)&v73,
          (__int64)v67,
          (__int64)&v66,
          (__int64)&v63);
      }
    }
    goto LABEL_58;
  }
LABEL_18:
  v25 = *(_QWORD *)(*((_QWORD *)v20 + 6) + 256LL);
  if ( v25 )
  {
    v26 = v24 + 8;
    if ( !(unsigned __int8)LPA::EsimManager::EsimRecord::RulesAuthorizationTable::IsAllowedByPolicy(
                             v25,
                             v67[0],
                             a5,
                             a6,
                             *(_DWORD *)(*(_QWORD *)(v24 + 8) + 152LL),
                             (__int64)v69) )
    {
      v27 = 4;
LABEL_24:
      v64 = v27;
LABEL_35:
      *(_DWORD *)(*(_QWORD *)v26 + 28LL) |= 1u;
      *(_DWORD *)(*(_QWORD *)v26 + 32LL) |= 2u;
      *(_DWORD *)(*(_QWORD *)v26 + 80LL) = 6;
      *(_DWORD *)(*(_QWORD *)v26 + 4LL) |= 4u;
      *(_DWORD *)(*(_QWORD *)v26 + 12LL) = v27;
      goto LABEL_37;
    }
  }
  v26 = v24 + 8;
  v28 = *(_QWORD *)(v24 + 8);
  if ( (*(_BYTE *)(v28 + 28) & 4) != 0 && *(_DWORD *)(v28 + 156) == 2 )
  {
    v27 = 5;
    goto LABEL_24;
  }
  if ( (*(_BYTE *)(v28 + 28) & 2) != 0 && (*(_BYTE *)(v28 + 152) & 1) != 0 )
  {
    std::list<LPA_PROFILE_DETAILS const *>::list<LPA_PROFILE_DETAILS const *>(v67);
    LPA::EsimManager::EsimRecord::GetProfiles(*((LPA::EsimManager::EsimRecord **)v20 + 6));
    for ( i = *(_QWORD **)v67[0]; i != v67[0]; i = (_QWORD *)*i )
    {
      v30 = i[2];
      if ( (*(_BYTE *)(v30 + 4) & 4) != 0 && !*(_DWORD *)(v30 + 132) )
      {
        v27 = 3;
        v64 = 3;
        goto LABEL_34;
      }
    }
    v27 = v64;
LABEL_34:
    std::_List_node<PipeManager::PipeImplementation *,void *>::_Free_non_head<std::allocator<std::_List_node<PipeManager::PipeImplementation *,void *>>>();
    std::_Deallocate<16>(v67[0], (struct std::nothrow_t *)0x18);
    if ( v27 )
      goto LABEL_35;
  }
  else
  {
    v27 = 0;
  }
LABEL_37:
  LPA::EsimManager::EsimRecord::SetAvailableProfile(*((_QWORD *)v20 + 6), v70, v65);
  if ( !v62 )
  {
    if ( v27 )
    {
      v61 = 0;
      v73 = 0;
      LODWORD(v74) = 0;
      LPA::EsimManager::EsimRecord::SetOperationSubState(*((_QWORD *)v20 + 6), 5);
      v31 = *(_QWORD *)(a1 + 104);
      v32 = *(__int64 (__fastcall **)(__int64, const char *, __int64 *, __int64, __int64, int, int, _QWORD, const char **, int *))(*(_QWORD *)v31 + 8LL);
      v34 = 4 - (v27 != v33);
      v35 = *(_QWORD *)v26 + 36LL;
      std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this(a1 + 32, &v75);
      v36 = std::weak_ptr<LPA::LpdCompletionHandler>::weak_ptr<LPA::LpdCompletionHandler>(v67);
      LODWORD(v63) = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v20 + 6) + 32LL) + 108LL);
      LOBYTE(v59) = 0;
      v58 = v35;
      v37 = (int)v68;
      v21 = v32(v31, v68, &v63, v36, v58, v59, v34, 0, &v73, &v61);
      if ( v76 )
        std::_Ref_count_base::_Decref(v76);
      if ( v21 >= 0 )
      {
        LODWORD(v63) = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v20 + 6) + 32LL) + 108LL);
        v38 = std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this(a1 + 32, &v75);
        v39 = (__int64 *)std::make_unique<LPA::EsimManager::OperationEntry,std::shared_ptr<LPA::EsimManager>,unsigned long &,_GUID const &,unsigned long,0>(
                           (unsigned int)v67,
                           v38,
                           (unsigned int)&v61,
                           v37,
                           (__int64)&v63);
        v40 = std::map<unsigned long,std::unique_ptr<LPA::EsimManager::OperationEntry>>::_Try_emplace<unsigned long const &,>(
                a1 + 184,
                &v71,
                &v61);
        std::unique_ptr<LPA::EsimManager::OperationEntry>::operator=<std::default_delete<LPA::EsimManager::OperationEntry>,0>(
          (__int64 *)(*(_QWORD *)v40 + 40LL),
          v39);
        std::unique_ptr<LPA::EsimManager::OperationEntry>::~unique_ptr<LPA::EsimManager::OperationEntry>(v67);
        if ( v76 )
          std::_Ref_count_base::_Decref(v76);
      }
    }
    else
    {
      LPA::EsimManager::EsimRecord::SetOperationSubState(*((_QWORD *)v20 + 6), 2);
    }
  }
  LPA::EsimManager::ProcessAndBroadcastChanges((LPA::EsimManager *)(a1 - 56), 0);
  v10 = v64;
  LOBYTE(v7) = v62;
  if ( v21 < 0 )
    goto LABEL_48;
LABEL_58:
  if ( v7 && v20 != *(const char **)(a1 + 152) )
  {
    v49 = v70;
    if ( v60 )
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(a1 + 120) + 160LL))(
        *(_QWORD *)(a1 + 120),
        *(_QWORD *)(v70 + 8) + 36LL,
        *(unsigned int *)(*(_QWORD *)(v15 + 40) + 36LL));
    v65 = 0;
    v75 = 0;
    LODWORD(v76) = 0;
    v50 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(a1 + 120) + 176LL))(
            *(_QWORD *)(a1 + 120),
            *(_QWORD *)(v49 + 8) + 36LL,
            *(unsigned int *)(*(_QWORD *)(v15 + 40) + 36LL));
    v51 = *(_QWORD *)(a1 + 104);
    v67[0] = *(void **)(*(_QWORD *)v51 + 8LL);
    if ( v10 )
      v52 = 3;
    else
      v52 = (v50 >> 31) & 4;
    v53 = *(_QWORD *)(v49 + 8) + 36LL;
    std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this(a1 + 32, &v71);
    v54 = std::weak_ptr<LPA::LpdCompletionHandler>::weak_ptr<LPA::LpdCompletionHandler>(&v73);
    LODWORD(v63) = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v20 + 6) + 32LL) + 108LL);
    LOBYTE(v59) = v62;
    v55 = ((__int64 (__fastcall *)(__int64, const char *, __int64 *, __int64, __int64, int, int, _QWORD, const char **, unsigned int *))v67[0])(
            v51,
            v68,
            &v63,
            v54,
            v53,
            v59,
            v52,
            0,
            &v75,
            &v65);
    if ( v72 )
      std::_Ref_count_base::_Decref(v72);
    if ( v55 >= 0 )
    {
      v56 = *(_QWORD *)(v15 + 40);
      *(_QWORD *)(v15 + 40) = 0;
      v68 = (const char *)v56;
      std::_Tree<std::_Tmap_traits<unsigned long,std::unique_ptr<LPA::EsimManager::OperationEntry>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::unique_ptr<LPA::EsimManager::OperationEntry>>>,0>>::_Erase_unchecked(
        a1 + 184,
        v15);
      v57 = std::map<unsigned long,std::unique_ptr<LPA::EsimManager::OperationEntry>>::_Try_emplace<unsigned long const &,>(
              a1 + 184,
              v67,
              &v65);
      std::unique_ptr<LPA::EsimManager::OperationEntry>::operator=<std::default_delete<LPA::EsimManager::OperationEntry>,0>(
        (__int64 *)(*(_QWORD *)v57 + 40LL),
        (__int64 *)&v68);
      std::unique_ptr<LPA::EsimManager::OperationEntry>::~unique_ptr<LPA::EsimManager::OperationEntry>(&v68);
    }
  }
}

```

## disassembly

```asm
0x18008f0a0  push    rbp
0x18008f0a2  push    rbx
0x18008f0a3  push    rsi
0x18008f0a4  push    rdi
0x18008f0a5  push    r12
0x18008f0a7  push    r13
0x18008f0a9  push    r14
0x18008f0ab  push    r15
0x18008f0ad  lea     rbp, [rsp-7]
0x18008f0b2  sub     rsp, 0F8h
0x18008f0b9  mov     rax, cs:__security_cookie
0x18008f0c0  xor     rax, rsp
0x18008f0c3  mov     [rbp+3Fh+var_50], rax
0x18008f0c7  mov     [rbp+3Fh+var_A8], r9
0x18008f0cb  mov     [rbp+3Fh+var_88], r8
0x18008f0cf  mov     rbx, rdx
0x18008f0d2  mov     [rbp+3Fh+var_98], rdx
0x18008f0d6  mov     r13, rcx
0x18008f0d9  xor     r12d, r12d
0x18008f0dc  mov     [rbp+3Fh+var_B8], r12d
0x18008f0e0  xor     sil, sil
0x18008f0e3  mov     [rsp+130h+var_C8], esi
0x18008f0e7  mov     [rsp+130h+var_D0], r12b
0x18008f0ec  or      r14d, 0FFFFFFFFh
0x18008f0f0  mov     [rsp+130h+var_CC], r14d
0x18008f0f5  lea     r15, [rcx+0B8h]
0x18008f0fc  lea     r8, [rbp+3Fh+arg_30]
0x18008f100  lea     rdx, [rsp+130h+var_C0]
0x18008f105  mov     rcx, r15
0x18008f108  call    ?find@?$_Tree@V?$_Tmap_traits@KV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@std@@@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,std::shared_ptr<LPA::Lpd::DownloadInstance>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<LPA::Lpd::DownloadInstance>>>,0>>::find(ulong const &)
0x18008f10d  lea     rcx, aLpaEsimmanager_42; "LPA::EsimManager::OnLpdProfileAvailable"...
0x18008f114  mov     rdi, [rsp+130h+var_C0]
0x18008f119  cmp     [r15], rdi
0x18008f11c  jnz     short loc_18008F18A
0x18008f11e  xor     r15d, r15d
0x18008f121  mov     [rbp+3Fh+var_B4], r15d
0x18008f125  mov     eax, cs:CallbackContext
0x18008f12b  cmp     eax, 2
0x18008f12e  jbe     short loc_18008F1A2
0x18008f130  mov     [rbp+3Fh+var_80], rbx
0x18008f134  mov     eax, [rbp+3Fh+arg_30]
0x18008f137  mov     [rbp+3Fh+var_B0], eax
0x18008f13a  mov     dword ptr [rsp+130h+var_C0], r12d
0x18008f13f  mov     [rbp+3Fh+var_60], rcx
0x18008f143  lea     rax, aLpaserviceesim; "LpaServiceEsimManager"
0x18008f14a  mov     [rbp+3Fh+var_70], rax
0x18008f14e  lea     rax, [rbp+3Fh+var_80]
0x18008f152  mov     [rsp+130h+var_F0], rax
0x18008f157  lea     rax, [rbp+3Fh+var_B0]
0x18008f15b  mov     [rsp+130h+var_F8], rax
0x18008f160  lea     rax, [rsp+130h+var_C0]
0x18008f165  mov     [rsp+130h+var_100], rax
0x18008f16a  lea     rax, [rbp+3Fh+var_60]
0x18008f16e  mov     [rsp+130h+var_108], rax
0x18008f173  lea     rax, [rbp+3Fh+var_70]
0x18008f177  mov     [rsp+130h+var_110], rax
0x18008f17c  lea     rdx, word_18012CFBE
0x18008f183  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18008f188  jmp     short loc_18008F1A2
0x18008f18a  mov     rax, [rdi+28h]
0x18008f18e  mov     r14d, [rax+0E0h]
0x18008f195  mov     [rsp+130h+var_CC], r14d
0x18008f19a  mov     r15d, [rax+54h]
0x18008f19e  mov     [rbp+3Fh+var_B4], r15d
0x18008f1a2  lea     rcx, [r13-38h]
0x18008f1a6  mov     r9, rbx
0x18008f1a9  lea     r8, [rsp+130h+var_CC]
0x18008f1ae  lea     rdx, [rbp+3Fh+var_70]
0x18008f1b2  call    ?TryFindEsimRecordBySlotId@EsimManager@LPA@@AEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$unique_ptr@VEsimRecord@EsimManager@LPA@@U?$default_delete@VEsimRecord@EsimManager@LPA@@@std@@@std@@@std@@@std@@@std@@@std@@AEBKAEBU_GUID@@@Z; LPA::EsimManager::TryFindEsimRecordBySlotId(ulong const &,_GUID const &)
0x18008f1b7  lea     rcx, aLpaservicelpd; "LpaServiceLpd"
0x18008f1be  mov     rbx, [rbp+3Fh+var_70]
0x18008f1c2  cmp     rbx, [r13+98h]
0x18008f1c9  jnz     loc_18008F255
0x18008f1cf  mov     r15d, 80070490h
0x18008f1d5  mov     eax, cs:CallbackContext
0x18008f1db  cmp     eax, 3
0x18008f1de  jbe     loc_18008F5B6
0x18008f1e4  mov     dword ptr [rsp+130h+var_C0], r14d
0x18008f1e9  mov     eax, [rbp+3Fh+arg_30]
0x18008f1ec  mov     [rbp+3Fh+var_B0], eax
0x18008f1ef  mov     [rbp+3Fh+var_B4], 80070490h
0x18008f1f6  mov     r9, [rbp+3Fh+var_98]
0x18008f1fa  mov     [rbp+3Fh+var_70], r9
0x18008f1fe  lea     rax, aLpaEsimmanager_42; "LPA::EsimManager::OnLpdProfileAvailable"...
0x18008f205  mov     [rbp+3Fh+var_60], rax
0x18008f209  mov     [rbp+3Fh+var_80], rcx
0x18008f20d  lea     rax, [rsp+130h+var_C0]
0x18008f212  mov     [rsp+130h+var_E8], rax
0x18008f217  lea     rax, [rbp+3Fh+var_B0]
0x18008f21b  mov     [rsp+130h+var_F0], rax
0x18008f220  lea     rax, [rbp+3Fh+var_B4]
0x18008f224  mov     [rsp+130h+var_F8], rax
0x18008f229  lea     rax, [rbp+3Fh+var_70]
0x18008f22d  mov     [rsp+130h+var_100], rax
0x18008f232  lea     rax, [rbp+3Fh+var_60]
0x18008f236  mov     [rsp+130h+var_108], rax
0x18008f23b  lea     rax, [rbp+3Fh+var_80]
0x18008f23f  mov     [rsp+130h+var_110], rax
0x18008f244  lea     rdx, dword_18012CF5C
0x18008f24b  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18008f250  jmp     loc_18008F5B6
0x18008f255  mov     rcx, [rbx+30h]; this
0x18008f259  call    ?GetEsimInfo@EsimRecord@EsimManager@LPA@@QEBAPEBULPA_ESIM_INFO@@XZ; LPA::EsimManager::EsimRecord::GetEsimInfo(void)
0x18008f25e  mov     r11, rax
0x18008f261  mov     edx, 1
0x18008f266  lea     rcx, [r13+0B8h]
0x18008f26d  cmp     [rcx], rdi
0x18008f270  jz      short loc_18008F2C3
0x18008f272  mov     rax, [rdi+28h]
0x18008f276  movzx   esi, sil
0x18008f27a  cmp     dword ptr [rax+50h], 2
0x18008f27e  cmovz   esi, edx
0x18008f281  mov     [rsp+130h+var_C8], esi
0x18008f285  cmp     [rcx], rdi
0x18008f288  jz      short loc_18008F2C3
0x18008f28a  mov     r14, [rbp+3Fh+var_88]
0x18008f28e  cmp     dword ptr [rax+50h], 0Ah
0x18008f292  jnz     short loc_18008F2C7
0x18008f294  cmp     r15d, 2
0x18008f298  jnz     short loc_18008F2C7
0x18008f29a  mov     r8, [r14+8]
0x18008f29e  add     r8, 24h ; '$'; unsigned __int16 *
0x18008f2a2  lea     rcx, [r13+118h]; unsigned __int16 *
0x18008f2a9  lea     edx, [r15+13h]; unsigned __int64
0x18008f2ad  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008f2b2  lea     edx, [r15-1]
0x18008f2b6  mov     sil, dl
0x18008f2b9  mov     [rsp+130h+var_C8], esi
0x18008f2bd  mov     [rsp+130h+var_D0], dl
0x18008f2c1  jmp     short loc_18008F2C7
0x18008f2c3  mov     r14, [rbp+3Fh+var_88]
0x18008f2c7  test    r11, r11
0x18008f2ca  jz      loc_18008F5B0
0x18008f2d0  xor     r15d, r15d
0x18008f2d3  test    [r11], dl
0x18008f2d6  jz      short loc_18008F308
0x18008f2d8  lea     r8, [r11+4]; unsigned __int16 *
0x18008f2dc  mov     rcx, [r14+8]
0x18008f2e0  add     rcx, 54h ; 'T'; unsigned __int16 *
0x18008f2e4  lea     edx, [r15+21h]; unsigned __int64
0x18008f2e8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008f2ed  mov     r15d, eax
0x18008f2f0  test    eax, eax
0x18008f2f2  js      loc_18008F5B6
0x18008f2f8  mov     rcx, [r14+8]
0x18008f2fc  or      dword ptr [rcx+1Ch], 1
0x18008f300  mov     rcx, [r14+8]
0x18008f304  or      dword ptr [rcx+20h], 4
0x18008f308  mov     al, [rsp+130h+var_D0]
0x18008f30c  mov     [rsp+130h+var_D0], al
0x18008f310  mov     rax, [rbx+30h]
0x18008f314  mov     rcx, [rax+100h]
0x18008f31b  test    rcx, rcx
0x18008f31e  jz      short loc_18008F357
0x18008f320  lea     rsi, [r14+8]
0x18008f324  mov     rax, [rsi]
0x18008f327  lea     rdx, [rbp+3Fh+var_90]
0x18008f32b  mov     [rsp+130h+var_108], rdx
0x18008f330  mov     eax, [rax+98h]
0x18008f336  mov     dword ptr [rsp+130h+var_110], eax
0x18008f33a  mov     r9, [rbp+3Fh+arg_28]
0x18008f33e  mov     r8, [rbp+3Fh+arg_20]
0x18008f342  mov     rdx, [rbp+3Fh+var_A8]
0x18008f346  call    ?IsAllowedByPolicy@RulesAuthorizationTable@EsimRecord@EsimManager@LPA@@QEAA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$vector@EV?$allocator@E@std@@@6@1KAEA_N@Z; LPA::EsimManager::EsimRecord::RulesAuthorizationTable::IsAllowedByPolicy(std::string const &,std::vector<uchar> const &,std::vector<uchar> const &,ulong,bool &)
0x18008f34b  test    al, al
0x18008f34d  jnz     short loc_18008F357
0x18008f34f  mov     r14d, 4
0x18008f355  jmp     short loc_18008F373
0x18008f357  lea     rsi, [r14+8]
0x18008f35b  mov     rax, [rsi]
0x18008f35e  test    byte ptr [rax+1Ch], 4
0x18008f362  jz      short loc_18008F379
0x18008f364  cmp     dword ptr [rax+9Ch], 2
0x18008f36b  jnz     short loc_18008F379
0x18008f36d  mov     r14d, 5
0x18008f373  mov     [rbp+3Fh+var_B8], r14d
0x18008f377  jmp     short loc_18008F3F3
0x18008f379  test    byte ptr [rax+1Ch], 2
0x18008f37d  jz      loc_18008F41B
0x18008f383  test    byte ptr [rax+98h], 1
0x18008f38a  jz      loc_18008F41B
0x18008f390  lea     rcx, [rbp+3Fh+var_A8]
0x18008f394  call    ??0?$list@PEBULPA_PROFILE_DETAILS@@V?$allocator@PEBULPA_PROFILE_DETAILS@@@std@@@std@@QEAA@XZ; std::list<LPA_PROFILE_DETAILS const *>::list<LPA_PROFILE_DETAILS const *>(void)
0x18008f399  nop
0x18008f39a  lea     rdx, [rbp+3Fh+var_A8]
0x18008f39e  mov     rcx, [rbx+30h]; this
0x18008f3a2  call    ?GetProfiles@EsimRecord@EsimManager@LPA@@QEBAXAEAV?$list@PEBULPA_PROFILE_DETAILS@@V?$allocator@PEBULPA_PROFILE_DETAILS@@@std@@@std@@@Z; LPA::EsimManager::EsimRecord::GetProfiles(std::list<LPA_PROFILE_DETAILS const *> &)
0x18008f3a7  mov     rdx, [rbp+3Fh+var_A8]
0x18008f3ab  mov     rax, [rdx]
0x18008f3ae  cmp     rax, rdx
0x18008f3b1  jz      short loc_18008F3D7
0x18008f3b3  mov     rcx, [rax+10h]
0x18008f3b7  test    byte ptr [rcx+4], 4
0x18008f3bb  jz      short loc_18008F3C6
0x18008f3bd  cmp     dword ptr [rcx+84h], 0
0x18008f3c4  jz      short loc_18008F3CB
0x18008f3c6  mov     rax, [rax]
0x18008f3c9  jmp     short loc_18008F3AE
0x18008f3cb  mov     r14d, 3
0x18008f3d1  mov     [rbp+3Fh+var_B8], r14d
0x18008f3d5  jmp     short loc_18008F3DB
0x18008f3d7  mov     r14d, [rbp+3Fh+var_B8]
0x18008f3db  call    ??$_Free_non_head@V?$allocator@U?$_List_node@PEAVPipeImplementation@PipeManager@@PEAX@std@@@std@@@?$_List_node@PEAVPipeImplementation@PipeManager@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@PEAVPipeImplementation@PipeManager@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<PipeManager::PipeImplementation *,void *>::_Free_non_head<std::allocator<std::_List_node<PipeManager::PipeImplementation *,void *>>>(std::allocator<std::_List_node<PipeManager::PipeImplementation *,void *>> &,std::_List_node<PipeManager::PipeImplementation *,void *> *)
0x18008f3e0  mov     edx, 18h
0x18008f3e5  mov     rcx, [rbp+3Fh+var_A8]
0x18008f3e9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18008f3ee  test    r14d, r14d
0x18008f3f1  jz      short loc_18008F41E
0x18008f3f3  mov     rax, [rsi]
0x18008f3f6  or      dword ptr [rax+1Ch], 1
0x18008f3fa  mov     rax, [rsi]
0x18008f3fd  or      dword ptr [rax+20h], 2
0x18008f401  mov     rax, [rsi]
0x18008f404  mov     dword ptr [rax+50h], 6
0x18008f40b  mov     rax, [rsi]
0x18008f40e  or      dword ptr [rax+4], 4
0x18008f412  mov     rax, [rsi]
0x18008f415  mov     [rax+0Ch], r14d
0x18008f419  jmp     short loc_18008F41E
0x18008f41b  mov     r14d, r12d
0x18008f41e  mov     r8d, [rbp+3Fh+var_B4]
0x18008f422  mov     rdx, [rbp+3Fh+var_88]
0x18008f426  mov     rcx, [rbx+30h]
0x18008f42a  call    ?SetAvailableProfile@EsimRecord@EsimManager@LPA@@QEAAXAEBV?$unique_ptr@ULPA_PROFILE_AVAILABLE_FOR_INSTALL@@P6AXPEAX@Z@std@@W4LPACLIENTMODEINTERNAL@3@@Z; LPA::EsimManager::EsimRecord::SetAvailableProfile(std::unique_ptr<LPA_PROFILE_AVAILABLE_FOR_INSTALL,void (*)(void *)> const &,LPA::LPACLIENTMODEINTERNAL)
0x18008f42f  cmp     byte ptr [rsp+130h+var_C8], 0
0x18008f434  jnz     loc_18008F58E
0x18008f43a  test    r14d, r14d
0x18008f43d  jnz     short loc_18008F451
0x18008f43f  lea     edx, [r14+2]
0x18008f443  mov     rcx, [rbx+30h]
0x18008f447  call    ?SetOperationSubState@EsimRecord@EsimManager@LPA@@QEAAXW4LPAESIMOPERATIONSUBSTATE@@@Z; LPA::EsimManager::EsimRecord::SetOperationSubState(LPAESIMOPERATIONSUBSTATE)
0x18008f44c  jmp     loc_18008F58E
0x18008f451  mov     [rsp+130h+var_CC], 0
0x18008f459  xor     eax, eax
0x18008f45b  mov     [rbp+3Fh+var_70], rax
0x18008f45f  mov     dword ptr [rbp+3Fh+var_68], eax
0x18008f462  lea     edx, [rax+5]
0x18008f465  mov     rcx, [rbx+30h]
0x18008f469  call    ?SetOperationSubState@EsimRecord@EsimManager@LPA@@QEAAXW4LPAESIMOPERATIONSUBSTATE@@@Z; LPA::EsimManager::EsimRecord::SetOperationSubState(LPAESIMOPERATIONSUBSTATE)
0x18008f46e  mov     r12, [r13+68h]
0x18008f472  mov     rax, [r12]
0x18008f476  mov     r15, [rax+8]
0x18008f47a  sub     edx, r14d
0x18008f47d  neg     edx
0x18008f47f  sbb     r14d, r14d
0x18008f482  add     r14d, 4
0x18008f486  mov     rsi, [rsi]
0x18008f489  add     rsi, 24h ; '$'
0x18008f48d  lea     rcx, [r13+20h]
0x18008f491  lea     rdx, [rbp+3Fh+var_60]
0x18008f495  call    ?shared_from_this@?$enable_shared_from_this@VEnterpriseManager@LPA@@@std@@QEAA?AV?$shared_ptr@VEnterpriseManager@LPA@@@2@XZ; std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this(void)
0x18008f49a  nop
0x18008f49b  mov     rdx, rax
0x18008f49e  lea     rcx, [rbp+3Fh+var_A8]
0x18008f4a2  call    ??$?0VEsimManager@LPA@@$0A@@?$weak_ptr@ULpdCompletionHandler@LPA@@@std@@QEAA@AEBV?$shared_ptr@VEsimManager@LPA@@@1@@Z; std::weak_ptr<LPA::LpdCompletionHandler>::weak_ptr<LPA::LpdCompletionHandler>(std::shared_ptr<LPA::EsimManager> const &)
0x18008f4a7  mov     rcx, [rbx+30h]
0x18008f4ab  mov     rdx, [rcx+20h]
0x18008f4af  mov     r8d, [rdx+6Ch]
0x18008f4b3  mov     dword ptr [rsp+130h+var_C0], r8d
0x18008f4b8  lea     rcx, [rsp+130h+var_CC]
0x18008f4bd  mov     [rsp+130h+var_E8], rcx
0x18008f4c2  lea     rcx, [rbp+3Fh+var_70]
0x18008f4c6  mov     [rsp+130h+var_F0], rcx
0x18008f4cb  mov     [rsp+130h+var_F8], 0
0x18008f4d4  mov     dword ptr [rsp+130h+var_100], r14d
0x18008f4d9  mov     byte ptr [rsp+130h+var_108], 0
0x18008f4de  mov     [rsp+130h+var_110], rsi
0x18008f4e3  mov     r9, rax
0x18008f4e6  lea     r8, [rsp+130h+var_C0]
0x18008f4eb  mov     rsi, [rbp+3Fh+var_98]
0x18008f4ef  mov     rdx, rsi
0x18008f4f2  mov     rcx, r12
0x18008f4f5  mov     rax, r15
0x18008f4f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f4fd  mov     r15d, eax
0x18008f500  mov     rcx, [rbp+3Fh+var_58]; this
0x18008f504  test    rcx, rcx
0x18008f507  jz      short loc_18008F50E
0x18008f509  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008f50e  test    r15d, r15d
0x18008f511  js      short loc_18008F58E
0x18008f513  mov     rax, [rbx+30h]
0x18008f517  mov     rdx, [rax+20h]
0x18008f51b  mov     eax, [rdx+6Ch]
0x18008f51e  mov     dword ptr [rsp+130h+var_C0], eax
0x18008f522  lea     rdx, [rbp+3Fh+var_60]
0x18008f526  lea     rcx, [r13+20h]
0x18008f52a  call    ?shared_from_this@?$enable_shared_from_this@VEnterpriseManager@LPA@@@std@@QEAA?AV?$shared_ptr@VEnterpriseManager@LPA@@@2@XZ; std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this(void)
0x18008f52f  nop
0x18008f530  lea     rcx, [rsp+130h+var_C0]
0x18008f535  mov     [rsp+130h+var_110], rcx
0x18008f53a  mov     r9, rsi
0x18008f53d  lea     r8, [rsp+130h+var_CC]
0x18008f542  mov     rdx, rax
0x18008f545  lea     rcx, [rbp+3Fh+var_A8]
0x18008f549  call    ??$make_unique@VOperationEntry@EsimManager@LPA@@V?$shared_ptr@VEsimManager@LPA@@@std@@AEAKAEBU_GUID@@K$0A@@std@@YA?AV?$unique_ptr@VOperationEntry@EsimManager@LPA@@U?$default_delete@VOperationEntry@EsimManager@LPA@@@std@@@0@$$QEAV?$shared_ptr@VEsimManager@LPA@@@0@AEAKAEBU_GUID@@$$QEAK@Z; std::make_unique<LPA::EsimManager::OperationEntry,std::shared_ptr<LPA::EsimManager>,ulong &,_GUID const &,ulong,0>(std::shared_ptr<LPA::EsimManager> &&,ulong &,_GUID const &,ulong &&)
0x18008f54e  mov     rsi, rax
0x18008f551  lea     r8, [rsp+130h+var_CC]
0x18008f556  lea     rdx, [rbp+3Fh+var_80]
0x18008f55a  lea     rcx, [r13+0B8h]
  ... truncated ...
```
