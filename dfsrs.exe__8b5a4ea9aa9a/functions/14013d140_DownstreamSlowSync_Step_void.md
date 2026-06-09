# DownstreamSlowSync::Step(void)

- ea: `0x14013d140`
- end: `0x14013ddf1`
- name: `?Step@DownstreamSlowSync@@UEAA?AW4STEP_RESULT@Task@@XZ`
- size: `3249`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callees

- `0x14000cdc0`
- `0x14000d980`
- `0x14000dcc0`
- `0x14000e34c`
- `0x14002c2f4`
- `0x1400370bc`
- `0x1400391c4`
- `0x14007b760`
- `0x140086dcc`
- `0x1400923f8`
- `0x140110f94`
- `0x140111380`
- `0x1401345ec`
- `0x14013930c`
- `0x140139498`
- `0x14013ab90`
- `0x14013afe0`
- `0x14013c290`
- `0x14013c40c`
- `0x14013d140`
- `0x14013e770`
- `0x14016ca28`
- `0x1401b9340`
- `0x1401b9494`
- `0x1401bda10`
- `0x140223010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14013d214`
- `KERNEL32!LeaveCriticalSection` at `0x14013d714`
- `KERNEL32!LeaveCriticalSection` at `0x14013d8ce`
- `KERNEL32!LeaveCriticalSection` at `0x14013d214`
- `KERNEL32!LeaveCriticalSection` at `0x14013d714`
- `KERNEL32!LeaveCriticalSection` at `0x14013d8ce`
- `KERNEL32!EnterCriticalSection` at `0x14013d233`
- `KERNEL32!EnterCriticalSection` at `0x14013d762`
- `KERNEL32!EnterCriticalSection` at `0x14013d904`
- `KERNEL32!EnterCriticalSection` at `0x14013d233`
- `KERNEL32!EnterCriticalSection` at `0x14013d762`
- `KERNEL32!EnterCriticalSection` at `0x14013d904`
- `KERNEL32!GetCurrentThreadId` at `0x14013d512`
- `KERNEL32!GetCurrentThreadId` at `0x14013d524`
- `KERNEL32!GetCurrentThreadId` at `0x14013d832`
- `KERNEL32!GetCurrentThreadId` at `0x14013d844`
- `KERNEL32!GetCurrentThreadId` at `0x14013db48`
- `KERNEL32!GetCurrentThreadId` at `0x14013d512`
- `KERNEL32!GetCurrentThreadId` at `0x14013d524`
- `KERNEL32!GetCurrentThreadId` at `0x14013d832`
- `KERNEL32!GetCurrentThreadId` at `0x14013d844`
- `KERNEL32!GetCurrentThreadId` at `0x14013db48`

## string_xrefs

