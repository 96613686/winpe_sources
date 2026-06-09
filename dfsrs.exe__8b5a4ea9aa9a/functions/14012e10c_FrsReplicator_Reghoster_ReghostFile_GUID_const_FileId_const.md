# FrsReplicator::Reghoster::ReghostFile(_GUID const &,FileId const &)

- ea: `0x14012e10c`
- end: `0x14012e6d7`
- name: `?ReghostFile@Reghoster@FrsReplicator@@QEAAPEAVFrsStatus@@AEBU_GUID@@AEBVFileId@@@Z`
- size: `1483`
- prototype: `struct FrsStatus *(FrsReplicator::Reghoster *__hidden this, const struct _GUID *, const struct FileId *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, service_task`

## callers

- `0x1400e363c`

## callees

- `0x1400036a0`
- `0x14000daa0`
- `0x14000dd10`
- `0x140022d1c`
- `0x14002c1c0`
- `0x14002c2f4`
- `0x1400370bc`
- `0x1400391c4`
- `0x140041500`
- `0x14006f224`
- `0x1400923f8`
- `0x1400dc69c`
- `0x1400f7530`
- `0x1401107b4`
- `0x140115844`
- `0x140115bb8`
- `0x140115e7c`
- `0x14012c754`
- `0x14012d478`
- `0x14012e10c`
- `0x1401b9494`
- `0x1401bda10`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14012e202`
- `KERNEL32!GetCurrentThreadId` at `0x14012e2b6`
- `KERNEL32!GetCurrentThreadId` at `0x14012e33e`
- `KERNEL32!GetCurrentThreadId` at `0x14012e3ab`
- `KERNEL32!GetCurrentThreadId` at `0x14012e422`
- `KERNEL32!GetCurrentThreadId` at `0x14012e471`
- `KERNEL32!GetCurrentThreadId` at `0x14012e4e8`
- `KERNEL32!GetCurrentThreadId` at `0x14012e512`
- `KERNEL32!GetCurrentThreadId` at `0x14012e554`
- `KERNEL32!GetCurrentThreadId` at `0x14012e63d`
- `KERNEL32!GetCurrentThreadId` at `0x14012e202`
- `KERNEL32!GetCurrentThreadId` at `0x14012e2b6`
- `KERNEL32!GetCurrentThreadId` at `0x14012e33e`
- `KERNEL32!GetCurrentThreadId` at `0x14012e3ab`
- `KERNEL32!GetCurrentThreadId` at `0x14012e422`
- `KERNEL32!GetCurrentThreadId` at `0x14012e471`
- `KERNEL32!GetCurrentThreadId` at `0x14012e4e8`
- `KERNEL32!GetCurrentThreadId` at `0x14012e512`
- `KERNEL32!GetCurrentThreadId` at `0x14012e554`
- `KERNEL32!GetCurrentThreadId` at `0x14012e63d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
struct FrsStatus *__fastcall FrsReplicator::Reghoster::ReghostFile(
        FrsReplicator::Reghoster *this,
        const struct _GUID *a2,
        const struct FileId *a3)
{
  __int64 v6; // rsi
  __int64 v7; // rdx
  int v8; // eax
  struct VolumeManager *v9; // rdi
  DWORD v10; // eax
  __int64 v11; // rcx
  struct FrsStatus *v12; // r14
  __int64 (__fastcall *v13)(struct VolumeManager *, __int128 *, _QWORD); // rbx
  DWORD CurrentThreadId; // eax
  __int64 v15; // rax
  ConfigContext *v16; // rcx
  DWORD v17; // eax
  __int64 v18; // rcx
  struct Config::ContentSet *ContentSet; // rax
  const struct _GUID *v20; // rbx
  DWORD v21; // eax
  __int64 v22; // rcx
  ContentSetManager *v23; // rbx
  DWORD v24; // eax
  __int64 v25; // rcx
  DWORD v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rcx
  DWORD v32; // eax
  __int64 v33; // rcx
  DWORD v35; // [rsp+38h] [rbp-C8h]
  DWORD v36; // [rsp+38h] [rbp-C8h]
  DWORD v37; // [rsp+38h] [rbp-C8h]
  int v38; // [rsp+50h] [rbp-B0h] BYREF
  struct ContentSetManager *v39; // [rsp+58h] [rbp-A8h] BYREF
  int v40; // [rsp+60h] [rbp-A0h] BYREF
  int v41; // [rsp+64h] [rbp-9Ch] BYREF
  struct Db *v42; // [rsp+68h] [rbp-98h] BYREF
  struct VolumeManager *v43; // [rsp+70h] [rbp-90h] BYREF
  const wchar_t *v44; // [rsp+78h] [rbp-88h] BYREF
  int v45; // [rsp+80h] [rbp-80h]
  int v46; // [rsp+84h] [rbp-7Ch]
  const wchar_t *v47; // [rsp+88h] [rbp-78h]
  unsigned int v48; // [rsp+90h] [rbp-70h] BYREF
  ContentSetManager *v49; // [rsp+98h] [rbp-68h] BYREF
  const struct _GUID *v50; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v51; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v52; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v53; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v54[64]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v55[72]; // [rsp+110h] [rbp+10h] BYREF
  struct _GUID v56; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v57[32]; // [rsp+3C0h] [rbp+2C0h] BYREF

  v6 = 0;
  v43 = 0;
  v50 = 0;
  v49 = 0;
  v53 = 0;
  v41 = 0;
  v38 = 0;
  v40 = 0;
  ID_RECORD::ID_RECORD((ID_RECORD *)v55);
  v42 = 0;
  VolumeId::VolumeId((VolumeId *)v54, a2);
  v52 = 0;
  v48 = 0;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v44 = L"FrsReplicator::Reghoster::ReghostFile";
    v45 = 615;
    v46 = 4;
    v47 = L"REGH";
    dbgobj::DbgPrint<unsigned short,FileId,_GUID>(&v44, v7, a3, a2);
  }
  v8 = VolumeManagerMap::Find((VolumeManagerMap *)(*(_QWORD *)this + 8LL), (const struct VolumeId *)v54, &v43);
  v9 = v43;
  if ( v8
    || (v10 = GetCurrentThreadId(),
        (v12 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                     v11,
                                     1168,
                                     0,
                                     1,
                                     "base\\fs\\remotefs\\frs\\src\\sync\\reghost.cpp",
                                     "FrsReplicator::Reghoster::ReghostFile",
                                     622,
                                     v10,
                                     0)) == 0) )
  {
    if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugVolumeManagerRefCount)
      && g_DebugLog
      && LODWORD(g_DebugLog[1].LockSemaphore)
      && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v44 = L"FrsReplicator::Reghoster::ReghostFile";
      v45 = 630;
      v46 = 5;
      v47 = L"REGH";
      v39 = v9;
      dbgobj::DbgPrint<unsigned short,unsigned __int64>(
        &v44,
        L"[VMREF] Added reference to volume manager. ptr:%p",
        &v39);
    }
    v13 = *(__int64 (__fastcall **)(struct VolumeManager *, __int128 *, _QWORD))(*(_QWORD *)v9 + 32LL);
    CurrentThreadId = GetCurrentThreadId();
    v12 = (struct FrsStatus *)v13(v9, &v53, CurrentThreadId);
    if ( !v12 )
    {
      (*(void (__fastcall **)(_QWORD, struct Db **))(*(_QWORD *)v53 + 48LL))(v53, &v42);
      v15 = *(_QWORD *)v42;
      v51 = 0;
      v12 = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, int *, const struct FileId *, _BYTE *, __int64 *))(v15 + 40))(
                                  v42,
                                  &v40,
                                  a3,
                                  v55,
                                  &v51);
      if ( v12 )
        goto LABEL_33;
      if ( !v40 || !(unsigned int)ID_RECORD::Alive((ID_RECORD *)v55) )
      {
        v17 = GetCurrentThreadId();
        v12 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                    v18,
                                    1168,
                                    0,
                                    1,
                                    "base\\fs\\remotefs\\frs\\src\\sync\\reghost.cpp",
                                    "FrsReplicator::Reghoster::ReghostFile",
                                    645,
                                    v17,
                                    0);
        if ( v12 )
          goto LABEL_33;
      }
      ContentSet = ConfigContext::GetContentSet(v16, &v56, 0);
      ScopedRef<Config::ContentSet>::Set(&v50, ContentSet);
      v20 = v50;
      if ( !v50 )
      {
        v21 = GetCurrentThreadId();
        v12 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                    v22,
                                    9001,
                                    0,
                                    3,
                                    "base\\fs\\remotefs\\frs\\src\\sync\\reghost.cpp",
                                    "FrsReplicator::Reghoster::ReghostFile",
                                    659,
                                    v21,
                                    0);
        if ( v12 )
          goto LABEL_33;
      }
      v39 = 0;
      ContentSetManagerMap::Find((struct VolumeManager *)((char *)v9 + 648), v20 + 9, &v39);
      ScopedRef<VolumeManager::ShutdownRestartTask>::Set(&v49, v39);
      v23 = v49;
      if ( !v49 )
      {
        v24 = GetCurrentThreadId();
        v12 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                    v25,
                                    9001,
                                    0,
                                    3,
                                    "base\\fs\\remotefs\\frs\\src\\sync\\reghost.cpp",
                                    "FrsReplicator::Reghoster::ReghostFile",
                                    666,
                                    v24,
                                    0);
        if ( v12 )
          goto LABEL_33;
      }
      if ( !(unsigned int)ContentSetManager::IsGhosted(v23) )
      {
        v26 = GetCurrentThreadId();
        v12 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                    v27,
                                    9304,
                                    0,
                                    3,
                                    "base\\fs\\remotefs\\frs\\src\\sync\\reghost.cpp",
                                    "FrsReplicator::Reghoster::ReghostFile",
                                    683,
                                    v26,
                                    0);
        if ( v12 )
          goto LABEL_33;
      }
      v12 = ContentSetManager::IsFileGhosted(v23, (struct FileId *)v57, &v41, &v38, &v48);
      if ( v12 )
        goto LABEL_33;
      if ( v41 )
      {
        v35 = GetCurrentThreadId();
        v29 = FrsStatusList::PushNewError(
                v28,
                9303,
                0,
                3,
                "base\\fs\\remotefs\\frs\\src\\sync\\reghost.cpp",
                "FrsReplicator::Reghoster::ReghostFile",
                713,
                v35,
                0);
      }
      else if ( v38 )
      {
        v36 = GetCurrentThreadId();
        v29 = FrsStatusList::PushNewError(
                v30,
                9304,
                0,
                3,
                "base\\fs\\remotefs\\frs\\src\\sync\\reghost.cpp",
                "FrsReplicator::Reghoster::ReghostFile",
                721,
                v36,
                0);
      }
      else
      {
        v38 = 0;
        v12 = ContentSetManager::IsVersionKnownToUpstreamPartners(v23, (struct ID_RECORD *)v55, &v38);
        if ( v12 )
          goto LABEL_33;
        if ( v38 )
        {
LABEL_32:
          v12 = ContentSetManager::ReghostFile(v23, (struct ID_RECORD *)v55, v42, (struct FileId *)&v52);
          goto LABEL_33;
        }
        v37 = GetCurrentThreadId();
        v29 = FrsStatusList::PushNewError(
                v31,
                9304,
                0,
                3,
                "base\\fs\\remotefs\\frs\\src\\sync\\reghost.cpp",
                "FrsReplicator::Reghoster::ReghostFile",
                733,
                v37,
                0);
      }
      v12 = (struct FrsStatus *)v29;
      if ( !v29 )
        goto LABEL_32;
