# SubordinateMonitor::Step(void)

- ea: `0x140192a90`
- end: `0x1401939c2`
- name: `?Step@SubordinateMonitor@@UEAA?AW4STEP_RESULT@Task@@XZ`
- size: `3890`
- prototype: ``
- caller_count: `0`
- callee_count: `44`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1400036a0`
- `0x14000c910`
- `0x14000cdc0`
- `0x14000d980`
- `0x14000dcc0`
- `0x14000e34c`
- `0x14000ee94`
- `0x140011408`
- `0x14001e704`
- `0x14002bf70`
- `0x14002c2f4`
- `0x14002c404`
- `0x1400370bc`
- `0x1400391c4`
- `0x14006b654`
- `0x14007acf8`
- `0x14007b760`
- `0x14007dedc`
- `0x140086dcc`
- `0x1400923f8`
- `0x1400e61a0`
- `0x140111380`
- `0x1401627fc`
- `0x140190768`
- `0x1401909b0`
- `0x140190a74`
- `0x140190d90`
- `0x14019113c`
- `0x1401914e8`
- `0x140191efc`
- `0x140191f94`
- `0x1401926c0`
- `0x14019283c`
- `0x140192a90`
- `0x1401bda10`
- `0x1401c3a0c`
- `0x1401c3abc`
- `0x1401c3afc`
- `0x1401c3bc0`
- `0x1401c3be4`
- `0x1401c3ce4`
- `0x1401c3d7c`
- `0x1401c4940`
- `0x140223010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140192c3e`
- `KERNEL32!LeaveCriticalSection` at `0x140192ebb`
- `KERNEL32!LeaveCriticalSection` at `0x14019313c`
- `KERNEL32!LeaveCriticalSection` at `0x140192c3e`
- `KERNEL32!LeaveCriticalSection` at `0x140192ebb`
- `KERNEL32!LeaveCriticalSection` at `0x14019313c`
- `KERNEL32!EnterCriticalSection` at `0x140192eea`
- `KERNEL32!EnterCriticalSection` at `0x140193176`
- `KERNEL32!EnterCriticalSection` at `0x140192eea`
- `KERNEL32!EnterCriticalSection` at `0x140193176`
- `KERNEL32!GetCurrentThreadId` at `0x140192d09`
- `KERNEL32!GetCurrentThreadId` at `0x1401936a5`
- `KERNEL32!GetCurrentThreadId` at `0x140192d09`
- `KERNEL32!GetCurrentThreadId` at `0x1401936a5`

## string_xrefs

- `0x1401931fc`: `Upstream version vector retrieved from context. connId:%? csId:%?`
- `0x140193342`: `BLOCK. No credit available. connId:%? csId:%?`
- `0x140193274`: `Upstream version vector requested from upstream. connId:%? csId:%?`
- `0x140192b6b`: `state:%? connId:%? csId:%?`
- `0x1401938f8`: `Wait for local version change. connId:%? csId:%?`
- `0x1401933b9`: `Checking if there is any new local update.  connId:%? csId:%?`
- `0x140193893`: `Updates from previous sessions were dropped. Reprocess updates. connId:%? csId:%?`
- `0x14019357d`: `No local update is found.  connId:%? csId:%?`
- `0x140193112`: `Task is run without an error in REQUEST_VVUP_PENDING state.`
- `0x14019351a`: `Local update is found. connId:%? csId:%?`
- `0x140192c13`: `Task is run in WAIT_SUBMIT_LOCAL_UPDATES state. Ignored.`
- `0x140192e9b`: `Upstream version vector dominates. connId:%? csId:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall SubordinateMonitor::Step(__int64 a1)
{
  char v2; // r14
  unsigned int v3; // r15d
  LPCRITICAL_SECTION v4; // rdx
  __int64 v5; // rdi
  __int64 v6; // rbx
  int CurrentStateString; // eax
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  const wchar_t *v14; // rdx
  const wchar_t **v15; // rcx
  int v16; // eax
  __int64 v17; // r8
  struct FrsStatus *VolumeManager; // rdi
  struct FrsStatus *v19; // rbx
  __int64 (__fastcall *v20)(struct FrsStatus *, struct DbManager **, _QWORD); // rdi
  DWORD v21; // eax
  int v22; // edx
  int v23; // ebx
  __int64 v24; // rax
  int v25; // ecx
  _QWORD *v26; // rax
  _QWORD **v27; // rcx
  _QWORD *v28; // rax
  _QWORD **v29; // rcx
  int v30; // ebx
  LPCRITICAL_SECTION v31; // rax
  _QWORD *v32; // rax
  _QWORD **v33; // rcx
  int v34; // edx
  int v35; // eax
  __int64 v36; // r8
  struct FrsStatus *v37; // rbx
  __int64 (__fastcall *v38)(struct FrsStatus *, __int128 *, _QWORD); // rdi
  DWORD CurrentThreadId; // eax
  struct DbManager *v41[2]; // [rsp+48h] [rbp-C0h] BYREF
  const wchar_t *v42; // [rsp+58h] [rbp-B0h]
  int v43[2]; // [rsp+60h] [rbp-A8h] BYREF
  struct FrsStatus *v44; // [rsp+68h] [rbp-A0h] BYREF
  struct FrsStatus *v45; // [rsp+70h] [rbp-98h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+78h] [rbp-90h] BYREF
  int v47; // [rsp+80h] [rbp-88h]
  int v48[2]; // [rsp+88h] [rbp-80h] BYREF
  int v49; // [rsp+90h] [rbp-78h] BYREF
  _BYTE v50[16]; // [rsp+98h] [rbp-70h] BYREF
  const wchar_t *v51; // [rsp+A8h] [rbp-60h] BYREF
  int v52; // [rsp+B0h] [rbp-58h]
  int v53; // [rsp+B4h] [rbp-54h]
  const wchar_t *v54; // [rsp+B8h] [rbp-50h]
  _BYTE v55[8]; // [rsp+C0h] [rbp-48h] BYREF
  _BYTE v56[8]; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v57[48]; // [rsp+D0h] [rbp-38h] BYREF
  _BYTE v58[56]; // [rsp+100h] [rbp-8h] BYREF
  __int128 v59; // [rsp+138h] [rbp+30h] BYREF
  const wchar_t *v60; // [rsp+148h] [rbp+40h]

  v2 = 0;
  v43[0] = 0;
  v49 = 0;
  v3 = 0;
  ScopedLock::ScopedLock((ScopedLock *)&lpCriticalSection, (struct ScopedCS *)(a1 + 168));
  SubordinateMonitor::ReturnCredit((SubordinateMonitor *)(a1 - 8));
  v4 = g_DebugLog;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v51 = L"SubordinateMonitor::Step";
    v52 = 208;
    v53 = 4;
    v54 = L"SLVS";
    v5 = *(_QWORD *)(a1 + 384) + 168LL;
    v6 = *(_QWORD *)(a1 + 376);
    CurrentStateString = SubordinateMonitor::GetCurrentStateString(a1 - 8, v55);
    v2 = 1;
    v43[0] = 1;
    dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,_GUID>(
      (unsigned int)&v51,
      (unsigned int)L"state:%? connId:%? csId:%?",
      CurrentStateString,
      v6 + 168,
      v5);
    v4 = g_DebugLog;
  }
  if ( (v2 & 1) != 0 )
  {
    FrsStringImpl<char,unsigned short>::ReleaseBody(v55);
    v4 = g_DebugLog;
  }
  v8 = *(_DWORD *)(a1 + 224);
  if ( !v8 )
  {
    *(_QWORD *)v48 = *(_QWORD *)(a1 + 248);
    if ( *(_DWORD *)(a1 + 232) )
      *(_DWORD *)(a1 + 236) = 1000;
    if ( *(_QWORD *)(a1 + 280) )
    {
      std::_Tree<std::_Tmap_traits<Guid,IntervalSet,std::less<Guid>,std::allocator<std::pair<Guid const,IntervalSet>>,0>>::operator=(
        a1 + 256,
        a1 + 272);
      std::_Tree<std::_Tmap_traits<Guid,IntervalSet,std::less<Guid>,std::allocator<std::pair<Guid const,IntervalSet>>,0>>::clear(a1 + 272);
    }
    std::_Tree<std::_Tmap_traits<Guid,IntervalSet,std::less<Guid>,std::allocator<std::pair<Guid const,IntervalSet>>,0>>::clear(a1 + 288);
    v59 = 0;
    *(_QWORD *)v43 = 0;
    VolumeManager = (struct FrsStatus *)ContentSetManager::GetVolumeManager(*(_QWORD *)(a1 + 384), v43, v36);
    v44 = VolumeManager;
    v37 = *(struct FrsStatus **)v43;
    if ( !VolumeManager )
    {
      if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugVolumeManagerRefCount)
        && g_DebugLog
        && LODWORD(g_DebugLog[1].LockSemaphore)
        && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        v41[0] = (struct DbManager *)L"SubordinateMonitor::Step";
        v41[1] = (struct DbManager *)0x5000000F1LL;
        v42 = L"SLVS";
        v45 = v37;
        dbgobj::DbgPrint<unsigned short,unsigned __int64>(
          v41,
          L"[VMREF] Added reference to volume manager. ptr:%p",
          &v45);
      }
      v38 = *(__int64 (__fastcall **)(struct FrsStatus *, __int128 *, _QWORD))(*(_QWORD *)v37 + 32LL);
      CurrentThreadId = GetCurrentThreadId();
      VolumeManager = (struct FrsStatus *)v38(v37, &v59, CurrentThreadId);
      v44 = VolumeManager;
      if ( !VolumeManager )
      {
        VolumeManager = (struct FrsStatus *)(*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64, int *, __int64))(*(_QWORD *)v59 + 32LL))(
                                              v59,
                                              a1 & -(__int64)(a1 != 8),
                                              *(_QWORD *)(a1 + 384) + 168LL,
                                              a1 + 272,
                                              &v49,
                                              a1 + 248);
        v44 = VolumeManager;
      }
    }
    v3 = 0;
    if ( v37 )
    {
      if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugVolumeManagerRefCount)
        && g_DebugLog
        && LODWORD(g_DebugLog[1].LockSemaphore)
        && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        v41[0] = (struct DbManager *)L"SubordinateMonitor::Step";
        v41[1] = (struct DbManager *)0x5000000FELL;
        v42 = L"SLVS";
        v45 = v37;
        dbgobj::DbgPrint<unsigned short,unsigned __int64>(
          v41,
          L"[VMREF] Release reference to volume manager. ptr:%p",
          &v45);
      }
      ScopedRef<VolumeManager::ShutdownRestartTask>::Set(v43, 0);
    }
    ScopedRef<VvUpData>::~ScopedRef<VvUpData>(v43);
    DbManagerInstance::FinalizeDbManagerInstance((DbManagerInstance *)&v59);
    if ( !VolumeManager )
    {
      *(_DWORD *)(a1 + 232) = 1;
      if ( v49 )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v41[0] = (struct DbManager *)L"SubordinateMonitor::Step";
          v41[1] = (struct DbManager *)0x400000104LL;
          v42 = L"SLVS";
          dbgobj::DbgPrint<unsigned short,unsigned __int64,unsigned __int64,_GUID,_GUID>(
            (unsigned int)v41,
            168,
            (unsigned int)v48,
            a1 + 248,
            *(_QWORD *)(a1 + 376) + 168LL,
            *(_QWORD *)(a1 + 384) + 168LL);
        }
      }
      else
      {
        if ( !*(_QWORD *)(a1 + 312) )
        {
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            v41[0] = (struct DbManager *)L"SubordinateMonitor::Step";
            v41[1] = (struct DbManager *)0x400000118LL;
            v42 = L"SLVS";
            dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
              v41,
              L"Wait for local version change. connId:%? csId:%?",
              *(_QWORD *)(a1 + 376) + 168LL,
              *(_QWORD *)(a1 + 384) + 168LL);
          }
          *(_DWORD *)(a1 + 224) = 0;
          goto LABEL_19;
        }
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v41[0] = (struct DbManager *)L"SubordinateMonitor::Step";
          v41[1] = (struct DbManager *)0x40000010FLL;
          v42 = L"SLVS";
          dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
            v41,
            L"Updates from previous sessions were dropped. Reprocess updates. connId:%? csId:%?",
            *(_QWORD *)(a1 + 376) + 168LL,
            *(_QWORD *)(a1 + 384) + 168LL);
        }
      }
      *(_DWORD *)(a1 + 224) = 1;
      goto LABEL_161;
    }
    *(_DWORD *)(a1 + 232) = 0;
    v3 = 1;
    goto LABEL_154;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    v43[0] = 0;
    v45 = 0;
    std::map<_GUID,LdbManager::VvCompactMan::VvInfo>::map<_GUID,LdbManager::VvCompactMan::VvInfo>(v50);
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v41[0] = (struct DbManager *)L"SubordinateMonitor::Step";
      v41[1] = (struct DbManager *)0x400000131LL;
      v42 = L"SLVS";
      dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
        v41,
        L"Checking if there is any new local update.  connId:%? csId:%?",
        *(_QWORD *)(a1 + 376) + 168LL,
        *(_QWORD *)(a1 + 384) + 168LL);
    }
    VolumeManager = SubordinateMonitor::GetDroppedVersions(
                      (SubordinateMonitor *)(a1 - 8),
                      (struct VersionChainVector *)v50);
    v44 = VolumeManager;
    if ( !VolumeManager )
    {
      std::_Tree<std::_Tmap_traits<Guid,IntervalSet,std::less<Guid>,std::allocator<std::pair<Guid const,IntervalSet>>,0>>::operator=(
        a1 + 288,
        a1 + 272);
      VersionChainVector::Delete((VersionChainVector *)(a1 + 288), (const struct VersionChainVector *)(a1 + 256));
      VersionChainVector::Union((VersionChainVector *)(a1 + 288), (const struct VersionChainVector *)v50);
      if ( g_DebugLog )
      {
        if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v41[0] = (struct DbManager *)L"SubordinateMonitor::Step";
          v41[1] = (struct DbManager *)0x50000013DLL;
          v42 = L"SLVS";
          dbgobj::DbgPrint<unsigned short,VersionChainVector,VersionChainVector,VersionChainVector,VersionChainVector>(
            (unsigned int)v41,
            v34,
            a1 + 272,
            a1 + 256,
            (__int64)v50,
            a1 + 288);
        }
      }
    }
    if ( VolumeManager
      || (v44 = 0,
          VolumeManager = SubordinateMonitor::CheckLocalUpdate(
                            (SubordinateMonitor *)(a1 - 8),
                            (const struct VERSION *)&v44,
                            v43,
                            (struct VERSION *)&v45),
          (v44 = VolumeManager) != 0) )
    {
      v3 = 1;
    }
    else
    {
      if ( v43[0] )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v41[0] = (struct DbManager *)L"SubordinateMonitor::Step";
          v41[1] = (struct DbManager *)0x400000147LL;
          v42 = L"SLVS";
          dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
            v41,
            L"Local update is found. connId:%? csId:%?",
            *(_QWORD *)(a1 + 376) + 168LL,
            *(_QWORD *)(a1 + 384) + 168LL);
        }
        v35 = 2;
      }
      else
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v41[0] = (struct DbManager *)L"SubordinateMonitor::Step";
          v41[1] = (struct DbManager *)0x40000014ELL;
          v42 = L"SLVS";
          dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
            v41,
            L"No local update is found.  connId:%? csId:%?",
            *(_QWORD *)(a1 + 376) + 168LL,
            *(_QWORD *)(a1 + 384) + 168LL);
        }
        v35 = 0;
      }
      *(_DWORD *)(a1 + 224) = v35;
      v3 = 0;
    }
    goto LABEL_64;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    *(_DWORD *)(a1 + 224) = 3;
    v30 = --v47;
    LeaveCriticalSection(lpCriticalSection);
    v48[0] = 0;
    v43[0] = 0;
    *(_DWORD *)(a1 + 348) = 0;
    VolumeManager = SubordinateMonitor::RequestVvUp((SubordinateMonitor *)(a1 - 8), v48, v43);
    v44 = VolumeManager;
    EnterCriticalSection(lpCriticalSection);
    v47 = v30 + 1;
    if ( !VolumeManager && !v48[0] )
    {
      v31 = g_DebugLog;
      if ( v43[0] )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v41[0] = (struct DbManager *)L"SubordinateMonitor::Step";
          v41[1] = (struct DbManager *)0x400000178LL;
          v42 = L"SLVS";
          dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
            v41,
            L"Upstream version vector retrieved from context. connId:%? csId:%?",
            *(_QWORD *)(a1 + 376) + 168LL,
            *(_QWORD *)(a1 + 384) + 168LL);
          v31 = g_DebugLog;
        }
        *(_DWORD *)(a1 + 224) = 4;
        v3 = 0;
      }
      else
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          *(_QWORD *)&v59 = L"SubordinateMonitor::Step";
          *((_QWORD *)&v59 + 1) = 0x400000180LL;
          v60 = L"SLVS";
          dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
            &v59,
            L"Upstream version vector requested from upstream. connId:%? csId:%?",
            *(_QWORD *)(a1 + 376) + 168LL,
            *(_QWORD *)(a1 + 384) + 168LL);
          v31 = g_DebugLog;
        }
        v3 = 2;
      }