- `0x14013d8af`: `BLOCK. Normal sync is going on. Request VvUp later. connId:%? csId:%?`
- `0x14013dc65`: `Retrieved version vector. connId:%? csId:%?`
- `0x14013d981`: `Upstream version vector retrieved from context. connId:%? csId:%?`
- `0x14013da91`: `BLOCK. No credit available. connId:%? csId:%?`
- `0x14013d9f6`: `Upstream version vector requested from upstream. connId:%? csId:%?`
- `0x14013d5b3`: `BLOCK. Normal sync is going on. Request records later. connId:%? csId:%?`
- `0x14013d7cd`: `Records requested from upstream. connId:%? csId:%?`
- `0x14013d6ce`: `BLOCK. No credit is available. Request records later. connId:%? csId:%?`
- `0x14013d43d`: `No mismatches found. Request more records. connId:%? csId:%?`
- `0x14013d37f`: `Find next mismatch. connId:%? csId:%?`
- `0x14013d328`: `SlowSync task has failed two many times: %d Abort. connId:%? csId:%?`
- `0x14013d4a6`: `No mismatches found. Finished. connId:%? csId:%?`
- `0x14013dcda`: `The content set is either removed or disabled on upstream. connId:%? csId:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DownstreamSlowSync::Step(__int64 a1)
{
  unsigned int v2; // ebx
  struct FrsStatus *NextMismatch; // rdi
  int *v4; // r14
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ebx
  int v13; // eax
  LPCRITICAL_SECTION v14; // r8
  unsigned int v15; // r9d
  unsigned int PreviousErrorCode; // eax
  unsigned int v17; // edx
  _ID_GVSN *v18; // rcx
  int v19; // eax
  DWORD v20; // eax
  __int64 v21; // rcx
  __int64 v22; // r9
  struct FrsStatus *v23; // rax
  __int64 v24; // rax
  __int64 v25; // r15
  _DWORD *v26; // r12
  InConnection **v27; // r13
  int v28; // ebx
  int v29; // eax
  DWORD CurrentThreadId; // eax
  __int64 v31; // rcx
  __int64 v32; // r9
  __int64 v33; // rax
  int v34; // ebx
  int v35; // eax
  __int64 v36; // rbx
  __int64 (__fastcall *v37)(__int64, struct DbManager **, _QWORD); // rdi
  DWORD v38; // eax
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp-69h] BYREF
  int v41; // [rsp+58h] [rbp-61h]
  const wchar_t *v42; // [rsp+60h] [rbp-59h] BYREF
  int v43; // [rsp+68h] [rbp-51h]
  int v44; // [rsp+6Ch] [rbp-4Dh]
  const wchar_t *v45; // [rsp+70h] [rbp-49h]
  struct DbManager *v46[2]; // [rsp+78h] [rbp-41h] BYREF
  const wchar_t *v47; // [rsp+88h] [rbp-31h]
  const wchar_t *v48; // [rsp+90h] [rbp-29h] BYREF
  int v49; // [rsp+98h] [rbp-21h]
  int v50; // [rsp+9Ch] [rbp-1Dh]
  const wchar_t *v51; // [rsp+A0h] [rbp-19h]
  const wchar_t *v52; // [rsp+A8h] [rbp-11h] BYREF
  int v53; // [rsp+B0h] [rbp-9h]
  int v54; // [rsp+B4h] [rbp-5h]
  const wchar_t *v55; // [rsp+B8h] [rbp-1h]
  const wchar_t *v56; // [rsp+C0h] [rbp+7h] BYREF
  int v57; // [rsp+C8h] [rbp+Fh]
  int v58; // [rsp+CCh] [rbp+13h]
  const wchar_t *v59; // [rsp+D0h] [rbp+17h]
  __int64 v60; // [rsp+120h] [rbp+67h] BYREF
  __int64 v61; // [rsp+128h] [rbp+6Fh] BYREF
  struct FrsStatus *v62; // [rsp+130h] [rbp+77h] BYREF

  v2 = 0;
  NextMismatch = 0;
  v62 = 0;
  ScopedLock::ScopedLock((ScopedLock *)&lpCriticalSection, (struct ScopedCS *)(a1 + 240));
  DownstreamSlowSync::ReturnCredit((DownstreamSlowSync *)(a1 - 8));
  *(_DWORD *)(a1 + 300) = 0;
  v4 = (int *)(a1 + 296);
  v5 = *(_DWORD *)(a1 + 296);
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( !v7 )
      {
        v29 = *(_DWORD *)(a1 + 340);
        if ( v29 )
        {
          *v4 = 1;
          *(_DWORD *)(a1 + 300) = 3;
          v2 = 1;
          if ( (unsigned int)(v29 - 9001) > 0x25D )
          {
            CurrentThreadId = GetCurrentThreadId();
            v32 = 1;
          }
          else
          {
            CurrentThreadId = GetCurrentThreadId();
            v32 = 3;
          }
          v23 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                      v31,
                                      *(unsigned int *)(a1 + 340),
                                      0,
                                      v32,
                                      "base\\fs\\remotefs\\frs\\src\\sync\\slowsync.cpp",
                                      "DownstreamSlowSync::Step",
                                      897,
                                      CurrentThreadId,
                                      0);
          goto LABEL_56;
        }
LABEL_147:
        v14 = g_DebugLog;
        goto LABEL_148;
      }
      v8 = v7 - 1;
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( v9 )
        {
          v10 = v9 - 1;
          if ( v10 )
          {
            v11 = v10 - 1;
            if ( v11 )
            {
              if ( v11 == 1 )
                v2 = 2;
              goto LABEL_147;
            }
            v12 = --v41;
            LeaveCriticalSection(lpCriticalSection);
            NextMismatch = DownstreamSlowSync::SubmitUpdate((DownstreamSlowSync *)(a1 - 8));
            v62 = NextMismatch;
            EnterCriticalSection(lpCriticalSection);
            v41 = v12 + 1;
            if ( NextMismatch )
            {
              *(_DWORD *)(a1 + 300) = 4;
              v2 = 1;
              v13 = 6;
            }
            else
            {
              v2 = 0;
              v13 = 5;
            }
            *v4 = v13;
            goto LABEL_15;
          }
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            v48 = L"DownstreamSlowSync::Step";
            v49 = 975;
            v50 = 4;
            v51 = L"SSYN";
            dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
              &v48,
              L"Find next mismatch. connId:%? csId:%?",
              *(_QWORD *)(a1 + 192) + 168LL,
              *(_QWORD *)(a1 + 184) + 168LL);
          }
          LODWORD(v60) = 0;
          NextMismatch = DownstreamSlowSync::FindNextMismatch((DownstreamSlowSync *)(a1 - 8), (int *)&v60);
          v62 = NextMismatch;
          if ( NextMismatch )
          {
            *v4 = 3;
            *(_DWORD *)(a1 + 300) = 4;
            v2 = 1;
            goto LABEL_15;
          }
          if ( (_DWORD)v60 )
          {
            *v4 = 6;
            v2 = 0;
LABEL_15:
            v14 = g_DebugLog;
            goto LABEL_16;
          }
          v18 = *(_ID_GVSN **)(a1 + 328);
          if ( v18 )
            _ID_GVSN::`vector deleting destructor'(v18, v17);
          *(_QWORD *)(a1 + 328) = 0;
          *(_QWORD *)(a1 + 316) = 0;
          v14 = g_DebugLog;
          if ( *(_DWORD *)(a1 + 336) == 1 )
          {
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
            {
              v48 = L"DownstreamSlowSync::Step";
              v49 = 997;
              v50 = 4;
              v51 = L"SSYN";
              dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
                &v48,
                L"No mismatches found. Request more records. connId:%? csId:%?",
                *(_QWORD *)(a1 + 192) + 168LL,
                *(_QWORD *)(a1 + 184) + 168LL);
              v14 = g_DebugLog;
            }
            *v4 = 3;
LABEL_43:
            v2 = 0;
            goto LABEL_16;
          }
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            v46[0] = (struct DbManager *)L"DownstreamSlowSync::Step";
            v46[1] = (struct DbManager *)0x4000003EFLL;
            v47 = L"SSYN";
            dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
              v46,
              L"No mismatches found. Finished. connId:%? csId:%?",
              *(_QWORD *)(a1 + 192) + 168LL,
              *(_QWORD *)(a1 + 184) + 168LL);
            v14 = g_DebugLog;
          }
          *v4 = 7;
