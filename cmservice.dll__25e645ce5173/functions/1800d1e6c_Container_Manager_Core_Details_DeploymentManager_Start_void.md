# Container::Manager::Core::Details::DeploymentManager::Start(void)

- ea: `0x1800d1e6c`
- end: `0x1800d28d3`
- name: `?Start@DeploymentManager@Details@Core@Manager@Container@@QEAAJXZ`
- size: `2663`
- prototype: `__int64 __fastcall(Container::Manager::Core::Details::DeploymentManager *__hidden this)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180075fb8`

## callees

- `0x180004bd0`
- `0x180004fc4`
- `0x18000a10c`
- `0x18000da88`
- `0x18002d070`
- `0x180032d0c`
- `0x18003943c`
- `0x18003bb80`
- `0x18004feb4`
- `0x180057b10`
- `0x180058bdc`
- `0x18005a30c`
- `0x18005d0d4`
- `0x1800606e8`
- `0x18008b908`
- `0x1800cf700`
- `0x1800cfccc`
- `0x1800d1e6c`
- `0x1800daee8`
- `0x1800ec978`
- `0x1800ecf4c`
- `0x1800fb024`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d27a6`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d27a6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d260b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d2781`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d260b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d2781`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d2666`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d274c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d27bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d2666`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d274c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d27bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800d2224`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800d22ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800d2329`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800d238b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800d2224`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800d22ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800d2329`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800d238b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800d2206`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800d2280`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800d22ee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800d2206`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800d2280`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800d22ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d2617`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d2617`

## string_xrefs

- `0x1800d289a`: `onecore\base\gendrv\silos\clem\core\lib\ResourceBroker.h`
- `0x1800d28ac`: `onecore\base\gendrv\silos\clem\core\lib\ResourceBroker.h`
- `0x1800d2888`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::DeploymentManager::Start(
        Container::Manager::Core::Details::DeploymentManager *this)
{
  Csl::RegistryKey *v1; // r15
  __int64 v2; // rcx
  int v3; // eax
  int WimPath; // edi
  void *v5; // rcx
  void *v6; // rbx
  __int64 v8; // rdx
  _BYTE *v9; // r12
  Container::Manager::Core::ResourceHandle **v10; // rbx
  Container::Manager::Core::ResourceHandle **i; // rdi
  __int64 v12; // rax
  __int64 v13; // r14
  int v14; // esi
  int Validity; // esi
  __int64 v16; // rcx
  __int64 v17; // rcx
  struct _GUID *Id; // rax
  bool v19; // r9
  Container::Manager::Core::ResourceHandle *v20; // rsi
  struct _GUID v21; // xmm0
  __int64 v22; // rdx
  void *v23; // rcx
  __int64 v24; // rcx
  int v25; // eax
  __int64 v26; // rcx
  void *v27; // rdi
  __int64 v28; // rdi
  _BYTE *v29; // r13
  const struct Container::Manager::Core::ResourceHandle **v30; // rdi
  const struct Container::Manager::Core::ResourceHandle **j; // rsi
  __int64 v32; // rax
  __int64 v33; // r14
  __int64 v34; // rax
  __int64 v35; // r14
  int IsValidLocked; // eax
  unsigned int v37; // r14d
  int v38; // eax
  unsigned __int64 v39; // r9
  __int64 v40; // rdx
  __int64 v41; // rcx
  void *v42; // rcx
  __int64 v43; // rcx
  int v44; // eax
  const char *v45; // r9
  void *v46; // rsi
  void *v47; // rcx
  Container::Manager::Core::ResourceHandle **v48; // r14
  Container::Manager::Core::ResourceHandle **v49; // rsi
  RTL_SRWLOCK *v50; // r15
  char IsHotPatchUpdateRequired; // r15
  struct _GUID *v52; // rax
  bool v53; // r9
  Container::Manager::Core::ResourceHandle *v54; // r15
  struct _GUID v55; // xmm0
  int InitialDeploymentProfiles; // eax
  __int64 v57; // rdx
  void *v58; // r15
  char *v59; // r14
  DWORD CurrentThreadId; // eax
  Csl::RegistryKey *v61; // rcx
  int v62; // eax
  __int64 v63; // rcx
  void *v64; // r15
  void *v65; // rcx
  __int64 v66; // r14
  bool v67; // zf
  RTL_SRWLOCK *v68; // rcx
  void *v69; // r15
  void *v70; // rcx
  int v71; // [rsp+20h] [rbp-89h] BYREF
  _DWORD v72[3]; // [rsp+24h] [rbp-85h] BYREF
  void *v73[2]; // [rsp+30h] [rbp-79h] BYREF
  __int64 v74; // [rsp+40h] [rbp-69h]
  void *v75; // [rsp+48h] [rbp-61h] BYREF
  char *v76; // [rsp+50h] [rbp-59h]
  _WORD v77[8]; // [rsp+58h] [rbp-51h] BYREF
  void *v78[2]; // [rsp+68h] [rbp-41h] BYREF
  _WORD v79[8]; // [rsp+78h] [rbp-31h] BYREF
  Csl::RegistryKey *v80; // [rsp+88h] [rbp-21h]
  struct _GUID si128; // [rsp+90h] [rbp-19h] BYREF
  __int64 v82; // [rsp+A0h] [rbp-9h]
  struct _GUID v83; // [rsp+A8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v80 = this;
  v1 = this;
  v74 = -1;
  v2 = *((_QWORD *)this + 1);
  *(__m128i *)v73 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v3 = Container::Manager::Core::Details::ResourceBroker::EnumerateResourceHandles(
         v2,
         5,
         L"DeploymentManager_Start_BaseImages",
         v73);
  WimPath = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA8,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\deployment.cpp",
      (const char *)(unsigned int)v3,
      v71);
    v6 = v73[0];
    if ( v73[0] == (void *)-1LL )
      return (unsigned int)WimPath;
LABEL_3:
    utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(
      v5,
      v73[0],
      ((char *)v73[1] - (char *)v73[0]) >> 3);
    operator delete(v6, (const struct std::nothrow_t *)&std::nothrow);
    return (unsigned int)WimPath;
  }
  v78[0] = v79;
  v78[1] = v79;
  v79[0] = 0;
  WimPath = Container::Manager::Core::Details::DeploymentManager::GetWimPath(v1, (struct Path *)v78);
  v77[0] = 0;
  v75 = v77;
  v76 = (char *)v77;
  if ( (unsigned int)(WimPath + 2147024894) > 1 )
  {
    if ( WimPath < 0 )
    {
      v8 = 180;
      goto LABEL_8;
    }
    WimPath = Container::Manager::Core::Details::BaseImage::GetWimOsVersion(v78, &v75);
    if ( WimPath < 0 )
    {
      v8 = 182;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\deployment.cpp",
        (const char *)(unsigned int)WimPath,
        v71);
      if ( v75 != v77 )
        operator delete(v75, (const struct std::nothrow_t *)&std::nothrow);
      v5 = v78[0];
      if ( v78[0] != v79 )
        operator delete(v78[0], (const struct std::nothrow_t *)&std::nothrow);
      v6 = v73[0];
      if ( v73[0] == (void *)-1LL )
        return (unsigned int)WimPath;
      goto LABEL_3;
    }
  }
  v9 = v73[0];
  v10 = (Container::Manager::Core::ResourceHandle **)v73[1];
  for ( i = (Container::Manager::Core::ResourceHandle **)v73[0]; i != v10; ++i )
  {
    if ( *((_DWORD *)*i + 8) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x10A,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\inc\\CmCore.h",
        (const char *)retaddr);
    v12 = *((_QWORD *)*i + 5);
    if ( *(_DWORD *)(v12 + 16) != 5 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x71,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\ResourceBroker.h",
        (const char *)retaddr);
    if ( !*(_BYTE *)(v12 + 104) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x72,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\ResourceBroker.h",
        (const char *)retaddr);
    v13 = *(_QWORD *)(v12 + 96);
    v14 = 0;
    v72[0] = 0;
    if ( *(_DWORD *)(v13 + 136) == 2 )
    {
      Validity = Container::Manager::Core::Details::BaseImage::GetValidity(
                   (Container::Manager::Core::Details::BaseImage *)v13,
                   (enum Container::Manager::Core::Details::BaseImageValidity *)v72);
      if ( Validity < 0 )
      {
        v22 = 196;
        goto LABEL_32;
      }
      v14 = v72[0];
    }
    if ( v75 != v76 )
    {
      v73[0] = v75;
      v16 = *(_QWORD *)(v13 + 104);
      v73[1] = (void *)((v76 - (_BYTE *)v75) >> 1);
      v17 = v16 - *(_QWORD *)(v13 + 96);
      *(_QWORD *)&v83.Data1 = *(_QWORD *)(v13 + 96);
      *(_QWORD *)v83.Data4 = v17 >> 1;
      if ( (unsigned __int8)Csl::StringEqualIgnoreCase(&v83, v73) )
      {
        if ( !v14 )
          continue;
      }
    }
    Id = (struct _GUID *)Container::Manager::Core::ResourceHandle::GetId(*i);
    v20 = *i;
    v21 = *Id;
    *i = 0;
    si128 = v21;
    if ( v20 )
    {
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v20);
      operator delete(v20, (const struct std::nothrow_t *)0x58);
    }
    Validity = Container::Manager::Core::Details::ResourceBroker::DeleteResourceTree(
                 *((Container::Manager::Core::Details::ResourceBroker **)v1 + 1),
                 &si128,
                 (enum ResourceType)5,
                 v19);
    if ( Validity < 0 )
    {
      v22 = 215;
LABEL_32:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\deployment.cpp",
        (const char *)(unsigned int)Validity,
        v71);
LABEL_33:
      if ( v75 != v77 )
        operator delete(v75, (const struct std::nothrow_t *)&std::nothrow);
      v23 = v78[0];
      if ( v78[0] != v79 )
        operator delete(v78[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v9 != (_BYTE *)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(
          v23,
          v9,
          ((char *)v10 - v9) >> 3);
        operator delete(v9, (const struct std::nothrow_t *)&std::nothrow);
      }
      return (unsigned int)Validity;
    }
  }
  v24 = *((_QWORD *)v1 + 1);
  v74 = -1;
  *(__m128i *)v73 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v25 = Container::Manager::Core::Details::ResourceBroker::EnumerateResourceHandles(
          v24,
          2,
          L"DeploymentManager_Start_Layers",
          v73);
  Validity = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDF,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\deployment.cpp",
      (const char *)(unsigned int)v25,
      v71);
    v27 = v73[0];
    if ( v73[0] != (void *)-1LL )
    {
      utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(
        v26,
        v73[0],
        ((char *)v73[1] - (char *)v73[0]) >> 3);
      operator delete(v27, (const struct std::nothrow_t *)&std::nothrow);
    }
    goto LABEL_33;
  }
  v28 = *((_QWORD *)v1 + 3);
  AcquireSRWLockShared((PSRWLOCK)(v28 + 40));
  v72[0] = *(_DWORD *)(v28 + 832);
  if ( v28 != -40 )
    ReleaseSRWLockShared((PSRWLOCK)(v28 + 40));
  v29 = v73[0];
  v30 = (const struct Container::Manager::Core::ResourceHandle **)v73[1];
  for ( j = (const struct Container::Manager::Core::ResourceHandle **)v73[0]; j != v30; ++j )
  {
    v32 = Container::Manager::Core::ResourceHandle::Get<Container::Manager::Core::Details::Layer>(*j);
    if ( *(_BYTE *)(v32 + 680) )
    {
      v33 = *((_QWORD *)v1 + 5);
      *(_QWORD *)&si128.Data1 = v32 + 384;
      BYTE1(v71) = 0;
      *(_QWORD *)&v72[1] = 0;
      v73[0] = *(void **)(v32 + 448);
      AcquireSRWLockShared((PSRWLOCK)v33);
      if ( !*(_BYTE *)(v33 + 153) || (LOBYTE(v71) = 1, !*(_BYTE *)(v33 + 152)) )
        LOBYTE(v71) = 0;
      ReleaseSRWLockShared((PSRWLOCK)v33);
      if ( (_BYTE)v71 && (*((_BYTE *)v73[0] + 228) & 2) != 0 )
      {
        v34 = *((_QWORD *)v1 + 5);
        LOBYTE(v83.Data2) = 1;
        v83.Data1 = *(_DWORD *)(v34 + 156);
        *(_QWORD *)&v72[1] = *(_QWORD *)&v83.Data1;
      }
      v35 = *(_QWORD *)&si128.Data1;
      AcquireSRWLockShared((PSRWLOCK)(*(_QWORD *)&si128.Data1 + 72LL));
      IsValidLocked = Container::Manager::Core::Details::SpecializationLayer::IsValidLocked(
                        v35,
                        &v72[1],
                        *((_QWORD *)v1 + 5) + 56LL,
                        (char *)&v71 + 1);
      v72[1] = IsValidLocked;
      v37 = IsValidLocked;
      if ( IsValidLocked < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x23C,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
          (const char *)(unsigned int)IsValidLocked,
          v71);
        if ( *(_QWORD *)&si128.Data1 != -72 )
          ReleaseSRWLockShared((PSRWLOCK)(*(_QWORD *)&si128.Data1 + 72LL));
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x79E,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
          (const char *)v37,
          v71);
        v39 = v37;
        v40 = 235;
        goto LABEL_65;
      }
      if ( *(_QWORD *)&si128.Data1 != -72 )
        ReleaseSRWLockShared((PSRWLOCK)(*(_QWORD *)&si128.Data1 + 72LL));
      if ( !BYTE1(v71) )
        goto LABEL_60;
    }
    if ( (v72[0] & 1) != 0 )
    {
LABEL_60:
      v38 = Container::Manager::Core::Details::ResourceBroker::RecreateLayerStorage(*((RTL_SRWLOCK **)v1 + 1), *j);
      v72[1] = v38;
      if ( v38 < 0 )
      {
        v39 = (unsigned int)v38;
        v40 = 239;
LABEL_65:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v40,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\deployment.cpp",
          (const char *)v39,
          v71);
        goto LABEL_66;
      }
    }
  }
  v43 = *((_QWORD *)v1 + 1);
  v82 = -1;
  si128 = (struct _GUID)_mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v44 = Container::Manager::Core::Details::ResourceBroker::EnumerateResourceHandles(
          v43,
          3,
          L"DeploymentManager_Start_Snapshots",
          &si128);
  v72[1] = v44;
  if ( v44 >= 0 )
  {
    v48 = *(Container::Manager::Core::ResourceHandle ***)&si128.Data1;
    v49 = *(Container::Manager::Core::ResourceHandle ***)si128.Data4;
    while ( v48 != v49 )
    {
      if ( *((_DWORD *)*v48 + 8) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xEF,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
          v45);
      if ( *(_DWORD *)(*((_QWORD *)*v48 + 5) + 20LL) == 1 )
      {
        v50 = (RTL_SRWLOCK *)*((_QWORD *)v1 + 5);
        v73[0] = *(void **)(Container::Manager::Core::ResourceHandle::Get<Container::Manager::Core::Details::Snapshot>(*v48)
                          + 112);
        IsHotPatchUpdateRequired = Container::Manager::Core::Details::SystemConfigurationManager::IsHotPatchUpdateRequired(v50);
        if ( !Container::Manager::Core::ResourceHandle::IsMaterialized(*v48)
          || IsHotPatchUpdateRequired
          || (v72[0] & 2) != 0 )
        {
          v52 = (struct _GUID *)Container::Manager::Core::ResourceHandle::GetId(*v48);
          v54 = *v48;
          v55 = *v52;
          *v48 = 0;
          v83 = v55;
          if ( v54 )
          {
            Container::Manager::Core::ResourceHandle::~ResourceHandle(v54);
            operator delete(v54, (const struct std::nothrow_t *)0x58);
          }
          v1 = v80;
          InitialDeploymentProfiles = Container::Manager::Core::Details::ResourceBroker::DeleteResourceTree(
                                        *((Container::Manager::Core::Details::ResourceBroker **)v80 + 1),
                                        &v83,
                                        (enum ResourceType)3,
                                        v53);
          v72[1] = InitialDeploymentProfiles;
          if ( InitialDeploymentProfiles < 0 )
          {
            v57 = 272;
            goto LABEL_91;
          }
        }
        else
        {
          v1 = v80;
        }
      }
      ++v48;
    }
    if ( v72[0] )
    {
      v80 = (Csl::RegistryKey *)*((_QWORD *)v1 + 3);
      v59 = (char *)v80 + 40;
      AcquireSRWLockExclusive((PSRWLOCK)v80 + 5);
      CurrentThreadId = GetCurrentThreadId();
      v61 = v80;
      *((_DWORD *)v59 + 2) = CurrentThreadId;
      v62 = Csl::RegistryKey::DeleteValue(v61, L"DeploymentFlags");
      v72[0] = v62;
      if ( v62 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x37D,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\policy.cpp",
          (const char *)(unsigned int)v62,
          v71);
        *((_DWORD *)v59 + 2) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)v59);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x119,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\deployment.cpp",
          (const char *)v72[0],
          v71);
        v64 = *(void **)&si128.Data1;
        if ( *(_QWORD *)&si128.Data1 != -1 )
        {
          utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(
            v63,
            *(_QWORD *)&si128.Data1,
            ((__int64)v49 - *(_QWORD *)&si128.Data1) >> 3);
          operator delete(v64, (const struct std::nothrow_t *)&std::nothrow);
        }
        if ( v29 != (_BYTE *)-1LL )
        {
          utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(
            v63,
            v29,
            ((char *)v30 - v29) >> 3);
          operator delete(v29, (const struct std::nothrow_t *)&std::nothrow);
        }
        if ( v75 != v77 )
          operator delete(v75, (const struct std::nothrow_t *)&std::nothrow);
        v65 = v78[0];
        if ( v78[0] != v79 )
          operator delete(v78[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v9 != (_BYTE *)-1LL )
        {
          utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(
            v65,
            v9,
            ((char *)v10 - v9) >> 3);
          operator delete(v9, (const struct std::nothrow_t *)&std::nothrow);
        }
        return v72[0];
      }
      *((_DWORD *)v80 + 208) = 0;
      *((_DWORD *)v59 + 2) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v59);
    }
    InitialDeploymentProfiles = Container::Manager::Core::Details::DeploymentManager::LoadInitialDeploymentProfiles(
                                  v1,
                                  (char *)v1 + 104);
    v72[1] = InitialDeploymentProfiles;
    if ( InitialDeploymentProfiles >= 0 )
    {
      v66 = **((_QWORD **)v1 + 9);
      AcquireSRWLockExclusive((PSRWLOCK)(v66 + 8));
      v67 = *(_DWORD *)v66 == 2;
      *(_QWORD *)(v66 + 16) = Container::Manager::Core::Details::DeploymentManager::OnUpdatesCompleted;
      *(_QWORD *)(v66 + 24) = v1;
      if ( v67 )
        SubmitThreadpoolWork(*(PTP_WORK *)(v66 + 32));
      v68 = (RTL_SRWLOCK *)(v66 + 8);
      if ( v66 != -8 )
        ReleaseSRWLockExclusive(v68);
      v69 = *(void **)&si128.Data1;
      if ( *(_QWORD *)&si128.Data1 != -1 )
      {
        utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(
          v68,
          *(_QWORD *)&si128.Data1,
          ((__int64)v49 - *(_QWORD *)&si128.Data1) >> 3);
        operator delete(v69, (const struct std::nothrow_t *)&std::nothrow);
      }
      if ( v29 != (_BYTE *)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(
          v68,
          v29,
          ((char *)v30 - v29) >> 3);
        operator delete(v29, (const struct std::nothrow_t *)&std::nothrow);
      }
      if ( v75 != v77 )
        operator delete(v75, (const struct std::nothrow_t *)&std::nothrow);
      v70 = v78[0];
      if ( v78[0] != v79 )
        operator delete(v78[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v9 != (_BYTE *)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(
          v70,
          v9,
          ((char *)v10 - v9) >> 3);
        operator delete(v9, (const struct std::nothrow_t *)&std::nothrow);
      }
      return 0;
    }
    v57 = 285;
LABEL_91:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v57,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\deployment.cpp",
      (const char *)(unsigned int)InitialDeploymentProfiles,
      v71);
    v58 = *(void **)&si128.Data1;
    if ( *(_QWORD *)&si128.Data1 == -1 )
      goto LABEL_66;
    utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(
      v41,
      *(_QWORD *)&si128.Data1,
      ((__int64)v49 - *(_QWORD *)&si128.Data1) >> 3);
    v47 = v58;
    goto LABEL_79;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xF8,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\deployment.cpp",
    (const char *)(unsigned int)v44,
    v71);
  v46 = *(void **)&si128.Data1;
  if ( *(_QWORD *)&si128.Data1 != -1 )
  {
    utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(
      v41,
      *(_QWORD *)&si128.Data1,
      (__int64)(*(_QWORD *)si128.Data4 - *(_QWORD *)&si128.Data1) >> 3);
    v47 = v46;
LABEL_79:
    operator delete(v47, (const struct std::nothrow_t *)&std::nothrow);
  }
LABEL_66:
  if ( v29 != (_BYTE *)-1LL )
  {
    utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(
      v41,
      v29,
      ((char *)v30 - v29) >> 3);
    operator delete(v29, (const struct std::nothrow_t *)&std::nothrow);
  }
  if ( v75 != v77 )
    operator delete(v75, (const struct std::nothrow_t *)&std::nothrow);
  v42 = v78[0];
  if ( v78[0] != v79 )
    operator delete(v78[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v9 != (_BYTE *)-1LL )
  {
    utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(
      v42,
      v9,
      ((char *)v10 - v9) >> 3);
    operator delete(v9, (const struct std::nothrow_t *)&std::nothrow);
  }
  return v72[1];
}

```

