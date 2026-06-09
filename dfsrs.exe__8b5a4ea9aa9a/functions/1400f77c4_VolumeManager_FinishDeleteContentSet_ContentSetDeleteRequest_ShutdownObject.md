# VolumeManager::FinishDeleteContentSet(ContentSetDeleteRequest &,ShutdownObject &)

- ea: `0x1400f77c4`
- end: `0x1400f7ec1`
- name: `?FinishDeleteContentSet@VolumeManager@@QEAAPEAVFrsStatus@@AEAVContentSetDeleteRequest@@AEAVShutdownObject@@@Z`
- size: `1789`
- prototype: `struct FrsStatus *__fastcall(VolumeManager *__hidden this, struct ContentSetDeleteRequest *, struct ShutdownObject *)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140142c90`

## callees

- `0x1400036a0`
- `0x1400046cc`
- `0x14000d980`
- `0x14000daa0`
- `0x14000dcc0`
- `0x14000e34c`
- `0x140022d1c`
- `0x140024924`
- `0x140024c84`
- `0x14002bf70`
- `0x14002c1c0`
- `0x14002c404`
- `0x14003add4`
- `0x140047e14`
- `0x140058128`
- `0x1400727e8`
- `0x14007f9f4`
- `0x140086dcc`
- `0x1400923f8`
- `0x1400f1ce4`
- `0x1400f20a0`
- `0x1400f2b88`
- `0x1400f45b4`
- `0x1400f77c4`
- `0x14010f9f8`
- `0x1401b9494`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400f78cd`
- `KERNEL32!GetCurrentThreadId` at `0x1400f7960`
- `KERNEL32!GetCurrentThreadId` at `0x1400f79b6`
- `KERNEL32!GetCurrentThreadId` at `0x1400f7e39`
- `KERNEL32!GetCurrentThreadId` at `0x1400f78cd`
- `KERNEL32!GetCurrentThreadId` at `0x1400f7960`
- `KERNEL32!GetCurrentThreadId` at `0x1400f79b6`
- `KERNEL32!GetCurrentThreadId` at `0x1400f7e39`

## string_xrefs

- `0x1400f7839`: `VolumeManager::FinishDeleteContentSet`
- `0x1400f7bef`: `VolumeManager::FinishDeleteContentSet`
- `0x1400f797d`: `VolumeManager::FinishDeleteContentSet`
- `0x1400f79d3`: `VolumeManager::FinishDeleteContentSet`
- `0x1400f7e56`: `VolumeManager::FinishDeleteContentSet`
- `0x1400f78b6`: `Completing deletion of content set from DB. csId:%? csName:%? volId:%? volPath:%? volState:%?`
- `0x1400f7ae5`: `Deleting staging folder. csId:%? csName:%? volId:%? volPath:%? volState:%?`
- `0x1400f7c31`: `Failed to get version vector for csId:%? csName:%?. Error:%?`
- `0x1400f7b82`: `Deleting database records. csId:%? csName:%? volId:%? volPath:%? volState:%?`
- `0x1400f7c89`: `Version vector after deleting content set. csId:%? csName:%? vv:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
struct FrsStatus *__fastcall VolumeManager::FinishDeleteContentSet(
        VolumeManager *this,
        struct ContentSetDeleteRequest *a2,
        struct ShutdownObject *a3)
{
  __int64 v6; // rsi
  __int64 (__fastcall *v7)(VolumeManager *, struct DbManager **, _QWORD); // rbx
  DWORD CurrentThreadId; // eax
  struct FrsStatus *v9; // rbx
  DWORD v10; // eax
  __int64 v11; // rcx
  DWORD v12; // eax
  __int64 v13; // rcx
  struct DbManager *v14; // rdi
  __int64 (__fastcall *v15)(struct DbManager *, char *, __int64); // rbx
  __int64 v16; // rax
  struct Config::ContentSet *ContentSet; // rax
  __int64 v18; // rdx
  struct FrsStatus *v19; // rbx
  DWORD v20; // eax
  __int64 v21; // rcx
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  struct FrsStatus *v24; // [rsp+58h] [rbp-A8h] BYREF
  Config::Volume *v25; // [rsp+60h] [rbp-A0h] BYREF
  struct Db *v26; // [rsp+68h] [rbp-98h] BYREF
  const wchar_t *v27; // [rsp+70h] [rbp-90h] BYREF
  int v28; // [rsp+78h] [rbp-88h]
  int v29; // [rsp+7Ch] [rbp-84h]
  const wchar_t *v30; // [rsp+80h] [rbp-80h]
  int v31; // [rsp+88h] [rbp-78h] BYREF
  int v32; // [rsp+8Ch] [rbp-74h] BYREF
  const wchar_t *v33; // [rsp+90h] [rbp-70h] BYREF
  int v34; // [rsp+98h] [rbp-68h]
  int v35; // [rsp+9Ch] [rbp-64h]
  const wchar_t *v36; // [rsp+A0h] [rbp-60h]
  struct DbManager *v37[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v38; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v39[8]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v40[16]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v41[16]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v42; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v43; // [rsp+100h] [rbp+0h]
  struct _GUID v44; // [rsp+110h] [rbp+10h] BYREF
  union _LARGE_INTEGER v45; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v46[16]; // [rsp+148h] [rbp+48h] BYREF
  struct _FILETIME v47; // [rsp+158h] [rbp+58h] BYREF
  char v48; // [rsp+189h] [rbp+89h]
  _BYTE v49[720]; // [rsp+1A0h] [rbp+A0h] BYREF

  std::map<_GUID,LdbManager::VvCompactMan::VvInfo>::map<_GUID,LdbManager::VvCompactMan::VvInfo>(v40);
  *(_OWORD *)v37 = 0;
  memset_0(&v44, 0, 0x88u);
  ID_RECORD::ID_RECORD((ID_RECORD *)v49);
  v6 = 0;
  v31 = 0;
  v32 = 0;
  v26 = 0;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v33 = L"VolumeManager::FinishDeleteContentSet";
    v34 = 1840;
    v35 = 4;
    v36 = L"VLMG";
    v23 = *((_DWORD *)this + 108);
    v25 = (Config::Volume *)(*((_QWORD *)this + 22) + 18LL);
    dbgobj::DbgPrint<unsigned short,_GUID,FrsStringImpl<unsigned short,char>,_GUID,unsigned short const *,enum BaseVolumeManager::VOLUME_STATE>(
      (unsigned int)&v33,
      (unsigned int)L"Completing deletion of content set from DB. csId:%? csName:%? volId:%? volPath:%? volState:%?",
      (_DWORD)a2 + 8,
      (_DWORD)a2,
      (__int64)this + 184,
      (__int64)&v25,
      (__int64)&v23);
  }
  v7 = *(__int64 (__fastcall **)(VolumeManager *, struct DbManager **, _QWORD))(*(_QWORD *)this + 32LL);
  CurrentThreadId = GetCurrentThreadId();
  v9 = (struct FrsStatus *)v7(this, v37, CurrentThreadId);
  if ( !v9 )
  {
    (*(void (__fastcall **)(struct DbManager *, struct Db **))(*(_QWORD *)v37[0] + 48LL))(v37[0], &v26);
    v9 = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, __int64))(*(_QWORD *)v26 + 16LL))(v26, 1);
    if ( !v9 )
    {
      v9 = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, int *, char *, struct _GUID *))(*(_QWORD *)v26 + 80LL))(
                                 v26,
                                 &v31,
                                 (char *)a2 + 8,
                                 &v44);
      if ( !v9 )
      {
        if ( v31
          || (v10 = GetCurrentThreadId(),
              (v9 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                          v11,
                                          9097,
                                          0,
                                          3,
                                          "base\\fs\\remotefs\\frs\\src\\sync\\volumemanager.cpp",
                                          "VolumeManager::FinishDeleteContentSet",
                                          1869,
                                          v10,
                                          0)) == 0) )
        {
          if ( !v48 )
          {
            v12 = GetCurrentThreadId();
            v9 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                       v13,
                                       9097,
                                       0,
                                       3,
                                       "base\\fs\\remotefs\\frs\\src\\sync\\volumemanager.cpp",
                                       "VolumeManager::FinishDeleteContentSet",
                                       1874,
                                       v12,
                                       0);
          }
        }
      }
    }
  }
  if ( !v9 )
  {
    v42 = *(_OWORD *)((char *)a2 + 8);
    v43 = 1;
    v9 = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, int *, __int128 *, _BYTE *))(*(_QWORD *)v26 + 56LL))(
                               v26,
                               &v32,
                               &v42,
                               v49);
  }
  if ( v26 )
  {
    v9 = DbUtil::CommitTransaction(v26, v9, 0);
    (*(void (__fastcall **)(struct DbManager *, struct Db **))(*(_QWORD *)v37[0] + 64LL))(v37[0], &v26);
  }
  if ( v9 )
    goto LABEL_48;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v33 = L"VolumeManager::FinishDeleteContentSet";
    v34 = 1902;
    v35 = 5;
    v36 = L"VLMG";
    v23 = *((_DWORD *)this + 108);
    v25 = (Config::Volume *)(*((_QWORD *)this + 22) + 18LL);
    dbgobj::DbgPrint<unsigned short,_GUID,FrsStringImpl<unsigned short,char>,_GUID,unsigned short const *,enum BaseVolumeManager::VOLUME_STATE>(
      (unsigned int)&v33,
      (unsigned int)L"Deleting staging folder. csId:%? csName:%? volId:%? volPath:%? volState:%?",
      (_DWORD)a2 + 8,
      (_DWORD)a2,
      (__int64)this + 184,
      (__int64)&v25,
      (__int64)&v23);
  }
  ContentSetManager::DeleteStageFolder(&v44, &v45, (const struct FileId *)v46, &v47);
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v27 = L"VolumeManager::FinishDeleteContentSet";
    v28 = 1922;
    v29 = 5;
    v30 = L"VLMG";
    v23 = *((_DWORD *)this + 108);
    v25 = (Config::Volume *)(*((_QWORD *)this + 22) + 18LL);
    dbgobj::DbgPrint<unsigned short,_GUID,FrsStringImpl<unsigned short,char>,_GUID,unsigned short const *,enum BaseVolumeManager::VOLUME_STATE>(
      (unsigned int)&v27,
      (unsigned int)L"Deleting database records. csId:%? csName:%? volId:%? volPath:%? volState:%?",
      (_DWORD)a2 + 8,
      (_DWORD)a2,
      (__int64)this + 184,
      (__int64)&v25,
      (__int64)&v23);
  }
  v14 = v37[0];
  v15 = *(__int64 (__fastcall **)(struct DbManager *, char *, __int64))(*(_QWORD *)v37[0] + 24LL);
  v16 = (*(__int64 (__fastcall **)(struct ShutdownObject *))(*(_QWORD *)a3 + 40LL))(a3);
  v9 = (struct FrsStatus *)v15(v14, (char *)a2 + 8, v16);
  if ( v9 )
    goto LABEL_48;
  v9 = DbUtil::VersionVector(v37[0], (const struct _GUID *)((char *)a2 + 8), (struct VersionChainVector *)v40);
  v24 = v9;
  if ( v9 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v27 = L"VolumeManager::FinishDeleteContentSet";
      v28 = 1939;
      v29 = 5;
      v30 = L"VLMG";
      dbgobj::DbgPrint<unsigned short,_GUID,FrsStringImpl<unsigned short,char>,FrsStatus>(
        (unsigned int)&v27,
        (unsigned int)L"Failed to get version vector for csId:%? csName:%?. Error:%?",
        (_DWORD)a2 + 8,
        (_DWORD)a2,
        (__int64)v9);
    }
    CLEAR_ERROR(&v24);
    v9 = v24;
  }
  else if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v27 = L"VolumeManager::FinishDeleteContentSet";
    v28 = 1946;
    v29 = 5;
    v30 = L"VLMG";
    dbgobj::DbgPrint<unsigned short,_GUID,FrsStringImpl<unsigned short,char>,VersionChainVector>(
      (unsigned int)&v27,
      (unsigned int)L"Version vector after deleting content set. csId:%? csName:%? vv:%?",
      (_DWORD)a2 + 8,
      (_DWORD)a2,
      (__int64)v40);
  }
  if ( v9 )
  {
LABEL_48:
    v20 = GetCurrentThreadId();
    v6 = FrsStatusList::PushNewError(
           v21,
           *((unsigned int *)v9 + 1),
           *((unsigned int *)v9 + 2),
           *(unsigned int *)v9,
           "base\\fs\\remotefs\\frs\\src\\sync\\volumemanager.cpp",
           "VolumeManager::FinishDeleteContentSet",
           2007,
           v20,
           v9);
  }
  else
  {
    ScopedCrewLock::ScopedCrewLock(v39, (char *)this + 1480);
    ScopedLock::ScopedLock((ScopedLock *)v41, (VolumeManager *)((char *)this + 592));
    v24 = 0;
    v25 = 0;
    v25 = (Config::Volume *)Config::ConfigInstance<Config::ContentSet>::Get((char *)this + 232);
    ContentSet = Config::Volume::FindContentSet(v25, (const struct _GUID *)((char *)a2 + 8), 0);
    ScopedRef<Config::ContentSet>::Set(&v24, ContentSet);
    if ( v24
      && (unsigned int)Config::BoolParam::Get((struct FrsStatus *)((char *)v24 + 1120))
      && *(_DWORD *)(v18 + 1604)
      && *((_DWORD *)this + 108) == 3 )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v27 = L"VolumeManager::FinishDeleteContentSet";
        v28 = 1982;
        v29 = 4;
        v30 = L"VLMG";
        v23 = *((_DWORD *)this + 108);
        v38 = *((_QWORD *)this + 22) + 18LL;
        v19 = v24;
        dbgobj::DbgPrint<unsigned short,Config::GuidParam,Config::StringParam,Config::PathParam,_GUID,unsigned short const *,enum BaseVolumeManager::VOLUME_STATE>(
          (unsigned int)&v27,
          (unsigned int)&v38,
          (_DWORD)v24 + 112,
          (_DWORD)v24 + 240,
          (__int64)v24 + 576,
          (__int64)this + 184,
          (__int64)&v38,
          (__int64)&v23);
      }
      else
      {
        v19 = v24;
      }
      VolumeManager::AddContentSet(this, v19);
    }
    ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v25);
    ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v24);
    ScopedLock::~ScopedLock((ScopedLock *)v41);
    ScopedCrewLock::~ScopedCrewLock((ScopedCrewLock *)v39);
  }
  DbManagerInstance::FinalizeDbManagerInstance((DbManagerInstance *)v37);
  std::_Tree<std::_Tmap_traits<Guid,IntervalSet,std::less<Guid>,std::allocator<std::pair<Guid const,IntervalSet>>,0>>::~_Tree<std::_Tmap_traits<Guid,IntervalSet,std::less<Guid>,std::allocator<std::pair<Guid const,IntervalSet>>,0>>(v40);
  return (struct FrsStatus *)v6;
}