LABEL_49:
          v2 = 2;
          goto LABEL_16;
        }
        v19 = *(_DWORD *)(a1 + 340);
        if ( v19 )
        {
          *v4 = 3;
          *(_DWORD *)(a1 + 300) = 3;
          v2 = 1;
          if ( (unsigned int)(v19 - 9001) > 0x25D )
          {
            v20 = GetCurrentThreadId();
            v22 = 1;
          }
          else
          {
            v20 = GetCurrentThreadId();
            v22 = 3;
          }
          v23 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                      v21,
                                      *(unsigned int *)(a1 + 340),
                                      0,
                                      v22,
                                      "base\\fs\\remotefs\\frs\\src\\sync\\slowsync.cpp",
                                      "DownstreamSlowSync::Step",
                                      970,
                                      v20,
                                      0);
LABEL_56:
          NextMismatch = v23;
          v62 = v23;
          goto LABEL_15;
        }
        goto LABEL_147;
      }
      v24 = *(_QWORD *)(a1 + 192);
      if ( *(_DWORD *)(v24 + 1184) )
      {
        v14 = g_DebugLog;
        if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 5 )
          goto LABEL_63;
        v46[0] = (struct DbManager *)L"DownstreamSlowSync::Step";
        v46[1] = (struct DbManager *)0x500000387LL;
        v47 = L"SSYN";
        dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
          v46,
          L"BLOCK. Normal sync is going on. Request records later. connId:%? csId:%?",
          v24 + 168,
          *(_QWORD *)(a1 + 184) + 168LL);
LABEL_62:
        v14 = g_DebugLog;
LABEL_63:
        *(_DWORD *)(a1 + 300) = 1;
        v2 = 1;
        goto LABEL_148;
      }
      if ( *(_DWORD *)(a1 + 304) )
      {
        v25 = a1 + 184;
        v26 = (_DWORD *)(a1 + 296);
        v27 = (InConnection **)(a1 + 192);
      }
      else
      {
        v60 = 0;
        v25 = a1 + 184;
        NextMismatch = (struct FrsStatus *)ContentSetManager::GetReplicaSetManager(
                                             *(_QWORD *)(a1 + 184),
                                             &v60,
                                             3,
                                             L"DownstreamSlowSync::Step");
        v62 = NextMismatch;
        if ( !NextMismatch )
          *(_DWORD *)(a1 + 304) = CreditManager::GetCredits(
                                    *(CreditManager **)(v60 + 56),
                                    (struct CreditManager::ICallback *)(a1 - 8),
                                    0);
        ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v60);
        v26 = (_DWORD *)(a1 + 296);
        v27 = (InConnection **)(a1 + 192);
        v4 = (int *)(a1 + 296);
        if ( NextMismatch )
          goto LABEL_77;
      }
      if ( !*(_DWORD *)(a1 + 304) )
      {
        v14 = g_DebugLog;
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v48 = L"DownstreamSlowSync::Step";
          v49 = 924;
          v50 = 5;
          v51 = L"SSYN";
          dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
            &v48,
            L"BLOCK. No credit is available. Request records later. connId:%? csId:%?",
            *(_QWORD *)(a1 + 192) + 168LL,
            *(_QWORD *)(a1 + 184) + 168LL);
          v14 = g_DebugLog;
        }
        *(_DWORD *)(a1 + 300) = 2;
LABEL_76:
        v2 = 1;
        goto LABEL_16;
      }
