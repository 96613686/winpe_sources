# InConnection::CommitSession(InConnection::InConnectionContentSetContext *,std::_List_iterator<std::_List_val<std::_List_simple_types<SessionInfo>>>,SYNC_TYPE)

- ea: `0x140161300`
- end: `0x140161e83`
- name: `?CommitSession@InConnection@@AEAAPEAVFrsStatus@@PEAVInConnectionContentSetContext@1@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@VSessionInfo@@@std@@@std@@@std@@W4SYNC_TYPE@@@Z`
- size: `2947`
- prototype: `__int64 __fastcall(InConnection *this, struct InConnection::InConnectionContentSetContext *)`
- caller_count: `3`
- callee_count: `39`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14016862c`
- `0x14016c03c`
- `0x14016dbf0`

## callees

- `0x14000c910`
- `0x14000e34c`
- `0x140024ebc`
- `0x14002bf70`
- `0x14002c2f4`
- `0x14002c404`
- `0x1400370bc`
- `0x1400391c4`
- `0x140048370`
- `0x14006a550`
- `0x1400867e0`
- `0x140086dcc`
- `0x1400923f8`
- `0x1400fc06c`
- `0x140111380`
- `0x140132d18`
- `0x14015cee8`
- `0x14015d6ec`
- `0x14015d7b8`
- `0x14015d8ac`
- `0x140160934`
- `0x140160c4c`
- `0x140160f6c`
- `0x140161208`
- `0x140161300`
- `0x1401649ac`
- `0x1401651d0`
- `0x140165a18`
- `0x1401668d8`
- `0x140169e74`
- `0x14016d480`
- `0x14016e40c`
- `0x14016e43c`
- `0x1401b30b0`
- `0x1401b324c`
- `0x1401b9494`
- `0x1401bda10`
- `0x1401c4560`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x1401618f7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140161959`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1401618f7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140161959`
- `KERNEL32!LeaveCriticalSection` at `0x140161932`
- `KERNEL32!LeaveCriticalSection` at `0x140161a94`
- `KERNEL32!LeaveCriticalSection` at `0x140161caf`
- `KERNEL32!LeaveCriticalSection` at `0x140161932`
- `KERNEL32!LeaveCriticalSection` at `0x140161a94`
- `KERNEL32!LeaveCriticalSection` at `0x140161caf`
- `KERNEL32!EnterCriticalSection` at `0x140161865`
- `KERNEL32!EnterCriticalSection` at `0x140161987`
- `KERNEL32!EnterCriticalSection` at `0x140161bbd`
- `KERNEL32!EnterCriticalSection` at `0x140161865`
- `KERNEL32!EnterCriticalSection` at `0x140161987`
- `KERNEL32!EnterCriticalSection` at `0x140161bbd`
- `KERNEL32!GetCurrentThreadId` at `0x140161428`
- `KERNEL32!GetCurrentThreadId` at `0x140161619`
- `KERNEL32!GetCurrentThreadId` at `0x140161cc4`
- `KERNEL32!GetCurrentThreadId` at `0x140161428`
- `KERNEL32!GetCurrentThreadId` at `0x140161619`
- `KERNEL32!GetCurrentThreadId` at `0x140161cc4`

## string_xrefs

- `0x1401618b2`: `Update syncInfoHistory`
- `0x140161c0a`: `Update syncInfoHistory`
- `0x1401619d7`: `Update cxtionInfoHistory`
- `0x140161d93`: `Committed %s session connId:%? csId:%? csName:%?`
- `0x140161e31`: `Committed %s session connId:%? csId:%? csName:%?`
- `0x140161387`: `InConnection::CommitSession`
- `0x140161471`: `InConnection::CommitSession`
- `0x140161687`: `InConnection::CommitSession`
- `0x14016170d`: `InConnection::CommitSession`
- `0x140161aff`: `InConnection::CommitSession`
- `0x140161d34`: `InConnection::CommitSession`
- `0x140161dd5`: `InConnection::CommitSession`
- `0x140161ce1`: `InConnection::CommitSession`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall InConnection::CommitSession(
        InConnection *this,
        struct InConnection::InConnectionContentSetContext *a2,
        __int64 a3,
        int a4)
{
  __int64 v7; // r14
  struct FrsStatus *VolumeManager; // r12
  RefCountObject *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // r8
  int v13; // ebx
  __int64 v14; // rdi
  struct FrsStatus *v15; // rbx
  __int64 (__fastcall *v16)(struct FrsStatus *, struct DbManager **, _QWORD); // rsi
  DWORD CurrentThreadId; // eax
  int v18; // eax
  __int64 v19; // rbx
  __int64 v20; // r8
  struct FrsStatus *v21; // rdi
  __int64 (__fastcall *v22)(struct FrsStatus *, struct DbManager **, _QWORD); // rsi
  DWORD v23; // eax
  __int64 v24; // r11
  int v25; // edx
  __int64 v26; // r10
  int v27; // edx
  struct MonitorContext *v28; // rbx
  struct _RTL_CRITICAL_SECTION *v29; // rcx
  struct MonitorContext *v30; // rbx
  __int64 v31; // r9
  ReplicaSetManager **v32; // r10
  struct MonitorContext *v33; // rcx
  __int64 v34; // r10
  struct MonitorContext *v35; // rbx
  int v36; // edx
  struct _RTL_CRITICAL_SECTION *v37; // rcx
  DWORD v38; // eax
  __int64 v39; // rcx
  __int64 v40; // rbx
  const wchar_t *v42; // [rsp+50h] [rbp-89h] BYREF
  int v43; // [rsp+58h] [rbp-81h]
  int v44; // [rsp+5Ch] [rbp-7Dh]
  const wchar_t *v45; // [rsp+60h] [rbp-79h]
  struct FrsStatus *v46; // [rsp+68h] [rbp-71h] BYREF
  ReplicaSetManager *v47; // [rsp+70h] [rbp-69h] BYREF
  const wchar_t *v48; // [rsp+78h] [rbp-61h] BYREF
  VersionChainVector *v49; // [rsp+80h] [rbp-59h] BYREF
  __int64 v50; // [rsp+88h] [rbp-51h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+90h] [rbp-49h] BYREF
  const wchar_t *v52; // [rsp+98h] [rbp-41h] BYREF
  int v53; // [rsp+A0h] [rbp-39h]
  int v54; // [rsp+A4h] [rbp-35h]
  const wchar_t *v55; // [rsp+A8h] [rbp-31h]
  unsigned int v56; // [rsp+B0h] [rbp-29h] BYREF
  unsigned __int64 v57; // [rsp+B8h] [rbp-21h] BYREF
  struct DbManager *v58[2]; // [rsp+C0h] [rbp-19h] BYREF
  struct DbManager *v59[2]; // [rsp+D8h] [rbp-1h] BYREF
  _BYTE v60[64]; // [rsp+F0h] [rbp+17h] BYREF
  __int64 v61; // [rsp+148h] [rbp+6Fh] BYREF
  __int64 v62; // [rsp+150h] [rbp+77h] BYREF

  v62 = a3;
  v7 = 0;
  VolumeManager = 0;
  v50 = 0;
  v9 = (RefCountObject *)*((_QWORD *)a2 + 4);
  if ( v9 )
  {
    RefCountObject::AddRef(v9);
    v10 = *((_QWORD *)a2 + 4);
  }
  else
  {
    v10 = 0;
  }
  ScopedRef<VolumeManager::ShutdownRestartTask>::Set(&v50, v10);
  v11 = std::_List_iterator<std::_List_val<std::_List_simple_types<CONTENT_SET_RECORD>>>::operator->(&v62);
  v49 = (VersionChainVector *)v11;
  if ( *(_DWORD *)(v11 + 64) || *(_DWORD *)(v11 + 52) )
    goto LABEL_102;
  v13 = a4 - 1;
  if ( !v13 )
  {
    v40 = v50;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v42 = L"InConnection::CommitSession";
      v43 = 5395;
      v44 = 4;
      v45 = L"INCO";
      v61 = *(_QWORD *)(v50 + 200) + 18LL;
      v48 = L"SlowSync";
      dbgobj::DbgPrint<unsigned short,unsigned short const *,_GUID,_GUID,unsigned short const *>(
        (unsigned int)&v42,
        (unsigned int)L"Committed %s session connId:%? csId:%? csName:%?",
        (unsigned int)&v48,
        (_DWORD)this + 168,
        v50 + 168,
        (__int64)&v61);
    }
    InConnection::ClearSlowSync(this, (const struct _GUID *)(v40 + 168));
    goto LABEL_101;
  }
  if ( v13 == 1 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v42 = L"InConnection::CommitSession";
      v43 = 5411;
      v44 = 4;
      v45 = L"INCO";
      v61 = *(_QWORD *)(v50 + 200) + 18LL;
      v48 = L"SubordinateSync";
      dbgobj::DbgPrint<unsigned short,unsigned short const *,_GUID,_GUID,unsigned short const *>(
        (unsigned int)&v42,
        (unsigned int)L"Committed %s session connId:%? csId:%? csName:%?",
        (unsigned int)&v48,
        (_DWORD)this + 168,
        v50 + 168,
        (__int64)&v61);
    }
    std::list<SessionInfo>::clear((char *)a2 + 184);
LABEL_101:
    SessionTask::CheckHibernate(*((SessionTask **)a2 + 9));
    goto LABEL_102;
  }
  v14 = v50;
  if ( *(_QWORD *)(v11 + 8) )
  {
    v61 = 0;
    *(_OWORD *)v58 = 0;
    VolumeManager = (struct FrsStatus *)ContentSetManager::GetVolumeManager(v50, &v61, v12);
    v15 = (struct FrsStatus *)v61;
    if ( !VolumeManager )
    {
      if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugVolumeManagerRefCount)
        && g_DebugLog
        && LODWORD(g_DebugLog[1].LockSemaphore)
        && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        v52 = L"InConnection::CommitSession";
        v53 = 5436;
        v54 = 5;
        v55 = L"INCO";
        v46 = v15;
        dbgobj::DbgPrint<unsigned short,unsigned __int64>(
          &v52,
          L"[VMREF] Added reference to volume manager. ptr:%p",
          &v46);
      }
      v16 = *(__int64 (__fastcall **)(struct FrsStatus *, struct DbManager **, _QWORD))(*(_QWORD *)v15 + 32LL);
      CurrentThreadId = GetCurrentThreadId();
      VolumeManager = (struct FrsStatus *)v16(v15, v58, CurrentThreadId);
      if ( !VolumeManager )
        VolumeManager = DbUtil::UpdateVersionVector(
                          v58[0],
                          (const struct _GUID *)(v14 + 168),
                          v49,
                          0,
                          (const volatile int *)this + 12);
    }
    if ( v15 )
    {
      if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugVolumeManagerRefCount)
        && g_DebugLog
        && LODWORD(g_DebugLog[1].LockSemaphore)
        && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        v52 = L"InConnection::CommitSession";
        v53 = 5449;
        v54 = 5;
        v55 = L"INCO";
        v46 = v15;
        dbgobj::DbgPrint<unsigned short,unsigned __int64>(
          &v52,
          L"[VMREF] Release reference to volume manager. ptr:%p",
          &v46);
      }
      ScopedRef<VolumeManager::ShutdownRestartTask>::Set(&v61, 0);
    }
    DbManagerInstance::FinalizeDbManagerInstance((DbManagerInstance *)v58);
    ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v61);
  }
  v18 = *(_DWORD *)(v14 + 592);
  if ( !VolumeManager && (v18 == 5 || v18 == 2) && *((_QWORD *)a2 + 17) )
    VolumeManager = InConnection::CheckFinishInitialSync(this, a2);
  v47 = 0;
  if ( !VolumeManager )
  {
    VolumeManager = (struct FrsStatus *)InConnection::GetReplicaSetManager(this, &v47);
    if ( !VolumeManager
      && (unsigned int)ReplicaSetManager::IsSysVolGroup(v47)
      && *((_QWORD *)a2 + 26)
      && !*((_DWORD *)a2 + 54) )
    {
      VolumeManager = InConnection::CheckSysVolSynced(this, a2);
    }
  }
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v47);
  std::map<_GUID,LdbManager::VvCompactMan::VvInfo>::map<_GUID,LdbManager::VvCompactMan::VvInfo>(&v52);
  *(_OWORD *)v59 = 0;
  v47 = 0;
  v19 = v50;
  v46 = (struct FrsStatus *)ContentSetManager::GetVolumeManager(v50, &v47, v20);
  v21 = v47;
  if ( v46 )
    goto LABEL_46;
  if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugVolumeManagerRefCount)
    && g_DebugLog
    && LODWORD(g_DebugLog[1].LockSemaphore)
    && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v42 = L"InConnection::CommitSession";
    v43 = 5496;
    v44 = 5;
    v45 = L"INCO";
    v46 = v21;
    dbgobj::DbgPrint<unsigned short,unsigned __int64>(&v42, L"[VMREF] Added reference to volume manager. ptr:%p", &v46);
  }
  v22 = *(__int64 (__fastcall **)(struct FrsStatus *, struct DbManager **, _QWORD))(*(_QWORD *)v21 + 32LL);
  v23 = GetCurrentThreadId();
  v46 = (struct FrsStatus *)v22(v21, v59, v23);
  if ( v46
    || (v46 = DbUtil::VersionVector(v59[0], (const struct _GUID *)(v19 + 168), (struct VersionChainVector *)&v52)) != 0 )
  {
LABEL_46:
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v42 = L"InConnection::CommitSession";
      v43 = 5508;
      v44 = 3;
      v45 = L"INCO";
      v57 = VersionChainVector::NumberOfIntervals(v49);
      v48 = (const wchar_t *)(*(_QWORD *)(v19 + 200) + 18LL);
      dbgobj::DbgPrint<unsigned short,_GUID,_GUID,unsigned short const *,unsigned long,unsigned __int64,FrsStatus>(
        (unsigned int)&v42,
        v25,
        (_DWORD)this + 168,
        v19 + 168,
        (__int64)&v48,
        v24 + 60,
        (__int64)&v57,
        v26);
    }
    CLEAR_ERROR(&v46);
  }
  else if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v42 = L"InConnection::CommitSession";
    v43 = 5518;
    v44 = 5;
    v45 = L"INCO";
    v48 = (const wchar_t *)VersionChainVector::NumberOfIntervals((VersionChainVector *)&v52);
    v57 = VersionChainVector::NumberOfIntervals(v49);
    v46 = (struct FrsStatus *)(*(_QWORD *)(v19 + 200) + 18LL);
    dbgobj::DbgPrint<unsigned short,_GUID,_GUID,unsigned short const *,unsigned long,unsigned __int64,unsigned __int64,VersionChainVector>(
      (unsigned int)&v42,
      v34 + 60,
      (_DWORD)this + 168,
      v19 + 168,
      (__int64)&v46,
      v34 + 60,
      (__int64)&v57,
      (__int64)&v48,
      (__int64)&v52);
  }
  if ( v21 )
  {
    if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugVolumeManagerRefCount)
      && g_DebugLog
      && LODWORD(g_DebugLog[1].LockSemaphore)
      && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v42 = L"InConnection::CommitSession";
      v43 = 5528;
      v44 = 5;
      v45 = L"INCO";
      v48 = (const wchar_t *)v21;
      dbgobj::DbgPrint<unsigned short,unsigned __int64>(
        &v42,
        L"[VMREF] Release reference to volume manager. ptr:%p",
        &v48);
    }
    ScopedRef<VolumeManager::ShutdownRestartTask>::Set(&v47, 0);
  }
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v47);
  DbManagerInstance::FinalizeDbManagerInstance((DbManagerInstance *)v59);
  std::_Tree<std::_Tmap_traits<Guid,IntervalSet,std::less<Guid>,std::allocator<std::pair<Guid const,IntervalSet>>,0>>::~_Tree<std::_Tmap_traits<Guid,IntervalSet,std::less<Guid>,std::allocator<std::pair<Guid const,IntervalSet>>,0>>(&v52);
  if ( *((_DWORD *)v49 + 14) )
    ++*((_DWORD *)a2 + 58);
  ++*((_DWORD *)a2 + 57);
  std::list<SessionInfo>::erase((char *)a2 + 80, v60, v62);
  SessionTask::CheckHibernate(*((SessionTask **)a2 + 9));
  if ( (unsigned int)InConnection::InSync(this) )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v42 = L"InConnection::CommitSession";
      v43 = 5545;
      v44 = 4;
      v45 = L"INCO";
      v48 = (const wchar_t *)(*(_QWORD *)(v19 + 200) + 18LL);
      dbgobj::DbgPrint<unsigned short,_GUID,_GUID,unsigned short const *,unsigned long>(
        (unsigned int)&v42,
        v27,
        (_DWORD)this + 168,
        v19 + 168,
        (__int64)&v48,
        (__int64)a2 + 232);
    }
    v28 = g_MonitorContext;
    EnterCriticalSection((LPCRITICAL_SECTION)g_MonitorContext + 15);
    *((_DWORD *)v28 + 148) = 1;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v42 = L"InConnection::CommitSession";
      v43 = 5551;
      v44 = 5;
      v45 = L"INCO";
      dbgobj::DbgPrint<unsigned short>(&v42, L"Update syncInfoHistory");
    }
    *((_DWORD *)this + 152) = 4;
    if ( *((_DWORD *)a2 + 58) )
    {
      *((_DWORD *)this + 152) = 6;
      *((_DWORD *)this + 148) = 8;
      *((_DWORD *)this + 151) = 0;
      GetSystemTimeAsFileTime((LPFILETIME)((char *)this + 596));
    }
    StateHistory::Update(
      (struct MonitorContext *)((char *)g_MonitorContext + 536),
      (InConnection *)((char *)this + 536));
    v29 = (struct _RTL_CRITICAL_SECTION *)g_MonitorContext;
    *((_DWORD *)g_MonitorContext + 148) = 0;
    LeaveCriticalSection(v29 + 15);
    *((_QWORD *)a2 + 29) = 0;
    SystemTimeAsFileTime = 0;
    LODWORD(v49) = 0;
    LODWORD(v61) = 0;
    v56 = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    InConnection::UpdateBandwidth(this, (int *)&v49, (unsigned int *)&v61, &v56);
    v30 = g_MonitorContext;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_MonitorContext + 496));
    *((_DWORD *)v30 + 122) = 1;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v42 = L"InConnection::CommitSession";
      v43 = 5575;
      v44 = 5;
      v45 = L"INCO";
      dbgobj::DbgPrint<unsigned short>(&v42, L"Update cxtionInfoHistory");
    }
    *(_QWORD *)((char *)this + 924) = *(_QWORD *)((char *)this + 932);
    *((_DWORD *)this + 237) = FileTime::Diff(&SystemTimeAsFileTime, (const struct _FILETIME *)((char *)this + 932))
                            / 0x3E8;
    *(_QWORD *)((char *)this + 940) = v31;
    v47 = (ReplicaSetManager *)(10000LL * (unsigned int)v61 + *(_QWORD *)&SystemTimeAsFileTime);
    v46 = v47;
    *v32 = v47;
    StateHistory::Update(
      (struct MonitorContext *)((char *)g_MonitorContext + 432),
      (InConnection *)((char *)this + 752));
    v33 = g_MonitorContext;
    *((_DWORD *)g_MonitorContext + 122) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v33 + 496));
    if ( *((_DWORD *)this + 264) == 4 )
    {
      *((_QWORD *)this + 132) = 1;
      *((_QWORD *)this + 133) = 0;
      *((_QWORD *)this + 134) = 0;
      *((_DWORD *)this + 270) = 0;
      InConnection::ReConfigure(this);
      InConnection::LogModeChangeEvent(this, 4, *((unsigned int *)this + 264), 0, 0);
    }
  }
  else
  {
    v35 = g_MonitorContext;
    EnterCriticalSection((LPCRITICAL_SECTION)g_MonitorContext + 15);
    *((_DWORD *)v35 + 148) = 1;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v42 = L"InConnection::CommitSession";
      v43 = 5603;
      v44 = 5;
      v45 = L"INCO";
      dbgobj::DbgPrint<unsigned short>(&v42, L"Update syncInfoHistory");
    }
    if ( *((_DWORD *)this + 152) != 2 || !(unsigned int)HistoryRecord::IsVisible((InConnection *)((char *)this + 536)) )
    {
      *((_DWORD *)this + 152) = 2;
      *((_DWORD *)this + 153) = ReplModeToInitReason(*((unsigned int *)this + 264));
      if ( ((v36 - 2) & 0xFFFFFFFD) == 0 )
      {
        *((_QWORD *)this + 92) = *(_QWORD *)((char *)this + 1068);
        *((_DWORD *)this + 186) = Config::ScheduleParam::MapKbpsToBandwidthLevel(*((unsigned int *)this + 269));
      }
      StateHistory::Update(
        (struct MonitorContext *)((char *)g_MonitorContext + 536),
        (InConnection *)((char *)this + 536));
    }
    v37 = (struct _RTL_CRITICAL_SECTION *)g_MonitorContext;
    *((_DWORD *)g_MonitorContext + 148) = 0;
    LeaveCriticalSection(v37 + 15);
  }
  if ( VolumeManager )
  {
    v38 = GetCurrentThreadId();
    v7 = FrsStatusList::PushNewError(
           v39,
           *((unsigned int *)VolumeManager + 1),
           *((unsigned int *)VolumeManager + 2),
           *(unsigned int *)VolumeManager,
           "base\\fs\\remotefs\\frs\\src\\sync\\inconnection.cpp",
           "InConnection::CommitSession",
           5621,
           v38,
           VolumeManager);
  }
LABEL_102:
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v50);
  return v7;
}

```

