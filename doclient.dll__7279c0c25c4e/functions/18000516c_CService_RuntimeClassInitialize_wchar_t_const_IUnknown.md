# CService::RuntimeClassInitialize(wchar_t const *,IUnknown *)

- ea: `0x18000516c`
- end: `0x180005818`
- name: `?RuntimeClassInitialize@CService@@QEAAJPEB_WPEAUIUnknown@@@Z`
- size: `1708`
- prototype: `int __fastcall(struct IClassFactory *this, LPCWSTR lpServiceName, struct IUnknown *)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180007040`

## callees

- `0x18000516c`
- `0x180005e20`
- `0x180006530`
- `0x18000739c`
- `0x180007ca4`
- `0x180007ea0`
- `0x1800089f8`
- `0x180008a54`
- `0x180008b1c`
- `0x180008cbc`
- `0x180008d14`
- `0x180008fb8`
- `0x18000a4e0`
- `0x1800181b8`
- `0x180019010`
- `0x18007d454`
- `0x18009b290`
- `0x18009b880`
- `0x1800a20ac`
- `0x1800a274c`
- `0x1800a3238`
- `0x1800a3ea8`
- `0x1800f82f0`
- `0x1800f8314`
- `0x1800f8320`
- `0x180108e50`
- `0x180108ed0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005502`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005502`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800051f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800051f1`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800054c0`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800054c0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800051a4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800051a4`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000535c`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000535c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005624`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005624`
- `WS2_32!__imp_WSAStartup` at `0x1800053b3`
- `WS2_32!__imp_WSAStartup` at `0x1800053b3`

## string_xrefs

- `0x18000523f`: `C:\__w\1\s\src\DeliveryOptimization\dll\dosvc.cpp`
- `0x180005293`: `C:\__w\1\s\src\DeliveryOptimization\dll\dosvc.cpp`
- `0x180005376`: `Failed to register service control handler`
- `0x18000540e`: `Failed to open DO registry root, redirected ? %u, path : %hs`
- `0x18000545a`: `MigrateRegistry failed`
- `0x180005521`: `Failed to create ShutdownEvent`
- `0x180005638`: `Failed to CoCreate CLSID_ContextSwitcher`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
int __fastcall CService::RuntimeClassInitialize(struct IClassFactory *this, LPCWSTR lpServiceName, struct IUnknown *a3)
{
  CService *v6; // rcx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // r14
  struct IClassFactoryVtbl *lpVtbl; // rcx
  int v9; // eax
  HRESULT (__stdcall *v10)(IUnknown *, const IID *const, void **); // r15
  struct IClassFactoryVtbl *v11; // rcx
  struct IDOPlatformHost *v12; // rax
  struct IClassFactoryVtbl *v13; // rax
  COrderedTaskExecutor *v14; // rbx
  int v15; // edx
  unsigned int v17; // eax
  int v18; // ebx
  CService *v19; // rcx
  unsigned int v20; // eax
  int v21; // eax
  unsigned int v22; // eax
  CTraceConsumer *Instance; // rax
  unsigned int refreshed; // eax
  wil::details *v25; // rcx
  struct IClassFactoryVtbl *Event; // r14
  struct IClassFactoryVtbl *v27; // rbx
  DWORD LastError; // r12d
  unsigned int v29; // r8d
  const char *v30; // r9
  int LastErrorFailHr; // ebx
  struct IClassFactoryVtbl *v32; // r12
  volatile signed __int32 *v33; // rbx
  struct IClassFactory *v34; // r12
  struct IClassFactoryVtbl *v35; // rcx
  HRESULT v36; // ebx
  int v37; // ebx
  struct IClassFactoryVtbl *v38; // rbx
  char *v39; // rcx
  struct IClassFactoryVtbl *v40; // rax
  volatile signed __int32 *v41; // rbx
  int v42; // edx
  int v43; // ebx
  LPVOID *ppv; // [rsp+20h] [rbp-228h]
  int ppva; // [rsp+20h] [rbp-228h]
  char *v46; // [rsp+28h] [rbp-220h]
  char *v47; // [rsp+28h] [rbp-220h]
  char *v48; // [rsp+28h] [rbp-220h]
  char *v49; // [rsp+28h] [rbp-220h]
  void *v50; // [rsp+40h] [rbp-208h]
  void *v51; // [rsp+40h] [rbp-208h]
  char *v52; // [rsp+40h] [rbp-208h]
  _QWORD v53[2]; // [rsp+50h] [rbp-1F8h] BYREF
  WSAData WSAData; // [rsp+60h] [rbp-1E8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  AcquireSRWLockExclusive(&CService::_svcStatusLock);
  v6 = CService::s_spServiceRef;
  if ( CService::s_spServiceRef != (CService *)this )
  {
    if ( this )
    {
      ((void (__fastcall *)(struct IClassFactory *))this->lpVtbl->AddRef)(this);
      v6 = CService::s_spServiceRef;
    }
    CService::s_spServiceRef = (CService *)this;
    if ( v6 )
      (*(void (__fastcall **)(CService *))(*(_QWORD *)v6 + 16LL))(v6);
  }
  ReleaseSRWLockExclusive(&CService::_svcStatusLock);
  if ( a3 )
  {
    QueryInterface = a3->lpVtbl->QueryInterface;
    lpVtbl = this[13].lpVtbl;
    if ( lpVtbl )
    {
      this[13].lpVtbl = 0;
      (*((void (__fastcall **)(struct IClassFactoryVtbl *, HRESULT (__stdcall *)(IClassFactory *, const IID *const, void **)))lpVtbl->QueryInterface
       + 2))(
        lpVtbl,
        lpVtbl->QueryInterface);
    }
    v9 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IClassFactory *))QueryInterface)(
           a3,
           &GUID_a92e7211_62cc_4a07_8e5c_2972f0bfe476,
           &this[13]);
    if ( v9 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x38,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\dosvc.cpp",
        (const char *)(unsigned int)v9,
        (int)ppv);
    v10 = a3->lpVtbl->QueryInterface;
    v11 = this[14].lpVtbl;
    if ( v11 )
    {
      this[14].lpVtbl = 0;
      (*((void (__fastcall **)(struct IClassFactoryVtbl *, HRESULT (__stdcall *)(IClassFactory *, const IID *const, void **)))v11->QueryInterface
       + 2))(
        v11,
        v11->QueryInterface);
    }
    ((void (__fastcall *)(struct IUnknown *, GUID *, struct IClassFactory *))v10)(
      a3,
      &GUID_67ed8e25_a748_4265_a6d4_8cdd80016333,
      &this[14]);
  }
  v50 = operator new(0x1E0u);
  memset(v50, 0, 0x1E0u);
  CDOThreadPool::s_pGlobalInstance = (CDOThreadPool *)CDOThreadPool::CDOThreadPool(v50, 30);
  v12 = (struct IDOPlatformHost *)&this[4];
  if ( !this )
    v12 = 0;
  CGlobalObjects::_pPlatformHost = v12;
  v51 = operator new(0x68u);
  memset(v51, 0, 0x68u);
  v13 = (struct IClassFactoryVtbl *)COrderedTaskExecutor::COrderedTaskExecutor((COrderedTaskExecutor *)v51);
  v14 = (COrderedTaskExecutor *)this[16].lpVtbl;
  this[16].lpVtbl = v13;
  if ( v14 )
  {
    COrderedTaskExecutor::CancelPendingTasks(v14, 1);
    std::_Tree<std::_Tmap_traits<std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>,std::unique_ptr<CTaskQueue::Task>,std::less<std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>>,std::allocator<std::pair<std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>> const,std::unique_ptr<CTaskQueue::Task>>>,1>>::~_Tree<std::_Tmap_traits<std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>,std::unique_ptr<CTaskQueue::Task>,std::less<std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>>,std::allocator<std::pair<std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>> const,std::unique_ptr<CTaskQueue::Task>>>,1>>(v14);
    operator delete(v14);
  }
  CService::_hSvcStatus = RegisterServiceCtrlHandlerExW(lpServiceName, CService::s_SvcCtrlHandlerEx, 0);
  if ( !CService::_hSvcStatus )
    return wil::details::in1diag3::Return_GetLastErrorMsg(
             retaddr,
             (void *)0x40,
             (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\dosvc.cpp",
             "Failed to register service control handler",
             (const char *)ppv);
  CService::s_NotifySvcStatus(2u, v15);
  memset(&WSAData, 0, sizeof(WSAData));
  v17 = WSAStartup(0x202u, &WSAData);
  if ( v17 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x45,
             (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\dosvc.cpp",
             (const char *)v17,
             (unsigned int)ppv);
  CPersistenceLocation::Instance();
  v18 = *((unsigned __int8 *)CPersistenceLocation::Instance() + 160);
  v20 = CService::_EnsureDORegRoot(v19);
  LODWORD(v46) = v18;
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0x4B,
    (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\dosvc.cpp",
    (const char *)v20,
    (int)"Failed to open DO registry root, redirected ? %u, path : %hs",
    v46);
  v21 = CPersistenceLocation::EnsureDefaultBasePaths();
  if ( v21 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\dosvc.cpp",
      (const char *)(unsigned int)v21,
      ppva);
  v22 = MigrateRegistry(0);
  if ( wil::details::in1diag3::Log_IfFailedMsg(
         retaddr,
         (void *)0x4F,
         (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\dosvc.cpp",
         (const char *)v22,
         (int)"MigrateRegistry failed",
         v47) >= 0 )
  {
    Instance = CTraceConsumer::getInstance();
    refreshed = CTraceConsumer::RefreshProperties(Instance);
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0x51,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\dosvc.cpp",
      (const char *)refreshed,
      (int)"CTraceConsumer.RefreshProperties failed",
      v48);
  }
  CServiceLocker::SetSvcFactory(this);
  Event = (struct IClassFactoryVtbl *)CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    v27 = this[5].lpVtbl;
    if ( v27 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v27) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v29, v30);
      SetLastError(LastError);
    }
    this[5].lpVtbl = Event;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v25);
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x56,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\dosvc.cpp",
        (const char *)(unsigned int)LastErrorFailHr,
        (int)"Failed to create ShutdownEvent",
        v48);
      return LastErrorFailHr;
    }
  }
  v32 = this[16].lpVtbl;
  v52 = (char *)operator new(0x38u);
  *((_DWORD *)v52 + 2) = 1;
  *((_DWORD *)v52 + 3) = 1;
  *(_QWORD *)v52 = &std::_Ref_count_obj2<CUserToken>::`vftable';
  *((_QWORD *)v52 + 2) = 0;
  *((_QWORD *)v52 + 3) = 0;
  *((_QWORD *)v52 + 4) = 0;
  v52[40] = 1;
  *((_QWORD *)v52 + 6) = v32;
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    v52 + 16,
    1,
    0,
    0,
    0);
  this[10].lpVtbl = (struct IClassFactoryVtbl *)(v52 + 16);
  v33 = (volatile signed __int32 *)this[11].lpVtbl;
  this[11].lpVtbl = (struct IClassFactoryVtbl *)v52;
  if ( v33 )
  {
    if ( _InterlockedExchangeAdd(v33 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
      if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
    }
  }
  v34 = this + 12;
  v35 = this[12].lpVtbl;
  if ( v35 )
  {
    v34->lpVtbl = 0;
    (*((void (__fastcall **)(struct IClassFactoryVtbl *))v35->QueryInterface + 2))(v35);
  }
  v36 = CoCreateInstance(
          &CLSID_ContextSwitcher,
          0,
          1u,
          &GUID_000001da_0000_0000_c000_000000000046,
          (LPVOID *)&this[12].lpVtbl);
  if ( v36 >= 0 )
  {
    v37 = CDeliveryOptimizationManager::Make(&this[6]);
    if ( v37 >= 0 )
    {
      v38 = this[16].lpVtbl;
      v39 = (char *)operator new(0x50u);
      *((_DWORD *)v39 + 2) = 1;
      *((_DWORD *)v39 + 3) = 1;
      *(_QWORD *)v39 = &std::_Ref_count_obj2<CUsageCallback>::`vftable';
      *((_QWORD *)v39 + 2) = &CUsageCallback::`vftable';
      *((_QWORD *)v39 + 3) = 0;
      *((_QWORD *)v39 + 4) = 0;
      v40 = this[7].lpVtbl;
      if ( v40 )
        _InterlockedAdd((volatile signed __int32 *)&v40->AddRef, 1u);
      *((struct IClassFactory *)v39 + 3) = this[6];
      *((struct IClassFactory *)v39 + 4) = this[7];
      *((_QWORD *)v39 + 5) = 0;
      *((_QWORD *)v39 + 6) = 0;
      *((_QWORD *)v39 + 7) = 0;
      *((_QWORD *)v39 + 8) = 0;
      *((_QWORD *)v39 + 9) = v38;
      this[8].lpVtbl = (struct IClassFactoryVtbl *)(v39 + 16);
      v41 = (volatile signed __int32 *)this[9].lpVtbl;
      this[9].lpVtbl = (struct IClassFactoryVtbl *)v39;
      if ( v41 )
      {
        if ( _InterlockedExchangeAdd(v41 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v41)(v41);
          if ( _InterlockedExchangeAdd(v41 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v41 + 8LL))(v41);
        }
      }
      ((void (__fastcall *)(struct IClassFactory *, __int64))this->lpVtbl->LockServer)(this, 1);
      CService::s_NotifySvcStatus(4u, v42);
      v53[0] = 0;
      v53[1] = this;
      v43 = (*((__int64 (__fastcall **)(struct IClassFactoryVtbl *, __int64 (__fastcall *)(struct tagComCallData *), _QWORD *, GUID *, int, _QWORD))v34->lpVtbl->QueryInterface
             + 3))(
              v34->lpVtbl,
              CService::RegisterClassFactory,
              v53,
              &GUID_000001da_0000_0000_c000_000000000046,
              5,
              0);
      if ( v43 >= 0 )
      {
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x6D,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\dosvc.cpp",
          (const char *)(unsigned int)v43,
          (int)"RegisterClassFactory failed",
          v49);
        return v43;
      }
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x5E,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\dosvc.cpp",
        (const char *)(unsigned int)v37,
        (int)"Failed to make DO Manager",
        v48);
      return v37;
    }
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x5C,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\dosvc.cpp",
      (const char *)(unsigned int)v36,
      (int)"Failed to CoCreate CLSID_ContextSwitcher",
      v48);
    return v36;
  }
}

