# FrsService::RunAsService(void)

- ea: `0x14000fad0`
- end: `0x140010298`
- name: `?RunAsService@FrsService@@QEAAPEAVFrsStatus@@XZ`
- size: `1992`
- prototype: `struct FrsStatus *__fastcall(FrsService *__hidden this)`
- caller_count: `1`
- callee_count: `33`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x140010518`

## callees

- `0x1400036d0`
- `0x14000cdc0`
- `0x14000d8e8`
- `0x14000d980`
- `0x14000daa0`
- `0x14000dcc0`
- `0x14000e34c`
- `0x14000e48c`
- `0x14000e5f0`
- `0x14000eaa0`
- `0x14000fad0`
- `0x140015408`
- `0x140019a58`
- `0x14001b788`
- `0x14001bd24`
- `0x1400230b4`
- `0x1400319f8`
- `0x14003f89c`
- `0x140041814`
- `0x140042690`
- `0x14004d0c4`
- `0x14006a550`
- `0x1400c2df0`
- `0x140197a80`
- `0x140198c10`
- `0x1401b3140`
- `0x1401b49ec`
- `0x1401b4b28`
- `0x1401b88e0`
- `0x1401b9494`
- `0x1401bda10`
- `0x1401cca58`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x140010010`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140010010`
- `KERNEL32!LeaveCriticalSection` at `0x14000fdac`
- `KERNEL32!LeaveCriticalSection` at `0x140010033`
- `KERNEL32!LeaveCriticalSection` at `0x14000fdac`
- `KERNEL32!LeaveCriticalSection` at `0x140010033`
- `KERNEL32!EnterCriticalSection` at `0x14000fd7b`
- `KERNEL32!EnterCriticalSection` at `0x14000fff2`
- `KERNEL32!EnterCriticalSection` at `0x14000fd7b`
- `KERNEL32!EnterCriticalSection` at `0x14000fff2`
- `KERNEL32!GetCurrentThreadId` at `0x14001004e`
- `KERNEL32!GetCurrentThreadId` at `0x140010275`
- `KERNEL32!GetCurrentThreadId` at `0x14001004e`
- `KERNEL32!GetCurrentThreadId` at `0x140010275`
- `KERNEL32!InitializeCriticalSection` at `0x14000fe37`
- `KERNEL32!InitializeCriticalSection` at `0x14000fe37`

## string_xrefs

- `0x140010077`: `base\fs\remotefs\frs\src\main\frsservice.cpp`
- `0x14000fb47`: `FrsService::RunAsService`
- `0x14000fe61`: `FrsService::RunAsService`
- `0x14000feba`: `FrsService::RunAsService`
- `0x14000ff68`: `FrsService::RunAsService`
- `0x140010225`: `FrsService::RunAsService`
- `0x14001011b`: `Failed to SetFinalState to SERVICE_RUNNING. Error:%?`
- `0x14000ff2e`: `(Ignored) Failed to connect to Read Only driver. Error:%?`
- `0x14000ffb1`: `Failed to register service WMI providers. Error:%?`
- `0x14001006b`: `FrsService::RunAsService`
- `0x1400101c0`: `Failed to Run Service: %?`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
struct FrsStatus *__fastcall FrsService::RunAsService(FrsService *this)
{
  __int64 v2; // r14
  const struct Config::Machine *Machine; // rbx
  struct FrsStatus *inited; // r15
  int v5; // edx
  struct FrsStatus *v6; // rdi
  unsigned int v7; // eax
  int v8; // edx
  char *v9; // rsi
  __int64 v10; // rdi
  struct FrsStatus *v11; // rdi
  NetworkGlobals *v12; // rcx
  __int64 v13; // rdi
  struct FrsStatus *v14; // rax
  _QWORD *v15; // rdi
  struct MonitorContext *v16; // rsi
  struct _RTL_CRITICAL_SECTION *v17; // rdi
  ConfigContext *v18; // rcx
  struct _RTL_CRITICAL_SECTION *v19; // rdi
  FrsFilter *v20; // rcx
  struct FrsStatus *started; // r8
  struct FrsStatus *v22; // r8
  BaseServiceConfig *v23; // rcx
  struct FrsStatus *v24; // rax
  struct MonitorContext *v25; // rsi
  __int64 v26; // rcx
  __int64 v27; // rax
  struct FrsStatus *v29; // r8
  const wchar_t *v30; // rdx
  ConfigContext *v31; // rcx
  MonitorContext *v32; // rcx
  struct FrsStatus *v33; // r8
  __int64 v34; // rcx
  DWORD CurrentThreadId; // [rsp+38h] [rbp-48h]
  DWORD v36; // [rsp+38h] [rbp-48h]
  _BYTE v37[16]; // [rsp+58h] [rbp-28h] BYREF
  const wchar_t *v38; // [rsp+68h] [rbp-18h] BYREF
  int v39; // [rsp+70h] [rbp-10h]
  int v40; // [rsp+74h] [rbp-Ch]
  const wchar_t *v41; // [rsp+78h] [rbp-8h]
  struct FrsStatus *v42; // [rsp+C8h] [rbp+48h] BYREF
  const struct Config::Machine *v43; // [rsp+D0h] [rbp+50h] BYREF
  struct ScopedCS *v44; // [rsp+D8h] [rbp+58h]

  v2 = 0;
  Machine = 0;
  v43 = 0;
  inited = FrsEvent::Initialize();
  if ( inited )
    goto LABEL_44;
  FrsEvent::Log(1073742826);
  v44 = (FrsService *)((char *)this + 128);
  ScopedLock::ScopedLock((ScopedLock *)v37, (FrsService *)((char *)this + 128));
  inited = ServiceControl::SetFinalState((LPSERVICE_STATUS)this + 8, 4u, 0);
  if ( inited || *((_DWORD *)this + 4) )
  {
    if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 2 )
      goto LABEL_57;
    v39 = 863;
    v29 = inited;
    v30 = L"Failed to SetFinalState to SERVICE_RUNNING. Error:%?";
LABEL_56:
    v38 = L"FrsService::RunAsService";
    v40 = 2;
    v41 = L"FSVC";
    dbgobj::DbgPrint<unsigned short,FrsStatus>(&v38, v30, v29);
    goto LABEL_57;
  }
  inited = MainInitializeGlobalsAfterServiceStarted();
  if ( inited || *((_DWORD *)this + 4) )
    goto LABEL_57;
  v42 = (struct FrsStatus *)operator new(0xB0u);
  *((_QWORD *)this + 168) = TaskPool::TaskPool(v42, v5, 0);
  v6 = (struct FrsStatus *)operator new(0xB0u);
  v42 = v6;
  v7 = Settings::GenericDwordSetting::operator()(&Settings::UpdateWorkerThreadCount);
  TaskPool::TaskPool(v6, v8, v7);
  *(_QWORD *)v6 = &UpdateWorkerTaskPool::`vftable';
  *((_QWORD *)this + 169) = v6;
  v9 = (char *)operator new(0x90u);
  v42 = (struct FrsStatus *)v9;
  v10 = *((_QWORD *)this + 168);
  *(_QWORD *)v9 = &RpcNetwork::`vftable';
  CREWLock::CREWLock((CREWLock *)(v9 + 8));
  *((_DWORD *)v9 + 28) = 0;
  *((_QWORD *)v9 + 15) = 0;
  *((_DWORD *)v9 + 32) = 0;
  *((_DWORD *)v9 + 33) = -1;
  *((_QWORD *)v9 + 17) = v10;
  *((_QWORD *)this + 170) = v9;
  v11 = (struct FrsStatus *)operator new(0xB0u);
  v42 = v11;
  Task::Task(v11, *((struct TaskPool **)this + 168));
  *(_QWORD *)v11 = &FrsService::RestartFromInternalShutdownTask::`vftable'{for `RefCountObject'};
  *((_QWORD *)v11 + 4) = &FrsService::RestartFromInternalShutdownTask::`vftable'{for `ShutdownObject'};
  *((_QWORD *)v11 + 21) = this;
  *((_QWORD *)this + 174) = v11;
  v13 = *((_QWORD *)this + 170);
  if ( !g_NetworkGlobals )
  {
    v42 = (struct FrsStatus *)operator new(0xD8u);
    g_NetworkGlobals = NetworkGlobals::NetworkGlobals(v42);
  }
  v14 = NetworkGlobals::Initialize(v12, *(struct TaskPool **)(v13 + 136));
  inited = v14;
  if ( v14 || (*(_DWORD *)(v13 + 112) = 1, *((_DWORD *)this + 4)) )
  {
    if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 2 )
      goto LABEL_57;
    v39 = 906;
    v29 = v14;
    v30 = L"Failed to initialize network. Error:%?";
    goto LABEL_56;
  }
  *((_QWORD *)this + 135) = *((_QWORD *)this + 170);
  FrsEvent::Log(1073742828);
  *((_DWORD *)this + 47) = 1;
  inited = Config::RegWriter::InitAccessChecks();
  if ( !inited && !*((_DWORD *)this + 4) )
  {
    v15 = (_QWORD *)((char *)this + 1368);
    inited = DBClone::GetOrCreate(this, (struct DBClone **)this + 171);
    if ( !inited && !*((_DWORD *)this + 4) )
    {
      if ( *v15 )
      {
        *((_QWORD *)g_MonitorContext + 2) = *v15;
        inited = (struct FrsStatus *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 41) + 24LL))((char *)this + 328);
        if ( !inited && !*((_DWORD *)this + 4) )
        {
          v16 = g_MonitorContext;
          v17 = (struct _RTL_CRITICAL_SECTION *)((char *)g_MonitorContext + 184);
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_MonitorContext + 184));
          *((_DWORD *)v16 + 44) = 1;
          *((_DWORD *)v16 + 26) = 0;
          StateHistory::Update(
            (struct MonitorContext *)((char *)v16 + 120),
            (struct MonitorContext *)((char *)v16 + 32));
          *((_DWORD *)v16 + 44) = 0;
          LeaveCriticalSection(v17);
          *(_DWORD *)v16 = 1;
          Machine = ConfigContext::GetMachine(v18);
          v43 = Machine;
          ConfigContext::InitLogger(g_ConfigContext, Machine);
          FrsService::InitializeReplicator(this);
          if ( *((_DWORD *)this + 4) )
          {
            ScopedLock::~ScopedLock((ScopedLock *)v37);
            goto LABEL_64;
          }
          if ( Settings::GhostingEnabled )
          {
            v19 = (struct _RTL_CRITICAL_SECTION *)operator new(0xC89F0u);
            v42 = (struct FrsStatus *)v19;
            ScopedCS::ScopedCS((ScopedCS *)&v19->LockCount);
            v19[1].LockSemaphore = CreateEventOrDie(1, 1);
            InitializeCriticalSection(v19 + 2);
            LODWORD(v19[1].SpinCount) = -1;
            *(_QWORD *)&v19[20543].LockCount = this;
            g_FrsFilter = (struct FrsFilter *)v19;
            started = FrsFilter::StartProcessingMessages(v20);
            v42 = started;
            if ( started )
            {
              if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
              {
                v38 = L"FrsService::RunAsService";
                v39 = 990;
                v40 = 3;
                v41 = L"FSVC";
                dbgobj::DbgPrint<unsigned short,FrsStatus>(
                  &v38,
                  L"(Ignored) Failed to connect to ghosting driver. Error:%?",
                  started);
              }
              CLEAR_ERROR(&v42);
            }
          }
          v42 = (struct FrsStatus *)operator new(0x108u);
          g_FrsReadOnlyFilter = FrsReadOnlyFilter::FrsReadOnlyFilter(v42);
          v22 = (struct FrsStatus *)(*(__int64 (__fastcall **)(FrsReadOnlyFilter *))(*(_QWORD *)g_FrsReadOnlyFilter
                                                                                   + 64LL))(g_FrsReadOnlyFilter);
          v42 = v22;
          if ( v22 )
          {
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
            {
              v38 = L"FrsService::RunAsService";
              v39 = 1013;
              v40 = 3;
              v41 = L"FSVC";
              dbgobj::DbgPrint<unsigned short,FrsStatus>(
                &v38,
                L"(Ignored) Failed to connect to Read Only driver. Error:%?",
                v22);
            }
            CLEAR_ERROR(&v42);
          }
          BaseServiceConfig::SetConfigReplicator(
            (FrsService *)((char *)this + 328),
            *((struct FrsReplicator **)this + 167));
          v24 = BaseServiceConfig::RegisterProviders(v23);
          inited = v24;
          v42 = v24;
          if ( !*((_DWORD *)this + 4) )
          {
            if ( v24 )
            {
              if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
              {
                v38 = L"FrsService::RunAsService";
                v39 = 1032;
                v40 = 2;
                v41 = L"FSVC";
                dbgobj::DbgPrint<unsigned short,FrsStatus>(
                  &v38,
                  L"Failed to register service WMI providers. Error:%?",
                  v24);
              }
              CLEAR_ERROR(&v42);
              inited = v42;
            }
            ServiceConfig::StartTasks((FrsService *)((char *)this + 328));
            if ( !*((_DWORD *)this + 4) )
            {
              v25 = g_MonitorContext;
              if ( *(_DWORD *)g_MonitorContext )
              {
                EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_MonitorContext + 184));
                *((_DWORD *)v25 + 44) = 1;
                *((_DWORD *)v25 + 26) = 1;
                GetSystemTimeAsFileTime((LPFILETIME)v25 + 8);
                StateHistory::Update(
                  (struct MonitorContext *)((char *)v25 + 120),
                  (struct MonitorContext *)((char *)v25 + 32));
                *((_DWORD *)v25 + 44) = 0;
                LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v25 + 184));
              }
              ScopedLock::~ScopedLock((ScopedLock *)v37);
              if ( !inited )
                goto LABEL_46;
