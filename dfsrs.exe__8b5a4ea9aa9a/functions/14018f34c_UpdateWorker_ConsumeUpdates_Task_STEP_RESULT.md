# UpdateWorker::ConsumeUpdates(Task::STEP_RESULT &)

- ea: `0x14018f34c`
- end: `0x14018fe86`
- name: `?ConsumeUpdates@UpdateWorker@@AEAAPEAVFrsStatus@@AEAW4STEP_RESULT@Task@@@Z`
- size: `2874`
- prototype: `struct FrsStatus *__fastcall(UpdateWorker *__hidden this, enum Task::STEP_RESULT *)`
- caller_count: `1`
- callee_count: `44`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1401902a0`

## callees

- `0x1400036a0`
- `0x14000c910`
- `0x14000cdc0`
- `0x14000d980`
- `0x14000dcc0`
- `0x140011408`
- `0x1400239a8`
- `0x140024ec8`
- `0x140024ed4`
- `0x140037500`
- `0x140067510`
- `0x140069bb0`
- `0x14006a490`
- `0x14006a7ac`
- `0x140087b54`
- `0x140096bf0`
- `0x14009ccfc`
- `0x1400c6ba8`
- `0x1400d43d8`
- `0x1400e58f4`
- `0x14011da00`
- `0x140139a00`
- `0x1401449bc`
- `0x140144aec`
- `0x140144ca4`
- `0x140145854`
- `0x140146168`
- `0x1401463d0`
- `0x1401464dc`
- `0x14014673c`
- `0x140166070`
- `0x14016dbf0`
- `0x140182d78`
- `0x14018e9d4`
- `0x14018ea88`
- `0x14018eb54`
- `0x14018ec0c`
- `0x14018edac`
- `0x14018f34c`
- `0x140190438`
- `0x1401b30b0`
- `0x1401b3a04`
- `0x1401b9494`
- `0x1401bda10`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14018f5a2`
- `KERNEL32!LeaveCriticalSection` at `0x14018f801`
- `KERNEL32!LeaveCriticalSection` at `0x14018f9be`
- `KERNEL32!LeaveCriticalSection` at `0x14018fb41`
- `KERNEL32!LeaveCriticalSection` at `0x14018f5a2`
- `KERNEL32!LeaveCriticalSection` at `0x14018f801`
- `KERNEL32!LeaveCriticalSection` at `0x14018f9be`
- `KERNEL32!LeaveCriticalSection` at `0x14018fb41`
- `KERNEL32!EnterCriticalSection` at `0x14018f512`
- `KERNEL32!EnterCriticalSection` at `0x14018f667`
- `KERNEL32!EnterCriticalSection` at `0x14018f932`
- `KERNEL32!EnterCriticalSection` at `0x14018fab2`
- `KERNEL32!EnterCriticalSection` at `0x14018f512`
- `KERNEL32!EnterCriticalSection` at `0x14018f667`
- `KERNEL32!EnterCriticalSection` at `0x14018f932`
- `KERNEL32!EnterCriticalSection` at `0x14018fab2`
- `KERNEL32!GetCurrentThreadId` at `0x14018fd64`
- `KERNEL32!GetCurrentThreadId` at `0x14018fd64`

## string_xrefs