LABEL_155:
      if ( !VolumeManager )
        goto LABEL_161;
      goto LABEL_156;
    }
    if ( *(_QWORD *)(a1 + 328) )
    {
      v32 = (_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(
                        a1 + 320,
                        &v45);
      std::_Tree<std::_Tset_traits<UID,std::less<UID>,std::allocator<UID>,0>>::insert<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<UID>>>>(
        a1 + 304,
        **v33,
        *v32);
    }
    *(_DWORD *)(a1 + 224) = 1;
    v3 = 1;
    v31 = g_DebugLog;
    if ( VolumeManager )
    {
LABEL_156:
      if ( v31 && LODWORD(v31[1].LockSemaphore) && SLODWORD(v31[1].OwningThread) >= 2 )
      {
        v41[0] = (struct DbManager *)L"SubordinateMonitor::Step";
        v41[1] = (struct DbManager *)0x200000207LL;
        v42 = L"SLVS";
        dbgobj::DbgPrint<unsigned short,FrsStatus>(v41, L"%?", VolumeManager);
      }
      CLEAR_ERROR(&v44);
      goto LABEL_161;
    }
    if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 5 )
      goto LABEL_161;
    v41[0] = (struct DbManager *)L"SubordinateMonitor::Step";
    v41[1] = (struct DbManager *)0x500000170LL;
    v42 = L"SLVS";
    dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
      v41,
      L"BLOCK. No credit available. connId:%? csId:%?",
      *(_QWORD *)(a1 + 376) + 168LL,
      *(_QWORD *)(a1 + 384) + 168LL);