LABEL_33:
      (*(void (__fastcall **)(_QWORD, struct Db **))(*(_QWORD *)v53 + 64LL))(v53, &v42);
    }
  }
  if ( v9 )
  {
    if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugVolumeManagerRefCount)
      && g_DebugLog
      && LODWORD(g_DebugLog[1].LockSemaphore)
      && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v44 = L"FrsReplicator::Reghoster::ReghostFile";
      v45 = 758;
      v46 = 5;
      v47 = L"REGH";
      v39 = v9;
      dbgobj::DbgPrint<unsigned short,unsigned __int64>(
        &v44,
        L"[VMREF] Release reference to volume manager. ptr:%p",
        &v39);
    }
    ScopedRef<VolumeManager::ShutdownRestartTask>::Set(&v43, 0);
  }
  if ( v12 )
  {
    v32 = GetCurrentThreadId();
    v6 = FrsStatusList::PushNewError(
           v33,
           *((unsigned int *)v12 + 1),
           *((unsigned int *)v12 + 2),
           *(unsigned int *)v12,
           "base\\fs\\remotefs\\frs\\src\\sync\\reghost.cpp",
           "FrsReplicator::Reghoster::ReghostFile",
           759,
           v32,
           v12);
  }
  VolumeId::~VolumeId((VolumeId *)v54);
  DbManagerInstance::FinalizeDbManagerInstance((DbManagerInstance *)&v53);
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v49);
  ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v50);
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v43);
  return (struct FrsStatus *)v6;
}

