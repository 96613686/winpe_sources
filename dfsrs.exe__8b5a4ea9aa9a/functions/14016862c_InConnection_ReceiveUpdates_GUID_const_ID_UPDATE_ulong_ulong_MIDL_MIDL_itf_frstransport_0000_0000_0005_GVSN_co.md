# InConnection::ReceiveUpdates(_GUID const &,ID_UPDATE *,ulong,ulong,__MIDL___MIDL_itf_frstransport_0000_0000_0005,GVSN const &,ulong)

- ea: `0x14016862c`
- end: `0x140168f9c`
- name: `?ReceiveUpdates@InConnection@@QEAAPEAVFrsStatus@@AEBU_GUID@@PEAVID_UPDATE@@KKW4__MIDL___MIDL_itf_frstransport_0000_0000_0005@@AEBVGVSN@@K@Z`
- size: `2416`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1401aa3f0`

## callees

- `0x1400036a0`
- `0x1400036d0`
- `0x14000c910`
- `0x14000d980`
- `0x14000dcc0`
- `0x14000ee94`
- `0x140011408`
- `0x140024ebc`
- `0x14002c2f4`
- `0x14006a550`
- `0x14006d538`
- `0x14007e63c`
- `0x1400812c8`
- `0x1400925a8`
- `0x14015c4e0`
- `0x14015c75c`
- `0x14015c828`
- `0x14015c9c4`
- `0x14015e2d8`
- `0x140161300`
- `0x140166220`
- `0x14016862c`
- `0x14016e230`
- `0x14016e3f8`
- `0x14018e65c`
- `0x14018ede0`
- `0x140190104`
- `0x1401b3a04`
- `0x1401b9494`
- `0x1401bda10`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140168ae5`
- `KERNEL32!LeaveCriticalSection` at `0x140168ae5`
- `KERNEL32!EnterCriticalSection` at `0x140168a4b`
- `KERNEL32!EnterCriticalSection` at `0x140168a4b`
- `KERNEL32!GetCurrentThreadId` at `0x1401686b0`
- `KERNEL32!GetCurrentThreadId` at `0x1401686c3`
- `KERNEL32!GetCurrentThreadId` at `0x14016870b`
- `KERNEL32!GetCurrentThreadId` at `0x1401688a4`
- `KERNEL32!GetCurrentThreadId` at `0x140168976`
- `KERNEL32!GetCurrentThreadId` at `0x140168f24`
- `KERNEL32!GetCurrentThreadId` at `0x1401686b0`
- `KERNEL32!GetCurrentThreadId` at `0x1401686c3`
- `KERNEL32!GetCurrentThreadId` at `0x14016870b`
- `KERNEL32!GetCurrentThreadId` at `0x1401688a4`
- `KERNEL32!GetCurrentThreadId` at `0x140168976`
- `KERNEL32!GetCurrentThreadId` at `0x140168f24`

## string_xrefs