LABEL_154:
    v31 = g_DebugLog;
    goto LABEL_155;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    if ( !*(_DWORD *)(a1 + 348) )
    {
      if ( !v4 || !LODWORD(v4[1].LockSemaphore) || SLODWORD(v4[1].OwningThread) < 5 )
        goto LABEL_19;
      v41[0] = (struct DbManager *)L"SubordinateMonitor::Step";
      v41[1] = (struct DbManager *)0x500000197LL;
      v42 = L"SLVS";
      v14 = L"Task is run without an error in REQUEST_VVUP_PENDING state.";
      v15 = (const wchar_t **)v41;
      goto LABEL_18;
    }
    if ( *(_QWORD *)(a1 + 328) )
    {
      v28 = (_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(
                        a1 + 320,
                        &v45);
      std::_Tree<std::_Tset_traits<UID,std::less<UID>,std::allocator<UID>,0>>::insert<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<UID>>>>(
        a1 + 304,
        **v29,
        *v28);
    }
    v16 = 1;
    *(_DWORD *)(a1 + 224) = 1;
LABEL_21:
    v3 = v16;
    goto LABEL_161;
  }
  v12 = v11 - 1;
  if ( !v12 )
  {
    std::map<_GUID,LdbManager::VvCompactMan::VvInfo>::map<_GUID,LdbManager::VvCompactMan::VvInfo>(v50);
    *(_OWORD *)v41 = 0;
    *(_QWORD *)v43 = 0;
    VolumeManager = (struct FrsStatus *)ContentSetManager::GetVolumeManager(*(_QWORD *)(a1 + 384), v43, v17);
    v44 = VolumeManager;
    v19 = *(struct FrsStatus **)v43;
    if ( !VolumeManager )
    {
      if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugVolumeManagerRefCount)
        && g_DebugLog
        && LODWORD(g_DebugLog[1].LockSemaphore)
        && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        *(_QWORD *)&v59 = L"SubordinateMonitor::Step";
        *((_QWORD *)&v59 + 1) = 0x5000001AFLL;
        v60 = L"SLVS";
        v44 = v19;
        dbgobj::DbgPrint<unsigned short,unsigned __int64>(
          &v59,
          L"[VMREF] Added reference to volume manager. ptr:%p",
          &v44);
      }
      v20 = *(__int64 (__fastcall **)(struct FrsStatus *, struct DbManager **, _QWORD))(*(_QWORD *)v19 + 32LL);
      v21 = GetCurrentThreadId();
      VolumeManager = (struct FrsStatus *)v20(v19, v41, v21);
      v44 = VolumeManager;
      if ( !VolumeManager )
      {
        VolumeManager = DbUtil::VersionVector(
                          v41[0],
                          (const struct _GUID *)(*(_QWORD *)(a1 + 384) + 168LL),
                          (struct VersionChainVector *)v50);
        v44 = VolumeManager;
        if ( !VolumeManager )
        {
          v59 = *(_OWORD *)((char *)v41[0] + 312);
          *(_QWORD *)v48 = -1;
          v45 = 0;
          VersionChainVector::Delete(
            (VersionChainVector *)v50,
            (const struct Guid *)&v59,
            (const struct VERSION *)&v45,
            (const struct VERSION *)v48);
        }
      }
    }
    if ( v19 )
    {
      if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugVolumeManagerRefCount)
        && g_DebugLog
        && LODWORD(g_DebugLog[1].LockSemaphore)
        && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        *(_QWORD *)&v59 = L"SubordinateMonitor::Step";
        *((_QWORD *)&v59 + 1) = 0x5000001BELL;
        v60 = L"SLVS";
        v45 = v19;
        dbgobj::DbgPrint<unsigned short,unsigned __int64>(
          &v59,
          L"[VMREF] Release reference to volume manager. ptr:%p",
          &v45);
      }
      ScopedRef<VolumeManager::ShutdownRestartTask>::Set(v43, 0);
    }
    ScopedRef<VvUpData>::~ScopedRef<VvUpData>(v43);
    DbManagerInstance::FinalizeDbManagerInstance((DbManagerInstance *)v41);
    if ( VolumeManager )
    {
      v3 = 1;
    }
    else
    {
      if ( VersionChainVector::Dominates((VersionChainVector *)(a1 + 352), (const struct VersionChainVector *)v50) )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v41[0] = (struct DbManager *)L"SubordinateMonitor::Step";
          v41[1] = (struct DbManager *)0x4000001C3LL;
          v42 = L"SLVS";
          dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
            v41,
            L"Upstream version vector dominates. connId:%? csId:%?",
            *(_QWORD *)(a1 + 376) + 168LL,
            *(_QWORD *)(a1 + 384) + 168LL);
        }
        v23 = --v47;
        LeaveCriticalSection(lpCriticalSection);
        VolumeManager = InConnection::CreateSubordinateSyncSession(
                          *(InConnection **)(a1 + 376),
                          (const struct _GUID *)(*(_QWORD *)(a1 + 384) + 168LL));
        v44 = VolumeManager;
        EnterCriticalSection(lpCriticalSection);
        v47 = v23 + 1;
        if ( !VolumeManager )
        {
          VersionChainVector::ConstVvIterator::ConstVvIterator((VersionChainVector::ConstVvIterator *)v56);
          v24 = VersionChainVector::ConstVvBegin(a1 + 288, v58);
          VersionChainVector::ConstVvIterator::operator=(v56, v24);
          VersionChainVector::ConstVvIterator::ConstVvIterator((VersionChainVector::ConstVvIterator *)v58);
          if ( !(unsigned __int8)VersionChainVector::ConstVvIterator::operator==(v56, v58) )
            *(_QWORD *)(a1 + 336) = *(_QWORD *)std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<UID const,UpdateReference *>>>>::operator*(v57);
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
          {
            v41[0] = (struct DbManager *)L"SubordinateMonitor::Step";
            v41[1] = (struct DbManager *)0x5000001D5LL;
            v42 = L"SLVS";
            dbgobj::DbgPrint<unsigned short,VERSION>(v41, L"Versions start from: %?", a1 + 336);
          }
          *(_DWORD *)(a1 + 224) = 5;
        }
        v25 = 1000;
        v3 = 0;
      }
      else
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v41[0] = (struct DbManager *)L"SubordinateMonitor::Step";
          v41[1] = (struct DbManager *)0x4000001DDLL;
          v42 = L"SLVS";
          dbgobj::DbgPrint<unsigned short,_GUID,_GUID,VersionChainVector,VersionChainVector>(
            (unsigned int)v41,
            v22,
            *(_QWORD *)(a1 + 376) + 168,
            *(_DWORD *)(a1 + 384) + 168,
            a1 + 352,
            (__int64)v50);
        }
        if ( *(_QWORD *)(a1 + 328) )
        {
          v26 = (_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(
                            a1 + 320,
                            &v45);
          std::_Tree<std::_Tset_traits<UID,std::less<UID>,std::allocator<UID>,0>>::insert<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<UID>>>>(
            a1 + 304,
            **v27,
            *v26);
        }
        v25 = 900000;
        if ( (unsigned int)(2 * *(_DWORD *)(a1 + 240)) < 0xDBBA0 )
          v25 = 2 * *(_DWORD *)(a1 + 240);
        *(_DWORD *)(a1 + 236) = v25;
        *(_DWORD *)(a1 + 224) = 1;
        v3 = 1;
      }
      *(_DWORD *)(a1 + 240) = v25;
    }