LABEL_77:
      *v4 = 4;
      v28 = --v41;
      LeaveCriticalSection(lpCriticalSection);
      *(_DWORD *)(a1 + 340) = 0;
      if ( !NextMismatch )
      {
        NextMismatch = InConnection::TransportRequestRecords(
                         *v27,
                         (const struct _GUID *)(*(_QWORD *)v25 + 168LL),
                         (const struct UID *)(a1 + 352),
                         *(_DWORD *)(a1 + 176));
        v62 = NextMismatch;
      }
      EnterCriticalSection(lpCriticalSection);
      v41 = v28 + 1;
      v14 = g_DebugLog;
      if ( !NextMismatch )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v42 = L"DownstreamSlowSync::Step";
          v43 = 948;
          v44 = 4;
          v45 = L"SSYN";
          dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
            &v42,
            L"Records requested from upstream. connId:%? csId:%?",
            *(_QWORD *)(a1 + 192) + 168LL,
            *(_QWORD *)(a1 + 184) + 168LL);
          v14 = g_DebugLog;
        }
        v2 = 2;
        goto LABEL_148;
      }
      *v26 = 3;
      *(_DWORD *)(a1 + 300) = 3;
      goto LABEL_76;
    }
    v33 = *(_QWORD *)(a1 + 192);
    if ( *(_DWORD *)(v33 + 1184) )
    {
      v14 = g_DebugLog;
      if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 5 )
        goto LABEL_63;
      v42 = L"DownstreamSlowSync::Step";
      v43 = 841;
      v44 = 5;
      v45 = L"SSYN";
      dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
        &v42,
        L"BLOCK. Normal sync is going on. Request VvUp later. connId:%? csId:%?",
        v33 + 168,
        *(_QWORD *)(a1 + 184) + 168LL);
      goto LABEL_62;
    }
    *v4 = 2;
    v34 = --v41;
    LeaveCriticalSection(lpCriticalSection);
    LODWORD(v60) = 0;
    LODWORD(v61) = 0;
    *(_DWORD *)(a1 + 340) = 0;
    NextMismatch = DownstreamSlowSync::RequestVvUp((DownstreamSlowSync *)(a1 - 8), (int *)&v60, (int *)&v61);
    v62 = NextMismatch;
    EnterCriticalSection(lpCriticalSection);
    v41 = v34 + 1;
    v35 = v60;
    if ( !NextMismatch && !(_DWORD)v60 )
    {
      v14 = g_DebugLog;
      if ( (_DWORD)v61 )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v46[0] = (struct DbManager *)L"DownstreamSlowSync::Step";
          v46[1] = (struct DbManager *)0x400000368LL;
          v47 = L"SSYN";
          dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
            v46,
            L"Upstream version vector retrieved from context. connId:%? csId:%?",
            *(_QWORD *)(a1 + 192) + 168LL,
            *(_QWORD *)(a1 + 184) + 168LL);
          v14 = g_DebugLog;
        }
        *(_DWORD *)(a1 + 296) = 3;
        goto LABEL_43;
      }
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v48 = L"DownstreamSlowSync::Step";
        v49 = 880;
        v50 = 4;
        v51 = L"SSYN";
        dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
          &v48,
          L"Upstream version vector requested from upstream. connId:%? csId:%?",
          *(_QWORD *)(a1 + 192) + 168LL,
          *(_QWORD *)(a1 + 184) + 168LL);
        v14 = g_DebugLog;
      }
      goto LABEL_49;
    }
    *v4 = 1;
    *(_DWORD *)(a1 + 300) = 3 - (v35 != 0);
    v2 = 1;
    v14 = g_DebugLog;
    if ( !NextMismatch
      && g_DebugLog
      && LODWORD(g_DebugLog[1].LockSemaphore)
      && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v46[0] = (struct DbManager *)L"DownstreamSlowSync::Step";
      v46[1] = (struct DbManager *)0x500000361LL;
      v47 = L"SSYN";
      dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
        v46,
        L"BLOCK. No credit available. connId:%? csId:%?",
        *(_QWORD *)(a1 + 192) + 168LL,
        *(_QWORD *)(a1 + 184) + 168LL);
      v14 = g_DebugLog;
    }
  }
  else
  {
    *(_OWORD *)v46 = 0;
    v60 = 0;
    NextMismatch = (struct FrsStatus *)ContentSetManager::GetVolumeManager(*(_QWORD *)(a1 + 184), &v60, 3);
    v62 = NextMismatch;
    v36 = v60;
    if ( !NextMismatch )
    {
      if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugVolumeManagerRefCount)
        && g_DebugLog
        && LODWORD(g_DebugLog[1].LockSemaphore)
        && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        v42 = L"DownstreamSlowSync::Step";
        v43 = 808;
        v44 = 5;
        v45 = L"SSYN";
        v61 = v36;
        dbgobj::DbgPrint<unsigned short,unsigned __int64>(
          &v42,
          L"[VMREF] Added reference to volume manager. ptr:%p",
          &v61);
      }
      v37 = *(__int64 (__fastcall **)(__int64, struct DbManager **, _QWORD))(*(_QWORD *)v36 + 32LL);
      v38 = GetCurrentThreadId();
      NextMismatch = (struct FrsStatus *)v37(v36, v46, v38);
      v62 = NextMismatch;
    }
    if ( v36 )
    {
      if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugVolumeManagerRefCount)
        && g_DebugLog
        && LODWORD(g_DebugLog[1].LockSemaphore)
        && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        v42 = L"DownstreamSlowSync::Step";
        v43 = 812;
        v44 = 5;
        v45 = L"SSYN";
        v61 = v36;
        dbgobj::DbgPrint<unsigned short,unsigned __int64>(
          &v42,
          L"[VMREF] Release reference to volume manager. ptr:%p",
          &v61);
      }
      ScopedRef<VolumeManager::ShutdownRestartTask>::Set(&v60, 0);
    }
    ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v60);
    if ( NextMismatch
      || (NextMismatch = DbUtil::VersionVector(
                           v46[0],
                           (const struct _GUID *)(*(_QWORD *)(a1 + 184) + 168LL),
                           (struct VersionChainVector *)(a1 + 216)),
          (v62 = NextMismatch) != 0) )
    {
      v2 = 1;
    }
    else
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v42 = L"DownstreamSlowSync::Step";
        v43 = 824;
        v44 = 4;
        v45 = L"SSYN";
        dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
          &v42,
          L"Retrieved version vector. connId:%? csId:%?",
          *(_QWORD *)(a1 + 192) + 168LL,
          *(_QWORD *)(a1 + 184) + 168LL);
      }
      *(_DWORD *)(a1 + 296) = 1;
      v2 = 0;
    }
    DbManagerInstance::FinalizeDbManagerInstance((DbManagerInstance *)v46);
    v14 = g_DebugLog;
  }
