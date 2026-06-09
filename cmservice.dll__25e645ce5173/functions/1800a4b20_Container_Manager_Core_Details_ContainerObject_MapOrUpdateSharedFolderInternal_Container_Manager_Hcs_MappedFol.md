# Container::Manager::Core::Details::ContainerObject::MapOrUpdateSharedFolderInternal(Container::Manager::Hcs::MappedFolderConfiguration,Csl::SrwLock::ReleaseOnScopeExit<0> &)

- ea: `0x1800a4b20`
- end: `0x1800a5565`
- name: `?MapOrUpdateSharedFolderInternal@ContainerObject@Details@Core@Manager@Container@@AEAAJVMappedFolderConfiguration@Hcs@45@AEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z`
- size: `2629`
- prototype: ``
- caller_count: `5`
- callee_count: `23`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800a34a0`
- `0x1800a3768`
- `0x1800a469c`
- `0x1800a71b4`
- `0x1800aab8c`

## callees

- `0x180004bf4`
- `0x180004fc4`
- `0x180005704`
- `0x18000da88`
- `0x18000dad8`
- `0x180016774`
- `0x18004891c`
- `0x1800785d4`
- `0x1800982a8`
- `0x180098594`
- `0x180098fe0`
- `0x1800990d0`
- `0x1800a4b20`
- `0x1800ad4e0`
- `0x1800ba2c0`
- `0x1800ba6b8`
- `0x1800ba77c`
- `0x180121670`
- `0x1801220d0`
- `0x180123878`
- `0x180125814`
- `0x180198404`
- `0x180198494`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800a52d6`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800a52d6`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800a4f49`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800a4f49`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a5269`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a53cb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a5269`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a53cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a50e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a522b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a529e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a52c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a538e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a53fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a541a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a50e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a522b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a529e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a52c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a538e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a53fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a541a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a4f55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a5275`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a53d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a4f55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a5275`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a53d7`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::ContainerObject::MapOrUpdateSharedFolderInternal(
        __int64 a1,
        __int64 *a2,
        PSRWLOCK *a3)
{
  __int64 *v4; // r13
  __int64 v5; // rbx
  __int64 *v6; // r8
  void *v7; // rcx
  char *v8; // rax
  char *v9; // r14
  Container::Manager::Hcs::VsmbShareConfiguration *v10; // rdx
  Container::Manager::Hcs::VsmbShareConfiguration *v11; // rdi
  __int64 v12; // rdx
  __int64 v13; // r8
  Container::Manager::Hcs::VsmbShareConfiguration *v14; // r8
  bool v15; // zf
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  unsigned __int64 *v19; // rbx
  unsigned __int64 v20; // rdi
  unsigned __int64 *v21; // rax
  _OWORD *InsertionPointUniqueUpper; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rdi
  __int64 v29; // rbx
  __int64 v30; // rdx
  __int64 v31; // rdx
  unsigned int v32; // ebx
  Container::Manager::Hcs::MappedFolderConfiguration *v33; // rcx
  char *v34; // rax
  PSRWLOCK v35; // rcx
  int updated; // eax
  char *v37; // rbx
  char *v38; // rcx
  PSRWLOCK v39; // rcx
  int v40; // edi
  RTL_SRWLOCK *v41; // r15
  PSRWLOCK v42; // rcx
  __int64 v43; // rdi
  Container::Manager::Hcs::VsmbShareConfiguration *v44; // rax
  __int64 v45; // rax
  __int64 v46; // rbx
  __int64 v47; // r13
  PSRWLOCK v48; // rcx
  PSRWLOCK v49; // rcx
  void *v51[2]; // [rsp+28h] [rbp-89h] BYREF
  _WORD v52[8]; // [rsp+38h] [rbp-79h] BYREF
  void *v53[2]; // [rsp+48h] [rbp-69h] BYREF
  _WORD v54[8]; // [rsp+58h] [rbp-59h] BYREF
  _QWORD *v55; // [rsp+68h] [rbp-49h]
  void *v56[2]; // [rsp+70h] [rbp-41h] BYREF
  _WORD v57[8]; // [rsp+80h] [rbp-31h] BYREF
  Container::Manager::Hcs::VsmbShareConfiguration *v58; // [rsp+90h] [rbp-21h]
  char *v59[2]; // [rsp+98h] [rbp-19h] BYREF
  char *v60; // [rsp+A8h] [rbp-9h] BYREF
  char v61; // [rsp+B0h] [rbp-1h] BYREF
  char v62; // [rsp+B8h] [rbp+7h] BYREF
  char v63[72]; // [rsp+C0h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+110h] [rbp+5Fh]
  __int64 *v66; // [rsp+120h] [rbp+6Fh] BYREF
  unsigned __int64 *v67; // [rsp+130h] [rbp+7Fh] BYREF

  v66 = a2;
  v53[0] = v54;
  v4 = a2;
  v5 = a1;
  v53[1] = v54;
  v54[0] = 0;
  if ( *((_BYTE *)a2 + 224) )
  {
    v6 = (__int64 *)a2[20];
    if ( v6 != a2 + 18
      && !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             v53,
                             v6[3],
                             (v6[4] - v6[3]) >> 1) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14B3,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        (const char *)0x8007000ELL,
        (int)v51[0]);
      v7 = v53[0];
      if ( v53[0] != v54 )
        goto LABEL_148;
      goto LABEL_149;
    }
  }
  v8 = (char *)operator new(0x138u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( !v8 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14B8,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)0x8007000ELL,
      (int)v51[0]);
LABEL_147:
    v7 = v53[0];
    if ( v53[0] != v54 )
LABEL_148:
      operator delete(v7, (const struct std::nothrow_t *)&std::nothrow);
