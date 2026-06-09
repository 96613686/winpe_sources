# CJob::~CJob(void)

- ea: `0x18002b5a0`
- end: `0x18002bee9`
- name: `??1CJob@@UEAA@XZ`
- size: `2377`
- prototype: `void __fastcall(CJob *__hidden this)`
- caller_count: `4`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180088e80`
- `0x1800cc15c`
- `0x1800ff75b`
- `0x18010716f`

## callees

- `0x18001d7f0`
- `0x18002b5a0`
- `0x18002bef0`
- `0x18002c360`
- `0x18002c6ac`
- `0x18002c6e0`
- `0x18002c718`
- `0x18002e6b8`
- `0x1800410b0`
- `0x180065728`
- `0x180066e6c`
- `0x180078768`
- `0x1800861d8`
- `0x180088fd4`
- `0x1800938ac`
- `0x180094cd4`
- `0x180099740`
- `0x18009e9c8`
- `0x1800a3444`
- `0x1800a7558`
- `0x1800ab7fc`
- `0x1800acacc`
- `0x18010f010`

## import_xrefs

- `combase!__imp_CoReleaseSharedService` at `0x18002b98e`
- `combase!__imp_CoReleaseSharedService` at `0x18002b98e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002bb78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002bb78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bb9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bb9b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b978`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b978`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b9f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b9f8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ba34`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ba34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b8c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002baab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b8c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002baab`
- `CRYPT32!CertCloseStore` at `0x18002bbed`
- `CRYPT32!CertCloseStore` at `0x18002bbed`
- `CRYPT32!CertFreeCertificateContext` at `0x18002bbd9`
- `CRYPT32!CertFreeCertificateContext` at `0x18002bbd9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CJob::~CJob(CJob *this)
{
  struct TaskSchedulerWorkItem *v2; // rdx
  struct TaskSchedulerWorkItem *v3; // rdx
  struct TaskSchedulerWorkItem *v4; // rdx
  struct TaskSchedulerWorkItem *v5; // rdx
  unsigned int v6; // edx
  CJobSecurityDescriptor *v7; // rcx
  _QWORD *i; // rbx
  __int64 v9; // rax
  __int64 v10; // rdx
  int v11; // ebx
  unsigned int v12; // eax
  unsigned int v13; // eax
  void *v14; // rcx
  __int64 v15; // rcx
  unsigned int v16; // eax
  unsigned int v17; // edx
  __int64 v18; // rcx
  char *v19; // rcx
  void **v20; // rdi
  void **v21; // rbx
  void *v22; // rbp
  DWORD LastError; // eax
  const CERT_CONTEXT *v24; // rcx
  void *v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  CEncryptedBlob *v28; // rcx
  __int64 v29; // rax
  char *v30; // rcx
  CEncryptedCredentials *v31; // rdi
  void *v32; // rax
  unsigned int v33; // edx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // [rsp+80h] [rbp+8h] BYREF

  *(_QWORD *)this = &CJob::`vftable'{for `CJobInactivityTimeout'};
  *((_QWORD *)this + 12) = &CJob::`vftable'{for `CJobRetryItem'};
  *((_QWORD *)this + 24) = &CJob::`vftable'{for `CJobCallbackItem'};
  *((_QWORD *)this + 38) = &CJob::`vftable'{for `CJobNoProgressItem'};
  *((_QWORD *)this + 50) = &CJob::`vftable'{for `CJobMaxDownloadTimeItem'};
  *((_QWORD *)this + 62) = &CJob::`vftable'{for `CJobModificationItem'};
  *((_QWORD *)this + 75) = &CJob::`vftable'{for `RefCountedObject'};
  *((_QWORD *)this + 77) = &CUploadJob::`vftable'{for `IServerCertificateValidator'};
  TaskScheduler::CancelWorkItem((CJobManager *)((char *)g_Manager + 520), this);
  v2 = (CJob *)((char *)this + 304);
  if ( !this )
    v2 = 0;
  TaskScheduler::CancelWorkItem((CJobManager *)((char *)g_Manager + 520), v2);
  v3 = (CJob *)((char *)this + 96);
  if ( !this )
    v3 = 0;
  TaskScheduler::CancelWorkItem((CJobManager *)((char *)g_Manager + 520), v3);
  v4 = (CJob *)((char *)this + 400);
  if ( !this )
    v4 = 0;
  TaskScheduler::CancelWorkItem((CJobManager *)((char *)g_Manager + 520), v4);
  v5 = (CJob *)((char *)this + 192);
  if ( !this )
    v5 = 0;
  if ( !TaskScheduler::CancelWorkItem((CJobManager *)((char *)g_Manager + 520), v5) )
  {
    _InterlockedExchange((volatile __int32 *)this + 72, 0);
    CJob::ReevaluateIdleStopConditions(this);
  }
  *((_DWORD *)this + 73) = 0;
  v7 = (CJobSecurityDescriptor *)*((_QWORD *)this + 104);
  if ( v7 )
    CJobSecurityDescriptor::`scalar deleting destructor'(v7, v6);
  for ( i = (_QWORD *)*((_QWORD *)this + 106); i != *((_QWORD **)this + 107); ++i )
  {
    if ( *i )
      (**(void (__fastcall ***)(_QWORD, __int64))*i)(*i, 1);
  }
  v9 = *((_QWORD *)this + 106);
  if ( v9 != *((_QWORD *)this + 107) )
    *((_QWORD *)this + 107) = v9;
  if ( g_LastServiceControl != 1 )
  {
    if ( g_LastServiceControl == 15 )
      goto LABEL_42;
    if ( g_GlobalInfo )
      BitsESE::BitsJetDatabaseSession::GetCorruptionRegKeyValue();
  }
  v10 = *((unsigned int *)this + 192);
  if ( (_DWORD)v10 )
  {
    v41 = 0;
    v11 = (*(__int64 (__fastcall **)(LPVOID, __int64, char *, __int64 *))(*(_QWORD *)g_GIT + 40LL))(
            g_GIT,
            v10,
            (char *)this + 772,
            &v41);
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids,
        *((unsigned int *)this + 192));
    if ( v11 >= 0 )
    {
      if ( v41 )
      {
        v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids, v12);
      }
    }
    (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)g_GIT + 32LL))(g_GIT, *((unsigned int *)this + 192));
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids,
        *((unsigned int *)this + 192));
    if ( v11 >= 0 )
    {
      if ( v41 )
      {
        v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids, v13);
      }
    }
    *((_DWORD *)this + 192) = 0;
  }
LABEL_42:
  if ( g_LastServiceControl != 1 )
  {
    if ( g_LastServiceControl == 15 )
      goto LABEL_47;
    if ( g_GlobalInfo )
      BitsESE::BitsJetDatabaseSession::GetCorruptionRegKeyValue();
  }
  CJob::SetServerCertificateValidationInterface(this, 0, 1);
LABEL_47:
  v14 = (void *)*((_QWORD *)this + 153);
  if ( v14 )
  {
    CloseHandle(v14);
    *((_QWORD *)this + 153) = 0;
  }
  v15 = *((_QWORD *)this + 191);
  if ( v15 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v15 + 8), 0xFFFFFFFF) == 1 )
      operator delete(*((void **)this + 191), 0x10u);
    *((_QWORD *)this + 191) = 0;
  }
  std::_Tree<std::_Tmap_traits<ServerCertCache::ServerEndpoint,std::vector<ServerCertCache::CertHash>,std::less<ServerCertCache::ServerEndpoint>,std::allocator<std::pair<ServerCertCache::ServerEndpoint const,std::vector<ServerCertCache::CertHash>>>,0>>::~_Tree<std::_Tmap_traits<ServerCertCache::ServerEndpoint,std::vector<ServerCertCache::CertHash>,std::less<ServerCertCache::ServerEndpoint>,std::allocator<std::pair<ServerCertCache::ServerEndpoint const,std::vector<ServerCertCache::CertHash>>>,0>>((char *)this + 1512);
  if ( *((_QWORD *)this + 187) )
    std::default_delete<ScopedSmePolicyTrackingMaintainer>::operator()();
  if ( *((_QWORD *)this + 186) )
    std::default_delete<ScopedSmePolicyTrackingMaintainer>::operator()();
  if ( *((_BYTE *)this + 1440)
    && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      &WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids,
      (char *)this + 1400);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)this + 35);
  if ( *((_BYTE *)this + 1448) )
  {
    v16 = CoReleaseSharedService(*((unsigned int *)g_ComServerModule + 5));
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_b9cae9cbb65e31ab8ab5087a10ce05fe_Traceguids, v16);
    *((_BYTE *)this + 1448) = 0;
  }
  if ( *((_BYTE *)this + 1440)
    && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      &WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids,
      (char *)this + 1400);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 35);
  if ( *((_BYTE *)this + 1440)
    && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      &WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids,
      (char *)this + 1400);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 35);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 1368);
  std::vector<unsigned char>::_Tidy((char *)this + 1304);
  v18 = *((_QWORD *)this + 161);
  if ( v18 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v18 + 8), 0xFFFFFFFF) == 1 )
      operator delete(*((void **)this + 161), 0x10u);
    *((_QWORD *)this + 161) = 0;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)this + 155) + 8LL), 0xFFFFFFFF) == 1 )
  {
    v19 = (char *)**((_QWORD **)this + 155);
    if ( (unsigned __int64)(v19 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v19);
      **((_QWORD **)this + 155) = 0;
    }
    operator delete(*((void **)this + 155), 0x10u);
    *((_QWORD *)this + 155) = 0;
  }
  *((_DWORD *)this + 278) = 0;
  *((_DWORD *)this + 274) = 0;
  *((_DWORD *)this + 284) = 0;
  v20 = (void **)((char *)this + 1080);
  if ( **((_QWORD **)this + 135) )
  {
    _InterlockedIncrement(&dword_180145058);
    StringCchCopyW(&word_18014505C, 1u, (const unsigned __int16 *)*v20 + 6);
    GenericStringHandle<unsigned short>::FreeIt((char *)this + 1080);
    *v20 = &GenericStringHandle<unsigned short>::s_EmptyString;
  }
  v21 = (void **)((char *)this + 1104);
  if ( **((_QWORD **)this + 138) )
  {
    _InterlockedIncrement(&dword_180145058);
    StringCchCopyW(&word_18014505C, 1u, (const unsigned __int16 *)*v21 + 6);
    GenericStringHandle<unsigned short>::FreeIt((char *)this + 1104);
    *v21 = &GenericStringHandle<unsigned short>::s_EmptyString;
  }
  v22 = (void *)*((_QWORD *)this + 136);
  if ( v22 )
  {
    if ( !HeapFree(hBitsHeap, 0, *((LPVOID *)this + 136))
      && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        &WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids,
        v22,
        LastError);
    }
    v22 = 0;
    *((_QWORD *)this + 136) = 0;
  }
  v24 = (const CERT_CONTEXT *)*((_QWORD *)this + 140);
  if ( v24 )
    CertFreeCertificateContext(v24);
  v25 = (void *)*((_QWORD *)this + 141);
  if ( v25 )
    CertCloseStore(v25, 0);
  *((_QWORD *)this + 140) = v22;
  *((_QWORD *)this + 141) = v22;
  v26 = *((_QWORD *)this + 146);
  if ( v26 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v26 + 8), 0xFFFFFFFF) == 1 )
      operator delete(*((void **)this + 146), 0x10u);
    *((_QWORD *)this + 146) = v22;
  }
  v27 = *((_QWORD *)this + 143);
  if ( v27 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v27 + 8), 0xFFFFFFFF) == 1 )
      operator delete(*((void **)this + 143), 0x10u);
    *((_QWORD *)this + 143) = v22;
  }
  if ( *v21 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)*v21 + 2, 0xFFFFFFFF) == 1 )
      operator delete(*v21, 0x10u);
    *v21 = v22;
  }
  if ( *v20 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)*v20 + 2, 0xFFFFFFFF) == 1 )
      operator delete(*v20, 0x10u);
    *v20 = v22;
  }
  v28 = (CEncryptedBlob *)*((_QWORD *)this + 133);
  if ( v28 )
  {
    CEncryptedBlob::`scalar deleting destructor'(v28, v17);
    *((_QWORD *)this + 133) = v22;
  }
  while ( 1 )
  {
    v29 = *((_QWORD *)this + 129);
    v30 = (char *)this + 1032;
    if ( *(_QWORD *)v29 == v29 )
      break;
    v31 = *(CEncryptedCredentials **)(*(_QWORD *)v29 + 40LL);
    v32 = (void *)std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,CEncryptedCredentials *>>>::_Extract(v30);
    operator delete(v32, 0x30u);
    if ( v31 )
      CEncryptedCredentials::`scalar deleting destructor'(v31, v33);
  }
  std::_Tree<std::_Tmap_traits<unsigned long,CEncryptedCredentials *,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CEncryptedCredentials *>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,CEncryptedCredentials *,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CEncryptedCredentials *>>,0>>(v30);
  operator delete(*((void **)this + 127), 2u);
  operator delete(*((void **)this + 128), 2u);
  v34 = *((_QWORD *)this + 106);
  if ( v34 )
  {
    std::_Deallocate<16>(v34, (*((_QWORD *)this + 108) - v34) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 106) = v22;
    *((_QWORD *)this + 107) = v22;
    *((_QWORD *)this + 108) = v22;
  }
  v35 = *((_QWORD *)this + 102);
  if ( v35 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v35 + 8), 0xFFFFFFFF) == 1 )
      operator delete(*((void **)this + 102), 0x10u);
    *((_QWORD *)this + 102) = v22;
  }
  v36 = *((_QWORD *)this + 101);
  if ( v36 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v36 + 8), 0xFFFFFFFF) == 1 )
      operator delete(*((void **)this + 101), 0x10u);
    *((_QWORD *)this + 101) = v22;
  }
  v37 = *((_QWORD *)this + 92);
  if ( v37 )
    std::default_delete<AppPackageInfo>::operator()(v36, v37);
  v38 = *((_QWORD *)this + 91);
  if ( v38 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v38 + 8), 0xFFFFFFFF) == 1 )
      operator delete(*((void **)this + 91), 0x10u);
    *((_QWORD *)this + 91) = v22;
  }
  if ( _InterlockedExchangeAdd(*((volatile signed __int32 **)this + 90), 0xFFFFFFFF) == 1 )
  {
    operator delete(*((void **)this + 90), 4u);
    operator delete(*((void **)this + 89), 0);
    *((_QWORD *)this + 90) = v22;
    *((_QWORD *)this + 89) = v22;
  }
  v39 = *((_QWORD *)this + 88);
  if ( v39 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v39 + 8), 0xFFFFFFFF) == 1 )
      operator delete(*((void **)this + 88), 0x10u);
    *((_QWORD *)this + 88) = v22;
  }
  v40 = *((_QWORD *)this + 87);
  if ( v40 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v40 + 8), 0xFFFFFFFF) == 1 )
      operator delete(*((void **)this + 87), 0x10u);
    *((_QWORD *)this + 87) = v22;
  }
  *((_QWORD *)this + 75) = &RefCountedObject::`vftable';
  *((_QWORD *)this + 62) = &TaskSchedulerWorkItem::`vftable';
  *((_QWORD *)this + 50) = &TaskSchedulerWorkItem::`vftable';
  *((_QWORD *)this + 38) = &TaskSchedulerWorkItem::`vftable';
  *((_QWORD *)this + 24) = &TaskSchedulerWorkItem::`vftable';
  *((_QWORD *)this + 12) = &TaskSchedulerWorkItem::`vftable';
  *(_QWORD *)this = &TaskSchedulerWorkItem::`vftable';
}