- `0x140168a96`: `Update syncInfoHistory`
- `0x1401686e6`: `InConnection::ReceiveUpdates`
- `0x1401688c1`: `InConnection::ReceiveUpdates`
- `0x140168f41`: `InConnection::ReceiveUpdates`
- `0x14016877d`: `InConnection::ReceiveUpdates`
- `0x140168a1b`: `InConnection::ReceiveUpdates`
- `0x140168e90`: `InConnection::ReceiveUpdates`
- `0x140168966`: `Failed to process updates received without an active session session:%d connId:%? csId:%? csName:%ws`
- `0x140168894`: `Failed to process updates received without an active session. connId:%? csId:%? csName:%ws`
- `0x140168ed8`: `[CREDIT] Returning unused credits following received updates. creditsToReturn:%? totalConnectionCreditsGranted:%? totalGlobalCreditsGranted:%? connId:%?`
- `0x140168e41`: `Session has been closed. sessionId:%d connId:%? csId:%? csName:%ws`
- `0x140168d0b`: `[CREDIT] Returning unused credits following received updates. creditsToReturn:%? totalConnectionCreditsGranted:%? totalGlobalCreditsGranted:%? outstandingCredits:%? connId:%? csId:%? csName:%? sessionTaskPtr:%p`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall InConnection::ReceiveUpdates(
        _DWORD *a1,
        struct _GUID *a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        _OWORD *a7,
        unsigned int a8)
{
  struct _GUID *v8; // r15
  unsigned int v10; // r14d
  unsigned int v11; // ebx
  __int64 v12; // r12
  char v13; // si
  unsigned int *v14; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v16; // rcx
  __int64 v17; // r9
  __int64 v18; // rbx
  DWORD v19; // eax
  __int64 v20; // rcx
  const wchar_t *v21; // r8
  const wchar_t *v22; // r9
  struct InConnection::InConnectionContentSetContext *v23; // rbx
  LPCRITICAL_SECTION v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  const wchar_t *v30; // r9
  int v31; // r10d
  int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // rax
  unsigned int v35; // ecx
  struct UpdateManager *v36; // r15
  __int64 updated; // rax
  unsigned int v38; // r14d
  __int64 v39; // rsi
  struct MonitorContext *v40; // rbx
  struct _RTL_CRITICAL_SECTION *v41; // rcx
  __int64 v42; // rax
  _OWORD *v43; // rcx
  __int64 v44; // r14
  RefCountObject *v45; // rcx
  __int64 *v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // rax
  struct ISessionTaskWithCredits *v49; // r8
  int v50; // eax
  int v51; // eax
  DWORD v52; // eax
  __int64 v53; // rcx
  DWORD v55; // [rsp+38h] [rbp-C8h]
  DWORD v56; // [rsp+38h] [rbp-C8h]
  unsigned int v57; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v58; // [rsp+58h] [rbp-A8h] BYREF
  struct _GUID *v59; // [rsp+60h] [rbp-A0h]
  struct InConnection::InConnectionContentSetContext *v60; // [rsp+68h] [rbp-98h] BYREF
  __int64 v61; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v62; // [rsp+78h] [rbp-88h] BYREF
  int v63; // [rsp+80h] [rbp-80h]
  struct UpdateManager **v64; // [rsp+88h] [rbp-78h] BYREF
  __int64 v65; // [rsp+90h] [rbp-70h] BYREF
  __int64 v66; // [rsp+98h] [rbp-68h] BYREF
  const wchar_t *v67; // [rsp+A0h] [rbp-60h] BYREF
  int v68; // [rsp+A8h] [rbp-58h]
  int v69; // [rsp+ACh] [rbp-54h]
  const wchar_t *v70; // [rsp+B0h] [rbp-50h]
  __int64 v71; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v72; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v73; // [rsp+C8h] [rbp-38h] BYREF
  int v74; // [rsp+D0h] [rbp-30h]
  int v75; // [rsp+D4h] [rbp-2Ch]
  const wchar_t *v76; // [rsp+D8h] [rbp-28h]
  const wchar_t *v77; // [rsp+E0h] [rbp-20h] BYREF
  int v78; // [rsp+E8h] [rbp-18h]
  int v79; // [rsp+ECh] [rbp-14h]
  const wchar_t *v80; // [rsp+F0h] [rbp-10h]
  const wchar_t *v81; // [rsp+F8h] [rbp-8h] BYREF
  int v82; // [rsp+100h] [rbp+0h]
  int v83; // [rsp+104h] [rbp+4h]
  const wchar_t *v84; // [rsp+108h] [rbp+8h]
  const wchar_t *v85; // [rsp+110h] [rbp+10h] BYREF
  int v86; // [rsp+118h] [rbp+18h]
  int v87; // [rsp+11Ch] [rbp+1Ch]
  const wchar_t *v88; // [rsp+120h] [rbp+20h]
  const wchar_t *v89; // [rsp+128h] [rbp+28h] BYREF
  int v90; // [rsp+130h] [rbp+30h]
  int v91; // [rsp+134h] [rbp+34h]
  const wchar_t *v92; // [rsp+138h] [rbp+38h]
  const wchar_t *v93; // [rsp+140h] [rbp+40h] BYREF
  int v94; // [rsp+148h] [rbp+48h]
  int v95; // [rsp+14Ch] [rbp+4Ch]
  const wchar_t *v96; // [rsp+150h] [rbp+50h]
  _BYTE v97[16]; // [rsp+158h] [rbp+58h] BYREF
  __int128 v98; // [rsp+168h] [rbp+68h] BYREF
  __int128 v99; // [rsp+178h] [rbp+78h] BYREF
  __int64 v100; // [rsp+188h] [rbp+88h]
  __int128 v101; // [rsp+190h] [rbp+90h] BYREF
  __int64 v102; // [rsp+1A0h] [rbp+A0h]

  v61 = a3;
  v8 = a2;
  v59 = a2;
  v62 = a4;
  v10 = a6;
  LODWORD(v58) = a6;
  v11 = a8;
  v12 = 0;
  v13 = 0;
  LODWORD(v66) = 0;
  v63 = 0;
  v57 = a4;
  v60 = 0;
  v14 = 0;
  if ( a8 )
  {
    CurrentThreadId = GetCurrentThreadId();
    if ( v11 - 9001 > 0x25D )
      v17 = 1;
    else
      v17 = 3;
    v18 = FrsStatusList::PushNewError(
            v16,
            v11,
            0,
            v17,
            "base\\fs\\remotefs\\frs\\src\\sync\\inconnection.cpp",
            "InConnection::ReceiveUpdates",
            2968,
            CurrentThreadId,
            0);
    v19 = GetCurrentThreadId();
    v14 = (unsigned int *)FrsStatusList::PushNewError(
                            v20,
                            9027,
                            1,
                            3,
                            "base\\fs\\remotefs\\frs\\src\\sync\\inconnection.cpp",
                            "InConnection::ReceiveUpdates",
                            2976,
                            v19,
                            v18);
  }
  ScopedLock::ScopedLock((ScopedLock *)v97, (struct ScopedCS *)(a1 + 248));
  if ( (unsigned int)RefMap<_GUID,InConnection::InConnectionContentSetContext,std::less<_GUID>>::Find(
                       a1 + 276,
                       v8,
                       &v60) )
  {
    v22 = L"INCO";
    v23 = v60;
    v24 = g_DebugLog;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v73 = L"InConnection::ReceiveUpdates";
      v74 = 2991;
      v75 = 4;
      v76 = L"INCO";
      v72 = *(_QWORD *)(*((_QWORD *)v60 + 4) + 200LL) + 18LL;
      dbgobj::DbgPrint<unsigned short,unsigned long,unsigned long,unsigned long,_GUID,_GUID,unsigned short const *>(
        (unsigned int)&v73,
        (_DWORD)g_DebugLog,
        (_DWORD)v60 + 124,
        (unsigned int)&v62,
        (__int64)&a5,
        (__int64)(a1 + 42),
        (__int64)v59,
        (__int64)&v72);
      v24 = g_DebugLog;
      v22 = L"INCO";
    }
    if ( v14 )
      goto LABEL_47;
    if ( *((_DWORD *)v23 + 55) != 5 )
      goto LABEL_46;
    if ( !*((_QWORD *)v23 + 11) )
    {
      if ( v24 && LODWORD(v24[1].LockSemaphore) && SLODWORD(v24[1].OwningThread) >= 2 )
      {
        v77 = L"InConnection::ReceiveUpdates";
        v78 = 3011;
        v79 = 2;
        v80 = L"INCO";
        v61 = *(_QWORD *)(*((_QWORD *)v23 + 4) + 200LL) + 18LL;
        dbgobj::DbgPrint<unsigned short,_GUID,_GUID,unsigned short const *>(
          (unsigned int)&v77,
          (unsigned int)L"Failed to process updates received without an active session. connId:%? csId:%? csName:%ws",
          (_DWORD)a1 + 168,
          (_DWORD)v59,
          (__int64)&v61);
      }
      v55 = GetCurrentThreadId();
      v26 = FrsStatusList::PushNewError(
              v25,
              9031,
              0,
              3,
              "base\\fs\\remotefs\\frs\\src\\sync\\inconnection.cpp",
              "InConnection::ReceiveUpdates",
              3016,
              v55,
              0);
      goto LABEL_74;
    }
    if ( !*(_DWORD *)(std::list<SessionInfo>::back((char *)v23 + 80) + 64) )
    {
      if ( v27 && *(_DWORD *)(v27 + 64) && *(_DWORD *)(v27 + 56) >= v31 )
      {
        v67 = L"InConnection::ReceiveUpdates";
        v68 = 3021;
        v69 = v31;
        v70 = v30;
        v61 = *(_QWORD *)(*((_QWORD *)v23 + 4) + 200LL) + 18LL;
        v32 = std::list<SessionInfo>::back(v29);
        dbgobj::DbgPrint<unsigned short,unsigned long,_GUID,_GUID,unsigned short const *>(
          (unsigned int)&v67,
          (unsigned int)L"Failed to process updates received without an active session session:%d connId:%? csId:%? csName:%ws",
          v32 + 60,
          (_DWORD)a1 + 168,
          (__int64)v59,
          (__int64)&v61);
      }
      v56 = GetCurrentThreadId();
      v26 = FrsStatusList::PushNewError(
              v33,
              9031,
              0,
              3,
              "base\\fs\\remotefs\\frs\\src\\sync\\inconnection.cpp",
              "InConnection::ReceiveUpdates",
              3028,
              v56,
              0);
      goto LABEL_74;
    }
    v34 = std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(
            v28,
            &v98);
    v65 = *(_QWORD *)std::_List_iterator<std::_List_val<std::_List_simple_types<SessionInfo>>>::operator--(v34);
    v64 = (struct UpdateManager **)((char *)v23 + 48);
    v35 = a5;
    if ( !*((_QWORD *)v23 + 6) && a5 )
    {
      v36 = (struct UpdateManager *)operator new(0x40u);
      v71 = (__int64)v36;
      Settings::GenericDwordSetting::operator()(&Settings::UpdateWorkerThreadCount);
      updated = UpdateManager::UpdateManager(v36, (__int64)(a1 + 316), (__int64)v23 + 32);
      *v64 = (struct UpdateManager *)updated;
      v35 = a5;
      v13 = v66;
    }
    v38 = 0;
    if ( v35 )
    {
      v39 = std::_List_iterator<std::_List_val<std::_List_simple_types<CONTENT_SET_RECORD>>>::operator->(&v65);
      do
      {
        _InterlockedIncrement((volatile signed __int32 *)(v39 + 52));
        v40 = g_MonitorContext;
        EnterCriticalSection((LPCRITICAL_SECTION)g_MonitorContext + 15);
        *((_DWORD *)v40 + 148) = 1;
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v81 = L"InConnection::ReceiveUpdates";
          v82 = 3060;
          v83 = 5;
          v84 = L"INCO";
          dbgobj::DbgPrint<unsigned short>(&v81, L"Update syncInfoHistory");
        }
        ++a1[181];
        StateHistory::Update(
          (struct MonitorContext *)((char *)g_MonitorContext + 536),
          (struct HistoryRecord *)(a1 + 134));
        v41 = (struct _RTL_CRITICAL_SECTION *)g_MonitorContext;
        *((_DWORD *)g_MonitorContext + 148) = 0;
        LeaveCriticalSection(v41 + 15);
        v23 = v60;
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v85 = L"InConnection::ReceiveUpdates";
          v86 = 3065;
          v87 = 4;
          v88 = L"INCO";
          v66 = *(_QWORD *)(*((_QWORD *)v60 + 4) + 200LL) + 18LL;
          dbgobj::DbgPrint<unsigned short,UID,GVSN,unsigned short [261],unsigned long,_GUID,_GUID,unsigned short const *>(
            (unsigned int)&v85,
            v39 + 60,
            v61 + 680 * v38,
            v61 + 680 * v38 + 24,
            v61 + 680LL * v38 + 156,
            v39 + 60,
            (__int64)(a1 + 42),
            (__int64)v59,
            (__int64)&v66);
        }
        UpdateManager::ProduceUpdate(*v64);
        ++v38;
        v35 = a5;
      }
      while ( v38 < a5 );
      v13 = v63;
    }
    v57 = v62 - v35;
    if ( (_DWORD)v58 != 2 )
    {
      if ( (_DWORD)v58 == 3 )
      {
        v42 = std::_List_iterator<std::_List_val<std::_List_simple_types<CONTENT_SET_RECORD>>>::operator->(&v65);
        if ( !*(_DWORD *)(v42 + 120) )
          *(_DWORD *)(v42 + 120) = 1;
        v43 = a7;
        *(_OWORD *)(v42 + 72) = *a7;
        *(_QWORD *)(v42 + 88) = *((_QWORD *)v43 + 2);
      }
      goto LABEL_45;
    }
    v22 = (const wchar_t *)std::_List_iterator<std::_List_val<std::_List_simple_types<CONTENT_SET_RECORD>>>::operator->(&v65);
    v21 = v22 + 48;
    *(_OWORD *)(v22 + 36) = *((_OWORD *)v22 + 6);
    *((_QWORD *)v22 + 11) = *((_QWORD *)v22 + 14);
    v50 = *((_DWORD *)v22 + 30);
    if ( v50 )
    {
      v51 = v50 - 1;
      if ( !v51 )
      {
        v101 = 0;
        v102 = 0;
        if ( (unsigned __int8)GVSN::operator==(v21, &v101, v21) )
          *((_DWORD *)v22 + 30) = 2;
        goto LABEL_66;
      }
      if ( v51 != 1 )
      {
LABEL_45:
        v10 = v58;
LABEL_46:
        v14 = (unsigned int *)SessionTask::UpdatesReceiveComplete(*((_QWORD *)v23 + 9), v10, v21, v22);
LABEL_47:
        v44 = (__int64)v23 + 120;
        *((_QWORD *)v23 + 15) = *((_DWORD *)v23 + 30) - v57;
        v45 = (RefCountObject *)*((_QWORD *)v23 + 14);
        if ( v45 )
        {
          RefCountObject::Release(v45);
          *((_QWORD *)v23 + 14) = 0;
        }
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v93 = L"InConnection::ReceiveUpdates";
          v94 = 3180;
          v95 = 5;
          v96 = L"INCO";
          v46 = (__int64 *)((char *)v23 + 72);
          v58 = *((_QWORD *)v23 + 9);
          v47 = *(_QWORD *)(*((_QWORD *)v23 + 9) + 200LL);
          v64 = (struct UpdateManager **)v47;
          if ( !*(_BYTE *)(v47 + 16) )
          {
            _InterlockedIncrement((volatile signed __int32 *)v47);
            v23 = v60;
          }
          v48 = *v46;
          v13 = 3;
          v63 = 3;
          v98 = *(_OWORD *)(v48 + 184);
          dbgobj::DbgPrint<unsigned short,unsigned long,long,long,unsigned long,_GUID,Guid,FrsStringImpl<unsigned short,char>,unsigned __int64>(
            (unsigned int)&v93,
            (unsigned int)L"[CREDIT] Returning unused credits following received updates. creditsToReturn:%? totalConnecti"
                           "onCreditsGranted:%? totalGlobalCreditsGranted:%? outstandingCredits:%? connId:%? csId:%? csNa"
                           "me:%? sessionTaskPtr:%p",
            (unsigned int)&v57,
            (_DWORD)a1 + 336,
            (__int64)(a1 + 108),
            v44,
            (__int64)(a1 + 42),
            (__int64)&v98,
            (__int64)&v64,
            (__int64)&v58);
        }
        if ( (v13 & 2) != 0 )
          v13 &= ~2u;
        if ( (v13 & 1) != 0 )
          FrsStringImpl<char,unsigned short>::ReleaseBody(&v64);
        v8 = v59;
        goto LABEL_60;
      }
      v99 = 0;
      v100 = 0;
      if ( !(unsigned __int8)GVSN::operator==(v21, &v99, v21) )
      {
LABEL_66:
        v10 = 3;
        goto LABEL_46;
      }
    }
    *((_DWORD *)v22 + 16) = 0;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v89 = L"InConnection::ReceiveUpdates";
      v90 = 3129;
      v91 = 4;
      v92 = L"INCO";
      v71 = *(_QWORD *)(*((_QWORD *)v23 + 4) + 200LL) + 18LL;
      dbgobj::DbgPrint<unsigned short,unsigned long,_GUID,_GUID,unsigned short const *>(
        (unsigned int)&v89,
        (unsigned int)L"Session has been closed. sessionId:%d connId:%? csId:%? csName:%ws",
        (_DWORD)v22 + 60,
        (_DWORD)a1 + 168,
        (__int64)v59,
        (__int64)&v71);
    }
    v26 = InConnection::CommitSession((InConnection *)a1, v23);
    v10 = v58;
