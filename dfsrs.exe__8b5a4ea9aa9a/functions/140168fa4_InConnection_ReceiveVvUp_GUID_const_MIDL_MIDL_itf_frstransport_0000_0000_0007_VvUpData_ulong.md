# InConnection::ReceiveVvUp(_GUID const &,__MIDL___MIDL_itf_frstransport_0000_0000_0007,VvUpData *,ulong)

- ea: `0x140168fa4`
- end: `0x140169e37`
- name: `?ReceiveVvUp@InConnection@@QEAAPEAVFrsStatus@@AEBU_GUID@@W4__MIDL___MIDL_itf_frstransport_0000_0000_0007@@PEAVVvUpData@@K@Z`
- size: `3731`
- prototype: ``
- caller_count: `1`
- callee_count: `52`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1401aa7c0`

## callees

- `0x1400036a0`
- `0x14000c910`
- `0x14000d980`
- `0x14000dcc0`
- `0x140011408`
- `0x140024ebc`
- `0x140024ed4`
- `0x140029390`
- `0x14002bf70`
- `0x14002c2f4`
- `0x14002c404`
- `0x1400370bc`
- `0x1400391c4`
- `0x140048370`
- `0x140069770`
- `0x14006a384`
- `0x14006a550`
- `0x14007dedc`
- `0x14007e63c`
- `0x140086dcc`
- `0x1400923f8`
- `0x1400925a8`
- `0x140111380`
- `0x14011bdec`
- `0x14015cd04`
- `0x14015da7c`
- `0x14015db48`
- `0x14015f6d0`
- `0x14015fd04`
- `0x140160c4c`
- `0x140160cbc`
- `0x140160e80`
- `0x1401625b4`
- `0x14016465c`
- `0x140164d64`
- `0x140164f10`
- `0x1401653ac`
- `0x140165a18`
- `0x140166220`
- `0x1401668d8`
- `0x140168fa4`
- `0x140169e74`
- `0x14016d480`
- `0x14016e43c`
- `0x14016e4dc`
- `0x140192320`
- `0x1401b324c`
- `0x1401b3a04`
- `0x1401b9494`
- `0x1401bda10`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x140169aaf`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140169aaf`
- `KERNEL32!LeaveCriticalSection` at `0x140169a46`
- `KERNEL32!LeaveCriticalSection` at `0x140169be6`
- `KERNEL32!LeaveCriticalSection` at `0x140169d8d`
- `KERNEL32!LeaveCriticalSection` at `0x140169a46`
- `KERNEL32!LeaveCriticalSection` at `0x140169be6`
- `KERNEL32!LeaveCriticalSection` at `0x140169d8d`
- `KERNEL32!EnterCriticalSection` at `0x14016999d`
- `KERNEL32!EnterCriticalSection` at `0x140169ade`
- `KERNEL32!EnterCriticalSection` at `0x140169c69`
- `KERNEL32!EnterCriticalSection` at `0x14016999d`
- `KERNEL32!EnterCriticalSection` at `0x140169ade`
- `KERNEL32!EnterCriticalSection` at `0x140169c69`
- `KERNEL32!GetCurrentThreadId` at `0x1401690f8`
- `KERNEL32!GetCurrentThreadId` at `0x14016922e`
- `KERNEL32!GetCurrentThreadId` at `0x140169240`
- `KERNEL32!GetCurrentThreadId` at `0x140169285`
- `KERNEL32!GetCurrentThreadId` at `0x140169460`
- `KERNEL32!GetCurrentThreadId` at `0x1401698fb`
- `KERNEL32!GetCurrentThreadId` at `0x140169db9`
- `KERNEL32!GetCurrentThreadId` at `0x1401690f8`
- `KERNEL32!GetCurrentThreadId` at `0x14016922e`
- `KERNEL32!GetCurrentThreadId` at `0x140169240`
- `KERNEL32!GetCurrentThreadId` at `0x140169285`
- `KERNEL32!GetCurrentThreadId` at `0x140169460`
- `KERNEL32!GetCurrentThreadId` at `0x1401698fb`
- `KERNEL32!GetCurrentThreadId` at `0x140169db9`

## string_xrefs

- `0x1401699f2`: `Update syncInfoHistory`
- `0x140169cbe`: `Update syncInfoHistory`
- `0x140169b1f`: `Update cxtionInfoHistory`
- `0x140169377`: `(Ignored) Response to %s request discarded due to missing task. status:%d`
- `0x140169420`: `(Ignored) Response to %s request discarded due to missing task. status:%d`
- `0x1401698e5`: `Previous session was not closed, abandoning current connection. connId:%? csId:%? csName:%ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall InConnection::ReceiveVvUp(__int64 a1, const struct _GUID *a2, int a3, __int64 a4, unsigned int a5)
{
  int v6; // edi
  const struct _GUID *v7; // r14
  __int64 v9; // r12
  struct FrsStatus *ContentSet; // rsi
  __int64 v11; // r8
  struct InConnection::InConnectionContentSetContext *v12; // rbx
  __int64 (__fastcall *v13)(struct InConnection::InConnectionContentSetContext *, struct DbManager **, _QWORD); // rdi
  DWORD CurrentThreadId; // eax
  __int64 v15; // rdx
  DWORD v16; // eax
  __int64 v17; // rcx
  __int64 v18; // r9
  __int64 v19; // rbx
  DWORD v20; // eax
  __int64 v21; // rcx
  struct InConnection::InConnectionContentSetContext *v22; // rbx
  RefCountObject *v23; // rcx
  SubordinateMonitor *v24; // rcx
  RefCountObject *v25; // rcx
  DWORD v26; // eax
  __int64 v27; // rcx
  struct FrsStatus *v28; // rax
  LPCRITICAL_SECTION v29; // rax
  _QWORD *v30; // rax
  __int64 v31; // r8
  const struct VersionChainVector *v32; // rsi
  int v33; // edx
  SessionInfo *v34; // rax
  __int64 v35; // rax
  struct InConnection::InConnectionContentSetContext *v36; // rdi
  _QWORD *v37; // rsi
  struct VvUpData *v38; // r15
  DWORD v39; // eax
  __int64 v40; // rcx
  struct _FILETIME v41; // rax
  struct MonitorContext *v42; // rdi
  struct _RTL_CRITICAL_SECTION *v43; // rcx
  struct MonitorContext *v44; // rdi
  __int64 v45; // r9
  struct InConnection::InConnectionContentSetContext **v46; // r10
  struct MonitorContext *v47; // rcx
  int v48; // edx
  RefCountObject *v49; // rcx
  struct MonitorContext *v50; // rdi
  int v51; // ecx
  const struct HistoryRecord *v52; // rdx
  int v53; // edx
  struct _RTL_CRITICAL_SECTION *v54; // rcx
  DWORD v55; // eax
  __int64 v56; // rcx
  struct InConnection::InConnectionContentSetContext *v58; // [rsp+50h] [rbp-B0h] BYREF
  int v59; // [rsp+58h] [rbp-A8h]
  int v60[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp-98h] BYREF
  int v62; // [rsp+70h] [rbp-90h]
  int v63; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v64; // [rsp+78h] [rbp-88h]
  const wchar_t *v65; // [rsp+80h] [rbp-80h] BYREF
  int v66; // [rsp+88h] [rbp-78h]
  int v67; // [rsp+8Ch] [rbp-74h]
  const wchar_t *v68; // [rsp+90h] [rbp-70h]
  const struct _GUID *v69; // [rsp+98h] [rbp-68h]
  struct InConnection::InConnectionContentSetContext *v70; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v71; // [rsp+A8h] [rbp-58h] BYREF
  struct VvUpData *v72; // [rsp+B0h] [rbp-50h] BYREF
  const wchar_t *v73; // [rsp+B8h] [rbp-48h] BYREF
  int v74; // [rsp+C0h] [rbp-40h]
  int v75; // [rsp+C4h] [rbp-3Ch]
  const wchar_t *v76; // [rsp+C8h] [rbp-38h]
  _BYTE v77[16]; // [rsp+D0h] [rbp-30h] BYREF
  struct DbManager *v78[2]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v79[128]; // [rsp+100h] [rbp+0h] BYREF

  v72 = (struct VvUpData *)a4;
  v6 = a3;
  v59 = a3;
  v7 = a2;
  v69 = a2;
  std::map<_GUID,LdbManager::VvCompactMan::VvInfo>::map<_GUID,LdbManager::VvCompactMan::VvInfo>(v77);
  v9 = 0;
  if ( !v6 && !a5 && a4 && *(_DWORD *)(a4 + 64) )
  {
    *(_OWORD *)v78 = 0;
    ScopedLock::ScopedLock((ScopedLock *)&SystemTimeAsFileTime, (struct ScopedCS *)(a1 + 992));
    v58 = 0;
    *(_QWORD *)v60 = 0;
    ContentSet = InConnection::GetContentSet((InConnection *)a1, v7, &v58);
    if ( !ContentSet )
    {
      ContentSet = (struct FrsStatus *)ContentSetManager::GetVolumeManager(*((_QWORD *)v58 + 4), v60, v11);
      v12 = *(struct InConnection::InConnectionContentSetContext **)v60;
      if ( !ContentSet )
      {
        if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugVolumeManagerRefCount)
          && g_DebugLog
          && LODWORD(g_DebugLog[1].LockSemaphore)
          && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v73 = L"InConnection::ReceiveVvUp";
          v74 = 3272;
          v75 = 5;
          v76 = L"INCO";
          v70 = v12;
          dbgobj::DbgPrint<unsigned short,unsigned __int64>(
            &v73,
            L"[VMREF] Added reference to volume manager. ptr:%p",
            &v70);
        }
        v13 = *(__int64 (__fastcall **)(struct InConnection::InConnectionContentSetContext *, struct DbManager **, _QWORD))(*(_QWORD *)v12 + 32LL);
        CurrentThreadId = GetCurrentThreadId();
        ContentSet = (struct FrsStatus *)v13(v12, v78, CurrentThreadId);
      }
      if ( v12 )
      {
        if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugVolumeManagerRefCount)
          && g_DebugLog
          && LODWORD(g_DebugLog[1].LockSemaphore)
          && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v73 = L"InConnection::ReceiveVvUp";
          v74 = 3276;
          v75 = 5;
          v76 = L"INCO";
          v70 = v12;
          dbgobj::DbgPrint<unsigned short,unsigned __int64>(
            &v73,
            L"[VMREF] Release reference to volume manager. ptr:%p",
            &v70);
        }
        ScopedRef<VolumeManager::ShutdownRestartTask>::Set(v60, 0);
      }
      v6 = v59;
    }
    ScopedRef<VvUpData>::~ScopedRef<VvUpData>(v60);
    ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v58);
    ScopedLock::~ScopedLock((ScopedLock *)&SystemTimeAsFileTime);
    if ( !ContentSet )
      ContentSet = DbUtil::VersionVector(v78[0], v7, (struct VersionChainVector *)v77);
    DbManagerInstance::FinalizeDbManagerInstance((DbManagerInstance *)v78);
    if ( ContentSet )
      goto LABEL_129;
  }
  ScopedLock::ScopedLock((ScopedLock *)&v73, (struct ScopedCS *)(a1 + 992));
  v70 = 0;
  ContentSet = InConnection::GetContentSet((InConnection *)a1, v7, &v70);
  v15 = a5;
  if ( !ContentSet && a5 )
  {
    if ( a5 - 9001 > 0x25D )
    {
      v16 = GetCurrentThreadId();
      v18 = 1;
    }
    else
    {
      v16 = GetCurrentThreadId();
      v18 = 3;
    }
    v19 = FrsStatusList::PushNewError(
            v17,
            a5,
            0,
            v18,
            "base\\fs\\remotefs\\frs\\src\\sync\\inconnection.cpp",
            "InConnection::ReceiveVvUp",
            3296,
            v16,
            0);
    v20 = GetCurrentThreadId();
    ContentSet = (struct FrsStatus *)FrsStatusList::PushNewError(
                                       v21,
                                       9027,
                                       1,
                                       3,
                                       "base\\fs\\remotefs\\frs\\src\\sync\\inconnection.cpp",
                                       "InConnection::ReceiveVvUp",
                                       3304,
                                       v20,
                                       v19);
    v15 = a5;
  }
  v22 = v70;
  if ( !v70 )
    goto LABEL_114;
  if ( v6 == 1 )
  {
    if ( *((_QWORD *)v70 + 18) )
    {
      if ( !(_DWORD)v15 )
      {
        InConnection::CreateSpecialSyncSession(a1, v70, 1);
        v15 = a5;
      }
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)v22 + 18) + 48LL))(
        *((_QWORD *)v22 + 18),
        v15,
        a4);
    }
    else if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      SystemTimeAsFileTime = (struct _FILETIME)L"InConnection::ReceiveVvUp";
      v62 = 3318;
      v63 = 3;
      v64 = L"INCO";
      v58 = (struct InConnection::InConnectionContentSetContext *)L"SlowSync";
      dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned long>(
        &SystemTimeAsFileTime,
        L"(Ignored) Response to %s request discarded due to missing task. status:%d",
        &v58,
        &a5);
    }
    v23 = (RefCountObject *)*((_QWORD *)v22 + 21);
    if ( v23 )
    {
      RefCountObject::Release(v23);
      *((_QWORD *)v22 + 21) = 0;
    }
    goto LABEL_114;
  }
  if ( v6 == 2 )
  {
    v24 = (SubordinateMonitor *)*((_QWORD *)v70 + 22);
    if ( v24 )
    {
      SubordinateMonitor::GotVvUp(v24, v15, (struct VvUpData *)a4);
    }
    else if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      SystemTimeAsFileTime = (struct _FILETIME)L"InConnection::ReceiveVvUp";
      v62 = 3329;
      v63 = 3;
      v64 = L"INCO";
      v58 = (struct InConnection::InConnectionContentSetContext *)L"SubordinateSync";
      dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned long>(
        &SystemTimeAsFileTime,
        L"(Ignored) Response to %s request discarded due to missing task. status:%d",
        &v58,
        &a5);
    }
    v25 = (RefCountObject *)*((_QWORD *)v22 + 25);
    if ( v25 )
    {
      RefCountObject::Release(v25);
      *((_QWORD *)v22 + 25) = 0;
    }
    goto LABEL_114;
  }
  if ( !ContentSet )
  {
    if ( !a4 )
    {
      v26 = GetCurrentThreadId();
      v28 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                  v27,
                                  87,
                                  0,
                                  1,
                                  "base\\fs\\remotefs\\frs\\src\\sync\\inconnection.cpp",
                                  "InConnection::ReceiveVvUp",
                                  3339,
                                  v26,
                                  0);
LABEL_60:
      ContentSet = v28;
      goto LABEL_111;
    }
    if ( !*(_DWORD *)(a4 + 64) )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        SystemTimeAsFileTime = (struct _FILETIME)L"InConnection::ReceiveVvUp";
        v62 = 3343;
        v63 = 5;
        v64 = L"INCO";
        dbgobj::DbgPrint<unsigned short>(&SystemTimeAsFileTime, L"Change notify");
      }
      v28 = SessionTask::GotVvUpChangeNotify(*((SessionTask **)v22 + 9));
      goto LABEL_60;
    }
    if ( !*(_QWORD *)(a4 + 40) )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        SystemTimeAsFileTime = (struct _FILETIME)L"InConnection::ReceiveVvUp";
        v62 = 3348;
        v63 = 5;
        v64 = L"INCO";
        dbgobj::DbgPrint<unsigned short>(&SystemTimeAsFileTime, L"Empty vvUp");
      }
      *((_QWORD *)v22 + 13) = *(_QWORD *)(a4 + 72);
      ContentSet = SessionTask::GotVvUp(*((SessionTask **)v22 + 9), 0);
      if ( !ContentSet )
        InConnection::CheckSaveVvUpForInitialSync(
          (InConnection *)a1,
          v22,
          (const struct VersionChainVector *)(a4 + 32),
          0);
      goto LABEL_111;
    }
    ++*((_DWORD *)v70 + 24);
    *((_QWORD *)v22 + 13) = *(_QWORD *)(a4 + 72);
    v29 = g_DebugLog;
    if ( g_DebugLog )
    {
      if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        SystemTimeAsFileTime = (struct _FILETIME)L"InConnection::ReceiveVvUp";
        v62 = 3364;
        v63 = 4;
        v64 = L"INCO";
        v58 = (struct InConnection::InConnectionContentSetContext *)(*(_QWORD *)(*((_QWORD *)v22 + 4) + 200LL) + 18LL);
        dbgobj::DbgPrint<unsigned short,_GUID,_GUID,unsigned short const *,VersionChainVector>(
          (unsigned int)&SystemTimeAsFileTime,
          v15,
          a1 + 168,
          (_DWORD)v7,
          (__int64)&v58,
          a4 + 32);
        v29 = g_DebugLog;
      }
      if ( v29 && LODWORD(v29[1].LockSemaphore) && SLODWORD(v29[1].OwningThread) >= 4 )
      {
        v65 = L"InConnection::ReceiveVvUp";
        v66 = 3371;
        v67 = 4;
        v68 = L"INCO";
        v58 = (struct InConnection::InConnectionContentSetContext *)(*(_QWORD *)(*((_QWORD *)v22 + 4) + 200LL) + 18LL);
        SystemTimeAsFileTime = (struct _FILETIME)*((_QWORD *)v22 + 14);
        dbgobj::DbgPrint<unsigned short,unsigned long,unsigned __int64,_GUID,_GUID,unsigned short const *,VersionChainVector>(
          (unsigned int)&v65,
          v15,
          (_DWORD)v22 + 96,
          (unsigned int)&SystemTimeAsFileTime,
          a1 + 168,
          (__int64)v7,
          (__int64)&v58,
          (__int64)v77);
      }
    }
    *(_QWORD *)v60 = **((_QWORD **)v22 + 10);
    while ( 1 )
    {
      v30 = (_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(
                        (char *)v22 + 80,
                        &SystemTimeAsFileTime);
      if ( v31 == *v30 )
        break;
      v32 = (const struct VersionChainVector *)std::_List_iterator<std::_List_val<std::_List_simple_types<CONTENT_SET_RECORD>>>::operator->(v60);
      VersionChainVector::Union((VersionChainVector *)v77, v32);
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v65 = L"InConnection::ReceiveVvUp";
        v66 = 3387;
        v67 = 4;
        v68 = L"INCO";
        v58 = (struct InConnection::InConnectionContentSetContext *)(*(_QWORD *)(*((_QWORD *)v22 + 4) + 200LL) + 18LL);
        dbgobj::DbgPrint<unsigned short,_GUID,_GUID,unsigned short const *,VersionChainVector,VersionChainVector>(
          (unsigned int)&v65,
          v33,
          a1 + 168,
          (_DWORD)v7,
          (__int64)&v58,
          (__int64)v32,
          (__int64)v77);
      }
      std::_List_iterator<std::_List_val<std::_List_simple_types<CreditManager::ICallback *>>>::operator++(v60);
    }
    v34 = SessionInfo::SessionInfo((SessionInfo *)v79);
    std::list<SessionInfo>::push_back((char *)v22 + 80, v34);
    SessionInfo::~SessionInfo((SessionInfo *)v79);
    v35 = std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(
            (char *)v22 + 80,
            &v58);
    v36 = *(struct InConnection::InConnectionContentSetContext **)std::_List_iterator<std::_List_val<std::_List_simple_types<SessionInfo>>>::operator--(v35);
    *(_QWORD *)v60 = v36;
    ++*((_DWORD *)v22 + 56);
    v37 = (_QWORD *)std::_List_iterator<std::_List_val<std::_List_simple_types<CONTENT_SET_RECORD>>>::operator->(v60);
    SystemTimeAsFileTime = (struct _FILETIME)v37;
    v38 = v72;
    SessionInfo::Initialize((SessionInfo *)v37, (const struct VersionChainVector *)v77, v72, v7, *((_DWORD *)v22 + 24));
    v38 = (struct VvUpData *)((char *)v38 + 32);
    InConnection::CheckSaveVvUpForInitialSync((InConnection *)a1, v22, v38, v37[1] != 0);
    InConnection::CheckSaveVvUpForSysVol((InConnection *)a1, v22, v38);
    VersionChainVector::Union(
      (VersionChainVector *)(v37 + 2),
      (struct InConnection::InConnectionContentSetContext *)((char *)v22 + 56));
    std::_Tree<std::_Tmap_traits<Guid,IntervalSet,std::less<Guid>,std::allocator<std::pair<Guid const,IntervalSet>>,0>>::operator=(
      (char *)v22 + 56,
      v37 + 2);
    ContentSet = ContentSetManager::UpdateVersionsKnownToUpstreamPartners(*((ContentSetManager **)v22 + 4), v38);
    if ( !ContentSet )
    {
      if ( v36 != **((struct InConnection::InConnectionContentSetContext ***)v22 + 10) )
      {
        v58 = v36;
        std::_List_iterator<std::_List_val<std::_List_simple_types<SessionInfo>>>::operator--(&v58);
        if ( *(_DWORD *)(std::_List_iterator<std::_List_val<std::_List_simple_types<CONTENT_SET_RECORD>>>::operator->(&v58)
                       + 64) )
        {
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) )
          {
            v7 = v69;
            if ( SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
            {
              v65 = L"InConnection::ReceiveVvUp";
              v66 = 3451;
              v67 = 2;
              v68 = L"INCO";
              v58 = (struct InConnection::InConnectionContentSetContext *)(*(_QWORD *)(*((_QWORD *)v22 + 4) + 200LL)
                                                                         + 18LL);
              dbgobj::DbgPrint<unsigned short,_GUID,_GUID,unsigned short const *>(
                (unsigned int)&v65,
                (unsigned int)L"Previous session was not closed, abandoning current connection. connId:%? csId:%? csName:%ws",
                a1 + 168,
                (_DWORD)v69,
                (__int64)&v58);
            }
          }
          else
          {
            v7 = v69;
          }
          v39 = GetCurrentThreadId();
          ContentSet = (struct FrsStatus *)FrsStatusList::PushNewError(
                                             v40,
                                             9031,
                                             0,
                                             3,
                                             "base\\fs\\remotefs\\frs\\src\\sync\\inconnection.cpp",
                                             "InConnection::ReceiveVvUp",
                                             3458,
                                             v39,
                                             0);
          if ( ContentSet )
            goto LABEL_110;
        }
      }
      v41 = SystemTimeAsFileTime;
      if ( *(_QWORD *)(*(_QWORD *)&SystemTimeAsFileTime + 8LL) )
      {
        v50 = g_MonitorContext;
        EnterCriticalSection((LPCRITICAL_SECTION)g_MonitorContext + 15);
        *((_DWORD *)v50 + 148) = 1;
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v65 = L"InConnection::ReceiveVvUp";
          v66 = 3531;
          v67 = 5;
          v68 = L"INCO";
          dbgobj::DbgPrint<unsigned short>(&v65, L"Update syncInfoHistory");
        }
        v51 = *(_DWORD *)(a1 + 608);
        if ( ((v51 - 3) & 0xFFFFFFFC) == 0 && v51 != 5 )
        {
          StateHistory::Delete(
            (struct MonitorContext *)((char *)g_MonitorContext + 536),
            (struct HistoryRecord *)(a1 + 536));
          SyncInfo::ResetInfo((SyncInfo *)(a1 + 536), v52);
          *(_DWORD *)(a1 + 612) = ReplModeToInitReason(*(unsigned int *)(a1 + 1056));
          if ( ((v53 - 2) & 0xFFFFFFFD) == 0 )
          {
            *(_QWORD *)(a1 + 736) = *(_QWORD *)(a1 + 1068);
            *(_DWORD *)(a1 + 744) = Config::ScheduleParam::MapKbpsToBandwidthLevel(*(unsigned int *)(a1 + 1076));
          }
        }
        if ( *(_DWORD *)(a1 + 608) != 2 )
          *(_DWORD *)(a1 + 608) = 2;
        StateHistory::Update(
          (struct MonitorContext *)((char *)g_MonitorContext + 536),
          (struct HistoryRecord *)(a1 + 536));
        v54 = (struct _RTL_CRITICAL_SECTION *)g_MonitorContext;
        *((_DWORD *)g_MonitorContext + 148) = 0;
        LeaveCriticalSection(v54 + 15);
        v48 = 1;
      }
      else
      {
        *(_DWORD *)(*(_QWORD *)&SystemTimeAsFileTime + 64LL) = 0;
        *(_QWORD *)(*(_QWORD *)&v41 + 52LL) = 0;
        std::list<SessionInfo>::erase((char *)v22 + 80, &v58, v36);
        if ( *((_DWORD *)v22 + 57) == --*((_DWORD *)v22 + 56) )
        {
          v42 = g_MonitorContext;
          EnterCriticalSection((LPCRITICAL_SECTION)g_MonitorContext + 15);
          *((_DWORD *)v42 + 148) = 1;
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
          {
            v65 = L"InConnection::ReceiveVvUp";
            v66 = 3486;
            v67 = 5;
            v68 = L"INCO";
            dbgobj::DbgPrint<unsigned short>(&v65, L"Update syncInfoHistory");
          }
          if ( *(_DWORD *)(a1 + 608) != 4 )
          {
            *(_DWORD *)(a1 + 608) = 4;
            StateHistory::Update(
              (struct MonitorContext *)((char *)g_MonitorContext + 536),
              (struct HistoryRecord *)(a1 + 536));
          }
          v43 = (struct _RTL_CRITICAL_SECTION *)g_MonitorContext;
          *((_DWORD *)g_MonitorContext + 148) = 0;
          LeaveCriticalSection(v43 + 15);
          if ( *(_DWORD *)(a1 + 1056) == 4 )
          {
            *(_QWORD *)(a1 + 1056) = 1;
            *(_QWORD *)(a1 + 1064) = 0;
            *(_QWORD *)(a1 + 1072) = 0;
            *(_DWORD *)(a1 + 1080) = 0;
            InConnection::ReConfigure((InConnection *)a1);
            InConnection::LogModeChangeEvent(a1, 4, *(unsigned int *)(a1 + 1056), 0, 0);
          }
          SystemTimeAsFileTime = 0;
          v60[0] = 0;
          v71 = 0;
          LODWORD(v72) = 0;
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          InConnection::UpdateBandwidth((InConnection *)a1, v60, &v71, (unsigned int *)&v72);
          v44 = g_MonitorContext;
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_MonitorContext + 496));
          *((_DWORD *)v44 + 122) = 1;
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
          {
            v65 = L"InConnection::ReceiveVvUp";
            v66 = 3516;
            v67 = 5;
            v68 = L"INCO";
            dbgobj::DbgPrint<unsigned short>(&v65, L"Update cxtionInfoHistory");
          }
          *(_QWORD *)(a1 + 924) = *(_QWORD *)(a1 + 932);
          *(_DWORD *)(a1 + 948) = FileTime::Diff(&SystemTimeAsFileTime, (const struct _FILETIME *)(a1 + 932)) / 0x3E8;
          *(_QWORD *)(a1 + 940) = v45;
          v58 = (struct InConnection::InConnectionContentSetContext *)(10000LL * v71 + *(_QWORD *)&SystemTimeAsFileTime);
          *v46 = v58;
          StateHistory::Update(
            (struct MonitorContext *)((char *)g_MonitorContext + 432),
            (struct HistoryRecord *)(a1 + 752));
          v47 = g_MonitorContext;
          *((_DWORD *)g_MonitorContext + 122) = 0;
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v47 + 496));
        }
        SessionTask::CheckHibernate(*((SessionTask **)v22 + 9));
        v48 = 0;
      }
      ContentSet = SessionTask::GotVvUp(*((SessionTask **)v22 + 9), v48);
    }
    v7 = v69;
