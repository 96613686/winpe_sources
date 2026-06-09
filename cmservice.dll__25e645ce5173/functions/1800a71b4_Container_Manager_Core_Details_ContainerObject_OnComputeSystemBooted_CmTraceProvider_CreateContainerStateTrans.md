# Container::Manager::Core::Details::ContainerObject::OnComputeSystemBooted(CmTraceProvider::CreateContainerStateTransition const &,Csl::SrwLock::ReleaseOnScopeExit<0> &)

- ea: `0x1800a71b4`
- end: `0x1800a7d57`
- name: `?OnComputeSystemBooted@ContainerObject@Details@Core@Manager@Container@@AEAAJAEBVCreateContainerStateTransition@CmTraceProvider@@AEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z`
- size: `2979`
- prototype: `__int64 __fastcall(Container::Manager::Core::Details::ContainerObject *this)`
- caller_count: `1`
- callee_count: `38`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a9bb4`

## callees

- `0x180004bd0`
- `0x180004fc4`
- `0x180005704`
- `0x180007b48`
- `0x180007dd4`
- `0x180009ba0`
- `0x18000da88`
- `0x1800103a4`
- `0x1800246ac`
- `0x18002fae4`
- `0x18002fc34`
- `0x180031c14`
- `0x1800471dc`
- `0x180049a0c`
- `0x1800505a4`
- `0x180076978`
- `0x180077dd8`
- `0x1800785d4`
- `0x180098830`
- `0x180098e58`
- `0x180099680`
- `0x18009970c`
- `0x18009a8d8`
- `0x18009c714`
- `0x18009cda0`
- `0x18009e154`
- `0x18009fa48`
- `0x18009fb88`
- `0x18009fea8`
- `0x1800a31bc`
- `0x1800a321c`
- `0x1800a4b20`
- `0x1800a64d0`
- `0x1800a71b4`
- `0x1800abe60`
- `0x1800ac894`
- `0x1800afa54`
- `0x18010db88`

## import_xrefs

- `ntdll!RtlDoesFileExists_U` at `0x1800a78bc`
- `ntdll!RtlDoesFileExists_U` at `0x1800a78bc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a749d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a7552`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a79c8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a749d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a7552`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a79c8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a7440`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a74cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a74ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a759d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a799b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a7a02`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a7440`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a74cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a74ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a759d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a799b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a7a02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a74a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a755e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a79d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a74a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a755e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a79d4`

## string_xrefs