LABEL_74:
    v14 = (unsigned int *)v26;
    if ( v26 )
      goto LABEL_47;
    goto LABEL_46;
  }
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v67 = L"InConnection::ReceiveUpdates";
    v68 = 3192;
    v69 = 5;
    v70 = L"INCO";
    dbgobj::DbgPrint<unsigned short,unsigned long,long,long,_GUID>(
      (unsigned int)&v67,
      (unsigned int)L"[CREDIT] Returning unused credits following received updates. creditsToReturn:%? totalConnectionCred"
                     "itsGranted:%? totalGlobalCreditsGranted:%? connId:%?",
      (unsigned int)&v57,
      (_DWORD)a1 + 336,
      (__int64)(a1 + 108),
      (__int64)(a1 + 42));
  }
  v23 = v60;
LABEL_60:
  if ( v23 )
    v49 = (struct ISessionTaskWithCredits *)*((_QWORD *)v23 + 9);
  else
    v49 = 0;
  IInConnectionCreditManager::ReturnCredits((IInConnectionCreditManager *)a1, v57, v49);
  ScopedLock::~ScopedLock((ScopedLock *)v97);
  InConnection::ProcessErrorStatus((InConnection *)a1, v8, (const struct FrsStatus *)v14, 1);
  if ( v14 )
  {
    v52 = GetCurrentThreadId();
    v12 = FrsStatusList::PushNewError(
            v53,
            v14[1],
            v14[2],
            *v14,
            "base\\fs\\remotefs\\frs\\src\\sync\\inconnection.cpp",
            "InConnection::ReceiveUpdates",
            3206,
            v52,
            v14);
  }
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v60);
  return v12;
}