LABEL_110:
    v6 = v59;
  }
LABEL_111:
  if ( !v6 )
  {
    v49 = (RefCountObject *)*((_QWORD *)v22 + 14);
    if ( v49 )
    {
      RefCountObject::Release(v49);
      *((_QWORD *)v22 + 14) = 0;
    }
  }
LABEL_114:
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v70);
  ScopedLock::~ScopedLock((ScopedLock *)&v73);
  if ( ContentSet )
  {
    if ( v6 )
    {
LABEL_130:
      v55 = GetCurrentThreadId();
      v9 = FrsStatusList::PushNewError(
             v56,
             *((unsigned int *)ContentSet + 1),
             *((unsigned int *)ContentSet + 2),
             *(unsigned int *)ContentSet,
             "base\\fs\\remotefs\\frs\\src\\sync\\inconnection.cpp",
             "InConnection::ReceiveVvUp",
             3586,
             v55,
             ContentSet);
      goto LABEL_131;
    }
LABEL_129:
    InConnection::ProcessErrorStatus((InConnection *)a1, v7, ContentSet, 1);
    goto LABEL_130;
  }
  if ( !v6 )
    *(_DWORD *)(a1 + 1168) = 1;
LABEL_131:
  std::_Tree<std::_Tmap_traits<Guid,IntervalSet,std::less<Guid>,std::allocator<std::pair<Guid const,IntervalSet>>,0>>::~_Tree<std::_Tmap_traits<Guid,IntervalSet,std::less<Guid>,std::allocator<std::pair<Guid const,IntervalSet>>,0>>(v77);
  return v9;
}