- `0x14018f6ab`: `Update contentInfoHistory`
- `0x14018f556`: `Update idUpdateInfoHistory`
- `0x14018f97a`: `Update idUpdateInfoHistory`
- `0x14018fafa`: `Update idUpdateInfoHistory`
- `0x14018f40f`: `UpdateWorker::ConsumeUpdates`
- `0x14018fbaf`: `UpdateWorker::ConsumeUpdates`
- `0x14018fc49`: `UpdateWorker::ConsumeUpdates`
- `0x14018fce3`: `UpdateWorker::ConsumeUpdates`
- `0x14018f474`: `RegisterNormalUpdate task:%? taskPtr:%p`
- `0x14018f4e2`: `UnregisterNormalUpdate task:%? taskPtr:%p`
- `0x14018f7ae`: `Removed blocked record from content set info. update:%?`
- `0x14018f5f4`: `Install error: %?`
- `0x14018f72c`: `Adding blocked record to content set info. update:%?`
- `0x14018fd41`: `No pending updates. connId:%? csName:%ws csId:%?`
- `0x14018fd81`: `UpdateWorker::ConsumeUpdates`
- `0x14018fc16`: `Repolling updates in:%d connId:%? csName:%ws csId:%?`
- `0x14018fca7`: `Available updates were locked. connId:%? csName:%ws csId:%?`
- `0x14018fd8d`: `base\fs\remotefs\frs\src\sync\updatemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct FrsStatus *__fastcall UpdateWorker::ConsumeUpdates(UpdateWorker *this, enum Task::STEP_RESULT *a2)
{
  enum Task::STEP_RESULT *v2; // r15
  __int64 v4; // rdi
  UpdateWorker *v5; // rbx
  int v6; // r13d
  __int64 v7; // r15
  int v8; // ecx
  struct MonitorContext *v9; // rbx
  struct HistoryRecord *v10; // rdx
  struct MonitorContext *v11; // rcx
  struct FrsStatus *v12; // rax
  struct MonitorContext *v13; // rbx
  __int64 v14; // rax
  __int64 v15; // r9
  struct MonitorContext *v16; // rbx
  __int64 v17; // rax
  struct MonitorContext *v18; // rcx
  __int64 v19; // rax
  struct MonitorContext *v20; // rbx
  struct HistoryRecord *v21; // rbx
  struct MonitorContext *v22; // rcx
  struct ScopedCS *v23; // rbx
  unsigned int v24; // edx
  struct MonitorContext *v25; // rbx
  struct HistoryRecord *v26; // rbx
  struct MonitorContext *v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  DWORD CurrentThreadId; // eax
  __int64 v32; // rcx
  _QWORD *v33; // rax
  __int64 v34; // r8
  UpdateReference **v35; // rbx
  unsigned int v36; // edx
  struct HistoryRecord *i; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v39; // [rsp+58h] [rbp-A8h] BYREF
  int v40; // [rsp+60h] [rbp-A0h]
  int v41; // [rsp+64h] [rbp-9Ch]
  const wchar_t *v42; // [rsp+68h] [rbp-98h]
  enum Task::STEP_RESULT *v43; // [rsp+70h] [rbp-90h] BYREF
  __int64 v44; // [rsp+78h] [rbp-88h] BYREF
  UpdateWorker *v45; // [rsp+80h] [rbp-80h] BYREF
  __int64 v46; // [rsp+88h] [rbp-78h] BYREF
  int v47; // [rsp+90h] [rbp-70h] BYREF
  UpdateWorker *v48; // [rsp+98h] [rbp-68h] BYREF
  __int64 v49[2]; // [rsp+A0h] [rbp-60h] BYREF
  const wchar_t *v50; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD v51[2]; // [rsp+B8h] [rbp-48h] BYREF
  const wchar_t *v52; // [rsp+C0h] [rbp-40h]
  _BYTE v53[16]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v54[16]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v55[16]; // [rsp+F8h] [rbp-8h] BYREF
  const wchar_t *v56; // [rsp+108h] [rbp+8h] BYREF
  int v57; // [rsp+110h] [rbp+10h]
  int v58; // [rsp+114h] [rbp+14h]
  const wchar_t *v59; // [rsp+118h] [rbp+18h]

  v2 = a2;
  v43 = a2;
  v4 = 0;
  v5 = 0;
  std::_Compressed_pair<std::allocator<std::_List_node<MultiCREW<unsigned __int64,CREWLock>::Waiter,void *>>,std::_List_val<std::_List_simple_types<MultiCREW<unsigned __int64,CREWLock>::Waiter>>,1>::_Compressed_pair<std::allocator<std::_List_node<MultiCREW<unsigned __int64,CREWLock>::Waiter,void *>>,std::_List_val<std::_List_simple_types<MultiCREW<unsigned __int64,CREWLock>::Waiter>>,1>(v49);
  std::list<void *>::_Alloc_sentinel_and_proxy(v49);
  v6 = 2;
  *(_DWORD *)v2 = 2;
  i = 0;
  LODWORD(v44) = 0;
  *((_DWORD *)this + 48) = 0;
  UpdateLock::Retrieve((UpdateLock *)(*((_QWORD *)this + 27) + 264LL), (__int64)v49, (__int64)&v44, (__int64)this + 192);
  if ( i )
  {
    v7 = *((_QWORD *)i + 34);
    v8 = *((_DWORD *)this + 59);
    if ( *(_DWORD *)(v7 + 776) == 1 )
    {
      if ( v8 )
      {
        *((_DWORD *)this + 59) = 0;
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v56 = L"UpdateWorker::ConsumeUpdates";
          v57 = 287;
          v58 = 5;
          v59 = L"UPMG";
          v45 = this;
          LODWORD(v46) = *((_DWORD *)this + 42);
          dbgobj::DbgPrint<unsigned short,unsigned int,unsigned __int64>(
            &v56,
            L"UnregisterNormalUpdate task:%? taskPtr:%p",
            &v46,
            &v45);
        }
        _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(*((_QWORD *)this + 26) + 24LL) + 1184LL));
      }
    }
    else if ( !v8 )
    {
      *((_DWORD *)this + 59) = 1;
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        v50 = L"UpdateWorker::ConsumeUpdates";
        v51[0] = 280;
        v51[1] = 5;
        v52 = L"UPMG";
        v48 = this;
        v47 = *((_DWORD *)this + 42);
        dbgobj::DbgPrint<unsigned short,unsigned int,unsigned __int64>(
          &v50,
          L"RegisterNormalUpdate task:%? taskPtr:%p",
          &v47,
          &v48);
      }
      _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(*((_QWORD *)this + 26) + 24LL) + 1184LL), 1u);
    }
    v9 = g_MonitorContext;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_MonitorContext + 808));
    *((_DWORD *)v9 + 200) = 1;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v56 = L"UpdateWorker::ConsumeUpdates";
      v57 = 292;
      v58 = 5;
      v59 = L"UPMG";
      dbgobj::DbgPrint<unsigned short>(&v56, L"Update idUpdateInfoHistory");
    }
    v10 = i;
    *((_DWORD *)i + 18) = 2;
    IdUpdateInfoHistoryProcessor::Update((struct MonitorContext *)((char *)g_MonitorContext + 744), v10);
    v11 = g_MonitorContext;
    *((_DWORD *)g_MonitorContext + 200) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v11 + 808));
    v12 = Meet::Install((Meet *)v7, (UpdateWorker *)((char *)this + 32));
    v48 = v12;
    if ( v12 )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        v56 = L"UpdateWorker::ConsumeUpdates";
        v57 = 300;
        v58 = 5;
        v59 = L"UPMG";
        dbgobj::DbgPrint<unsigned short,FrsStatus>(&v56, L"Install error: %?", v12);
      }
      InConnection::UpdateProcessed(*((InConnection **)this + 28), *(_QWORD *)(v7 + 728), *(_DWORD *)(v7 + 776));
      UpdateLock::Cancel((UpdateLock *)(*((_QWORD *)this + 27) + 264LL), i);
      goto LABEL_53;
    }
    PtrList<ContentSetInfo>::PtrList<ContentSetInfo>(&v50);
    v13 = g_MonitorContext;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_MonitorContext + 704));
    *((_DWORD *)v13 + 174) = 1;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v56 = L"UpdateWorker::ConsumeUpdates";
      v57 = 315;
      v58 = 5;
      v59 = L"UPMG";
      dbgobj::DbgPrint<unsigned short>(&v56, L"Update contentInfoHistory");
    }
    if ( (unsigned int)ConnectionInfoHistory::FindByCxtionGuid((char *)g_MonitorContext + 640, v7 + 112, &v50) )
    {
      v14 = *(_QWORD *)std::vector<MemberInfo *>::at(v51);
      v46 = v14;
      if ( *(_DWORD *)(v7 + 32) == 4 )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v56 = L"UpdateWorker::ConsumeUpdates";
          v57 = 326;
          v58 = 5;
          v59 = L"UPMG";
          dbgobj::DbgPrint<unsigned short,ID_UPDATE>(
            &v56,
            L"Adding blocked record to content set info. update:%?",
            v7 + 40);
        }
        std::pair<UID,enum UPDATE_TYPE>::pair<UID,enum UPDATE_TYPE>(&v56, v7 + 40, v7 + 36, v46);
        std::map<UID,enum UPDATE_TYPE>::insert<std::pair<UID,enum UPDATE_TYPE>,0>(v15 + 176, v55, &v56);
      }
      else if ( std::_Tree<std::_Tmap_traits<UID,enum UPDATE_TYPE,std::less<UID>,std::allocator<std::pair<UID const,enum UPDATE_TYPE>>,0>>::erase(
                  v14 + 176,
                  v7 + 40)
             && g_DebugLog
             && LODWORD(g_DebugLog[1].LockSemaphore)
             && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        v39 = L"UpdateWorker::ConsumeUpdates";
        v40 = 335;
        v41 = 5;
        v42 = L"UPMG";
        dbgobj::DbgPrint<unsigned short,ID_UPDATE>(
          &v39,
          L"Removed blocked record from content set info. update:%?",
          v7 + 40);
      }
      v16 = g_MonitorContext;
      v17 = std::map<UID,enum UPDATE_TYPE>::map<UID,enum UPDATE_TYPE>(v53, v46 + 176);
      ContentSetInfoHistory::UpdateBlockedIds((char *)v16 + 640, v7 + 112, v17);
    }
    v18 = g_MonitorContext;
    *((_DWORD *)g_MonitorContext + 174) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v18 + 704));
    switch ( *(_DWORD *)(v7 + 32) )
    {
      case 1:
        goto LABEL_51;
      case 2:
        v25 = g_MonitorContext;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_MonitorContext + 808));
        *((_DWORD *)v25 + 200) = 1;
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v39 = L"UpdateWorker::ConsumeUpdates";
          v40 = 405;
          v41 = 5;
          v42 = L"UPMG";
          dbgobj::DbgPrint<unsigned short>(&v39, L"Update idUpdateInfoHistory");
        }
        v26 = i;
        *((_DWORD *)i + 18) = 4;
        IdUpdateInfoHistoryProcessor::Update((struct MonitorContext *)((char *)g_MonitorContext + 744), v26);
        v27 = g_MonitorContext;
        *((_DWORD *)g_MonitorContext + 200) = 0;
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v27 + 808));
        RefCountObject::AddRef((RefCountObject *)v7);
        UpdateLock::Wait((UpdateLock *)(*((_QWORD *)this + 27) + 264LL), v26);
        break;
      case 3:
        InConnection::UpdateProcessed(*((InConnection **)this + 28), *(_QWORD *)(v7 + 728), *(_DWORD *)(v7 + 776));
        v23 = (struct ScopedCS *)(*((_QWORD *)this + 27) + 264LL);
        ScopedLock::ScopedLock((ScopedLock *)v54, v23);
        UpdateLock::UnLock(v23, i);
        UpdateLock::UpdatesDelete(v23, i);
        std::_Tree<std::_Tset_traits<UID,std::less<UID>,std::allocator<UID>,0>>::erase(
          (char *)v23 + 224,
          (char *)i + 208);
        UpdateLock::UnblockDependents(v23, i);
        UpdateReference::`scalar deleting destructor'(i, v24);
        ScopedLock::~ScopedLock((ScopedLock *)v54);
        goto LABEL_52;
      case 4:
        v20 = g_MonitorContext;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_MonitorContext + 808));
        *((_DWORD *)v20 + 200) = 1;
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v39 = L"UpdateWorker::ConsumeUpdates";
          v40 = 388;
          v41 = 5;
          v42 = L"UPMG";
          dbgobj::DbgPrint<unsigned short>(&v39, L"Update idUpdateInfoHistory");
        }
        v21 = i;
        *((_DWORD *)i + 18) = 5;
        IdUpdateInfoHistoryProcessor::Update((struct MonitorContext *)((char *)g_MonitorContext + 744), v21);
        v22 = g_MonitorContext;
        *((_DWORD *)g_MonitorContext + 200) = 0;
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v22 + 808));
        RefCountObject::AddRef((RefCountObject *)v7);
        UpdateLock::Blocked((UpdateLock *)(*((_QWORD *)this + 27) + 264LL), v21);
        break;
      default:
        if ( *(_DWORD *)(v7 + 32) == 5
          && g_DebugLog
          && LODWORD(g_DebugLog[1].LockSemaphore)
          && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v39 = L"UpdateWorker::ConsumeUpdates";
          v40 = 366;
          v41 = 4;
          v42 = L"UPMG";
          v19 = *((_QWORD *)this + 27);
          v45 = (UpdateWorker *)(*(_QWORD *)(v19 + 200) + 18LL);
          dbgobj::DbgPrint<unsigned short,GVSN,_GUID,unsigned short const *,_GUID>(
            (unsigned int)&v39,
            v19 + 168,
            v7 + 64,
            *((_QWORD *)this + 28) + 168,
            (__int64)&v45,
            v19 + 168);
        }