## disassembly

```asm
0x1800d1e6c  push    rbp
0x1800d1e6e  push    rbx
0x1800d1e6f  push    rsi
0x1800d1e70  push    rdi
0x1800d1e71  push    r12
0x1800d1e73  push    r13
0x1800d1e75  push    r14
0x1800d1e77  push    r15
0x1800d1e79  lea     rbp, [rsp-1Fh]
0x1800d1e7e  sub     rsp, 0C8h
0x1800d1e85  mov     rax, cs:__security_cookie
0x1800d1e8c  xor     rax, rsp
0x1800d1e8f  mov     [rbp+57h+var_48], rax
0x1800d1e93  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800d1e9b  lea     r9, [rbp+57h+var_D0]
0x1800d1e9f  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800d1ea3  mov     [rbp+57h+var_78], rcx
0x1800d1ea7  mov     r15, rcx
0x1800d1eaa  mov     [rbp+57h+var_C0], r13
0x1800d1eae  mov     rcx, [rcx+8]
0x1800d1eb2  lea     r8, aDeploymentmana_2; "DeploymentManager_Start_BaseImages"
0x1800d1eb9  movdqu  xmmword ptr [rbp+57h+var_D0], xmm0
0x1800d1ebe  lea     edx, [r13+6]
0x1800d1ec2  call    ?EnumerateResourceHandles@ResourceBroker@Details@Core@Manager@Container@@QEAAJW4ResourceType@2345@PEBGAEAV?$vector@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@V?$allocator@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@@Z; Container::Manager::Core::Details::ResourceBroker::EnumerateResourceHandles(Container::Manager::Core::Details::ResourceType,ushort const *,utl::vector<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>> &)
0x1800d1ec7  mov     edi, eax
0x1800d1ec9  test    eax, eax
0x1800d1ecb  jns     short loc_1800D1F17
0x1800d1ecd  mov     rcx, [rbp+5Fh]; this
0x1800d1ed1  lea     r8, aOnecoreBaseGen_23; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800d1ed8  mov     r9d, eax; char *
0x1800d1edb  mov     edx, 0A8h; void *
0x1800d1ee0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d1ee5  mov     rbx, [rbp+57h+var_D0]
0x1800d1ee9  cmp     rbx, r13
0x1800d1eec  jz      short loc_1800D1F10
0x1800d1eee  mov     r8, [rbp+57h+var_D0+8]
0x1800d1ef2  mov     rdx, rbx
0x1800d1ef5  sub     r8, rbx
0x1800d1ef8  sar     r8, 3
0x1800d1efc  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@0@PEAV?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@_K@Z; utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>> &,wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>> *,unsigned __int64)
0x1800d1f01  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800d1f08  mov     rcx, rbx; void *
0x1800d1f0b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d1f10  mov     eax, edi
0x1800d1f12  jmp     loc_1800D2867
0x1800d1f17  lea     rax, [rbp+57h+var_88]
0x1800d1f1b  mov     rcx, r15; this
0x1800d1f1e  mov     [rbp+57h+var_98], rax
0x1800d1f22  lea     rdx, [rbp+57h+var_98]; struct Path *
0x1800d1f26  lea     rax, [rbp+57h+var_88]
0x1800d1f2a  mov     [rbp+57h+var_90], rax
0x1800d1f2e  xor     eax, eax
0x1800d1f30  mov     [rbp+57h+var_88], ax
0x1800d1f34  call    ?GetWimPath@DeploymentManager@Details@Core@Manager@Container@@AEBAJAEAVPath@Csl@@@Z; Container::Manager::Core::Details::DeploymentManager::GetWimPath(Csl::Path &)
0x1800d1f39  mov     edi, eax
0x1800d1f3b  xor     ecx, ecx
0x1800d1f3d  lea     rax, [rbp+57h+var_A8]
0x1800d1f41  mov     [rbp+57h+var_A8], cx
0x1800d1f45  mov     [rbp+57h+var_B8], rax
0x1800d1f49  lea     rax, [rbp+57h+var_A8]
0x1800d1f4d  mov     [rbp+57h+var_B0], rax
0x1800d1f51  lea     ecx, [rdi+7FF8FFFEh]
0x1800d1f57  cmp     ecx, 1
0x1800d1f5a  jbe     loc_1800D1FF2
0x1800d1f60  test    edi, edi
0x1800d1f62  jns     short loc_1800D1FD5
0x1800d1f64  mov     edx, 0B4h; void *
0x1800d1f69  mov     rcx, [rbp+5Fh]; this
0x1800d1f6d  lea     r8, aOnecoreBaseGen_23; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800d1f74  mov     r9d, edi; char *
0x1800d1f77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d1f7c  mov     rcx, [rbp+57h+var_B8]; void *
0x1800d1f80  lea     rax, [rbp+57h+var_A8]
0x1800d1f84  lea     r14, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800d1f8b  cmp     rcx, rax
0x1800d1f8e  jz      short loc_1800D1F98
0x1800d1f90  mov     rdx, r14; struct std::nothrow_t *
0x1800d1f93  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d1f98  mov     rcx, [rbp+57h+var_98]; void *
0x1800d1f9c  lea     rax, [rbp+57h+var_88]
0x1800d1fa0  cmp     rcx, rax
0x1800d1fa3  jz      short loc_1800D1FAD
0x1800d1fa5  mov     rdx, r14; struct std::nothrow_t *
0x1800d1fa8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d1fad  mov     rbx, [rbp+57h+var_D0]
0x1800d1fb1  cmp     rbx, r13
0x1800d1fb4  jz      loc_1800D1F10
0x1800d1fba  mov     r8, [rbp+57h+var_D0+8]
0x1800d1fbe  mov     rdx, rbx
0x1800d1fc1  sub     r8, rbx
0x1800d1fc4  sar     r8, 3
0x1800d1fc8  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@0@PEAV?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@_K@Z; utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>> &,wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>> *,unsigned __int64)
0x1800d1fcd  mov     rdx, r14
0x1800d1fd0  jmp     loc_1800D1F08
0x1800d1fd5  lea     rdx, [rbp+57h+var_B8]
0x1800d1fd9  lea     rcx, [rbp+57h+var_98]
0x1800d1fdd  call    ?GetWimOsVersion@BaseImage@Details@Core@Manager@Container@@SAJAEBVPath@Csl@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Container::Manager::Core::Details::BaseImage::GetWimOsVersion(Csl::Path const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x1800d1fe2  mov     edi, eax
0x1800d1fe4  test    eax, eax
0x1800d1fe6  jns     short loc_1800D1FF2
0x1800d1fe8  mov     edx, 0B6h
0x1800d1fed  jmp     loc_1800D1F69
0x1800d1ff2  mov     r12, [rbp+57h+var_D0]
0x1800d1ff6  mov     rbx, [rbp+57h+var_D0+8]
0x1800d1ffa  mov     rdi, r12
0x1800d1ffd  cmp     rdi, rbx
0x1800d2000  jz      loc_1800D217C
0x1800d2006  mov     rcx, [rdi]
0x1800d2009  mov     r9, [rbp+5Fh]; char *
0x1800d200d  mov     eax, [rcx+20h]
0x1800d2010  test    eax, eax
0x1800d2012  jnz     loc_1800D28BE
0x1800d2018  mov     rax, [rcx+28h]
0x1800d201c  mov     rcx, [rbp+5Fh]; this
0x1800d2020  cmp     dword ptr [rax+10h], 5
0x1800d2024  jnz     loc_1800D28AC
0x1800d202a  cmp     byte ptr [rax+68h], 0
0x1800d202e  mov     rcx, [rbp+5Fh]; this
0x1800d2032  jz      loc_1800D289A
0x1800d2038  mov     r14, [rax+60h]
0x1800d203c  xor     esi, esi
0x1800d203e  mov     dword ptr [rsp+100h+var_DC], esi
0x1800d2042  cmp     dword ptr [r14+88h], 2
0x1800d204a  jnz     short loc_1800D2067
0x1800d204c  lea     rdx, [rsp+100h+var_DC]; enum Container::Manager::Core::Details::BaseImageValidity *
0x1800d2051  mov     rcx, r14; this
0x1800d2054  call    ?GetValidity@BaseImage@Details@Core@Manager@Container@@QEBAJAEAW4BaseImageValidity@2345@@Z; Container::Manager::Core::Details::BaseImage::GetValidity(Container::Manager::Core::Details::BaseImageValidity &)
0x1800d2059  mov     esi, eax
0x1800d205b  test    eax, eax
0x1800d205d  js      loc_1800D2103
0x1800d2063  mov     esi, dword ptr [rsp+100h+var_DC]
0x1800d2067  mov     rcx, [rbp+57h+var_B8]
0x1800d206b  mov     rax, [rbp+57h+var_B0]
0x1800d206f  cmp     rcx, rax
0x1800d2072  jz      short loc_1800D20AD
0x1800d2074  sub     rax, rcx
0x1800d2077  mov     [rbp+57h+var_D0], rcx
0x1800d207b  mov     rcx, [r14+68h]
0x1800d207f  lea     rdx, [rbp+57h+var_D0]
0x1800d2083  sar     rax, 1
0x1800d2086  mov     [rbp+57h+var_D0+8], rax
0x1800d208a  mov     rax, [r14+60h]
0x1800d208e  sub     rcx, rax
0x1800d2091  mov     qword ptr [rbp+57h+var_58.Data1], rax
0x1800d2095  sar     rcx, 1
0x1800d2098  mov     qword ptr [rbp+57h+var_58.Data4], rcx
0x1800d209c  lea     rcx, [rbp+57h+var_58]
0x1800d20a0  call    ?StringEqualIgnoreCase@Csl@@YA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@0@Z; Csl::StringEqualIgnoreCase(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &,utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x1800d20a5  test    al, al
0x1800d20a7  jz      short loc_1800D20AD
0x1800d20a9  test    esi, esi
0x1800d20ab  jz      short loc_1800D20FA
0x1800d20ad  mov     rcx, [rdi]; this
0x1800d20b0  call    ?GetId@ResourceHandle@Core@Manager@Container@@QEBAAEBU_GUID@@XZ; Container::Manager::Core::ResourceHandle::GetId(void)
0x1800d20b5  mov     rsi, [rdi]
0x1800d20b8  movups  xmm0, xmmword ptr [rax]
0x1800d20bb  mov     qword ptr [rdi], 0
0x1800d20c2  movdqu  xmmword ptr [rbp+57h+var_70.Data1], xmm0
0x1800d20c7  test    rsi, rsi
0x1800d20ca  jz      short loc_1800D20E1
0x1800d20cc  mov     rcx, rsi; this
0x1800d20cf  call    ??1ResourceHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ResourceHandle::~ResourceHandle(void)
0x1800d20d4  mov     edx, 58h ; 'X'; struct std::nothrow_t *
0x1800d20d9  mov     rcx, rsi; void *
0x1800d20dc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d20e1  mov     rcx, [r15+8]; this
0x1800d20e5  lea     rdx, [rbp+57h+var_70]; struct _GUID *
0x1800d20e9  mov     r8d, 5; enum ResourceType
0x1800d20ef  call    ?DeleteResourceTree@ResourceBroker@Details@Core@Manager@Container@@QEAAJAEBU_GUID@@W4ResourceType@2345@_N@Z; Container::Manager::Core::Details::ResourceBroker::DeleteResourceTree(_GUID const &,Container::Manager::Core::Details::ResourceType,bool)
0x1800d20f4  mov     esi, eax
0x1800d20f6  test    eax, eax
0x1800d20f8  js      short loc_1800D2175
0x1800d20fa  add     rdi, 8
0x1800d20fe  jmp     loc_1800D1FFD
0x1800d2103  mov     edx, 0C4h; void *
0x1800d2108  mov     rcx, [rbp+5Fh]; this
0x1800d210c  lea     r8, aOnecoreBaseGen_23; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800d2113  mov     r9d, esi; char *
0x1800d2116  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d211b  lea     r14, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800d2122  mov     rcx, [rbp+57h+var_B8]; void *
0x1800d2126  lea     rax, [rbp+57h+var_A8]
0x1800d212a  cmp     rcx, rax
0x1800d212d  jz      short loc_1800D2137
0x1800d212f  mov     rdx, r14; struct std::nothrow_t *
0x1800d2132  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d2137  mov     rcx, [rbp+57h+var_98]; void *
0x1800d213b  lea     rax, [rbp+57h+var_88]
0x1800d213f  cmp     rcx, rax
0x1800d2142  jz      short loc_1800D214C
0x1800d2144  mov     rdx, r14; struct std::nothrow_t *
0x1800d2147  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d214c  cmp     r12, r13
0x1800d214f  jz      short loc_1800D216E
0x1800d2151  sub     rbx, r12
0x1800d2154  mov     rdx, r12
0x1800d2157  sar     rbx, 3
0x1800d215b  mov     r8, rbx
0x1800d215e  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@0@PEAV?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@_K@Z; utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>> &,wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>> *,unsigned __int64)
0x1800d2163  mov     rdx, r14; struct std::nothrow_t *
0x1800d2166  mov     rcx, r12; void *
0x1800d2169  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d216e  mov     eax, esi
0x1800d2170  jmp     loc_1800D2867
0x1800d2175  mov     edx, 0D7h
0x1800d217a  jmp     short loc_1800D2108
0x1800d217c  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800d2184  lea     r9, [rbp+57h+var_D0]
0x1800d2188  mov     rcx, [r15+8]
0x1800d218c  lea     r8, aDeploymentmana_0; "DeploymentManager_Start_Layers"
0x1800d2193  mov     edx, 2
0x1800d2198  mov     [rbp+57h+var_C0], r13
0x1800d219c  movdqu  xmmword ptr [rbp+57h+var_D0], xmm0
0x1800d21a1  call    ?EnumerateResourceHandles@ResourceBroker@Details@Core@Manager@Container@@QEAAJW4ResourceType@2345@PEBGAEAV?$vector@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@V?$allocator@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@@Z; Container::Manager::Core::Details::ResourceBroker::EnumerateResourceHandles(Container::Manager::Core::Details::ResourceType,ushort const *,utl::vector<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>> &)
0x1800d21a6  mov     esi, eax
0x1800d21a8  test    eax, eax
0x1800d21aa  jns     short loc_1800D21FB
0x1800d21ac  mov     rcx, [rbp+5Fh]; this
0x1800d21b0  lea     r8, aOnecoreBaseGen_23; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800d21b7  mov     r9d, eax; char *
0x1800d21ba  mov     edx, 0DFh; void *
0x1800d21bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d21c4  mov     rdi, [rbp+57h+var_D0]
0x1800d21c8  lea     r14, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800d21cf  cmp     rdi, r13
0x1800d21d2  jz      loc_1800D2122
0x1800d21d8  mov     r8, [rbp+57h+var_D0+8]
0x1800d21dc  mov     rdx, rdi
0x1800d21df  sub     r8, rdi
0x1800d21e2  sar     r8, 3
0x1800d21e6  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@@0@PEAV?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@_K@Z; utl::_RangeDestroyApc<utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>>>(utl::allocator<wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>> &,wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>> *,unsigned __int64)
0x1800d21eb  mov     rdx, r14; struct std::nothrow_t *
0x1800d21ee  mov     rcx, rdi; void *
0x1800d21f1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d21f6  jmp     loc_1800D2122
0x1800d21fb  mov     rdi, [r15+18h]
0x1800d21ff  lea     rsi, [rdi+28h]
0x1800d2203  mov     rcx, rsi; SRWLock
0x1800d2206  call    cs:__imp_AcquireSRWLockShared
0x1800d220d  nop     dword ptr [rax+rax+00h]
0x1800d2212  mov     eax, [rdi+340h]
0x1800d2218  mov     dword ptr [rsp+100h+var_DC], eax
0x1800d221c  test    rsi, rsi
0x1800d221f  jz      short loc_1800D2230
0x1800d2221  mov     rcx, rsi; SRWLock
0x1800d2224  call    cs:__imp_ReleaseSRWLockShared
0x1800d222b  nop     dword ptr [rax+rax+00h]
0x1800d2230  mov     r13, [rbp+57h+var_D0]
0x1800d2234  mov     rdi, [rbp+57h+var_D0+8]
0x1800d2238  mov     rsi, r13
0x1800d223b  cmp     rsi, rdi
0x1800d223e  jz      loc_1800D2454
0x1800d2244  mov     rcx, [rsi]
0x1800d2247  call    ??$Get@VLayer@Details@Core@Manager@Container@@@ResourceHandle@Core@Manager@Container@@QEBAPEAVLayer@Details@123@XZ; Container::Manager::Core::ResourceHandle::Get<Container::Manager::Core::Details::Layer>(void)
0x1800d224c  cmp     byte ptr [rax+2A8h], 0
0x1800d2253  jz      loc_1800D2341
0x1800d2259  mov     r14, [r15+28h]
0x1800d225d  add     rax, 180h
0x1800d2263  mov     qword ptr [rbp+57h+var_70.Data1], rax
0x1800d2267  mov     rcx, r14; SRWLock
0x1800d226a  mov     byte ptr [rsp+100h+var_E0+1], 0
0x1800d226f  mov     qword ptr [rsp+100h+var_DC+4], 0
0x1800d2278  mov     rax, [rax+40h]
0x1800d227c  mov     [rbp+57h+var_D0], rax
0x1800d2280  call    cs:__imp_AcquireSRWLockShared
0x1800d2287  nop     dword ptr [rax+rax+00h]
0x1800d228c  xor     eax, eax
0x1800d228e  cmp     [r14+99h], al
0x1800d2295  jz      short loc_1800D22A5
0x1800d2297  mov     byte ptr [rsp+100h+var_E0], 1
0x1800d229c  cmp     [r14+98h], al
0x1800d22a3  jnz     short loc_1800D22A9
0x1800d22a5  mov     byte ptr [rsp+100h+var_E0], al; int
0x1800d22a9  mov     rcx, r14; SRWLock
0x1800d22ac  call    cs:__imp_ReleaseSRWLockShared
0x1800d22b3  nop     dword ptr [rax+rax+00h]
0x1800d22b8  cmp     byte ptr [rsp+100h+var_E0], 0
0x1800d22bd  jz      short loc_1800D22E6
0x1800d22bf  mov     rax, [rbp+57h+var_D0]
0x1800d22c3  test    byte ptr [rax+0E4h], 2
0x1800d22ca  jz      short loc_1800D22E6
0x1800d22cc  mov     rax, [r15+28h]
0x1800d22d0  mov     byte ptr [rbp+57h+var_58.Data2], 1
0x1800d22d4  mov     edx, [rax+9Ch]
0x1800d22da  mov     [rbp+57h+var_58.Data1], edx
0x1800d22dd  mov     rax, qword ptr [rbp+57h+var_58.Data1]
0x1800d22e1  mov     qword ptr [rsp+100h+var_DC+4], rax
0x1800d22e6  mov     r14, qword ptr [rbp+57h+var_70.Data1]
0x1800d22ea  lea     rcx, [r14+48h]; SRWLock
0x1800d22ee  call    cs:__imp_AcquireSRWLockShared
0x1800d22f5  nop     dword ptr [rax+rax+00h]
0x1800d22fa  mov     r8, [r15+28h]
0x1800d22fe  lea     r9, [rsp+100h+var_E0+1]
0x1800d2303  add     r8, 38h ; '8'
0x1800d2307  lea     rdx, [rsp+100h+var_DC+4]
0x1800d230c  mov     rcx, r14
0x1800d230f  call    ?IsValidLocked@SpecializationLayer@Details@Core@Manager@Container@@AEBAJAEBV?$optional@K@utl@@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@7@AEA_N@Z; Container::Manager::Core::Details::SpecializationLayer::IsValidLocked(utl::optional<ulong> const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &,bool &)
0x1800d2314  mov     dword ptr [rsp+100h+var_DC+4], eax
0x1800d2318  mov     r14d, eax
0x1800d231b  test    eax, eax
  ... truncated ...
```
