# OutConnection::TransportEstablishSession(_GUID const &)

- ea: `0x140175880`
- end: `0x1401760c0`
- name: `?TransportEstablishSession@OutConnection@@QEAAPEAVFrsStatus@@AEBU_GUID@@@Z`
- size: `2112`
- prototype: `struct FrsStatus *__fastcall(OutConnection *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1401b09fc`

## callees

- `0x1400036a0`
- `0x1400036d0`
- `0x14000daa0`
- `0x14000e34c`
- `0x140024964`
- `0x140024c84`
- `0x14002c2f4`
- `0x1400370bc`
- `0x1400391c4`
- `0x140047e14`
- `0x14006b418`
- `0x1400727e8`
- `0x1400812c8`
- `0x140083594`
- `0x140111380`
- `0x140115e28`
- `0x140119388`
- `0x14011b650`
- `0x14012f8b0`
- `0x1401311b8`
- `0x14016fcd0`
- `0x140170c54`
- `0x140173f30`
- `0x140175880`
- `0x1401942d8`
- `0x1401b30b0`
- `0x1401b9494`
- `0x1401bda10`
- `0x1401bf590`
- `0x1401c9fec`
- `0x1401ca138`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140175958`
- `KERNEL32!GetCurrentThreadId` at `0x140175a27`
- `KERNEL32!GetCurrentThreadId` at `0x140175cc9`
- `KERNEL32!GetCurrentThreadId` at `0x140175d1a`
- `KERNEL32!GetCurrentThreadId` at `0x140175d6e`
- `KERNEL32!GetCurrentThreadId` at `0x140176034`
- `KERNEL32!GetCurrentThreadId` at `0x140175958`
- `KERNEL32!GetCurrentThreadId` at `0x140175a27`
- `KERNEL32!GetCurrentThreadId` at `0x140175cc9`
- `KERNEL32!GetCurrentThreadId` at `0x140175d1a`
- `KERNEL32!GetCurrentThreadId` at `0x140175d6e`
- `KERNEL32!GetCurrentThreadId` at `0x140176034`

## string_xrefs

- `0x1401759e9`: `Cannot establish session. This a read only content set. csId:%? connId:%? rgName:%?`
- `0x140175eba`: `(Ignored) Failed to restart inconnection session task. csId:%? connId:%? rgName:%? Error:%?`
- `0x140175ada`: `Replacing content set. csId:%? connId:%? rgName:%?`
- `0x140175e0d`: `Shutdown in progress. csId:%? connId:%? rgName:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
struct FrsStatus *__fastcall OutConnection::TransportEstablishSession(OutConnection *this, const struct _GUID *a2)
{
  __int64 v4; // r15
  unsigned int *VolumeManager; // r12
  OutConnectionContentSetContext *v6; // rdi
  ContentSetManager *v7; // rbx
  RefCountObject *v8; // rcx
  __int64 v9; // rdx
  DWORD v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rax
  DWORD v13; // eax
  __int64 v14; // rcx
  __int64 v15; // r8
  struct FrsStatus *v16; // r14
  __int64 v17; // rax
  struct ShutdownObject *v18; // rdx
  __int64 v19; // rsi
  struct ShutdownObject *v20; // rdx
  DWORD v21; // eax
  __int64 v22; // rcx
  DWORD v23; // eax
  __int64 v24; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v26; // rcx
  TimeoutCounter *v27; // rcx
  __int64 v28; // r8
  struct FrsStatus *v29; // rbx
  __int64 v30; // rax
  DWORD v31; // eax
  __int64 v32; // rcx
  struct FrsStatus *v34; // [rsp+50h] [rbp-49h] BYREF
  const wchar_t *v35; // [rsp+58h] [rbp-41h] BYREF
  int v36; // [rsp+60h] [rbp-39h]
  int v37; // [rsp+64h] [rbp-35h]
  const wchar_t *v38; // [rsp+68h] [rbp-31h]
  ContentSetManager *v39; // [rsp+70h] [rbp-29h] BYREF
  OutConnectionContentSetContext *v40; // [rsp+78h] [rbp-21h] BYREF
  struct FrsStatus *v41; // [rsp+80h] [rbp-19h] BYREF
  struct FrsStatus *v42; // [rsp+88h] [rbp-11h] BYREF
  __int64 v43; // [rsp+90h] [rbp-9h] BYREF
  RefCountObject *v44; // [rsp+98h] [rbp-1h] BYREF
  __int128 v45; // [rsp+A0h] [rbp+7h] BYREF