```

## disassembly

```asm
0x18002b5a0  push    rbx
0x18002b5a2  push    rbp
0x18002b5a3  push    rsi
0x18002b5a4  push    rdi
0x18002b5a5  push    r12
0x18002b5a7  push    r13
0x18002b5a9  push    r14
0x18002b5ab  push    r15
0x18002b5ad  sub     rsp, 38h
0x18002b5b1  mov     rsi, rcx
0x18002b5b4  lea     rax, ??_7CJob@@6BCJobInactivityTimeout@@@; const CJob::`vftable'{for `CJobInactivityTimeout'}
0x18002b5bb  mov     [rcx], rax
0x18002b5be  lea     rax, ??_7CJob@@6BCJobRetryItem@@@; const CJob::`vftable'{for `CJobRetryItem'}
0x18002b5c5  mov     [rcx+60h], rax
0x18002b5c9  lea     rax, ??_7CJob@@6BCJobCallbackItem@@@; const CJob::`vftable'{for `CJobCallbackItem'}
0x18002b5d0  mov     [rcx+0C0h], rax
0x18002b5d7  lea     rax, ??_7CJob@@6BCJobNoProgressItem@@@; const CJob::`vftable'{for `CJobNoProgressItem'}
0x18002b5de  mov     [rcx+130h], rax
0x18002b5e5  lea     rax, ??_7CJob@@6BCJobMaxDownloadTimeItem@@@; const CJob::`vftable'{for `CJobMaxDownloadTimeItem'}
0x18002b5ec  mov     [rcx+190h], rax
0x18002b5f3  lea     rax, ??_7CJob@@6BCJobModificationItem@@@; const CJob::`vftable'{for `CJobModificationItem'}
0x18002b5fa  mov     [rcx+1F0h], rax
0x18002b601  lea     rax, ??_7CJob@@6BRefCountedObject@@@; const CJob::`vftable'{for `RefCountedObject'}
0x18002b608  mov     [rcx+258h], rax
0x18002b60f  lea     rax, ??_7CUploadJob@@6BIServerCertificateValidator@@@; const CUploadJob::`vftable'{for `IServerCertificateValidator'}
0x18002b616  mov     [rcx+268h], rax
0x18002b61d  mov     rcx, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x18002b624  add     rcx, 208h; this
0x18002b62b  mov     rdx, rsi; struct TaskSchedulerWorkItem *
0x18002b62e  call    ?CancelWorkItem@TaskScheduler@@QEAA_NPEAVTaskSchedulerWorkItem@@@Z; TaskScheduler::CancelWorkItem(TaskSchedulerWorkItem *)
0x18002b633  lea     rdx, [rsi+130h]
0x18002b63a  xor     ebp, ebp
0x18002b63c  test    rsi, rsi
0x18002b63f  cmovz   rdx, rbp; struct TaskSchedulerWorkItem *
0x18002b643  mov     rcx, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x18002b64a  add     rcx, 208h; this
0x18002b651  call    ?CancelWorkItem@TaskScheduler@@QEAA_NPEAVTaskSchedulerWorkItem@@@Z; TaskScheduler::CancelWorkItem(TaskSchedulerWorkItem *)
0x18002b656  lea     rdx, [rsi+60h]
0x18002b65a  test    rsi, rsi
0x18002b65d  cmovz   rdx, rbp; struct TaskSchedulerWorkItem *
0x18002b661  mov     rcx, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x18002b668  add     rcx, 208h; this
0x18002b66f  call    ?CancelWorkItem@TaskScheduler@@QEAA_NPEAVTaskSchedulerWorkItem@@@Z; TaskScheduler::CancelWorkItem(TaskSchedulerWorkItem *)
0x18002b674  lea     rdx, [rsi+190h]
0x18002b67b  test    rsi, rsi
0x18002b67e  cmovz   rdx, rbp; struct TaskSchedulerWorkItem *
0x18002b682  mov     rcx, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x18002b689  add     rcx, 208h; this
0x18002b690  call    ?CancelWorkItem@TaskScheduler@@QEAA_NPEAVTaskSchedulerWorkItem@@@Z; TaskScheduler::CancelWorkItem(TaskSchedulerWorkItem *)
0x18002b695  lea     rdx, [rsi+0C0h]
0x18002b69c  test    rsi, rsi
0x18002b69f  cmovz   rdx, rbp; struct TaskSchedulerWorkItem *
0x18002b6a3  mov     rcx, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x18002b6aa  add     rcx, 208h; this
0x18002b6b1  call    ?CancelWorkItem@TaskScheduler@@QEAA_NPEAVTaskSchedulerWorkItem@@@Z; TaskScheduler::CancelWorkItem(TaskSchedulerWorkItem *)
0x18002b6b6  test    al, al
0x18002b6b8  jnz     short loc_18002B6CA
0x18002b6ba  mov     eax, ebp
0x18002b6bc  xchg    eax, [rsi+120h]
0x18002b6c2  mov     rcx, rsi; this
0x18002b6c5  call    ?ReevaluateIdleStopConditions@CJob@@AEAAXXZ; CJob::ReevaluateIdleStopConditions(void)
0x18002b6ca  mov     [rsi+124h], ebp
0x18002b6d0  mov     rcx, [rsi+340h]; this
0x18002b6d7  test    rcx, rcx
0x18002b6da  jz      short loc_18002B6E1
0x18002b6dc  call    ??_GCJobSecurityDescriptor@@QEAAPEAXI@Z; CJobSecurityDescriptor::`scalar deleting destructor'(uint)
0x18002b6e1  mov     rbx, [rsi+350h]
0x18002b6e8  cmp     rbx, [rsi+358h]
0x18002b6ef  jz      short loc_18002B70F
0x18002b6f1  mov     rcx, [rbx]
0x18002b6f4  test    rcx, rcx
0x18002b6f7  jz      short loc_18002B709
0x18002b6f9  mov     rax, [rcx]
0x18002b6fc  mov     edx, 1
0x18002b701  mov     rax, [rax]
0x18002b704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b709  add     rbx, 8
0x18002b70d  jmp     short loc_18002B6E8
0x18002b70f  mov     rax, [rsi+350h]
0x18002b716  cmp     rax, [rsi+358h]
0x18002b71d  jz      short loc_18002B726
0x18002b71f  mov     [rsi+358h], rax
0x18002b726  mov     eax, cs:?g_LastServiceControl@@3KA; ulong g_LastServiceControl
0x18002b72c  lea     rdi, WPP_GLOBAL_Control
0x18002b733  sub     eax, 1
0x18002b736  jz      short loc_18002B74F
0x18002b738  cmp     eax, 0Eh
0x18002b73b  jz      loc_18002B892
0x18002b741  cmp     cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA, rbp; GlobalInfo * g_GlobalInfo
0x18002b748  jz      short loc_18002B74F
0x18002b74a  call    ?GetCorruptionRegKeyValue@BitsJetDatabaseSession@BitsESE@@SA_NXZ; BitsESE::BitsJetDatabaseSession::GetCorruptionRegKeyValue(void)
0x18002b74f  mov     edx, [rsi+300h]
0x18002b755  test    edx, edx
0x18002b757  jz      loc_18002B892
0x18002b75d  mov     [rsp+78h+arg_0], rbp
0x18002b765  mov     rcx, cs:?g_GIT@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_GIT
0x18002b76c  mov     rax, [rcx]
0x18002b76f  lea     r8, [rsi+304h]
0x18002b776  lea     r9, [rsp+78h+arg_0]
0x18002b77e  mov     rax, [rax+28h]
0x18002b782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b787  mov     ebx, eax
0x18002b789  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b790  cmp     rcx, rdi
0x18002b793  jz      short loc_18002B7B7
0x18002b795  test    byte ptr [rcx+1Ch], 1
0x18002b799  jz      short loc_18002B7B7
0x18002b79b  mov     edx, 1Fh
0x18002b7a0  mov     r9d, [rsi+300h]
0x18002b7a7  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x18002b7ae  mov     rcx, [rcx+10h]
0x18002b7b2  call    WPP_SF_d
0x18002b7b7  test    ebx, ebx
0x18002b7b9  js      short loc_18002B7FE
0x18002b7bb  mov     rcx, [rsp+78h+arg_0]
0x18002b7c3  test    rcx, rcx
0x18002b7c6  jz      short loc_18002B7FE
0x18002b7c8  mov     rax, [rcx]
0x18002b7cb  mov     rax, [rax+10h]
0x18002b7cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b7db  cmp     rcx, rdi
0x18002b7de  jz      short loc_18002B7FE
0x18002b7e0  test    byte ptr [rcx+1Ch], 1
0x18002b7e4  jz      short loc_18002B7FE
0x18002b7e6  mov     edx, 20h ; ' '
0x18002b7eb  mov     r9d, eax
0x18002b7ee  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x18002b7f5  mov     rcx, [rcx+10h]
0x18002b7f9  call    WPP_SF_d
0x18002b7fe  mov     rcx, cs:?g_GIT@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_GIT
0x18002b805  mov     rax, [rcx]
0x18002b808  mov     edx, [rsi+300h]
0x18002b80e  mov     rax, [rax+20h]
0x18002b812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b817  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b81e  cmp     rcx, rdi
0x18002b821  jz      short loc_18002B845
0x18002b823  test    byte ptr [rcx+1Ch], 1
0x18002b827  jz      short loc_18002B845
0x18002b829  mov     edx, 21h ; '!'
0x18002b82e  mov     r9d, [rsi+300h]
0x18002b835  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x18002b83c  mov     rcx, [rcx+10h]
0x18002b840  call    WPP_SF_d
0x18002b845  test    ebx, ebx
0x18002b847  js      short loc_18002B88C
0x18002b849  mov     rcx, [rsp+78h+arg_0]
0x18002b851  test    rcx, rcx
0x18002b854  jz      short loc_18002B88C
0x18002b856  mov     rax, [rcx]
0x18002b859  mov     rax, [rax+10h]
0x18002b85d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b862  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b869  cmp     rcx, rdi
0x18002b86c  jz      short loc_18002B88C
0x18002b86e  test    byte ptr [rcx+1Ch], 1
0x18002b872  jz      short loc_18002B88C
0x18002b874  mov     edx, 22h ; '"'
0x18002b879  mov     r9d, eax
0x18002b87c  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x18002b883  mov     rcx, [rcx+10h]
0x18002b887  call    WPP_SF_d
0x18002b88c  mov     [rsi+300h], ebp
0x18002b892  mov     eax, cs:?g_LastServiceControl@@3KA; ulong g_LastServiceControl
0x18002b898  sub     eax, 1
0x18002b89b  jz      short loc_18002B8B0
0x18002b89d  cmp     eax, 0Eh
0x18002b8a0  jz      short loc_18002B8BD
0x18002b8a2  cmp     cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA, rbp; GlobalInfo * g_GlobalInfo
0x18002b8a9  jz      short loc_18002B8B0
0x18002b8ab  call    ?GetCorruptionRegKeyValue@BitsJetDatabaseSession@BitsESE@@SA_NXZ; BitsESE::BitsJetDatabaseSession::GetCorruptionRegKeyValue(void)
0x18002b8b0  mov     r8b, 1; bool
0x18002b8b3  xor     edx, edx; struct IBackgroundCopyServerCertificateValidationCallback *
0x18002b8b5  mov     rcx, rsi; this
0x18002b8b8  call    ?SetServerCertificateValidationInterface@CJob@@QEAAJPEAUIBackgroundCopyServerCertificateValidationCallback@@_N@Z; CJob::SetServerCertificateValidationInterface(IBackgroundCopyServerCertificateValidationCallback *,bool)
0x18002b8bd  mov     rcx, [rsi+4C8h]; hObject
0x18002b8c4  test    rcx, rcx
0x18002b8c7  jz      short loc_18002B8D6
0x18002b8c9  call    cs:__imp_CloseHandle
0x18002b8cf  mov     [rsi+4C8h], rbp
0x18002b8d6  mov     rcx, [rsi+5F8h]
0x18002b8dd  mov     r14d, 0FFFFFFFFh
0x18002b8e3  test    rcx, rcx
0x18002b8e6  jz      short loc_18002B90D
0x18002b8e8  mov     eax, r14d
0x18002b8eb  lock xadd [rcx+8], eax
0x18002b8f0  cmp     eax, 1
0x18002b8f3  jnz     short loc_18002B906
0x18002b8f5  mov     edx, 10h; unsigned __int64
0x18002b8fa  mov     rcx, [rsi+5F8h]; void *
0x18002b901  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002b906  mov     [rsi+5F8h], rbp
0x18002b90d  lea     rcx, [rsi+5E8h]
0x18002b914  call    ??1?$_Tree@V?$_Tmap_traits@VServerEndpoint@ServerCertCache@@V?$vector@VCertHash@ServerCertCache@@V?$allocator@VCertHash@ServerCertCache@@@std@@@std@@U?$less@VServerEndpoint@ServerCertCache@@@4@V?$allocator@U?$pair@$$CBVServerEndpoint@ServerCertCache@@V?$vector@VCertHash@ServerCertCache@@V?$allocator@VCertHash@ServerCertCache@@@std@@@std@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ServerCertCache::ServerEndpoint,std::vector<ServerCertCache::CertHash>,std::less<ServerCertCache::ServerEndpoint>,std::allocator<std::pair<ServerCertCache::ServerEndpoint const,std::vector<ServerCertCache::CertHash>>>,0>>::~_Tree<std::_Tmap_traits<ServerCertCache::ServerEndpoint,std::vector<ServerCertCache::CertHash>,std::less<ServerCertCache::ServerEndpoint>,std::allocator<std::pair<ServerCertCache::ServerEndpoint const,std::vector<ServerCertCache::CertHash>>>,0>>(void)
0x18002b919  mov     rdx, [rsi+5D8h]
0x18002b920  test    rdx, rdx
0x18002b923  jz      short loc_18002B92A
0x18002b925  call    ??R?$default_delete@VScopedSmePolicyTrackingMaintainer@@@std@@QEBAXPEAVScopedSmePolicyTrackingMaintainer@@@Z; std::default_delete<ScopedSmePolicyTrackingMaintainer>::operator()(ScopedSmePolicyTrackingMaintainer *)
0x18002b92a  mov     rdx, [rsi+5D0h]
0x18002b931  test    rdx, rdx
0x18002b934  jz      short loc_18002B93B
0x18002b936  call    ??R?$default_delete@VScopedSmePolicyTrackingMaintainer@@@std@@QEBAXPEAVScopedSmePolicyTrackingMaintainer@@@Z; std::default_delete<ScopedSmePolicyTrackingMaintainer>::operator()(ScopedSmePolicyTrackingMaintainer *)
0x18002b93b  lea     rbx, [rsi+578h]
0x18002b942  cmp     [rbx+28h], bpl
0x18002b946  jz      short loc_18002B975
0x18002b948  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b94f  cmp     rcx, rdi
0x18002b952  jz      short loc_18002B975
0x18002b954  test    dword ptr [rcx+1Ch], 100h
0x18002b95b  jz      short loc_18002B975
0x18002b95d  mov     edx, 0Fh
0x18002b962  mov     r9, rbx
0x18002b965  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x18002b96c  mov     rcx, [rcx+10h]
0x18002b970  call    WPP_SF_q
0x18002b975  mov     rcx, rbx; lpCriticalSection
0x18002b978  call    cs:__imp_EnterCriticalSection
0x18002b97e  cmp     [rbx+30h], bpl
0x18002b982  jz      short loc_18002B9C2
0x18002b984  mov     rcx, cs:?g_ComServerModule@@3PEAVBitsComModule@@EA; BitsComModule * g_ComServerModule
0x18002b98b  mov     ecx, [rcx+14h]
0x18002b98e  call    cs:__imp_CoReleaseSharedService
0x18002b994  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b99b  cmp     rcx, rdi
0x18002b99e  jz      short loc_18002B9BE
0x18002b9a0  test    byte ptr [rcx+1Ch], 1
0x18002b9a4  jz      short loc_18002B9BE
0x18002b9a6  mov     edx, 0Bh
0x18002b9ab  mov     r9d, eax
0x18002b9ae  lea     r8, WPP_b9cae9cbb65e31ab8ab5087a10ce05fe_Traceguids
0x18002b9b5  mov     rcx, [rcx+10h]
0x18002b9b9  call    WPP_SF_d
0x18002b9be  mov     [rbx+30h], bpl
0x18002b9c2  cmp     [rbx+28h], bpl
0x18002b9c6  jz      short loc_18002B9F5
0x18002b9c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b9cf  cmp     rcx, rdi
0x18002b9d2  jz      short loc_18002B9F5
0x18002b9d4  test    dword ptr [rcx+1Ch], 100h
0x18002b9db  jz      short loc_18002B9F5
0x18002b9dd  mov     edx, 10h
0x18002b9e2  mov     r9, rbx
0x18002b9e5  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x18002b9ec  mov     rcx, [rcx+10h]
0x18002b9f0  call    WPP_SF_q
0x18002b9f5  mov     rcx, rbx; lpCriticalSection
0x18002b9f8  call    cs:__imp_LeaveCriticalSection
0x18002b9fe  cmp     [rbx+28h], bpl
0x18002ba02  jz      short loc_18002BA31
0x18002ba04  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ba0b  cmp     rcx, rdi
0x18002ba0e  jz      short loc_18002BA31
0x18002ba10  test    dword ptr [rcx+1Ch], 100h
0x18002ba17  jz      short loc_18002BA31
0x18002ba19  mov     edx, 0Eh
0x18002ba1e  mov     r9, rbx
0x18002ba21  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x18002ba28  mov     rcx, [rcx+10h]
0x18002ba2c  call    WPP_SF_q
0x18002ba31  mov     rcx, rbx; lpCriticalSection
0x18002ba34  call    cs:__imp_DeleteCriticalSection
0x18002ba3a  lea     rcx, [rsi+558h]
0x18002ba41  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ba46  lea     rcx, [rsi+518h]
0x18002ba4d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18002ba52  mov     rcx, [rsi+508h]
0x18002ba59  test    rcx, rcx
0x18002ba5c  jz      short loc_18002BA83
0x18002ba5e  mov     eax, r14d
0x18002ba61  lock xadd [rcx+8], eax
0x18002ba66  cmp     eax, 1
0x18002ba69  jnz     short loc_18002BA7C
0x18002ba6b  mov     edx, 10h; unsigned __int64
0x18002ba70  mov     rcx, [rsi+508h]; void *
0x18002ba77  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002ba7c  mov     [rsi+508h], rbp
0x18002ba83  mov     rcx, [rsi+4D8h]
0x18002ba8a  mov     eax, r14d
0x18002ba8d  lock xadd [rcx+8], eax
0x18002ba92  cmp     eax, 1
0x18002ba95  jnz     short loc_18002BAD3
0x18002ba97  mov     rax, [rsi+4D8h]
0x18002ba9e  mov     rcx, [rax]; hObject
0x18002baa1  lea     rax, [rcx-1]
0x18002baa5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002baa9  ja      short loc_18002BABB
0x18002baab  call    cs:__imp_CloseHandle
0x18002bab1  mov     rax, [rsi+4D8h]
0x18002bab8  mov     [rax], rbp
0x18002babb  mov     edx, 10h; unsigned __int64
0x18002bac0  mov     rcx, [rsi+4D8h]; void *
0x18002bac7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002bacc  mov     [rsi+4D8h], rbp
0x18002bad3  mov     [rsi+458h], ebp
0x18002bad9  mov     [rsi+448h], ebp
0x18002badf  mov     [rsi+470h], ebp
0x18002bae5  lea     rdi, [rsi+438h]
0x18002baec  mov     rax, [rdi]
0x18002baef  lea     rbp, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; GenericStringHandle<ushort>::StringData GenericStringHandle<ushort>::s_EmptyString
  ... truncated ...
```
