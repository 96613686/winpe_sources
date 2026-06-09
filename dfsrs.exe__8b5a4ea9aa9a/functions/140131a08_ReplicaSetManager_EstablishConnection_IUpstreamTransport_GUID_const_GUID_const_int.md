# ReplicaSetManager::EstablishConnection(IUpstreamTransport *,_GUID const &,_GUID const &,int)

- ea: `0x140131a08`
- end: `0x1401322c6`
- name: `?EstablishConnection@ReplicaSetManager@@QEAAPEAVFrsStatus@@PEAVIUpstreamTransport@@AEBU_GUID@@1H@Z`
- size: `2238`
- prototype: `struct FrsStatus *(ReplicaSetManager *__hidden this, struct IUpstreamTransport *, const struct _GUID *, const struct _GUID *, int)`
- caller_count: `1`
- callee_count: `35`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14019f8e0`

## callees

- `0x1400036d0`
- `0x14000d980`
- `0x14000daa0`
- `0x14000dcc0`
- `0x140011408`
- `0x14001e6f4`
- `0x14001e710`
- `0x14002c2f4`
- `0x1400370bc`
- `0x14003793c`
- `0x14003980c`
- `0x1400398bc`
- `0x14003c928`
- `0x14003d368`
- `0x140052ae8`
- `0x14006b418`
- `0x14007ca24`
- `0x1400812c8`
- `0x140083594`
- `0x1400878e4`
- `0x140087aa8`
- `0x1400e5f48`
- `0x14012f7e4`
- `0x14012fd64`
- `0x1401302c8`
- `0x1401311b8`
- `0x140131a08`
- `0x1401325f4`
- `0x140165dbc`
- `0x14016f880`
- `0x14017060c`
- `0x140175284`
- `0x1401b30b0`
- `0x1401b9494`
- `0x140223010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140131e7b`
- `KERNEL32!LeaveCriticalSection` at `0x140131e7b`
- `KERNEL32!EnterCriticalSection` at `0x140131e94`
- `KERNEL32!EnterCriticalSection` at `0x140131e94`
- `KERNEL32!GetCurrentThreadId` at `0x140131ad9`
- `KERNEL32!GetCurrentThreadId` at `0x140131b86`
- `KERNEL32!GetCurrentThreadId` at `0x140131c50`
- `KERNEL32!GetCurrentThreadId` at `0x140131d2e`
- `KERNEL32!GetCurrentThreadId` at `0x140131f39`
- `KERNEL32!GetCurrentThreadId` at `0x140131f83`
- `KERNEL32!GetCurrentThreadId` at `0x14013202d`
- `KERNEL32!GetCurrentThreadId` at `0x140132243`
- `KERNEL32!GetCurrentThreadId` at `0x140131ad9`
- `KERNEL32!GetCurrentThreadId` at `0x140131b86`
- `KERNEL32!GetCurrentThreadId` at `0x140131c50`
- `KERNEL32!GetCurrentThreadId` at `0x140131d2e`
- `KERNEL32!GetCurrentThreadId` at `0x140131f39`
- `KERNEL32!GetCurrentThreadId` at `0x140131f83`
- `KERNEL32!GetCurrentThreadId` at `0x14013202d`
- `KERNEL32!GetCurrentThreadId` at `0x140132243`

## string_xrefs

- `0x140131d1e`: `Connection was not found in configuration. connId:%? rgId:%? rgName:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
struct FrsStatus *__fastcall ReplicaSetManager::EstablishConnection(
        ReplicaSetManager *this,
        struct IUpstreamTransport *a2,
        struct _GUID *a3,
        const struct _GUID *a4,
        int a5)
{
  const struct _GUID *v5; // r12
  __int64 v8; // rsi
  unsigned int *v9; // rdi
  __int64 v10; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v12; // rcx
  DWORD v13; // eax
  __int64 v14; // rcx
  int v15; // edx
  const struct Member *v16; // r12
  DWORD v17; // eax
  __int64 v18; // rcx
  DWORD v19; // eax
  __int64 v20; // rcx
  _QWORD *v21; // rax
  _QWORD *v22; // r8
  char *v23; // r13
  int v24; // ebx
  DWORD v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rax
  DWORD v28; // eax
  __int64 v29; // rcx
  DWORD v30; // eax
  __int64 v31; // rcx
  __int64 v32; // rax
  OutConnection *v33; // rbx
  _QWORD *v34; // rax
  __int64 v35; // r8
  RefCountObject **v36; // rdi
  InConnection **j; // rbx
  DWORD v38; // eax
  __int64 v39; // rcx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+58h] [rbp-61h] BYREF
  int v42; // [rsp+60h] [rbp-59h]
  int v43; // [rsp+64h] [rbp-55h]
  const wchar_t *v44; // [rsp+68h] [rbp-51h]
  const wchar_t *v45; // [rsp+70h] [rbp-49h] BYREF
  int v46; // [rsp+78h] [rbp-41h]
  int v47; // [rsp+7Ch] [rbp-3Dh]
  const wchar_t *v48; // [rsp+80h] [rbp-39h]
  RefCountObject *v49; // [rsp+88h] [rbp-31h] BYREF
  struct Config::ReplicaSet *i; // [rsp+90h] [rbp-29h] BYREF
  __int64 v51; // [rsp+98h] [rbp-21h] BYREF
  __int64 v52; // [rsp+A0h] [rbp-19h] BYREF
  _QWORD v53[12]; // [rsp+A8h] [rbp-11h] BYREF
  OutConnection *v54; // [rsp+118h] [rbp+5Fh] BYREF
  RefCountObject *v55; // [rsp+120h] [rbp+67h]
  const struct _GUID *v56; // [rsp+130h] [rbp+77h]

  v56 = a4;
  v55 = a2;
  v5 = a4;
  v8 = 0;
  v9 = 0;
  v54 = 0;
  v52 = 0;
  ScopedLock::ScopedLock((ScopedLock *)&lpCriticalSection, (ReplicaSetManager *)((char *)this + 112));
  v10 = *((_QWORD *)this + 13);
  i = (struct Config::ReplicaSet *)v10;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 40LL))(v10);
  ScopedLock::~ScopedLock((ScopedLock *)&lpCriticalSection);
  v52 = v10;
  if ( !*((_DWORD *)this + 114) )
    goto LABEL_68;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    lpCriticalSection = (LPCRITICAL_SECTION)L"ReplicaSetManager::EstablishConnection";
    v42 = 390;
    v43 = 5;
    v44 = L"RSMG";
    dbgobj::DbgPrint<unsigned short,_GUID,FrsStringImpl<unsigned short,char>>(
      &lpCriticalSection,
      L"Shutting down. rgId:%? rgName:%?",
      (char *)this + 88,
      (char *)this + 72);
  }
  CurrentThreadId = GetCurrentThreadId();
  v9 = (unsigned int *)FrsStatusList::PushNewError(
                         v12,
                         9033,
                         0,
                         3,
                         "base\\fs\\remotefs\\frs\\src\\sync\\replicasetmanager.cpp",
                         "ReplicaSetManager::EstablishConnection",
                         391,
                         CurrentThreadId,
                         0);
  if ( !v9 )
  {
LABEL_68:
    if ( v10 )
      goto LABEL_13;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      lpCriticalSection = (LPCRITICAL_SECTION)L"ReplicaSetManager::EstablishConnection";
      v42 = 395;
      v43 = 5;
      v44 = L"RSMG";
      dbgobj::DbgPrint<unsigned short,_GUID,FrsStringImpl<unsigned short,char>>(
        &lpCriticalSection,
        L"Replication group does not exist. rgId:%? rgName:%?",
        (char *)this + 88,
        (char *)this + 72);
    }
    v13 = GetCurrentThreadId();
    v9 = (unsigned int *)FrsStatusList::PushNewError(
                           v14,
                           9057,
                           0,
                           3,
                           "base\\fs\\remotefs\\frs\\src\\sync\\replicasetmanager.cpp",
                           "ReplicaSetManager::EstablishConnection",
                           396,
                           v13,
                           0);
    if ( !v9 )
    {
LABEL_13:
      v16 = (const struct Member *)Config::ConnectionList::Find(
                                     (Config::ConnectionList *)(v10 + 904),
                                     (const struct _GUID *)this + 2,
                                     0);
      if ( !v16 )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
        {
          lpCriticalSection = (LPCRITICAL_SECTION)L"ReplicaSetManager::EstablishConnection";
          v42 = 402;
          v43 = 3;
          v44 = L"RSMG";
          dbgobj::DbgPrint<unsigned short,_GUID,_GUID,_GUID,FrsStringImpl<unsigned short,char>>(
            (unsigned int)&lpCriticalSection,
            v15,
            (_DWORD)a3,
            (_DWORD)this + 32,
            (__int64)this + 88,
            (__int64)this + 72);
        }
        v17 = GetCurrentThreadId();
        v9 = (unsigned int *)FrsStatusList::PushNewError(
                               v18,
                               9056,
                               0,
                               3,
                               "base\\fs\\remotefs\\frs\\src\\sync\\replicasetmanager.cpp",
                               "ReplicaSetManager::EstablishConnection",
                               407,
                               v17,
                               0);
        if ( v9 )
          goto LABEL_57;
      }
      Config::Member::ScopedMemberConnectionList::ScopedMemberConnectionList(
        (Config::Member::ScopedMemberConnectionList *)v53,
        v16);
      if ( !Config::ConnectionList::Find((Config::ConnectionList *)(v53[0] + 392LL), a3, 0) )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
        {
          lpCriticalSection = (LPCRITICAL_SECTION)L"ReplicaSetManager::EstablishConnection";
          v42 = 416;
          v43 = 3;
          v44 = L"RSMG";
          dbgobj::DbgPrint<unsigned short,_GUID,_GUID,FrsStringImpl<unsigned short,char>>(
            (unsigned int)&lpCriticalSection,
            (unsigned int)L"Connection was not found in configuration. connId:%? rgId:%? rgName:%?",
            (_DWORD)a3,
            (_DWORD)this + 88,
            (__int64)this + 72);
        }
        v19 = GetCurrentThreadId();
        v9 = (unsigned int *)FrsStatusList::PushNewError(
                               v20,
                               9026,
                               0,
                               3,
                               "base\\fs\\remotefs\\frs\\src\\sync\\replicasetmanager.cpp",
                               "ReplicaSetManager::EstablishConnection",
                               420,
                               v19,
                               0);
      }
      Config::Member::ScopedMemberConnectionList::~ScopedMemberConnectionList((Config::Member::ScopedMemberConnectionList *)v53);
      if ( v9 )
        goto LABEL_57;
      ScopedLock::ScopedLock((ScopedLock *)&lpCriticalSection, (ReplicaSetManager *)((char *)this + 264));
      if ( a5 )
        std::_Tree<std::_Tset_traits<_GUID,std::less<_GUID>,std::allocator<_GUID>,0>>::insert<0,0>(
          (char *)this + 248,
          &v45,
          a3);
      std::_Tree<std::_Tmap_traits<Guid,_SYSTEMTIME,std::less<Guid>,std::allocator<std::pair<Guid const,_SYSTEMTIME>>,0>>::find(
        (char *)this + 216,
        &v51,
        a3);
      v21 = (_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(
                        (char *)this + 216,
                        &v49);
      if ( *v22 == *v21 )
      {
        v23 = (char *)this + 192;
        if ( !(unsigned int)RefMap<_GUID,InConnection::InConnectionContentSetContext,std::less<_GUID>>::Find(
                              (char *)this + 192,
                              a3,
                              &v54) )
          goto LABEL_42;
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
        {
          v45 = L"ReplicaSetManager::EstablishConnection";
          v46 = 453;
          v47 = 3;
          v48 = L"RSMG";
          dbgobj::DbgPrint<unsigned short,_GUID,_GUID,FrsStringImpl<unsigned short,char>>(
            (unsigned int)&v45,
            (unsigned int)L"Shutting down existing connection. connId:%? rgId:%? rgName:%?",
            (_DWORD)a3,
            (_DWORD)this + 88,
            (__int64)this + 72);
        }
        std::_Tree<std::_Tset_traits<_GUID,std::less<_GUID>,std::allocator<_GUID>,0>>::insert<0,0>(
          (char *)this + 216,
          &v45,
          a3);
        v24 = --v42;
        LeaveCriticalSection(lpCriticalSection);
        OutConnection::ShutdownOutConnection(v54);
        EnterCriticalSection(lpCriticalSection);
        v42 = v24 + 1;
        std::_Tree<std::_Tset_traits<_GUID,std::less<_GUID>,std::allocator<_GUID>,0>>::erase((char *)this + 216, a3);
        RefMap<_GUID,ReplicaSetManager,std::less<_GUID>>::Delete((char *)this + 192, a3);
        ScopedRef<VolumeManager::ShutdownRestartTask>::Set(&v54, 0);
        if ( !(unsigned int)RefMap<_GUID,InConnection::InConnectionContentSetContext,std::less<_GUID>>::Find(
                              (char *)this + 192,
                              a3,
                              &v54) )
          goto LABEL_42;
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
        {
          v45 = L"ReplicaSetManager::EstablishConnection";
          v46 = 470;
          v47 = 3;
          v48 = L"RSMG";
          dbgobj::DbgPrint<unsigned short,_GUID,_GUID,FrsStringImpl<unsigned short,char>>(
            (unsigned int)&v45,
            (unsigned int)L"Abandoning new connection. connId:%? rgId:%? rgName:%?",
            (_DWORD)a3,
            (_DWORD)this + 88,
            (__int64)this + 72);
        }
        v25 = GetCurrentThreadId();
        v27 = FrsStatusList::PushNewError(
                v26,
                9026,
                0,
                3,
                "base\\fs\\remotefs\\frs\\src\\sync\\replicasetmanager.cpp",
                "ReplicaSetManager::EstablishConnection",
                474,
                v25,
                0);
      }
      else
      {
        v28 = GetCurrentThreadId();
        v27 = FrsStatusList::PushNewError(
                v29,
                9032,
                0,
                3,
                "base\\fs\\remotefs\\frs\\src\\sync\\replicasetmanager.cpp",
                "ReplicaSetManager::EstablishConnection",
                446,
                v28,
                0);
        v23 = (char *)this + 192;
      }
      v9 = (unsigned int *)v27;
      if ( v27 )
      {
LABEL_56:
        ScopedLock::~ScopedLock((ScopedLock *)&lpCriticalSection);
LABEL_57:
        v5 = v56;
        goto LABEL_58;
      }
LABEL_42:
      if ( !*((_DWORD *)this + 114) )
        goto LABEL_48;
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        v45 = L"ReplicaSetManager::EstablishConnection";
        v46 = 483;
        v47 = 5;
        v48 = L"RSMG";
        dbgobj::DbgPrint<unsigned short,_GUID,FrsStringImpl<unsigned short,char>>(
          &v45,
          L"Shutting down. rgId:%? rgName:%?",
          (char *)this + 88,
          (char *)this + 72);
      }
      v30 = GetCurrentThreadId();
      v9 = (unsigned int *)FrsStatusList::PushNewError(
                             v31,
                             9033,
                             0,
                             3,
                             "base\\fs\\remotefs\\frs\\src\\sync\\replicasetmanager.cpp",
                             "ReplicaSetManager::EstablishConnection",
                             484,
                             v30,
                             0);
      if ( !v9 )
      {
LABEL_48:
        v51 = 0;
        RefCountObject::AddRef(this);
        ScopedRef<VolumeManager::ShutdownRestartTask>::Set(&v51, this);
        v49 = (RefCountObject *)operator new(0x320u);
        v32 = OutConnection::OutConnection(v49, a3, v55, i);
        ScopedRef<VolumeManager::ShutdownRestartTask>::Set(&v54, v32);
        v33 = v54;
        RefMap<_GUID,ReplicaSetManager,std::less<_GUID>>::Insert(v23, a3, v54);
        for ( i = (struct Config::ReplicaSet *)**((_QWORD **)this + 66);
              ;
              std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,VvCompactTask *>>>,std::_Iterator_base0>::operator++(&i) )
        {
          v34 = (_QWORD *)std::_Tree<std::_Tmap_traits<UpdateManager *,std::multimap<_FILETIME,UpdateReference *>,ComparePointers<UpdateManager>,std::allocator<std::pair<UpdateManager * const,std::multimap<_FILETIME,UpdateReference *>>>,0>>::end(
                            (char *)this + 464,
                            &v45);
          if ( v35 == *v34 )
            break;
          v49 = 0;
          v36 = (RefCountObject **)std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<VolumeId const,IMarkAndSweepTask *>>>>::operator*(&i);
          RefCountObject::AddRef(*v36);
          ScopedRef<VolumeManager::ShutdownRestartTask>::Set(&v49, *v36);
          OutConnection::AddContentSetToOutConnection(v33, &v49);
          ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v49);
        }
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v45 = L"ReplicaSetManager::EstablishConnection";
          v46 = 511;
          v47 = 5;
          v48 = L"RSMG";
          dbgobj::DbgPrint<unsigned short,_GUID,FrsStringImpl<unsigned short,char>>(
            &v45,
            L"Attaching out connection to transport rgId:%? rgName:%?",
            (char *)this + 88,
            (char *)this + 72);
        }
        v9 = (unsigned int *)(*(__int64 (__fastcall **)(RefCountObject *, OutConnection *))(*(_QWORD *)v55 + 8LL))(
                               v55,
                               v33);
        ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v51);
      }
      goto LABEL_56;
    }
  }