LABEL_64:
    std::_Tree<std::_Tmap_traits<Guid,IntervalSet,std::less<Guid>,std::allocator<std::pair<Guid const,IntervalSet>>,0>>::~_Tree<std::_Tmap_traits<Guid,IntervalSet,std::less<Guid>,std::allocator<std::pair<Guid const,IntervalSet>>,0>>(v50);
    goto LABEL_154;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    *(_DWORD *)(a1 + 368) = 0;
    --v47;
    LeaveCriticalSection(lpCriticalSection);
    v16 = SubordinateMonitor::FindAndSubmitLocalUpdates(a1 - 8);
    goto LABEL_21;
  }
  if ( v13 == 1 )
  {
    if ( !v4 || !LODWORD(v4[1].LockSemaphore) || SLODWORD(v4[1].OwningThread) < 5 )
      goto LABEL_19;
    v51 = L"SubordinateMonitor::Step";
    v52 = 512;
    v53 = 5;
    v54 = L"SLVS";
    v14 = L"Task is run in WAIT_SUBMIT_LOCAL_UPDATES state. Ignored.";
    v15 = &v51;
LABEL_18:
    dbgobj::DbgPrint<unsigned short>(v15, v14);
LABEL_19:
    v3 = 2;
  }
LABEL_161:
  ScopedLock::~ScopedLock((ScopedLock *)&lpCriticalSection);
  return v3;
}