- `0x1800a7a97`: `CreateContainerStateTransition_MapConfigFileFolders`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
__int64 __fastcall Container::Manager::Core::Details::ContainerObject::OnComputeSystemBooted(
        Container::Manager::Core::Details::ContainerObject *this,
        struct Path *a2,
        char *a3)
{
  struct Path *v4; // r15
  int updated; // ebx
  __int64 v7; // rdx
  __int64 v9; // rax
  __int64 v10; // rcx
  unsigned int v11; // eax
  bool v12; // r13
  __int128 v13; // xmm6
  int v14; // ebx
  int v15; // r15d
  char IsHotPatchUpdateRequired; // di
  __int64 v17; // rcx
  int v18; // edi
  __int64 v19; // rcx
  __int64 v20; // rbx
  _QWORD *v21; // rdi
  _QWORD *v22; // rcx
  PSRWLOCK v23; // rax
  int v24; // eax
  void *v25; // rbx
  __int64 v26; // rcx
  RTL_SRWLOCK *v27; // rbx
  PVOID Ptr; // rdi
  unsigned __int64 v29; // rax
  utl::_RefCountBase *v30; // rcx
  RTL_SRWLOCK *v31; // rbx
  PVOID v32; // rdi
  unsigned __int64 v33; // rax
  __int64 v34; // rdx
  utl::_RefCountBase *v35; // rcx
  int SystemDrivePath; // eax
  __int64 v37; // rdx
  RTL_SRWLOCK *v38; // rax
  void *v39; // rbx
  __int64 v40; // rcx
  RTL_SRWLOCK *v41; // rcx
  int v42; // eax
  bool *v43; // rbx
  bool *v44; // rdi
  int v45; // r15d
  __int64 v46; // rax
  __int64 v47; // rdx
  void *v48; // rbx
  int MappedLayer; // eax
  PSRWLOCK v50; // rbx
  char *v51; // rcx
  PSRWLOCK v52; // rax
  utl::_RefCountBase *v53; // rcx
  void *v54; // rbx
  int v55; // [rsp+28h] [rbp-E0h]
  int v56; // [rsp+28h] [rbp-E0h]
  char v57; // [rsp+49h] [rbp-BFh]
  PSRWLOCK SRWLock_8[2]; // [rsp+58h] [rbp-B0h] BYREF
  utl::_RefCountBase *v59[2]; // [rsp+68h] [rbp-A0h] BYREF
  int v60; // [rsp+78h] [rbp-90h]
  void *v61[2]; // [rsp+88h] [rbp-80h] BYREF
  int v62; // [rsp+98h] [rbp-70h]
  char v63; // [rsp+A0h] [rbp-68h]
  _QWORD v64[2]; // [rsp+A8h] [rbp-60h] BYREF
  int Address; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v66; // [rsp+BCh] [rbp-4Ch]
  PCWSTR FileName[2]; // [rsp+C8h] [rbp-40h] BYREF
  _WORD v68[8]; // [rsp+D8h] [rbp-30h] BYREF
  void *v69[2]; // [rsp+E8h] [rbp-20h] BYREF
  _WORD v70[8]; // [rsp+F8h] [rbp-10h] BYREF
  _QWORD v71[2]; // [rsp+108h] [rbp+0h] BYREF
  __int128 v72; // [rsp+118h] [rbp+10h]
  int v73; // [rsp+128h] [rbp+20h]
  char v74; // [rsp+138h] [rbp+30h] BYREF
  int v75[4]; // [rsp+148h] [rbp+40h] BYREF
  __int128 v76; // [rsp+158h] [rbp+50h]
  __int64 v77; // [rsp+168h] [rbp+60h]
  _BYTE v78[184]; // [rsp+170h] [rbp+68h] BYREF
  char v79; // [rsp+228h] [rbp+120h]
  __int128 v80; // [rsp+230h] [rbp+128h]
  __int128 v81; // [rsp+240h] [rbp+138h]
  __int128 v82; // [rsp+250h] [rbp+148h]
  _BYTE v83[168]; // [rsp+268h] [rbp+160h] BYREF
  struct Path *v84; // [rsp+310h] [rbp+208h]
  struct Path *v85; // [rsp+318h] [rbp+210h]
  _BYTE v86[288]; // [rsp+348h] [rbp+240h] BYREF
  _QWORD v87[42]; // [rsp+468h] [rbp+360h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+610h] [rbp+508h]

  v4 = a2;
  SRWLock_8[0] = (PSRWLOCK)a2;
  if ( *((_DWORD *)this + 22) == 1 )
  {
    if ( Container::Manager::Core::Details::ContainerObject::IsBootTraceEnabled(this) )
    {
      v69[0] = v70;
      v69[1] = v70;
      v70[0] = 0;
      v71[0] = L"C:\\ContainerLogs";
      v71[1] = 16;
      if ( !(unsigned __int8)Csl::Path::Assign((Csl::Path *)v69) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2C29,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
          (const char *)0x8007000ELL,
          v55);
        if ( v69[0] != v70 )
          operator delete(v69[0], (const struct std::nothrow_t *)&std::nothrow);
        return 2147942414LL;
      }
      *(_OWORD *)v75 = 0;
      v76 = 0;
      v77 = 0;
      memset_0(v78, 0, 0xC0u);
      v78[0] = 0;
      v79 = 0;
      v80 = 0;
      v81 = 0;
      v82 = 0;
      LOBYTE(v80) = 0;
      BYTE8(v82) = 0;
      updated = Container::Manager::Core::Details::ContainerObject::ConstructDefaultMappedFolderConfiguration(
                  this,
                  (const struct Path *)(*((_QWORD *)this + 163) + 408LL),
                  (const struct Path *)v69,
                  0,
                  (struct Container::Manager::Hcs::MappedFolderConfiguration *)v75);
      if ( updated < 0 )
      {
        v7 = 11312;
LABEL_8:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v7,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
          (const char *)(unsigned int)updated,
          v56);
        Container::Manager::Hcs::MappedFolderConfiguration::~MappedFolderConfiguration((Container::Manager::Hcs::MappedFolderConfiguration *)v75);
        if ( v69[0] != v70 )
          operator delete(v69[0], (const struct std::nothrow_t *)&std::nothrow);
        return (unsigned int)updated;
      }
      v9 = Container::Manager::Hcs::MappedFolderConfiguration::MappedFolderConfiguration(v86, v75);
      updated = Container::Manager::Core::Details::ContainerObject::MapOrUpdateSharedFolderInternal(this, v9, a3);
      if ( updated < 0 )
      {
        v7 = 11314;
        goto LABEL_8;
      }
      Container::Manager::Hcs::MappedFolderConfiguration::~MappedFolderConfiguration((Container::Manager::Hcs::MappedFolderConfiguration *)v75);
      if ( v69[0] != v70 )
        operator delete(v69[0], (const struct std::nothrow_t *)&std::nothrow);
    }
    v10 = *((_QWORD *)this + 158);
    if ( !*(_BYTE *)(v10 + 1248) )
      __int2c();
    v11 = *(_DWORD *)(v10 + 456) - 2;
    v12 = v11 <= 1;
    v13 = 0;
    v14 = 0;
    *(_OWORD *)v59 = 0;
    v60 = 0;
    if ( v11 <= 1 )
    {
      *(_OWORD *)v59 = *(_OWORD *)(v10 + 168);
      LOBYTE(v60) = 1;
      v14 = v60;
      v13 = *(_OWORD *)v59;
    }
    v15 = *(_DWORD *)(*((_QWORD *)this + 188) + 228LL) & 0x10;
    IsHotPatchUpdateRequired = Container::Manager::Core::Details::ContainerObject::IsHotPatchUpdateRequired(this);
    v57 = IsHotPatchUpdateRequired;
    v17 = *(_QWORD *)a3;
    if ( *(_QWORD *)a3 )
    {
      *(_DWORD *)(v17 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v17);
      *(_QWORD *)a3 = 0;
    }
    *(_OWORD *)v59 = 0;
    v71[0] = 0;
    v72 = v13;
    v73 = v14;
    v18 = Container::Manager::Core::Details::ContainerObject::NotifyAgentCreating(
            this,
            IsHotPatchUpdateRequired,
            (__int64)v59,
            (__int64)v71);
    AcquireSRWLockExclusive((PSRWLOCK)this + 57);
    *((_DWORD *)this + 116) = GetCurrentThreadId();
    if ( a3 == &v74 )
    {
      if ( this != (Container::Manager::Core::Details::ContainerObject *)-456LL )
      {
        *((_DWORD *)this + 116) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)this + 57);
      }
    }
    else
    {
      v19 = *(_QWORD *)a3;
      if ( *(_QWORD *)a3 )
      {
        *(_DWORD *)(v19 + 8) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)v19);
      }
      *(_QWORD *)a3 = (char *)this + 456;
    }
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C63,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        (const char *)(unsigned int)v18,
        v55);
      return (unsigned int)v18;
    }
    if ( v15 )
      *(_OWORD *)((char *)this + 792) = *(_OWORD *)v59;
    if ( v57 )
      *((_QWORD *)this + 103) = v71[0];
    v20 = *((_QWORD *)this + 169);
    v21 = (_QWORD *)*((_QWORD *)this + 69);
    AcquireSRWLockExclusive((PSRWLOCK)v20);
    *(_DWORD *)(v20 + 8) = GetCurrentThreadId();
    v22 = *(_QWORD **)(v20 + 40);
    if ( *v22 != v20 + 32 )
      __fastfail(3u);
    *v21 = v20 + 32;
    v21[1] = v22;
    *v22 = v21;
    *(_QWORD *)(v20 + 40) = v21;
    Container::Manager::Core::Details::HeartbeatMonitor::CheckStartStopHeartbeats(v20);
    *(_DWORD *)(v20 + 8) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)v20);
    v4 = (struct Path *)SRWLock_8[0];
  }
  else
  {
    v12 = 0;
  }
  *(_OWORD *)v61 = 0;
  v62 = 0;
  v63 = 0;
  v64[1] = v64;
  v64[0] = v64;
  Address = 0;
  v66 = 0;
  if ( *((_BYTE *)this + 152) )
  {
    utl::make_shared<Container::Manager::Core::Details::ContainerObject::MirrorNetworksSynchronizeContext,>(SRWLock_8);
    v23 = SRWLock_8[0];
    if ( !SRWLock_8[0] )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C89,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        (const char *)0x8007000ELL,
        v55);
      if ( SRWLock_8[1] )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)SRWLock_8[1]);
      goto LABEL_90;
    }
    LODWORD(SRWLock_8[0][3].Ptr) = 3;
    *(_OWORD *)((char *)&v23[3].Ptr + 4) = *(_OWORD *)(*((_QWORD *)v4 + 34) + 8LL);
    if ( !BYTE4(v23[5].Ptr) )
      BYTE4(v23[5].Ptr) = 1;
    *(_OWORD *)v59 = *(_OWORD *)SRWLock_8;
    v24 = Container::Manager::Core::Details::ContainerObject::QueueMirrorNetworkWorkItems(this, 1, v59);
    v18 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C91,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        (const char *)(unsigned int)v24,
        v55);
      goto LABEL_44;
    }
  }
  if ( v12 )
  {
    v26 = *((_QWORD *)this + 158);
    if ( !*(_BYTE *)(v26 + 1248) )
      __int2c();
    if ( *(_DWORD *)(v26 + 224) != *(_DWORD *)(v26 + 1240) )
    {
      Container::Manager::Core::Details::ContainerObject::AllocateWorkItem(SRWLock_8);
      v27 = SRWLock_8[0];
      if ( !SRWLock_8[0] )
      {
        v34 = 11428;
LABEL_68:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v34,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
          (const char *)0x8007000ELL,
          v55);
LABEL_90:
        v39 = v61[0];
        v61[0] = 0;
        if ( v39 )
        {
          Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>::~ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>(v39);
          operator delete(v39, (const struct std::nothrow_t *)0x20);
        }
        return 2147942414LL;
      }
      *(_DWORD *)SRWLock_8[0]->Ptr = 2;
      Ptr = v27->Ptr;
      v29 = *((char *)v27->Ptr + 48);
      if ( (_BYTE)v29 == 1 )
      {
        *((_QWORD *)Ptr + 1) = v4;
      }
      else
      {
        if ( (_BYTE)v29 != 0xFF )
        {
          if ( v29 >= 3 )
          {
LABEL_80:
            __int2c();
LABEL_81:
            v34 = 11447;
            goto LABEL_68;
          }
          if ( !*((_BYTE *)v27->Ptr + 48) )
          {
            v30 = (utl::_RefCountBase *)*((_QWORD *)Ptr + 5);
            if ( v30 )
              utl::_RefCountBase::_DecStrong(v30);
          }
        }
        *((_QWORD *)Ptr + 1) = v4;
        *((_BYTE *)Ptr + 48) = 1;
      }
      SRWLock_8[0] = v27;
      Csl::List<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>::EmplaceBack(
        v61,
        SRWLock_8);
    }
  }
  if ( !*((_DWORD *)this + 54) )
    goto LABEL_76;
  Container::Manager::Core::Details::ContainerObject::AllocateWorkItem(SRWLock_8);
  v31 = SRWLock_8[0];
  if ( !SRWLock_8[0] )
    goto LABEL_81;
  *(_DWORD *)SRWLock_8[0]->Ptr = 3;
  v32 = v31->Ptr;
  v33 = *((char *)v31->Ptr + 48);
  if ( (_BYTE)v33 != 2 )
  {
    if ( (_BYTE)v33 == 0xFF )
    {
LABEL_74:
      *((_QWORD *)v32 + 1) = v4;
      *((_BYTE *)v32 + 48) = 2;
      goto LABEL_75;
    }
    if ( v33 < 3 )
    {
      if ( !*((_BYTE *)v31->Ptr + 48) )
      {
        v35 = (utl::_RefCountBase *)*((_QWORD *)v32 + 5);
        if ( v35 )
          utl::_RefCountBase::_DecStrong(v35);
      }
      goto LABEL_74;
    }
    goto LABEL_80;
  }
  *((_QWORD *)v32 + 1) = v4;