```

## disassembly

```asm
0x14016862c  push    rbp
0x14016862e  push    rbx
0x14016862f  push    rsi
0x140168630  push    rdi
0x140168631  push    r12
0x140168633  push    r13
0x140168635  push    r14
0x140168637  push    r15
0x140168639  lea     rbp, [rsp-0B8h]
0x140168641  sub     rsp, 1B8h
0x140168648  mov     rax, cs:__security_cookie
0x14016864f  xor     rax, rsp
0x140168652  mov     [rbp+0F0h+var_48], rax
0x140168659  mov     [rsp+1F0h+var_180], r8
0x14016865e  mov     r15, rdx
0x140168661  mov     [rsp+1F0h+var_190], rdx
0x140168666  mov     r13, rcx
0x140168669  mov     [rsp+1F0h+var_178], r9d
0x14016866e  mov     r14d, [rbp+0F0h+arg_28]
0x140168675  mov     dword ptr [rsp+1F0h+var_198], r14d
0x14016867a  mov     ebx, [rbp+0F0h+arg_38]
0x140168680  xor     r12d, r12d
0x140168683  mov     esi, r12d
0x140168686  mov     dword ptr [rbp+0F0h+var_158], r12d
0x14016868a  mov     [rbp+0F0h+var_170], r12d
0x14016868e  mov     [rsp+1F0h+var_1A0], r9d
0x140168693  mov     [rsp+1F0h+var_188], r12
0x140168698  mov     edi, r12d
0x14016869b  test    ebx, ebx
0x14016869d  jz      loc_140168750
0x1401686a3  lea     eax, [rbx-2329h]
0x1401686a9  cmp     eax, 25Dh
0x1401686ae  ja      short loc_1401686C3
0x1401686b0  call    cs:__imp_GetCurrentThreadId
0x1401686b7  nop     dword ptr [rax+rax+00h]
0x1401686bc  lea     r9d, [r12+3]
0x1401686c1  jmp     short loc_1401686D5
0x1401686c3  call    cs:__imp_GetCurrentThreadId
0x1401686ca  nop     dword ptr [rax+rax+00h]
0x1401686cf  mov     r9d, 1
0x1401686d5  mov     [rsp+1F0h+var_1B0], r12
0x1401686da  mov     dword ptr [rsp+1F0h+var_1B8], eax
0x1401686de  mov     dword ptr [rsp+1F0h+var_1C0], 0B98h
0x1401686e6  lea     rdi, aInconnectionRe_5; "InConnection::ReceiveUpdates"
0x1401686ed  mov     [rsp+1F0h+var_1C8], rdi
0x1401686f2  lea     rax, aBaseFsRemotefs_1; "base\\fs\\remotefs\\frs\\src\\sync\\inc"...
0x1401686f9  mov     [rsp+1F0h+var_1D0], rax
0x1401686fe  xor     r8d, r8d
0x140168701  mov     edx, ebx
0x140168703  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140168708  mov     rbx, rax
0x14016870b  call    cs:__imp_GetCurrentThreadId
0x140168712  nop     dword ptr [rax+rax+00h]
0x140168717  mov     [rsp+1F0h+var_1B0], rbx
0x14016871c  mov     dword ptr [rsp+1F0h+var_1B8], eax
0x140168720  mov     dword ptr [rsp+1F0h+var_1C0], 0BA0h
0x140168728  mov     [rsp+1F0h+var_1C8], rdi
0x14016872d  lea     rax, aBaseFsRemotefs_1; "base\\fs\\remotefs\\frs\\src\\sync\\inc"...
0x140168734  mov     [rsp+1F0h+var_1D0], rax
0x140168739  mov     edx, 2343h
0x14016873e  mov     r9d, 3
0x140168744  lea     r8d, [r9-2]
0x140168748  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14016874d  mov     rdi, rax
0x140168750  lea     rdx, [r13+3E0h]; struct ScopedCS *
0x140168757  lea     rcx, [rbp+0F0h+var_98]; this
0x14016875b  call    ??0ScopedLock@@QEAA@AEAVScopedCS@@@Z; ScopedLock::ScopedLock(ScopedCS &)
0x140168760  nop
0x140168761  lea     rcx, [r13+450h]
0x140168768  lea     r8, [rsp+1F0h+var_188]
0x14016876d  mov     rdx, r15
0x140168770  call    ?Find@?$RefMap@U_GUID@@VInConnectionContentSetContext@InConnection@@U?$less@U_GUID@@@std@@@@QEAAHAEBU_GUID@@AEAPEAVInConnectionContentSetContext@InConnection@@@Z; RefMap<_GUID,InConnection::InConnectionContentSetContext,std::less<_GUID>>::Find(_GUID const &,InConnection::InConnectionContentSetContext * &)
0x140168775  test    eax, eax
0x140168777  jz      loc_140168E78
0x14016877d  lea     r15, aInconnectionRe_9; "InConnection::ReceiveUpdates"
0x140168784  lea     r9, aInco; "INCO"
0x14016878b  mov     rbx, [rsp+1F0h+var_188]
0x140168790  mov     rdx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140168797  test    rdx, rdx
0x14016879a  jz      loc_140168820
0x1401687a0  cmp     [rdx+40h], r12d
0x1401687a4  jz      short loc_140168820
0x1401687a6  cmp     dword ptr [rdx+38h], 4
0x1401687aa  jl      short loc_140168820
0x1401687ac  mov     [rbp+0F0h+var_128], r15
0x1401687b0  mov     [rbp+0F0h+var_120], 0BAFh
0x1401687b7  mov     [rbp+0F0h+var_11C], 4
0x1401687be  mov     [rbp+0F0h+var_118], r9
0x1401687c2  mov     rax, [rbx+20h]
0x1401687c6  mov     rcx, [rax+0C8h]
0x1401687cd  add     rcx, 12h
0x1401687d1  mov     [rbp+0F0h+var_130], rcx
0x1401687d5  lea     r8, [rbx+7Ch]
0x1401687d9  lea     rax, [r13+0A8h]
0x1401687e0  lea     rcx, [rbp+0F0h+var_130]
0x1401687e4  mov     [rsp+1F0h+var_1B8], rcx
0x1401687e9  mov     rcx, [rsp+1F0h+var_190]
0x1401687ee  mov     [rsp+1F0h+var_1C0], rcx
0x1401687f3  mov     [rsp+1F0h+var_1C8], rax
0x1401687f8  lea     rax, [rbp+0F0h+arg_20]
0x1401687ff  mov     [rsp+1F0h+var_1D0], rax
0x140168804  lea     r9, [rsp+1F0h+var_178]
0x140168809  lea     rcx, [rbp+0F0h+var_128]
0x14016880d  call    ??$DbgPrint@GKKKU_GUID@@U1@PEBG@dbgobj@@QEAA_KPEBGAEBK11AEBU_GUID@@2AEBQEBG@Z; dbgobj::DbgPrint<ushort,ulong,ulong,ulong,_GUID,_GUID,ushort const *>(ushort const *,ulong const &,ulong const &,ulong const &,_GUID const &,_GUID const &,ushort const * const &)
0x140168812  mov     rdx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140168819  lea     r9, aInco; "INCO"
0x140168820  mov     r10d, 2
0x140168826  test    rdi, rdi
0x140168829  jnz     loc_140168C22
0x14016882f  cmp     dword ptr [rbx+0DCh], 5
0x140168836  jnz     loc_140168C13
0x14016883c  cmp     [rbx+58h], r12
0x140168840  jnz     loc_1401688F1
0x140168846  test    rdx, rdx
0x140168849  jz      short loc_1401688A4
0x14016884b  cmp     [rdx+40h], r12d
0x14016884f  jz      short loc_1401688A4
0x140168851  cmp     [rdx+38h], r10d
0x140168855  jl      short loc_1401688A4
0x140168857  mov     [rbp+0F0h+var_110], r15
0x14016885b  mov     [rbp+0F0h+var_108], 0BC3h
0x140168862  mov     [rbp+0F0h+var_104], r10d
0x140168866  mov     [rbp+0F0h+var_100], r9
0x14016886a  mov     rax, [rbx+20h]
0x14016886e  mov     rcx, [rax+0C8h]
0x140168875  add     rcx, 12h
0x140168879  mov     [rsp+1F0h+var_180], rcx
0x14016887e  lea     r8, [r13+0A8h]
0x140168885  lea     rax, [rsp+1F0h+var_180]
0x14016888a  mov     [rsp+1F0h+var_1D0], rax
0x14016888f  mov     r9, [rsp+1F0h+var_190]
0x140168894  lea     rdx, aFailedToProces_11; "Failed to process updates received with"...
0x14016889b  lea     rcx, [rbp+0F0h+var_110]
0x14016889f  call    ??$DbgPrint@GU_GUID@@U1@PEBG@dbgobj@@QEAA_KPEBGAEBU_GUID@@1AEBQEBG@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID,ushort const *>(ushort const *,_GUID const &,_GUID const &,ushort const * const &)
0x1401688a4  call    cs:__imp_GetCurrentThreadId
0x1401688ab  nop     dword ptr [rax+rax+00h]
0x1401688b0  mov     [rsp+1F0h+var_1B0], r12
0x1401688b5  mov     dword ptr [rsp+1F0h+var_1B8], eax
0x1401688b9  mov     dword ptr [rsp+1F0h+var_1C0], 0BC8h
0x1401688c1  lea     rax, aInconnectionRe_5; "InConnection::ReceiveUpdates"
0x1401688c8  mov     [rsp+1F0h+var_1C8], rax
0x1401688cd  lea     rax, aBaseFsRemotefs_1; "base\\fs\\remotefs\\frs\\src\\sync\\inc"...
0x1401688d4  mov     [rsp+1F0h+var_1D0], rax
0x1401688d9  mov     r9d, 3
0x1401688df  xor     r8d, r8d
0x1401688e2  mov     edx, 2347h
0x1401688e7  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401688ec  jmp     loc_140168E67
0x1401688f1  lea     r8, [rbx+50h]
0x1401688f5  mov     rcx, r8
0x1401688f8  call    ?back@?$list@VSessionInfo@@V?$allocator@VSessionInfo@@@std@@@std@@QEAAAEAVSessionInfo@@XZ; std::list<SessionInfo>::back(void)
0x1401688fd  cmp     [rax+40h], r12d
0x140168901  jnz     loc_140168998
0x140168907  test    rdx, rdx
0x14016890a  jz      short loc_140168976
0x14016890c  cmp     [rdx+40h], r12d
0x140168910  jz      short loc_140168976
0x140168912  cmp     [rdx+38h], r10d
0x140168916  jl      short loc_140168976
0x140168918  mov     [rbp+0F0h+var_150], r15
0x14016891c  mov     [rbp+0F0h+var_148], 0BCDh
0x140168923  mov     [rbp+0F0h+var_144], r10d
0x140168927  mov     [rbp+0F0h+var_140], r9
0x14016892b  mov     rax, [rbx+20h]
0x14016892f  mov     rcx, [rax+0C8h]
0x140168936  add     rcx, 12h
0x14016893a  mov     [rsp+1F0h+var_180], rcx
0x14016893f  mov     rcx, r8
0x140168942  call    ?back@?$list@VSessionInfo@@V?$allocator@VSessionInfo@@@std@@@std@@QEAAAEAVSessionInfo@@XZ; std::list<SessionInfo>::back(void)
0x140168947  lea     r8, [rax+3Ch]
0x14016894b  lea     r9, [r13+0A8h]
0x140168952  lea     rcx, [rsp+1F0h+var_180]
0x140168957  mov     [rsp+1F0h+var_1C8], rcx
0x14016895c  mov     rcx, [rsp+1F0h+var_190]
0x140168961  mov     [rsp+1F0h+var_1D0], rcx
0x140168966  lea     rdx, aFailedToProces_20; "Failed to process updates received with"...
0x14016896d  lea     rcx, [rbp+0F0h+var_150]
0x140168971  call    ??$DbgPrint@GKU_GUID@@U1@PEBG@dbgobj@@QEAA_KPEBGAEBKAEBU_GUID@@2AEBQEBG@Z; dbgobj::DbgPrint<ushort,ulong,_GUID,_GUID,ushort const *>(ushort const *,ulong const &,_GUID const &,_GUID const &,ushort const * const &)
0x140168976  call    cs:__imp_GetCurrentThreadId
0x14016897d  nop     dword ptr [rax+rax+00h]
0x140168982  mov     [rsp+1F0h+var_1B0], r12
0x140168987  mov     dword ptr [rsp+1F0h+var_1B8], eax
0x14016898b  mov     dword ptr [rsp+1F0h+var_1C0], 0BD4h
0x140168993  jmp     loc_1401688C1
0x140168998  lea     rdx, [rbp+0F0h+var_88]
0x14016899c  call    ?end@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@@std@@@3@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(void)
0x1401689a1  mov     rcx, rax
0x1401689a4  call    ??F?$_List_iterator@V?$_List_val@U?$_List_simple_types@VSessionInfo@@@std@@@std@@@std@@QEAAAEAV01@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<SessionInfo>>>::operator--(void)
0x1401689a9  mov     rdi, [rax]
0x1401689ac  mov     [rbp+0F0h+var_160], rdi
0x1401689b0  lea     rax, [rbx+30h]
0x1401689b4  mov     [rbp+0F0h+var_168], rax
0x1401689b8  mov     ecx, [rbp+0F0h+arg_20]
0x1401689be  cmp     [rax], r12
0x1401689c1  jnz     short loc_140168A22
0x1401689c3  test    ecx, ecx
0x1401689c5  jz      short loc_140168A22
0x1401689c7  mov     ecx, 40h ; '@'; Size
0x1401689cc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1401689d1  mov     r15, rax
0x1401689d4  mov     [rbp+0F0h+var_138], rax
0x1401689d8  lea     rsi, [rbx+20h]
0x1401689dc  lea     rcx, ?UpdateWorkerThreadCount@Settings@@3VCUpdateWorkerThreadCount@1@A; Settings::CUpdateWorkerThreadCount Settings::UpdateWorkerThreadCount
0x1401689e3  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x1401689e8  lea     rcx, [r13+4F0h]
0x1401689ef  mov     [rsp+1F0h+var_1C8], rsi
0x1401689f4  mov     [rsp+1F0h+var_1D0], rcx
0x1401689f9  lea     r9, [rbx+28h]
0x1401689fd  mov     r8, r13
0x140168a00  mov     edx, eax
0x140168a02  mov     rcx, r15
0x140168a05  call    ??0UpdateManager@@QEAA@HPEAVInConnection@@AEAV?$ScopedRef@VVolumeManager@@@@AEAV?$ScopedRef@VReplicaSetManager@@@@AEAV?$ScopedRef@VContentSetManager@@@@@Z; UpdateManager::UpdateManager(int,InConnection *,ScopedRef<VolumeManager> &,ScopedRef<ReplicaSetManager> &,ScopedRef<ContentSetManager> &)
0x140168a0a  nop
0x140168a0b  mov     rcx, [rbp+0F0h+var_168]
0x140168a0f  mov     [rcx], rax
0x140168a12  mov     ecx, [rbp+0F0h+arg_20]
0x140168a18  mov     esi, dword ptr [rbp+0F0h+var_158]
0x140168a1b  lea     r15, aInconnectionRe_9; "InConnection::ReceiveUpdates"
0x140168a22  mov     r14d, r12d
0x140168a25  test    ecx, ecx
0x140168a27  jz      loc_140168BC5
0x140168a2d  lea     rcx, [rbp+0F0h+var_160]
0x140168a31  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@UCONTENT_SET_RECORD@@@std@@@std@@@std@@QEBAPEAUCONTENT_SET_RECORD@@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<CONTENT_SET_RECORD>>>::operator->(void)
0x140168a36  mov     rsi, rax
0x140168a39  lock inc dword ptr [rsi+34h]
0x140168a3d  mov     rbx, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x140168a44  lea     rcx, [rbx+258h]; lpCriticalSection
0x140168a4b  call    cs:__imp_EnterCriticalSection
0x140168a52  nop     dword ptr [rax+rax+00h]
0x140168a57  mov     dword ptr [rbx+250h], 1
0x140168a61  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140168a68  test    rax, rax
0x140168a6b  jz      short loc_140168AA8
0x140168a6d  cmp     [rax+40h], r12d
0x140168a71  jz      short loc_140168AA8
0x140168a73  lea     rdi, aInco; "INCO"
0x140168a7a  cmp     dword ptr [rax+38h], 5
0x140168a7e  jl      short loc_140168AAF
0x140168a80  mov     [rbp+0F0h+var_F8], r15
0x140168a84  mov     [rbp+0F0h+var_F0], 0BF4h
0x140168a8b  mov     [rbp+0F0h+var_EC], 5
0x140168a92  mov     [rbp+0F0h+var_E8], rdi
0x140168a96  lea     rdx, aUpdateSyncinfo; "Update syncInfoHistory"
0x140168a9d  lea     rcx, [rbp+0F0h+var_F8]
0x140168aa1  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140168aa6  jmp     short loc_140168AAF
0x140168aa8  lea     rdi, aInco; "INCO"
0x140168aaf  inc     dword ptr [r13+2D4h]
0x140168ab6  mov     rcx, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x140168abd  add     rcx, 218h; this
0x140168ac4  lea     rdx, [r13+218h]; struct HistoryRecord *
0x140168acb  call    ?Update@StateHistory@@MEAAXPEAVHistoryRecord@@@Z; StateHistory::Update(HistoryRecord *)
0x140168ad0  mov     rcx, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x140168ad7  mov     [rcx+250h], r12d
0x140168ade  add     rcx, 258h; lpCriticalSection
0x140168ae5  call    cs:__imp_LeaveCriticalSection
0x140168aec  nop     dword ptr [rax+rax+00h]
0x140168af1  mov     rbx, [rsp+1F0h+var_188]
0x140168af6  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140168afd  test    rax, rax
0x140168b00  jz      loc_140168B8B
0x140168b06  cmp     [rax+40h], r12d
0x140168b0a  jz      short loc_140168B8B
0x140168b0c  cmp     dword ptr [rax+38h], 4
0x140168b10  jl      short loc_140168B8B
0x140168b12  mov     [rbp+0F0h+var_E0], r15
0x140168b16  mov     [rbp+0F0h+var_D8], 0BF9h
0x140168b1d  mov     [rbp+0F0h+var_D4], 4
0x140168b24  mov     [rbp+0F0h+var_D0], rdi
0x140168b28  mov     rax, [rbx+20h]
0x140168b2c  mov     rcx, [rax+0C8h]
0x140168b33  add     rcx, 12h
0x140168b37  mov     [rbp+0F0h+var_158], rcx
0x140168b3b  lea     rdx, [rsi+3Ch]
0x140168b3f  mov     eax, r14d
0x140168b42  imul    r8, rax, 2A8h
0x140168b49  add     r8, [rsp+1F0h+var_180]
0x140168b4e  lea     rax, [r13+0A8h]
0x140168b55  lea     rcx, [r8+9Ch]
0x140168b5c  lea     r9, [r8+18h]
0x140168b60  lea     r10, [rbp+0F0h+var_158]
0x140168b64  mov     [rsp+1F0h+var_1B0], r10
0x140168b69  mov     r10, [rsp+1F0h+var_190]
0x140168b6e  mov     [rsp+1F0h+var_1B8], r10
0x140168b73  mov     [rsp+1F0h+var_1C0], rax
0x140168b78  mov     [rsp+1F0h+var_1C8], rdx
0x140168b7d  mov     [rsp+1F0h+var_1D0], rcx
0x140168b82  lea     rcx, [rbp+0F0h+var_E0]
0x140168b86  call    ??$DbgPrint@GVUID@@VGVSN@@$$BY0BAF@GKU_GUID@@U3@PEBG@dbgobj@@QEAA_KPEBGAEBVUID@@AEBVGVSN@@AEAY0BAF@$$CBGAEBKAEBU_GUID@@5AEBQEBG@Z; dbgobj::DbgPrint<ushort,UID,GVSN,ushort [261],ulong,_GUID,_GUID,ushort const *>(ushort const *,UID const &,GVSN const &,ushort const (&)[261],ulong const &,_GUID const &,_GUID const &,ushort const * const &)
0x140168b8b  mov     eax, r14d
0x140168b8e  imul    rdx, rax, 2A8h
0x140168b95  add     rdx, [rsp+1F0h+var_180]
0x140168b9a  xor     r9d, r9d
0x140168b9d  mov     rdi, [rbp+0F0h+var_160]
0x140168ba1  mov     r8, rdi
0x140168ba4  mov     rax, [rbp+0F0h+var_168]
0x140168ba8  mov     rcx, [rax]; struct UpdateManager *
0x140168bab  call    ?ProduceUpdate@UpdateManager@@QEAAXAEBVID_UPDATE@@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@VSessionInfo@@@std@@@std@@@std@@W4SYNC_TYPE@@@Z; UpdateManager::ProduceUpdate(ID_UPDATE const &,std::_List_iterator<std::_List_val<std::_List_simple_types<SessionInfo>>>,SYNC_TYPE)
0x140168bb0  inc     r14d
0x140168bb3  mov     ecx, [rbp+0F0h+arg_20]
  ... truncated ...
```