  *(_QWORD *)&v45 = a2;
  v4 = 0;
  VolumeManager = 0;
  v6 = 0;
  v40 = 0;
  v43 = 0;
  v7 = 0;
  v39 = 0;
  LODWORD(v42) = 0;
  ScopedCrewLock::ScopedCrewLock(&v41, (char *)this + 632);
  if ( (*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 7) + 48LL))((char *)this + 56) )
  {
    CurrentThreadId = GetCurrentThreadId();
    VolumeManager = (unsigned int *)FrsStatusList::PushNewError(
                                      v26,
                                      9032,
                                      0,
                                      3,
                                      "base\\fs\\remotefs\\frs\\src\\sync\\outconnection.cpp",
                                      "OutConnection::TransportEstablishSession",
                                      458,
                                      CurrentThreadId,
                                      0);
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v35 = L"OutConnection::TransportEstablishSession";
      v36 = 459;
      v37 = 4;
      v38 = L"OUTC";
      dbgobj::DbgPrint<unsigned short,_GUID,_GUID,FrsStringImpl<unsigned short,char>>(
        (unsigned int)&v35,
        (unsigned int)L"Shutdown in progress. csId:%? connId:%? rgName:%?",
        v45,
        (_DWORD)this + 32,
        *((_QWORD *)this + 21) + 72LL);
    }
  }
  else if ( (unsigned int)RefMap<_GUID,InConnection::InConnectionContentSetContext,std::less<_GUID>>::Find(
                            (char *)this + 184,
                            a2,
                            &v40) )
  {
    v6 = v40;
    v8 = (RefCountObject *)*((_QWORD *)v40 + 7);
    if ( v8 )
    {
      RefCountObject::AddRef(v8);
      v9 = *((_QWORD *)v6 + 7);
    }
    else
    {
      v9 = 0;
    }
    ScopedRef<VolumeManager::ShutdownRestartTask>::Set(&v39, v9);
    v7 = v39;
    if ( !(unsigned int)ContentSetManager::IsSubordinate(v39) )
      goto LABEL_12;
    v10 = GetCurrentThreadId();
    VolumeManager = (unsigned int *)FrsStatusList::PushNewError(
                                      v11,
                                      9077,
                                      0,
                                      3,
                                      "base\\fs\\remotefs\\frs\\src\\sync\\outconnection.cpp",
                                      "OutConnection::TransportEstablishSession",
                                      386,
                                      v10,
                                      0);
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v35 = L"OutConnection::TransportEstablishSession";
      v36 = 388;
      v37 = 4;
      v38 = L"OUTC";
      dbgobj::DbgPrint<unsigned short,_GUID,_GUID,FrsStringImpl<unsigned short,char>>(
        (unsigned int)&v35,
        (unsigned int)L"Cannot establish session. This a read only content set. csId:%? connId:%? rgName:%?",
        v45,
        (_DWORD)this + 32,
        *((_QWORD *)this + 21) + 72LL);
    }
    if ( !VolumeManager )
    {
LABEL_12:
      v12 = Config::ConfigInstance<Config::ContentSet>::Get((char *)v7 + 1120);
      v34 = (struct FrsStatus *)v12;
      if ( v12 && !(unsigned int)Config::BoolParam::Get((Config::BoolParam *)(v12 + 1120)) )
      {
        v13 = GetCurrentThreadId();
        VolumeManager = (unsigned int *)FrsStatusList::PushNewError(
                                          v14,
                                          9052,
                                          0,
                                          3,
                                          "base\\fs\\remotefs\\frs\\src\\sync\\outconnection.cpp",
                                          "OutConnection::TransportEstablishSession",
                                          407,
                                          v13,
                                          0);
      }
      ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v34);
      if ( !VolumeManager )
      {
        if ( *((_DWORD *)v7 + 148) )
        {
          v21 = GetCurrentThreadId();
          VolumeManager = (unsigned int *)FrsStatusList::PushNewError(
                                            v22,
                                            9051,
                                            0,
                                            3,
                                            "base\\fs\\remotefs\\frs\\src\\sync\\outconnection.cpp",
                                            "OutConnection::TransportEstablishSession",
                                            449,
                                            v21,
                                            0);
          v6 = v40;
          v7 = v39;
        }
        else
        {
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            v35 = L"OutConnection::TransportEstablishSession";
            v36 = 415;
            v37 = 4;
            v38 = L"OUTC";
            dbgobj::DbgPrint<unsigned short,_GUID,_GUID,FrsStringImpl<unsigned short,char>>(
              (unsigned int)&v35,
              (unsigned int)L"Replacing content set. csId:%? connId:%? rgName:%?",
              v45,
              (_DWORD)this + 32,
              *((_QWORD *)this + 21) + 72LL);
          }
          v34 = 0;
          v7 = v39;
          VolumeManager = (unsigned int *)ContentSetManager::GetVolumeManager(v39, &v34, v15);
          v6 = v40;
          v16 = v34;
          if ( !VolumeManager )
          {
            if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugVolumeManagerRefCount)
              && g_DebugLog
              && LODWORD(g_DebugLog[1].LockSemaphore)
              && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
            {
              v35 = L"OutConnection::TransportEstablishSession";
              v36 = 429;
              v37 = 5;
              v38 = L"OUTC";
              v42 = v16;
              dbgobj::DbgPrint<unsigned short,unsigned __int64>(
                &v35,
                L"[VMREF] Added reference to volume manager. ptr:%p",
                &v42);
            }
            v44 = (RefCountObject *)operator new(0x130u);
            Join::Join((_DWORD)v44, *((_QWORD *)v16 + 7), (_DWORD)this, (unsigned int)&v34, (__int64)&v39);
            v44 = (RefCountObject *)operator new(0xE8u);
            v17 = OutConnectionContentSetContext::OutConnectionContentSetContext(v44, (__int64)&v39);
            ScopedRef<VolumeManager::ShutdownRestartTask>::Set(&v43, v17);
            OutConnectionContentSetContext::PrepareShutdownOutConnectionContentSetContext(v6);
            v18 = (OutConnectionContentSetContext *)((char *)v6 + 32);
            if ( !v6 )
              v18 = 0;
            CompositeShutdownObject::UnRegisterShutdownObject((OutConnection *)((char *)this + 56), v18);
            RefMap<_GUID,ReplicaSetManager,std::less<_GUID>>::Delete((char *)this + 184, v45);
            v19 = v43;
            RefMap<_GUID,ReplicaSetManager,std::less<_GUID>>::Insert((char *)this + 184, v45, v43);
            v20 = (struct ShutdownObject *)(v19 + 32);
            if ( !v19 )
              v20 = 0;
            CompositeShutdownObject::RegisterShutdownObject((OutConnection *)((char *)this + 56), v20);
            LODWORD(v42) = 1;
          }
          if ( v16 )
          {
            if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugVolumeManagerRefCount)
              && g_DebugLog
              && LODWORD(g_DebugLog[1].LockSemaphore)
              && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
            {
              v35 = L"OutConnection::TransportEstablishSession";
              v36 = 446;
              v37 = 5;
              v38 = L"OUTC";
              v44 = v16;
              dbgobj::DbgPrint<unsigned short,unsigned __int64>(
                &v35,
                L"[VMREF] Release reference to volume manager. ptr:%p",
                &v44);
            }
            ScopedRef<VolumeManager::ShutdownRestartTask>::Set(&v34, 0);
          }
          ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v34);
        }
      }
    }
  }
  else
  {
    v23 = GetCurrentThreadId();
    VolumeManager = (unsigned int *)FrsStatusList::PushNewError(
                                      v24,
                                      9028,
                                      0,
                                      3,
                                      "base\\fs\\remotefs\\frs\\src\\sync\\outconnection.cpp",
                                      "OutConnection::TransportEstablishSession",
                                      454,
                                      v23,
                                      0);
    v6 = v40;
  }
  ScopedCrewLock::~ScopedCrewLock((ScopedCrewLock *)&v41);
  if ( !VolumeManager )
  {
    if ( v7 )
    {
      if ( !(unsigned int)ContentSetManager::IsSubordinate(v7) )
      {
        VolumeManager = (unsigned int *)ContentSetManager::RestartInConnectionSessionTask(
                                          v7,
                                          (const struct _GUID *)this + 2);
        v34 = (struct FrsStatus *)VolumeManager;
        if ( VolumeManager )
        {
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
          {
            v35 = L"OutConnection::TransportEstablishSession";
            v36 = 477;
            v37 = 3;
            v38 = L"OUTC";
            dbgobj::DbgPrint<unsigned short,_GUID,_GUID,FrsStringImpl<unsigned short,char>,FrsStatus>(
              (unsigned int)&v35,
              (unsigned int)L"(Ignored) Failed to restart inconnection session task. csId:%? connId:%? rgName:%? Error:%?",
              v45,
              (_DWORD)this + 32,
              *((_QWORD *)this + 21) + 72LL,
              (__int64)VolumeManager);
          }
          CLEAR_ERROR(&v34);
          VolumeManager = (unsigned int *)v34;
        }
      }
    }
  }
  if ( (_DWORD)v42 )
    OutConnectionContentSetContext::FinalizeOutConnectionContentSetContext(v6);
  if ( !VolumeManager && v7 )
  {
    ContentSetManager::UpdateLastOnlineTime(v7);
    v34 = 0;
    VolumeManager = (unsigned int *)ContentSetManager::GetVolumeManager(v7, &v34, v28);
    v29 = v34;
    if ( !VolumeManager )
    {
      if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugVolumeManagerRefCount)
        && g_DebugLog
        && LODWORD(g_DebugLog[1].LockSemaphore)
        && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        v35 = L"OutConnection::TransportEstablishSession";
        v36 = 501;
        v37 = 5;
        v38 = L"OUTC";
        v41 = v29;
        dbgobj::DbgPrint<unsigned short,unsigned __int64>(
          &v35,
          L"[VMREF] Added reference to volume manager. ptr:%p",
          &v41);
      }
      v30 = *(_QWORD *)v29;
      v45 = *(_OWORD *)v45;
      VolumeManager = (unsigned int *)(*(__int64 (__fastcall **)(struct FrsStatus *, __int128 *))(v30 + 64))(v29, &v45);
    }
    if ( v29 )
    {
      if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugVolumeManagerRefCount)
        && g_DebugLog
        && LODWORD(g_DebugLog[1].LockSemaphore)
        && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        v35 = L"OutConnection::TransportEstablishSession";
        v36 = 505;
        v37 = 5;
        v38 = L"OUTC";
        v41 = v29;
        dbgobj::DbgPrint<unsigned short,unsigned __int64>(
          &v35,
          L"[VMREF] Release reference to volume manager. ptr:%p",
          &v41);
      }
      ScopedRef<VolumeManager::ShutdownRestartTask>::Set(&v34, 0);
    }
    ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v34);
  }
  TimeoutCounter::Sample(v27, (union _LARGE_INTEGER *)this + 92);
  if ( VolumeManager )
  {
    v31 = GetCurrentThreadId();
    v4 = FrsStatusList::PushNewError(
           v32,
           VolumeManager[1],
           VolumeManager[2],
           *VolumeManager,
           "base\\fs\\remotefs\\frs\\src\\sync\\outconnection.cpp",
           "OutConnection::TransportEstablishSession",
           510,
           v31,
           VolumeManager);
  }
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v39);
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v43);
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v40);
  return (struct FrsStatus *)v4;
}