LABEL_75:
  SRWLock_8[0] = v31;
  Container::Manager::Core::Details::ContainerObject::WorkItemGroup::AddWorkItem(v61, SRWLock_8);
LABEL_76:
  if ( *(_BYTE *)(*((_QWORD *)this + 188) + 136LL) )
  {
    FileName[0] = v68;
    FileName[1] = v68;
    v68[0] = 0;
    SystemDrivePath = Csl::GetSystemDrivePath((Csl *)FileName, a2);
    v18 = SystemDrivePath;
    if ( SystemDrivePath < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2CC8,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        (const char *)(unsigned int)SystemDrivePath,
        v55);
      if ( FileName[0] != v68 )
        operator delete((void *)FileName[0], (const struct std::nothrow_t *)&std::nothrow);
      goto LABEL_44;
    }
    v59[0] = (utl::_RefCountBase *)L"Program Files (x86)\\Microsoft\\Edge";
    v59[1] = (utl::_RefCountBase *)34;
    if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)FileName) )
    {
      v37 = 11465;
      goto LABEL_88;
    }
    if ( RtlDoesFileExists_U(FileName[0]) )
    {
      Container::Manager::Core::Details::ContainerObject::AllocateWorkItem(SRWLock_8);
      v38 = SRWLock_8[0];
      if ( !SRWLock_8[0] )
      {
        v37 = 11471;
LABEL_88:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v37,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
          (const char *)0x8007000ELL,
          v55);
        if ( FileName[0] != v68 )
          operator delete((void *)FileName[0], (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_90;
      }
      *(_DWORD *)SRWLock_8[0]->Ptr = 6;
      SRWLock_8[0] = v38;
      Container::Manager::Core::Details::ContainerObject::WorkItemGroup::AddWorkItem(v61, SRWLock_8);
    }
    else
    {
      CmTraceProvider::EdgeIsMissing();
    }
    if ( FileName[0] != v68 )
      operator delete((void *)FileName[0], (const struct std::nothrow_t *)&std::nothrow);
  }
  Container::Manager::Core::Details::ContainerObject::QueueWorkItemGroup(this, v61);
  v40 = *(_QWORD *)a3;
  if ( *(_QWORD *)a3 )
  {
    *(_DWORD *)(v40 + 8) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)v40);
    *(_QWORD *)a3 = 0;
  }
  wil::slim_event_t<1>::wait(&Address);
  v18 = BYTE4(v66) != 0 ? v66 : 0;
  AcquireSRWLockExclusive((PSRWLOCK)this + 57);
  *((_DWORD *)this + 116) = GetCurrentThreadId();
  SRWLock_8[0] = (PSRWLOCK)((char *)this + 456);
  Csl::SrwLock::ReleaseOnScopeExit<0>::operator=(a3, SRWLock_8);
  v41 = SRWLock_8[0];
  if ( SRWLock_8[0] )
  {
    LODWORD(SRWLock_8[0][1].Ptr) = 0;
    ReleaseSRWLockExclusive(v41);
  }
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2CEB,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)(unsigned int)v18,
      v55);
    goto LABEL_44;
  }
  Container::Manager::Core::Details::DeploymentSettings::DeploymentSettings((Container::Manager::Core::Details::DeploymentSettings *)v83);
  v42 = Container::Manager::Core::Details::DeploymentSettings::Initialize(
          (Container::Manager::Core::Details::DeploymentSettings *)v83,
          *((const struct Container::Manager::Core::Details::PolicyManager **)this + 163));
  v18 = v42;
  if ( v42 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2CEF,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)(unsigned int)v42,
      v55);