```

## disassembly

```asm
0x140168fa4  mov     [rsp-8+arg_10], rbx
0x140168fa9  push    rbp
0x140168faa  push    rsi
0x140168fab  push    rdi
0x140168fac  push    r12
0x140168fae  push    r13
0x140168fb0  push    r14
0x140168fb2  push    r15
0x140168fb4  lea     rbp, [rsp-90h]
0x140168fbc  sub     rsp, 190h
0x140168fc3  mov     rax, cs:__security_cookie
0x140168fca  xor     rax, rsp
0x140168fcd  mov     [rbp+0C0h+var_40], rax
0x140168fd4  mov     r15, r9
0x140168fd7  mov     [rbp+0C0h+var_110], r9
0x140168fdb  mov     edi, r8d
0x140168fde  mov     [rsp+1C0h+var_168], r8d
0x140168fe3  mov     r14, rdx
0x140168fe6  mov     [rbp+0C0h+var_128], rdx
0x140168fea  mov     r13, rcx
0x140168fed  lea     rcx, [rbp+0C0h+var_F0]
0x140168ff1  call    ??0?$map@U_GUID@@VVvInfo@VvCompactMan@LdbManager@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@VVvInfo@VvCompactMan@LdbManager@@@std@@@6@@std@@QEAA@XZ; std::map<_GUID,LdbManager::VvCompactMan::VvInfo>::map<_GUID,LdbManager::VvCompactMan::VvInfo>(void)
0x140168ff6  nop
0x140168ff7  lea     rbx, aInconnectionRe_3; "InConnection::ReceiveVvUp"
0x140168ffe  xor     r12d, r12d
0x140169001  test    edi, edi
0x140169003  jnz     loc_1401691E3
0x140169009  cmp     [rbp+0C0h+arg_20], r12d
0x140169010  jnz     loc_1401691E3
0x140169016  test    r15, r15
0x140169019  jz      loc_1401691E3
0x14016901f  cmp     [r15+40h], r12d
0x140169023  jz      loc_1401691E3
0x140169029  xorps   xmm0, xmm0
0x14016902c  movdqu  xmmword ptr [rbp+0C0h+var_E0], xmm0
0x140169031  lea     rdx, [r13+3E0h]; struct ScopedCS *
0x140169038  lea     rcx, [rsp+1C0h+SystemTimeAsFileTime]; this
0x14016903d  call    ??0ScopedLock@@QEAA@AEAVScopedCS@@@Z; ScopedLock::ScopedLock(ScopedCS &)
0x140169042  nop
0x140169043  mov     [rsp+1C0h+var_170], r12
0x140169048  mov     qword ptr [rsp+1C0h+var_160], r12
0x14016904d  lea     r8, [rsp+1C0h+var_170]; struct InConnection::InConnectionContentSetContext **
0x140169052  mov     rdx, r14; struct _GUID *
0x140169055  mov     rcx, r13; this
0x140169058  call    ?GetContentSet@InConnection@@AEAAPEAVFrsStatus@@AEBU_GUID@@PEAPEAVInConnectionContentSetContext@1@@Z; InConnection::GetContentSet(_GUID const &,InConnection::InConnectionContentSetContext * *)
0x14016905d  mov     rsi, rax
0x140169060  test    rax, rax
0x140169063  jnz     loc_140169199
0x140169069  mov     rax, [rsp+1C0h+var_170]
0x14016906e  lea     rdx, [rsp+1C0h+var_160]
0x140169073  mov     rcx, [rax+20h]
0x140169077  call    ?GetVolumeManager@ContentSetManager@@QEAAPEAVFrsStatus@@AEAV?$ScopedRef@VVolumeManager@@@@@Z; ContentSetManager::GetVolumeManager(ScopedRef<VolumeManager> &)
0x14016907c  mov     rsi, rax
0x14016907f  mov     rbx, qword ptr [rsp+1C0h+var_160]
0x140169084  test    rax, rax
0x140169087  jnz     loc_140169119
0x14016908d  lea     rcx, ?DebugVolumeManagerRefCount@Settings@@3VCDebugVolumeManagerRefCount@1@A; Settings::CDebugVolumeManagerRefCount Settings::DebugVolumeManagerRefCount
0x140169094  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x140169099  test    eax, eax
0x14016909b  jz      short loc_1401690F1
0x14016909d  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401690a4  test    rax, rax
0x1401690a7  jz      short loc_1401690F1
0x1401690a9  cmp     [rax+40h], r12d
0x1401690ad  jz      short loc_1401690F1
0x1401690af  cmp     dword ptr [rax+38h], 5
0x1401690b3  jl      short loc_1401690F1
0x1401690b5  lea     rax, aInconnectionRe; "InConnection::ReceiveVvUp"
0x1401690bc  mov     [rbp+0C0h+var_108], rax
0x1401690c0  mov     [rbp+0C0h+var_100], 0CC8h
0x1401690c7  mov     [rbp+0C0h+var_FC], 5
0x1401690ce  lea     rax, aInco; "INCO"
0x1401690d5  mov     [rbp+0C0h+var_F8], rax
0x1401690d9  mov     [rbp+0C0h+var_120], rbx
0x1401690dd  lea     r8, [rbp+0C0h+var_120]
0x1401690e1  lea     rdx, aVmrefAddedRefe; "[VMREF] Added reference to volume manag"...
0x1401690e8  lea     rcx, [rbp+0C0h+var_108]
0x1401690ec  call    ??$DbgPrint@G_K@dbgobj@@QEAA_KPEBGAEB_K@Z; dbgobj::DbgPrint<ushort,unsigned __int64>(ushort const *,unsigned __int64 const &)
0x1401690f1  mov     rax, [rbx]
0x1401690f4  mov     rdi, [rax+20h]
0x1401690f8  call    cs:__imp_GetCurrentThreadId
0x1401690ff  nop     dword ptr [rax+rax+00h]
0x140169104  mov     r8d, eax
0x140169107  lea     rdx, [rbp+0C0h+var_E0]
0x14016910b  mov     rcx, rbx
0x14016910e  mov     rax, rdi
0x140169111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140169116  mov     rsi, rax
0x140169119  test    rbx, rbx
0x14016911c  jz      short loc_14016918E
0x14016911e  lea     rcx, ?DebugVolumeManagerRefCount@Settings@@3VCDebugVolumeManagerRefCount@1@A; Settings::CDebugVolumeManagerRefCount Settings::DebugVolumeManagerRefCount
0x140169125  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x14016912a  test    eax, eax
0x14016912c  jz      short loc_140169182
0x14016912e  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140169135  test    rax, rax
0x140169138  jz      short loc_140169182
0x14016913a  cmp     [rax+40h], r12d
0x14016913e  jz      short loc_140169182
0x140169140  cmp     dword ptr [rax+38h], 5
0x140169144  jl      short loc_140169182
0x140169146  lea     rax, aInconnectionRe; "InConnection::ReceiveVvUp"
0x14016914d  mov     [rbp+0C0h+var_108], rax
0x140169151  mov     [rbp+0C0h+var_100], 0CCCh
0x140169158  mov     [rbp+0C0h+var_FC], 5
0x14016915f  lea     rax, aInco; "INCO"
0x140169166  mov     [rbp+0C0h+var_F8], rax
0x14016916a  mov     [rbp+0C0h+var_120], rbx
0x14016916e  lea     r8, [rbp+0C0h+var_120]
0x140169172  lea     rdx, aVmrefReleaseRe; "[VMREF] Release reference to volume man"...
0x140169179  lea     rcx, [rbp+0C0h+var_108]
0x14016917d  call    ??$DbgPrint@G_K@dbgobj@@QEAA_KPEBGAEB_K@Z; dbgobj::DbgPrint<ushort,unsigned __int64>(ushort const *,unsigned __int64 const &)
0x140169182  xor     edx, edx
0x140169184  lea     rcx, [rsp+1C0h+var_160]
0x140169189  call    ?Set@?$ScopedRef@VShutdownRestartTask@VolumeManager@@@@AEAAXPEAVShutdownRestartTask@VolumeManager@@@Z; ScopedRef<VolumeManager::ShutdownRestartTask>::Set(VolumeManager::ShutdownRestartTask *)
0x14016918e  lea     rbx, aInconnectionRe_3; "InConnection::ReceiveVvUp"
0x140169195  mov     edi, [rsp+1C0h+var_168]
0x140169199  lea     rcx, [rsp+1C0h+var_160]
0x14016919e  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x1401691a3  nop
0x1401691a4  lea     rcx, [rsp+1C0h+var_170]
0x1401691a9  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x1401691ae  nop
0x1401691af  lea     rcx, [rsp+1C0h+SystemTimeAsFileTime]; this
0x1401691b4  call    ??1ScopedLock@@QEAA@XZ; ScopedLock::~ScopedLock(void)
0x1401691b9  test    rsi, rsi
0x1401691bc  jnz     short loc_1401691D1
0x1401691be  lea     r8, [rbp+0C0h+var_F0]; struct VersionChainVector *
0x1401691c2  mov     rdx, r14; struct _GUID *
0x1401691c5  mov     rcx, [rbp+0C0h+var_E0]; struct DbManager *
0x1401691c9  call    ?VersionVector@DbUtil@@SAPEAVFrsStatus@@PEAVDbManager@@AEBU_GUID@@AEAVVersionChainVector@@@Z; DbUtil::VersionVector(DbManager *,_GUID const &,VersionChainVector &)
0x1401691ce  mov     rsi, rax
0x1401691d1  lea     rcx, [rbp+0C0h+var_E0]; this
0x1401691d5  call    ?FinalizeDbManagerInstance@DbManagerInstance@@QEAAXXZ; DbManagerInstance::FinalizeDbManagerInstance(void)
0x1401691da  test    rsi, rsi
0x1401691dd  jnz     loc_140169DA5
0x1401691e3  lea     rdx, [r13+3E0h]; struct ScopedCS *
0x1401691ea  lea     rcx, [rbp+0C0h+var_108]; this
0x1401691ee  call    ??0ScopedLock@@QEAA@AEAVScopedCS@@@Z; ScopedLock::ScopedLock(ScopedCS &)
0x1401691f3  nop
0x1401691f4  mov     [rbp+0C0h+var_120], r12
0x1401691f8  lea     r8, [rbp+0C0h+var_120]; struct InConnection::InConnectionContentSetContext **
0x1401691fc  mov     rdx, r14; struct _GUID *
0x1401691ff  mov     rcx, r13; this
0x140169202  call    ?GetContentSet@InConnection@@AEAAPEAVFrsStatus@@AEBU_GUID@@PEAPEAVInConnectionContentSetContext@1@@Z; InConnection::GetContentSet(_GUID const &,InConnection::InConnectionContentSetContext * *)
0x140169207  mov     rsi, rax
0x14016920a  mov     edx, [rbp+0C0h+arg_20]
0x140169210  test    rax, rax
0x140169213  jnz     loc_1401692D0
0x140169219  test    edx, edx
0x14016921b  jz      loc_1401692D0
0x140169221  lea     eax, [rdx-2329h]
0x140169227  cmp     eax, 25Dh
0x14016922c  ja      short loc_140169240
0x14016922e  call    cs:__imp_GetCurrentThreadId
0x140169235  nop     dword ptr [rax+rax+00h]
0x14016923a  lea     r9d, [rsi+3]
0x14016923e  jmp     short loc_140169252
0x140169240  call    cs:__imp_GetCurrentThreadId
0x140169247  nop     dword ptr [rax+rax+00h]
0x14016924c  mov     r9d, 1
0x140169252  mov     [rsp+1C0h+var_180], r12
0x140169257  mov     dword ptr [rsp+1C0h+var_188], eax
0x14016925b  mov     dword ptr [rsp+1C0h+var_190], 0CE0h
0x140169263  mov     [rsp+1C0h+var_198], rbx
0x140169268  lea     rsi, aBaseFsRemotefs_1; "base\\fs\\remotefs\\frs\\src\\sync\\inc"...
0x14016926f  mov     qword ptr [rsp+1C0h+var_1A0], rsi
0x140169274  xor     r8d, r8d
0x140169277  mov     edx, [rbp+0C0h+arg_20]
0x14016927d  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140169282  mov     rbx, rax
0x140169285  call    cs:__imp_GetCurrentThreadId
0x14016928c  nop     dword ptr [rax+rax+00h]
0x140169291  mov     [rsp+1C0h+var_180], rbx
0x140169296  mov     dword ptr [rsp+1C0h+var_188], eax
0x14016929a  mov     dword ptr [rsp+1C0h+var_190], 0CE8h
0x1401692a2  lea     rax, aInconnectionRe_3; "InConnection::ReceiveVvUp"
0x1401692a9  mov     [rsp+1C0h+var_198], rax
0x1401692ae  mov     qword ptr [rsp+1C0h+var_1A0], rsi
0x1401692b3  mov     edx, 2343h
0x1401692b8  mov     r9d, 3
0x1401692be  lea     r8d, [r9-2]
0x1401692c2  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401692c7  mov     rsi, rax
0x1401692ca  mov     edx, [rbp+0C0h+arg_20]; unsigned int
0x1401692d0  mov     rbx, [rbp+0C0h+var_120]
0x1401692d4  test    rbx, rbx
0x1401692d7  jz      loc_140169C27
0x1401692dd  cmp     edi, 1
0x1401692e0  jnz     loc_1401693A9
0x1401692e6  cmp     [rbx+90h], r12
0x1401692ed  jz      short loc_14016931F
0x1401692ef  test    edx, edx
0x1401692f1  jnz     short loc_140169307
0x1401692f3  mov     r8d, edi
0x1401692f6  mov     rdx, rbx
0x1401692f9  mov     rcx, r13
0x1401692fc  call    ?CreateSpecialSyncSession@InConnection@@AEAAXPEAVInConnectionContentSetContext@1@W4SYNC_TYPE@@@Z; InConnection::CreateSpecialSyncSession(InConnection::InConnectionContentSetContext *,SYNC_TYPE)
0x140169301  mov     edx, [rbp+0C0h+arg_20]
0x140169307  mov     rcx, [rbx+90h]
0x14016930e  mov     rax, [rcx]
0x140169311  mov     r8, r15
0x140169314  mov     rax, [rax+30h]
0x140169318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14016931d  jmp     short loc_140169388
0x14016931f  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140169326  test    rax, rax
0x140169329  jz      short loc_140169388
0x14016932b  cmp     [rax+40h], r12d
0x14016932f  jz      short loc_140169388
0x140169331  cmp     dword ptr [rax+38h], 3
0x140169335  jl      short loc_140169388
0x140169337  lea     rax, aInconnectionRe; "InConnection::ReceiveVvUp"
0x14016933e  mov     qword ptr [rsp+1C0h+SystemTimeAsFileTime.dwLowDateTime], rax
0x140169343  mov     [rsp+1C0h+var_150], 0CF6h
0x14016934b  mov     [rsp+1C0h+var_14C], 3
0x140169353  lea     rax, aInco; "INCO"
0x14016935a  mov     [rsp+1C0h+var_148], rax
0x14016935f  lea     rax, aSlowsync; "SlowSync"
0x140169366  mov     [rsp+1C0h+var_170], rax
0x14016936b  lea     r9, [rbp+0C0h+arg_20]
0x140169372  lea     r8, [rsp+1C0h+var_170]
0x140169377  lea     rdx, aIgnoredRespons; "(Ignored) Response to %s request discar"...
0x14016937e  lea     rcx, [rsp+1C0h+SystemTimeAsFileTime]
0x140169383  call    ??$DbgPrint@GPEBGK@dbgobj@@QEAA_KPEBGAEBQEBGAEBK@Z; dbgobj::DbgPrint<ushort,ushort const *,ulong>(ushort const *,ushort const * const &,ulong const &)
0x140169388  mov     rcx, [rbx+0A8h]; this
0x14016938f  test    rcx, rcx
0x140169392  jz      loc_140169C27
0x140169398  call    ?Release@RefCountObject@@QEAAJXZ; RefCountObject::Release(void)
0x14016939d  mov     [rbx+0A8h], r12
0x1401693a4  jmp     loc_140169C27
0x1401693a9  cmp     edi, 2
0x1401693ac  jnz     loc_140169452
0x1401693b2  mov     rcx, [rbx+0B0h]; this
0x1401693b9  test    rcx, rcx
0x1401693bc  jz      short loc_1401693C8
0x1401693be  mov     r8, r15; struct VvUpData *
0x1401693c1  call    ?GotVvUp@SubordinateMonitor@@QEAAPEAVFrsStatus@@KPEAVVvUpData@@@Z; SubordinateMonitor::GotVvUp(ulong,VvUpData *)
0x1401693c6  jmp     short loc_140169431
0x1401693c8  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401693cf  test    rax, rax
0x1401693d2  jz      short loc_140169431
0x1401693d4  cmp     [rax+40h], r12d
0x1401693d8  jz      short loc_140169431
0x1401693da  cmp     dword ptr [rax+38h], 3
0x1401693de  jl      short loc_140169431
0x1401693e0  lea     rax, aInconnectionRe; "InConnection::ReceiveVvUp"
0x1401693e7  mov     qword ptr [rsp+1C0h+SystemTimeAsFileTime.dwLowDateTime], rax
0x1401693ec  mov     [rsp+1C0h+var_150], 0D01h
0x1401693f4  mov     [rsp+1C0h+var_14C], 3
0x1401693fc  lea     rax, aInco; "INCO"
0x140169403  mov     [rsp+1C0h+var_148], rax
0x140169408  lea     rax, aSubordinatesyn; "SubordinateSync"
0x14016940f  mov     [rsp+1C0h+var_170], rax
0x140169414  lea     r9, [rbp+0C0h+arg_20]
0x14016941b  lea     r8, [rsp+1C0h+var_170]
0x140169420  lea     rdx, aIgnoredRespons; "(Ignored) Response to %s request discar"...
0x140169427  lea     rcx, [rsp+1C0h+SystemTimeAsFileTime]
0x14016942c  call    ??$DbgPrint@GPEBGK@dbgobj@@QEAA_KPEBGAEBQEBGAEBK@Z; dbgobj::DbgPrint<ushort,ushort const *,ulong>(ushort const *,ushort const * const &,ulong const &)
0x140169431  mov     rcx, [rbx+0C8h]; this
0x140169438  test    rcx, rcx
0x14016943b  jz      loc_140169C27
0x140169441  call    ?Release@RefCountObject@@QEAAJXZ; RefCountObject::Release(void)
0x140169446  mov     [rbx+0C8h], r12
0x14016944d  jmp     loc_140169C27
0x140169452  test    rsi, rsi
0x140169455  jnz     loc_140169C11
0x14016945b  test    r15, r15
0x14016945e  jnz     short loc_1401694A6
0x140169460  call    cs:__imp_GetCurrentThreadId
0x140169467  nop     dword ptr [rax+rax+00h]
0x14016946c  mov     [rsp+1C0h+var_180], r12
0x140169471  mov     dword ptr [rsp+1C0h+var_188], eax
0x140169475  mov     dword ptr [rsp+1C0h+var_190], 0D0Bh
0x14016947d  lea     rax, aInconnectionRe_3; "InConnection::ReceiveVvUp"
0x140169484  mov     [rsp+1C0h+var_198], rax
0x140169489  lea     rax, aBaseFsRemotefs_1; "base\\fs\\remotefs\\frs\\src\\sync\\inc"...
0x140169490  mov     qword ptr [rsp+1C0h+var_1A0], rax
0x140169495  lea     r9d, [rsi+1]
0x140169499  xor     r8d, r8d
0x14016949c  lea     edx, [rsi+57h]
0x14016949f  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401694a4  jmp     short loc_140169506
0x1401694a6  cmp     [r15+40h], r12d
0x1401694aa  jnz     short loc_14016950E
0x1401694ac  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401694b3  test    rax, rax
0x1401694b6  jz      short loc_1401694FD
0x1401694b8  cmp     [rax+40h], r12d
0x1401694bc  jz      short loc_1401694FD
0x1401694be  cmp     dword ptr [rax+38h], 5
0x1401694c2  jl      short loc_1401694FD
0x1401694c4  lea     rax, aInconnectionRe; "InConnection::ReceiveVvUp"
0x1401694cb  mov     qword ptr [rsp+1C0h+SystemTimeAsFileTime.dwLowDateTime], rax
0x1401694d0  mov     [rsp+1C0h+var_150], 0D0Fh
0x1401694d8  mov     [rsp+1C0h+var_14C], 5
0x1401694e0  lea     rax, aInco; "INCO"
0x1401694e7  mov     [rsp+1C0h+var_148], rax
0x1401694ec  lea     rdx, aChangeNotify; "Change notify"
0x1401694f3  lea     rcx, [rsp+1C0h+SystemTimeAsFileTime]
  ... truncated ...
```