```

## disassembly

```asm
0x1400f77c4  mov     [rsp-8+arg_18], rbx
0x1400f77c9  push    rbp
0x1400f77ca  push    rsi
0x1400f77cb  push    rdi
0x1400f77cc  push    r12
0x1400f77ce  push    r13
0x1400f77d0  push    r14
0x1400f77d2  push    r15
0x1400f77d4  lea     rbp, [rsp-380h]
0x1400f77dc  sub     rsp, 480h
0x1400f77e3  mov     rax, cs:__security_cookie
0x1400f77ea  xor     rax, rsp
0x1400f77ed  mov     [rbp+3B0h+var_40], rax
0x1400f77f4  mov     r12, r8
0x1400f77f7  mov     r15, rdx
0x1400f77fa  mov     r14, rcx
0x1400f77fd  lea     rcx, [rbp+3B0h+var_3E0]
0x1400f7801  call    ??0?$map@U_GUID@@VVvInfo@VvCompactMan@LdbManager@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@VVvInfo@VvCompactMan@LdbManager@@@std@@@6@@std@@QEAA@XZ; std::map<_GUID,LdbManager::VvCompactMan::VvInfo>::map<_GUID,LdbManager::VvCompactMan::VvInfo>(void)
0x1400f7806  nop
0x1400f7807  xorps   xmm0, xmm0
0x1400f780a  movdqu  xmmword ptr [rbp+3B0h+var_408], xmm0
0x1400f780f  xor     edx, edx; Val
0x1400f7811  mov     r8d, 88h; Size
0x1400f7817  lea     rcx, [rbp+3B0h+var_3A0]; void *
0x1400f781b  call    memset_0
0x1400f7820  lea     rcx, [rbp+3B0h+var_310]; this
0x1400f7827  call    ??0ID_RECORD@@QEAA@XZ; ID_RECORD::ID_RECORD(void)
0x1400f782c  xor     esi, esi
0x1400f782e  mov     [rbp+3B0h+var_428], esi
0x1400f7831  mov     [rbp+3B0h+var_424], esi
0x1400f7834  mov     [rsp+4B0h+var_448], rsi
0x1400f7839  lea     rdi, aVolumemanagerF_1; "VolumeManager::FinishDeleteContentSet"
0x1400f7840  lea     rcx, aVlmg; "VLMG"
0x1400f7847  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400f784e  test    rax, rax
0x1400f7851  jz      short loc_1400F78C6
0x1400f7853  cmp     [rax+40h], esi
0x1400f7856  jz      short loc_1400F78C6
0x1400f7858  cmp     dword ptr [rax+38h], 4
0x1400f785c  jl      short loc_1400F78C6
0x1400f785e  mov     [rbp+3B0h+var_420], rdi
0x1400f7862  mov     [rbp+3B0h+var_418], 730h
0x1400f7869  mov     [rbp+3B0h+var_414], 4
0x1400f7870  mov     [rbp+3B0h+var_410], rcx
0x1400f7874  mov     eax, [r14+1B0h]
0x1400f787b  mov     [rsp+4B0h+var_460], eax
0x1400f787f  mov     rax, [r14+0B0h]
0x1400f7886  add     rax, 12h
0x1400f788a  mov     [rsp+4B0h+var_450], rax
0x1400f788f  lea     rax, [r14+0B8h]
0x1400f7896  lea     r8, [r15+8]
0x1400f789a  lea     rcx, [rsp+4B0h+var_460]
0x1400f789f  mov     [rsp+4B0h+var_480], rcx
0x1400f78a4  lea     rcx, [rsp+4B0h+var_450]
0x1400f78a9  mov     [rsp+4B0h+var_488], rcx
0x1400f78ae  mov     [rsp+4B0h+var_490], rax
0x1400f78b3  mov     r9, r15
0x1400f78b6  lea     rdx, aCompletingDele; "Completing deletion of content set from"...
0x1400f78bd  lea     rcx, [rbp+3B0h+var_420]
0x1400f78c1  call    ??$DbgPrint@GU_GUID@@V?$FrsStringImpl@GD@@U1@PEBGW4VOLUME_STATE@BaseVolumeManager@@@dbgobj@@QEAA_KPEBGAEBU_GUID@@AEBV?$FrsStringImpl@GD@@1AEBQEBGAEBW4VOLUME_STATE@BaseVolumeManager@@@Z; dbgobj::DbgPrint<ushort,_GUID,FrsStringImpl<ushort,char>,_GUID,ushort const *,BaseVolumeManager::VOLUME_STATE>(ushort const *,_GUID const &,FrsStringImpl<ushort,char> const &,_GUID const &,ushort const * const &,BaseVolumeManager::VOLUME_STATE const &)
0x1400f78c6  mov     rax, [r14]
0x1400f78c9  mov     rbx, [rax+20h]
0x1400f78cd  call    cs:__imp_GetCurrentThreadId
0x1400f78d4  nop     dword ptr [rax+rax+00h]
0x1400f78d9  mov     r8d, eax
0x1400f78dc  lea     rdx, [rbp+3B0h+var_408]
0x1400f78e0  mov     rcx, r14
0x1400f78e3  mov     rax, rbx
0x1400f78e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f78eb  mov     rbx, rax
0x1400f78ee  test    rax, rax
0x1400f78f1  jnz     loc_1400F79FE
0x1400f78f7  mov     rcx, [rbp+3B0h+var_408]
0x1400f78fb  mov     rax, [rcx]
0x1400f78fe  lea     rdx, [rsp+4B0h+var_448]
0x1400f7903  mov     rax, [rax+30h]
0x1400f7907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f790c  mov     rcx, [rsp+4B0h+var_448]
0x1400f7911  mov     rax, [rcx]
0x1400f7914  lea     edx, [rbx+1]
0x1400f7917  mov     rax, [rax+10h]
0x1400f791b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f7920  mov     rbx, rax
0x1400f7923  test    rax, rax
0x1400f7926  jnz     loc_1400F79FE
0x1400f792c  mov     rcx, [rsp+4B0h+var_448]
0x1400f7931  mov     rax, [rcx]
0x1400f7934  lea     r8, [r15+8]
0x1400f7938  lea     r9, [rbp+3B0h+var_3A0]
0x1400f793c  lea     rdx, [rbp+3B0h+var_428]
0x1400f7940  mov     rax, [rax+50h]
0x1400f7944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f7949  mov     rbx, rax
0x1400f794c  mov     r13d, 3
0x1400f7952  test    rax, rax
0x1400f7955  jnz     loc_1400F79FE
0x1400f795b  cmp     [rbp+3B0h+var_428], esi
0x1400f795e  jnz     short loc_1400F79AD
0x1400f7960  call    cs:__imp_GetCurrentThreadId
0x1400f7967  nop     dword ptr [rax+rax+00h]
0x1400f796c  mov     [rsp+4B0h+var_470], rsi
0x1400f7971  mov     dword ptr [rsp+4B0h+var_478], eax
0x1400f7975  mov     dword ptr [rsp+4B0h+var_480], 74Dh
0x1400f797d  lea     rax, aVolumemanagerF_3; "VolumeManager::FinishDeleteContentSet"
0x1400f7984  mov     [rsp+4B0h+var_488], rax
0x1400f7989  lea     rax, aBaseFsRemotefs_105; "base\\fs\\remotefs\\frs\\src\\sync\\vol"...
0x1400f7990  mov     [rsp+4B0h+var_490], rax
0x1400f7995  mov     r9d, r13d
0x1400f7998  xor     r8d, r8d
0x1400f799b  mov     edx, 2389h
0x1400f79a0  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400f79a5  mov     rbx, rax
0x1400f79a8  test    rax, rax
0x1400f79ab  jnz     short loc_1400F79FE
0x1400f79ad  cmp     [rbp+3B0h+var_327], sil
0x1400f79b4  jnz     short loc_1400F79FE
0x1400f79b6  call    cs:__imp_GetCurrentThreadId
0x1400f79bd  nop     dword ptr [rax+rax+00h]
0x1400f79c2  mov     [rsp+4B0h+var_470], rsi
0x1400f79c7  mov     dword ptr [rsp+4B0h+var_478], eax
0x1400f79cb  mov     dword ptr [rsp+4B0h+var_480], 752h
0x1400f79d3  lea     rax, aVolumemanagerF_3; "VolumeManager::FinishDeleteContentSet"
0x1400f79da  mov     [rsp+4B0h+var_488], rax
0x1400f79df  lea     rax, aBaseFsRemotefs_105; "base\\fs\\remotefs\\frs\\src\\sync\\vol"...
0x1400f79e6  mov     [rsp+4B0h+var_490], rax
0x1400f79eb  mov     r9d, r13d
0x1400f79ee  xor     r8d, r8d
0x1400f79f1  mov     edx, 2389h
0x1400f79f6  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400f79fb  mov     rbx, rax
0x1400f79fe  test    rbx, rbx
0x1400f7a01  jnz     short loc_1400F7A38
0x1400f7a03  movups  xmm0, xmmword ptr [r15+8]
0x1400f7a08  movdqu  [rbp+3B0h+var_3C0], xmm0
0x1400f7a0d  mov     [rbp+3B0h+var_3B0], 1
0x1400f7a15  mov     rcx, [rsp+4B0h+var_448]
0x1400f7a1a  mov     rax, [rcx]
0x1400f7a1d  lea     r9, [rbp+3B0h+var_310]
0x1400f7a24  lea     r8, [rbp+3B0h+var_3C0]
0x1400f7a28  lea     rdx, [rbp+3B0h+var_424]
0x1400f7a2c  mov     rax, [rax+38h]
0x1400f7a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f7a35  mov     rbx, rax
0x1400f7a38  mov     rcx, [rsp+4B0h+var_448]; struct Db *
0x1400f7a3d  test    rcx, rcx
0x1400f7a40  jz      short loc_1400F7A65
0x1400f7a42  xor     r8d, r8d; int
0x1400f7a45  mov     rdx, rbx; struct FrsStatus *
0x1400f7a48  call    ?CommitTransaction@DbUtil@@SAPEAVFrsStatus@@PEAVDb@@PEAV2@H@Z; DbUtil::CommitTransaction(Db *,FrsStatus *,int)
0x1400f7a4d  mov     rbx, rax
0x1400f7a50  mov     rcx, [rbp+3B0h+var_408]
0x1400f7a54  mov     rax, [rcx]
0x1400f7a57  lea     rdx, [rsp+4B0h+var_448]
0x1400f7a5c  mov     rax, [rax+40h]
0x1400f7a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f7a65  test    rbx, rbx
0x1400f7a68  jnz     loc_1400F7E39
0x1400f7a6e  lea     r13d, [rbx+5]
0x1400f7a72  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400f7a79  test    rax, rax
0x1400f7a7c  jz      short loc_1400F7AF7
0x1400f7a7e  cmp     [rax+40h], esi
0x1400f7a81  jz      short loc_1400F7AF7
0x1400f7a83  lea     rbx, aVlmg; "VLMG"
0x1400f7a8a  cmp     [rax+38h], r13d
0x1400f7a8e  jl      short loc_1400F7AFE
0x1400f7a90  mov     [rbp+3B0h+var_420], rdi
0x1400f7a94  mov     [rbp+3B0h+var_418], 76Eh
0x1400f7a9b  mov     [rbp+3B0h+var_414], r13d
0x1400f7a9f  mov     [rbp+3B0h+var_410], rbx
0x1400f7aa3  mov     eax, [r14+1B0h]
0x1400f7aaa  mov     [rsp+4B0h+var_460], eax
0x1400f7aae  mov     rax, [r14+0B0h]
0x1400f7ab5  add     rax, 12h
0x1400f7ab9  mov     [rsp+4B0h+var_450], rax
0x1400f7abe  lea     rax, [r14+0B8h]
0x1400f7ac5  lea     r8, [r15+8]
0x1400f7ac9  lea     rcx, [rsp+4B0h+var_460]
0x1400f7ace  mov     [rsp+4B0h+var_480], rcx
0x1400f7ad3  lea     rcx, [rsp+4B0h+var_450]
0x1400f7ad8  mov     [rsp+4B0h+var_488], rcx
0x1400f7add  mov     [rsp+4B0h+var_490], rax
0x1400f7ae2  mov     r9, r15
0x1400f7ae5  lea     rdx, aDeletingStagin; "Deleting staging folder. csId:%? csName"...
0x1400f7aec  lea     rcx, [rbp+3B0h+var_420]
0x1400f7af0  call    ??$DbgPrint@GU_GUID@@V?$FrsStringImpl@GD@@U1@PEBGW4VOLUME_STATE@BaseVolumeManager@@@dbgobj@@QEAA_KPEBGAEBU_GUID@@AEBV?$FrsStringImpl@GD@@1AEBQEBGAEBW4VOLUME_STATE@BaseVolumeManager@@@Z; dbgobj::DbgPrint<ushort,_GUID,FrsStringImpl<ushort,char>,_GUID,ushort const *,BaseVolumeManager::VOLUME_STATE>(ushort const *,_GUID const &,FrsStringImpl<ushort,char> const &,_GUID const &,ushort const * const &,BaseVolumeManager::VOLUME_STATE const &)
0x1400f7af5  jmp     short loc_1400F7AFE
0x1400f7af7  lea     rbx, aVlmg; "VLMG"
0x1400f7afe  lea     r9, [rbp+3B0h+var_358]; struct _FILETIME *
0x1400f7b02  lea     r8, [rbp+3B0h+var_368]; struct FileId *
0x1400f7b06  lea     rdx, [rbp+3B0h+var_370]; union _LARGE_INTEGER *
0x1400f7b0a  lea     rcx, [rbp+3B0h+var_3A0]; struct _GUID *
0x1400f7b0e  call    ?DeleteStageFolder@ContentSetManager@@SAXAEBU_GUID@@AEBT_LARGE_INTEGER@@AEBVFileId@@AEBU_FILETIME@@@Z; ContentSetManager::DeleteStageFolder(_GUID const &,_LARGE_INTEGER const &,FileId const &,_FILETIME const &)
0x1400f7b13  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400f7b1a  test    rax, rax
0x1400f7b1d  jz      short loc_1400F7B93
0x1400f7b1f  cmp     [rax+40h], esi
0x1400f7b22  jz      short loc_1400F7B93
0x1400f7b24  cmp     [rax+38h], r13d
0x1400f7b28  jl      short loc_1400F7B93
0x1400f7b2a  mov     [rsp+4B0h+var_440], rdi
0x1400f7b2f  mov     [rsp+4B0h+var_438], 782h
0x1400f7b37  mov     [rsp+4B0h+var_434], r13d
0x1400f7b3c  mov     [rbp+3B0h+var_430], rbx
0x1400f7b40  mov     eax, [r14+1B0h]
0x1400f7b47  mov     [rsp+4B0h+var_460], eax
0x1400f7b4b  mov     rax, [r14+0B0h]
0x1400f7b52  add     rax, 12h
0x1400f7b56  mov     [rsp+4B0h+var_450], rax
0x1400f7b5b  lea     rax, [r14+0B8h]
0x1400f7b62  lea     r8, [r15+8]
0x1400f7b66  lea     rcx, [rsp+4B0h+var_460]
0x1400f7b6b  mov     [rsp+4B0h+var_480], rcx
0x1400f7b70  lea     rcx, [rsp+4B0h+var_450]
0x1400f7b75  mov     [rsp+4B0h+var_488], rcx
0x1400f7b7a  mov     [rsp+4B0h+var_490], rax
0x1400f7b7f  mov     r9, r15
0x1400f7b82  lea     rdx, aDeletingDataba_0; "Deleting database records. csId:%? csNa"...
0x1400f7b89  lea     rcx, [rsp+4B0h+var_440]
0x1400f7b8e  call    ??$DbgPrint@GU_GUID@@V?$FrsStringImpl@GD@@U1@PEBGW4VOLUME_STATE@BaseVolumeManager@@@dbgobj@@QEAA_KPEBGAEBU_GUID@@AEBV?$FrsStringImpl@GD@@1AEBQEBGAEBW4VOLUME_STATE@BaseVolumeManager@@@Z; dbgobj::DbgPrint<ushort,_GUID,FrsStringImpl<ushort,char>,_GUID,ushort const *,BaseVolumeManager::VOLUME_STATE>(ushort const *,_GUID const &,FrsStringImpl<ushort,char> const &,_GUID const &,ushort const * const &,BaseVolumeManager::VOLUME_STATE const &)
0x1400f7b93  mov     rdi, [rbp+3B0h+var_408]
0x1400f7b97  mov     rax, [rdi]
0x1400f7b9a  mov     rbx, [rax+18h]
0x1400f7b9e  mov     rcx, [r12]
0x1400f7ba2  mov     rax, [rcx+28h]
0x1400f7ba6  mov     rcx, r12
0x1400f7ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f7bae  mov     r8, rax
0x1400f7bb1  lea     rdx, [r15+8]
0x1400f7bb5  mov     rcx, rdi
0x1400f7bb8  mov     rax, rbx
0x1400f7bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f7bc0  mov     rbx, rax
0x1400f7bc3  test    rax, rax
0x1400f7bc6  jnz     loc_1400F7E39
0x1400f7bcc  lea     r8, [rbp+3B0h+var_3E0]; struct VersionChainVector *
0x1400f7bd0  lea     rdx, [r15+8]; struct _GUID *
0x1400f7bd4  mov     rcx, [rbp+3B0h+var_408]; struct DbManager *
0x1400f7bd8  call    ?VersionVector@DbUtil@@SAPEAVFrsStatus@@PEAVDbManager@@AEBU_GUID@@AEAVVersionChainVector@@@Z; DbUtil::VersionVector(DbManager *,_GUID const &,VersionChainVector &)
0x1400f7bdd  mov     rbx, rax
0x1400f7be0  mov     [rsp+4B0h+var_458], rax
0x1400f7be5  test    rax, rax
0x1400f7be8  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400f7bef  lea     rdi, aVolumemanagerF_1; "VolumeManager::FinishDeleteContentSet"
0x1400f7bf6  lea     r12, aVlmg; "VLMG"
0x1400f7bfd  jz      short loc_1400F7C53
0x1400f7bff  test    rax, rax
0x1400f7c02  jz      short loc_1400F7C42
0x1400f7c04  cmp     [rax+40h], esi
0x1400f7c07  jz      short loc_1400F7C42
0x1400f7c09  cmp     [rax+38h], r13d
0x1400f7c0d  jl      short loc_1400F7C42
0x1400f7c0f  mov     [rsp+4B0h+var_440], rdi
0x1400f7c14  mov     [rsp+4B0h+var_438], 793h
0x1400f7c1c  mov     [rsp+4B0h+var_434], r13d
0x1400f7c21  mov     [rbp+3B0h+var_430], r12
0x1400f7c25  lea     r8, [r15+8]
0x1400f7c29  mov     [rsp+4B0h+var_490], rbx
0x1400f7c2e  mov     r9, r15
0x1400f7c31  lea     rdx, aFailedToGetVer; "Failed to get version vector for csId:%"...
0x1400f7c38  lea     rcx, [rsp+4B0h+var_440]
0x1400f7c3d  call    ??$DbgPrint@GU_GUID@@V?$FrsStringImpl@GD@@VFrsStatus@@@dbgobj@@QEAA_KPEBGAEBU_GUID@@AEBV?$FrsStringImpl@GD@@AEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,_GUID,FrsStringImpl<ushort,char>,FrsStatus>(ushort const *,_GUID const &,FrsStringImpl<ushort,char> const &,FrsStatus const &)
0x1400f7c42  lea     rcx, [rsp+4B0h+var_458]; struct FrsStatus **
0x1400f7c47  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1400f7c4c  mov     rbx, [rsp+4B0h+var_458]
0x1400f7c51  jmp     short loc_1400F7C9A
0x1400f7c53  test    rax, rax
0x1400f7c56  jz      short loc_1400F7C9A
0x1400f7c58  cmp     [rax+40h], esi
0x1400f7c5b  jz      short loc_1400F7C9A
0x1400f7c5d  cmp     [rax+38h], r13d
0x1400f7c61  jl      short loc_1400F7C9A
0x1400f7c63  mov     [rsp+4B0h+var_440], rdi
0x1400f7c68  mov     [rsp+4B0h+var_438], 79Ah
0x1400f7c70  mov     [rsp+4B0h+var_434], r13d
0x1400f7c75  mov     [rbp+3B0h+var_430], r12
0x1400f7c79  lea     r8, [r15+8]
0x1400f7c7d  lea     rax, [rbp+3B0h+var_3E0]
0x1400f7c81  mov     [rsp+4B0h+var_490], rax
0x1400f7c86  mov     r9, r15
0x1400f7c89  lea     rdx, aVersionVectorA; "Version vector after deleting content s"...
0x1400f7c90  lea     rcx, [rsp+4B0h+var_440]
0x1400f7c95  call    ??$DbgPrint@GU_GUID@@V?$FrsStringImpl@GD@@VVersionChainVector@@@dbgobj@@QEAA_KPEBGAEBU_GUID@@AEBV?$FrsStringImpl@GD@@AEBVVersionChainVector@@@Z; dbgobj::DbgPrint<ushort,_GUID,FrsStringImpl<ushort,char>,VersionChainVector>(ushort const *,_GUID const &,FrsStringImpl<ushort,char> const &,VersionChainVector const &)
0x1400f7c9a  test    rbx, rbx
0x1400f7c9d  jnz     loc_1400F7E39
0x1400f7ca3  lea     rdx, [r14+5C8h]
0x1400f7caa  lea     rcx, [rbp+3B0h+var_3E8]
0x1400f7cae  call    ??0ScopedCrewLock@@QEAA@AEAVCREWLock@@URead@0@@Z; ScopedCrewLock::ScopedCrewLock(CREWLock &,ScopedCrewLock::Read)
0x1400f7cb3  nop
0x1400f7cb4  lea     rdx, [r14+250h]; struct ScopedCS *
0x1400f7cbb  lea     rcx, [rbp+3B0h+var_3D0]; this
0x1400f7cbf  call    ??0ScopedLock@@QEAA@AEAVScopedCS@@@Z; ScopedLock::ScopedLock(ScopedCS &)
0x1400f7cc4  nop
0x1400f7cc5  mov     [rsp+4B0h+var_458], rsi
0x1400f7cca  mov     [rsp+4B0h+var_450], rsi
0x1400f7ccf  lea     rcx, [r14+0E8h]
0x1400f7cd6  call    ?Get@?$ConfigInstance@VContentSet@Config@@@Config@@QEAAPEAVContentSet@2@XZ; Config::ConfigInstance<Config::ContentSet>::Get(void)
0x1400f7cdb  mov     [rsp+4B0h+var_450], rax
0x1400f7ce0  lea     rdx, [r15+8]; struct _GUID *
0x1400f7ce4  xor     r8d, r8d; unsigned int
  ... truncated ...
```