LABEL_16:
  if ( NextMismatch )
  {
    v15 = *(_DWORD *)(a1 + 344) + 1;
    *(_DWORD *)(a1 + 344) = v15;
    PreviousErrorCode = *((_DWORD *)NextMismatch + 1);
    if ( PreviousErrorCode == 9027 )
      PreviousErrorCode = FrsStatus::GetPreviousErrorCode(NextMismatch);
    if ( PreviousErrorCode != 9028 && PreviousErrorCode != 9052 && PreviousErrorCode != 9470 && v15 < 0x80 )
      goto LABEL_142;
    if ( v15 < 0x80 )
    {
      if ( !v14 || !LODWORD(v14[1].LockSemaphore) || SLODWORD(v14[1].OwningThread) < 4 )
        goto LABEL_141;
      v52 = L"DownstreamSlowSync::Step";
      v53 = 1070;
      v54 = 4;
      v55 = L"SSYN";
      dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
        &v52,
        L"The content set is either removed or disabled on upstream. connId:%? csId:%?",
        *(_QWORD *)(a1 + 192) + 168LL,
        *(_QWORD *)(a1 + 184) + 168LL);
    }
    else
    {
      if ( !v14 || !LODWORD(v14[1].LockSemaphore) || SLODWORD(v14[1].OwningThread) < 3 )
        goto LABEL_141;
      v56 = L"DownstreamSlowSync::Step";
      v57 = 1061;
      v58 = 3;
      v59 = L"SSYN";
      dbgobj::DbgPrint<unsigned short,unsigned long,_GUID,_GUID>(
        (unsigned int)&v56,
        (unsigned int)L"SlowSync task has failed two many times: %d Abort. connId:%? csId:%?",
        a1 + 344,
        *(_QWORD *)(a1 + 192) + 168,
        *(_QWORD *)(a1 + 184) + 168LL);
    }
    v14 = g_DebugLog;
LABEL_141:
    *(_QWORD *)(a1 + 296) = 7;
    v2 = 2;
LABEL_142:
    if ( v14 && LODWORD(v14[1].LockSemaphore) && SLODWORD(v14[1].OwningThread) >= 2 )
    {
      v52 = L"DownstreamSlowSync::Step";
      v53 = 1081;
      v54 = 2;
      v55 = L"SSYN";
      dbgobj::DbgPrint<unsigned short,FrsStatus>(&v52, L"%?", NextMismatch);
    }
    CLEAR_ERROR(&v62);
    goto LABEL_147;
  }
LABEL_148:
  if ( v14 && LODWORD(v14[1].LockSemaphore) && SLODWORD(v14[1].OwningThread) >= 5 )
  {
    v52 = L"DownstreamSlowSync::Step";
    v53 = 1085;
    v54 = 5;
    v55 = L"SSYN";
    dbgobj::DbgPrint<unsigned short,char const *,unsigned short const *,_GUID,_GUID>(
      (unsigned int)&v52,
      *(_DWORD *)(a1 + 192) + 168,
      (unsigned int)&(&Task::stepResultText)[v2],
      (unsigned int)&(&DownstreamSlowSync::stateText)[*(_DWORD *)(a1 + 296)],
      *(_QWORD *)(a1 + 192) + 168LL,
      *(_QWORD *)(a1 + 184) + 168LL);
  }
  ScopedLock::~ScopedLock((ScopedLock *)&lpCriticalSection);
  return v2;
}