LABEL_149:
    Container::Manager::Hcs::MappedFolderConfiguration::~MappedFolderConfiguration((Container::Manager::Hcs::MappedFolderConfiguration *)v4);
    return 2147942414LL;
  }
  *v8 = 0;
  *(_OWORD *)(v8 + 8) = 0;
  *(_OWORD *)(v8 + 24) = 0;
  *((_QWORD *)v8 + 5) = 0;
  memset_0(v8 + 48, 0, 0xC0u);
  v60 = v9;
  *((_OWORD *)v9 + 15) = 0;
  *((_OWORD *)v9 + 16) = 0;
  *((_OWORD *)v9 + 17) = 0;
  *((_QWORD *)v9 + 36) = 0;
  *((_QWORD *)v9 + 37) = 0;
  *((_DWORD *)v9 + 76) = 0;
  if ( !Container::Manager::Hcs::MappedFolderConfiguration::Assign(
          (Container::Manager::Hcs::MappedFolderConfiguration *)(v9 + 8),
          (const struct Container::Manager::Hcs::MappedFolderConfiguration *)v4) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x57E,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\Container.h",
      (const char *)0x8007000ELL,
      (int)v51[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14BA,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)0x8007000ELL,
      (int)v51[0]);
    Container::Manager::Hcs::MappedFolderConfiguration::~MappedFolderConfiguration((Container::Manager::Hcs::MappedFolderConfiguration *)(v9 + 8));
    operator delete(v9, (const struct std::nothrow_t *)0x138);
    goto LABEL_147;
  }
  v10 = (Container::Manager::Hcs::VsmbShareConfiguration *)(v4 + 5);
  v11 = (Container::Manager::Hcs::VsmbShareConfiguration *)(v4 + 5);
  while ( 1 )
  {
    v51[0] = v52;
    v51[1] = v52;
    v52[0] = 0;
    if ( !*((_BYTE *)v4 + 32) )
    {
      __int2c();
      v11 = v10;
    }
    v12 = *v4;
    v13 = (v4[1] - *v4) >> 1;
    v58 = v11;
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             v51,
                             v12,
                             v13) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14C4,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        (const char *)0x8007000ELL,
        (int)v51[0]);
      goto LABEL_138;
    }
    v14 = v11;
    v56[0] = v57;
    v56[1] = v57;
    v15 = *((_BYTE *)v4 + 224) == 0;
    v57[0] = 0;
    if ( v15 )
      v14 = (Container::Manager::Hcs::VsmbShareConfiguration *)(v4 + 29);
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             v56,
                             *(_QWORD *)v14,
                             (__int64)(*((_QWORD *)v14 + 1) - *(_QWORD *)v14) >> 1) )
    {
      v30 = 5319;
      goto LABEL_57;
    }
    v55 = (_QWORD *)(v5 + 736);
    v16 = utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>,0>::_FindImpl<Csl::Path>(
            v5 + 736,
            v51);
    v19 = (unsigned __int64 *)v16;
    if ( (_QWORD *)v16 == v55 )
    {
      v20 = (unsigned __int64)v55;
      if ( *(_QWORD *)(v20 + 16) == v20 )
      {
        v21 = (unsigned __int64 *)utl::_Tree<Csl::Path,utl::pair<Csl::Path const,utl::map<Csl::Path,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,utl::map<Csl::Path,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>>>>,0>::_NewNodeConstruct<utl::_PairMapTag,Csl::Path>(
                                    v18,
                                    v17,
                                    v51);
        v19 = v21;
        if ( v21 )
        {
          *v21 = v20 | 1;
          v21[1] = (unsigned __int64)&utl::_TreeSentinel;
          v21[2] = (unsigned __int64)&utl::_TreeSentinel;
          *(_QWORD *)v20 = v21;
          *(_QWORD *)(v20 + 8) = v21;
          *(_QWORD *)(v20 + 16) = v21;
          ++*(_QWORD *)(v20 + 24);
LABEL_24:
          if ( v19 )
            goto LABEL_25;
          v30 = 5334;
LABEL_57:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v30,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
            (const char *)0x8007000ELL,
            (int)v51[0]);
          if ( v56[0] != v57 )
            operator delete(v56[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_138:
          if ( v51[0] != v52 )
            operator delete(v51[0], (const struct std::nothrow_t *)&std::nothrow);
          Container::Manager::Hcs::MappedFolderConfiguration::~MappedFolderConfiguration((Container::Manager::Hcs::MappedFolderConfiguration *)(v9 + 8));
          v38 = v9;
LABEL_141:
          operator delete(v38, (const struct std::nothrow_t *)0x138);
LABEL_142:
          if ( v53[0] != v54 )
            operator delete(v53[0], (const struct std::nothrow_t *)&std::nothrow);
          v32 = -2147024882;
          goto LABEL_145;
        }
      }
      else
      {
        v67 = 0;
        InsertionPointUniqueUpper = (_OWORD *)utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>,0>::_FindInsertionPointUniqueUpper(
                                                v55,
                                                v63,
                                                &v67,
                                                v51);
        v19 = v67;
        *(_OWORD *)v59 = *InsertionPointUniqueUpper;
        if ( v67 )
        {
LABEL_25:
          LOBYTE(v67) = 1;
          goto LABEL_37;
        }
        v25 = utl::_Tree<Csl::Path,utl::pair<Csl::Path const,utl::map<Csl::Path,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,utl::map<Csl::Path,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>>>>,0>::_NewNodeConstruct<utl::_PairMapTag,Csl::Path>(
                v24,
                v23,
                v51);
        v19 = (unsigned __int64 *)v25;
        if ( v25 )
        {
          utl::_Tree<_GUID,utl::pair<_GUID const,enum Container::Manager::Hns::NetworkType>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,enum Container::Manager::Hns::NetworkType>>,0>::_InsertAt(
            v20,
            v59,
            v25);
          goto LABEL_24;
        }
      }
      v19 = 0;
      goto LABEL_24;
    }
    LOBYTE(v67) = 0;
    if ( *(_QWORD *)(v16 + 72) != v16 + 56 && *((_BYTE *)v4 + 224) )
    {
      v26 = *(_QWORD *)(*(_QWORD *)(v16 + 72) + 56LL);
      if ( *(_BYTE *)(v26 + 232) && *(_BYTE *)(v26 + 80) )
      {
        if ( !*((_BYTE *)v11 + 184) )
          __int2c();
        if ( *((Container::Manager::Hcs::VsmbShareConfiguration **)v11 + 15) == (Container::Manager::Hcs::VsmbShareConfiguration *)((char *)v11 + 104) )
        {
          v31 = 5358;
          goto LABEL_61;
        }
      }
      if ( !*((_BYTE *)v11 + 184) )
        __int2c();
      if ( *((_BYTE *)v11 + 32) )
      {
        v31 = 5364;
        goto LABEL_61;
      }
    }
    v20 = (unsigned __int64)v55;
LABEL_37:
    v27 = utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>,0>::_FindImpl<Csl::Path>(
            v19 + 7,
            v56);
    if ( (unsigned __int64 *)v27 == v19 + 7 )
      break;
    v28 = *(_QWORD *)(v27 + 56);
    if ( !*(_BYTE *)(v28 + 232) )
      goto LABEL_84;
    if ( *((_BYTE *)v4 + 224) )
    {
      if ( !*((_BYTE *)v58 + 184) )
        __int2c();
      if ( *((Container::Manager::Hcs::VsmbShareConfiguration **)v58 + 15) == (Container::Manager::Hcs::VsmbShareConfiguration *)((char *)v58 + 104) )
      {
LABEL_84:
        v32 = -2147024713;
        if ( (*(_DWORD *)(*(_QWORD *)(a1 + 1304) + 96LL) & 8) == 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1524,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
            (const char *)0x800700B7LL,
            (int)v51[0]);
LABEL_62:
        if ( v56[0] != v57 )
          operator delete(v56[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v51[0] != v52 )
          operator delete(v51[0], (const struct std::nothrow_t *)&std::nothrow);
        v33 = (Container::Manager::Hcs::MappedFolderConfiguration *)(v9 + 8);
LABEL_67:
        Container::Manager::Hcs::MappedFolderConfiguration::~MappedFolderConfiguration(v33);
        operator delete(v9, (const struct std::nothrow_t *)0x138);
LABEL_68:
        if ( v53[0] != v54 )
          operator delete(v53[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_145:
        Container::Manager::Hcs::MappedFolderConfiguration::~MappedFolderConfiguration((Container::Manager::Hcs::MappedFolderConfiguration *)v4);
        return v32;
      }
    }
    if ( !*(_BYTE *)(v28 + 232) )
      __int2c();
    if ( *(_QWORD *)(v28 + 168) == v28 + 152 && !*(_BYTE *)(v28 + 80) )
    {
      v31 = 5428;
LABEL_61:
      v32 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v31,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
              (const char *)0x32,
              (unsigned int)v51[0]);
      goto LABEL_62;
    }
    v59[0] = (char *)v58 + 184;
    if ( !*((_BYTE *)v58 + 184) )
      __int2c();
    if ( !Container::Manager::Hcs::VsmbShareConfiguration::CanOverlayWith(
            v58,
            (const struct Container::Manager::Hcs::VsmbShareConfiguration *)(v28 + 48)) )
    {
      v31 = 5436;
      goto LABEL_61;
    }
    v15 = *(_BYTE *)v28 == 0;
    LOBYTE(v67) = 1;
    v29 = v28;
    if ( v15 )
    {
      if ( v56[0] != v57 )
        operator delete(v56[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v51[0] == v52 )
        LOBYTE(v67) = 1;
      else
        operator delete(v51[0], (const struct std::nothrow_t *)&std::nothrow);
      v34 = v59[0];
      *(_BYTE *)v28 = 1;
      if ( !*(_BYTE *)(v28 + 232) )
        __int2c();
      if ( !*v34 )
        __int2c();
      utl::set<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::merge<utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>(
        v28 + 152,
        (char *)v58 + 104);
      v35 = *a3;
      if ( *a3 )
      {
        LODWORD(v35[1].Ptr) = 0;
        ReleaseSRWLockExclusive(v35);
        *a3 = 0;
      }
      updated = Container::Manager::Hcs::ComputeSystem::UpdateSharedFolder(
                  *(Container::Manager::Hcs::ComputeSystem **)(a1 + 1256),
                  (const struct Container::Manager::Hcs::MappedFolderConfiguration *)(v28 + 8));
      goto LABEL_102;
    }
    v67 = 0;
    Csl::RundownReference::TryAcquireRundownProtection(
      (Csl::RundownReference *)(v28 + 296),
      (struct Csl::RundownProtection *)&v67);
    LODWORD((*a3)[1].Ptr) = 0;
    SleepConditionVariableSRW((PCONDITION_VARIABLE)(v28 + 288), *a3, 0xFFFFFFFF, 0);
    LODWORD((*a3)[1].Ptr) = GetCurrentThreadId();
    Csl::RundownProtection::Reset((Csl::RundownProtection *)&v67);
    if ( v56[0] != v57 )
      operator delete(v56[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v51[0] != v52 )
      operator delete(v51[0], (const struct std::nothrow_t *)&std::nothrow);
    v11 = v58;
    v10 = (Container::Manager::Hcs::VsmbShareConfiguration *)(v4 + 5);
    v5 = a1;
  }
  utl::map<Csl::Path,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>>::try_emplace<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>,0>(
    v19 + 7,
    v59,
    v56,
    &v60);
  if ( !v59[0] )
  {
    if ( (_BYTE)v67 )
      utl::_Tree<Csl::Path,utl::pair<Csl::Path const,utl::map<Csl::Path,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,utl::map<Csl::Path,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>>>>,0>::erase(
        v20,
        &v66,
        v19);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1506,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)0x8007000ELL,
      (int)v51[0]);
    if ( v56[0] != v57 )
      operator delete(v56[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v51[0] != v52 )
      operator delete(v51[0], (const struct std::nothrow_t *)&std::nothrow);
    v37 = v60;
    if ( v60 )
    {
      Container::Manager::Hcs::MappedFolderConfiguration::~MappedFolderConfiguration((Container::Manager::Hcs::MappedFolderConfiguration *)(v60 + 8));
      v38 = v37;
      goto LABEL_141;
    }
    goto LABEL_142;
  }
  v29 = *((_QWORD *)v59[0] + 7);
  if ( v56[0] != v57 )
    operator delete(v56[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v51[0] != v52 )
    operator delete(v51[0], (const struct std::nothrow_t *)&std::nothrow);
  *(_BYTE *)v29 = 1;
  v39 = *a3;
  if ( *a3 )
  {
    LODWORD(v39[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v39);
    *a3 = 0;
  }
  updated = Container::Manager::Hcs::ComputeSystem::MapSharedFolder(
              *(Container::Manager::Hcs::ComputeSystem **)(a1 + 1256),
              (const struct Container::Manager::Hcs::MappedFolderConfiguration *)v4);
  LOBYTE(v67) = 0;
  v9 = v60;
LABEL_102:
  v40 = updated;
  v41 = (RTL_SRWLOCK *)(a1 + 456);
  LODWORD(v59[0]) = updated;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 456));
  *(_DWORD *)(a1 + 464) = GetCurrentThreadId();
  if ( a3 == (PSRWLOCK *)&v61 )
  {
    if ( a1 != -456 )
    {
      *(_DWORD *)(a1 + 464) = 0;
      ReleaseSRWLockExclusive(v41);
    }
  }
  else
  {
    v42 = *a3;
    if ( *a3 )
    {
      LODWORD(v42[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v42);
    }
    *a3 = v41;
  }
  *(_BYTE *)v29 = 0;
  WakeAllConditionVariable((PCONDITION_VARIABLE)(v29 + 288));
  if ( v40 < 0 )
  {
    if ( !*((_BYTE *)v4 + 32) )
      __int2c();
    v43 = utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>,0>::_FindImpl<Csl::Path>(
            v55,
            v4);
    v44 = v58;
    if ( !*((_BYTE *)v4 + 224) )
      v44 = (Container::Manager::Hcs::VsmbShareConfiguration *)(v4 + 29);
    v45 = utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>,0>::_FindImpl<Csl::Path>(
            v43 + 56,
            v44);
    v46 = v45;
    if ( !(_BYTE)v67 )
    {
      v47 = *(_QWORD *)(v45 + 56);
      *(_QWORD *)(v45 + 56) = 0;
      if ( v9 )
      {
        Container::Manager::Hcs::MappedFolderConfiguration::~MappedFolderConfiguration((Container::Manager::Hcs::MappedFolderConfiguration *)(v9 + 8));
        operator delete(v9, (const struct std::nothrow_t *)0x138);
      }
      utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>,0>::erase(
        v43 + 56,
        &v67,
        v46);
      if ( *(_QWORD *)(v43 + 72) == v43 + 56 )
        utl::_Tree<Csl::Path,utl::pair<Csl::Path const,utl::map<Csl::Path,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,utl::map<Csl::Path,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>>>>,0>::erase(
          v55,
          &v67,
          v43);
      v48 = *a3;
      if ( *a3 )
      {
        LODWORD(v48[1].Ptr) = 0;
        ReleaseSRWLockExclusive(v48);
        *a3 = 0;
      }
      Csl::RundownReference::WaitForRundownProtectionRelease((Csl::RundownReference *)(v47 + 296));
      v9 = 0;
      if ( v47 )
      {
        Container::Manager::Hcs::MappedFolderConfiguration::~MappedFolderConfiguration((Container::Manager::Hcs::MappedFolderConfiguration *)(v47 + 8));
        operator delete((void *)v47, (const struct std::nothrow_t *)0x138);
      }
      AcquireSRWLockExclusive(v41);
      *(_DWORD *)(a1 + 464) = GetCurrentThreadId();
      if ( a3 == (PSRWLOCK *)&v62 )
      {
        if ( a1 != -456 )
        {
          *(_DWORD *)(a1 + 464) = 0;
          ReleaseSRWLockExclusive(v41);
        }
      }
      else
      {
        v49 = *a3;
        if ( *a3 )
        {
          LODWORD(v49[1].Ptr) = 0;
          ReleaseSRWLockExclusive(v49);
        }
        *a3 = v41;
      }
      v4 = v66;
    }
    v32 = (unsigned int)v59[0];
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15A9,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)LODWORD(v59[0]),
      (int)v51[0]);
    if ( v9 )
    {
      v33 = (Container::Manager::Hcs::MappedFolderConfiguration *)(v9 + 8);
      goto LABEL_67;
    }
    goto LABEL_68;
  }
  if ( v9 )
  {
    Container::Manager::Hcs::MappedFolderConfiguration::~MappedFolderConfiguration((Container::Manager::Hcs::MappedFolderConfiguration *)(v9 + 8));
    operator delete(v9, (const struct std::nothrow_t *)0x138);
  }
  if ( v53[0] != v54 )
    operator delete(v53[0], (const struct std::nothrow_t *)&std::nothrow);
  Container::Manager::Hcs::MappedFolderConfiguration::~MappedFolderConfiguration((Container::Manager::Hcs::MappedFolderConfiguration *)v4);
  return 0;
}

```

## disassembly

```asm
0x1800a4b20  mov     rax, rsp
0x1800a4b23  mov     [rax+18h], rbx
0x1800a4b27  mov     [rax+10h], rdx
0x1800a4b2b  mov     [rax+8], rcx
0x1800a4b2f  push    rbp
0x1800a4b30  push    rsi
0x1800a4b31  push    rdi
0x1800a4b32  push    r12
0x1800a4b34  push    r13
0x1800a4b36  push    r14
0x1800a4b38  push    r15
0x1800a4b3a  lea     rbp, [rax-5Fh]
0x1800a4b3e  sub     rsp, 0D0h
0x1800a4b45  lea     rax, [rbp+57h+var_B0]
0x1800a4b49  xor     edi, edi
0x1800a4b4b  mov     r12, r8
0x1800a4b4e  mov     [rbp+57h+var_C0], rax
0x1800a4b52  lea     rax, [rbp+57h+var_B0]
0x1800a4b56  mov     r13, rdx
0x1800a4b59  mov     rbx, rcx
0x1800a4b5c  mov     [rbp+57h+var_B8], rax
0x1800a4b60  mov     [rbp+57h+var_B0], di
0x1800a4b64  cmp     [rdx+0E0h], dil
0x1800a4b6b  jz      short loc_1800A4BD0
0x1800a4b6d  lea     rax, [rdx+90h]
0x1800a4b74  mov     r8, [rax+10h]
0x1800a4b78  cmp     r8, rax
0x1800a4b7b  jz      short loc_1800A4BD0
0x1800a4b7d  mov     rdx, [r8+18h]
0x1800a4b81  lea     rcx, [rbp+57h+var_C0]
0x1800a4b85  mov     r8, [r8+20h]
0x1800a4b89  sub     r8, rdx
0x1800a4b8c  sar     r8, 1
0x1800a4b8f  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800a4b94  test    al, al
0x1800a4b96  jnz     short loc_1800A4BD0
0x1800a4b98  mov     rcx, [rbp+5Fh]; this
0x1800a4b9c  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a4ba3  mov     r9d, 8007000Eh; char *
0x1800a4ba9  mov     edx, 14B3h; void *
0x1800a4bae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4bb3  mov     rcx, [rbp+57h+var_C0]
0x1800a4bb7  lea     rax, [rbp+57h+var_B0]
0x1800a4bbb  cmp     rcx, rax
0x1800a4bbe  jz      loc_1800A553C
0x1800a4bc4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800a4bcb  jmp     loc_1800A5537
0x1800a4bd0  lea     rsi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800a4bd7  mov     ecx, 138h; unsigned __int64
0x1800a4bdc  mov     rdx, rsi; struct std::nothrow_t *
0x1800a4bdf  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800a4be4  mov     r14, rax
0x1800a4be7  test    rax, rax
0x1800a4bea  jz      loc_1800A550C
0x1800a4bf0  mov     [rax], dil
0x1800a4bf3  lea     rcx, [r14+30h]; void *
0x1800a4bf7  xorps   xmm0, xmm0
0x1800a4bfa  xor     eax, eax
0x1800a4bfc  movups  xmmword ptr [r14+8], xmm0
0x1800a4c01  xor     edx, edx; Val
0x1800a4c03  mov     r8d, 0C0h; Size
0x1800a4c09  movups  xmmword ptr [r14+18h], xmm0
0x1800a4c0e  mov     [r14+28h], rax
0x1800a4c12  call    memset_0
0x1800a4c17  xorps   xmm0, xmm0
0x1800a4c1a  mov     [rbp+57h+var_60], r14
0x1800a4c1e  movups  xmmword ptr [r14+0F0h], xmm0
0x1800a4c26  lea     r15, [r14+8]
0x1800a4c2a  mov     rdx, r13; struct Container::Manager::Hcs::MappedFolderConfiguration *
0x1800a4c2d  movups  xmmword ptr [r14+100h], xmm0
0x1800a4c35  mov     rcx, r15; this
0x1800a4c38  movups  xmmword ptr [r14+110h], xmm0
0x1800a4c40  mov     [r14+120h], rdi
0x1800a4c47  mov     [r14+128h], rdi
0x1800a4c4e  mov     [r14+130h], edi
0x1800a4c55  call    ?Assign@MappedFolderConfiguration@Hcs@Manager@Container@@QEAA_NAEBV1234@@Z; Container::Manager::Hcs::MappedFolderConfiguration::Assign(Container::Manager::Hcs::MappedFolderConfiguration const &)
0x1800a4c5a  test    al, al
0x1800a4c5c  jnz     short loc_1800A4CAE
0x1800a4c5e  mov     rcx, [rbp+5Fh]; this
0x1800a4c62  lea     r8, aOnecoreBaseGen_79; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a4c69  mov     r9d, 8007000Eh; char *
0x1800a4c6f  mov     edx, 57Eh; void *
0x1800a4c74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4c79  mov     rcx, [rbp+5Fh]; this
0x1800a4c7d  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a4c84  mov     r9d, 8007000Eh; char *
0x1800a4c8a  mov     edx, 14BAh; void *
0x1800a4c8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4c94  mov     rcx, r15; this
0x1800a4c97  call    ??1MappedFolderConfiguration@Hcs@Manager@Container@@QEAA@XZ; Container::Manager::Hcs::MappedFolderConfiguration::~MappedFolderConfiguration(void)
0x1800a4c9c  mov     edx, 138h; struct std::nothrow_t *
0x1800a4ca1  mov     rcx, r14; void *
0x1800a4ca4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a4ca9  jmp     loc_1800A5527
0x1800a4cae  lea     rdx, [r13+28h]
0x1800a4cb2  mov     rdi, rdx
0x1800a4cb5  lea     rax, [rbp+57h+var_D0]
0x1800a4cb9  mov     [rsp+100h+var_E0], rax; int
0x1800a4cbe  lea     rax, [rbp+57h+var_D0]
0x1800a4cc2  mov     [rsp+28h], rax
0x1800a4cc7  xor     eax, eax
0x1800a4cc9  mov     [rbp+57h+var_D0], ax
0x1800a4ccd  cmp     [r13+20h], al
0x1800a4cd1  jnz     short loc_1800A4CD8
0x1800a4cd3  int     2Ch; Windows NT - assertion failure
0x1800a4cd5  mov     rdi, rdx
0x1800a4cd8  mov     r8, [r13+8]
0x1800a4cdc  lea     rcx, [rsp+100h+var_E0]
0x1800a4ce1  sub     r8, [r13+0]
0x1800a4ce5  mov     rdx, [r13+0]
0x1800a4ce9  sar     r8, 1
0x1800a4cec  mov     [rbp+57h+var_78], rdi
0x1800a4cf0  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800a4cf5  test    al, al
0x1800a4cf7  jz      loc_1800A54A0
0x1800a4cfd  lea     rax, [rbp+57h+var_88]
0x1800a4d01  mov     r8, rdi
0x1800a4d04  mov     [rbp+57h+var_98], rax
0x1800a4d08  lea     rcx, [rbp+57h+var_98]
0x1800a4d0c  lea     rax, [rbp+57h+var_88]
0x1800a4d10  mov     [rbp+57h+var_90], rax
0x1800a4d14  xor     eax, eax
0x1800a4d16  cmp     byte ptr [r13+0E0h], 0
0x1800a4d1e  mov     [rbp+57h+var_88], ax
0x1800a4d22  lea     rax, [r13+0E8h]
0x1800a4d29  cmovz   r8, rax
0x1800a4d2d  mov     rdx, [r8]
0x1800a4d30  mov     r8, [r8+8]
0x1800a4d34  sub     r8, rdx
0x1800a4d37  sar     r8, 1
0x1800a4d3a  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800a4d3f  test    al, al
0x1800a4d41  jz      loc_1800A5496
0x1800a4d47  lea     rax, [rbx+2E0h]
0x1800a4d4e  mov     rcx, rax
0x1800a4d51  mov     [rbp+57h+var_A0], rax
0x1800a4d55  lea     rdx, [rsp+100h+var_E0]
0x1800a4d5a  call    ??$_FindImpl@VPath@Csl@@@?$_Tree@VPath@Csl@@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@VPath@Csl@@@4@V?$allocator@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@4@$0A@@utl@@AEBAPEAU?$_TreeNode@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@1@AEBVPath@Csl@@@Z; utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>,0>::_FindImpl<Csl::Path>(Csl::Path const &)
0x1800a4d5f  mov     rbx, rax
0x1800a4d62  cmp     rax, [rbp+57h+var_A0]
0x1800a4d66  jnz     loc_1800A4E14
0x1800a4d6c  mov     rdi, [rbp+57h+var_A0]
0x1800a4d70  cmp     [rdi+10h], rdi
0x1800a4d74  jnz     short loc_1800A4DB2
0x1800a4d76  lea     r8, [rsp+100h+var_E0]
0x1800a4d7b  call    ??$_NewNodeConstruct@U_PairMapTag@utl@@VPath@Csl@@@?$_Tree@VPath@Csl@@U?$pair@$$CBVPath@Csl@@V?$map@VPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@U?$less@VPath@Csl@@@utl@@V?$allocator@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@6@@utl@@@utl@@U?$less@VPath@Csl@@@4@V?$allocator@U?$pair@$$CBVPath@Csl@@V?$map@VPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@U?$less@VPath@Csl@@@utl@@V?$allocator@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@6@@utl@@@utl@@@4@$0A@@utl@@AEAAPEAU?$_TreeNode@U?$pair@$$CBVPath@Csl@@V?$map@VPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@U?$less@VPath@Csl@@@utl@@V?$allocator@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@6@@utl@@@utl@@@1@$$QEAU_PairMapTag@1@$$QEAVPath@Csl@@@Z; utl::_Tree<Csl::Path,utl::pair<Csl::Path const,utl::map<Csl::Path,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,utl::map<Csl::Path,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>>>>,0>::_NewNodeConstruct<utl::_PairMapTag,Csl::Path>(utl::_PairMapTag &&,Csl::Path &&)
0x1800a4d80  mov     rbx, rax
0x1800a4d83  test    rax, rax
0x1800a4d86  jz      short loc_1800A4DF2
0x1800a4d88  mov     rax, rdi
0x1800a4d8b  or      rax, 1
0x1800a4d8f  mov     [rbx], rax
0x1800a4d92  lea     rax, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x1800a4d99  mov     [rbx+8], rax
0x1800a4d9d  mov     [rbx+10h], rax
0x1800a4da1  mov     [rdi], rbx
0x1800a4da4  mov     [rdi+8], rbx
0x1800a4da8  mov     [rdi+10h], rbx
0x1800a4dac  inc     qword ptr [rdi+18h]
0x1800a4db0  jmp     short loc_1800A4E05
0x1800a4db2  lea     r9, [rsp+100h+var_E0]
0x1800a4db7  mov     [rbp+57h+arg_18], 0
0x1800a4dbf  lea     r8, [rbp+57h+arg_18]
0x1800a4dc3  mov     rcx, rdi
0x1800a4dc6  lea     rdx, [rbp+57h+var_48]
0x1800a4dca  call    ?_FindInsertionPointUniqueUpper@?$_Tree@VPath@Csl@@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@VPath@Csl@@@4@V?$allocator@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@4@$0A@@utl@@AEAA?AU?$pair@PEAU?$_TreeNode@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@_N@2@AEAPEAU?$_TreeNode@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@2@AEBVPath@Csl@@@Z; utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>,0>::_FindInsertionPointUniqueUpper(utl::_TreeNode<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>> * &,Csl::Path const &)
0x1800a4dcf  mov     rbx, [rbp+57h+arg_18]
0x1800a4dd3  movups  xmm0, xmmword ptr [rax]
0x1800a4dd6  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x1800a4ddb  test    rbx, rbx
0x1800a4dde  jnz     short loc_1800A4E0E
0x1800a4de0  lea     r8, [rsp+100h+var_E0]
0x1800a4de5  call    ??$_NewNodeConstruct@U_PairMapTag@utl@@VPath@Csl@@@?$_Tree@VPath@Csl@@U?$pair@$$CBVPath@Csl@@V?$map@VPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@U?$less@VPath@Csl@@@utl@@V?$allocator@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@6@@utl@@@utl@@U?$less@VPath@Csl@@@4@V?$allocator@U?$pair@$$CBVPath@Csl@@V?$map@VPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@U?$less@VPath@Csl@@@utl@@V?$allocator@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@6@@utl@@@utl@@@4@$0A@@utl@@AEAAPEAU?$_TreeNode@U?$pair@$$CBVPath@Csl@@V?$map@VPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@U?$less@VPath@Csl@@@utl@@V?$allocator@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@6@@utl@@@utl@@@1@$$QEAU_PairMapTag@1@$$QEAVPath@Csl@@@Z; utl::_Tree<Csl::Path,utl::pair<Csl::Path const,utl::map<Csl::Path,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,utl::map<Csl::Path,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>>>>,0>::_NewNodeConstruct<utl::_PairMapTag,Csl::Path>(utl::_PairMapTag &&,Csl::Path &&)
0x1800a4dea  mov     rbx, rax
0x1800a4ded  test    rax, rax
0x1800a4df0  jnz     short loc_1800A4DF6
0x1800a4df2  xor     ebx, ebx
0x1800a4df4  jmp     short loc_1800A4E05
0x1800a4df6  mov     r8, rax
0x1800a4df9  lea     rdx, [rbp+57h+var_70]
0x1800a4dfd  mov     rcx, rdi
0x1800a4e00  call    ?_InsertAt@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@W4NetworkType@Hns@Manager@Container@@@utl@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@W4NetworkType@Hns@Manager@Container@@@utl@@@3@$0A@@utl@@AEAAXAEBU?$pair@PEAU?$_TreeNode@U?$pair@$$CBU_GUID@@W4NetworkType@Hns@Manager@Container@@@utl@@@utl@@_N@2@PEAU?$_TreeNode@U?$pair@$$CBU_GUID@@W4NetworkType@Hns@Manager@Container@@@utl@@@2@@Z; utl::_Tree<_GUID,utl::pair<_GUID const,Container::Manager::Hns::NetworkType>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,Container::Manager::Hns::NetworkType>>,0>::_InsertAt(utl::pair<utl::_TreeNode<utl::pair<_GUID const,Container::Manager::Hns::NetworkType>> *,bool> const &,utl::_TreeNode<utl::pair<_GUID const,Container::Manager::Hns::NetworkType>> *)
0x1800a4e05  test    rbx, rbx
0x1800a4e08  jz      loc_1800A4FAD
0x1800a4e0e  mov     byte ptr [rbp+57h+arg_18], 1
0x1800a4e12  jmp     short loc_1800A4E70
0x1800a4e14  xor     edx, edx
0x1800a4e16  add     rax, 38h ; '8'
0x1800a4e1a  mov     byte ptr [rbp+57h+arg_18], dl
0x1800a4e1d  cmp     [rax+10h], rax
0x1800a4e21  jz      short loc_1800A4E6C
0x1800a4e23  cmp     [r13+0E0h], dl
0x1800a4e2a  jz      short loc_1800A4E6C
0x1800a4e2c  mov     rax, [rbx+48h]
0x1800a4e30  mov     rcx, [rax+38h]
0x1800a4e34  cmp     [rcx+0E8h], dl
0x1800a4e3a  jz      short loc_1800A4E59
0x1800a4e3c  cmp     [rcx+50h], dl
0x1800a4e3f  jz      short loc_1800A4E59
0x1800a4e41  cmp     [rdi+0B8h], dl
0x1800a4e47  jnz     short loc_1800A4E4B
0x1800a4e49  int     2Ch; Windows NT - assertion failure
0x1800a4e4b  lea     rax, [rdi+68h]
0x1800a4e4f  cmp     [rax+10h], rax
0x1800a4e53  jz      loc_1800A4FE6
0x1800a4e59  cmp     [rdi+0B8h], dl
0x1800a4e5f  jnz     short loc_1800A4E63
0x1800a4e61  int     2Ch; Windows NT - assertion failure
0x1800a4e63  cmp     [rdi+20h], dl
0x1800a4e66  jnz     loc_1800A4FED
0x1800a4e6c  mov     rdi, [rbp+57h+var_A0]
0x1800a4e70  lea     rcx, [rbx+38h]
0x1800a4e74  lea     rdx, [rbp+57h+var_98]
0x1800a4e78  call    ??$_FindImpl@VPath@Csl@@@?$_Tree@VPath@Csl@@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@VPath@Csl@@@4@V?$allocator@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@4@$0A@@utl@@AEBAPEAU?$_TreeNode@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@1@AEBVPath@Csl@@@Z; utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>,0>::_FindImpl<Csl::Path>(Csl::Path const &)
0x1800a4e7d  lea     rcx, [rbx+38h]
0x1800a4e81  cmp     rax, rcx
0x1800a4e84  jz      loc_1800A5156
0x1800a4e8a  mov     rdi, [rax+38h]
0x1800a4e8e  xor     ebx, ebx
0x1800a4e90  cmp     [rdi+0E8h], bl
0x1800a4e96  jz      loc_1800A5116
0x1800a4e9c  mov     rcx, [rbp+57h+var_78]; this
0x1800a4ea0  cmp     [r13+0E0h], bl
0x1800a4ea7  jz      short loc_1800A4EC1
0x1800a4ea9  cmp     [rcx+0B8h], bl
0x1800a4eaf  jnz     short loc_1800A4EB3
0x1800a4eb1  int     2Ch; Windows NT - assertion failure
0x1800a4eb3  lea     rax, [rcx+68h]
0x1800a4eb7  cmp     [rax+10h], rax
0x1800a4ebb  jz      loc_1800A5116
0x1800a4ec1  lea     rdx, [rdi+30h]; struct Container::Manager::Hcs::VsmbShareConfiguration *
0x1800a4ec5  cmp     [rdx+0B8h], bl
0x1800a4ecb  jnz     short loc_1800A4ECF
0x1800a4ecd  int     2Ch; Windows NT - assertion failure
0x1800a4ecf  lea     rax, [rdx+68h]
0x1800a4ed3  cmp     [rax+10h], rax
0x1800a4ed7  jnz     short loc_1800A4EE2
0x1800a4ed9  cmp     [rdx+20h], bl
0x1800a4edc  jz      loc_1800A5068
0x1800a4ee2  lea     rax, [rcx+0B8h]
0x1800a4ee9  mov     [rbp+57h+var_70], rax
0x1800a4eed  cmp     [rax], bl
0x1800a4eef  jnz     short loc_1800A4EF3
0x1800a4ef1  int     2Ch; Windows NT - assertion failure
0x1800a4ef3  call    ?CanOverlayWith@VsmbShareConfiguration@Hcs@Manager@Container@@QEBA_NAEBU1234@@Z; Container::Manager::Hcs::VsmbShareConfiguration::CanOverlayWith(Container::Manager::Hcs::VsmbShareConfiguration const &)
0x1800a4ef8  test    al, al
0x1800a4efa  jz      loc_1800A510C
0x1800a4f00  cmp     byte ptr [rdi], 0
0x1800a4f03  mov     edx, 1
0x1800a4f08  mov     byte ptr [rbp+57h+arg_18], dl
0x1800a4f0b  mov     rbx, rdi
0x1800a4f0e  jz      loc_1800A506F
0x1800a4f14  lea     rcx, [rdi+128h]; this
0x1800a4f1b  mov     [rbp+57h+arg_18], 0
0x1800a4f23  lea     rdx, [rbp+57h+arg_18]; struct Csl::RundownProtection *
0x1800a4f27  call    ?TryAcquireRundownProtection@RundownReference@Csl@@QEAA_NAEAVRundownProtection@2@@Z; Csl::RundownReference::TryAcquireRundownProtection(Csl::RundownProtection &)
0x1800a4f2c  mov     rax, [r12]
0x1800a4f30  lea     rcx, [rdi+120h]; ConditionVariable
0x1800a4f37  xor     r9d, r9d; Flags
0x1800a4f3a  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x1800a4f3e  mov     dword ptr [rax+8], 0
0x1800a4f45  mov     rdx, [r12]; SRWLock
0x1800a4f49  call    cs:__imp_SleepConditionVariableSRW
0x1800a4f50  nop     dword ptr [rax+rax+00h]
0x1800a4f55  call    cs:__imp_GetCurrentThreadId
0x1800a4f5c  nop     dword ptr [rax+rax+00h]
0x1800a4f61  mov     rcx, [r12]
0x1800a4f65  mov     [rcx+8], eax
0x1800a4f68  lea     rcx, [rbp+57h+arg_18]; this
0x1800a4f6c  call    ?Reset@RundownProtection@Csl@@QEAAXXZ; Csl::RundownProtection::Reset(void)
0x1800a4f71  mov     rcx, [rbp+57h+var_98]; void *
0x1800a4f75  lea     rax, [rbp+57h+var_88]
0x1800a4f79  cmp     rcx, rax
0x1800a4f7c  jz      short loc_1800A4F86
0x1800a4f7e  mov     rdx, rsi; struct std::nothrow_t *
0x1800a4f81  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a4f86  mov     rcx, [rsp+100h+var_E0]; void *
0x1800a4f8b  lea     rax, [rbp+57h+var_D0]
0x1800a4f8f  cmp     rcx, rax
0x1800a4f92  jz      short loc_1800A4F9C
0x1800a4f94  mov     rdx, rsi; struct std::nothrow_t *
0x1800a4f97  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a4f9c  mov     rdi, [rbp+57h+var_78]
0x1800a4fa0  lea     rdx, [r13+28h]
0x1800a4fa4  mov     rbx, [rbp+57h+arg_0]
0x1800a4fa8  jmp     loc_1800A4CB5
0x1800a4fad  mov     edx, 14D6h; void *
0x1800a4fb2  mov     rcx, [rbp+5Fh]; this
0x1800a4fb6  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a4fbd  mov     r9d, 8007000Eh; char *
0x1800a4fc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4fc8  mov     rcx, [rbp+57h+var_98]; void *
0x1800a4fcc  lea     rax, [rbp+57h+var_88]
0x1800a4fd0  cmp     rcx, rax
0x1800a4fd3  jz      loc_1800A54BB
0x1800a4fd9  mov     rdx, rsi; struct std::nothrow_t *
0x1800a4fdc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a4fe1  jmp     loc_1800A54BB
0x1800a4fe6  mov     edx, 14EEh
0x1800a4feb  jmp     short loc_1800A4FF2
  ... truncated ...
```