```

## disassembly

```asm
0x18000516c  push    rbx
0x18000516e  push    rsi
0x18000516f  push    rdi
0x180005170  push    r12
0x180005172  push    r13
0x180005174  push    r14
0x180005176  push    r15
0x180005178  sub     rsp, 210h
0x18000517f  mov     rax, cs:__security_cookie
0x180005186  xor     rax, rsp
0x180005189  mov     [rsp+248h+var_48], rax
0x180005191  mov     rbx, r8
0x180005194  mov     r12, rdx
0x180005197  mov     rdi, rcx
0x18000519a  xor     r13d, r13d
0x18000519d  lea     rcx, ?_svcStatusLock@CService@@0VSRWLock@Wrappers@WRL@Microsoft@@A; SRWLock
0x1800051a4  call    cs:__imp_AcquireSRWLockExclusive
0x1800051aa  mov     rcx, cs:?s_spServiceRef@CService@@0V?$ComPtr@VCService@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<CService> CService::s_spServiceRef
0x1800051b1  cmp     rcx, rdi
0x1800051b4  jz      short loc_1800051EA
0x1800051b6  test    rdi, rdi
0x1800051b9  jz      short loc_1800051D1
0x1800051bb  mov     rax, [rdi]
0x1800051be  mov     rcx, rdi
0x1800051c1  mov     rax, [rax+8]
0x1800051c5  call    _guard_dispatch_icall
0x1800051ca  mov     rcx, cs:?s_spServiceRef@CService@@0V?$ComPtr@VCService@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<CService> CService::s_spServiceRef
0x1800051d1  mov     cs:?s_spServiceRef@CService@@0V?$ComPtr@VCService@@@WRL@Microsoft@@A, rdi; Microsoft::WRL::ComPtr<CService> CService::s_spServiceRef
0x1800051d8  test    rcx, rcx
0x1800051db  jz      short loc_1800051EA
0x1800051dd  mov     rax, [rcx]
0x1800051e0  mov     rax, [rax+10h]
0x1800051e4  call    _guard_dispatch_icall
0x1800051e9  nop
0x1800051ea  lea     rcx, ?_svcStatusLock@CService@@0VSRWLock@Wrappers@WRL@Microsoft@@A; SRWLock
0x1800051f1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800051f7  test    rbx, rbx
0x1800051fa  jz      loc_180005293
0x180005200  mov     rax, [rbx]
0x180005203  mov     r14, [rax]
0x180005206  lea     rsi, [rdi+68h]
0x18000520a  mov     rcx, [rsi]
0x18000520d  test    rcx, rcx
0x180005210  jz      short loc_180005222
0x180005212  mov     [rsi], r13
0x180005215  mov     rdx, [rcx]
0x180005218  mov     rax, [rdx+10h]
0x18000521c  call    _guard_dispatch_icall
0x180005221  nop
0x180005222  mov     r8, rsi
0x180005225  lea     rdx, _GUID_a92e7211_62cc_4a07_8e5c_2972f0bfe476
0x18000522c  mov     rcx, rbx
0x18000522f  mov     rax, r14
0x180005232  call    _guard_dispatch_icall
0x180005237  mov     rcx, [rsp+248h]; this
0x18000523f  lea     rsi, aCW1SSrcDeliver_56; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x180005246  test    eax, eax
0x180005248  jns     short loc_18000525A
0x18000524a  mov     r9d, eax; char *
0x18000524d  mov     r8, rsi; unsigned int
0x180005250  mov     edx, 38h ; '8'; void *
0x180005255  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000525a  mov     rax, [rbx]
0x18000525d  mov     r15, [rax]
0x180005260  lea     r14, [rdi+70h]
0x180005264  mov     rcx, [r14]
0x180005267  test    rcx, rcx
0x18000526a  jz      short loc_18000527C
0x18000526c  mov     [r14], r13
0x18000526f  mov     rdx, [rcx]
0x180005272  mov     rax, [rdx+10h]
0x180005276  call    _guard_dispatch_icall
0x18000527b  nop
0x18000527c  mov     r8, r14
0x18000527f  lea     rdx, _GUID_67ed8e25_a748_4265_a6d4_8cdd80016333
0x180005286  mov     rcx, rbx
0x180005289  mov     rax, r15
0x18000528c  call    _guard_dispatch_icall
0x180005291  jmp     short loc_18000529A
0x180005293  lea     rsi, aCW1SSrcDeliver_56; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000529a  mov     r14d, 1E0h
0x1800052a0  mov     ecx, r14d; Size
0x1800052a3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800052a8  mov     rbx, rax
0x1800052ab  mov     [rsp+248h+var_208], rax
0x1800052b0  mov     r8d, r14d; Size
0x1800052b3  xor     edx, edx; Val
0x1800052b5  mov     rcx, rax; void *
0x1800052b8  call    memset
0x1800052bd  mov     edx, 1Eh
0x1800052c2  mov     rcx, rbx
0x1800052c5  call    ??0CDOThreadPool@@QEAA@V?$duration@_JU?$ratio@$00$00@std@@@chrono@std@@@Z; CDOThreadPool::CDOThreadPool(std::chrono::duration<__int64,std::ratio<1,1>>)
0x1800052ca  nop
0x1800052cb  mov     cs:?s_pGlobalInstance@CDOThreadPool@@0PEAV1@EA, rax; CDOThreadPool * CDOThreadPool::s_pGlobalInstance
0x1800052d2  test    rdi, rdi
0x1800052d5  lea     rax, [rdi+20h]
0x1800052d9  jnz     short loc_1800052DE
0x1800052db  mov     rax, r13
0x1800052de  mov     cs:?_pPlatformHost@CGlobalObjects@@0PEAVIDOPlatformHost@@EA, rax; IDOPlatformHost * CGlobalObjects::_pPlatformHost
0x1800052e5  mov     r14d, 68h ; 'h'
0x1800052eb  mov     ecx, r14d; Size
0x1800052ee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800052f3  mov     rbx, rax
0x1800052f6  mov     [rsp+248h+var_208], rax
0x1800052fb  mov     r8d, r14d; Size
0x1800052fe  xor     edx, edx; Val
0x180005300  mov     rcx, rax; void *
0x180005303  call    memset
0x180005308  mov     rcx, rbx; this
0x18000530b  call    ??0COrderedTaskExecutor@@QEAA@XZ; COrderedTaskExecutor::COrderedTaskExecutor(void)
0x180005310  nop
0x180005311  mov     rbx, [rdi+80h]
0x180005318  mov     [rdi+80h], rax
0x18000531f  test    rbx, rbx
0x180005322  jz      short loc_180005349
0x180005324  lea     r15d, [r14-67h]
0x180005328  mov     dl, r15b; bool
0x18000532b  mov     rcx, rbx; this
0x18000532e  call    ?CancelPendingTasks@COrderedTaskExecutor@@QEAAX_N@Z; COrderedTaskExecutor::CancelPendingTasks(bool)
0x180005333  mov     rcx, rbx
0x180005336  call    ??1?$_Tree@V?$_Tmap_traits@V?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@std@@V?$unique_ptr@VTask@CTaskQueue@@U?$default_delete@VTask@CTaskQueue@@@std@@@3@U?$less@V?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@std@@@3@V?$allocator@U?$pair@$$CBV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@std@@V?$unique_ptr@VTask@CTaskQueue@@U?$default_delete@VTask@CTaskQueue@@@std@@@3@@std@@@3@$00@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>,std::unique_ptr<CTaskQueue::Task>,std::less<std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>>,std::allocator<std::pair<std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>> const,std::unique_ptr<CTaskQueue::Task>>>,1>>::~_Tree<std::_Tmap_traits<std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>,std::unique_ptr<CTaskQueue::Task>,std::less<std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>>,std::allocator<std::pair<std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>> const,std::unique_ptr<CTaskQueue::Task>>>,1>>(void)
0x18000533b  nop
0x18000533c  mov     edx, r14d
0x18000533f  mov     rcx, rbx; Block
0x180005342  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005347  jmp     short loc_18000534F
0x180005349  mov     r15d, 1
0x18000534f  xor     r8d, r8d; lpContext
0x180005352  lea     rdx, ?s_SvcCtrlHandlerEx@CService@@CAKKKPEAX0@Z; lpHandlerProc
0x180005359  mov     rcx, r12; lpServiceName
0x18000535c  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180005362  mov     cs:?_hSvcStatus@CService@@0PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * CService::_hSvcStatus
0x180005369  test    rax, rax
0x18000536c  jnz     short loc_18000538D
0x18000536e  mov     rcx, [rsp+248h]; this
0x180005376  lea     r9, aFailedToRegist_7; "Failed to register service control hand"...
0x18000537d  mov     r8, rsi; unsigned int
0x180005380  lea     edx, [rax+40h]; void *
0x180005383  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180005388  jmp     loc_1800057E9
0x18000538d  mov     ecx, 2; unsigned int
0x180005392  call    ?s_NotifySvcStatus@CService@@SAXKJ@Z; CService::s_NotifySvcStatus(ulong,long)
0x180005397  xor     edx, edx; Val
0x180005399  mov     r8d, 198h; Size
0x18000539f  lea     rcx, [rsp+248h+WSAData]; void *
0x1800053a4  call    memset
0x1800053a9  mov     ecx, 202h; wVersionRequested
0x1800053ae  lea     rdx, [rsp+248h+WSAData]; lpWSAData
0x1800053b3  call    cs:__imp_WSAStartup
0x1800053b9  test    eax, eax
0x1800053bb  jz      short loc_1800053DA
0x1800053bd  mov     rcx, [rsp+248h]; this
0x1800053c5  mov     r9d, eax; char *
0x1800053c8  mov     r8, rsi; unsigned int
0x1800053cb  mov     edx, 45h ; 'E'; void *
0x1800053d0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800053d5  jmp     loc_1800057E9
0x1800053da  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x1800053df  mov     r14, rax
0x1800053e2  cmp     qword ptr [rax+18h], 0Fh
0x1800053e7  jbe     short loc_1800053EC
0x1800053e9  mov     r14, [rax]
0x1800053ec  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x1800053f1  movzx   ebx, byte ptr [rax+0A0h]
0x1800053f8  call    ?_EnsureDORegRoot@CService@@AEAAJXZ; CService::_EnsureDORegRoot(void)
0x1800053fd  mov     rcx, [rsp+248h]; this
0x180005405  mov     [rsp+248h+var_218], r14
0x18000540a  mov     dword ptr [rsp+248h+var_220], ebx; char *
0x18000540e  lea     rdx, aFailedToOpenDo; "Failed to open DO registry root, redire"...
0x180005415  mov     [rsp+248h+ppv], rdx; int
0x18000541a  mov     r9d, eax; char *
0x18000541d  mov     r8, rsi; unsigned int
0x180005420  mov     edx, 4Bh ; 'K'; void *
0x180005425  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000542a  call    ?EnsureDefaultBasePaths@CPersistenceLocation@@SAJXZ; CPersistenceLocation::EnsureDefaultBasePaths(void)
0x18000542f  mov     rcx, [rsp+248h]; this
0x180005437  test    eax, eax
0x180005439  jns     short loc_18000544B
0x18000543b  mov     r9d, eax; char *
0x18000543e  mov     r8, rsi; unsigned int
0x180005441  mov     edx, 4Dh ; 'M'; void *
0x180005446  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000544b  xor     ecx, ecx
0x18000544d  call    MigrateRegistry
0x180005452  mov     rcx, [rsp+248h]; this
0x18000545a  lea     rdx, aMigrateregistr; "MigrateRegistry failed"
0x180005461  mov     [rsp+248h+ppv], rdx; int
0x180005466  mov     r9d, eax; char *
0x180005469  mov     r8, rsi; unsigned int
0x18000546c  mov     edx, 4Fh ; 'O'; void *
0x180005471  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180005476  test    eax, eax
0x180005478  js      short loc_1800054AB
0x18000547a  call    ?getInstance@CTraceConsumer@@SAAEAV1@XZ; CTraceConsumer::getInstance(void)
0x18000547f  mov     rcx, rax; this
0x180005482  call    ?RefreshProperties@CTraceConsumer@@QEAAJXZ; CTraceConsumer::RefreshProperties(void)
0x180005487  mov     rcx, [rsp+248h]; this
0x18000548f  lea     rdx, aCtraceconsumer_0; "CTraceConsumer.RefreshProperties failed"
0x180005496  mov     [rsp+248h+ppv], rdx; int
0x18000549b  mov     r9d, eax; char *
0x18000549e  mov     r8, rsi; unsigned int
0x1800054a1  mov     edx, 51h ; 'Q'; void *
0x1800054a6  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800054ab  mov     rcx, rdi; struct IClassFactory *
0x1800054ae  call    ?SetSvcFactory@CServiceLocker@@SAXPEAUIClassFactory@@@Z; CServiceLocker::SetSvcFactory(IClassFactory *)
0x1800054b3  mov     r9d, 1F0003h; dwDesiredAccess
0x1800054b9  mov     r8d, r15d; dwFlags
0x1800054bc  xor     edx, edx; lpName
0x1800054be  xor     ecx, ecx; lpEventAttributes
0x1800054c0  call    cs:__imp_CreateEventExW
0x1800054c6  mov     r14, rax
0x1800054c9  test    rax, rax
0x1800054cc  jz      short loc_18000550E
0x1800054ce  call    cs:__imp_GetLastError
0x1800054d4  mov     rbx, [rdi+28h]
0x1800054d8  test    rbx, rbx
0x1800054db  jz      short loc_180005508
0x1800054dd  call    cs:__imp_GetLastError
0x1800054e3  mov     r12d, eax
0x1800054e6  mov     rcx, rbx; hObject
0x1800054e9  call    cs:__imp_CloseHandle
0x1800054ef  mov     rcx, [rsp+248h]; this
0x1800054f7  test    eax, eax
0x1800054f9  jz      loc_18000580C
0x1800054ff  mov     ecx, r12d; dwErrCode
0x180005502  call    cs:__imp_SetLastError
0x180005508  mov     [rdi+28h], r14
0x18000550c  jmp     short loc_180005544
0x18000550e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005513  mov     ebx, eax
0x180005515  test    eax, eax
0x180005517  jns     short loc_180005544
0x180005519  mov     rcx, [rsp+248h]; this
0x180005521  lea     rax, aFailedToCreate_0; "Failed to create ShutdownEvent"
0x180005528  mov     [rsp+248h+ppv], rax; int
0x18000552d  mov     r9d, ebx; char *
0x180005530  mov     r8, rsi; unsigned int
0x180005533  mov     edx, 56h ; 'V'; void *
0x180005538  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000553d  mov     eax, ebx
0x18000553f  jmp     loc_1800057E9
0x180005544  mov     r12, [rdi+80h]
0x18000554b  mov     ecx, 38h ; '8'; Size
0x180005550  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005555  mov     r14, rax
0x180005558  mov     [rsp+248h+var_208], rax
0x18000555d  mov     [rax+8], r15d
0x180005561  mov     [rax+0Ch], r15d
0x180005565  lea     rax, ??_7?$_Ref_count_obj2@VCUserToken@@@std@@6B@; const std::_Ref_count_obj2<CUserToken>::`vftable'
0x18000556c  mov     [r14], rax
0x18000556f  lea     rbx, [r14+10h]
0x180005573  mov     [rsp+248h+var_200], rbx
0x180005578  mov     [rbx], r13
0x18000557b  mov     [rbx+8], r13
0x18000557f  mov     [rbx+10h], r13
0x180005583  mov     [rbx+18h], r15b
0x180005587  mov     [rbx+20h], r12
0x18000558b  mov     [rsp+248h+ppv], r13
0x180005590  xor     r9d, r9d
0x180005593  xor     r8d, r8d
0x180005596  mov     edx, r15d
0x180005599  mov     rcx, rbx
0x18000559c  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800055a1  nop
0x1800055a2  mov     [rdi+50h], rbx
0x1800055a6  mov     rbx, [rdi+58h]
0x1800055aa  mov     [rdi+58h], r14
0x1800055ae  or      r14d, 0FFFFFFFFh
0x1800055b2  test    rbx, rbx
0x1800055b5  jz      short loc_1800055EE
0x1800055b7  mov     eax, r14d
0x1800055ba  lock xadd [rbx+8], eax
0x1800055bf  add     eax, r14d
0x1800055c2  jnz     short loc_1800055EE
0x1800055c4  mov     rax, [rbx]
0x1800055c7  mov     rcx, rbx
0x1800055ca  mov     rax, [rax]
0x1800055cd  call    _guard_dispatch_icall
0x1800055d2  mov     eax, r14d
0x1800055d5  lock xadd [rbx+0Ch], eax
0x1800055da  add     eax, r14d
0x1800055dd  jnz     short loc_1800055EE
0x1800055df  mov     rax, [rbx]
0x1800055e2  mov     rcx, rbx
0x1800055e5  mov     rax, [rax+8]
0x1800055e9  call    _guard_dispatch_icall
0x1800055ee  lea     r12, [rdi+60h]
0x1800055f2  mov     rcx, [r12]
0x1800055f6  test    rcx, rcx
0x1800055f9  jz      short loc_18000560C
0x1800055fb  mov     [r12], r13
0x1800055ff  mov     rax, [rcx]
0x180005602  mov     rax, [rax+10h]
0x180005606  call    _guard_dispatch_icall
0x18000560b  nop
0x18000560c  mov     [rsp+248h+ppv], r12; ppv
0x180005611  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x180005618  mov     r8d, r15d; dwClsContext
0x18000561b  xor     edx, edx; pUnkOuter
0x18000561d  lea     rcx, CLSID_ContextSwitcher; rclsid
  ... truncated ...
```