```

## disassembly

```asm
0x14013d140  mov     [rsp-8+arg_18], rbx
0x14013d145  push    rbp
0x14013d146  push    rsi
0x14013d147  push    rdi
0x14013d148  push    r12
0x14013d14a  push    r13
0x14013d14c  push    r14
0x14013d14e  push    r15
0x14013d150  lea     rbp, [rsp-27h]
0x14013d155  sub     rsp, 0E0h
0x14013d15c  mov     rsi, rcx
0x14013d15f  xor     r13d, r13d
0x14013d162  mov     ebx, r13d
0x14013d165  mov     edi, r13d
0x14013d168  mov     [rbp+57h+arg_10], r13
0x14013d16c  lea     rdx, [rcx+0F0h]; struct ScopedCS *
0x14013d173  lea     rcx, [rbp+57h+lpCriticalSection]; this
0x14013d177  call    ??0ScopedLock@@QEAA@AEAVScopedCS@@@Z; ScopedLock::ScopedLock(ScopedCS &)
0x14013d17c  nop
0x14013d17d  lea     r12, [rsi-8]
0x14013d181  mov     rcx, r12; this
0x14013d184  call    ?ReturnCredit@DownstreamSlowSync@@IEAAXXZ; DownstreamSlowSync::ReturnCredit(void)
0x14013d189  mov     [rsi+12Ch], r13d
0x14013d190  lea     r14, [rsi+128h]
0x14013d197  mov     ecx, [r14]
0x14013d19a  lea     edx, [r13+5]
0x14013d19e  lea     r9, aDownstreamslow_7; "DownstreamSlowSync::Step"
0x14013d1a5  lea     r10, aSsyn; "SSYN"
0x14013d1ac  mov     r15d, 0A8h
0x14013d1b2  lea     r11d, [r13+2]
0x14013d1b6  lea     r8d, [r13+3]
0x14013d1ba  test    ecx, ecx
0x14013d1bc  jz      loc_14013DAAD
0x14013d1c2  sub     ecx, 1
0x14013d1c5  jz      loc_14013D869
0x14013d1cb  sub     ecx, 1
0x14013d1ce  jz      loc_14013D805
0x14013d1d4  sub     ecx, 1
0x14013d1d7  jz      loc_14013D576
0x14013d1dd  sub     ecx, 1
0x14013d1e0  jz      loc_14013D4E9
0x14013d1e6  sub     ecx, 1
0x14013d1e9  jz      loc_14013D33D
0x14013d1ef  sub     ecx, 1
0x14013d1f2  jz      short loc_14013D208
0x14013d1f4  cmp     ecx, 1
0x14013d1f7  jnz     short loc_14013D1FC
0x14013d1f9  mov     ebx, r11d
0x14013d1fc  lea     r12, aDownstreamslow_7; "DownstreamSlowSync::Step"
0x14013d203  jmp     loc_14013DD45
0x14013d208  mov     ebx, [rbp+57h+var_B8]
0x14013d20b  dec     ebx
0x14013d20d  mov     [rbp+57h+var_B8], ebx
0x14013d210  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x14013d214  call    cs:__imp_LeaveCriticalSection
0x14013d21b  nop     dword ptr [rax+rax+00h]
0x14013d220  mov     rcx, r12; this
0x14013d223  call    ?SubmitUpdate@DownstreamSlowSync@@IEAAPEAVFrsStatus@@XZ; DownstreamSlowSync::SubmitUpdate(void)
0x14013d228  mov     rdi, rax
0x14013d22b  mov     [rbp+57h+arg_10], rax
0x14013d22f  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x14013d233  call    cs:__imp_EnterCriticalSection
0x14013d23a  nop     dword ptr [rax+rax+00h]
0x14013d23f  lea     eax, [rbx+1]
0x14013d242  mov     [rbp+57h+var_B8], eax
0x14013d245  test    rdi, rdi
0x14013d248  jnz     short loc_14013D252
0x14013d24a  mov     ebx, r13d
0x14013d24d  lea     eax, [rdi+5]
0x14013d250  jmp     short loc_14013D264
0x14013d252  mov     dword ptr [rsi+12Ch], 4
0x14013d25c  mov     ebx, 1
0x14013d261  lea     eax, [rbx+5]
0x14013d264  mov     [r14], eax
0x14013d267  mov     r8, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14013d26e  lea     r12, aDownstreamslow_7; "DownstreamSlowSync::Step"
0x14013d275  lea     r14, aSsyn; "SSYN"
0x14013d27c  test    rdi, rdi
0x14013d27f  jz      loc_14013DD4C
0x14013d285  mov     r9d, [rsi+158h]
0x14013d28c  inc     r9d
0x14013d28f  mov     [rsi+158h], r9d
0x14013d296  mov     eax, [rdi+4]
0x14013d299  cmp     eax, 2343h
0x14013d29e  jnz     short loc_14013D2A8
0x14013d2a0  mov     rcx, rdi; this
0x14013d2a3  call    ?GetPreviousErrorCode@FrsStatus@@QEBAKXZ; FrsStatus::GetPreviousErrorCode(void)
0x14013d2a8  mov     ecx, 80h
0x14013d2ad  cmp     eax, 2344h
0x14013d2b2  jz      short loc_14013D2CB
0x14013d2b4  cmp     eax, 235Ch
0x14013d2b9  jz      short loc_14013D2CB
0x14013d2bb  cmp     eax, 24FEh
0x14013d2c0  jz      short loc_14013D2CB
0x14013d2c2  cmp     r9d, ecx
0x14013d2c5  jb      loc_14013DD01
0x14013d2cb  cmp     r9d, ecx
0x14013d2ce  jb      loc_14013DC9E
0x14013d2d4  test    r8, r8
0x14013d2d7  jz      loc_14013DCF1
0x14013d2dd  cmp     [r8+40h], r13d
0x14013d2e1  jz      loc_14013DCF1
0x14013d2e7  cmp     dword ptr [r8+38h], 3
0x14013d2ec  jl      loc_14013DCF1
0x14013d2f2  mov     [rbp+57h+var_50], r12
0x14013d2f6  mov     [rbp+57h+var_48], 425h
0x14013d2fd  mov     [rbp+57h+var_44], 3
0x14013d304  mov     [rbp+57h+var_40], r14
0x14013d308  mov     rax, [rsi+0B8h]
0x14013d30f  add     rax, r15
0x14013d312  mov     r9, [rsi+0C0h]
0x14013d319  add     r9, r15
0x14013d31c  lea     r8, [rsi+158h]
0x14013d323  mov     [rsp+110h+var_F0], rax
0x14013d328  lea     rdx, aSlowsyncTaskHa; "SlowSync task has failed two many times"...
0x14013d32f  lea     rcx, [rbp+57h+var_50]
0x14013d333  call    ??$DbgPrint@GKU_GUID@@U1@@dbgobj@@QEAA_KPEBGAEBKAEBU_GUID@@2@Z; dbgobj::DbgPrint<ushort,ulong,_GUID,_GUID>(ushort const *,ulong const &,_GUID const &,_GUID const &)
0x14013d338  jmp     loc_14013DCEA
0x14013d33d  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14013d344  test    rax, rax
0x14013d347  jz      short loc_14013D38F
0x14013d349  cmp     [rax+40h], r13d
0x14013d34d  jz      short loc_14013D38F
0x14013d34f  cmp     dword ptr [rax+38h], 4
0x14013d353  jl      short loc_14013D38F
0x14013d355  mov     [rbp+57h+var_80], r9
0x14013d359  mov     [rbp+57h+var_78], 3CFh
0x14013d360  mov     [rbp+57h+var_74], 4
0x14013d367  mov     [rbp+57h+var_70], r10
0x14013d36b  mov     r9, [rsi+0B8h]
0x14013d372  add     r9, r15
0x14013d375  mov     r8, [rsi+0C0h]
0x14013d37c  add     r8, r15
0x14013d37f  lea     rdx, aFindNextMismat; "Find next mismatch. connId:%? csId:%?"
0x14013d386  lea     rcx, [rbp+57h+var_80]
0x14013d38a  call    ??$DbgPrint@GU_GUID@@U1@@dbgobj@@QEAA_KPEBGAEBU_GUID@@1@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID>(ushort const *,_GUID const &,_GUID const &)
0x14013d38f  mov     dword ptr [rbp+57h+arg_0], r13d
0x14013d393  lea     rdx, [rbp+57h+arg_0]; int *
0x14013d397  mov     rcx, r12; this
0x14013d39a  call    ?FindNextMismatch@DownstreamSlowSync@@IEAAPEAVFrsStatus@@AEAH@Z; DownstreamSlowSync::FindNextMismatch(int &)
0x14013d39f  mov     rdi, rax
0x14013d3a2  mov     [rbp+57h+arg_10], rax
0x14013d3a6  test    rax, rax
0x14013d3a9  jnz     loc_14013D4CE
0x14013d3af  cmp     dword ptr [rbp+57h+arg_0], r13d
0x14013d3b3  jz      short loc_14013D3C4
0x14013d3b5  mov     dword ptr [r14], 6
0x14013d3bc  mov     ebx, r13d
0x14013d3bf  jmp     loc_14013D267
0x14013d3c4  mov     rcx, [rsi+148h]; this
0x14013d3cb  test    rcx, rcx
0x14013d3ce  jz      short loc_14013D3D5
0x14013d3d0  call    ??_E_ID_GVSN@@QEAAPEAXI@Z; _ID_GVSN::`vector deleting destructor'(uint)
0x14013d3d5  mov     [rsi+148h], r13
0x14013d3dc  mov     [rsi+13Ch], r13
0x14013d3e3  mov     r8, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14013d3ea  lea     r12, aDownstreamslow_7; "DownstreamSlowSync::Step"
0x14013d3f1  cmp     dword ptr [rsi+150h], 1
0x14013d3f8  jnz     short loc_14013D463
0x14013d3fa  test    r8, r8
0x14013d3fd  jz      short loc_14013D454
0x14013d3ff  cmp     [r8+40h], r13d
0x14013d403  jz      short loc_14013D454
0x14013d405  cmp     dword ptr [r8+38h], 4
0x14013d40a  jl      short loc_14013D454
0x14013d40c  mov     [rbp+57h+var_80], r12
0x14013d410  mov     [rbp+57h+var_78], 3E5h
0x14013d417  mov     [rbp+57h+var_74], 4
0x14013d41e  lea     rax, aSsyn; "SSYN"
0x14013d425  mov     [rbp+57h+var_70], rax
0x14013d429  mov     r9, [rsi+0B8h]
0x14013d430  add     r9, r15
0x14013d433  mov     r8, [rsi+0C0h]
0x14013d43a  add     r8, r15
0x14013d43d  lea     rdx, aNoMismatchesFo_0; "No mismatches found. Request more recor"...
0x14013d444  lea     rcx, [rbp+57h+var_80]
0x14013d448  call    ??$DbgPrint@GU_GUID@@U1@@dbgobj@@QEAA_KPEBGAEBU_GUID@@1@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID>(ushort const *,_GUID const &,_GUID const &)
0x14013d44d  mov     r8, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14013d454  mov     dword ptr [r14], 3
0x14013d45b  mov     ebx, r13d
0x14013d45e  jmp     loc_14013D275
0x14013d463  test    r8, r8
0x14013d466  jz      short loc_14013D4BD
0x14013d468  cmp     [r8+40h], r13d
0x14013d46c  jz      short loc_14013D4BD
0x14013d46e  cmp     dword ptr [r8+38h], 4
0x14013d473  jl      short loc_14013D4BD
0x14013d475  mov     [rbp+57h+var_98], r12
0x14013d479  mov     dword ptr [rbp+57h+var_98+8], 3EFh
0x14013d480  mov     dword ptr [rbp+57h+var_98+0Ch], 4
0x14013d487  lea     rax, aSsyn; "SSYN"
0x14013d48e  mov     [rbp+57h+var_88], rax
0x14013d492  mov     r9, [rsi+0B8h]
0x14013d499  add     r9, r15
0x14013d49c  mov     r8, [rsi+0C0h]
0x14013d4a3  add     r8, r15
0x14013d4a6  lea     rdx, aNoMismatchesFo; "No mismatches found. Finished. connId:%"...
0x14013d4ad  lea     rcx, [rbp+57h+var_98]
0x14013d4b1  call    ??$DbgPrint@GU_GUID@@U1@@dbgobj@@QEAA_KPEBGAEBU_GUID@@1@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID>(ushort const *,_GUID const &,_GUID const &)
0x14013d4b6  mov     r8, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14013d4bd  mov     dword ptr [r14], 7
0x14013d4c4  mov     ebx, 2
0x14013d4c9  jmp     loc_14013D275
0x14013d4ce  mov     dword ptr [r14], 3
0x14013d4d5  mov     dword ptr [rsi+12Ch], 4
0x14013d4df  mov     ebx, 1
0x14013d4e4  jmp     loc_14013D267
0x14013d4e9  mov     eax, [rsi+154h]
0x14013d4ef  test    eax, eax
0x14013d4f1  jz      loc_14013D1FC
0x14013d4f7  mov     [r14], r8d
0x14013d4fa  mov     [rsi+12Ch], r8d
0x14013d501  mov     ebx, 1
0x14013d506  add     eax, 0FFFFDCD7h
0x14013d50b  cmp     eax, 25Dh
0x14013d510  ja      short loc_14013D524
0x14013d512  call    cs:__imp_GetCurrentThreadId
0x14013d519  nop     dword ptr [rax+rax+00h]
0x14013d51e  lea     r9d, [rbx+2]
0x14013d522  jmp     short loc_14013D533
0x14013d524  call    cs:__imp_GetCurrentThreadId
0x14013d52b  nop     dword ptr [rax+rax+00h]
0x14013d530  mov     r9d, ebx
0x14013d533  mov     [rsp+110h+var_D0], r13
0x14013d538  mov     [rsp+110h+var_D8], eax
0x14013d53c  mov     [rsp+110h+var_E0], 3CAh
0x14013d544  lea     rax, aDownstreamslow_6; "DownstreamSlowSync::Step"
0x14013d54b  mov     [rsp+110h+var_E8], rax
0x14013d550  lea     rax, aBaseFsRemotefs_94; "base\\fs\\remotefs\\frs\\src\\sync\\slo"...
0x14013d557  mov     [rsp+110h+var_F0], rax
0x14013d55c  xor     r8d, r8d
0x14013d55f  mov     edx, [rsi+154h]
0x14013d565  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14013d56a  mov     rdi, rax
0x14013d56d  mov     [rbp+57h+arg_10], rax
0x14013d571  jmp     loc_14013D267
0x14013d576  lea     rcx, [rsi+0C0h]
0x14013d57d  mov     rax, [rcx]
0x14013d580  cmp     [rax+4A0h], r13d
0x14013d587  jz      short loc_14013D5F6
0x14013d589  mov     r8, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14013d590  test    r8, r8
0x14013d593  jz      short loc_14013D5DB
0x14013d595  cmp     [r8+40h], r13d
0x14013d599  jz      short loc_14013D5DB
0x14013d59b  cmp     [r8+38h], edx
0x14013d59f  jl      short loc_14013D5DB
0x14013d5a1  mov     [rbp+57h+var_98], r9
0x14013d5a5  mov     dword ptr [rbp+57h+var_98+8], 387h
0x14013d5ac  mov     dword ptr [rbp+57h+var_98+0Ch], edx
0x14013d5af  mov     [rbp+57h+var_88], r10
0x14013d5b3  lea     rdx, aBlockNormalSyn; "BLOCK. Normal sync is going on. Request"...
0x14013d5ba  lea     rcx, [rbp+57h+var_98]
0x14013d5be  mov     r9, [rsi+0B8h]
0x14013d5c5  lea     r8, [rax+0A8h]
0x14013d5cc  add     r9, r15
0x14013d5cf  call    ??$DbgPrint@GU_GUID@@U1@@dbgobj@@QEAA_KPEBGAEBU_GUID@@1@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID>(ushort const *,_GUID const &,_GUID const &)
0x14013d5d4  mov     r8, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14013d5db  mov     dword ptr [rsi+12Ch], 1
0x14013d5e5  mov     ebx, 1
0x14013d5ea  lea     r12, aDownstreamslow_7; "DownstreamSlowSync::Step"
0x14013d5f1  jmp     loc_14013DD4C
0x14013d5f6  cmp     [rsi+130h], r13d
0x14013d5fd  jnz     short loc_14013D671
0x14013d5ff  mov     [rbp+57h+arg_0], r13
0x14013d603  lea     r15, [rsi+0B8h]
0x14013d60a  lea     rdx, [rbp+57h+arg_0]
0x14013d60e  mov     rcx, [r15]
0x14013d611  call    ?GetReplicaSetManager@ContentSetManager@@QEAAPEAVFrsStatus@@AEAV?$ScopedRef@VReplicaSetManager@@@@@Z; ContentSetManager::GetReplicaSetManager(ScopedRef<ReplicaSetManager> &)
0x14013d616  mov     rdi, rax
0x14013d619  mov     [rbp+57h+arg_10], rax
0x14013d61d  test    rax, rax
0x14013d620  jnz     short loc_14013D63B
0x14013d622  mov     rax, [rbp+57h+arg_0]
0x14013d626  xor     r8d, r8d; int
0x14013d629  mov     rdx, r12; struct CreditManager::ICallback *
0x14013d62c  mov     rcx, [rax+38h]; this
0x14013d630  call    ?GetCredits@CreditManager@@QEAAKPEAVICallback@1@H@Z; CreditManager::GetCredits(CreditManager::ICallback *,int)
0x14013d635  mov     [rsi+130h], eax
0x14013d63b  lea     rcx, [rbp+57h+arg_0]
0x14013d63f  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x14013d644  lea     r12, [rsi+128h]
0x14013d64b  lea     r13, [rsi+0C0h]
0x14013d652  mov     r14, r12
0x14013d655  test    rdi, rdi
0x14013d658  jnz     loc_14013D701
0x14013d65e  lea     edx, [rdi+5]
0x14013d661  lea     r9, aDownstreamslow_7; "DownstreamSlowSync::Step"
0x14013d668  lea     r10, aSsyn; "SSYN"
0x14013d66f  jmp     short loc_14013D67E
0x14013d671  lea     r15, [rsi+0B8h]
0x14013d678  mov     r12, r14
0x14013d67b  mov     r13, rcx
0x14013d67e  cmp     dword ptr [rsi+130h], 0
0x14013d685  jnz     short loc_14013D701
0x14013d687  mov     r8, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14013d68e  xor     r13d, r13d
0x14013d691  test    r8, r8
0x14013d694  jz      short loc_14013D6E7
0x14013d696  cmp     [r8+40h], r13d
  ... truncated ...
```