```

## disassembly

```asm
0x14012e10c  mov     [rsp-8+arg_18], rbx
0x14012e111  push    rbp
0x14012e112  push    rsi
0x14012e113  push    rdi
0x14012e114  push    r12
0x14012e116  push    r13
0x14012e118  push    r14
0x14012e11a  push    r15
0x14012e11c  lea     rbp, [rsp-2F0h]
0x14012e124  sub     rsp, 3F0h
0x14012e12b  mov     rax, cs:__security_cookie
0x14012e132  xor     rax, rsp
0x14012e135  mov     [rbp+320h+var_40], rax
0x14012e13c  mov     r15, r8
0x14012e13f  mov     rbx, rdx
0x14012e142  mov     rdi, rcx
0x14012e145  xor     esi, esi
0x14012e147  mov     [rsp+420h+var_3B0], rsi
0x14012e14c  mov     [rbp+320h+var_380], rsi
0x14012e150  mov     [rbp+320h+var_388], rsi
0x14012e154  xorps   xmm0, xmm0
0x14012e157  movdqu  [rbp+320h+var_368], xmm0
0x14012e15c  mov     [rsp+420h+var_3BC], esi
0x14012e160  mov     [rsp+420h+var_3D0], esi
0x14012e164  mov     [rsp+420h+var_3C0], esi
0x14012e168  lea     rcx, [rbp+320h+var_310]; this
0x14012e16c  call    ??0ID_RECORD@@QEAA@XZ; ID_RECORD::ID_RECORD(void)
0x14012e171  mov     [rsp+420h+var_3B8], rsi
0x14012e176  mov     rdx, rbx; struct _GUID *
0x14012e179  lea     rcx, [rbp+320h+var_350]; this
0x14012e17d  call    ??0VolumeId@@QEAA@AEBU_GUID@@@Z; VolumeId::VolumeId(_GUID const &)
0x14012e182  nop
0x14012e183  mov     [rbp+320h+var_370], rsi
0x14012e187  mov     [rbp+320h+var_390], esi
0x14012e18a  lea     r14, aFrsreplicatorR_12; "FrsReplicator::Reghoster::ReghostFile"
0x14012e191  lea     rcx, aRegh; "REGH"
0x14012e198  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14012e19f  test    rax, rax
0x14012e1a2  jz      short loc_14012E1D6
0x14012e1a4  cmp     [rax+40h], esi
0x14012e1a7  jz      short loc_14012E1D6
0x14012e1a9  cmp     dword ptr [rax+38h], 4
0x14012e1ad  jl      short loc_14012E1D6
0x14012e1af  mov     [rsp+420h+var_3A8], r14
0x14012e1b4  mov     [rbp+320h+var_3A0], 267h
0x14012e1bb  mov     [rbp+320h+var_39C], 4
0x14012e1c2  mov     [rbp+320h+var_398], rcx
0x14012e1c6  mov     r9, rbx
0x14012e1c9  mov     r8, r15
0x14012e1cc  lea     rcx, [rsp+420h+var_3A8]
0x14012e1d1  call    ??$DbgPrint@GVFileId@@U_GUID@@@dbgobj@@QEAA_KPEBGAEBVFileId@@AEBU_GUID@@@Z; dbgobj::DbgPrint<ushort,FileId,_GUID>(ushort const *,FileId const &,_GUID const &)
0x14012e1d6  mov     rcx, [rdi]
0x14012e1d9  add     rcx, 8; this
0x14012e1dd  lea     r8, [rsp+420h+var_3B0]; struct VolumeManager **
0x14012e1e2  lea     rdx, [rbp+320h+var_350]; struct VolumeId *
0x14012e1e6  call    ?Find@VolumeManagerMap@@QEAAHAEBVVolumeId@@AEAPEAVVolumeManager@@@Z; VolumeManagerMap::Find(VolumeId const &,VolumeManager * &)
0x14012e1eb  mov     rdi, [rsp+420h+var_3B0]
0x14012e1f0  lea     r12, aFrsreplicatorR_8; "FrsReplicator::Reghoster::ReghostFile"
0x14012e1f7  lea     r13, aBaseFsRemotefs_40; "base\\fs\\remotefs\\frs\\src\\sync\\reg"...
0x14012e1fe  test    eax, eax
0x14012e200  jnz     short loc_14012E24F
0x14012e202  call    cs:__imp_GetCurrentThreadId
0x14012e209  nop     dword ptr [rax+rax+00h]
0x14012e20e  mov     [rsp+420h+var_3E0], rsi
0x14012e213  mov     [rsp+420h+var_3E8], eax
0x14012e217  mov     [rsp+420h+var_3F0], 26Eh
0x14012e21f  mov     [rsp+420h+var_3F8], r12
0x14012e224  mov     [rsp+420h+var_400], r13
0x14012e229  mov     r9d, 1
0x14012e22f  xor     r8d, r8d
0x14012e232  mov     edx, 490h
0x14012e237  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14012e23c  mov     r14, rax
0x14012e23f  test    rax, rax
0x14012e242  jnz     loc_14012E5C0
0x14012e248  lea     r14, aFrsreplicatorR_12; "FrsReplicator::Reghoster::ReghostFile"
0x14012e24f  lea     rcx, ?DebugVolumeManagerRefCount@Settings@@3VCDebugVolumeManagerRefCount@1@A; Settings::CDebugVolumeManagerRefCount Settings::DebugVolumeManagerRefCount
0x14012e256  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x14012e25b  test    eax, eax
0x14012e25d  jz      short loc_14012E2AF
0x14012e25f  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14012e266  test    rax, rax
0x14012e269  jz      short loc_14012E2AF
0x14012e26b  cmp     [rax+40h], esi
0x14012e26e  jz      short loc_14012E2AF
0x14012e270  cmp     dword ptr [rax+38h], 5
0x14012e274  jl      short loc_14012E2AF
0x14012e276  mov     [rsp+420h+var_3A8], r14
0x14012e27b  mov     [rbp+320h+var_3A0], 276h
0x14012e282  mov     [rbp+320h+var_39C], 5
0x14012e289  lea     rax, aRegh; "REGH"
0x14012e290  mov     [rbp+320h+var_398], rax
0x14012e294  mov     [rsp+420h+var_3C8], rdi
0x14012e299  lea     r8, [rsp+420h+var_3C8]
0x14012e29e  lea     rdx, aVmrefAddedRefe; "[VMREF] Added reference to volume manag"...
0x14012e2a5  lea     rcx, [rsp+420h+var_3A8]
0x14012e2aa  call    ??$DbgPrint@G_K@dbgobj@@QEAA_KPEBGAEB_K@Z; dbgobj::DbgPrint<ushort,unsigned __int64>(ushort const *,unsigned __int64 const &)
0x14012e2af  mov     rax, [rdi]
0x14012e2b2  mov     rbx, [rax+20h]
0x14012e2b6  call    cs:__imp_GetCurrentThreadId
0x14012e2bd  nop     dword ptr [rax+rax+00h]
0x14012e2c2  mov     r8d, eax
0x14012e2c5  lea     rdx, [rbp+320h+var_368]
0x14012e2c9  mov     rcx, rdi
0x14012e2cc  mov     rax, rbx
0x14012e2cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012e2d4  mov     r14, rax
0x14012e2d7  test    rax, rax
0x14012e2da  jnz     loc_14012E5C0
0x14012e2e0  mov     rcx, qword ptr [rbp+320h+var_368]
0x14012e2e4  mov     rax, [rcx]
0x14012e2e7  lea     rdx, [rsp+420h+var_3B8]
0x14012e2ec  mov     rax, [rax+30h]
0x14012e2f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012e2f5  mov     rcx, [rsp+420h+var_3B8]
0x14012e2fa  mov     rax, [rcx]
0x14012e2fd  mov     [rbp+320h+var_378], rsi
0x14012e301  lea     rdx, [rbp+320h+var_378]
0x14012e305  mov     [rsp+420h+var_400], rdx
0x14012e30a  lea     r9, [rbp+320h+var_310]
0x14012e30e  mov     r8, r15
0x14012e311  lea     rdx, [rsp+420h+var_3C0]
0x14012e316  mov     rax, [rax+28h]
0x14012e31a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012e31f  mov     r14, rax
0x14012e322  test    rax, rax
0x14012e325  jnz     loc_14012E5AB
0x14012e32b  cmp     [rsp+420h+var_3C0], esi
0x14012e32f  jz      short loc_14012E33E
0x14012e331  lea     rcx, [rbp+320h+var_310]; this
0x14012e335  call    ?Alive@ID_RECORD@@QEBAHXZ; ID_RECORD::Alive(void)
0x14012e33a  test    eax, eax
0x14012e33c  jnz     short loc_14012E384
0x14012e33e  call    cs:__imp_GetCurrentThreadId
0x14012e345  nop     dword ptr [rax+rax+00h]
0x14012e34a  mov     [rsp+420h+var_3E0], rsi
0x14012e34f  mov     [rsp+420h+var_3E8], eax
0x14012e353  mov     [rsp+420h+var_3F0], 285h
0x14012e35b  mov     [rsp+420h+var_3F8], r12
0x14012e360  mov     [rsp+420h+var_400], r13
0x14012e365  mov     r9d, 1
0x14012e36b  xor     r8d, r8d
0x14012e36e  mov     edx, 490h
0x14012e373  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14012e378  mov     r14, rax
0x14012e37b  test    rax, rax
0x14012e37e  jnz     loc_14012E5AB
0x14012e384  xor     r8d, r8d; struct Config::Volume **
0x14012e387  lea     rdx, [rbp+320h+var_2C8]; struct _GUID *
0x14012e38b  call    ?GetContentSet@ConfigContext@@QEAAPEAVContentSet@Config@@PEBU_GUID@@PEAPEAVVolume@3@@Z; ConfigContext::GetContentSet(_GUID const *,Config::Volume * *)
0x14012e390  mov     rdx, rax
0x14012e393  lea     rcx, [rbp+320h+var_380]
0x14012e397  call    ?Set@?$ScopedRef@VContentSet@Config@@@@AEAAXPEAVContentSet@Config@@@Z; ScopedRef<Config::ContentSet>::Set(Config::ContentSet *)
0x14012e39c  mov     r15d, 3
0x14012e3a2  mov     rbx, [rbp+320h+var_380]
0x14012e3a6  test    rbx, rbx
0x14012e3a9  jnz     short loc_14012E3EE
0x14012e3ab  call    cs:__imp_GetCurrentThreadId
0x14012e3b2  nop     dword ptr [rax+rax+00h]
0x14012e3b7  mov     [rsp+420h+var_3E0], rsi
0x14012e3bc  mov     [rsp+420h+var_3E8], eax
0x14012e3c0  mov     [rsp+420h+var_3F0], 293h
0x14012e3c8  mov     [rsp+420h+var_3F8], r12
0x14012e3cd  mov     [rsp+420h+var_400], r13
0x14012e3d2  mov     r9d, r15d
0x14012e3d5  xor     r8d, r8d
0x14012e3d8  mov     edx, 2329h
0x14012e3dd  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14012e3e2  mov     r14, rax
0x14012e3e5  test    rax, rax
0x14012e3e8  jnz     loc_14012E5AB
0x14012e3ee  lea     rdx, [rbx+90h]; struct _GUID *
0x14012e3f5  mov     [rsp+420h+var_3C8], rsi
0x14012e3fa  lea     rcx, [rdi+288h]; this
0x14012e401  lea     r8, [rsp+420h+var_3C8]; struct ContentSetManager **
0x14012e406  call    ?Find@ContentSetManagerMap@@QEAAHAEBU_GUID@@AEAPEAVContentSetManager@@@Z; ContentSetManagerMap::Find(_GUID const &,ContentSetManager * &)
0x14012e40b  mov     rdx, [rsp+420h+var_3C8]
0x14012e410  lea     rcx, [rbp+320h+var_388]
0x14012e414  call    ?Set@?$ScopedRef@VShutdownRestartTask@VolumeManager@@@@AEAAXPEAVShutdownRestartTask@VolumeManager@@@Z; ScopedRef<VolumeManager::ShutdownRestartTask>::Set(VolumeManager::ShutdownRestartTask *)
0x14012e419  mov     rbx, [rbp+320h+var_388]
0x14012e41d  test    rbx, rbx
0x14012e420  jnz     short loc_14012E465
0x14012e422  call    cs:__imp_GetCurrentThreadId
0x14012e429  nop     dword ptr [rax+rax+00h]
0x14012e42e  mov     [rsp+420h+var_3E0], rsi
0x14012e433  mov     [rsp+420h+var_3E8], eax
0x14012e437  mov     [rsp+420h+var_3F0], 29Ah
0x14012e43f  mov     [rsp+420h+var_3F8], r12
0x14012e444  mov     [rsp+420h+var_400], r13
0x14012e449  mov     r9d, r15d
0x14012e44c  xor     r8d, r8d
0x14012e44f  mov     edx, 2329h
0x14012e454  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14012e459  mov     r14, rax
0x14012e45c  test    rax, rax
0x14012e45f  jnz     loc_14012E5AB
0x14012e465  mov     rcx, rbx; this
0x14012e468  call    ?IsGhosted@ContentSetManager@@QEAAHXZ; ContentSetManager::IsGhosted(void)
0x14012e46d  test    eax, eax
0x14012e46f  jnz     short loc_14012E4B4
0x14012e471  call    cs:__imp_GetCurrentThreadId
0x14012e478  nop     dword ptr [rax+rax+00h]
0x14012e47d  mov     [rsp+420h+var_3E0], rsi
0x14012e482  mov     [rsp+420h+var_3E8], eax
0x14012e486  mov     [rsp+420h+var_3F0], 2ABh
0x14012e48e  mov     [rsp+420h+var_3F8], r12
0x14012e493  mov     [rsp+420h+var_400], r13
0x14012e498  mov     r9d, r15d
0x14012e49b  xor     r8d, r8d
0x14012e49e  mov     edx, 2458h
0x14012e4a3  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14012e4a8  mov     r14, rax
0x14012e4ab  test    rax, rax
0x14012e4ae  jnz     loc_14012E5AB
0x14012e4b4  lea     rax, [rbp+320h+var_390]
0x14012e4b8  mov     [rsp+420h+var_400], rax; unsigned int *
0x14012e4bd  lea     r9, [rsp+420h+var_3D0]; int *
0x14012e4c2  lea     r8, [rsp+420h+var_3BC]; int *
0x14012e4c7  lea     rdx, [rbp+320h+var_60]; struct FileId *
0x14012e4ce  mov     rcx, rbx; this
0x14012e4d1  call    ?IsFileGhosted@ContentSetManager@@QEAAPEAVFrsStatus@@AEAVFileId@@AEAH1AEAK@Z; ContentSetManager::IsFileGhosted(FileId &,int &,int &,ulong &)
0x14012e4d6  mov     r14, rax
0x14012e4d9  test    rax, rax
0x14012e4dc  jnz     loc_14012E5AB
0x14012e4e2  cmp     [rsp+420h+var_3BC], esi
0x14012e4e6  jz      short loc_14012E50C
0x14012e4e8  call    cs:__imp_GetCurrentThreadId
0x14012e4ef  nop     dword ptr [rax+rax+00h]
0x14012e4f4  mov     [rsp+420h+var_3E0], rsi
0x14012e4f9  mov     [rsp+420h+var_3E8], eax
0x14012e4fd  mov     [rsp+420h+var_3F0], 2C9h
0x14012e505  mov     edx, 2457h
0x14012e50a  jmp     short loc_14012E576
0x14012e50c  cmp     [rsp+420h+var_3D0], esi
0x14012e510  jz      short loc_14012E531
0x14012e512  call    cs:__imp_GetCurrentThreadId
0x14012e519  nop     dword ptr [rax+rax+00h]
0x14012e51e  mov     [rsp+420h+var_3E0], rsi
0x14012e523  mov     [rsp+420h+var_3E8], eax
0x14012e527  mov     [rsp+420h+var_3F0], 2D1h
0x14012e52f  jmp     short loc_14012E571
0x14012e531  mov     [rsp+420h+var_3D0], esi
0x14012e535  lea     r8, [rsp+420h+var_3D0]; int *
0x14012e53a  lea     rdx, [rbp+320h+var_310]; struct ID_RECORD *
0x14012e53e  mov     rcx, rbx; this
0x14012e541  call    ?IsVersionKnownToUpstreamPartners@ContentSetManager@@QEAAPEAVFrsStatus@@AEAVID_RECORD@@AEAH@Z; ContentSetManager::IsVersionKnownToUpstreamPartners(ID_RECORD &,int &)
0x14012e546  mov     r14, rax
0x14012e549  test    rax, rax
0x14012e54c  jnz     short loc_14012E5AB
0x14012e54e  cmp     [rsp+420h+var_3D0], esi
0x14012e552  jnz     short loc_14012E593
0x14012e554  call    cs:__imp_GetCurrentThreadId
0x14012e55b  nop     dword ptr [rax+rax+00h]
0x14012e560  mov     [rsp+420h+var_3E0], rsi
0x14012e565  mov     [rsp+420h+var_3E8], eax
0x14012e569  mov     [rsp+420h+var_3F0], 2DDh
0x14012e571  mov     edx, 2458h
0x14012e576  mov     [rsp+420h+var_3F8], r12
0x14012e57b  mov     [rsp+420h+var_400], r13
0x14012e580  mov     r9d, r15d
0x14012e583  xor     r8d, r8d
0x14012e586  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14012e58b  mov     r14, rax
0x14012e58e  test    rax, rax
0x14012e591  jnz     short loc_14012E5AB
0x14012e593  lea     r9, [rbp+320h+var_370]; struct FileId *
0x14012e597  mov     r8, [rsp+420h+var_3B8]; struct Db *
0x14012e59c  lea     rdx, [rbp+320h+var_310]; struct ID_RECORD *
0x14012e5a0  mov     rcx, rbx; this
0x14012e5a3  call    ?ReghostFile@ContentSetManager@@QEAAPEAVFrsStatus@@AEAVID_RECORD@@PEAVDb@@AEAVFileId@@@Z; ContentSetManager::ReghostFile(ID_RECORD &,Db *,FileId &)
0x14012e5a8  mov     r14, rax
0x14012e5ab  mov     rcx, qword ptr [rbp+320h+var_368]
0x14012e5af  mov     rax, [rcx]
0x14012e5b2  lea     rdx, [rsp+420h+var_3B8]
0x14012e5b7  mov     rax, [rax+40h]
0x14012e5bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012e5c0  test    rdi, rdi
0x14012e5c3  jz      short loc_14012E638
0x14012e5c5  lea     rcx, ?DebugVolumeManagerRefCount@Settings@@3VCDebugVolumeManagerRefCount@1@A; Settings::CDebugVolumeManagerRefCount Settings::DebugVolumeManagerRefCount
0x14012e5cc  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x14012e5d1  test    eax, eax
0x14012e5d3  jz      short loc_14012E62C
0x14012e5d5  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14012e5dc  test    rax, rax
0x14012e5df  jz      short loc_14012E62C
0x14012e5e1  cmp     [rax+40h], esi
0x14012e5e4  jz      short loc_14012E62C
0x14012e5e6  cmp     dword ptr [rax+38h], 5
0x14012e5ea  jl      short loc_14012E62C
0x14012e5ec  lea     rax, aFrsreplicatorR_12; "FrsReplicator::Reghoster::ReghostFile"
0x14012e5f3  mov     [rsp+420h+var_3A8], rax
0x14012e5f8  mov     [rbp+320h+var_3A0], 2F6h
0x14012e5ff  mov     [rbp+320h+var_39C], 5
0x14012e606  lea     rax, aRegh; "REGH"
0x14012e60d  mov     [rbp+320h+var_398], rax
0x14012e611  mov     [rsp+420h+var_3C8], rdi
0x14012e616  lea     r8, [rsp+420h+var_3C8]
0x14012e61b  lea     rdx, aVmrefReleaseRe; "[VMREF] Release reference to volume man"...
0x14012e622  lea     rcx, [rsp+420h+var_3A8]
0x14012e627  call    ??$DbgPrint@G_K@dbgobj@@QEAA_KPEBGAEB_K@Z; dbgobj::DbgPrint<ushort,unsigned __int64>(ushort const *,unsigned __int64 const &)
  ... truncated ...
```