LABEL_104:
    Container::Manager::Core::Details::DeploymentSettings::~DeploymentSettings((Container::Manager::Core::Details::DeploymentSettings *)v83);
LABEL_44:
    v25 = v61[0];
    v61[0] = 0;
    if ( v25 )
    {
      Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>::~ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>(v25);
      operator delete(v25, (const struct std::nothrow_t *)0x20);
    }
    return (unsigned int)v18;
  }
  if ( v84 == v85 )
  {
LABEL_117:
    if ( *((_DWORD *)this + 22) == 1 )
    {
      *(_OWORD *)SRWLock_8 = 0;
      MappedLayer = Container::Manager::Core::Details::ContainerObject::GetOrCreateMappedLayer(
                      this,
                      *((_QWORD *)this + 188),
                      a3,
                      SRWLock_8);
      v18 = MappedLayer;
      if ( MappedLayer < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2D0C,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
          (const char *)(unsigned int)MappedLayer,
          v55);
        if ( SRWLock_8[1] )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)SRWLock_8[1]);
        goto LABEL_104;
      }
      v50 = SRWLock_8[0];
      utl::optional<Container::Manager::Core::Details::SiloSettings>::emplace<>(&SRWLock_8[0][40]);
      v51 = (char *)v50[2].Ptr;
      if ( v51 )
        utl::optional<Container::Manager::Core::Details::SiloSettings>::emplace<>(v51 + 320);
      v52 = SRWLock_8[1];
      *((_QWORD *)this + 193) = v50;
      v53 = (utl::_RefCountBase *)*((_QWORD *)this + 194);
      *((_QWORD *)this + 194) = v52;
      if ( v53 )
        utl::_RefCountBase::_DecStrong(v53);
    }
    Container::Manager::Core::Details::DeploymentSettings::~DeploymentSettings((Container::Manager::Core::Details::DeploymentSettings *)v83);
    v54 = v61[0];
    v61[0] = 0;
    if ( v54 )
    {
      Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>::~ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>(v54);
      operator delete(v54, (const struct std::nothrow_t *)0x20);
    }
    return 0;
  }
  else
  {
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
      v87,
      "CreateContainerStateTransition_MapConfigFileFolders");
    v87[0] = &CmTraceProvider::CreateContainerStateTransition_MapConfigFileFolders::`vftable';
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
      v87,
      *((_QWORD *)v4 + 34) + 8LL);
    CmTraceProvider::CreateContainerStateTransition_MapConfigFileFolders::StartActivity((CmTraceProvider::CreateContainerStateTransition_MapConfigFileFolders *)v87);
    v43 = (bool *)v84;
    v44 = (bool *)v85;
    while ( 1 )
    {
      if ( v43 == v44 )
      {
        wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
          v87,
          0);
        v87[0] = &CmTraceProvider::CreateContainerStateTransition_MapConfigFileFolders::`vftable';
        wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v87);
        wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v87);
        goto LABEL_117;
      }
      *(_OWORD *)v75 = 0;
      v76 = 0;
      v77 = 0;
      memset_0(v78, 0, 0xC0u);
      v78[0] = 0;
      v79 = 0;
      v80 = 0;
      v81 = 0;
      v82 = 0;
      LOBYTE(v80) = 0;
      BYTE8(v82) = 0;
      v45 = Container::Manager::Core::Details::ContainerObject::ConstructDefaultMappedFolderConfiguration(
              this,
              (const struct Path *)v43,
              (const struct Path *)(v43 + 32),
              v43[64],
              (struct Container::Manager::Hcs::MappedFolderConfiguration *)v75);
      if ( v45 < 0 )
        break;
      v46 = Container::Manager::Hcs::MappedFolderConfiguration::MappedFolderConfiguration(v86, v75);
      v45 = Container::Manager::Core::Details::ContainerObject::MapOrUpdateSharedFolderInternal(this, v46, a3);
      if ( v45 < 0 )
      {
        v47 = 11519;
        goto LABEL_113;
      }
      Container::Manager::Hcs::MappedFolderConfiguration::~MappedFolderConfiguration((Container::Manager::Hcs::MappedFolderConfiguration *)v75);
      v43 += 72;
    }
    v47 = 11517;
