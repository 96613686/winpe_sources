# CJobManager::Startup(void)

- ea: `0x180047114`
- end: `0x18004769d`
- name: `?Startup@CJobManager@@QEAAXXZ`
- size: `1417`
- prototype: `void __fastcall(CJobManager *__hidden this)`
- caller_count: `1`
- callee_count: `29`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180045ea0`

## callees

- `0x180006640`
- `0x18000b4d0`
- `0x180034760`
- `0x180046de8`
- `0x180047114`
- `0x1800476a4`
- `0x180047834`
- `0x180047abc`
- `0x180047cfc`
- `0x180047dec`
- `0x1800480d8`
- `0x1800482f0`
- `0x180048804`
- `0x1800489f4`
- `0x18006532c`
- `0x180068424`
- `0x1800736e0`
- `0x180090820`
- `0x180091acc`
- `0x180091afc`
- `0x180091b20`
- `0x1800950e4`
- `0x18009764c`
- `0x180099120`
- `0x180099e4c`
- `0x18009bb50`
- `0x1800ac434`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004714b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004714b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180047283`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180047283`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180047210`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180047210`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180047353`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800473e4`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180047353`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800473e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CJobManager::Startup(CJobManager *this)
{
  CJobManager *v1; // rsi
  TaskScheduler *v2; // r13
  int v3; // r12d
  HRESULT Instance; // eax
  _QWORD *v5; // rbx
  _QWORD *v6; // r14
  _QWORD *v7; // rdi
  unsigned __int64 v8; // rcx
  _DWORD *v9; // r15
  unsigned __int64 v10; // rcx
  __int64 *v11; // rbx
  __int64 inserted; // rcx
  __int64 v13; // rax
  int v14; // r9d
  __int64 v15; // rax
  __int64 v16; // rbx
  _QWORD *v17; // rdx
  _QWORD *v18; // rdx
  int v19; // eax
  int active; // eax
  __int64 i; // rbx
  int BackupWriterIfAvailable; // eax
  __int128 v23; // [rsp+30h] [rbp-D0h] BYREF
  void **pExceptionObject; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+68h] [rbp-98h]
  int v27; // [rsp+6Ch] [rbp-94h]
  int v28; // [rsp+70h] [rbp-90h]
  __int128 v29; // [rsp+B0h] [rbp-50h]
  char *v30; // [rsp+C0h] [rbp-40h] BYREF
  int v31; // [rsp+C8h] [rbp-38h]
  _QWORD *v32; // [rsp+D0h] [rbp-30h]
  _BYTE v33[16]; // [rsp+D8h] [rbp-28h] BYREF
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+E8h] [rbp-18h] BYREF
  CJobManager *v35; // [rsp+170h] [rbp+70h] BYREF
  LPVOID Context; // [rsp+178h] [rbp+78h] BYREF
  CJobManager **v37; // [rsp+180h] [rbp+80h] BYREF
  __int64 *v38; // [rsp+188h] [rbp+88h]

  v35 = this;
  v1 = g_Manager;
  v2 = (CJobManager *)((char *)g_Manager + 520);
  v30 = (char *)g_Manager + 520;
  v3 = 0;
  v31 = 0;
  if ( *((_DWORD *)v2 + 14) != GetCurrentThreadId() )
  {
    v3 = 1;
    v31 = 1;
    TaskScheduler::LockWriter(v2, 0);
  }
  ServiceRefHolder::ServiceRefHolder(&CriticalSection);
  CJobManager::BareServiceStartupChange(2u);
  if ( *((_BYTE *)g_GlobalInfo + 248) )
  {
    ServiceRefHolder::~ServiceRefHolder((ServiceRefHolder *)&CriticalSection);
    HoldWriterLock::~HoldWriterLock((HoldWriterLock *)&v30);
  }
  else
  {
    CBandwidthProfileMgr::LoadBandwidthProfiles((CJobManager *)((char *)v1 + 1552));
    PolicyMonitor::LoadJobInactivityTimeout((LPCRITICAL_SECTION)((char *)v1 + 1144));
    CThreadPoolConnector::SetupThreadPoolEnv((CJobManager *)((char *)v1 + 992));
    if ( *((_QWORD *)v1 + 208) )
    {
      ReportServiceStartupPhase(4);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v1 + 208) + 32LL))(*((_QWORD *)v1 + 208));
    }
    Instance = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &IID_IGlobalInterfaceTable, &g_GIT);
    if ( Instance < 0 )
    {
      v25 = 0;
      pExceptionObject = &ComError::`vftable';
      v26 = Instance;
      v27 = 823;
      v28 = 1;
      throw (ComError *)&pExceptionObject;
    }
    ReportServiceStartupPhase(7);
    CJobManager::UnserializeAndMigrateLegacyState(v1);
    CJobManager::UnserializeDatabaseState(v1);
    Context = 0;
    if ( !InitOnceExecuteOnce(
            &g_GlobalNotificationRegistrar,
            LazyGlobal<NotificationRegistrar>::LazyGlobalInitializer,
            0,
            &Context) )
    {
      v25 = 0;
      pExceptionObject = &ComError::`vftable';
      v26 = -2147024882;
      v27 = 51;
      v28 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v5 = Context;
    v6 = operator new(0x20u);
    if ( v6 )
      *v6 = &details::ClassMethodCallbackContext<CJobManager>::`vftable';
    else
      v6 = 0;
    v32 = v6;
    v6[1] = v1;
    *(_QWORD *)&v29 = CJobManager::OnBackgroundAccessChange;
    DWORD2(v29) = 0;
    HIDWORD(v29) = HIDWORD(v23);
    *((_OWORD *)v6 + 1) = v29;
    v7 = v5 + 3;
    v8 = ((__int64)(v5[4] - v5[3]) >> 3) + 1;
    v35 = (CJobManager *)v8;
    if ( v8 > (__int64)(v5[5] - v5[3]) >> 3 )
    {
      if ( v8 > 0x1FFFFFFFFFFFFFFFLL )
        std::_Xlength_error("vector too long");
      std::vector<details::DeletableContextBase *>::_Reallocate<0>(v5 + 3, &v35);
    }
    LODWORD(v35) = 14;
    v9 = operator new(0x20u);
    if ( v9 )
      *(_QWORD *)v9 = &details::ClassMethodCallbackContext<CJobManager>::`vftable';
    else
      v9 = 0;
    *(_QWORD *)&v29 = v9;
    v9[2] = (_DWORD)v35;
    *((_QWORD *)v9 + 2) = details::ConvertFreeCallbackToClassMethodCallback<CJobManager>;
    *((_QWORD *)v9 + 3) = v6;
    v10 = ((__int64)(v5[4] - v5[3]) >> 3) + 1;
    v37 = (CJobManager **)v10;
    if ( v10 > (__int64)(v5[5] - v5[3]) >> 3 )
    {
      if ( v10 > 0x1FFFFFFFFFFFFFFFLL )
        std::_Xlength_error("vector too long");
      std::vector<details::DeletableContextBase *>::_Reallocate<0>(v5 + 3, &v37);
    }
    v11 = v5 + 1;
    v38 = v11;
    inserted = *v11;
    v13 = *(_QWORD *)(*v11 + 8);
    v23 = (unsigned __int64)v13;
    while ( !*(_BYTE *)(v13 + 25) )
    {
      *(_QWORD *)&v23 = v13;
      if ( *(_DWORD *)(v13 + 32) >= (unsigned int)v35 )
      {
        DWORD2(v23) = 1;
        inserted = v13;
      }
      else
      {
        DWORD2(v23) = 0;
        v13 += 16;
      }
      v13 = *(_QWORD *)v13;
    }
    if ( *(_BYTE *)(inserted + 25) || (unsigned int)v35 < *(_DWORD *)(inserted + 32) )
    {
      std::_Tree<std::_Tmap_traits<enum NotifiableSystemEvent,ITriggerableNotifier *,std::less<enum NotifiableSystemEvent>,std::allocator<std::pair<enum NotifiableSystemEvent const,ITriggerableNotifier *>>,0>>::_Check_grow_by_1(v11);
      v37 = &v35;
      v15 = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<enum RegistryKeyType const,IRegistryKeyTypeInfo *>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<enum RegistryKeyType const,IRegistryKeyTypeInfo *>,void *>>>(
              (unsigned int)v33,
              (_DWORD)v11,
              *v11,
              v14,
              (__int64)&v37);
      v16 = *(_QWORD *)(v15 + 8);
      *(_QWORD *)(v15 + 8) = 0;
      std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<enum _CRM_CLIENT_ID const,void *>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<enum _CRM_CLIENT_ID const,void *>,void *>>>(v33);
      inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<enum NotifiableSystemEvent const,ITriggerableNotifier *>>>::_Insert_node(
                   v38,
                   &v23,
                   v16);
    }
    (*(void (__fastcall **)(_QWORD, _QWORD, _DWORD *))(**(_QWORD **)(inserted + 40) + 8LL))(
      *(_QWORD *)(inserted + 40),
      EventLoggingCallbackWrapper,
      v9);
    v37 = (CJobManager **)v9;
    v17 = (_QWORD *)v7[1];
    if ( v17 == (_QWORD *)v7[2] )
    {
      std::vector<ServiceAccountUserSession *>::_Emplace_reallocate<ServiceAccountUserSession * const &>(v7, v17, &v37);
    }
    else
    {
      *v17 = v9;
      v7[1] += 8LL;
    }
    v35 = (CJobManager *)v6;
    v18 = (_QWORD *)v7[1];
    if ( v18 == (_QWORD *)v7[2] )
    {
      std::vector<ServiceAccountUserSession *>::_Emplace_reallocate<ServiceAccountUserSession * const &>(v7, v18, &v35);
    }
    else
    {
      *v18 = v6;
      v7[1] += 8LL;
    }
    v19 = CLoggedOnUsers::AddServiceAccounts((CJobManager *)((char *)v1 + 784));
    if ( v19 < 0 )
    {
      v25 = 0;
      pExceptionObject = &ComError::`vftable';
      v26 = v19;
      v27 = 841;
      v28 = 1;
      throw (ComError *)&pExceptionObject;
    }
    ReportServiceStartupPhase(9);
    active = CLoggedOnUsers::AddActiveUserManagerUsers((CJobManager *)((char *)v1 + 784));
    if ( active < 0 )
    {
      v25 = 0;
      pExceptionObject = &ComError::`vftable';
      v26 = active;
      v27 = 843;
      v28 = 1;
      throw (ComError *)&pExceptionObject;
    }
    CLoggedOnUsers::Dump((CJobManager *)((char *)v1 + 784));
    for ( i = 1; i != 4; ++i )
      CBandwidthChangeWorkItem::StartTimer(*(CBandwidthChangeWorkItem **)(*((_QWORD *)v1 + 203) + 8 * i));
    (*(void (__fastcall **)(CJobManager *))(*(_QWORD *)v1 + 32LL))(v1);
    (*(void (__fastcall **)(CJobManager *))(*(_QWORD *)v1 + 48LL))(v1);
    (*(void (__fastcall **)(CJobManager *))(*(_QWORD *)v1 + 56LL))(v1);
    CLoggedOnUsers::AddActiveRemotePowerShellSessions((CJobManager *)((char *)v1 + 784));
    BackupWriterIfAvailable = CJobManager::CreateBackupWriterIfAvailable(v1);
    if ( BackupWriterIfAvailable < 0 )
    {
      v25 = 0;
      pExceptionObject = &ComError::`vftable';
      v26 = BackupWriterIfAvailable;
      v27 = 869;
      v28 = 1;
      throw (ComError *)&pExceptionObject;
    }
    CJobManager::StartTrackingSmePolicies(v1);
    ServiceRefHolder::~ServiceRefHolder((ServiceRefHolder *)&CriticalSection);
    for ( ; v3; --v3 )
      TaskScheduler::UnlockWriter(v2);
  }
}

```

## disassembly

```asm
0x180047114  mov     [rsp-8+arg_0], rcx
0x180047119  push    rbp
0x18004711a  push    rbx
0x18004711b  push    rsi
0x18004711c  push    rdi
0x18004711d  push    r12
0x18004711f  push    r13
0x180047121  push    r14
0x180047123  push    r15
0x180047125  lea     rbp, [rsp-28h]
0x18004712a  sub     rsp, 128h
0x180047131  mov     rsi, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x180047138  lea     r13, [rsi+208h]
0x18004713f  mov     [rbp+60h+var_A0], r13
0x180047143  xor     edi, edi
0x180047145  mov     r12d, edi
0x180047148  mov     [rbp+60h+var_98], edi
0x18004714b  call    cs:__imp_GetCurrentThreadId
0x180047151  lea     ebx, [rdi+1]
0x180047154  cmp     [r13+38h], eax
0x180047158  jz      short loc_18004716B
0x18004715a  mov     r12d, ebx
0x18004715d  mov     [rbp+60h+var_98], ebx
0x180047160  xor     edx, edx; void *
0x180047162  mov     rcx, r13; this
0x180047165  call    ?LockWriter@TaskScheduler@@QEAA_NPEAX@Z; TaskScheduler::LockWriter(void *)
0x18004716a  nop
0x18004716b  lea     rcx, [rbp+60h+CriticalSection]; lpCriticalSection
0x18004716f  call    ??0ServiceRefHolder@@QEAA@XZ; ServiceRefHolder::ServiceRefHolder(void)
0x180047174  nop
0x180047175  mov     ecx, 2
0x18004717a  call    ?BareServiceStartupChange@CJobManager@@SA_NW4ServiceStartupType@@@Z; CJobManager::BareServiceStartupChange(ServiceStartupType)
0x18004717f  mov     rax, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x180047186  cmp     [rax+0F8h], dil
0x18004718d  jz      short loc_1800471A7
0x18004718f  lea     rcx, [rbp+60h+CriticalSection]; this
0x180047193  call    ??1ServiceRefHolder@@QEAA@XZ; ServiceRefHolder::~ServiceRefHolder(void)
0x180047198  nop
0x180047199  lea     rcx, [rbp+60h+var_A0]; this
0x18004719d  call    ??1HoldWriterLock@@QEAA@XZ; HoldWriterLock::~HoldWriterLock(void)
0x1800471a2  jmp     loc_180047689
0x1800471a7  lea     rcx, [rsi+610h]; this
0x1800471ae  call    ?LoadBandwidthProfiles@CBandwidthProfileMgr@@QEAAKXZ; CBandwidthProfileMgr::LoadBandwidthProfiles(void)
0x1800471b3  lea     rcx, [rsi+478h]; lpCriticalSection
0x1800471ba  call    ?LoadJobInactivityTimeout@PolicyMonitor@@QEAAXXZ; PolicyMonitor::LoadJobInactivityTimeout(void)
0x1800471bf  lea     rcx, [rsi+3E0h]; this
0x1800471c6  call    ?SetupThreadPoolEnv@CThreadPoolConnector@@QEAAXXZ; CThreadPoolConnector::SetupThreadPoolEnv(void)
0x1800471cb  cmp     [rsi+680h], rdi
0x1800471d2  jz      short loc_1800471F1
0x1800471d4  mov     ecx, 4; int
0x1800471d9  call    ?ReportServiceStartupPhase@@YAJH@Z; ReportServiceStartupPhase(int)
0x1800471de  mov     rcx, [rsi+680h]
0x1800471e5  mov     rax, [rcx]
0x1800471e8  mov     rax, [rax+20h]
0x1800471ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800471f1  lea     rax, ?g_GIT@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_GIT
0x1800471f8  mov     [rsp+160h+ppv], rax; ppv
0x1800471fd  lea     r9, IID_IGlobalInterfaceTable; riid
0x180047204  mov     r8d, ebx; dwClsContext
0x180047207  xor     edx, edx; pUnkOuter
0x180047209  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180047210  call    cs:__imp_CoCreateInstance
0x180047216  test    eax, eax
0x180047218  jns     short loc_180047250
0x18004721a  xorps   xmm0, xmm0
0x18004721d  movups  [rsp+160h+var_108], xmm0
0x180047222  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180047229  mov     [rsp+160h+pExceptionObject], rcx
0x18004722e  mov     [rsp+160h+var_F8], eax
0x180047232  mov     [rsp+160h+var_F4], 337h
0x18004723a  mov     [rsp+160h+var_F0], ebx
0x18004723e  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180047245  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x18004724a  call    _CxxThrowException_0
0x180047250  mov     ecx, 7; int
0x180047255  call    ?ReportServiceStartupPhase@@YAJH@Z; ReportServiceStartupPhase(int)
0x18004725a  mov     rcx, rsi; this
0x18004725d  call    ?UnserializeAndMigrateLegacyState@CJobManager@@QEAAXXZ; CJobManager::UnserializeAndMigrateLegacyState(void)
0x180047262  mov     rcx, rsi; this
0x180047265  call    ?UnserializeDatabaseState@CJobManager@@QEAAXXZ; CJobManager::UnserializeDatabaseState(void)
0x18004726a  mov     [rbp+60h+Context], rdi
0x18004726e  lea     r9, [rbp+60h+Context]; Context
0x180047272  xor     r8d, r8d; Parameter
0x180047275  lea     rdx, ?LazyGlobalInitializer@?$LazyGlobal@VNotificationRegistrar@@@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18004727c  lea     rcx, ?g_GlobalNotificationRegistrar@@3V?$LazyGlobal@VNotificationRegistrar@@@@A; InitOnce
0x180047283  call    cs:__imp_InitOnceExecuteOnce
0x180047289  test    eax, eax
0x18004728b  jnz     short loc_1800472C7
0x18004728d  xorps   xmm0, xmm0
0x180047290  movups  [rsp+160h+var_108], xmm0
0x180047295  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18004729c  mov     [rsp+160h+pExceptionObject], rcx
0x1800472a1  mov     [rsp+160h+var_F8], 8007000Eh
0x1800472a9  mov     [rsp+160h+var_F4], 33h ; '3'
0x1800472b1  mov     [rsp+160h+var_F0], ebx
0x1800472b5  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800472bc  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x1800472c1  call    _CxxThrowException_0
0x1800472c7  mov     rbx, [rbp+60h+Context]
0x1800472cb  mov     r15d, 20h ; ' '
0x1800472d1  mov     ecx, r15d; dwBytes
0x1800472d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800472d9  mov     r14, rax
0x1800472dc  test    rax, rax
0x1800472df  jz      short loc_1800472ED
0x1800472e1  lea     rax, ??_7?$ClassMethodCallbackContext@VCJobManager@@@details@@6B@; const details::ClassMethodCallbackContext<CJobManager>::`vftable'
0x1800472e8  mov     [r14], rax
0x1800472eb  jmp     short loc_1800472F0
0x1800472ed  mov     r14, rdi
0x1800472f0  mov     [rbp+60h+var_90], r14
0x1800472f4  mov     [r14+8], rsi
0x1800472f8  lea     rax, ?OnBackgroundAccessChange@CJobManager@@AEAAXPEBXK@Z; CJobManager::OnBackgroundAccessChange(void const *,ulong)
0x1800472ff  mov     qword ptr [rbp+60h+var_B0], rax
0x180047303  mov     dword ptr [rbp+60h+var_B0+8], edi
0x180047306  mov     eax, dword ptr [rsp+160h+var_130+0Ch]
0x18004730a  mov     dword ptr [rbp+60h+var_B0+0Ch], eax
0x18004730d  movups  xmm0, [rbp+60h+var_B0]
0x180047311  movdqu  xmmword ptr [r14+10h], xmm0
0x180047317  lea     rdi, [rbx+18h]
0x18004731b  mov     rcx, [rdi+8]
0x18004731f  sub     rcx, [rdi]
0x180047322  sar     rcx, 3
0x180047326  inc     rcx
0x180047329  mov     [rbp+60h+arg_0], rcx
0x18004732d  mov     rax, [rdi+10h]
0x180047331  sub     rax, [rdi]
0x180047334  sar     rax, 3
0x180047338  mov     rdx, 1FFFFFFFFFFFFFFFh
0x180047342  cmp     rcx, rax
0x180047345  jbe     short loc_180047366
0x180047347  cmp     rcx, rdx
0x18004734a  jbe     short loc_18004735A
0x18004734c  lea     rcx, aVectorTooLong; "vector too long"
0x180047353  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18004735a  lea     rdx, [rbp+60h+arg_0]
0x18004735e  mov     rcx, rdi
0x180047361  call    ??$_Reallocate@$0A@@?$vector@PEAVDeletableContextBase@details@@V?$allocator@PEAVDeletableContextBase@details@@@std@@@std@@AEAAXAEA_K@Z; std::vector<details::DeletableContextBase *>::_Reallocate<0>(unsigned __int64 &)
0x180047366  mov     dword ptr [rbp+60h+arg_0], 0Eh
0x18004736d  mov     rcx, r15; dwBytes
0x180047370  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180047375  mov     r15, rax
0x180047378  xor     r8d, r8d
0x18004737b  test    rax, rax
0x18004737e  jz      short loc_18004738C
0x180047380  lea     rax, ??_7?$ClassMethodCallbackContext@VCJobManager@@@details@@6B@; const details::ClassMethodCallbackContext<CJobManager>::`vftable'
0x180047387  mov     [r15], rax
0x18004738a  jmp     short loc_18004738F
0x18004738c  mov     r15, r8
0x18004738f  mov     qword ptr [rbp+60h+var_B0], r15
0x180047393  mov     eax, dword ptr [rbp+60h+arg_0]
0x180047396  mov     [r15+8], eax
0x18004739a  lea     rax, ??$ConvertFreeCallbackToClassMethodCallback@VCJobManager@@@details@@YAXPEAXPEBXK@Z; details::ConvertFreeCallbackToClassMethodCallback<CJobManager>(void *,void const *,ulong)
0x1800473a1  mov     [r15+10h], rax
0x1800473a5  mov     [r15+18h], r14
0x1800473a9  mov     rcx, [rdi+8]
0x1800473ad  sub     rcx, [rdi]
0x1800473b0  sar     rcx, 3
0x1800473b4  inc     rcx
0x1800473b7  mov     [rbp+60h+arg_10], rcx
0x1800473be  mov     rax, [rdi+10h]
0x1800473c2  sub     rax, [rdi]
0x1800473c5  sar     rax, 3
0x1800473c9  cmp     rcx, rax
0x1800473cc  jbe     short loc_1800473FD
0x1800473ce  mov     rax, 1FFFFFFFFFFFFFFFh
0x1800473d8  cmp     rcx, rax
0x1800473db  jbe     short loc_1800473EB
0x1800473dd  lea     rcx, aVectorTooLong; "vector too long"
0x1800473e4  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800473eb  lea     rdx, [rbp+60h+arg_10]
0x1800473f2  mov     rcx, rdi
0x1800473f5  call    ??$_Reallocate@$0A@@?$vector@PEAVDeletableContextBase@details@@V?$allocator@PEAVDeletableContextBase@details@@@std@@@std@@AEAAXAEA_K@Z; std::vector<details::DeletableContextBase *>::_Reallocate<0>(unsigned __int64 &)
0x1800473fa  xor     r8d, r8d
0x1800473fd  add     rbx, 8
0x180047401  mov     [rbp+60h+arg_18], rbx
0x180047408  mov     rcx, [rbx]
0x18004740b  mov     rax, [rcx+8]
0x18004740f  mov     qword ptr [rsp+160h+var_130], rax
0x180047414  mov     qword ptr [rsp+38h], 0
0x18004741d  mov     edx, dword ptr [rbp+60h+arg_0]
0x180047420  jmp     short loc_180047445
0x180047422  mov     qword ptr [rsp+160h+var_130], rax
0x180047427  cmp     [rax+20h], edx
0x18004742a  jnb     short loc_180047437
0x18004742c  mov     dword ptr [rsp+160h+var_130+8], r8d
0x180047431  add     rax, 10h
0x180047435  jmp     short loc_180047442
0x180047437  mov     dword ptr [rsp+160h+var_130+8], 1
0x18004743f  mov     rcx, rax
0x180047442  mov     rax, [rax]
0x180047445  cmp     [rax+19h], r8b
0x180047449  jz      short loc_180047422
0x18004744b  cmp     [rcx+19h], r8b
0x18004744f  jnz     short loc_180047456
0x180047451  cmp     edx, [rcx+20h]
0x180047454  jnb     short loc_1800474BB
0x180047456  mov     rcx, rbx
0x180047459  call    ?_Check_grow_by_1@?$_Tree@V?$_Tmap_traits@W4NotifiableSystemEvent@@PEAVITriggerableNotifier@@U?$less@W4NotifiableSystemEvent@@@std@@V?$allocator@U?$pair@$$CBW4NotifiableSystemEvent@@PEAVITriggerableNotifier@@@std@@@4@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<NotifiableSystemEvent,ITriggerableNotifier *,std::less<NotifiableSystemEvent>,std::allocator<std::pair<NotifiableSystemEvent const,ITriggerableNotifier *>>,0>>::_Check_grow_by_1(void)
0x18004745e  lea     rax, [rbp+60h+arg_0]
0x180047462  mov     [rbp+60h+arg_10], rax
0x180047469  lea     rax, [rbp+60h+arg_10]
0x180047470  mov     [rsp+160h+ppv], rax
0x180047475  mov     r8, [rbx]
0x180047478  mov     rdx, rbx
0x18004747b  lea     rcx, [rbp+60h+var_88]
0x18004747f  call    ??$?0AEBUpiecewise_construct_t@std@@V?$tuple@AEBW4RegistryKeyType@@@1@V?$tuple@$$V@1@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4RegistryKeyType@@PEAVIRegistryKeyTypeInfo@@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBW4RegistryKeyType@@PEAVIRegistryKeyTypeInfo@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBW4RegistryKeyType@@PEAVIRegistryKeyTypeInfo@@@std@@PEAX@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEBW4RegistryKeyType@@@1@$$QEAV?$tuple@$$V@1@@Z; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<RegistryKeyType const,IRegistryKeyTypeInfo *>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<RegistryKeyType const,IRegistryKeyTypeInfo *>,void *>>>(std::allocator<std::_Tree_node<std::pair<RegistryKeyType const,IRegistryKeyTypeInfo *>,void *>> &,std::_Tree_node<std::pair<RegistryKeyType const,IRegistryKeyTypeInfo *>,void *> *,std::piecewise_construct_t const &,std::tuple<RegistryKeyType const &> &&,std::tuple<> &&)
0x180047484  mov     rbx, [rax+8]
0x180047488  mov     qword ptr [rax+8], 0
0x180047490  lea     rcx, [rbp+60h+var_88]
0x180047494  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4_CRM_CLIENT_ID@@PEAX@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_CRM_CLIENT_ID const,void *>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_CRM_CLIENT_ID const,void *>,void *>>>(void)
0x180047499  movups  xmm0, [rsp+160h+var_130]
0x18004749e  movdqu  [rsp+160h+var_130], xmm0
0x1800474a4  mov     r8, rbx
0x1800474a7  lea     rdx, [rsp+160h+var_130]
0x1800474ac  mov     rcx, [rbp+60h+arg_18]
0x1800474b3  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4NotifiableSystemEvent@@PEAVITriggerableNotifier@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4NotifiableSystemEvent@@PEAVITriggerableNotifier@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBW4NotifiableSystemEvent@@PEAVITriggerableNotifier@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<NotifiableSystemEvent const,ITriggerableNotifier *>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<NotifiableSystemEvent const,ITriggerableNotifier *>,void *> *>,std::_Tree_node<std::pair<NotifiableSystemEvent const,ITriggerableNotifier *>,void *> * const)
0x1800474b8  mov     rcx, rax
0x1800474bb  mov     rcx, [rcx+28h]
0x1800474bf  mov     rax, [rcx]
0x1800474c2  mov     r8, r15
0x1800474c5  lea     rdx, ?EventLoggingCallbackWrapper@@YAXPEAXPEBXK@Z; EventLoggingCallbackWrapper(void *,void const *,ulong)
0x1800474cc  mov     rax, [rax+8]
0x1800474d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800474d5  mov     [rbp+60h+arg_10], r15
0x1800474dc  mov     rdx, [rdi+8]
0x1800474e0  cmp     rdx, [rdi+10h]
0x1800474e4  jz      short loc_1800474F0
0x1800474e6  mov     [rdx], r15
0x1800474e9  add     qword ptr [rdi+8], 8
0x1800474ee  jmp     short loc_180047500
0x1800474f0  lea     r8, [rbp+60h+arg_10]
0x1800474f7  mov     rcx, rdi
0x1800474fa  call    ??$_Emplace_reallocate@AEBQEAVServiceAccountUserSession@@@?$vector@PEAVServiceAccountUserSession@@V?$allocator@PEAVServiceAccountUserSession@@@std@@@std@@AEAAPEAPEAVServiceAccountUserSession@@QEAPEAV2@AEBQEAV2@@Z; std::vector<ServiceAccountUserSession *>::_Emplace_reallocate<ServiceAccountUserSession * const &>(ServiceAccountUserSession * * const,ServiceAccountUserSession * const &)
0x1800474ff  nop
0x180047500  mov     [rbp+60h+arg_0], r14
0x180047504  mov     rdx, [rdi+8]
0x180047508  cmp     rdx, [rdi+10h]
0x18004750c  jz      short loc_180047518
0x18004750e  mov     [rdx], r14
0x180047511  add     qword ptr [rdi+8], 8
0x180047516  jmp     short loc_180047525
0x180047518  lea     r8, [rbp+60h+arg_0]
0x18004751c  mov     rcx, rdi
0x18004751f  call    ??$_Emplace_reallocate@AEBQEAVServiceAccountUserSession@@@?$vector@PEAVServiceAccountUserSession@@V?$allocator@PEAVServiceAccountUserSession@@@std@@@std@@AEAAPEAPEAVServiceAccountUserSession@@QEAPEAV2@AEBQEAV2@@Z; std::vector<ServiceAccountUserSession *>::_Emplace_reallocate<ServiceAccountUserSession * const &>(ServiceAccountUserSession * * const,ServiceAccountUserSession * const &)
0x180047524  nop
0x180047525  lea     rdi, [rsi+310h]
0x18004752c  mov     rcx, rdi; this
0x18004752f  call    ?AddServiceAccounts@CLoggedOnUsers@@QEAAJXZ; CLoggedOnUsers::AddServiceAccounts(void)
0x180047534  test    eax, eax
0x180047536  jns     short loc_180047572
0x180047538  xorps   xmm0, xmm0
0x18004753b  movups  [rsp+160h+var_108], xmm0
0x180047540  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180047547  mov     [rsp+160h+pExceptionObject], rcx
0x18004754c  mov     [rsp+160h+var_F8], eax
0x180047550  mov     [rsp+160h+var_F4], 349h
0x180047558  mov     [rsp+160h+var_F0], 1
0x180047560  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180047567  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x18004756c  call    _CxxThrowException_0
0x180047572  mov     ecx, 9; int
0x180047577  call    ?ReportServiceStartupPhase@@YAJH@Z; ReportServiceStartupPhase(int)
0x18004757c  mov     rcx, rdi; this
0x18004757f  call    ?AddActiveUserManagerUsers@CLoggedOnUsers@@QEAAJXZ; CLoggedOnUsers::AddActiveUserManagerUsers(void)
0x180047584  test    eax, eax
0x180047586  jns     short loc_1800475C2
0x180047588  xorps   xmm0, xmm0
0x18004758b  movups  [rsp+160h+var_108], xmm0
0x180047590  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180047597  mov     [rsp+160h+pExceptionObject], rcx
0x18004759c  mov     [rsp+160h+var_F8], eax
0x1800475a0  mov     [rsp+160h+var_F4], 34Bh
0x1800475a8  mov     [rsp+160h+var_F0], 1
0x1800475b0  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800475b7  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x1800475bc  call    _CxxThrowException_0
0x1800475c2  mov     rcx, rdi; this
0x1800475c5  call    ?Dump@CLoggedOnUsers@@QEAAXXZ; CLoggedOnUsers::Dump(void)
0x1800475ca  mov     r14d, 1
0x1800475d0  mov     ebx, r14d
0x1800475d3  mov     rcx, [rsi+658h]
0x1800475da  mov     rcx, [rcx+rbx*8]; this
0x1800475de  call    ?StartTimer@CBandwidthChangeWorkItem@@QEAAXXZ; CBandwidthChangeWorkItem::StartTimer(void)
0x1800475e3  add     rbx, r14
0x1800475e6  cmp     rbx, 4
0x1800475ea  jnz     short loc_1800475D3
0x1800475ec  mov     rax, [rsi]
0x1800475ef  mov     rcx, rsi
0x1800475f2  mov     rax, [rax+20h]
0x1800475f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800475fb  mov     rax, [rsi]
0x1800475fe  mov     rcx, rsi
0x180047601  mov     rax, [rax+30h]
0x180047605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004760a  mov     rax, [rsi]
0x18004760d  mov     rcx, rsi
0x180047610  mov     rax, [rax+38h]
0x180047614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047619  mov     rcx, rdi; this
0x18004761c  call    ?AddActiveRemotePowerShellSessions@CLoggedOnUsers@@QEAAXXZ; CLoggedOnUsers::AddActiveRemotePowerShellSessions(void)
  ... truncated ...
```