LABEL_58:
  RefList<InConnection>::RefList<InConnection>(v53);
  if ( !v9 )
  {
    ScopedLock::ScopedLock((ScopedLock *)&lpCriticalSection, (ReplicaSetManager *)((char *)this + 264));
    RefMap<_GUID,InConnection::InConnectionContentSetContext,std::less<_GUID>>::GetAll((char *)this + 168, v53);
    ScopedLock::~ScopedLock((ScopedLock *)&lpCriticalSection);
  }
  for ( j = *(InConnection ***)RefList<VolumeManager>::Begin(v53, &v45);
        j != *(InConnection ***)RefList<ContentSetManager>::End(v53, &v51);
        ++j )
  {
    InConnection::OnEstablishedOutConnection(*j, v5);
  }
  if ( v9 )
  {
    v38 = GetCurrentThreadId();
    v8 = FrsStatusList::PushNewError(
           v39,
           v9[1],
           v9[2],
           *v9,
           "base\\fs\\remotefs\\frs\\src\\sync\\replicasetmanager.cpp",
           "ReplicaSetManager::EstablishConnection",
           543,
           v38,
           v9);
  }
  RefList<InConnection>::~RefList<InConnection>(v53);
  ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v52);
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v54);
  return (struct FrsStatus *)v8;
}