LABEL_113:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v47,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)(unsigned int)v45,
      v55);
    Container::Manager::Hcs::MappedFolderConfiguration::~MappedFolderConfiguration((Container::Manager::Hcs::MappedFolderConfiguration *)v75);
    v87[0] = &CmTraceProvider::CreateContainerStateTransition_MapConfigFileFolders::`vftable';
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v87);
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v87);
    Container::Manager::Core::Details::DeploymentSettings::~DeploymentSettings((Container::Manager::Core::Details::DeploymentSettings *)v83);
    v48 = v61[0];
    v61[0] = 0;
    if ( v48 )
    {
      Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>::~ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>(v48);
      operator delete(v48, (const struct std::nothrow_t *)0x20);
    }
    return (unsigned int)v45;
  }
}

```

## disassembly

```asm
0x1800a71b4  mov     rax, rsp
0x1800a71b7  mov     [rax+20h], rbx
0x1800a71bb  push    rbp
0x1800a71bc  push    rsi
0x1800a71bd  push    rdi
0x1800a71be  push    r12
0x1800a71c0  push    r13
0x1800a71c2  push    r14
0x1800a71c4  push    r15
0x1800a71c6  lea     rbp, [rax-508h]
0x1800a71cd  sub     rsp, 5D0h
0x1800a71d4  movaps  xmmword ptr [rax-48h], xmm6
0x1800a71d8  mov     rax, cs:__security_cookie
0x1800a71df  xor     rax, rsp
0x1800a71e2  mov     [rbp+500h+var_50], rax
0x1800a71e9  mov     r12, r8
0x1800a71ec  mov     r15, rdx
0x1800a71ef  mov     [rsp+600h+SRWLock+8], rdx
0x1800a71f4  mov     r14, rcx
0x1800a71f7  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800a71fe  cmp     dword ptr [rcx+58h], 1
0x1800a7202  jnz     loc_1800A75B0
0x1800a7208  call    ?IsBootTraceEnabled@ContainerObject@Details@Core@Manager@Container@@AEBA_NXZ; Container::Manager::Core::Details::ContainerObject::IsBootTraceEnabled(void)
0x1800a720d  xor     esi, esi
0x1800a720f  test    al, al
0x1800a7211  jz      loc_1800A7393
0x1800a7217  lea     rax, [rbp+500h+var_510]
0x1800a721b  mov     [rbp+500h+var_520], rax
0x1800a721f  lea     rax, [rbp+500h+var_510]
0x1800a7223  mov     [rbp+500h+var_518], rax
0x1800a7227  mov     [rbp+500h+var_510], si
0x1800a722b  lea     rax, aCContainerlogs; "C:\\ContainerLogs"
0x1800a7232  mov     [rbp+500h+var_500], rax
0x1800a7236  mov     [rbp+500h+var_4F8], 10h
0x1800a723e  lea     rdx, [rbp+500h+var_500]
0x1800a7242  lea     rcx, [rbp+500h+var_520]; this
0x1800a7246  call    ?Assign@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Assign(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x1800a724b  test    al, al
0x1800a724d  jnz     short loc_1800A728B
0x1800a724f  mov     rcx, [rbp+508h]; this
0x1800a7256  mov     r9d, 8007000Eh; char *
0x1800a725c  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a7263  mov     edx, 2C29h; void *
0x1800a7268  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a726d  lea     rax, [rbp+500h+var_510]
0x1800a7271  mov     rcx, [rbp+500h+var_520]; void *
0x1800a7275  cmp     rcx, rax
0x1800a7278  jz      loc_1800A795B
0x1800a727e  mov     rdx, rdi; struct std::nothrow_t *
0x1800a7281  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a7286  jmp     loc_1800A795B
0x1800a728b  xorps   xmm0, xmm0
0x1800a728e  xor     eax, eax
0x1800a7290  movups  xmmword ptr [rbp+500h+var_4C0], xmm0
0x1800a7294  movups  [rbp+500h+var_4B0], xmm0
0x1800a7298  mov     [rbp+500h+var_4A0], rax
0x1800a729c  xor     edx, edx; Val
0x1800a729e  mov     r8d, 0C0h; Size
0x1800a72a4  lea     rcx, [rbp+500h+var_498]; void *
0x1800a72a8  call    memset_0
0x1800a72ad  mov     [rbp+500h+var_498], sil
0x1800a72b1  mov     [rbp+500h+var_3E0], sil
0x1800a72b8  xorps   xmm0, xmm0
0x1800a72bb  movups  [rbp+500h+var_3D8], xmm0
0x1800a72c2  movups  [rbp+500h+var_3C8], xmm0
0x1800a72c9  movups  [rbp+500h+var_3B8], xmm0
0x1800a72d0  mov     byte ptr [rbp+500h+var_3D8], sil
0x1800a72d7  mov     byte ptr [rbp+500h+var_3B8+8], sil
0x1800a72de  mov     rdx, [r14+518h]
0x1800a72e5  add     rdx, 198h; struct Path *
0x1800a72ec  lea     rax, [rbp+500h+var_4C0]
0x1800a72f0  mov     [rsp+600h+var_5E0], rax; int
0x1800a72f5  xor     r9d, r9d; bool
0x1800a72f8  lea     r8, [rbp+500h+var_520]; struct Path *
0x1800a72fc  mov     rcx, r14; this
0x1800a72ff  call    ?ConstructDefaultMappedFolderConfiguration@ContainerObject@Details@Core@Manager@Container@@AEBAJAEBVPath@Csl@@0_NAEAVMappedFolderConfiguration@Hcs@45@@Z; Container::Manager::Core::Details::ContainerObject::ConstructDefaultMappedFolderConfiguration(Csl::Path const &,Csl::Path const &,bool,Container::Manager::Hcs::MappedFolderConfiguration &)
0x1800a7304  mov     ebx, eax
0x1800a7306  test    eax, eax
0x1800a7308  jns     short loc_1800A734A
0x1800a730a  mov     edx, 2C30h; void *
0x1800a730f  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a7316  mov     r9d, ebx; char *
0x1800a7319  mov     rcx, [rbp+508h]; this
0x1800a7320  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7325  lea     rcx, [rbp+500h+var_4C0]; this
0x1800a7329  call    ??1MappedFolderConfiguration@Hcs@Manager@Container@@QEAA@XZ; Container::Manager::Hcs::MappedFolderConfiguration::~MappedFolderConfiguration(void)
0x1800a732e  lea     rax, [rbp+500h+var_510]
0x1800a7332  mov     rcx, [rbp+500h+var_520]; void *
0x1800a7336  cmp     rcx, rax
0x1800a7339  jz      short loc_1800A7343
0x1800a733b  mov     rdx, rdi; struct std::nothrow_t *
0x1800a733e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a7343  mov     eax, ebx
0x1800a7345  jmp     loc_1800A7D27
0x1800a734a  lea     rdx, [rbp+500h+var_4C0]
0x1800a734e  lea     rcx, [rbp+500h+var_2C0]
0x1800a7355  call    ??0MappedFolderConfiguration@Hcs@Manager@Container@@QEAA@$$QEAV0123@@Z; Container::Manager::Hcs::MappedFolderConfiguration::MappedFolderConfiguration(Container::Manager::Hcs::MappedFolderConfiguration &&)
0x1800a735a  mov     rdx, rax
0x1800a735d  mov     r8, r12
0x1800a7360  mov     rcx, r14
0x1800a7363  call    ?MapOrUpdateSharedFolderInternal@ContainerObject@Details@Core@Manager@Container@@AEAAJVMappedFolderConfiguration@Hcs@45@AEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::MapOrUpdateSharedFolderInternal(Container::Manager::Hcs::MappedFolderConfiguration,Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x1800a7368  mov     ebx, eax
0x1800a736a  test    eax, eax
0x1800a736c  jns     short loc_1800A7375
0x1800a736e  mov     edx, 2C32h
0x1800a7373  jmp     short loc_1800A730F
0x1800a7375  lea     rcx, [rbp+500h+var_4C0]; this
0x1800a7379  call    ??1MappedFolderConfiguration@Hcs@Manager@Container@@QEAA@XZ; Container::Manager::Hcs::MappedFolderConfiguration::~MappedFolderConfiguration(void)
0x1800a737e  lea     rax, [rbp+500h+var_510]
0x1800a7382  mov     rcx, [rbp+500h+var_520]; void *
0x1800a7386  cmp     rcx, rax
0x1800a7389  jz      short loc_1800A7393
0x1800a738b  mov     rdx, rdi; struct std::nothrow_t *
0x1800a738e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a7393  mov     rcx, [r14+4F0h]
0x1800a739a  cmp     [rcx+4E0h], sil
0x1800a73a1  jnz     short loc_1800A73A5
0x1800a73a3  int     2Ch; Windows NT - assertion failure
0x1800a73a5  mov     eax, [rcx+1C8h]
0x1800a73ab  sub     eax, 2
0x1800a73ae  cmp     eax, 1
0x1800a73b1  setbe   r13b
0x1800a73b5  xorps   xmm6, xmm6
0x1800a73b8  xor     ebx, ebx
0x1800a73ba  movups  xmmword ptr [rsp+600h+var_5A8+8], xmm6
0x1800a73bf  mov     [rsp+600h+var_590], ebx
0x1800a73c3  test    r13b, r13b
0x1800a73c6  jz      short loc_1800A740E
0x1800a73c8  mov     al, [rcx+0A8h]
0x1800a73ce  mov     byte ptr [rsp+600h+var_5A8+8], al
0x1800a73d2  movsd   xmm0, qword ptr [rcx+0A9h]
0x1800a73da  movsd   [rsp+600h+var_5A8+9], xmm0
0x1800a73e0  mov     eax, [rcx+0B1h]
0x1800a73e6  mov     [rsp+600h+var_598+1], eax
0x1800a73ea  movzx   eax, word ptr [rcx+0B5h]
0x1800a73f1  mov     [rsp+600h+var_593], ax
0x1800a73f6  mov     al, [rcx+0B7h]
0x1800a73fc  mov     [rsp+600h+var_591], al
0x1800a7400  mov     byte ptr [rsp+600h+var_590], 1
0x1800a7405  mov     ebx, [rsp+600h+var_590]
0x1800a7409  movups  xmm6, xmmword ptr [rsp+600h+var_5A8+8]
0x1800a740e  mov     rax, [r14+5E0h]
0x1800a7415  mov     r15d, [rax+0E4h]
0x1800a741c  and     r15d, 10h
0x1800a7420  setnz   [rsp+600h+var_5C0]
0x1800a7425  mov     rcx, r14; this
0x1800a7428  call    ?IsHotPatchUpdateRequired@ContainerObject@Details@Core@Manager@Container@@AEAA_NXZ; Container::Manager::Core::Details::ContainerObject::IsHotPatchUpdateRequired(void)
0x1800a742d  mov     dil, al
0x1800a7430  mov     [rsp+600h+var_5BF], al
0x1800a7434  mov     rcx, [r12]; SRWLock
0x1800a7438  test    rcx, rcx
0x1800a743b  jz      short loc_1800A7450
0x1800a743d  mov     [rcx+8], esi
0x1800a7440  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a7447  nop     dword ptr [rax+rax+00h]
0x1800a744c  mov     [r12], rsi
0x1800a7450  xorps   xmm0, xmm0
0x1800a7453  movups  xmmword ptr [rsp+600h+var_5A8+8], xmm0
0x1800a7458  mov     [rbp+500h+var_500], rsi
0x1800a745c  movaps  [rbp+500h+var_4F0], xmm6
0x1800a7460  mov     [rbp+500h+var_4E0], ebx
0x1800a7463  lea     rax, [rbp+500h+var_500]
0x1800a7467  mov     [rsp+600h+var_5D0], rax
0x1800a746c  lea     rax, [rsp+600h+var_5A8+8]
0x1800a7471  mov     [rsp+600h+var_5D8], rax
0x1800a7476  mov     byte ptr [rsp+600h+var_5E0], dil; int
0x1800a747b  mov     r9b, [rsp+600h+var_5C0]
0x1800a7480  lea     r8, [rbp+500h+var_4F0]
0x1800a7484  mov     rdx, [rsp+600h+SRWLock+8]
0x1800a7489  mov     rcx, r14
0x1800a748c  call    ?NotifyAgentCreating@ContainerObject@Details@Core@Manager@Container@@AEAAJAEBVCreateContainerStateTransition@CmTraceProvider@@V?$optional@U_GUID@@@utl@@_N2AEAV?$optional@_K@9@AEAV?$optional@K@9@@Z; Container::Manager::Core::Details::ContainerObject::NotifyAgentCreating(CmTraceProvider::CreateContainerStateTransition const &,utl::optional<_GUID>,bool,bool,utl::optional<unsigned __int64> &,utl::optional<ulong> &)
0x1800a7491  mov     edi, eax
0x1800a7493  lea     rbx, [r14+1C8h]
0x1800a749a  mov     rcx, rbx; SRWLock
0x1800a749d  call    cs:__imp_AcquireSRWLockExclusive
0x1800a74a4  nop     dword ptr [rax+rax+00h]
0x1800a74a9  call    cs:__imp_GetCurrentThreadId
0x1800a74b0  nop     dword ptr [rax+rax+00h]
0x1800a74b5  mov     [rbx+8], eax
0x1800a74b8  lea     rax, [rbp+500h+var_4D0]
0x1800a74bc  cmp     r12, rax
0x1800a74bf  jz      short loc_1800A74DF
0x1800a74c1  mov     rcx, [r12]; SRWLock
0x1800a74c5  test    rcx, rcx
0x1800a74c8  jz      short loc_1800A74D9
0x1800a74ca  mov     [rcx+8], esi
0x1800a74cd  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a74d4  nop     dword ptr [rax+rax+00h]
0x1800a74d9  mov     [r12], rbx
0x1800a74dd  jmp     short loc_1800A74F6
0x1800a74df  test    rbx, rbx
0x1800a74e2  jz      short loc_1800A74F6
0x1800a74e4  mov     [rbx+8], esi
0x1800a74e7  mov     rcx, rbx; SRWLock
0x1800a74ea  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a74f1  nop     dword ptr [rax+rax+00h]
0x1800a74f6  test    edi, edi
0x1800a74f8  jns     short loc_1800A751C
0x1800a74fa  mov     rcx, [rbp+508h]; this
0x1800a7501  mov     r9d, edi; char *
0x1800a7504  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a750b  mov     edx, 2C63h; void *
0x1800a7510  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7515  mov     eax, edi
0x1800a7517  jmp     loc_1800A7D27
0x1800a751c  test    r15d, r15d
0x1800a751f  jz      short loc_1800A752F
0x1800a7521  movups  xmm0, xmmword ptr [rsp+600h+var_5A8+8]
0x1800a7526  movdqu  xmmword ptr [r14+318h], xmm0
0x1800a752f  cmp     [rsp+600h+var_5BF], sil
0x1800a7534  jz      short loc_1800A7541
0x1800a7536  mov     rax, [rbp+500h+var_500]
0x1800a753a  mov     [r14+338h], rax
0x1800a7541  mov     rbx, [r14+548h]
0x1800a7548  mov     rdi, [r14+228h]
0x1800a754f  mov     rcx, rbx; SRWLock
0x1800a7552  call    cs:__imp_AcquireSRWLockExclusive
0x1800a7559  nop     dword ptr [rax+rax+00h]
0x1800a755e  call    cs:__imp_GetCurrentThreadId
0x1800a7565  nop     dword ptr [rax+rax+00h]
0x1800a756a  mov     [rbx+8], eax
0x1800a756d  lea     rax, [rbx+20h]
0x1800a7571  mov     rcx, [rax+8]
0x1800a7575  cmp     [rcx], rax
0x1800a7578  jz      short loc_1800A7581
0x1800a757a  mov     ecx, 3
0x1800a757f  int     29h; Win8: RtlFailFast(ecx)
0x1800a7581  mov     [rdi], rax
0x1800a7584  mov     [rdi+8], rcx
0x1800a7588  mov     [rcx], rdi
0x1800a758b  mov     [rax+8], rdi
0x1800a758f  mov     rcx, rbx
0x1800a7592  call    ?CheckStartStopHeartbeats@HeartbeatMonitor@Details@Core@Manager@Container@@AEAAXAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::HeartbeatMonitor::CheckStartStopHeartbeats(Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x1800a7597  mov     [rbx+8], esi
0x1800a759a  mov     rcx, rbx; SRWLock
0x1800a759d  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a75a4  nop     dword ptr [rax+rax+00h]
0x1800a75a9  mov     r15, [rsp+600h+SRWLock+8]
0x1800a75ae  jmp     short loc_1800A75B5
0x1800a75b0  xor     esi, esi
0x1800a75b2  mov     r13b, sil
0x1800a75b5  xorps   xmm0, xmm0
0x1800a75b8  movdqa  xmmword ptr [rbp+500h+var_580], xmm0
0x1800a75bd  mov     [rbp+500h+var_570], esi
0x1800a75c0  mov     [rbp+500h+var_568], sil
0x1800a75c4  lea     rax, [rbp+500h+var_560]
0x1800a75c8  mov     [rbp+500h+var_558], rax
0x1800a75cc  lea     rax, [rbp+500h+var_560]
0x1800a75d0  mov     [rbp+500h+var_560], rax
0x1800a75d4  mov     [rbp+500h+Address], esi
0x1800a75d7  xor     eax, eax
0x1800a75d9  mov     [rbp+500h+var_54C], rax
0x1800a75dd  mov     byte ptr [rbp+500h+var_54C], sil
0x1800a75e1  mov     byte ptr [rbp+500h+var_54C+4], sil
0x1800a75e5  cmp     [r14+98h], sil
0x1800a75ec  jz      loc_1800A7699
0x1800a75f2  lea     rcx, [rsp+600h+SRWLock+8]
0x1800a75f7  call    ??$make_shared@UMirrorNetworksSynchronizeContext@ContainerObject@Details@Core@Manager@Container@@$$V@utl@@YA?AV?$shared_ptr@UMirrorNetworksSynchronizeContext@ContainerObject@Details@Core@Manager@Container@@@0@XZ; utl::make_shared<Container::Manager::Core::Details::ContainerObject::MirrorNetworksSynchronizeContext,>(void)
0x1800a75fc  mov     rax, [rsp+600h+SRWLock+8]
0x1800a7601  test    rax, rax
0x1800a7604  jz      loc_1800A76F9
0x1800a760a  mov     dword ptr [rax+18h], 3
0x1800a7611  mov     rcx, [r15+110h]
0x1800a7618  movups  xmm0, xmmword ptr [rcx+8]
0x1800a761c  movdqu  xmmword ptr [rax+1Ch], xmm0
0x1800a7621  cmp     [rax+2Ch], sil
0x1800a7625  jnz     short loc_1800A762B
0x1800a7627  mov     byte ptr [rax+2Ch], 1
0x1800a762b  movaps  xmm0, xmmword ptr [rsp+600h+SRWLock+8]
0x1800a7630  movdqa  xmmword ptr [rsp+600h+var_5A8+8], xmm0
0x1800a7636  lea     r9, [rbp+500h+var_580]
0x1800a763a  lea     r8, [rsp+600h+var_5A8+8]
0x1800a763f  mov     edx, 1
0x1800a7644  mov     rcx, r14
0x1800a7647  call    ?QueueMirrorNetworkWorkItems@ContainerObject@Details@Core@Manager@Container@@AEAAJW4MirrorNetworkWorkItemType@12345@V?$shared_ptr@UMirrorNetworksSynchronizeContext@ContainerObject@Details@Core@Manager@Container@@@utl@@PEAUWorkItemGroup@12345@@Z; Container::Manager::Core::Details::ContainerObject::QueueMirrorNetworkWorkItems(Container::Manager::Core::Details::ContainerObject::MirrorNetworkWorkItemType,utl::shared_ptr<Container::Manager::Core::Details::ContainerObject::MirrorNetworksSynchronizeContext>,Container::Manager::Core::Details::ContainerObject::WorkItemGroup *)
0x1800a764c  mov     edi, eax
0x1800a764e  test    eax, eax
0x1800a7650  jns     short loc_1800A7699
0x1800a7652  mov     rcx, [rbp+508h]; this
0x1800a7659  mov     r9d, eax; char *
0x1800a765c  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a7663  mov     edx, 2C91h; void *
0x1800a7668  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a766d  nop
0x1800a766e  mov     rbx, [rbp+500h+var_580]
0x1800a7672  mov     [rbp+500h+var_580], rsi
0x1800a7676  test    rbx, rbx
0x1800a7679  jz      loc_1800A7515
0x1800a767f  mov     rcx, rbx
0x1800a7682  call    ??1?$ListEntry@V?$unique_ptr@UWorkItem@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UWorkItem@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@Csl@@QEAA@XZ; Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>::~ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>(void)
0x1800a7687  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x1800a768c  mov     rcx, rbx; void *
0x1800a768f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a7694  jmp     loc_1800A7515
0x1800a7699  test    r13b, r13b
0x1800a769c  jz      loc_1800A776A
0x1800a76a2  mov     rcx, [r14+4F0h]
0x1800a76a9  cmp     [rcx+4E0h], sil
0x1800a76b0  jnz     short loc_1800A76B4
0x1800a76b2  int     2Ch; Windows NT - assertion failure
  ... truncated ...
```