```

## disassembly

```asm
0x140175880  mov     [rsp-8+arg_10], rbx
0x140175885  push    rbp
0x140175886  push    rsi
0x140175887  push    rdi
0x140175888  push    r12
0x14017588a  push    r13
0x14017588c  push    r14
0x14017588e  push    r15
0x140175890  lea     rbp, [rsp-27h]
0x140175895  sub     rsp, 0C0h
0x14017589c  mov     rax, cs:__security_cookie
0x1401758a3  xor     rax, rsp
0x1401758a6  mov     [rbp+57h+var_40], rax
0x1401758aa  mov     rsi, rdx
0x1401758ad  mov     qword ptr [rbp+57h+var_50], rdx
0x1401758b1  mov     r13, rcx
0x1401758b4  xor     r15d, r15d
0x1401758b7  mov     r12d, r15d
0x1401758ba  mov     edi, r15d
0x1401758bd  mov     [rbp+57h+var_78], r15
0x1401758c1  mov     [rbp+57h+var_60], r15
0x1401758c5  mov     ebx, r15d
0x1401758c8  mov     [rbp+57h+var_80], rbx
0x1401758cc  mov     dword ptr [rbp+57h+var_68], r15d
0x1401758d0  lea     rdx, [rcx+278h]
0x1401758d7  lea     rcx, [rbp+57h+var_70]
0x1401758db  call    ??0ScopedCrewLock@@QEAA@AEAVCREWLock@@UWrite@0@@Z; ScopedCrewLock::ScopedCrewLock(CREWLock &,ScopedCrewLock::Write)
0x1401758e0  nop
0x1401758e1  lea     rcx, [r13+38h]
0x1401758e5  mov     rax, [rcx]
0x1401758e8  mov     rax, [rax+30h]
0x1401758ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401758f1  test    al, al
0x1401758f3  jnz     loc_140175D6E
0x1401758f9  lea     rcx, [r13+0B8h]
0x140175900  lea     r8, [rbp+57h+var_78]
0x140175904  mov     rdx, rsi
0x140175907  call    ?Find@?$RefMap@U_GUID@@VInConnectionContentSetContext@InConnection@@U?$less@U_GUID@@@std@@@@QEAAHAEBU_GUID@@AEAPEAVInConnectionContentSetContext@InConnection@@@Z; RefMap<_GUID,InConnection::InConnectionContentSetContext,std::less<_GUID>>::Find(_GUID const &,InConnection::InConnectionContentSetContext * &)
0x14017590c  test    eax, eax
0x14017590e  jz      loc_140175D1A
0x140175914  mov     rdi, [rbp+57h+var_78]
0x140175918  mov     rcx, [rdi+38h]; this
0x14017591c  test    rcx, rcx
0x14017591f  jnz     short loc_140175926
0x140175921  mov     edx, r15d
0x140175924  jmp     short loc_14017592F
0x140175926  call    ?AddRef@RefCountObject@@QEAAJXZ; RefCountObject::AddRef(void)
0x14017592b  mov     rdx, [rdi+38h]
0x14017592f  lea     rcx, [rbp+57h+var_80]
0x140175933  call    ?Set@?$ScopedRef@VShutdownRestartTask@VolumeManager@@@@AEAAXPEAVShutdownRestartTask@VolumeManager@@@Z; ScopedRef<VolumeManager::ShutdownRestartTask>::Set(VolumeManager::ShutdownRestartTask *)
0x140175938  mov     rbx, [rbp+57h+var_80]
0x14017593c  mov     rcx, rbx; this
0x14017593f  call    ?IsSubordinate@ContentSetManager@@QEAAHXZ; ContentSetManager::IsSubordinate(void)
0x140175944  lea     r14, aOutconnectionT_4; "OutConnection::TransportEstablishSessio"...
0x14017594b  mov     esi, 4
0x140175950  test    eax, eax
0x140175952  jz      loc_140175A02
0x140175958  call    cs:__imp_GetCurrentThreadId
0x14017595f  nop     dword ptr [rax+rax+00h]
0x140175964  mov     [rsp+0F0h+var_B0], r15
0x140175969  mov     [rsp+0F0h+var_B8], eax
0x14017596d  mov     [rsp+0F0h+var_C0], 182h
0x140175975  mov     [rsp+0F0h+var_C8], r14
0x14017597a  lea     rax, aBaseFsRemotefs_21; "base\\fs\\remotefs\\frs\\src\\sync\\out"...
0x140175981  mov     [rsp+0F0h+var_D0], rax
0x140175986  lea     r9d, [rsi-1]
0x14017598a  xor     r8d, r8d
0x14017598d  mov     edx, 2375h
0x140175992  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140175997  mov     r12, rax
0x14017599a  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401759a1  test    rax, rax
0x1401759a4  jz      short loc_1401759F9
0x1401759a6  cmp     [rax+40h], r15d
0x1401759aa  jz      short loc_1401759F9
0x1401759ac  cmp     [rax+38h], esi
0x1401759af  jl      short loc_1401759F9
0x1401759b1  lea     rax, aOutconnectionT_2; "OutConnection::TransportEstablishSessio"...
0x1401759b8  mov     [rbp+57h+var_98], rax
0x1401759bc  mov     [rbp+57h+var_90], 184h
0x1401759c3  mov     [rbp+57h+var_8C], esi
0x1401759c6  lea     rax, aOutc; "OUTC"
0x1401759cd  mov     [rbp+57h+var_88], rax
0x1401759d1  mov     rax, [r13+0A8h]
0x1401759d8  add     rax, 48h ; 'H'
0x1401759dc  lea     r9, [r13+20h]
0x1401759e0  mov     [rsp+0F0h+var_D0], rax
0x1401759e5  mov     r8, qword ptr [rbp+57h+var_50]
0x1401759e9  lea     rdx, aCannotEstablis; "Cannot establish session. This a read o"...
0x1401759f0  lea     rcx, [rbp+57h+var_98]
0x1401759f4  call    ??$DbgPrint@GU_GUID@@U1@V?$FrsStringImpl@GD@@@dbgobj@@QEAA_KPEBGAEBU_GUID@@1AEBV?$FrsStringImpl@GD@@@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID,FrsStringImpl<ushort,char>>(ushort const *,_GUID const &,_GUID const &,FrsStringImpl<ushort,char> const &)
0x1401759f9  test    r12, r12
0x1401759fc  jnz     loc_140175E1E
0x140175a02  lea     rcx, [rbx+460h]
0x140175a09  call    ?Get@?$ConfigInstance@VContentSet@Config@@@Config@@QEAAPEAVContentSet@2@XZ; Config::ConfigInstance<Config::ContentSet>::Get(void)
0x140175a0e  mov     [rbp+57h+var_A0], rax
0x140175a12  test    rax, rax
0x140175a15  jz      short loc_140175A6B
0x140175a17  lea     rcx, [rax+460h]; this
0x140175a1e  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x140175a23  test    eax, eax
0x140175a25  jnz     short loc_140175A6B
0x140175a27  call    cs:__imp_GetCurrentThreadId
0x140175a2e  nop     dword ptr [rax+rax+00h]
0x140175a33  mov     [rsp+0F0h+var_B0], r15
0x140175a38  mov     [rsp+0F0h+var_B8], eax
0x140175a3c  mov     [rsp+0F0h+var_C0], 197h
0x140175a44  mov     [rsp+0F0h+var_C8], r14
0x140175a49  lea     rax, aBaseFsRemotefs_21; "base\\fs\\remotefs\\frs\\src\\sync\\out"...
0x140175a50  mov     [rsp+0F0h+var_D0], rax
0x140175a55  mov     r9d, 3
0x140175a5b  xor     r8d, r8d
0x140175a5e  mov     edx, 235Ch
0x140175a63  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140175a68  mov     r12, rax
0x140175a6b  lea     rcx, [rbp+57h+var_A0]
0x140175a6f  call    ??1?$ScopedRef@VReplicaSet@Config@@@@QEAA@XZ; ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(void)
0x140175a74  test    r12, r12
0x140175a77  jnz     loc_140175E1E
0x140175a7d  mov     eax, [rbx+250h]
0x140175a83  test    eax, eax
0x140175a85  jnz     loc_140175CC9
0x140175a8b  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140175a92  test    rax, rax
0x140175a95  jz      short loc_140175AEC
0x140175a97  cmp     [rax+40h], r15d
0x140175a9b  jz      short loc_140175AEC
0x140175a9d  cmp     [rax+38h], esi
0x140175aa0  jl      short loc_140175AEC
0x140175aa2  lea     rax, aOutconnectionT_2; "OutConnection::TransportEstablishSessio"...
0x140175aa9  mov     [rbp+57h+var_98], rax
0x140175aad  mov     [rbp+57h+var_90], 19Fh
0x140175ab4  mov     [rbp+57h+var_8C], esi
0x140175ab7  lea     rsi, aOutc; "OUTC"
0x140175abe  mov     [rbp+57h+var_88], rsi
0x140175ac2  mov     rax, [r13+0A8h]
0x140175ac9  add     rax, 48h ; 'H'
0x140175acd  lea     r9, [r13+20h]
0x140175ad1  mov     [rsp+0F0h+var_D0], rax
0x140175ad6  mov     r8, qword ptr [rbp+57h+var_50]
0x140175ada  lea     rdx, aReplacingConte; "Replacing content set. csId:%? connId:%"...
0x140175ae1  lea     rcx, [rbp+57h+var_98]
0x140175ae5  call    ??$DbgPrint@GU_GUID@@U1@V?$FrsStringImpl@GD@@@dbgobj@@QEAA_KPEBGAEBU_GUID@@1AEBV?$FrsStringImpl@GD@@@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID,FrsStringImpl<ushort,char>>(ushort const *,_GUID const &,_GUID const &,FrsStringImpl<ushort,char> const &)
0x140175aea  jmp     short loc_140175AF3
0x140175aec  lea     rsi, aOutc; "OUTC"
0x140175af3  mov     [rbp+57h+var_A0], r15
0x140175af7  lea     rdx, [rbp+57h+var_A0]
0x140175afb  mov     rbx, [rbp+57h+var_80]
0x140175aff  mov     rcx, rbx
0x140175b02  call    ?GetVolumeManager@ContentSetManager@@QEAAPEAVFrsStatus@@AEAV?$ScopedRef@VVolumeManager@@@@@Z; ContentSetManager::GetVolumeManager(ScopedRef<VolumeManager> &)
0x140175b07  mov     r12, rax
0x140175b0a  mov     rdi, [rbp+57h+var_78]
0x140175b0e  mov     r14, [rbp+57h+var_A0]
0x140175b12  test    rax, rax
0x140175b15  jnz     loc_140175C3F
0x140175b1b  lea     rcx, ?DebugVolumeManagerRefCount@Settings@@3VCDebugVolumeManagerRefCount@1@A; Settings::CDebugVolumeManagerRefCount Settings::DebugVolumeManagerRefCount
0x140175b22  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x140175b27  test    eax, eax
0x140175b29  jz      short loc_140175B78
0x140175b2b  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140175b32  test    rax, rax
0x140175b35  jz      short loc_140175B78
0x140175b37  cmp     [rax+40h], r15d
0x140175b3b  jz      short loc_140175B78
0x140175b3d  cmp     dword ptr [rax+38h], 5
0x140175b41  jl      short loc_140175B78
0x140175b43  lea     rax, aOutconnectionT_2; "OutConnection::TransportEstablishSessio"...
0x140175b4a  mov     [rbp+57h+var_98], rax
0x140175b4e  mov     [rbp+57h+var_90], 1ADh
0x140175b55  mov     [rbp+57h+var_8C], 5
0x140175b5c  mov     [rbp+57h+var_88], rsi
0x140175b60  mov     [rbp+57h+var_68], r14
0x140175b64  lea     r8, [rbp+57h+var_68]
0x140175b68  lea     rdx, aVmrefAddedRefe; "[VMREF] Added reference to volume manag"...
0x140175b6f  lea     rcx, [rbp+57h+var_98]
0x140175b73  call    ??$DbgPrint@G_K@dbgobj@@QEAA_KPEBGAEB_K@Z; dbgobj::DbgPrint<ushort,unsigned __int64>(ushort const *,unsigned __int64 const &)
0x140175b78  mov     ecx, 130h; Size
0x140175b7d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140175b82  mov     [rbp+57h+var_58], rax
0x140175b86  lea     rcx, [rbp+57h+var_80]
0x140175b8a  mov     [rsp+0F0h+var_D0], rcx
0x140175b8f  lea     r9, [rbp+57h+var_A0]
0x140175b93  mov     r8, r13
0x140175b96  mov     rdx, [r14+38h]
0x140175b9a  mov     rcx, rax
0x140175b9d  call    ??0Join@@QEAA@PEAVTaskPool@@PEAVOutConnection@@AEAV?$ScopedRef@VVolumeManager@@@@AEAV?$ScopedRef@VContentSetManager@@@@@Z; Join::Join(TaskPool *,OutConnection *,ScopedRef<VolumeManager> &,ScopedRef<ContentSetManager> &)
0x140175ba2  mov     rsi, rax
0x140175ba5  mov     ecx, 0E8h; Size
0x140175baa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140175baf  mov     [rbp+57h+var_58], rax
0x140175bb3  lea     r9, [r13+20h]
0x140175bb7  lea     rdx, [r13+0A8h]
0x140175bbe  lea     rcx, [rbp+57h+var_80]
0x140175bc2  mov     [rsp+0F0h+var_D0], rcx
0x140175bc7  mov     r8, rsi
0x140175bca  mov     rcx, rax
0x140175bcd  call    ??0OutConnectionContentSetContext@@QEAA@AEAV?$ScopedRef@VReplicaSetManager@@@@PEAVJoin@@AEBU_GUID@@AEAV?$ScopedRef@VContentSetManager@@@@@Z; OutConnectionContentSetContext::OutConnectionContentSetContext(ScopedRef<ReplicaSetManager> &,Join *,_GUID const &,ScopedRef<ContentSetManager> &)
0x140175bd2  nop
0x140175bd3  mov     rdx, rax
0x140175bd6  lea     rcx, [rbp+57h+var_60]
0x140175bda  call    ?Set@?$ScopedRef@VShutdownRestartTask@VolumeManager@@@@AEAAXPEAVShutdownRestartTask@VolumeManager@@@Z; ScopedRef<VolumeManager::ShutdownRestartTask>::Set(VolumeManager::ShutdownRestartTask *)
0x140175bdf  mov     rcx, rdi; this
0x140175be2  call    ?PrepareShutdownOutConnectionContentSetContext@OutConnectionContentSetContext@@QEAAXXZ; OutConnectionContentSetContext::PrepareShutdownOutConnectionContentSetContext(void)
0x140175be7  test    rdi, rdi
0x140175bea  lea     rdx, [rdi+20h]
0x140175bee  jnz     short loc_140175BF3
0x140175bf0  mov     rdx, r15; struct ShutdownObject *
0x140175bf3  lea     rcx, [r13+38h]; this
0x140175bf7  call    ?UnRegisterShutdownObject@CompositeShutdownObject@@QEAAXPEAVShutdownObject@@@Z; CompositeShutdownObject::UnRegisterShutdownObject(ShutdownObject *)
0x140175bfc  mov     rdx, qword ptr [rbp+57h+var_50]
0x140175c00  lea     rcx, [r13+0B8h]
0x140175c07  call    ?Delete@?$RefMap@U_GUID@@VReplicaSetManager@@U?$less@U_GUID@@@std@@@@QEAAXAEBU_GUID@@@Z; RefMap<_GUID,ReplicaSetManager,std::less<_GUID>>::Delete(_GUID const &)
0x140175c0c  mov     rsi, [rbp+57h+var_60]
0x140175c10  mov     r8, rsi
0x140175c13  mov     rdx, qword ptr [rbp+57h+var_50]
0x140175c17  lea     rcx, [r13+0B8h]
0x140175c1e  call    ?Insert@?$RefMap@U_GUID@@VReplicaSetManager@@U?$less@U_GUID@@@std@@@@QEAAXAEBU_GUID@@PEAVReplicaSetManager@@@Z; RefMap<_GUID,ReplicaSetManager,std::less<_GUID>>::Insert(_GUID const &,ReplicaSetManager *)
0x140175c23  test    rsi, rsi
0x140175c26  lea     rdx, [rsi+20h]
0x140175c2a  jnz     short loc_140175C2F
0x140175c2c  mov     rdx, r15; struct ShutdownObject *
0x140175c2f  lea     rcx, [r13+38h]; this
0x140175c33  call    ?RegisterShutdownObject@CompositeShutdownObject@@QEAAXPEAVShutdownObject@@@Z; CompositeShutdownObject::RegisterShutdownObject(ShutdownObject *)
0x140175c38  mov     dword ptr [rbp+57h+var_68], 1
0x140175c3f  test    r14, r14
0x140175c42  jz      short loc_140175CB4
0x140175c44  lea     rcx, ?DebugVolumeManagerRefCount@Settings@@3VCDebugVolumeManagerRefCount@1@A; Settings::CDebugVolumeManagerRefCount Settings::DebugVolumeManagerRefCount
0x140175c4b  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x140175c50  test    eax, eax
0x140175c52  jz      short loc_140175CA8
0x140175c54  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140175c5b  test    rax, rax
0x140175c5e  jz      short loc_140175CA8
0x140175c60  cmp     [rax+40h], r15d
0x140175c64  jz      short loc_140175CA8
0x140175c66  cmp     dword ptr [rax+38h], 5
0x140175c6a  jl      short loc_140175CA8
0x140175c6c  lea     rax, aOutconnectionT_2; "OutConnection::TransportEstablishSessio"...
0x140175c73  mov     [rbp+57h+var_98], rax
0x140175c77  mov     [rbp+57h+var_90], 1BEh
0x140175c7e  mov     [rbp+57h+var_8C], 5
0x140175c85  lea     rax, aOutc; "OUTC"
0x140175c8c  mov     [rbp+57h+var_88], rax
0x140175c90  mov     [rbp+57h+var_58], r14
0x140175c94  lea     r8, [rbp+57h+var_58]
0x140175c98  lea     rdx, aVmrefReleaseRe; "[VMREF] Release reference to volume man"...
0x140175c9f  lea     rcx, [rbp+57h+var_98]
0x140175ca3  call    ??$DbgPrint@G_K@dbgobj@@QEAA_KPEBGAEB_K@Z; dbgobj::DbgPrint<ushort,unsigned __int64>(ushort const *,unsigned __int64 const &)
0x140175ca8  xor     edx, edx
0x140175caa  lea     rcx, [rbp+57h+var_A0]
0x140175cae  call    ?Set@?$ScopedRef@VShutdownRestartTask@VolumeManager@@@@AEAAXPEAVShutdownRestartTask@VolumeManager@@@Z; ScopedRef<VolumeManager::ShutdownRestartTask>::Set(VolumeManager::ShutdownRestartTask *)
0x140175cb3  nop
0x140175cb4  lea     rcx, [rbp+57h+var_A0]
0x140175cb8  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x140175cbd  lea     r14, aOutconnectionT_4; "OutConnection::TransportEstablishSessio"...
0x140175cc4  jmp     loc_140175E1E
0x140175cc9  call    cs:__imp_GetCurrentThreadId
0x140175cd0  nop     dword ptr [rax+rax+00h]
0x140175cd5  mov     [rsp+0F0h+var_B0], r15
0x140175cda  mov     [rsp+0F0h+var_B8], eax
0x140175cde  mov     [rsp+0F0h+var_C0], 1C1h
0x140175ce6  mov     [rsp+0F0h+var_C8], r14
0x140175ceb  lea     rax, aBaseFsRemotefs_21; "base\\fs\\remotefs\\frs\\src\\sync\\out"...
0x140175cf2  mov     [rsp+0F0h+var_D0], rax
0x140175cf7  mov     r9d, 3
0x140175cfd  xor     r8d, r8d
0x140175d00  mov     edx, 235Bh
0x140175d05  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140175d0a  mov     r12, rax
0x140175d0d  mov     rdi, [rbp+57h+var_78]
0x140175d11  mov     rbx, [rbp+57h+var_80]
0x140175d15  jmp     loc_140175E1E
0x140175d1a  call    cs:__imp_GetCurrentThreadId
0x140175d21  nop     dword ptr [rax+rax+00h]
0x140175d26  mov     [rsp+0F0h+var_B0], r15
0x140175d2b  mov     [rsp+0F0h+var_B8], eax
0x140175d2f  mov     [rsp+0F0h+var_C0], 1C6h
0x140175d37  lea     r14, aOutconnectionT_4; "OutConnection::TransportEstablishSessio"...
0x140175d3e  mov     [rsp+0F0h+var_C8], r14
0x140175d43  lea     rsi, aBaseFsRemotefs_21; "base\\fs\\remotefs\\frs\\src\\sync\\out"...
0x140175d4a  mov     [rsp+0F0h+var_D0], rsi
0x140175d4f  mov     r9d, 3
0x140175d55  xor     r8d, r8d
0x140175d58  mov     edx, 2344h
0x140175d5d  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140175d62  mov     r12, rax
0x140175d65  mov     rdi, [rbp+57h+var_78]
0x140175d69  jmp     loc_140175E1E
0x140175d6e  call    cs:__imp_GetCurrentThreadId
0x140175d75  nop     dword ptr [rax+rax+00h]
0x140175d7a  mov     [rsp+0F0h+var_B0], r15
0x140175d7f  mov     [rsp+0F0h+var_B8], eax
0x140175d83  mov     [rsp+0F0h+var_C0], 1CAh
0x140175d8b  lea     r14, aOutconnectionT_4; "OutConnection::TransportEstablishSessio"...
0x140175d92  mov     [rsp+0F0h+var_C8], r14
0x140175d97  lea     rax, aBaseFsRemotefs_21; "base\\fs\\remotefs\\frs\\src\\sync\\out"...
0x140175d9e  mov     [rsp+0F0h+var_D0], rax
0x140175da3  mov     r9d, 3
0x140175da9  xor     r8d, r8d
0x140175dac  mov     edx, 2348h
  ... truncated ...
```