LABEL_51:
        InConnection::UpdateProcessed(*((InConnection **)this + 28), *(_QWORD *)(v7 + 728), *(_DWORD *)(v7 + 776));
        UpdateLock::Cancel((UpdateLock *)(*((_QWORD *)this + 27) + 264LL), i);
LABEL_52:
        PtrList<ContentSetInfo>::~PtrList<ContentSetInfo>(&v50);
LABEL_53:
        v6 = 0;
        v5 = v48;
        v2 = v43;
LABEL_83:
        *(_DWORD *)v2 = v6;
        if ( v5 )
        {
          CurrentThreadId = GetCurrentThreadId();
          v4 = FrsStatusList::PushNewError(
                 v32,
                 *((unsigned int *)v5 + 1),
                 *((unsigned int *)v5 + 2),
                 *(unsigned int *)v5,
                 "base\\fs\\remotefs\\frs\\src\\sync\\updatemanager.cpp",
                 "UpdateWorker::ConsumeUpdates",
                 477,
                 CurrentThreadId,
                 v5);
        }
        goto LABEL_91;
    }
    InConnection::OnMeetRetry(*((_QWORD *)this + 28), v7 + 40, *(unsigned int *)(v7 + 776));
    RefCountObject::Release((RefCountObject *)v7);
    goto LABEL_52;
  }
  *((_DWORD *)this + 60) = 1;
  if ( !v49[1] )
  {
    if ( *((_DWORD *)this + 48) )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        v39 = L"UpdateWorker::ConsumeUpdates";
        v40 = 460;
        v41 = 5;
        v42 = L"UPMG";
        v28 = *((_QWORD *)this + 27);
        v43 = (enum Task::STEP_RESULT *)(*(_QWORD *)(v28 + 200) + 18LL);
        dbgobj::DbgPrint<unsigned short,unsigned long,_GUID,unsigned short const *,_GUID>(
          (unsigned int)&v39,
          (unsigned int)L"Repolling updates in:%d connId:%? csName:%ws csId:%?",
          (_DWORD)this + 192,
          *((_QWORD *)this + 28) + 168,
          (__int64)&v43,
          v28 + 168);
      }
    }
    else
    {
      if ( !(_DWORD)v44 )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v39 = L"UpdateWorker::ConsumeUpdates";
          v40 = 473;
          v41 = 4;
          v42 = L"UPMG";
          v30 = *((_QWORD *)this + 27);
          v43 = (enum Task::STEP_RESULT *)(*(_QWORD *)(v30 + 200) + 18LL);
          dbgobj::DbgPrint<unsigned short,_GUID,unsigned short const *,_GUID>(
            (unsigned int)&v39,
            (unsigned int)L"No pending updates. connId:%? csName:%ws csId:%?",
            *((_QWORD *)this + 28) + 168,
            (unsigned int)&v43,
            v30 + 168);
          v6 = 2;
        }
        goto LABEL_83;
      }
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v39 = L"UpdateWorker::ConsumeUpdates";
        v40 = 468;
        v41 = 4;
        v42 = L"UPMG";
        v29 = *((_QWORD *)this + 27);
        v43 = (enum Task::STEP_RESULT *)(*(_QWORD *)(v29 + 200) + 18LL);
        dbgobj::DbgPrint<unsigned short,_GUID,unsigned short const *,_GUID>(
          (unsigned int)&v39,
          (unsigned int)L"Available updates were locked. connId:%? csName:%ws csId:%?",
          *((_QWORD *)this + 28) + 168,
          (unsigned int)&v43,
          v29 + 168);
      }
      *((_DWORD *)this + 48) = Settings::GenericDwordSetting::operator()(&Settings::RetryTimeoutMinMs);
    }
    *(_DWORD *)v2 = 1;
    goto LABEL_91;
  }
  for ( i = *(struct HistoryRecord **)v49[0];
        ;
        std::_List_iterator<std::_List_val<std::_List_simple_types<CreditManager::ICallback *>>>::operator++(&i) )
  {
    v33 = (_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(
                      v49,
                      &v43);
    if ( v34 == *v33 )
      break;
    v35 = (UpdateReference **)std::_List_iterator<std::_List_val<std::_List_simple_types<FileId>>>::operator*(&i);
    InConnection::UpdateProcessed(
      *((InConnection **)this + 28),
      *(_QWORD *)(*((_QWORD *)*v35 + 34) + 728LL),
      *(_DWORD *)(*((_QWORD *)*v35 + 34) + 776LL));
    if ( *v35 )
      UpdateReference::`scalar deleting destructor'(*v35, v36);
  }
  std::list<unsigned long>::clear(v49);
  *(_DWORD *)v2 = 1;
  *((_DWORD *)this + 48) = Settings::GenericDwordSetting::operator()(&Settings::RetryTimeoutMinMs);
LABEL_91:
  std::list<unsigned long>::~list<unsigned long>(v49);
  return (struct FrsStatus *)v4;
}

```

## disassembly

```asm
0x14018f34c  mov     [rsp-8+arg_10], rbx
0x14018f351  push    rbp
0x14018f352  push    rsi
0x14018f353  push    rdi
0x14018f354  push    r12
0x14018f356  push    r13
0x14018f358  push    r14
0x14018f35a  push    r15
0x14018f35c  lea     rbp, [rsp-30h]
0x14018f361  sub     rsp, 130h
0x14018f368  mov     rax, cs:__security_cookie
0x14018f36f  xor     rax, rsp
0x14018f372  mov     [rbp+60h+var_38], rax
0x14018f376  mov     r15, rdx
0x14018f379  mov     [rsp+160h+var_F0], rdx
0x14018f37e  mov     rsi, rcx
0x14018f381  xor     edi, edi
0x14018f383  mov     ebx, edi
0x14018f385  lea     rcx, [rbp+60h+var_C0]
0x14018f389  call    ??$?0$$V@?$_Compressed_pair@V?$allocator@U?$_List_node@VWaiter@?$MultiCREW@_KVCREWLock@@@@PEAX@std@@@std@@V?$_List_val@U?$_List_simple_types@VWaiter@?$MultiCREW@_KVCREWLock@@@@@std@@@2@$00@std@@QEAA@U_Zero_then_variadic_args_t@1@@Z; std::_Compressed_pair<std::allocator<std::_List_node<MultiCREW<unsigned __int64,CREWLock>::Waiter,void *>>,std::_List_val<std::_List_simple_types<MultiCREW<unsigned __int64,CREWLock>::Waiter>>,1>::_Compressed_pair<std::allocator<std::_List_node<MultiCREW<unsigned __int64,CREWLock>::Waiter,void *>>,std::_List_val<std::_List_simple_types<MultiCREW<unsigned __int64,CREWLock>::Waiter>>,1>(std::_Zero_then_variadic_args_t)
0x14018f38e  lea     rcx, [rbp+60h+var_C0]
0x14018f392  call    ?_Alloc_sentinel_and_proxy@?$list@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::list<void *>::_Alloc_sentinel_and_proxy(void)
0x14018f397  nop
0x14018f398  lea     r13d, [rdi+2]
0x14018f39c  mov     [r15], r13d
0x14018f39f  mov     [rsp+160h+var_110], rdi
0x14018f3a4  mov     dword ptr [rsp+160h+var_E8], edi
0x14018f3a8  lea     r14, [rsi+0C0h]
0x14018f3af  mov     [r14], edi
0x14018f3b2  mov     rcx, [rsi+0D8h]
0x14018f3b9  add     rcx, 108h; this
0x14018f3c0  mov     [rsp+160h+var_130], r14; __int64
0x14018f3c5  lea     rax, [rsp+160h+var_E8]
0x14018f3ca  mov     [rsp+160h+var_138], rax; __int64
0x14018f3cf  lea     rax, [rbp+60h+var_C0]
0x14018f3d3  mov     [rsp+160h+var_140], rax; __int64
0x14018f3d8  lea     r9, [rsp+160h+var_110]
0x14018f3dd  mov     r8, rsi
0x14018f3e0  mov     rdx, [rsi+0D0h]
0x14018f3e7  call    ?Retrieve@UpdateLock@@QEAAXPEAVUpdateManager@@PEAVIUpdateTask@@PEAPEAVUpdateReference@@PEAV?$list@PEAVUpdateReference@@V?$allocator@PEAVUpdateReference@@@std@@@std@@PEAHPEAK@Z; UpdateLock::Retrieve(UpdateManager *,IUpdateTask *,UpdateReference * *,std::list<UpdateReference *> *,int *,ulong *)
0x14018f3ec  mov     rax, [rsp+160h+var_110]
0x14018f3f1  lea     r12d, [rdi+1]
0x14018f3f5  test    rax, rax
0x14018f3f8  jz      loc_14018FB70
0x14018f3fe  mov     r15, [rax+110h]
0x14018f405  mov     ecx, [rsi+0ECh]
0x14018f40b  lea     r14d, [rdi+5]
0x14018f40f  lea     r13, aUpdateworkerCo_0; "UpdateWorker::ConsumeUpdates"
0x14018f416  lea     rax, aUpmg; "UPMG"
0x14018f41d  cmp     [r15+308h], r12d
0x14018f424  jz      short loc_14018F499
0x14018f426  test    ecx, ecx
0x14018f428  jnz     loc_14018F504
0x14018f42e  mov     [rsi+0ECh], r12d
0x14018f435  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14018f43c  test    rcx, rcx
0x14018f43f  jz      short loc_14018F484
0x14018f441  cmp     [rcx+40h], edi
0x14018f444  jz      short loc_14018F484
0x14018f446  cmp     [rcx+38h], r14d
0x14018f44a  jl      short loc_14018F484
0x14018f44c  mov     [rbp+60h+var_B0], r13
0x14018f450  mov     [rbp+60h+var_A8], 118h
0x14018f457  mov     [rbp+60h+var_A4], r14d
0x14018f45b  mov     [rbp+60h+var_A0], rax
0x14018f45f  mov     [rbp+60h+var_C8], rsi
0x14018f463  mov     eax, [rsi+0A8h]
0x14018f469  mov     [rbp+60h+var_D0], eax
0x14018f46c  lea     r9, [rbp+60h+var_C8]
0x14018f470  lea     r8, [rbp+60h+var_D0]
0x14018f474  lea     rdx, aRegisternormal; "RegisterNormalUpdate task:%? taskPtr:%p"
0x14018f47b  lea     rcx, [rbp+60h+var_B0]
0x14018f47f  call    ??$DbgPrint@GI_K@dbgobj@@QEAA_KPEBGAEBIAEB_K@Z; dbgobj::DbgPrint<ushort,uint,unsigned __int64>(ushort const *,uint const &,unsigned __int64 const &)
0x14018f484  mov     rax, [rsi+0D0h]
0x14018f48b  mov     rcx, [rax+18h]
0x14018f48f  lock add [rcx+4A0h], r12d
0x14018f497  jmp     short loc_14018F504
0x14018f499  test    ecx, ecx
0x14018f49b  jz      short loc_14018F504
0x14018f49d  mov     [rsi+0ECh], edi
0x14018f4a3  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14018f4aa  test    rcx, rcx
0x14018f4ad  jz      short loc_14018F4F2
0x14018f4af  cmp     [rcx+40h], edi
0x14018f4b2  jz      short loc_14018F4F2
0x14018f4b4  cmp     [rcx+38h], r14d
0x14018f4b8  jl      short loc_14018F4F2
0x14018f4ba  mov     [rbp+60h+var_58], r13
0x14018f4be  mov     [rbp+60h+var_50], 11Fh
0x14018f4c5  mov     [rbp+60h+var_4C], r14d
0x14018f4c9  mov     [rbp+60h+var_48], rax
0x14018f4cd  mov     [rbp+60h+var_E0], rsi
0x14018f4d1  mov     eax, [rsi+0A8h]
0x14018f4d7  mov     dword ptr [rbp+60h+var_D8], eax
0x14018f4da  lea     r9, [rbp+60h+var_E0]
0x14018f4de  lea     r8, [rbp+60h+var_D8]
0x14018f4e2  lea     rdx, aUnregisternorm; "UnregisterNormalUpdate task:%? taskPtr:"...
0x14018f4e9  lea     rcx, [rbp+60h+var_58]
0x14018f4ed  call    ??$DbgPrint@GI_K@dbgobj@@QEAA_KPEBGAEBIAEB_K@Z; dbgobj::DbgPrint<ushort,uint,unsigned __int64>(ushort const *,uint const &,unsigned __int64 const &)
0x14018f4f2  mov     rax, [rsi+0D0h]
0x14018f4f9  mov     rcx, [rax+18h]
0x14018f4fd  lock dec dword ptr [rcx+4A0h]
0x14018f504  mov     rbx, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x14018f50b  lea     rcx, [rbx+328h]; lpCriticalSection
0x14018f512  call    cs:__imp_EnterCriticalSection
0x14018f519  nop     dword ptr [rax+rax+00h]
0x14018f51e  mov     [rbx+320h], r12d
0x14018f525  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14018f52c  test    rax, rax
0x14018f52f  jz      short loc_14018F568
0x14018f531  cmp     [rax+40h], edi
0x14018f534  jz      short loc_14018F568
0x14018f536  lea     rbx, aUpmg; "UPMG"
0x14018f53d  cmp     [rax+38h], r14d
0x14018f541  jl      short loc_14018F56F
0x14018f543  mov     [rbp+60h+var_58], r13
0x14018f547  mov     [rbp+60h+var_50], 124h
0x14018f54e  mov     [rbp+60h+var_4C], r14d
0x14018f552  mov     [rbp+60h+var_48], rbx
0x14018f556  lea     rdx, aUpdateIdupdate; "Update idUpdateInfoHistory"
0x14018f55d  lea     rcx, [rbp+60h+var_58]
0x14018f561  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x14018f566  jmp     short loc_14018F56F
0x14018f568  lea     rbx, aUpmg; "UPMG"
0x14018f56f  mov     rdx, [rsp+160h+var_110]; struct HistoryRecord *
0x14018f574  mov     dword ptr [rdx+48h], 2
0x14018f57b  mov     rcx, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x14018f582  add     rcx, 2E8h; this
0x14018f589  call    ?Update@IdUpdateInfoHistoryProcessor@@MEAAXPEAVHistoryRecord@@@Z; IdUpdateInfoHistoryProcessor::Update(HistoryRecord *)
0x14018f58e  mov     rcx, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x14018f595  mov     [rcx+320h], edi
0x14018f59b  add     rcx, 328h; lpCriticalSection
0x14018f5a2  call    cs:__imp_LeaveCriticalSection
0x14018f5a9  nop     dword ptr [rax+rax+00h]
0x14018f5ae  lea     rdx, [rsi+20h]; struct ShutdownObject *
0x14018f5b2  mov     rcx, r15; this
0x14018f5b5  call    ?Install@Meet@@QEAAPEAVFrsStatus@@AEAVShutdownObject@@@Z; Meet::Install(ShutdownObject &)
0x14018f5ba  mov     [rbp+60h+var_C8], rax
0x14018f5be  test    rax, rax
0x14018f5c1  jz      loc_14018F64F
0x14018f5c7  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14018f5ce  test    rcx, rcx
0x14018f5d1  jz      short loc_14018F604
0x14018f5d3  cmp     [rcx+40h], edi
0x14018f5d6  jz      short loc_14018F604
0x14018f5d8  cmp     [rcx+38h], r14d
0x14018f5dc  jl      short loc_14018F604
0x14018f5de  mov     [rbp+60h+var_58], r13
0x14018f5e2  mov     [rbp+60h+var_50], 12Ch
0x14018f5e9  mov     [rbp+60h+var_4C], r14d
0x14018f5ed  mov     [rbp+60h+var_48], rbx
0x14018f5f1  mov     r8, rax
0x14018f5f4  lea     rdx, aInstallError; "Install error: %?"
0x14018f5fb  lea     rcx, [rbp+60h+var_58]
0x14018f5ff  call    ??$DbgPrint@GVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStatus>(ushort const *,FrsStatus const &)
0x14018f604  lea     r8, [r15+28h]
0x14018f608  mov     eax, [r15+308h]
0x14018f60f  mov     dword ptr [rsp+160h+var_138], eax; int
0x14018f613  mov     rax, [r15+2D8h]
0x14018f61a  mov     [rsp+160h+var_140], rax; __int64
0x14018f61f  mov     r9d, [r15+24h]
0x14018f623  mov     edx, r12d
0x14018f626  mov     rcx, [rsi+0E0h]; this
0x14018f62d  call    ?UpdateProcessed@InConnection@@QEAAXW4PROCESS_STATUS@1@AEBVID_UPDATE@@W4UPDATE_TYPE@@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@VSessionInfo@@@std@@@std@@@std@@W4SYNC_TYPE@@PEAVUpdateCancelData@@@Z; InConnection::UpdateProcessed(InConnection::PROCESS_STATUS,ID_UPDATE const &,UPDATE_TYPE,std::_List_iterator<std::_List_val<std::_List_simple_types<SessionInfo>>>,SYNC_TYPE,UpdateCancelData *)
0x14018f632  mov     rcx, [rsi+0D8h]
0x14018f639  add     rcx, 108h; this
0x14018f640  mov     rdx, [rsp+160h+var_110]; struct UpdateReference *
0x14018f645  call    ?Cancel@UpdateLock@@QEAAXPEAVUpdateReference@@@Z; UpdateLock::Cancel(UpdateReference *)
0x14018f64a  jmp     loc_14018F913
0x14018f64f  lea     rcx, [rbp+60h+var_B0]
0x14018f653  call    ??0?$PtrList@VContentSetInfo@@@@QEAA@XZ; PtrList<ContentSetInfo>::PtrList<ContentSetInfo>(void)
0x14018f658  nop
0x14018f659  mov     rbx, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x14018f660  lea     rcx, [rbx+2C0h]; lpCriticalSection
0x14018f667  call    cs:__imp_EnterCriticalSection
0x14018f66e  nop     dword ptr [rax+rax+00h]
0x14018f673  mov     [rbx+2B8h], r12d
0x14018f67a  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14018f681  test    rax, rax
0x14018f684  jz      short loc_14018F6BD
0x14018f686  cmp     [rax+40h], edi
0x14018f689  jz      short loc_14018F6BD
0x14018f68b  lea     rbx, aUpmg; "UPMG"
0x14018f692  cmp     [rax+38h], r14d
0x14018f696  jl      short loc_14018F6C4
0x14018f698  mov     [rbp+60h+var_58], r13
0x14018f69c  mov     [rbp+60h+var_50], 13Bh
0x14018f6a3  mov     [rbp+60h+var_4C], r14d
0x14018f6a7  mov     [rbp+60h+var_48], rbx
0x14018f6ab  lea     rdx, aUpdateContenti; "Update contentInfoHistory"
0x14018f6b2  lea     rcx, [rbp+60h+var_58]
0x14018f6b6  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x14018f6bb  jmp     short loc_14018F6C4
0x14018f6bd  lea     rbx, aUpmg; "UPMG"
0x14018f6c4  mov     rcx, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x14018f6cb  add     rcx, 280h
0x14018f6d2  lea     rdx, [r15+70h]
0x14018f6d6  lea     r8, [rbp+60h+var_B0]
0x14018f6da  call    ?FindByCxtionGuid@ConnectionInfoHistory@@QEAAKPEBU_GUID@@PEAV?$PtrList@VConnectionInfo@@@@@Z; ConnectionInfoHistory::FindByCxtionGuid(_GUID const *,PtrList<ConnectionInfo> *)
0x14018f6df  test    eax, eax
0x14018f6e1  jz      loc_14018F7ED
0x14018f6e7  lea     rcx, [rbp+60h+var_A8]
0x14018f6eb  call    ?at@?$vector@PEAVMemberInfo@@V?$allocator@PEAVMemberInfo@@@std@@@std@@QEBAAEBQEAVMemberInfo@@_K@Z; std::vector<MemberInfo *>::at(unsigned __int64)
0x14018f6f0  mov     rax, [rax]
0x14018f6f3  mov     [rbp+60h+var_D8], rax
0x14018f6f7  cmp     dword ptr [r15+20h], 4
0x14018f6fc  jnz     short loc_14018F767
0x14018f6fe  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14018f705  test    rax, rax
0x14018f708  jz      short loc_14018F73C
0x14018f70a  cmp     [rax+40h], edi
0x14018f70d  jz      short loc_14018F73C
0x14018f70f  cmp     [rax+38h], r14d
0x14018f713  jl      short loc_14018F73C
0x14018f715  mov     [rbp+60h+var_58], r13
0x14018f719  mov     [rbp+60h+var_50], 146h
0x14018f720  mov     [rbp+60h+var_4C], r14d
0x14018f724  mov     [rbp+60h+var_48], rbx
0x14018f728  lea     r8, [r15+28h]
0x14018f72c  lea     rdx, aAddingBlockedR; "Adding blocked record to content set in"...
0x14018f733  lea     rcx, [rbp+60h+var_58]
0x14018f737  call    ??$DbgPrint@GVID_UPDATE@@@dbgobj@@QEAA_KPEBGAEBVID_UPDATE@@@Z; dbgobj::DbgPrint<ushort,ID_UPDATE>(ushort const *,ID_UPDATE const &)
0x14018f73c  mov     r9, [rbp+60h+var_D8]
0x14018f740  lea     r8, [r15+24h]
0x14018f744  lea     rdx, [r15+28h]
0x14018f748  lea     rcx, [rbp+60h+var_58]
0x14018f74c  call    ??$?0AEAVUID@@AEAW4UPDATE_TYPE@@$0A@@?$pair@VUID@@W4UPDATE_TYPE@@@std@@QEAA@AEAVUID@@AEAW4UPDATE_TYPE@@@Z; std::pair<UID,UPDATE_TYPE>::pair<UID,UPDATE_TYPE>(UID &,UPDATE_TYPE &)
0x14018f751  lea     r8, [rbp+60h+var_58]
0x14018f755  lea     rdx, [rbp+60h+var_68]
0x14018f759  lea     rcx, [r9+0B0h]
0x14018f760  call    ??$insert@U?$pair@VUID@@W4UPDATE_TYPE@@@std@@$0A@@?$map@VUID@@W4UPDATE_TYPE@@U?$less@VUID@@@std@@V?$allocator@U?$pair@$$CBVUID@@W4UPDATE_TYPE@@@std@@@4@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVUID@@W4UPDATE_TYPE@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@VUID@@W4UPDATE_TYPE@@@1@@Z; std::map<UID,UPDATE_TYPE>::insert<std::pair<UID,UPDATE_TYPE>,0>(std::pair<UID,UPDATE_TYPE> &&)
0x14018f765  jmp     short loc_14018F7BF
0x14018f767  lea     rcx, [rax+0B0h]
0x14018f76e  lea     rdx, [r15+28h]
0x14018f772  call    ?erase@?$_Tree@V?$_Tmap_traits@VUID@@W4UPDATE_TYPE@@U?$less@VUID@@@std@@V?$allocator@U?$pair@$$CBVUID@@W4UPDATE_TYPE@@@std@@@4@$0A@@std@@@std@@QEAA_KAEBVUID@@@Z; std::_Tree<std::_Tmap_traits<UID,UPDATE_TYPE,std::less<UID>,std::allocator<std::pair<UID const,UPDATE_TYPE>>,0>>::erase(UID const &)
0x14018f777  test    rax, rax
0x14018f77a  jz      short loc_14018F7BF
0x14018f77c  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14018f783  test    rax, rax
0x14018f786  jz      short loc_14018F7BF
0x14018f788  cmp     [rax+40h], edi
0x14018f78b  jz      short loc_14018F7BF
0x14018f78d  cmp     [rax+38h], r14d
0x14018f791  jl      short loc_14018F7BF
0x14018f793  mov     [rsp+160h+var_108], r13
0x14018f798  mov     [rsp+160h+var_100], 14Fh
0x14018f7a0  mov     [rsp+160h+var_FC], r14d
0x14018f7a5  mov     [rsp+160h+var_F8], rbx
0x14018f7aa  lea     r8, [r15+28h]
0x14018f7ae  lea     rdx, aRemovedBlocked; "Removed blocked record from content set"...
0x14018f7b5  lea     rcx, [rsp+160h+var_108]
0x14018f7ba  call    ??$DbgPrint@GVID_UPDATE@@@dbgobj@@QEAA_KPEBGAEBVID_UPDATE@@@Z; dbgobj::DbgPrint<ushort,ID_UPDATE>(ushort const *,ID_UPDATE const &)
0x14018f7bf  mov     rbx, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x14018f7c6  mov     rdx, [rbp+60h+var_D8]
0x14018f7ca  add     rdx, 0B0h
0x14018f7d1  lea     rcx, [rbp+60h+var_88]
0x14018f7d5  call    ??0?$map@VUID@@W4UPDATE_TYPE@@U?$less@VUID@@@std@@V?$allocator@U?$pair@$$CBVUID@@W4UPDATE_TYPE@@@std@@@4@@std@@QEAA@AEBV01@@Z; std::map<UID,UPDATE_TYPE>::map<UID,UPDATE_TYPE>(std::map<UID,UPDATE_TYPE> const &)
0x14018f7da  mov     r8, rax
0x14018f7dd  lea     rdx, [r15+70h]
0x14018f7e1  lea     rcx, [rbx+280h]
0x14018f7e8  call    ?UpdateBlockedIds@ContentSetInfoHistory@@QEAAXPEBU_GUID@@V?$map@VUID@@W4UPDATE_TYPE@@U?$less@VUID@@@std@@V?$allocator@U?$pair@$$CBVUID@@W4UPDATE_TYPE@@@std@@@4@@std@@@Z; ContentSetInfoHistory::UpdateBlockedIds(_GUID const *,std::map<UID,UPDATE_TYPE>)
0x14018f7ed  mov     rcx, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x14018f7f4  mov     [rcx+2B8h], edi
0x14018f7fa  add     rcx, 2C0h; lpCriticalSection
0x14018f801  call    cs:__imp_LeaveCriticalSection
0x14018f808  nop     dword ptr [rax+rax+00h]
0x14018f80d  mov     ecx, [r15+20h]
0x14018f811  sub     ecx, 1
0x14018f814  jz      loc_14018F8C1
0x14018f81a  sub     ecx, 1
0x14018f81d  jz      loc_14018FAA4
0x14018f823  sub     ecx, 1
0x14018f826  jz      loc_14018FA0C
0x14018f82c  sub     ecx, 1
0x14018f82f  jz      loc_14018F924
0x14018f835  cmp     ecx, 1
0x14018f838  jz      short loc_14018F842
0x14018f83a  mov     edx, r12d
0x14018f83d  jmp     loc_14018F8C6
0x14018f842  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14018f849  test    rax, rax
0x14018f84c  jz      short loc_14018F8C1
0x14018f84e  cmp     [rax+40h], edi
0x14018f851  jz      short loc_14018F8C1
0x14018f853  cmp     dword ptr [rax+38h], 4
0x14018f857  jl      short loc_14018F8C1
0x14018f859  mov     [rsp+160h+var_108], r13
0x14018f85e  mov     [rsp+160h+var_100], 16Eh
0x14018f866  mov     [rsp+160h+var_FC], 4
0x14018f86e  lea     rbx, aUpmg; "UPMG"
0x14018f875  mov     [rsp+160h+var_F8], rbx
0x14018f87a  mov     rax, [rsi+0D8h]
0x14018f881  lea     rdx, [rax+0A8h]
0x14018f888  mov     rcx, [rax+0C8h]
0x14018f88f  add     rcx, 12h
0x14018f893  mov     [rbp+60h+var_E0], rcx
0x14018f897  mov     r9, [rsi+0E0h]
0x14018f89e  add     r9, 0A8h
0x14018f8a5  lea     r8, [r15+40h]
0x14018f8a9  mov     [rsp+160h+var_138], rdx
  ... truncated ...
```