LABEL_44:
              CurrentThreadId = GetCurrentThreadId();
              v27 = FrsStatusList::PushNewError(
                      v26,
                      *((unsigned int *)inited + 1),
                      *((unsigned int *)inited + 2),
                      *(unsigned int *)inited,
                      "base\\fs\\remotefs\\frs\\src\\main\\frsservice.cpp",
                      "FrsService::RunAsService",
                      1049,
                      CurrentThreadId,
                      inited);
LABEL_45:
              v2 = v27;
              goto LABEL_46;
            }
          }
        }
      }
    }
  }
LABEL_57:
  ScopedLock::~ScopedLock((ScopedLock *)v37);
  if ( inited )
  {
    if ( !Machine )
    {
      if ( g_ConfigContext )
      {
        v43 = ConfigContext::GetMachine(v31);
        ConfigContext::InitLogger(g_ConfigContext, v43);
        if ( g_DebugLog )
        {
          if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
          {
            v38 = L"FrsService::RunAsService";
            v39 = 1059;
            v40 = 2;
            v41 = L"FSVC";
            dbgobj::DbgPrint<unsigned short,FrsStatus>(&v38, L"Failed to Run Service: %?", inited);
          }
        }
      }
    }
  }
LABEL_64:
  ScopedLock::ScopedLock((ScopedLock *)v37, v44);
  FrsEvent::Log(1073742832);
  MonitorContext::DeleteServiceInfo(v32);
  v33 = ServiceControl::SetFinalState((LPSERVICE_STATUS)this + 8, 1u, 0x42Bu);
  v42 = v33;
  if ( v33 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v38 = L"FrsService::RunAsService";
      v39 = 1069;
      v40 = 2;
      v41 = L"FSVC";
      dbgobj::DbgPrint<unsigned short,FrsStatus>(&v38, L"(Ignored) Failed to SetFinalState to Stopped. Error:%?", v33);
    }
    CLEAR_ERROR(&v42);
  }
  ScopedLock::~ScopedLock((ScopedLock *)v37);
  if ( inited )
  {
    v36 = GetCurrentThreadId();
    v27 = FrsStatusList::PushNewError(
            v34,
            *((unsigned int *)inited + 1),
            *((unsigned int *)inited + 2),
            *(unsigned int *)inited,
            "base\\fs\\remotefs\\frs\\src\\main\\frsservice.cpp",
            "FrsService::RunAsService",
            1074,
            v36,
            inited);
    goto LABEL_45;
  }