## disassembly

```asm
0x140161300  mov     [rsp-8+arg_0], rbx
0x140161305  mov     [rsp-8+arg_10], r8
0x14016130a  push    rbp
0x14016130b  push    rsi
0x14016130c  push    rdi
0x14016130d  push    r12
0x14016130f  push    r13
0x140161311  push    r14
0x140161313  push    r15
0x140161315  lea     rbp, [rsp-27h]
0x14016131a  sub     rsp, 100h
0x140161321  mov     ebx, r9d
0x140161324  mov     r13, rdx
0x140161327  mov     r15, rcx
0x14016132a  xor     r14d, r14d
0x14016132d  mov     r12d, r14d
0x140161330  mov     [rbp+57h+var_A8], r14
0x140161334  mov     rcx, [rdx+20h]; this
0x140161338  test    rcx, rcx
0x14016133b  jnz     short loc_140161342
0x14016133d  mov     edx, r14d
0x140161340  jmp     short loc_14016134B
0x140161342  call    ?AddRef@RefCountObject@@QEAAJXZ; RefCountObject::AddRef(void)
0x140161347  mov     rdx, [r13+20h]
0x14016134b  lea     rcx, [rbp+57h+var_A8]
0x14016134f  call    ?Set@?$ScopedRef@VShutdownRestartTask@VolumeManager@@@@AEAAXPEAVShutdownRestartTask@VolumeManager@@@Z; ScopedRef<VolumeManager::ShutdownRestartTask>::Set(VolumeManager::ShutdownRestartTask *)
0x140161354  lea     rcx, [rbp+57h+arg_10]
0x140161358  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@UCONTENT_SET_RECORD@@@std@@@std@@@std@@QEBAPEAUCONTENT_SET_RECORD@@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<CONTENT_SET_RECORD>>>::operator->(void)
0x14016135d  mov     [rbp+57h+var_B0], rax
0x140161361  cmp     [rax+40h], r14d
0x140161365  jnz     loc_140161E5B
0x14016136b  cmp     [rax+34h], r14d
0x14016136f  jnz     loc_140161E5B
0x140161375  sub     ebx, 1
0x140161378  jz      loc_140161DB5
0x14016137e  cmp     ebx, 1
0x140161381  jz      loc_140161D14
0x140161387  lea     rsi, aInconnectionCo; "InConnection::CommitSession"
0x14016138e  mov     rdi, [rbp+57h+var_A8]
0x140161392  cmp     [rax+8], r14
0x140161396  jz      loc_1401614F9
0x14016139c  mov     [rbp+57h+arg_8], r14
0x1401613a0  xorps   xmm0, xmm0
0x1401613a3  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x1401613a8  lea     rdx, [rbp+57h+arg_8]
0x1401613ac  mov     rcx, rdi
0x1401613af  call    ?GetVolumeManager@ContentSetManager@@QEAAPEAVFrsStatus@@AEAV?$ScopedRef@VVolumeManager@@@@@Z; ContentSetManager::GetVolumeManager(ScopedRef<VolumeManager> &)
0x1401613b4  mov     r12, rax
0x1401613b7  mov     rbx, [rbp+57h+arg_8]
0x1401613bb  test    rax, rax
0x1401613be  jnz     loc_140161478
0x1401613c4  lea     rcx, ?DebugVolumeManagerRefCount@Settings@@3VCDebugVolumeManagerRefCount@1@A; Settings::CDebugVolumeManagerRefCount Settings::DebugVolumeManagerRefCount
0x1401613cb  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x1401613d0  test    eax, eax
0x1401613d2  jz      short loc_140161421
0x1401613d4  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401613db  test    rax, rax
0x1401613de  jz      short loc_140161421
0x1401613e0  cmp     [rax+40h], r14d
0x1401613e4  jz      short loc_140161421
0x1401613e6  cmp     dword ptr [rax+38h], 5
0x1401613ea  jl      short loc_140161421
0x1401613ec  mov     [rbp+57h+var_98], rsi
0x1401613f0  mov     [rbp+57h+var_90], 153Ch
0x1401613f7  mov     [rbp+57h+var_8C], 5
0x1401613fe  lea     rax, aInco; "INCO"
0x140161405  mov     [rbp+57h+var_88], rax
0x140161409  mov     [rbp+57h+var_C8], rbx
0x14016140d  lea     r8, [rbp+57h+var_C8]
0x140161411  lea     rdx, aVmrefAddedRefe; "[VMREF] Added reference to volume manag"...
0x140161418  lea     rcx, [rbp+57h+var_98]
0x14016141c  call    ??$DbgPrint@G_K@dbgobj@@QEAA_KPEBGAEB_K@Z; dbgobj::DbgPrint<ushort,unsigned __int64>(ushort const *,unsigned __int64 const &)
0x140161421  mov     rax, [rbx]
0x140161424  mov     rsi, [rax+20h]
0x140161428  call    cs:__imp_GetCurrentThreadId
0x14016142f  nop     dword ptr [rax+rax+00h]
0x140161434  mov     r8d, eax
0x140161437  lea     rdx, [rbp+57h+var_70]
0x14016143b  mov     rcx, rbx
0x14016143e  mov     rax, rsi
0x140161441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140161446  mov     r12, rax
0x140161449  test    rax, rax
0x14016144c  jnz     short loc_140161471
0x14016144e  lea     rdx, [rdi+0A8h]; struct _GUID *
0x140161455  lea     rax, [r15+30h]
0x140161459  mov     [rsp+130h+var_110], rax; volatile int *
0x14016145e  xor     r9d, r9d; int
0x140161461  mov     r8, [rbp+57h+var_B0]; struct VersionChainVector *
0x140161465  mov     rcx, [rbp+57h+var_70]; struct DbManager *
0x140161469  call    ?UpdateVersionVector@DbUtil@@SAPEAVFrsStatus@@PEAVDbManager@@AEBU_GUID@@AEBVVersionChainVector@@HAEDH@Z; DbUtil::UpdateVersionVector(DbManager *,_GUID const &,VersionChainVector const &,int,int const volatile &)
0x14016146e  mov     r12, rax
0x140161471  lea     rsi, aInconnectionCo; "InConnection::CommitSession"
0x140161478  test    rbx, rbx
0x14016147b  jz      short loc_1401614E6
0x14016147d  lea     rcx, ?DebugVolumeManagerRefCount@Settings@@3VCDebugVolumeManagerRefCount@1@A; Settings::CDebugVolumeManagerRefCount Settings::DebugVolumeManagerRefCount
0x140161484  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x140161489  test    eax, eax
0x14016148b  jz      short loc_1401614DA
0x14016148d  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140161494  test    rax, rax
0x140161497  jz      short loc_1401614DA
0x140161499  cmp     [rax+40h], r14d
0x14016149d  jz      short loc_1401614DA
0x14016149f  cmp     dword ptr [rax+38h], 5
0x1401614a3  jl      short loc_1401614DA
0x1401614a5  mov     [rbp+57h+var_98], rsi
0x1401614a9  mov     [rbp+57h+var_90], 1549h
0x1401614b0  mov     [rbp+57h+var_8C], 5
0x1401614b7  lea     rax, aInco; "INCO"
0x1401614be  mov     [rbp+57h+var_88], rax
0x1401614c2  mov     [rbp+57h+var_C8], rbx
0x1401614c6  lea     r8, [rbp+57h+var_C8]
0x1401614ca  lea     rdx, aVmrefReleaseRe; "[VMREF] Release reference to volume man"...
0x1401614d1  lea     rcx, [rbp+57h+var_98]
0x1401614d5  call    ??$DbgPrint@G_K@dbgobj@@QEAA_KPEBGAEB_K@Z; dbgobj::DbgPrint<ushort,unsigned __int64>(ushort const *,unsigned __int64 const &)
0x1401614da  xor     edx, edx
0x1401614dc  lea     rcx, [rbp+57h+arg_8]
0x1401614e0  call    ?Set@?$ScopedRef@VShutdownRestartTask@VolumeManager@@@@AEAAXPEAVShutdownRestartTask@VolumeManager@@@Z; ScopedRef<VolumeManager::ShutdownRestartTask>::Set(VolumeManager::ShutdownRestartTask *)
0x1401614e5  nop
0x1401614e6  lea     rcx, [rbp+57h+var_70]; this
0x1401614ea  call    ?FinalizeDbManagerInstance@DbManagerInstance@@QEAAXXZ; DbManagerInstance::FinalizeDbManagerInstance(void)
0x1401614ef  nop
0x1401614f0  lea     rcx, [rbp+57h+arg_8]
0x1401614f4  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x1401614f9  mov     eax, [rdi+250h]
0x1401614ff  test    r12, r12
0x140161502  jnz     short loc_140161525
0x140161504  cmp     eax, 5
0x140161507  jz      short loc_14016150E
0x140161509  cmp     eax, 2
0x14016150c  jnz     short loc_140161525
0x14016150e  cmp     [r13+88h], r14
0x140161515  jz      short loc_140161525
0x140161517  mov     rdx, r13; struct InConnection::InConnectionContentSetContext *
0x14016151a  mov     rcx, r15; this
0x14016151d  call    ?CheckFinishInitialSync@InConnection@@AEAAPEAVFrsStatus@@AEAVInConnectionContentSetContext@1@@Z; InConnection::CheckFinishInitialSync(InConnection::InConnectionContentSetContext &)
0x140161522  mov     r12, rax
0x140161525  mov     [rbp+57h+var_C0], r14
0x140161529  test    r12, r12
0x14016152c  jnz     short loc_14016156F
0x14016152e  lea     rdx, [rbp+57h+var_C0]
0x140161532  mov     rcx, r15
0x140161535  call    ?GetReplicaSetManager@InConnection@@QEAAPEAVFrsStatus@@AEAV?$ScopedRef@VReplicaSetManager@@@@@Z; InConnection::GetReplicaSetManager(ScopedRef<ReplicaSetManager> &)
0x14016153a  mov     r12, rax
0x14016153d  test    rax, rax
0x140161540  jnz     short loc_14016156F
0x140161542  mov     rcx, [rbp+57h+var_C0]; this
0x140161546  call    ?IsSysVolGroup@ReplicaSetManager@@QEAAHXZ; ReplicaSetManager::IsSysVolGroup(void)
0x14016154b  test    eax, eax
0x14016154d  jz      short loc_14016156F
0x14016154f  cmp     [r13+0D0h], r14
0x140161556  jz      short loc_14016156F
0x140161558  cmp     [r13+0D8h], r14d
0x14016155f  jnz     short loc_14016156F
0x140161561  mov     rdx, r13; struct InConnection::InConnectionContentSetContext *
0x140161564  mov     rcx, r15; this
0x140161567  call    ?CheckSysVolSynced@InConnection@@AEAAPEAVFrsStatus@@AEAVInConnectionContentSetContext@1@@Z; InConnection::CheckSysVolSynced(InConnection::InConnectionContentSetContext &)
0x14016156c  mov     r12, rax
0x14016156f  lea     rcx, [rbp+57h+var_C0]
0x140161573  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x140161578  lea     rcx, [rbp+57h+var_98]
0x14016157c  call    ??0?$map@U_GUID@@VVvInfo@VvCompactMan@LdbManager@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@VVvInfo@VvCompactMan@LdbManager@@@std@@@6@@std@@QEAA@XZ; std::map<_GUID,LdbManager::VvCompactMan::VvInfo>::map<_GUID,LdbManager::VvCompactMan::VvInfo>(void)
0x140161581  nop
0x140161582  xorps   xmm0, xmm0
0x140161585  movdqu  xmmword ptr [rbp+57h+var_58], xmm0
0x14016158a  mov     [rbp+57h+var_C0], r14
0x14016158e  lea     rdx, [rbp+57h+var_C0]
0x140161592  mov     rbx, [rbp+57h+var_A8]
0x140161596  mov     rcx, rbx
0x140161599  call    ?GetVolumeManager@ContentSetManager@@QEAAPEAVFrsStatus@@AEAV?$ScopedRef@VVolumeManager@@@@@Z; ContentSetManager::GetVolumeManager(ScopedRef<VolumeManager> &)
0x14016159e  mov     r10, rax
0x1401615a1  mov     [rbp+57h+var_C8], rax
0x1401615a5  mov     rdi, [rbp+57h+var_C0]
0x1401615a9  test    rax, rax
0x1401615ac  jnz     loc_140161667
0x1401615b2  lea     rcx, ?DebugVolumeManagerRefCount@Settings@@3VCDebugVolumeManagerRefCount@1@A; Settings::CDebugVolumeManagerRefCount Settings::DebugVolumeManagerRefCount
0x1401615b9  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x1401615be  test    eax, eax
0x1401615c0  jz      short loc_140161612
0x1401615c2  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401615c9  test    rax, rax
0x1401615cc  jz      short loc_140161612
0x1401615ce  cmp     [rax+40h], r14d
0x1401615d2  jz      short loc_140161612
0x1401615d4  cmp     dword ptr [rax+38h], 5
0x1401615d8  jl      short loc_140161612
0x1401615da  mov     [rsp+130h+var_E0], rsi
0x1401615df  mov     [rsp+130h+var_D8], 1578h
0x1401615e7  mov     [rbp+57h+var_D4], 5
0x1401615ee  lea     rax, aInco; "INCO"
0x1401615f5  mov     [rbp+57h+var_D0], rax
0x1401615f9  mov     [rbp+57h+var_C8], rdi
0x1401615fd  lea     r8, [rbp+57h+var_C8]
0x140161601  lea     rdx, aVmrefAddedRefe; "[VMREF] Added reference to volume manag"...
0x140161608  lea     rcx, [rsp+130h+var_E0]
0x14016160d  call    ??$DbgPrint@G_K@dbgobj@@QEAA_KPEBGAEB_K@Z; dbgobj::DbgPrint<ushort,unsigned __int64>(ushort const *,unsigned __int64 const &)
0x140161612  mov     rax, [rdi]
0x140161615  mov     rsi, [rax+20h]
0x140161619  call    cs:__imp_GetCurrentThreadId
0x140161620  nop     dword ptr [rax+rax+00h]
0x140161625  mov     r8d, eax
0x140161628  lea     rdx, [rbp+57h+var_58]
0x14016162c  mov     rcx, rdi
0x14016162f  mov     rax, rsi
0x140161632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140161637  mov     r10, rax
0x14016163a  mov     [rbp+57h+var_C8], rax
0x14016163e  test    rax, rax
0x140161641  jnz     short loc_140161667
0x140161643  lea     rdx, [rbx+0A8h]; struct _GUID *
0x14016164a  lea     r8, [rbp+57h+var_98]; struct VersionChainVector *
0x14016164e  mov     rcx, [rbp+57h+var_58]; struct DbManager *
0x140161652  call    ?VersionVector@DbUtil@@SAPEAVFrsStatus@@PEAVDbManager@@AEBU_GUID@@AEAVVersionChainVector@@@Z; DbUtil::VersionVector(DbManager *,_GUID const &,VersionChainVector &)
0x140161657  mov     r10, rax
0x14016165a  mov     [rbp+57h+var_C8], rax
0x14016165e  test    rax, rax
0x140161661  jz      loc_140161AEF
0x140161667  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14016166e  test    rax, rax
0x140161671  jz      loc_140161704
0x140161677  cmp     [rax+40h], r14d
0x14016167b  jz      loc_140161704
0x140161681  cmp     dword ptr [rax+38h], 3
0x140161685  jl      short loc_140161704
0x140161687  lea     rax, aInconnectionCo; "InConnection::CommitSession"
0x14016168e  mov     [rsp+130h+var_E0], rax
0x140161693  mov     [rsp+130h+var_D8], 1584h
0x14016169b  mov     [rbp+57h+var_D4], 3
0x1401616a2  lea     rax, aInco; "INCO"
0x1401616a9  mov     [rbp+57h+var_D0], rax
0x1401616ad  mov     r11, [rbp+57h+var_B0]
0x1401616b1  mov     rcx, r11; this
0x1401616b4  call    ?NumberOfIntervals@VersionChainVector@@QEBA_KXZ; VersionChainVector::NumberOfIntervals(void)
0x1401616b9  mov     [rbp+57h+var_78], rax
0x1401616bd  lea     rcx, [r11+3Ch]
0x1401616c1  mov     rax, [rbx+0C8h]
0x1401616c8  add     rax, 12h
0x1401616cc  mov     [rbp+57h+var_B8], rax
0x1401616d0  lea     r9, [rbx+0A8h]
0x1401616d7  lea     r8, [r15+0A8h]
0x1401616de  mov     [rsp+130h+var_F8], r10
0x1401616e3  lea     rax, [rbp+57h+var_78]
0x1401616e7  mov     [rsp+130h+var_100], rax
0x1401616ec  mov     [rsp+130h+var_108], rcx
0x1401616f1  lea     rax, [rbp+57h+var_B8]
0x1401616f5  mov     [rsp+130h+var_110], rax
0x1401616fa  lea     rcx, [rsp+130h+var_E0]
0x1401616ff  call    ??$DbgPrint@GU_GUID@@U1@PEBGK_KVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBU_GUID@@1AEBQEBGAEBKAEB_KAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID,ushort const *,ulong,unsigned __int64,FrsStatus>(ushort const *,_GUID const &,_GUID const &,ushort const * const &,ulong const &,unsigned __int64 const &,FrsStatus const &)
0x140161704  lea     rcx, [rbp+57h+var_C8]; struct FrsStatus **
0x140161708  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x14016170d  lea     rsi, aInconnectionCo; "InConnection::CommitSession"
0x140161714  test    rdi, rdi
0x140161717  jz      short loc_140161785
0x140161719  lea     rcx, ?DebugVolumeManagerRefCount@Settings@@3VCDebugVolumeManagerRefCount@1@A; Settings::CDebugVolumeManagerRefCount Settings::DebugVolumeManagerRefCount
0x140161720  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x140161725  test    eax, eax
0x140161727  jz      short loc_140161779
0x140161729  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140161730  test    rax, rax
0x140161733  jz      short loc_140161779
0x140161735  cmp     [rax+40h], r14d
0x140161739  jz      short loc_140161779
0x14016173b  cmp     dword ptr [rax+38h], 5
0x14016173f  jl      short loc_140161779
0x140161741  mov     [rsp+130h+var_E0], rsi
0x140161746  mov     [rsp+130h+var_D8], 1598h
0x14016174e  mov     [rbp+57h+var_D4], 5
0x140161755  lea     rax, aInco; "INCO"
0x14016175c  mov     [rbp+57h+var_D0], rax
0x140161760  mov     [rbp+57h+var_B8], rdi
0x140161764  lea     r8, [rbp+57h+var_B8]
0x140161768  lea     rdx, aVmrefReleaseRe; "[VMREF] Release reference to volume man"...
0x14016176f  lea     rcx, [rsp+130h+var_E0]
0x140161774  call    ??$DbgPrint@G_K@dbgobj@@QEAA_KPEBGAEB_K@Z; dbgobj::DbgPrint<ushort,unsigned __int64>(ushort const *,unsigned __int64 const &)
0x140161779  xor     edx, edx
0x14016177b  lea     rcx, [rbp+57h+var_C0]
0x14016177f  call    ?Set@?$ScopedRef@VShutdownRestartTask@VolumeManager@@@@AEAAXPEAVShutdownRestartTask@VolumeManager@@@Z; ScopedRef<VolumeManager::ShutdownRestartTask>::Set(VolumeManager::ShutdownRestartTask *)
0x140161784  nop
0x140161785  lea     rcx, [rbp+57h+var_C0]
0x140161789  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x14016178e  nop
0x14016178f  lea     rcx, [rbp+57h+var_58]; this
0x140161793  call    ?FinalizeDbManagerInstance@DbManagerInstance@@QEAAXXZ; DbManagerInstance::FinalizeDbManagerInstance(void)
0x140161798  nop
0x140161799  lea     rcx, [rbp+57h+var_98]
0x14016179d  call    ??1?$_Tree@V?$_Tmap_traits@VGuid@@VIntervalSet@@U?$less@VGuid@@@std@@V?$allocator@U?$pair@$$CBVGuid@@VIntervalSet@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<Guid,IntervalSet,std::less<Guid>,std::allocator<std::pair<Guid const,IntervalSet>>,0>>::~_Tree<std::_Tmap_traits<Guid,IntervalSet,std::less<Guid>,std::allocator<std::pair<Guid const,IntervalSet>>,0>>(void)
0x1401617a2  mov     rax, [rbp+57h+var_B0]
0x1401617a6  cmp     [rax+38h], r14d
0x1401617aa  jz      short loc_1401617B3
0x1401617ac  inc     dword ptr [r13+0E8h]
0x1401617b3  inc     dword ptr [r13+0E4h]
0x1401617ba  lea     rcx, [r13+50h]
0x1401617be  mov     r8, [rbp+57h+arg_10]
0x1401617c2  lea     rdx, [rbp+57h+var_40]
0x1401617c6  call    ?erase@?$list@VSessionInfo@@V?$allocator@VSessionInfo@@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@VSessionInfo@@@std@@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@VSessionInfo@@@std@@@std@@@2@@Z; std::list<SessionInfo>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<SessionInfo>>>)
0x1401617cb  mov     rcx, [r13+48h]; this
0x1401617cf  call    ?CheckHibernate@SessionTask@@QEAAXXZ; SessionTask::CheckHibernate(void)
0x1401617d4  mov     rcx, r15; this
0x1401617d7  call    ?InSync@InConnection@@AEAAHXZ; InConnection::InSync(void)
  ... truncated ...
```