```

## disassembly

```asm
0x140192a90  mov     rax, rsp
0x140192a93  mov     [rax+10h], rbx
0x140192a97  mov     [rax+18h], rsi
0x140192a9b  mov     [rax+20h], rdi
0x140192a9f  push    rbp
0x140192aa0  push    r12
0x140192aa2  push    r13
0x140192aa4  push    r14
0x140192aa6  push    r15
0x140192aa8  lea     rbp, [rax-78h]
0x140192aac  sub     rsp, 150h
0x140192ab3  mov     rax, cs:__security_cookie
0x140192aba  xor     rax, rsp
0x140192abd  mov     [rbp+70h+var_28], rax
0x140192ac1  mov     rsi, rcx
0x140192ac4  xor     r13d, r13d
0x140192ac7  mov     r14d, r13d
0x140192aca  mov     [rsp+170h+var_118], r13d
0x140192acf  mov     [rbp+70h+var_E8], r13d
0x140192ad3  mov     r15d, r13d
0x140192ad6  lea     rdx, [rcx+0A8h]; struct ScopedCS *
0x140192add  lea     rcx, [rsp+170h+lpCriticalSection]; this
0x140192ae2  call    ??0ScopedLock@@QEAA@AEAVScopedCS@@@Z; ScopedLock::ScopedLock(ScopedCS &)
0x140192ae7  nop
0x140192ae8  lea     r12, [rsi-8]
0x140192aec  mov     rcx, r12; this
0x140192aef  call    ?ReturnCredit@SubordinateMonitor@@AEAAXXZ; SubordinateMonitor::ReturnCredit(void)
0x140192af4  lea     rdi, aSubordinatemon_11; "SubordinateMonitor::Step"
0x140192afb  lea     rax, aSlvs; "SLVS"
0x140192b02  mov     ebx, 0A8h
0x140192b07  mov     rdx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140192b0e  test    rdx, rdx
0x140192b11  jz      short loc_140192B8E
0x140192b13  cmp     [rdx+40h], r13d
0x140192b17  jz      short loc_140192B8E
0x140192b19  cmp     dword ptr [rdx+38h], 4
0x140192b1d  jl      short loc_140192B8E
0x140192b1f  mov     [rbp+70h+var_D0], rdi
0x140192b23  mov     [rbp+70h+var_C8], 0D0h
0x140192b2a  mov     [rbp+70h+var_C4], 4
0x140192b31  mov     [rbp+70h+var_C0], rax
0x140192b35  mov     rdi, [rsi+180h]
0x140192b3c  add     rdi, rbx
0x140192b3f  mov     rbx, [rsi+178h]
0x140192b46  lea     rdx, [rbp+70h+var_B8]
0x140192b4a  mov     rcx, r12
0x140192b4d  call    ?GetCurrentStateString@SubordinateMonitor@@AEAA?AV?$FrsStringImpl@GD@@XZ; SubordinateMonitor::GetCurrentStateString(void)
0x140192b52  nop
0x140192b53  lea     r14d, [r13+1]
0x140192b57  mov     [rsp+170h+var_118], r14d
0x140192b5c  mov     [rsp+170h+var_150], rdi
0x140192b61  lea     r9, [rbx+0A8h]
0x140192b68  mov     r8, rax
0x140192b6b  lea     rdx, aStateConnidCsi; "state:%? connId:%? csId:%?"
0x140192b72  lea     rcx, [rbp+70h+var_D0]
0x140192b76  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@U_GUID@@U2@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@AEBU_GUID@@2@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>,_GUID,_GUID>(ushort const *,FrsStringImpl<ushort,char> const &,_GUID const &,_GUID const &)
0x140192b7b  mov     rdx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140192b82  mov     ebx, 0A8h
0x140192b87  lea     rdi, aSubordinatemon_11; "SubordinateMonitor::Step"
0x140192b8e  test    r14b, 1
0x140192b92  jz      short loc_140192BA4
0x140192b94  lea     rcx, [rbp+70h+var_B8]
0x140192b98  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x140192b9d  mov     rdx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140192ba4  mov     ecx, [rsi+0E0h]
0x140192baa  test    ecx, ecx
0x140192bac  jz      loc_1401935A7
0x140192bb2  sub     ecx, 1
0x140192bb5  jz      loc_140193358
0x140192bbb  sub     ecx, 1
0x140192bbe  jz      loc_140193123
0x140192bc4  sub     ecx, 1
0x140192bc7  jz      loc_140193089
0x140192bcd  sub     ecx, 1
0x140192bd0  jz      loc_140192C5A
0x140192bd6  sub     ecx, 1
0x140192bd9  jz      short loc_140192C2E
0x140192bdb  cmp     ecx, 1
0x140192bde  jnz     loc_140193987
0x140192be4  test    rdx, rdx
0x140192be7  jz      short loc_140192C23
0x140192be9  cmp     [rdx+40h], r13d
0x140192bed  jz      short loc_140192C23
0x140192bef  lea     r14d, [rcx+4]
0x140192bf3  cmp     [rdx+38h], r14d
0x140192bf7  jl      short loc_140192C23
0x140192bf9  mov     [rbp+70h+var_D0], rdi
0x140192bfd  mov     [rbp+70h+var_C8], 200h
0x140192c04  mov     [rbp+70h+var_C4], r14d
0x140192c08  lea     rax, aSlvs; "SLVS"
0x140192c0f  mov     [rbp+70h+var_C0], rax
0x140192c13  lea     rdx, aTaskIsRunInWai; "Task is run in WAIT_SUBMIT_LOCAL_UPDATE"...
0x140192c1a  lea     rcx, [rbp+70h+var_D0]
0x140192c1e  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140192c23  mov     r15d, 2
0x140192c29  jmp     loc_140193987
0x140192c2e  mov     [rsi+170h], r13d
0x140192c35  dec     [rsp+170h+var_F8]
0x140192c39  mov     rcx, [rsp+170h+lpCriticalSection]; lpCriticalSection
0x140192c3e  call    cs:__imp_LeaveCriticalSection
0x140192c45  nop     dword ptr [rax+rax+00h]
0x140192c4a  mov     rcx, r12
0x140192c4d  call    ?FindAndSubmitLocalUpdates@SubordinateMonitor@@AEAA?AW4STEP_RESULT@Task@@XZ; SubordinateMonitor::FindAndSubmitLocalUpdates(void)
0x140192c52  mov     r15d, eax
0x140192c55  jmp     loc_140193987
0x140192c5a  lea     rcx, [rbp+70h+var_E0]
0x140192c5e  call    ??0?$map@U_GUID@@VVvInfo@VvCompactMan@LdbManager@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@VVvInfo@VvCompactMan@LdbManager@@@std@@@6@@std@@QEAA@XZ; std::map<_GUID,LdbManager::VvCompactMan::VvInfo>::map<_GUID,LdbManager::VvCompactMan::VvInfo>(void)
0x140192c63  nop
0x140192c64  xorps   xmm0, xmm0
0x140192c67  movdqu  xmmword ptr [rsp+170h+var_138+8], xmm0
0x140192c6d  mov     qword ptr [rsp+170h+var_118], r13
0x140192c72  lea     rdx, [rsp+170h+var_118]
0x140192c77  mov     rcx, [rsi+180h]
0x140192c7e  call    ?GetVolumeManager@ContentSetManager@@QEAAPEAVFrsStatus@@AEAV?$ScopedRef@VVolumeManager@@@@@Z; ContentSetManager::GetVolumeManager(ScopedRef<VolumeManager> &)
0x140192c83  mov     rdi, rax
0x140192c86  mov     [rsp+170h+var_110], rax
0x140192c8b  mov     r14d, 5
0x140192c91  mov     rbx, qword ptr [rsp+170h+var_118]
0x140192c96  test    rax, rax
0x140192c99  jnz     loc_140192D93
0x140192c9f  lea     rcx, ?DebugVolumeManagerRefCount@Settings@@3VCDebugVolumeManagerRefCount@1@A; Settings::CDebugVolumeManagerRefCount Settings::DebugVolumeManagerRefCount
0x140192ca6  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x140192cab  lea     r12, aSubordinatemon_11; "SubordinateMonitor::Step"
0x140192cb2  test    eax, eax
0x140192cb4  jz      short loc_140192D02
0x140192cb6  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140192cbd  test    rax, rax
0x140192cc0  jz      short loc_140192D02
0x140192cc2  cmp     [rax+40h], r13d
0x140192cc6  jz      short loc_140192D02
0x140192cc8  cmp     [rax+38h], r14d
0x140192ccc  jl      short loc_140192D02
0x140192cce  mov     qword ptr [rbp+70h+var_40], r12
0x140192cd2  mov     dword ptr [rbp+70h+var_40+8], 1AFh
0x140192cd9  mov     dword ptr [rbp+70h+var_40+0Ch], r14d
0x140192cdd  lea     rax, aSlvs; "SLVS"
0x140192ce4  mov     [rbp+70h+var_30], rax
0x140192ce8  mov     [rsp+170h+var_110], rbx
0x140192ced  lea     r8, [rsp+170h+var_110]
0x140192cf2  lea     rdx, aVmrefAddedRefe; "[VMREF] Added reference to volume manag"...
0x140192cf9  lea     rcx, [rbp+70h+var_40]
0x140192cfd  call    ??$DbgPrint@G_K@dbgobj@@QEAA_KPEBGAEB_K@Z; dbgobj::DbgPrint<ushort,unsigned __int64>(ushort const *,unsigned __int64 const &)
0x140192d02  mov     rax, [rbx]
0x140192d05  mov     rdi, [rax+20h]
0x140192d09  call    cs:__imp_GetCurrentThreadId
0x140192d10  nop     dword ptr [rax+rax+00h]
0x140192d15  mov     r8d, eax
0x140192d18  lea     rdx, [rsp+170h+var_138+8]
0x140192d1d  mov     rcx, rbx
0x140192d20  mov     rax, rdi
0x140192d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140192d28  mov     rdi, rax
0x140192d2b  mov     [rsp+170h+var_110], rax
0x140192d30  mov     r15d, 0A8h
0x140192d36  test    rax, rax
0x140192d39  jnz     short loc_140192DA0
0x140192d3b  mov     rdx, [rsi+180h]
0x140192d42  add     rdx, r15; struct _GUID *
0x140192d45  lea     r8, [rbp+70h+var_E0]; struct VersionChainVector *
0x140192d49  mov     rcx, [rsp+170h+var_138+8]; struct DbManager *
0x140192d4e  call    ?VersionVector@DbUtil@@SAPEAVFrsStatus@@PEAVDbManager@@AEBU_GUID@@AEAVVersionChainVector@@@Z; DbUtil::VersionVector(DbManager *,_GUID const &,VersionChainVector &)
0x140192d53  mov     rdi, rax
0x140192d56  mov     [rsp+170h+var_110], rax
0x140192d5b  test    rax, rax
0x140192d5e  jnz     short loc_140192DA0
0x140192d60  mov     rax, [rsp+170h+var_138+8]
0x140192d65  movups  xmm0, xmmword ptr [rax+138h]
0x140192d6c  movdqu  [rbp+70h+var_40], xmm0
0x140192d71  or      qword ptr [rbp+70h+var_F0], 0FFFFFFFFFFFFFFFFh
0x140192d76  mov     [rsp+170h+var_108], r13
0x140192d7b  lea     r9, [rbp+70h+var_F0]; struct VERSION *
0x140192d7f  lea     r8, [rsp+170h+var_108]; struct VERSION *
0x140192d84  lea     rdx, [rbp+70h+var_40]; struct Guid *
0x140192d88  lea     rcx, [rbp+70h+var_E0]; this
0x140192d8c  call    ?Delete@VersionChainVector@@QEAAXAEBVGuid@@AEBVVERSION@@1@Z; VersionChainVector::Delete(Guid const &,VERSION const &,VERSION const &)
0x140192d91  jmp     short loc_140192DA0
0x140192d93  mov     r15d, 0A8h
0x140192d99  lea     r12, aSubordinatemon_11; "SubordinateMonitor::Step"
0x140192da0  test    rbx, rbx
0x140192da3  jz      short loc_140192E0E
0x140192da5  lea     rcx, ?DebugVolumeManagerRefCount@Settings@@3VCDebugVolumeManagerRefCount@1@A; Settings::CDebugVolumeManagerRefCount Settings::DebugVolumeManagerRefCount
0x140192dac  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x140192db1  test    eax, eax
0x140192db3  jz      short loc_140192E01
0x140192db5  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140192dbc  test    rax, rax
0x140192dbf  jz      short loc_140192E01
0x140192dc1  cmp     [rax+40h], r13d
0x140192dc5  jz      short loc_140192E01
0x140192dc7  cmp     [rax+38h], r14d
0x140192dcb  jl      short loc_140192E01
0x140192dcd  mov     qword ptr [rbp+70h+var_40], r12
0x140192dd1  mov     dword ptr [rbp+70h+var_40+8], 1BEh
0x140192dd8  mov     dword ptr [rbp+70h+var_40+0Ch], r14d
0x140192ddc  lea     rax, aSlvs; "SLVS"
0x140192de3  mov     [rbp+70h+var_30], rax
0x140192de7  mov     [rsp+170h+var_108], rbx
0x140192dec  lea     r8, [rsp+170h+var_108]
0x140192df1  lea     rdx, aVmrefReleaseRe; "[VMREF] Release reference to volume man"...
0x140192df8  lea     rcx, [rbp+70h+var_40]
0x140192dfc  call    ??$DbgPrint@G_K@dbgobj@@QEAA_KPEBGAEB_K@Z; dbgobj::DbgPrint<ushort,unsigned __int64>(ushort const *,unsigned __int64 const &)
0x140192e01  xor     edx, edx
0x140192e03  lea     rcx, [rsp+170h+var_118]
0x140192e08  call    ?Set@?$ScopedRef@VShutdownRestartTask@VolumeManager@@@@AEAAXPEAVShutdownRestartTask@VolumeManager@@@Z; ScopedRef<VolumeManager::ShutdownRestartTask>::Set(VolumeManager::ShutdownRestartTask *)
0x140192e0d  nop
0x140192e0e  lea     rcx, [rsp+170h+var_118]
0x140192e13  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x140192e18  nop
0x140192e19  lea     rcx, [rsp+170h+var_138+8]; this
0x140192e1e  call    ?FinalizeDbManagerInstance@DbManagerInstance@@QEAAXXZ; DbManagerInstance::FinalizeDbManagerInstance(void)
0x140192e23  test    rdi, rdi
0x140192e26  jnz     loc_140193075
0x140192e2c  lea     rbx, [rsi+160h]
0x140192e33  lea     rdx, [rbp+70h+var_E0]; struct VersionChainVector *
0x140192e37  mov     rcx, rbx; this
0x140192e3a  call    ?Dominates@VersionChainVector@@QEBA_NAEBV1@@Z; VersionChainVector::Dominates(VersionChainVector const &)
0x140192e3f  test    al, al
0x140192e41  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140192e48  jz      loc_140192FBA
0x140192e4e  lea     r12, aSubordinatemon_11; "SubordinateMonitor::Step"
0x140192e55  test    rax, rax
0x140192e58  jz      short loc_140192EAC
0x140192e5a  cmp     [rax+40h], r13d
0x140192e5e  jz      short loc_140192EAC
0x140192e60  cmp     dword ptr [rax+38h], 4
0x140192e64  jl      short loc_140192EAC
0x140192e66  mov     [rsp+170h+var_138+8], r12
0x140192e6b  mov     dword ptr [rsp+170h+var_128], 1C3h
0x140192e73  mov     dword ptr [rsp+170h+var_128+4], 4
0x140192e7b  lea     rax, aSlvs; "SLVS"
0x140192e82  mov     [rsp+170h+var_120], rax
0x140192e87  mov     r9, [rsi+180h]
0x140192e8e  add     r9, r15
0x140192e91  mov     r8, [rsi+178h]
0x140192e98  add     r8, r15
0x140192e9b  lea     rdx, aUpstreamVersio_1; "Upstream version vector dominates. conn"...
0x140192ea2  lea     rcx, [rsp+170h+var_138+8]
0x140192ea7  call    ??$DbgPrint@GU_GUID@@U1@@dbgobj@@QEAA_KPEBGAEBU_GUID@@1@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID>(ushort const *,_GUID const &,_GUID const &)
0x140192eac  mov     ebx, [rsp+170h+var_F8]
0x140192eb0  dec     ebx
0x140192eb2  mov     [rsp+170h+var_F8], ebx
0x140192eb6  mov     rcx, [rsp+170h+lpCriticalSection]; lpCriticalSection
0x140192ebb  call    cs:__imp_LeaveCriticalSection
0x140192ec2  nop     dword ptr [rax+rax+00h]
0x140192ec7  mov     rdx, [rsi+180h]
0x140192ece  add     rdx, r15; struct _GUID *
0x140192ed1  mov     rcx, [rsi+178h]; this
0x140192ed8  call    ?CreateSubordinateSyncSession@InConnection@@AEAAPEAVFrsStatus@@AEBU_GUID@@@Z; InConnection::CreateSubordinateSyncSession(_GUID const &)
0x140192edd  mov     rdi, rax
0x140192ee0  mov     [rsp+170h+var_110], rax
0x140192ee5  mov     rcx, [rsp+170h+lpCriticalSection]; lpCriticalSection
0x140192eea  call    cs:__imp_EnterCriticalSection
0x140192ef1  nop     dword ptr [rax+rax+00h]
0x140192ef6  lea     eax, [rbx+1]
0x140192ef9  mov     [rsp+170h+var_F8], eax
0x140192efd  test    rdi, rdi
0x140192f00  jnz     loc_140192FAD
0x140192f06  lea     rcx, [rbp+70h+var_B0]; this
0x140192f0a  call    ??0ConstVvIterator@VersionChainVector@@QEAA@XZ; VersionChainVector::ConstVvIterator::ConstVvIterator(void)
0x140192f0f  lea     rcx, [rsi+120h]
0x140192f16  lea     rdx, [rbp+70h+var_78]
0x140192f1a  call    ?ConstVvBegin@VersionChainVector@@QEBA?AVConstVvIterator@1@XZ; VersionChainVector::ConstVvBegin(void)
0x140192f1f  mov     rdx, rax
0x140192f22  lea     rcx, [rbp+70h+var_B0]
0x140192f26  call    ??4ConstVvIterator@VersionChainVector@@QEAAAEAV01@AEBV01@@Z; VersionChainVector::ConstVvIterator::operator=(VersionChainVector::ConstVvIterator const &)
0x140192f2b  lea     rcx, [rbp+70h+var_78]; this
0x140192f2f  call    ??0ConstVvIterator@VersionChainVector@@QEAA@XZ; VersionChainVector::ConstVvIterator::ConstVvIterator(void)
0x140192f34  lea     rdx, [rbp+70h+var_78]
0x140192f38  lea     rcx, [rbp+70h+var_B0]
0x140192f3c  call    ??8ConstVvIterator@VersionChainVector@@QEBA_NAEBV01@@Z; VersionChainVector::ConstVvIterator::operator==(VersionChainVector::ConstVvIterator const &)
0x140192f41  test    al, al
0x140192f43  jnz     short loc_140192F58
0x140192f45  lea     rcx, [rbp+70h+var_A8]
0x140192f49  call    ??D?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVUID@@PEAVUpdateReference@@@std@@@std@@@std@@@std@@QEBAAEAU?$pair@$$CBVUID@@PEAVUpdateReference@@@1@XZ; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<UID const,UpdateReference *>>>>::operator*(void)
0x140192f4e  mov     rax, [rax]
0x140192f51  mov     [rsi+150h], rax
0x140192f58  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140192f5f  test    rax, rax
0x140192f62  jz      short loc_140192FA6
0x140192f64  cmp     [rax+40h], r13d
0x140192f68  jz      short loc_140192FA6
0x140192f6a  cmp     [rax+38h], r14d
0x140192f6e  jl      short loc_140192FA6
0x140192f70  mov     [rsp+170h+var_138+8], r12
0x140192f75  mov     dword ptr [rsp+170h+var_128], 1D5h
0x140192f7d  mov     dword ptr [rsp+170h+var_128+4], r14d
0x140192f82  lea     rax, aSlvs; "SLVS"
0x140192f89  mov     [rsp+170h+var_120], rax
0x140192f8e  lea     r8, [rsi+150h]
0x140192f95  lea     rdx, aVersionsStartF; "Versions start from: %?"
0x140192f9c  lea     rcx, [rsp+170h+var_138+8]
0x140192fa1  call    ??$DbgPrint@GVVERSION@@@dbgobj@@QEAA_KPEBGAEBVVERSION@@@Z; dbgobj::DbgPrint<ushort,VERSION>(ushort const *,VERSION const &)
0x140192fa6  mov     [rsi+0E0h], r14d
0x140192fad  mov     ecx, 3E8h
0x140192fb2  mov     r15d, r13d
0x140192fb5  jmp     loc_14019306D
0x140192fba  test    rax, rax
0x140192fbd  jz      short loc_140193018
0x140192fbf  cmp     [rax+40h], r13d
0x140192fc3  jz      short loc_140193018
  ... truncated ...
```