LABEL_46:
  ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v43);
  return (struct FrsStatus *)v2;
}

```

## disassembly

```asm
0x14000fad0  mov     [rsp-38h+arg_0], rbx
0x14000fad5  push    rbp
0x14000fad6  push    rsi
0x14000fad7  push    rdi
0x14000fad8  push    r12
0x14000fada  push    r13
0x14000fadc  push    r14
0x14000fade  push    r15
0x14000fae0  mov     rbp, rsp
0x14000fae3  sub     rsp, 80h
0x14000faea  mov     r13, rcx
0x14000faed  xor     r14d, r14d
0x14000faf0  mov     ebx, r14d
0x14000faf3  mov     [rbp+arg_10], rbx
0x14000faf7  call    ?Initialize@FrsEvent@@SAPEAVFrsStatus@@XZ; FrsEvent::Initialize(void)
0x14000fafc  mov     r15, rax
0x14000faff  test    rax, rax
0x14000fb02  jnz     loc_14001004E
0x14000fb08  mov     ecx, 400003EAh
0x14000fb0d  call    ?Log@FrsEvent@@SAXW4FrsEventsEnum0@@@Z; FrsEvent::Log(FrsEventsEnum0)
0x14000fb12  lea     rax, [r13+80h]
0x14000fb19  mov     [rbp+arg_18], rax
0x14000fb1d  mov     rdx, rax; struct ScopedCS *
0x14000fb20  lea     rcx, [rbp+var_28]; this
0x14000fb24  call    ??0ScopedLock@@QEAA@AEAVScopedCS@@@Z; ScopedLock::ScopedLock(ScopedCS &)
0x14000fb29  nop
0x14000fb2a  lea     rax, [r13+0E0h]
0x14000fb31  mov     [rbp+lpServiceStatus], rax
0x14000fb35  xor     r8d, r8d; unsigned int
0x14000fb38  lea     edx, [r14+4]; unsigned int
0x14000fb3c  mov     rcx, rax; lpServiceStatus
0x14000fb3f  call    ?SetFinalState@ServiceControl@@QEAAPEAVFrsStatus@@KK@Z; ServiceControl::SetFinalState(ulong,ulong)
0x14000fb44  mov     r15, rax
0x14000fb47  lea     r12, aFrsserviceRuna; "FrsService::RunAsService"
0x14000fb4e  lea     rsi, aFsvc; "FSVC"
0x14000fb55  test    rax, rax
0x14000fb58  jnz     loc_1400100F9
0x14000fb5e  cmp     [r13+10h], r14d
0x14000fb62  jnz     loc_1400100F9
0x14000fb68  call    ?MainInitializeGlobalsAfterServiceStarted@@YAPEAVFrsStatus@@XZ; MainInitializeGlobalsAfterServiceStarted(void)
0x14000fb6d  mov     r15, rax
0x14000fb70  test    rax, rax
0x14000fb73  jnz     loc_14001013B
0x14000fb79  cmp     [r13+10h], r14d
0x14000fb7d  jnz     loc_14001013B
0x14000fb83  mov     r15d, 0B0h
0x14000fb89  mov     ecx, r15d; Size
0x14000fb8c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000fb91  mov     [rbp+arg_8], rax
0x14000fb95  xor     r8d, r8d; unsigned int
0x14000fb98  mov     rcx, rax; this
0x14000fb9b  call    ??0TaskPool@@QEAA@HK@Z; TaskPool::TaskPool(int,ulong)
0x14000fba0  nop
0x14000fba1  mov     [r13+540h], rax
0x14000fba8  mov     ecx, r15d; Size
0x14000fbab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000fbb0  mov     rdi, rax
0x14000fbb3  mov     [rbp+arg_8], rax
0x14000fbb7  lea     rcx, ?UpdateWorkerThreadCount@Settings@@3VCUpdateWorkerThreadCount@1@A; Settings::CUpdateWorkerThreadCount Settings::UpdateWorkerThreadCount
0x14000fbbe  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x14000fbc3  mov     r8d, eax; unsigned int
0x14000fbc6  mov     rcx, rdi; this
0x14000fbc9  call    ??0TaskPool@@QEAA@HK@Z; TaskPool::TaskPool(int,ulong)
0x14000fbce  lea     rax, ??_7UpdateWorkerTaskPool@@6B@; const UpdateWorkerTaskPool::`vftable'
0x14000fbd5  mov     [rdi], rax
0x14000fbd8  mov     [r13+548h], rdi
0x14000fbdf  lea     ecx, [r15-20h]; Size
0x14000fbe3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000fbe8  mov     rsi, rax
0x14000fbeb  mov     [rbp+arg_8], rax
0x14000fbef  mov     rdi, [r13+540h]
0x14000fbf6  lea     rax, ??_7RpcNetwork@@6B@; const RpcNetwork::`vftable'
0x14000fbfd  mov     [rsi], rax
0x14000fc00  lea     rcx, [rsi+8]; this
0x14000fc04  call    ??0CREWLock@@QEAA@XZ; CREWLock::CREWLock(void)
0x14000fc09  mov     [rsi+70h], r14d
0x14000fc0d  mov     [rsi+78h], r14
0x14000fc11  mov     [rsi+80h], r14d
0x14000fc18  or      dword ptr [rsi+84h], 0FFFFFFFFh
0x14000fc1f  mov     [rsi+88h], rdi
0x14000fc26  mov     [r13+550h], rsi
0x14000fc2d  mov     ecx, r15d; Size
0x14000fc30  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000fc35  mov     rdi, rax
0x14000fc38  mov     [rbp+arg_8], rax
0x14000fc3c  mov     rdx, [r13+540h]; struct TaskPool *
0x14000fc43  mov     rcx, rax; this
0x14000fc46  call    ??0Task@@QEAA@PEAVTaskPool@@@Z; Task::Task(TaskPool *)
0x14000fc4b  lea     rax, ??_7RestartFromInternalShutdownTask@FrsService@@6BRefCountObject@@@; const FrsService::RestartFromInternalShutdownTask::`vftable'{for `RefCountObject'}
0x14000fc52  mov     [rdi], rax
0x14000fc55  lea     rax, ??_7RestartFromInternalShutdownTask@FrsService@@6BShutdownObject@@@; const FrsService::RestartFromInternalShutdownTask::`vftable'{for `ShutdownObject'}
0x14000fc5c  mov     [rdi+20h], rax
0x14000fc60  mov     [rdi+0A8h], r13
0x14000fc67  mov     [r13+570h], rdi
0x14000fc6e  mov     rdi, [r13+550h]
0x14000fc75  cmp     cs:?g_NetworkGlobals@@3PEAVNetworkGlobals@@EA, r14; NetworkGlobals * g_NetworkGlobals
0x14000fc7c  jnz     short loc_14000FC9B
0x14000fc7e  lea     ecx, [r15+28h]; Size
0x14000fc82  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000fc87  mov     [rbp+arg_8], rax
0x14000fc8b  mov     rcx, rax; this
0x14000fc8e  call    ??0NetworkGlobals@@QEAA@XZ; NetworkGlobals::NetworkGlobals(void)
0x14000fc93  nop
0x14000fc94  mov     cs:?g_NetworkGlobals@@3PEAVNetworkGlobals@@EA, rax; NetworkGlobals * g_NetworkGlobals
0x14000fc9b  mov     rdx, [rdi+88h]; struct TaskPool *
0x14000fca2  call    ?Initialize@NetworkGlobals@@QEAAPEAVFrsStatus@@PEAVTaskPool@@@Z; NetworkGlobals::Initialize(TaskPool *)
0x14000fca7  mov     r15, rax
0x14000fcaa  test    rax, rax
0x14000fcad  jnz     loc_1400100BE
0x14000fcb3  lea     esi, [rax+1]
0x14000fcb6  mov     [rdi+70h], esi
0x14000fcb9  cmp     [r13+10h], r14d
0x14000fcbd  jnz     loc_1400100BE
0x14000fcc3  lea     r12, [r13+148h]
0x14000fcca  mov     rax, [r13+550h]
0x14000fcd1  mov     [r12+2F0h], rax
0x14000fcd9  mov     ecx, 400003ECh
0x14000fcde  call    ?Log@FrsEvent@@SAXW4FrsEventsEnum0@@@Z; FrsEvent::Log(FrsEventsEnum0)
0x14000fce3  mov     [r13+0BCh], esi
0x14000fcea  call    ?InitAccessChecks@RegWriter@Config@@SAPEAVFrsStatus@@XZ; Config::RegWriter::InitAccessChecks(void)
0x14000fcef  mov     r15, rax
0x14000fcf2  test    rax, rax
0x14000fcf5  jnz     loc_14000FF68
0x14000fcfb  cmp     [r13+10h], r14d
0x14000fcff  jnz     loc_14000FF68
0x14000fd05  lea     rdi, [r13+558h]
0x14000fd0c  mov     rdx, rdi; struct DBClone **
0x14000fd0f  mov     rcx, r13; struct FrsService *
0x14000fd12  call    ?GetOrCreate@DBClone@@SAPEAVFrsStatus@@PEAVFrsService@@AEAPEAV1@@Z; DBClone::GetOrCreate(FrsService *,DBClone * &)
0x14000fd17  mov     r15, rax
0x14000fd1a  test    rax, rax
0x14000fd1d  jnz     loc_14000FF68
0x14000fd23  cmp     [r13+10h], r14d
0x14000fd27  jnz     loc_14000FF68
0x14000fd2d  mov     rcx, [rdi]
0x14000fd30  test    rcx, rcx
0x14000fd33  jz      loc_14000FF68
0x14000fd39  mov     rax, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x14000fd40  mov     [rax+10h], rcx
0x14000fd44  mov     rax, [r12]
0x14000fd48  mov     rcx, r12
0x14000fd4b  mov     rax, [rax+18h]
0x14000fd4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fd54  mov     r15, rax
0x14000fd57  test    rax, rax
0x14000fd5a  jnz     loc_14000FF68
0x14000fd60  cmp     [r13+10h], r14d
0x14000fd64  jnz     loc_14000FF68
0x14000fd6a  mov     rsi, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x14000fd71  lea     rdi, [rsi+0B8h]
0x14000fd78  mov     rcx, rdi; lpCriticalSection
0x14000fd7b  call    cs:__imp_EnterCriticalSection
0x14000fd82  nop     dword ptr [rax+rax+00h]
0x14000fd87  mov     dword ptr [rsi+0B0h], 1
0x14000fd91  mov     [rsi+68h], r14d
0x14000fd95  lea     rdx, [rsi+20h]; struct HistoryRecord *
0x14000fd99  lea     rcx, [rsi+78h]; this
0x14000fd9d  call    ?Update@StateHistory@@MEAAXPEAVHistoryRecord@@@Z; StateHistory::Update(HistoryRecord *)
0x14000fda2  mov     [rsi+0B0h], r14d
0x14000fda9  mov     rcx, rdi; lpCriticalSection
0x14000fdac  call    cs:__imp_LeaveCriticalSection
0x14000fdb3  nop     dword ptr [rax+rax+00h]
0x14000fdb8  mov     dword ptr [rsi], 1
0x14000fdbe  call    ?GetMachine@ConfigContext@@QEAAPEAVMachine@Config@@XZ; ConfigContext::GetMachine(void)
0x14000fdc3  mov     rbx, rax
0x14000fdc6  mov     [rbp+arg_10], rax
0x14000fdca  mov     rdx, rax; struct Config::Machine *
0x14000fdcd  mov     rcx, cs:?g_ConfigContext@@3PEAVConfigContext@@EA; this
0x14000fdd4  call    ?InitLogger@ConfigContext@@QEAAXPEBVMachine@Config@@@Z; ConfigContext::InitLogger(Config::Machine const *)
0x14000fdd9  mov     rcx, r13; this
0x14000fddc  call    ?InitializeReplicator@FrsService@@QEAAXXZ; FrsService::InitializeReplicator(void)
0x14000fde1  cmp     [r13+10h], r14d
0x14000fde5  jz      short loc_14000FDF5
0x14000fde7  lea     rcx, [rbp+var_28]; this
0x14000fdeb  call    ??1ScopedLock@@QEAA@XZ; ScopedLock::~ScopedLock(void)
0x14000fdf0  jmp     loc_1400101D0
0x14000fdf5  mov     r15d, 3
0x14000fdfb  cmp     cs:?GhostingEnabled@Settings@@3VGenericBoolSetting@1@A, r14d; Settings::GenericBoolSetting Settings::GhostingEnabled
0x14000fe02  jz      loc_14000FEBA
0x14000fe08  mov     ecx, 0C89F0h; Size
0x14000fe0d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000fe12  mov     rdi, rax
0x14000fe15  mov     [rbp+arg_8], rax
0x14000fe19  lea     rcx, [rax+8]; this
0x14000fe1d  call    ??0ScopedCS@@QEAA@XZ; ScopedCS::ScopedCS(void)
0x14000fe22  lea     esi, [r15-2]
0x14000fe26  mov     edx, esi; bInitialState
0x14000fe28  mov     ecx, esi; bManualReset
0x14000fe2a  call    ?CreateEventOrDie@@YAPEAXHH@Z; CreateEventOrDie(int,int)
0x14000fe2f  mov     [rdi+40h], rax
0x14000fe33  lea     rcx, [rdi+50h]; lpCriticalSection
0x14000fe37  call    cs:__imp_InitializeCriticalSection
0x14000fe3e  nop     dword ptr [rax+rax+00h]
0x14000fe43  or      dword ptr [rdi+48h], 0FFFFFFFFh
0x14000fe47  mov     [rdi+0C89E0h], r13
0x14000fe4e  mov     cs:?g_FrsFilter@@3PEAVFrsFilter@@EA, rdi; FrsFilter * g_FrsFilter
0x14000fe55  call    ?StartProcessingMessages@FrsFilter@@QEAAPEAVFrsStatus@@XZ; FrsFilter::StartProcessingMessages(void)
0x14000fe5a  mov     r8, rax
0x14000fe5d  mov     [rbp+arg_8], rax
0x14000fe61  lea     rdi, aFrsserviceRuna; "FrsService::RunAsService"
0x14000fe68  lea     rsi, aFsvc; "FSVC"
0x14000fe6f  test    rax, rax
0x14000fe72  jz      short loc_14000FEC8
0x14000fe74  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14000fe7b  test    rax, rax
0x14000fe7e  jz      short loc_14000FEAF
0x14000fe80  cmp     [rax+40h], r14d
0x14000fe84  jz      short loc_14000FEAF
0x14000fe86  cmp     [rax+38h], r15d
0x14000fe8a  jl      short loc_14000FEAF
0x14000fe8c  mov     [rbp+var_18], rdi
0x14000fe90  mov     [rbp+var_10], 3DEh
0x14000fe97  mov     [rbp+var_C], r15d
0x14000fe9b  mov     [rbp+var_8], rsi
0x14000fe9f  lea     rdx, aIgnoredFailedT_59; "(Ignored) Failed to connect to ghosting"...
0x14000fea6  lea     rcx, [rbp+var_18]
0x14000feaa  call    ??$DbgPrint@GVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStatus>(ushort const *,FrsStatus const &)
0x14000feaf  lea     rcx, [rbp+arg_8]; struct FrsStatus **
0x14000feb3  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x14000feb8  jmp     short loc_14000FEC8
0x14000feba  lea     rdi, aFrsserviceRuna; "FrsService::RunAsService"
0x14000fec1  lea     rsi, aFsvc; "FSVC"
0x14000fec8  mov     ecx, 108h; Size
0x14000fecd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000fed2  mov     [rbp+arg_8], rax
0x14000fed6  mov     rcx, rax; this
0x14000fed9  call    ??0FrsReadOnlyFilter@@QEAA@XZ; FrsReadOnlyFilter::FrsReadOnlyFilter(void)
0x14000fede  mov     rdx, rax
0x14000fee1  mov     cs:?g_FrsReadOnlyFilter@@3PEAVFrsReadOnlyFilter@@EA, rax; FrsReadOnlyFilter * g_FrsReadOnlyFilter
0x14000fee8  mov     rcx, [rax]
0x14000feeb  mov     rax, [rcx+40h]
0x14000feef  mov     rcx, rdx
0x14000fef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fef7  mov     r8, rax
0x14000fefa  mov     [rbp+arg_8], rax
0x14000fefe  test    rax, rax
0x14000ff01  jz      short loc_14000FF47
0x14000ff03  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14000ff0a  test    rax, rax
0x14000ff0d  jz      short loc_14000FF3E
0x14000ff0f  cmp     [rax+40h], r14d
0x14000ff13  jz      short loc_14000FF3E
0x14000ff15  cmp     [rax+38h], r15d
0x14000ff19  jl      short loc_14000FF3E
0x14000ff1b  mov     [rbp+var_18], rdi
0x14000ff1f  mov     [rbp+var_10], 3F5h
0x14000ff26  mov     [rbp+var_C], r15d
0x14000ff2a  mov     [rbp+var_8], rsi
0x14000ff2e  lea     rdx, aIgnoredFailedT_34; "(Ignored) Failed to connect to Read Onl"...
0x14000ff35  lea     rcx, [rbp+var_18]
0x14000ff39  call    ??$DbgPrint@GVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStatus>(ushort const *,FrsStatus const &)
0x14000ff3e  lea     rcx, [rbp+arg_8]; struct FrsStatus **
0x14000ff42  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x14000ff47  mov     rdx, [r13+538h]; struct FrsReplicator *
0x14000ff4e  mov     rcx, r12; this
0x14000ff51  call    ?SetConfigReplicator@BaseServiceConfig@@QEAAXPEAVFrsReplicator@@@Z; BaseServiceConfig::SetConfigReplicator(FrsReplicator *)
0x14000ff56  call    ?RegisterProviders@BaseServiceConfig@@QEAAPEAVFrsStatus@@XZ; BaseServiceConfig::RegisterProviders(void)
0x14000ff5b  mov     r15, rax
0x14000ff5e  mov     [rbp+arg_8], rax
0x14000ff62  cmp     [r13+10h], r14d
0x14000ff66  jz      short loc_14000FF7B
0x14000ff68  lea     r12, aFrsserviceRuna; "FrsService::RunAsService"
0x14000ff6f  lea     rsi, aFsvc; "FSVC"
0x14000ff76  jmp     loc_14001013B
0x14000ff7b  test    r15, r15
0x14000ff7e  jz      short loc_14000FFCE
0x14000ff80  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14000ff87  test    rax, rax
0x14000ff8a  jz      short loc_14000FFC1
0x14000ff8c  cmp     [rax+40h], r14d
0x14000ff90  jz      short loc_14000FFC1
0x14000ff92  cmp     dword ptr [rax+38h], 2
0x14000ff96  jl      short loc_14000FFC1
0x14000ff98  mov     [rbp+var_18], rdi
0x14000ff9c  mov     [rbp+var_10], 408h
0x14000ffa3  mov     [rbp+var_C], 2
0x14000ffaa  mov     [rbp+var_8], rsi
0x14000ffae  mov     r8, r15
0x14000ffb1  lea     rdx, aFailedToRegist_5; "Failed to register service WMI provider"...
0x14000ffb8  lea     rcx, [rbp+var_18]
0x14000ffbc  call    ??$DbgPrint@GVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStatus>(ushort const *,FrsStatus const &)
0x14000ffc1  lea     rcx, [rbp+arg_8]; struct FrsStatus **
0x14000ffc5  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x14000ffca  mov     r15, [rbp+arg_8]
0x14000ffce  mov     rcx, r12; this
0x14000ffd1  call    ?StartTasks@ServiceConfig@@QEAAXXZ; ServiceConfig::StartTasks(void)
0x14000ffd6  cmp     [r13+10h], r14d
0x14000ffda  jnz     short loc_14000FF68
0x14000ffdc  mov     rsi, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x14000ffe3  cmp     [rsi], r14d
0x14000ffe6  jz      short loc_140010040
0x14000ffe8  lea     rdi, [rsi+0B8h]
0x14000ffef  mov     rcx, rdi; lpCriticalSection
0x14000fff2  call    cs:__imp_EnterCriticalSection
0x14000fff9  nop     dword ptr [rax+rax+00h]
0x14000fffe  mov     eax, 1
0x140010003  mov     [rsi+0B0h], eax
0x140010009  mov     [rsi+68h], eax
0x14001000c  lea     rcx, [rsi+40h]; lpSystemTimeAsFileTime
0x140010010  call    cs:__imp_GetSystemTimeAsFileTime
  ... truncated ...
```