```

## disassembly

```asm
0x140131a08  mov     rax, rsp
0x140131a0b  mov     [rax+18h], rbx
0x140131a0f  mov     [rax+20h], r9
0x140131a13  mov     [rax+10h], rdx
0x140131a17  push    rbp
0x140131a18  push    rsi
0x140131a19  push    rdi
0x140131a1a  push    r12
0x140131a1c  push    r13
0x140131a1e  push    r14
0x140131a20  push    r15
0x140131a22  lea     rbp, [rax-57h]
0x140131a26  sub     rsp, 0D0h
0x140131a2d  mov     r12, r9
0x140131a30  mov     r15, r8
0x140131a33  mov     r14, rcx
0x140131a36  xor     esi, esi
0x140131a38  mov     edi, esi
0x140131a3a  mov     [rbp+4Fh+arg_0], rsi
0x140131a3e  mov     [rbp+4Fh+var_68], rsi
0x140131a42  lea     rdx, [rcx+70h]; struct ScopedCS *
0x140131a46  lea     rcx, [rbp+4Fh+lpCriticalSection]; this
0x140131a4a  call    ??0ScopedLock@@QEAA@AEAVScopedCS@@@Z; ScopedLock::ScopedLock(ScopedCS &)
0x140131a4f  nop
0x140131a50  mov     rbx, [r14+68h]
0x140131a54  mov     [rbp+4Fh+var_78], rbx
0x140131a58  mov     rax, [rbx]
0x140131a5b  mov     rcx, rbx
0x140131a5e  mov     rax, [rax+28h]
0x140131a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140131a67  nop
0x140131a68  lea     rcx, [rbp+4Fh+lpCriticalSection]; this
0x140131a6c  call    ??1ScopedLock@@QEAA@XZ; ScopedLock::~ScopedLock(void)
0x140131a71  mov     [rbp+4Fh+var_68], rbx
0x140131a75  lea     rcx, aReplicasetmana_8; "ReplicaSetManager::EstablishConnection"
0x140131a7c  lea     rdx, aRsmg; "RSMG"
0x140131a83  lea     r13d, [rsi+3]
0x140131a87  cmp     [r14+1C8h], esi
0x140131a8e  jz      loc_140131B38
0x140131a94  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140131a9b  test    rax, rax
0x140131a9e  jz      short loc_140131AD9
0x140131aa0  cmp     [rax+40h], esi
0x140131aa3  jz      short loc_140131AD9
0x140131aa5  cmp     dword ptr [rax+38h], 5
0x140131aa9  jl      short loc_140131AD9
0x140131aab  mov     [rbp+4Fh+lpCriticalSection], rcx
0x140131aaf  mov     [rbp+4Fh+var_A8], 186h
0x140131ab6  mov     [rbp+4Fh+var_A4], 5
0x140131abd  mov     [rbp+4Fh+var_A0], rdx
0x140131ac1  lea     r9, [r14+48h]
0x140131ac5  lea     r8, [r14+58h]
0x140131ac9  lea     rdx, aShuttingDownRg; "Shutting down. rgId:%? rgName:%?"
0x140131ad0  lea     rcx, [rbp+4Fh+lpCriticalSection]
0x140131ad4  call    ??$DbgPrint@GU_GUID@@V?$FrsStringImpl@GD@@@dbgobj@@QEAA_KPEBGAEBU_GUID@@AEBV?$FrsStringImpl@GD@@@Z; dbgobj::DbgPrint<ushort,_GUID,FrsStringImpl<ushort,char>>(ushort const *,_GUID const &,FrsStringImpl<ushort,char> const &)
0x140131ad9  call    cs:__imp_GetCurrentThreadId
0x140131ae0  nop     dword ptr [rax+rax+00h]
0x140131ae5  mov     [rsp+40h], rsi
0x140131aea  mov     dword ptr [rsp+100h+var_C8], eax
0x140131aee  mov     [rsp+100h+var_D0], 187h
0x140131af6  lea     rax, aReplicasetmana_3; "ReplicaSetManager::EstablishConnection"
0x140131afd  mov     qword ptr [rsp+100h+var_D8], rax
0x140131b02  lea     rax, aBaseFsRemotefs_76; "base\\fs\\remotefs\\frs\\src\\sync\\rep"...
0x140131b09  mov     [rsp+100h+var_E0], rax
0x140131b0e  mov     r9d, r13d
0x140131b11  xor     r8d, r8d
0x140131b14  mov     edx, 2349h
0x140131b19  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140131b1e  mov     rdi, rax
0x140131b21  test    rax, rax
0x140131b24  jnz     loc_1401321D1
0x140131b2a  lea     rcx, aReplicasetmana_8; "ReplicaSetManager::EstablishConnection"
0x140131b31  lea     rdx, aRsmg; "RSMG"
0x140131b38  test    rbx, rbx
0x140131b3b  jnz     loc_140131BD7
0x140131b41  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140131b48  test    rax, rax
0x140131b4b  jz      short loc_140131B86
0x140131b4d  cmp     [rax+40h], esi
0x140131b50  jz      short loc_140131B86
0x140131b52  cmp     dword ptr [rax+38h], 5
0x140131b56  jl      short loc_140131B86
0x140131b58  mov     [rbp+4Fh+lpCriticalSection], rcx
0x140131b5c  mov     [rbp+4Fh+var_A8], 18Bh
0x140131b63  mov     [rbp+4Fh+var_A4], 5
0x140131b6a  mov     [rbp+4Fh+var_A0], rdx
0x140131b6e  lea     r9, [r14+48h]
0x140131b72  lea     r8, [r14+58h]
0x140131b76  lea     rdx, aReplicationGro_5; "Replication group does not exist. rgId:"...
0x140131b7d  lea     rcx, [rbp+4Fh+lpCriticalSection]
0x140131b81  call    ??$DbgPrint@GU_GUID@@V?$FrsStringImpl@GD@@@dbgobj@@QEAA_KPEBGAEBU_GUID@@AEBV?$FrsStringImpl@GD@@@Z; dbgobj::DbgPrint<ushort,_GUID,FrsStringImpl<ushort,char>>(ushort const *,_GUID const &,FrsStringImpl<ushort,char> const &)
0x140131b86  call    cs:__imp_GetCurrentThreadId
0x140131b8d  nop     dword ptr [rax+rax+00h]
0x140131b92  mov     [rsp+40h], rsi
0x140131b97  mov     dword ptr [rsp+100h+var_C8], eax
0x140131b9b  mov     [rsp+100h+var_D0], 18Ch
0x140131ba3  lea     rax, aReplicasetmana_3; "ReplicaSetManager::EstablishConnection"
0x140131baa  mov     qword ptr [rsp+100h+var_D8], rax
0x140131baf  lea     rax, aBaseFsRemotefs_76; "base\\fs\\remotefs\\frs\\src\\sync\\rep"...
0x140131bb6  mov     [rsp+100h+var_E0], rax
0x140131bbb  mov     r9d, r13d
0x140131bbe  xor     r8d, r8d
0x140131bc1  mov     edx, 2361h
0x140131bc6  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140131bcb  mov     rdi, rax
0x140131bce  test    rax, rax
0x140131bd1  jnz     loc_1401321D1
0x140131bd7  lea     rcx, [rbx+388h]; this
0x140131bde  xor     r8d, r8d; unsigned int
0x140131be1  lea     rdx, [r14+20h]; struct _GUID *
0x140131be5  call    ?Find@ConnectionList@Config@@QEBAPEAVConnection@2@PEBU_GUID@@K@Z; Config::ConnectionList::Find(_GUID const *,ulong)
0x140131bea  mov     r12, rax
0x140131bed  test    rax, rax
0x140131bf0  jnz     loc_140131CA3
0x140131bf6  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140131bfd  test    rcx, rcx
0x140131c00  jz      short loc_140131C50
0x140131c02  cmp     [rcx+40h], esi
0x140131c05  jz      short loc_140131C50
0x140131c07  cmp     [rcx+38h], r13d
0x140131c0b  jl      short loc_140131C50
0x140131c0d  lea     rax, aReplicasetmana_8; "ReplicaSetManager::EstablishConnection"
0x140131c14  mov     [rbp+4Fh+lpCriticalSection], rax
0x140131c18  mov     [rbp+4Fh+var_A8], 192h
0x140131c1f  mov     [rbp+4Fh+var_A4], r13d
0x140131c23  lea     rax, aRsmg; "RSMG"
0x140131c2a  mov     [rbp+4Fh+var_A0], rax
0x140131c2e  lea     rax, [r14+48h]
0x140131c32  lea     rcx, [r14+58h]
0x140131c36  mov     qword ptr [rsp+100h+var_D8], rax
0x140131c3b  mov     [rsp+100h+var_E0], rcx
0x140131c40  lea     r9, [r14+20h]
0x140131c44  mov     r8, r15
0x140131c47  lea     rcx, [rbp+4Fh+lpCriticalSection]
0x140131c4b  call    ??$DbgPrint@GU_GUID@@U1@U1@V?$FrsStringImpl@GD@@@dbgobj@@QEAA_KPEBGAEBU_GUID@@11AEBV?$FrsStringImpl@GD@@@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID,_GUID,FrsStringImpl<ushort,char>>(ushort const *,_GUID const &,_GUID const &,_GUID const &,FrsStringImpl<ushort,char> const &)
0x140131c50  call    cs:__imp_GetCurrentThreadId
0x140131c57  nop     dword ptr [rax+rax+00h]
0x140131c5c  mov     [rsp+40h], rsi
0x140131c61  mov     dword ptr [rsp+100h+var_C8], eax
0x140131c65  mov     [rsp+100h+var_D0], 197h
0x140131c6d  lea     rbx, aReplicasetmana_3; "ReplicaSetManager::EstablishConnection"
0x140131c74  mov     qword ptr [rsp+100h+var_D8], rbx
0x140131c79  lea     rax, aBaseFsRemotefs_76; "base\\fs\\remotefs\\frs\\src\\sync\\rep"...
0x140131c80  mov     [rsp+100h+var_E0], rax
0x140131c85  mov     r9d, r13d
0x140131c88  xor     r8d, r8d
0x140131c8b  mov     edx, 2360h
0x140131c90  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140131c95  mov     rdi, rax
0x140131c98  test    rax, rax
0x140131c9b  jnz     loc_1401321CD
0x140131ca1  jmp     short loc_140131CAA
0x140131ca3  lea     rbx, aReplicasetmana_3; "ReplicaSetManager::EstablishConnection"
0x140131caa  mov     rdx, r12; struct Member *
0x140131cad  lea     rcx, [rbp+4Fh+var_60]; this
0x140131cb1  call    ??0ScopedMemberConnectionList@Member@Config@@QEAA@PEBV12@@Z; Config::Member::ScopedMemberConnectionList::ScopedMemberConnectionList(Config::Member const *)
0x140131cb6  nop
0x140131cb7  mov     rcx, [rbp+4Fh+var_60]
0x140131cbb  add     rcx, 188h; this
0x140131cc2  xor     r8d, r8d; unsigned int
0x140131cc5  mov     rdx, r15; struct _GUID *
0x140131cc8  call    ?Find@ConnectionList@Config@@QEBAPEAVConnection@2@PEBU_GUID@@K@Z; Config::ConnectionList::Find(_GUID const *,ulong)
0x140131ccd  test    rax, rax
0x140131cd0  jnz     loc_140131D71
0x140131cd6  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140131cdd  test    rax, rax
0x140131ce0  jz      short loc_140131D2E
0x140131ce2  cmp     [rax+40h], esi
0x140131ce5  jz      short loc_140131D2E
0x140131ce7  cmp     [rax+38h], r13d
0x140131ceb  jl      short loc_140131D2E
0x140131ced  lea     rax, aReplicasetmana_8; "ReplicaSetManager::EstablishConnection"
0x140131cf4  mov     [rbp+4Fh+lpCriticalSection], rax
0x140131cf8  mov     [rbp+4Fh+var_A8], 1A0h
0x140131cff  mov     [rbp+4Fh+var_A4], r13d
0x140131d03  lea     rax, aRsmg; "RSMG"
0x140131d0a  mov     [rbp+4Fh+var_A0], rax
0x140131d0e  lea     rax, [r14+48h]
0x140131d12  lea     r9, [r14+58h]
0x140131d16  mov     [rsp+100h+var_E0], rax
0x140131d1b  mov     r8, r15
0x140131d1e  lea     rdx, aConnectionWasN; "Connection was not found in configurati"...
0x140131d25  lea     rcx, [rbp+4Fh+lpCriticalSection]
0x140131d29  call    ??$DbgPrint@GU_GUID@@U1@V?$FrsStringImpl@GD@@@dbgobj@@QEAA_KPEBGAEBU_GUID@@1AEBV?$FrsStringImpl@GD@@@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID,FrsStringImpl<ushort,char>>(ushort const *,_GUID const &,_GUID const &,FrsStringImpl<ushort,char> const &)
0x140131d2e  call    cs:__imp_GetCurrentThreadId
0x140131d35  nop     dword ptr [rax+rax+00h]
0x140131d3a  mov     [rsp+40h], rsi
0x140131d3f  mov     dword ptr [rsp+100h+var_C8], eax
0x140131d43  mov     [rsp+100h+var_D0], 1A4h
0x140131d4b  mov     qword ptr [rsp+100h+var_D8], rbx
0x140131d50  lea     r12, aBaseFsRemotefs_76; "base\\fs\\remotefs\\frs\\src\\sync\\rep"...
0x140131d57  mov     [rsp+100h+var_E0], r12
0x140131d5c  mov     r9d, r13d
0x140131d5f  xor     r8d, r8d
0x140131d62  mov     edx, 2342h
0x140131d67  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140131d6c  mov     rdi, rax
0x140131d6f  jmp     short loc_140131D78
0x140131d71  lea     r12, aBaseFsRemotefs_76; "base\\fs\\remotefs\\frs\\src\\sync\\rep"...
0x140131d78  lea     rcx, [rbp+4Fh+var_60]; this
0x140131d7c  call    ??1ScopedMemberConnectionList@Member@Config@@QEAA@XZ; Config::Member::ScopedMemberConnectionList::~ScopedMemberConnectionList(void)
0x140131d81  test    rdi, rdi
0x140131d84  jnz     loc_1401321CD
0x140131d8a  lea     rdx, [r14+108h]; struct ScopedCS *
0x140131d91  lea     rcx, [rbp+4Fh+lpCriticalSection]; this
0x140131d95  call    ??0ScopedLock@@QEAA@AEAVScopedCS@@@Z; ScopedLock::ScopedLock(ScopedCS &)
0x140131d9a  nop
0x140131d9b  cmp     [rbp+4Fh+arg_20], esi
0x140131d9e  jz      short loc_140131DB3
0x140131da0  lea     rcx, [r14+0F8h]
0x140131da7  mov     r8, r15
0x140131daa  lea     rdx, [rbp+4Fh+var_98]
0x140131dae  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U_GUID@@@std@@@std@@@std@@_N@1@AEBU_GUID@@@Z; std::_Tree<std::_Tset_traits<_GUID,std::less<_GUID>,std::allocator<_GUID>,0>>::insert<0,0>(_GUID const &)
0x140131db3  lea     rdi, [r14+0D8h]
0x140131dba  mov     r8, r15
0x140131dbd  lea     rdx, [rbp+4Fh+var_70]
0x140131dc1  mov     rcx, rdi
0x140131dc4  call    ?find@?$_Tree@V?$_Tmap_traits@VGuid@@U_SYSTEMTIME@@U?$less@VGuid@@@std@@V?$allocator@U?$pair@$$CBVGuid@@U_SYSTEMTIME@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVGuid@@U_SYSTEMTIME@@@std@@@std@@@std@@@2@AEBVGuid@@@Z; std::_Tree<std::_Tmap_traits<Guid,_SYSTEMTIME,std::less<Guid>,std::allocator<std::pair<Guid const,_SYSTEMTIME>>,0>>::find(Guid const &)
0x140131dc9  mov     r8, rax
0x140131dcc  lea     rdx, [rbp+4Fh+var_80]
0x140131dd0  mov     rcx, rdi
0x140131dd3  call    ?end@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@@std@@@3@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(void)
0x140131dd8  mov     rcx, [rax]
0x140131ddb  cmp     [r8], rcx
0x140131dde  jnz     loc_140131F83
0x140131de4  lea     r12, [r14+0C0h]
0x140131deb  mov     r13, r12
0x140131dee  lea     r8, [rbp+4Fh+arg_0]
0x140131df2  mov     rdx, r15
0x140131df5  mov     rcx, r12
0x140131df8  call    ?Find@?$RefMap@U_GUID@@VInConnectionContentSetContext@InConnection@@U?$less@U_GUID@@@std@@@@QEAAHAEBU_GUID@@AEAPEAVInConnectionContentSetContext@InConnection@@@Z; RefMap<_GUID,InConnection::InConnectionContentSetContext,std::less<_GUID>>::Find(_GUID const &,InConnection::InConnectionContentSetContext * &)
0x140131dfd  test    eax, eax
0x140131dff  jz      loc_140131FCD
0x140131e05  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140131e0c  test    rax, rax
0x140131e0f  jz      short loc_140131E60
0x140131e11  cmp     [rax+40h], esi
0x140131e14  jz      short loc_140131E60
0x140131e16  cmp     dword ptr [rax+38h], 3
0x140131e1a  jl      short loc_140131E60
0x140131e1c  lea     rax, aReplicasetmana_8; "ReplicaSetManager::EstablishConnection"
0x140131e23  mov     [rbp+4Fh+var_98], rax
0x140131e27  mov     [rbp+4Fh+var_90], 1C5h
0x140131e2e  mov     [rbp+4Fh+var_8C], 3
0x140131e35  lea     rax, aRsmg; "RSMG"
0x140131e3c  mov     [rbp+4Fh+var_88], rax
0x140131e40  lea     rax, [r14+48h]
0x140131e44  lea     r9, [r14+58h]
0x140131e48  mov     [rsp+100h+var_E0], rax
0x140131e4d  mov     r8, r15
0x140131e50  lea     rdx, aShuttingDownEx; "Shutting down existing connection. conn"...
0x140131e57  lea     rcx, [rbp+4Fh+var_98]
0x140131e5b  call    ??$DbgPrint@GU_GUID@@U1@V?$FrsStringImpl@GD@@@dbgobj@@QEAA_KPEBGAEBU_GUID@@1AEBV?$FrsStringImpl@GD@@@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID,FrsStringImpl<ushort,char>>(ushort const *,_GUID const &,_GUID const &,FrsStringImpl<ushort,char> const &)
0x140131e60  mov     r8, r15
0x140131e63  lea     rdx, [rbp+4Fh+var_98]
0x140131e67  mov     rcx, rdi
0x140131e6a  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U_GUID@@@std@@@std@@@std@@_N@1@AEBU_GUID@@@Z; std::_Tree<std::_Tset_traits<_GUID,std::less<_GUID>,std::allocator<_GUID>,0>>::insert<0,0>(_GUID const &)
0x140131e6f  mov     ebx, [rbp+4Fh+var_A8]
0x140131e72  dec     ebx
0x140131e74  mov     [rbp+4Fh+var_A8], ebx
0x140131e77  mov     rcx, [rbp+4Fh+lpCriticalSection]; lpCriticalSection
0x140131e7b  call    cs:__imp_LeaveCriticalSection
0x140131e82  nop     dword ptr [rax+rax+00h]
0x140131e87  mov     rcx, [rbp+4Fh+arg_0]; this
0x140131e8b  call    ?ShutdownOutConnection@OutConnection@@QEAAXXZ; OutConnection::ShutdownOutConnection(void)
0x140131e90  mov     rcx, [rbp+4Fh+lpCriticalSection]; lpCriticalSection
0x140131e94  call    cs:__imp_EnterCriticalSection
0x140131e9b  nop     dword ptr [rax+rax+00h]
0x140131ea0  lea     eax, [rbx+1]
0x140131ea3  mov     [rbp+4Fh+var_A8], eax
0x140131ea6  mov     rdx, r15
0x140131ea9  mov     rcx, rdi
0x140131eac  call    ?erase@?$_Tree@V?$_Tset_traits@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@$0A@@std@@@std@@QEAA_KAEBU_GUID@@@Z; std::_Tree<std::_Tset_traits<_GUID,std::less<_GUID>,std::allocator<_GUID>,0>>::erase(_GUID const &)
0x140131eb1  mov     rdx, r15
0x140131eb4  mov     rcx, r12
0x140131eb7  call    ?Delete@?$RefMap@U_GUID@@VReplicaSetManager@@U?$less@U_GUID@@@std@@@@QEAAXAEBU_GUID@@@Z; RefMap<_GUID,ReplicaSetManager,std::less<_GUID>>::Delete(_GUID const &)
0x140131ebc  xor     edx, edx
0x140131ebe  lea     rcx, [rbp+4Fh+arg_0]
0x140131ec2  call    ?Set@?$ScopedRef@VShutdownRestartTask@VolumeManager@@@@AEAAXPEAVShutdownRestartTask@VolumeManager@@@Z; ScopedRef<VolumeManager::ShutdownRestartTask>::Set(VolumeManager::ShutdownRestartTask *)
0x140131ec7  lea     r8, [rbp+4Fh+arg_0]
0x140131ecb  mov     rdx, r15
0x140131ece  mov     rcx, r12
0x140131ed1  call    ?Find@?$RefMap@U_GUID@@VInConnectionContentSetContext@InConnection@@U?$less@U_GUID@@@std@@@@QEAAHAEBU_GUID@@AEAPEAVInConnectionContentSetContext@InConnection@@@Z; RefMap<_GUID,InConnection::InConnectionContentSetContext,std::less<_GUID>>::Find(_GUID const &,InConnection::InConnectionContentSetContext * &)
0x140131ed6  test    eax, eax
0x140131ed8  jz      loc_140131FCD
0x140131ede  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140131ee5  test    rax, rax
0x140131ee8  jz      short loc_140131F39
0x140131eea  cmp     [rax+40h], esi
0x140131eed  jz      short loc_140131F39
0x140131eef  cmp     dword ptr [rax+38h], 3
0x140131ef3  jl      short loc_140131F39
0x140131ef5  lea     rax, aReplicasetmana_8; "ReplicaSetManager::EstablishConnection"
0x140131efc  mov     [rbp+4Fh+var_98], rax
0x140131f00  mov     [rbp+4Fh+var_90], 1D6h
0x140131f07  mov     [rbp+4Fh+var_8C], 3
0x140131f0e  lea     rax, aRsmg; "RSMG"
0x140131f15  mov     [rbp+4Fh+var_88], rax
0x140131f19  lea     rax, [r14+48h]
0x140131f1d  lea     r9, [r14+58h]
  ... truncated ...
```
