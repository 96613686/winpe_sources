# ConfigMonitorTask::Step(void)

- ea: `0x140039910`
- end: `0x14003a62b`
- name: `?Step@ConfigMonitorTask@@MEAA?AW4STEP_RESULT@Task@@XZ`
- size: `3355`
- prototype: ``
- caller_count: `0`
- callee_count: `49`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1400036a0`
- `0x14000c910`
- `0x14000cb00`
- `0x14000cdc0`
- `0x14000d980`
- `0x14000dcc0`
- `0x14000dfa0`
- `0x14000e34c`
- `0x14000ea50`
- `0x14001b6dc`
- `0x14001bf80`
- `0x14001bfb0`
- `0x14001c030`
- `0x14001c480`
- `0x14001d00c`
- `0x14001dd04`
- `0x14002018c`
- `0x140021294`
- `0x140021ad0`
- `0x140021c94`
- `0x1400390d4`
- `0x1400391c4`
- `0x1400394a4`
- `0x1400394d4`
- `0x140039504`
- `0x140039564`
- `0x140039590`
- `0x140039624`
- `0x14003980c`
- `0x1400398bc`
- `0x140039910`
- `0x1400c2df0`
- `0x1400e839c`
- `0x1400e8e1c`
- `0x1400ebff4`
- `0x1400ed504`
- `0x1400ed7b8`
- `0x1400f81b4`
- `0x1400ff3ec`
- `0x1401b3a04`
- `0x1401b5e7c`
- `0x1401b9494`
- `0x1401bda10`
- `0x1401bf49c`
- `0x1401bf504`
- `0x1401bf590`
- `0x1401cd5ac`
- `0x1401fc134`
- `0x140223010`

## import_xrefs

- `KERNEL32!WaitForMultipleObjects` at `0x140039ae2`
- `KERNEL32!WaitForMultipleObjects` at `0x140039ae2`
- `KERNEL32!GetLastError` at `0x140039b2a`
- `KERNEL32!GetLastError` at `0x140039b2a`
- `KERNEL32!GetCurrentThreadId` at `0x140039b1c`
- `KERNEL32!GetCurrentThreadId` at `0x140039b1c`

## string_xrefs

- `0x14003997a`: `ConfigMonitorTask::Step`
- `0x140039cd5`: `ConfigMonitorTask::Step`
- `0x140039d99`: `ConfigMonitorTask::Step`
- `0x140039e34`: `ConfigMonitorTask::Step`
- `0x140039ef8`: `ConfigMonitorTask::Step`
- `0x140039f63`: `ConfigMonitorTask::Step`
- `0x14003a088`: `ConfigMonitorTask::Step`
- `0x14003a195`: `ConfigMonitorTask::Step`
- `0x140039aa6`: `Entering configuration monitoring thread`
- `0x14003a1e3`: `Received %d Machine configuration events`
- `0x14003a0d6`: `Received %d AD Poll configuration events`
- `0x140039c23`: `[CLUSTER] The service is shutting down. Ignoring pending cluster config events`
- `0x140039d0e`: `Received %d cluster configuration events`
- `0x140039f35`: `[CLUSTER] Request to bring content set online has been canceled by a more recent request to bring the content set offline. res:%? csId:%? rgId:%? volId:%?`
- `0x140039e71`: `[CLUSTER] Request to bring content set offline has been canceled by a more recent request to bring the content set online. res:%? csId:%? rgId:%? volId:%?`
- `0x140039fad`: `[CLUSTER] Processing of remaining %d cluster configuration events canceled by shutdown`
- `0x140039b47`: `ConfigMonitorTask::Step`
- `0x140039b53`: `base\fs\remotefs\frs\src\main\configmonitortask.cpp`
- `0x140039bbb`: `Failed to wait for configuration events. Error:%?`
- `0x14003a379`: `Failed to connect to the DFSR read only minifilter. Error:%?`
- `0x14003a5de`: `Exiting configuration monitoring task. error:%?`
- `0x14003a596`: `Exiting configuration monitoring task`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ConfigMonitorTask::Step(__int64 a1)
{
  unsigned int v2; // r14d
  __int64 v3; // r13
  int v4; // r12d
  struct FrsStatus *v5; // rax
  TimeoutCounter *v6; // rcx
  struct FrsStatus *started; // rbx
  DWORD v8; // eax
  FrsService *v9; // rcx
  DWORD CurrentThreadId; // ebx
  DWORD LastError; // eax
  unsigned int j; // esi
  __int64 v13; // rdi
  __int64 v14; // rsi
  LPCRITICAL_SECTION v15; // rcx
  const struct _GUID *v16; // rdi
  __int64 v17; // rdi
  unsigned int i; // esi
  unsigned int n; // esi
  __int64 v20; // rcx
  FrsFilter *v21; // rcx
  unsigned int v22; // eax
  TimeoutCounter *v23; // rcx
  VolumeManager **k; // rbx
  RefCountObject **m; // rbx
  RefCountObject *v27; // [rsp+58h] [rbp-B0h] BYREF
  struct FrsStatus *v28; // [rsp+60h] [rbp-A8h] BYREF
  const wchar_t *v29; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v30; // [rsp+70h] [rbp-98h]
  const wchar_t *v31; // [rsp+78h] [rbp-90h]
  int v32; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v33[8]; // [rsp+88h] [rbp-80h] BYREF
  __int64 v34; // [rsp+90h] [rbp-78h] BYREF
  __int64 v35; // [rsp+98h] [rbp-70h]
  int v36; // [rsp+B0h] [rbp-58h] BYREF
  union _LARGE_INTEGER v37; // [rsp+B8h] [rbp-50h] BYREF
  union _LARGE_INTEGER v38; // [rsp+C0h] [rbp-48h] BYREF
  const wchar_t *v39; // [rsp+C8h] [rbp-40h] BYREF
  int v40; // [rsp+D0h] [rbp-38h]
  int v41; // [rsp+D4h] [rbp-34h]
  const wchar_t *v42; // [rsp+D8h] [rbp-30h]
  const wchar_t *v43; // [rsp+E0h] [rbp-28h] BYREF
  int v44; // [rsp+E8h] [rbp-20h]
  int v45; // [rsp+ECh] [rbp-1Ch]
  const wchar_t *v46; // [rsp+F0h] [rbp-18h]
  __int64 v47; // [rsp+F8h] [rbp-10h]
  const wchar_t *v48; // [rsp+100h] [rbp-8h] BYREF
  int v49; // [rsp+108h] [rbp+0h]
  int v50; // [rsp+10Ch] [rbp+4h]
  const wchar_t *v51; // [rsp+110h] [rbp+8h]
  const wchar_t *v52; // [rsp+118h] [rbp+10h] BYREF
  int v53; // [rsp+120h] [rbp+18h]
  int v54; // [rsp+124h] [rbp+1Ch]
  const wchar_t *v55; // [rsp+128h] [rbp+20h]
  const wchar_t *v56; // [rsp+130h] [rbp+28h] BYREF
  int v57; // [rsp+138h] [rbp+30h]
  int v58; // [rsp+13Ch] [rbp+34h]
  const wchar_t *v59; // [rsp+140h] [rbp+38h]
  const wchar_t *v60; // [rsp+148h] [rbp+40h] BYREF
  int v61; // [rsp+150h] [rbp+48h]
  int v62; // [rsp+154h] [rbp+4Ch]
  const wchar_t *v63; // [rsp+158h] [rbp+50h]
  const wchar_t *v64; // [rsp+160h] [rbp+58h] BYREF
  int v65; // [rsp+168h] [rbp+60h]
  int v66; // [rsp+16Ch] [rbp+64h]
  const wchar_t *v67; // [rsp+170h] [rbp+68h]
  const wchar_t *v68; // [rsp+178h] [rbp+70h] BYREF
  int v69; // [rsp+180h] [rbp+78h]
  int v70; // [rsp+184h] [rbp+7Ch]
  const wchar_t *v71; // [rsp+188h] [rbp+80h]
  _BYTE v72[8]; // [rsp+190h] [rbp+88h] BYREF
  _BYTE v73[8]; // [rsp+198h] [rbp+90h] BYREF
  _BYTE v74[8]; // [rsp+1A0h] [rbp+98h] BYREF
  _BYTE v75[8]; // [rsp+1A8h] [rbp+A0h] BYREF
  _BYTE v76[16]; // [rsp+1B0h] [rbp+A8h] BYREF
  _BYTE v77[16]; // [rsp+1C0h] [rbp+B8h] BYREF
  HANDLE Handles[3]; // [rsp+1D0h] [rbp+C8h] BYREF

  v2 = 0;
  v37.QuadPart = 0;
  TimeoutCounter::InitializeHighPerfCounters();
  v38.QuadPart = 0;
  TimeoutCounter::InitializeHighPerfCounters();
  v3 = *(_QWORD *)(a1 + 168);
  v47 = v3;
  v4 = 0;
  v5 = Migration::SysVolUtil::IsLocalComputerDomainJoined();
  v28 = v5;
  if ( v5 && *((_DWORD *)v5 + 1) == 9551 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v43 = L"ConfigMonitorTask::Step";
      v44 = 125;
      v45 = 2;
      v46 = L"SCFG";
      dbgobj::DbgPrint<unsigned short,FrsStatus>(
        &v43,
        L"Local machine is not joined to any domain. Scheduling MarkAndSweepUninitializedVolumes. Error:%?",
        v5);
    }
    FrsReplicator::MarkAndSweepUninitializedVolumes(*(FrsReplicator **)(*(_QWORD *)(a1 + 168) + 744LL));
  }
  CLEAR_ERROR(&v28);
  (***(void (__fastcall ****)(_QWORD, __int64))(a1 + 168))(*(_QWORD *)(a1 + 168), 1);
  if ( dword_1403167F8 )
  {
    ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets(*(ServiceConfig **)(a1 + 168));
    v6 = *(TimeoutCounter **)(*(_QWORD *)(a1 + 168) + 744LL);
    *((_DWORD *)v6 + 128) = 1;
  }
  if ( Settings::GhostingEnabled )
    TimeoutCounter::Sample(v6, &v37);
  TimeoutCounter::Sample(v6, &v38);
  Handles[0] = *(HANDLE *)(v3 + 144);
  Handles[1] = *(HANDLE *)(v3 + 504);
  Handles[2] = *(HANDLE *)(v3 + 624);
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v48 = L"ConfigMonitorTask::Step";
    v49 = 194;
    v50 = 5;
    v51 = L"SCFG";
    dbgobj::DbgPrint<unsigned short>(&v48, L"Entering configuration monitoring thread");
  }
  started = v28;
  if ( !v28 )
  {
    while ( 1 )
    {
      if ( *(_DWORD *)(a1 + 48) )
      {
LABEL_129:
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v39 = L"ConfigMonitorTask::Step";
          v40 = 568;
          v41 = 5;
          v42 = L"SCFG";
          dbgobj::DbgPrint<unsigned short>(&v39, L"Exiting configuration monitoring task");
        }
        return 0;
      }
      v8 = WaitForMultipleObjects(3u, Handles, 0, 0x3E8u);
      if ( !v8 )
        break;
      switch ( v8 )
      {
        case 1u:
          started = FrsService::ActivateService(v9);
          v28 = started;
          if ( !started )
          {
            Task::Schedule(*(Task **)(*((_QWORD *)g_FrsService + 167) + 504LL));
            PtrList<Config::AdPollEventRecord>::PtrList<Config::AdPollEventRecord>(v33);
            ScopedLock::ScopedLock((ScopedLock *)v77, (struct ScopedCS *)(v3 + 408));
            for ( i = 0; i < (unsigned int)((__int64)(*(_QWORD *)(v3 + 480) - *(_QWORD *)(v3 + 472)) >> 3); ++i )
            {
              v27 = *(RefCountObject **)std::vector<ShutdownObject *>::at(v3 + 472, i);
              std::vector<ReplicaSetManager *>::push_back(&v34, &v27);
            }
            std::vector<VolumeId *>::clear(v3 + 472);
            ScopedLock::~ScopedLock((ScopedLock *)v77);
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
            {
              v29 = L"ConfigMonitorTask::Step";
              v30 = 0x40000010DLL;
              v31 = L"SCFG";
              LODWORD(v27) = (v35 - v34) >> 3;
              dbgobj::DbgPrint<unsigned short,unsigned int>(&v29, L"Received %d AD Poll configuration events", &v27);
            }
            ServiceConfig::ProcessAdPollConfigEvents(*(ServiceConfig **)(a1 + 168));
            PtrList<Config::AdPollEventRecord>::~PtrList<Config::AdPollEventRecord>(v33);
          }
          goto LABEL_81;
        case 2u:
          started = FrsService::ActivateService(v9);
          v28 = started;
          if ( started )
          {
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
            {
              v56 = L"ConfigMonitorTask::Step";
              v57 = 287;
              v58 = 4;
              v59 = L"SCFG";
              dbgobj::DbgPrint<unsigned short>(
                &v56,
                L"[CLUSTER] The service is shutting down. Ignoring pending cluster config events");
            }
            goto LABEL_81;
          }
          PtrList<Config::ClusterConfigEventRecord>::PtrList<Config::ClusterConfigEventRecord>(v33);
          ScopedLock::ScopedLock((ScopedLock *)v76, (struct ScopedCS *)(v3 + 528));
          for ( j = 0; j < (unsigned int)((__int64)(*(_QWORD *)(v3 + 600) - *(_QWORD *)(v3 + 592)) >> 3); ++j )
          {
            v27 = *(RefCountObject **)std::vector<ShutdownObject *>::at(v3 + 592, j);
            std::vector<ReplicaSetManager *>::push_back(&v34, &v27);
          }
          std::vector<VolumeId *>::clear(v3 + 592);
          ScopedLock::~ScopedLock((ScopedLock *)v76);
          v13 = v35;
          v14 = v34;
          v15 = g_DebugLog;
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            v29 = L"ConfigMonitorTask::Step";
            v30 = 0x40000012ALL;
            v31 = L"SCFG";
            v36 = (v35 - v34) >> 3;
            dbgobj::DbgPrint<unsigned short,unsigned int>(&v29, L"Received %d cluster configuration events", &v36);
            v15 = g_DebugLog;
          }
          while ( 2 )
          {
            if ( *(_DWORD *)(a1 + 48) || v2 >= (unsigned int)((v13 - v14) >> 3) )
            {
              v17 = (v13 - v14) >> 3;
              if ( v2 != (_DWORD)v17 && v15 && LODWORD(v15[1].LockSemaphore) && SLODWORD(v15[1].OwningThread) >= 4 )
              {
                v29 = L"ConfigMonitorTask::Step";
                v30 = 0x40000019CLL;
                v31 = L"SCFG";
                LODWORD(v27) = v17 - v2;
                dbgobj::DbgPrint<unsigned short,unsigned int>(
                  &v29,
                  L"[CLUSTER] Processing of remaining %d cluster configuration events canceled by shutdown",
                  &v27);
              }
              PtrList<Config::ClusterConfigEventRecord>::~PtrList<Config::ClusterConfigEventRecord>(v33);
              v2 = 0;
              goto LABEL_81;
            }
            v16 = *(const struct _GUID **)std::vector<ShutdownObject *>::at(&v34, v2);
            v32 = 6;
            FrsReplicator::ContentSetStatusMap::Get(
              (FrsReplicator::ContentSetStatusMap *)(*((_QWORD *)g_FrsService + 167) + 520LL),
              v16 + 1,
              (enum FrsReplicator::ContentSetStatus *)&v32);
            v15 = g_DebugLog;
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
            {
              v60 = L"ConfigMonitorTask::Step";
              v61 = 345;
              v62 = 4;
              v63 = L"SCFG";
              dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,_GUID,_GUID,enum Config::ClusterConfigEventRecord::EventType,enum FrsReplicator::ContentSetStatus>(
                (unsigned int)&v60,
                (unsigned int)&v32,
                (_DWORD)v16 + 8,
                (_DWORD)v16 + 16,
                (__int64)&v16[2],
                (__int64)&v16[3],
                (__int64)v16,
                (__int64)&v32);
              v15 = g_DebugLog;
            }
            if ( v16->Data1 == 1 )
            {
              if ( v32 == 5 )
              {
                FrsReplicator::BringContentSetOnline(
                  *((FrsReplicator **)g_FrsService + 167),
                  v16->Data4,
                  v16 + 1,
                  v16 + 2,
                  (struct _GUID *)&v16[3]);
              }
              else
              {
                if ( !v15 || !LODWORD(v15[1].LockSemaphore) || SLODWORD(v15[1].OwningThread) < 4 )
                  goto LABEL_58;
                v39 = L"ConfigMonitorTask::Step";
                v40 = 368;
                v41 = 4;
                v42 = L"SCFG";
                dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,_GUID,_GUID>(
                  (unsigned int)&v39,
                  (unsigned int)L"[CLUSTER] Request to bring content set online has been canceled by a more recent request"
                                 " to bring the content set offline. res:%? csId:%? rgId:%? volId:%?",
                  (_DWORD)v16 + 8,
                  (_DWORD)v16 + 16,
                  (__int64)&v16[2],
                  (__int64)&v16[3]);
              }
            }
            else
            {
              if ( v16->Data1 != 2 )
                goto LABEL_58;
              if ( ((v32 - 2) & 0xFFFFFFFB) != 0 )
              {
                if ( v15 && LODWORD(v15[1].LockSemaphore) && SLODWORD(v15[1].OwningThread) >= 4 )
                {
                  v64 = L"ConfigMonitorTask::Step";
                  v65 = 390;
                  v66 = 4;
                  v67 = L"SCFG";
                  dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,_GUID,_GUID>(
                    (unsigned int)&v64,
                    (unsigned int)L"[CLUSTER] Request to bring content set offline has been canceled by a more recent requ"
                                   "est to bring the content set online. res:%? csId:%? rgId:%? volId:%?",
                    (_DWORD)v16 + 8,
                    (_DWORD)v16 + 16,
                    (__int64)&v16[2],
                    (__int64)&v16[3]);
                  break;
                }
LABEL_58:
                ++v2;
                v13 = v35;
                v14 = v34;
                continue;
              }
              FrsReplicator::BringContentSetOffline(
                *((_QWORD *)g_FrsService + 167),
                v16->Data4,
                &v16[1],
                &v16[2],
                &v16[3],
                0);
            }
            break;
          }
          v15 = g_DebugLog;
          goto LABEL_58;
        case 0xFFFFFFFF:
          CurrentThreadId = GetCurrentThreadId();
          LastError = GetLastError();
          started = (struct FrsStatus *)FrsStatusList::PushNewError(
                                          "base\\fs\\remotefs\\frs\\src\\main\\configmonitortask.cpp",
                                          LastError,
                                          0,
                                          1,
                                          "base\\fs\\remotefs\\frs\\src\\main\\configmonitortask.cpp",
                                          "ConfigMonitorTask::Step",
                                          423,
                                          CurrentThreadId,
                                          0);
          v28 = started;
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
          {
            v52 = L"ConfigMonitorTask::Step";
            v53 = 424;
            v54 = 2;
            v55 = L"SCFG";
            dbgobj::DbgPrint<unsigned short,FrsStatus>(
              &v52,
              L"Failed to wait for configuration events. Error:%?",
              started);
          }
          goto LABEL_81;
      }
LABEL_82:
      if ( *(_DWORD *)(a1 + 48) )
        goto LABEL_129;
      if ( Settings::GhostingEnabled
        && (unsigned int)FrsService::IsActivated(v9)
        && (unsigned int)TimeoutCounter::OlderThan((TimeoutCounter *)&v37, 0xEA60u) )
      {
        TimeoutCounter::Sample(v9, &v37);
        started = FrsFilter::StartProcessingMessages(v21);
        v28 = started;
        if ( started )
        {
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
          {
            v29 = L"ConfigMonitorTask::Step";
            v30 = 0x5000001C8LL;
            v31 = L"SCFG";
            dbgobj::DbgPrint<unsigned short,FrsStatus>(
              &v29,
              L"Failed to connect to the FRS ghosting minifilter. Error:%?",
              started);
          }
          CLEAR_ERROR(&v28);
          started = v28;
        }
        if ( started )
          goto LABEL_133;
      }
      if ( *(_DWORD *)(a1 + 48) )
        goto LABEL_129;
      if ( (unsigned int)FrsService::IsActivated(v9) )
      {
        v22 = Settings::GenericDwordSetting::operator()(&Settings::ConfigCheckReadOnlyDriverLoadedWaitTime);
        if ( (unsigned int)TimeoutCounter::OlderThan((TimeoutCounter *)&v38, v22) )
        {
          TimeoutCounter::Sample(v23, &v38);
          if ( v4 || !(unsigned int)FrsReadOnlyFilter::IsCommunicationPortValid(g_FrsReadOnlyFilter) )
          {
            started = (struct FrsStatus *)(*(__int64 (__fastcall **)(FrsReadOnlyFilter *))(*(_QWORD *)g_FrsReadOnlyFilter
                                                                                         + 64LL))(g_FrsReadOnlyFilter);
            v28 = started;
            if ( started )
            {
              if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
              {
                v29 = L"ConfigMonitorTask::Step";
                v30 = 0x5000001EELL;
                v31 = L"SCFG";
                dbgobj::DbgPrint<unsigned short,FrsStatus>(
                  &v29,
                  L"Failed to connect to the DFSR read only minifilter. Error:%?",
                  started);
              }
              CLEAR_ERROR(&v28);
              if ( v4 )
              {
                started = v28;
              }
              else
              {
                RefList<VolumeManager>::RefList<VolumeManager>(v33);
                v4 = 1;
                if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugVolumeManagerRefCount)
                  && g_DebugLog
                  && LODWORD(g_DebugLog[1].LockSemaphore)
                  && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
                {
                  v29 = L"ConfigMonitorTask::Step";
                  v30 = 0x500000208LL;
                  v31 = L"SCFG";
                  dbgobj::DbgPrint<unsigned short>(&v29, L"[VMREF] Getting all volume managers");
                }
                VolumeManagerMap::GetAllVolumes(*((_QWORD *)g_FrsService + 167) + 8LL, v33);
                for ( k = *(VolumeManager ***)RefList<VolumeManager>::Begin(v33, v72);
                      k != *(VolumeManager ***)RefList<ContentSetManager>::End(v33, v73);
                      ++k )
                {
                  VolumeManager::RestartOnlineReadOnlyContentSets(*k);
                }
                for ( m = *(RefCountObject ***)RefList<VolumeManager>::Begin(v33, v74);
                      m != *(RefCountObject ***)RefList<ContentSetManager>::End(v33, v75);
                      ++m )
                {
                  if ( *m )
                  {
                    if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugVolumeManagerRefCount)
                      && g_DebugLog
                      && LODWORD(g_DebugLog[1].LockSemaphore)
                      && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
                    {
                      v29 = L"ConfigMonitorTask::Step";
                      v30 = 0x50000020ELL;
                      v31 = L"SCFG";
                      v27 = *m;
                      dbgobj::DbgPrint<unsigned short,unsigned __int64>(
                        &v29,
                        L"[VMREF] Release reference to volume manager. ptr:%p",
                        &v27);
                    }
                    RefCountObject::Release(*m);
                  }
                }
                std::vector<VolumeId *>::clear(&v34);
                RefList<VolumeManager>::~RefList<VolumeManager>(v33);
                started = v28;
                v3 = v47;
              }
            }
            else
            {
              FrsReplicator::MarkAndSweepReadOnlyContentSetsFromDriver(*((FrsReplicator **)g_FrsService + 167));
              v4 = 0;
            }
            if ( started )
              goto LABEL_133;
          }
        }
      }
      if ( *(_DWORD *)(a1 + 48) )
        goto LABEL_129;
      if ( (unsigned int)ServiceConfig::DsPollIsDue(*(ServiceConfig **)(a1 + 168)) )
        ServiceConfig::PollDs(*(ServiceConfig **)(a1 + 168));
    }
    started = FrsService::ActivateService(v9);
    v28 = started;
    if ( !started )
    {
      PtrList<Config::MachineEventRecord>::PtrList<Config::MachineEventRecord>(v33);
      ScopedLock::ScopedLock((ScopedLock *)&v43, (struct ScopedCS *)(v3 + 48));
      for ( n = 0; n < (unsigned int)((__int64)(*(_QWORD *)(v3 + 120) - *(_QWORD *)(v3 + 112)) >> 3); ++n )
      {
        v27 = *(RefCountObject **)std::vector<ShutdownObject *>::at(v3 + 112, n);
        std::vector<ReplicaSetManager *>::push_back(&v34, &v27);
      }
      std::vector<VolumeId *>::clear(v3 + 112);
      ScopedLock::~ScopedLock((ScopedLock *)&v43);
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v29 = L"ConfigMonitorTask::Step";
        v30 = 0x4000000F3LL;
        v31 = L"SCFG";
        LODWORD(v27) = (v35 - v34) >> 3;
        dbgobj::DbgPrint<unsigned short,unsigned int>(&v29, L"Received %d Machine configuration events", &v27);
      }
      BaseServiceConfig::ProcessMachineConfigEvents(v20, v33);
      PtrList<Config::MachineEventRecord>::~PtrList<Config::MachineEventRecord>(v33);
    }
LABEL_81:
    if ( started )
      goto LABEL_133;
    goto LABEL_82;
  }
LABEL_133:
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v68 = L"ConfigMonitorTask::Step";
    v69 = 564;
    v70 = 5;
    v71 = L"SCFG";
    dbgobj::DbgPrint<unsigned short,FrsStatus>(&v68, L"Exiting configuration monitoring task. error:%?", started);
  }
  CLEAR_ERROR(&v28);
  return 0;
}

```

## disassembly

```asm
0x140039910  mov     rax, rsp
0x140039913  mov     [rax+10h], rbx
0x140039917  mov     [rax+18h], rsi
0x14003991b  mov     [rax+20h], rdi
0x14003991f  push    rbp
0x140039920  push    r12
0x140039922  push    r13
0x140039924  push    r14
0x140039926  push    r15
0x140039928  lea     rbp, [rax-118h]
0x14003992f  sub     rsp, 1F0h
0x140039936  mov     rax, cs:__security_cookie
0x14003993d  xor     rax, rsp
0x140039940  mov     [rbp+110h+var_30], rax
0x140039947  mov     r15, rcx
0x14003994a  xor     r14d, r14d
0x14003994d  mov     qword ptr [rbp+110h+var_160], r14
0x140039951  call    ?InitializeHighPerfCounters@TimeoutCounter@@SAXXZ; TimeoutCounter::InitializeHighPerfCounters(void)
0x140039956  mov     qword ptr [rbp+110h+var_158], r14
0x14003995a  call    ?InitializeHighPerfCounters@TimeoutCounter@@SAXXZ; TimeoutCounter::InitializeHighPerfCounters(void)
0x14003995f  mov     r13, [r15+0A8h]
0x140039966  mov     [rbp+110h+var_120], r13
0x14003996a  mov     r12d, r14d
0x14003996d  call    ?IsLocalComputerDomainJoined@SysVolUtil@Migration@@SAPEAVFrsStatus@@XZ; Migration::SysVolUtil::IsLocalComputerDomainJoined(void)
0x140039972  mov     r8, rax
0x140039975  mov     [rsp+210h+var_1B8], rax
0x14003997a  lea     rsi, aConfigmonitort; "ConfigMonitorTask::Step"
0x140039981  lea     rbx, aScfg; "SCFG"
0x140039988  test    rax, rax
0x14003998b  jz      short loc_1400399E7
0x14003998d  cmp     dword ptr [rax+4], 254Fh
0x140039994  jnz     short loc_1400399E7
0x140039996  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14003999d  test    rax, rax
0x1400399a0  jz      short loc_1400399D4
0x1400399a2  cmp     [rax+40h], r14d
0x1400399a6  jz      short loc_1400399D4
0x1400399a8  cmp     dword ptr [rax+38h], 2
0x1400399ac  jl      short loc_1400399D4
0x1400399ae  mov     [rbp+110h+var_138], rsi
0x1400399b2  mov     [rbp+110h+var_130], 7Dh ; '}'
0x1400399b9  mov     [rbp+110h+var_12C], 2
0x1400399c0  mov     [rbp+110h+var_128], rbx
0x1400399c4  lea     rdx, aLocalMachineIs; "Local machine is not joined to any doma"...
0x1400399cb  lea     rcx, [rbp+110h+var_138]
0x1400399cf  call    ??$DbgPrint@GVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStatus>(ushort const *,FrsStatus const &)
0x1400399d4  mov     rcx, [r15+0A8h]
0x1400399db  mov     rcx, [rcx+2E8h]; this
0x1400399e2  call    ?MarkAndSweepUninitializedVolumes@FrsReplicator@@QEAAXXZ; FrsReplicator::MarkAndSweepUninitializedVolumes(void)
0x1400399e7  lea     rcx, [rsp+210h+var_1B8]; struct FrsStatus **
0x1400399ec  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1400399f1  mov     rcx, [r15+0A8h]
0x1400399f8  mov     rax, [rcx]
0x1400399fb  mov     edi, 1
0x140039a00  mov     edx, edi
0x140039a02  mov     rax, [rax]
0x140039a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039a0a  cmp     cs:dword_1403167F8, r14d
0x140039a11  jz      short loc_140039A33
0x140039a13  mov     rcx, [r15+0A8h]; this
0x140039a1a  call    ?BootstrapOnlineAndOnlinePendingContentSets@ServiceConfig@@IEAAXXZ; ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets(void)
0x140039a1f  mov     rax, [r15+0A8h]
0x140039a26  mov     rcx, [rax+2E8h]; this
0x140039a2d  mov     [rcx+200h], edi
0x140039a33  cmp     cs:?GhostingEnabled@Settings@@3VGenericBoolSetting@1@A, r14d; Settings::GenericBoolSetting Settings::GhostingEnabled
0x140039a3a  jz      short loc_140039A45
0x140039a3c  lea     rdx, [rbp+110h+var_160]; union _LARGE_INTEGER *
0x140039a40  call    ?Sample@TimeoutCounter@@AEAAXPEAT_LARGE_INTEGER@@@Z; TimeoutCounter::Sample(_LARGE_INTEGER *)
0x140039a45  lea     rdx, [rbp+110h+var_158]; union _LARGE_INTEGER *
0x140039a49  call    ?Sample@TimeoutCounter@@AEAAXPEAT_LARGE_INTEGER@@@Z; TimeoutCounter::Sample(_LARGE_INTEGER *)
0x140039a4e  mov     rax, [r13+90h]
0x140039a55  mov     [rbp+110h+Handles], rax
0x140039a5c  mov     rax, [r13+1F8h]
0x140039a63  mov     [rbp+110h+var_40], rax
0x140039a6a  mov     rax, [r13+270h]
0x140039a71  mov     [rbp+110h+var_38], rax
0x140039a78  mov     edi, 5
0x140039a7d  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140039a84  test    rax, rax
0x140039a87  jz      short loc_140039AB6
0x140039a89  cmp     [rax+40h], r14d
0x140039a8d  jz      short loc_140039AB6
0x140039a8f  cmp     [rax+38h], edi
0x140039a92  jl      short loc_140039AB6
0x140039a94  mov     [rbp+110h+var_118], rsi
0x140039a98  mov     [rbp+110h+var_110], 0C2h
0x140039a9f  mov     [rbp+110h+var_10C], edi
0x140039aa2  mov     [rbp+110h+var_108], rbx
0x140039aa6  lea     rdx, aEnteringConfig; "Entering configuration monitoring threa"...
0x140039aad  lea     rcx, [rbp+110h+var_118]
0x140039ab1  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140039ab6  mov     rbx, [rsp+210h+var_1B8]
0x140039abb  test    rbx, rbx
0x140039abe  jnz     loc_14003A5A8
0x140039ac4  cmp     [r15+30h], r14d
0x140039ac8  jnz     loc_14003A55E
0x140039ace  mov     r9d, 3E8h; dwMilliseconds
0x140039ad4  xor     r8d, r8d; bWaitAll
0x140039ad7  lea     rdx, [rbp+110h+Handles]; lpHandles
0x140039ade  lea     ecx, [r8+3]; nCount
0x140039ae2  call    cs:__imp_WaitForMultipleObjects
0x140039ae9  nop     dword ptr [rax+rax+00h]
0x140039aee  test    eax, eax
0x140039af0  jz      loc_14003A106
0x140039af6  cmp     eax, 1
0x140039af9  jz      loc_140039FD0
0x140039aff  cmp     eax, 2
0x140039b02  jz      loc_140039BD0
0x140039b08  cmp     eax, 102h
0x140039b0d  jz      loc_14003A215
0x140039b13  cmp     eax, 0FFFFFFFFh
0x140039b16  jnz     loc_14003A215
0x140039b1c  call    cs:__imp_GetCurrentThreadId
0x140039b23  nop     dword ptr [rax+rax+00h]
0x140039b28  mov     ebx, eax
0x140039b2a  call    cs:__imp_GetLastError
0x140039b31  nop     dword ptr [rax+rax+00h]
0x140039b36  mov     [rsp+210h+var_1D0], r14
0x140039b3b  mov     dword ptr [rsp+210h+var_1D8], ebx
0x140039b3f  mov     dword ptr [rsp+210h+var_1E0], 1A7h
0x140039b47  lea     rcx, aConfigmonitort_0; "ConfigMonitorTask::Step"
0x140039b4e  mov     [rsp+210h+var_1E8], rcx
0x140039b53  lea     rcx, aBaseFsRemotefs_69; "base\\fs\\remotefs\\frs\\src\\main\\con"...
0x140039b5a  mov     [rsp+210h+var_1F0], rcx
0x140039b5f  mov     r9d, 1
0x140039b65  xor     r8d, r8d
0x140039b68  mov     edx, eax
0x140039b6a  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140039b6f  mov     rbx, rax
0x140039b72  mov     [rsp+210h+var_1B8], rax
0x140039b77  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140039b7e  test    rax, rax
0x140039b81  jz      loc_14003A20C
0x140039b87  cmp     [rax+40h], r14d
0x140039b8b  jz      loc_14003A20C
0x140039b91  cmp     dword ptr [rax+38h], 2
0x140039b95  jl      loc_14003A20C
0x140039b9b  mov     [rbp+110h+var_100], rsi
0x140039b9f  mov     [rbp+110h+var_F8], 1A8h
0x140039ba6  mov     [rbp+110h+var_F4], 2
0x140039bad  lea     rax, aScfg; "SCFG"
0x140039bb4  mov     [rbp+110h+var_F0], rax
0x140039bb8  mov     r8, rbx
0x140039bbb  lea     rdx, aFailedToWaitFo; "Failed to wait for configuration events"...
0x140039bc2  lea     rcx, [rbp+110h+var_100]
0x140039bc6  call    ??$DbgPrint@GVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStatus>(ushort const *,FrsStatus const &)
0x140039bcb  jmp     loc_14003A20C
0x140039bd0  call    ?ActivateService@FrsService@@QEAAPEAVFrsStatus@@XZ; FrsService::ActivateService(void)
0x140039bd5  mov     rbx, rax
0x140039bd8  mov     [rsp+210h+var_1B8], rax
0x140039bdd  test    rax, rax
0x140039be0  jz      short loc_140039C38
0x140039be2  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140039be9  test    rax, rax
0x140039bec  jz      loc_14003A20C
0x140039bf2  cmp     [rax+40h], r14d
0x140039bf6  jz      loc_14003A20C
0x140039bfc  cmp     dword ptr [rax+38h], 4
0x140039c00  jl      loc_14003A20C
0x140039c06  mov     [rbp+110h+var_E8], rsi
0x140039c0a  mov     [rbp+110h+var_E0], 11Fh
0x140039c11  mov     [rbp+110h+var_DC], 4
0x140039c18  lea     rax, aScfg; "SCFG"
0x140039c1f  mov     [rbp+110h+var_D8], rax
0x140039c23  lea     rdx, aClusterTheServ; "[CLUSTER] The service is shutting down."...
0x140039c2a  lea     rcx, [rbp+110h+var_E8]
0x140039c2e  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140039c33  jmp     loc_14003A20C
0x140039c38  lea     rcx, [rbp+110h+var_190]
0x140039c3c  call    ??0?$PtrList@VClusterConfigEventRecord@Config@@@@QEAA@XZ; PtrList<Config::ClusterConfigEventRecord>::PtrList<Config::ClusterConfigEventRecord>(void)
0x140039c41  nop
0x140039c42  lea     rdx, [r13+210h]; struct ScopedCS *
0x140039c49  lea     rcx, [rbp+110h+var_68]; this
0x140039c50  call    ??0ScopedLock@@QEAA@AEAVScopedCS@@@Z; ScopedLock::ScopedLock(ScopedCS &)
0x140039c55  nop
0x140039c56  mov     esi, r14d
0x140039c59  lea     rdi, [r13+250h]
0x140039c60  mov     rax, [rdi+8]
0x140039c64  sub     rax, [rdi]
0x140039c67  sar     rax, 3
0x140039c6b  test    eax, eax
0x140039c6d  jz      short loc_140039CA0
0x140039c6f  mov     edx, esi
0x140039c71  mov     rcx, rdi
0x140039c74  call    ?at@?$vector@PEAVShutdownObject@@V?$allocator@PEAVShutdownObject@@@std@@@std@@QEAAAEAPEAVShutdownObject@@_K@Z; std::vector<ShutdownObject *>::at(unsigned __int64)
0x140039c79  mov     rcx, [rax]
0x140039c7c  mov     [rsp+210h+var_1C0], rcx
0x140039c81  lea     rdx, [rsp+210h+var_1C0]
0x140039c86  lea     rcx, [rbp+110h+var_188]
0x140039c8a  call    ?push_back@?$vector@PEAVReplicaSetManager@@V?$allocator@PEAVReplicaSetManager@@@std@@@std@@QEAAXAEBQEAVReplicaSetManager@@@Z; std::vector<ReplicaSetManager *>::push_back(ReplicaSetManager * const &)
0x140039c8f  inc     esi
0x140039c91  mov     rax, [rdi+8]
0x140039c95  sub     rax, [rdi]
0x140039c98  sar     rax, 3
0x140039c9c  cmp     esi, eax
0x140039c9e  jb      short loc_140039C6F
0x140039ca0  mov     rcx, rdi
0x140039ca3  call    ?clear@?$vector@PEAVVolumeId@@V?$allocator@PEAVVolumeId@@@std@@@std@@QEAAXXZ; std::vector<VolumeId *>::clear(void)
0x140039ca8  nop
0x140039ca9  lea     rcx, [rbp+110h+var_68]; this
0x140039cb0  call    ??1ScopedLock@@QEAA@XZ; ScopedLock::~ScopedLock(void)
0x140039cb5  mov     rdi, [rbp+110h+var_180]
0x140039cb9  mov     rsi, [rbp+110h+var_188]
0x140039cbd  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140039cc4  test    rcx, rcx
0x140039cc7  jz      short loc_140039D26
0x140039cc9  cmp     [rcx+40h], r14d
0x140039ccd  jz      short loc_140039D26
0x140039ccf  cmp     dword ptr [rcx+38h], 4
0x140039cd3  jl      short loc_140039D26
0x140039cd5  lea     rax, aConfigmonitort; "ConfigMonitorTask::Step"
0x140039cdc  mov     [rsp+210h+var_1B0], rax
0x140039ce1  mov     dword ptr [rsp+210h+var_1A8], 12Ah
0x140039ce9  mov     dword ptr [rsp+210h+var_1A8+4], 4
0x140039cf1  lea     rax, aScfg; "SCFG"
0x140039cf8  mov     [rsp+210h+var_1A0], rax
0x140039cfd  mov     rax, rdi
0x140039d00  sub     rax, rsi
0x140039d03  sar     rax, 3
0x140039d07  mov     [rbp+110h+var_168], eax
0x140039d0a  lea     r8, [rbp+110h+var_168]
0x140039d0e  lea     rdx, aReceivedDClust; "Received %d cluster configuration event"...
0x140039d15  lea     rcx, [rsp+210h+var_1B0]
0x140039d1a  call    ??$DbgPrint@GI@dbgobj@@QEAA_KPEBGAEBI@Z; dbgobj::DbgPrint<ushort,uint>(ushort const *,uint const &)
0x140039d1f  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140039d26  cmp     dword ptr [r15+30h], 0
0x140039d2b  jnz     loc_140039F5C
0x140039d31  mov     rax, rdi
0x140039d34  sub     rax, rsi
0x140039d37  sar     rax, 3
0x140039d3b  cmp     r14d, eax
0x140039d3e  jnb     loc_140039F5C
0x140039d44  mov     edx, r14d
0x140039d47  lea     rcx, [rbp+110h+var_188]
0x140039d4b  call    ?at@?$vector@PEAVShutdownObject@@V?$allocator@PEAVShutdownObject@@@std@@@std@@QEAAAEAPEAVShutdownObject@@_K@Z; std::vector<ShutdownObject *>::at(unsigned __int64)
0x140039d50  mov     rdi, [rax]
0x140039d53  mov     [rsp+210h+var_198], 6
0x140039d5b  mov     rax, cs:?g_FrsService@@3PEAVFrsService@@EA; FrsService * g_FrsService
0x140039d62  mov     rcx, [rax+538h]
0x140039d69  add     rcx, 208h; this
0x140039d70  lea     rsi, [rdi+10h]
0x140039d74  lea     r8, [rsp+210h+var_198]; enum FrsReplicator::ContentSetStatus *
0x140039d79  mov     rdx, rsi; struct _GUID *
0x140039d7c  call    ?Get@ContentSetStatusMap@FrsReplicator@@QEAAHAEBU_GUID@@AEAW4ContentSetStatus@2@@Z; FrsReplicator::ContentSetStatusMap::Get(_GUID const &,FrsReplicator::ContentSetStatus &)
0x140039d81  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140039d88  test    rcx, rcx
0x140039d8b  jz      short loc_140039DF5
0x140039d8d  cmp     dword ptr [rcx+40h], 0
0x140039d91  jz      short loc_140039DF5
0x140039d93  cmp     dword ptr [rcx+38h], 4
0x140039d97  jl      short loc_140039DF5
0x140039d99  lea     rax, aConfigmonitort; "ConfigMonitorTask::Step"
0x140039da0  mov     [rbp+110h+var_D0], rax
0x140039da4  mov     [rbp+110h+var_C8], 159h
0x140039dab  mov     [rbp+110h+var_C4], 4
0x140039db2  lea     rax, aScfg; "SCFG"
0x140039db9  mov     [rbp+110h+var_C0], rax
0x140039dbd  lea     rax, [rdi+30h]
0x140039dc1  lea     rcx, [rdi+20h]
0x140039dc5  lea     r8, [rdi+8]
0x140039dc9  lea     rdx, [rsp+210h+var_198]
0x140039dce  mov     [rsp+210h+var_1D8], rdx
0x140039dd3  mov     [rsp+210h+var_1E0], rdi
0x140039dd8  mov     [rsp+210h+var_1E8], rax
0x140039ddd  mov     [rsp+210h+var_1F0], rcx
0x140039de2  mov     r9, rsi
0x140039de5  lea     rcx, [rbp+110h+var_D0]
0x140039de9  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@U_GUID@@U2@U2@W4EventType@ClusterConfigEventRecord@Config@@W4ContentSetStatus@FrsReplicator@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@AEBU_GUID@@22AEBW4EventType@ClusterConfigEventRecord@Config@@AEBW4ContentSetStatus@FrsReplicator@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>,_GUID,_GUID,_GUID,Config::ClusterConfigEventRecord::EventType,FrsReplicator::ContentSetStatus>(ushort const *,FrsStringImpl<ushort,char> const &,_GUID const &,_GUID const &,_GUID const &,Config::ClusterConfigEventRecord::EventType const &,FrsReplicator::ContentSetStatus const &)
0x140039dee  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140039df5  mov     edx, [rdi]
0x140039df7  sub     edx, 1
0x140039dfa  jz      loc_140039EB7
0x140039e00  cmp     edx, 1
0x140039e03  jnz     loc_140039F4C
0x140039e09  mov     eax, [rsp+210h+var_198]
0x140039e0d  add     eax, 0FFFFFFFEh
0x140039e10  test    eax, 0FFFFFFFBh
0x140039e15  jz      short loc_140039E86
0x140039e17  test    rcx, rcx
0x140039e1a  jz      loc_140039F4C
0x140039e20  cmp     dword ptr [rcx+40h], 0
0x140039e24  jz      loc_140039F4C
0x140039e2a  cmp     dword ptr [rcx+38h], 4
0x140039e2e  jl      loc_140039F4C
0x140039e34  lea     rax, aConfigmonitort; "ConfigMonitorTask::Step"
0x140039e3b  mov     [rbp+110h+var_B8], rax
0x140039e3f  mov     [rbp+110h+var_B0], 186h
0x140039e46  mov     [rbp+110h+var_AC], 4
0x140039e4d  lea     rax, aScfg; "SCFG"
0x140039e54  mov     [rbp+110h+var_A8], rax
0x140039e58  lea     rax, [rdi+30h]
0x140039e5c  lea     rcx, [rdi+20h]
0x140039e60  lea     r8, [rdi+8]
0x140039e64  mov     [rsp+210h+var_1E8], rax
0x140039e69  mov     [rsp+210h+var_1F0], rcx
0x140039e6e  mov     r9, rsi
0x140039e71  lea     rdx, aClusterRequest_0; "[CLUSTER] Request to bring content set "...
0x140039e78  lea     rcx, [rbp+110h+var_B8]
0x140039e7c  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@U_GUID@@U2@U2@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@AEBU_GUID@@22@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>,_GUID,_GUID,_GUID>(ushort const *,FrsStringImpl<ushort,char> const &,_GUID const &,_GUID const &,_GUID const &)
0x140039e81  jmp     loc_140039F45
  ... truncated ...
```
