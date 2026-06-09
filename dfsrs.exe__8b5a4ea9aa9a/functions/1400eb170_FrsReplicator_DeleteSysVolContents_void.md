# FrsReplicator::DeleteSysVolContents(void)

- ea: `0x1400eb170`
- end: `0x1400eb8bf`
- name: `?DeleteSysVolContents@FrsReplicator@@QEAAPEAVFrsStatus@@XZ`
- size: `1871`
- prototype: `struct FrsStatus *__fastcall(FrsReplicator *__hidden this)`
- caller_count: `1`
- callee_count: `38`
- tags: `file_ops, reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x1400c9710`

## callees

- `0x1400036a0`
- `0x14000c910`
- `0x14000cdc0`
- `0x14000d980`
- `0x14000daa0`
- `0x14000dcc0`
- `0x14000dd10`
- `0x14000e34c`
- `0x14000ee94`
- `0x1400191fc`
- `0x14001c31c`
- `0x14001cfa0`
- `0x14001d7e8`
- `0x14001e4e4`
- `0x1400217d0`
- `0x1400249f4`
- `0x1400255c8`
- `0x14002a820`
- `0x14002c2f4`
- `0x140040a18`
- `0x140041ed0`
- `0x14004b648`
- `0x14004be88`
- `0x14004c1c0`
- `0x14004d29c`
- `0x14004e1f0`
- `0x1400e69c4`
- `0x1400eb06c`
- `0x1400eb170`
- `0x1400f7530`
- `0x1400f8d1c`
- `0x1400f8edc`
- `0x1401b9494`
- `0x1401c0b7c`
- `0x1401c1e48`
- `0x1401c27b4`
- `0x1401cd328`
- `0x1401cd6f8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400eb26e`
- `KERNEL32!GetCurrentThreadId` at `0x1400eb2f9`
- `KERNEL32!GetCurrentThreadId` at `0x1400eb6b3`
- `KERNEL32!GetCurrentThreadId` at `0x1400eb757`
- `KERNEL32!GetCurrentThreadId` at `0x1400eb834`
- `KERNEL32!GetCurrentThreadId` at `0x1400eb26e`
- `KERNEL32!GetCurrentThreadId` at `0x1400eb2f9`
- `KERNEL32!GetCurrentThreadId` at `0x1400eb6b3`
- `KERNEL32!GetCurrentThreadId` at `0x1400eb757`
- `KERNEL32!GetCurrentThreadId` at `0x1400eb834`

## string_xrefs

- `0x1400eb262`: `base\fs\remotefs\frs\src\config\reg.h`
- `0x1400eb68f`: `base\fs\remotefs\frs\src\config\reg.h`
- `0x1400eb1d6`: `FrsReplicator::DeleteSysVolContents`
- `0x1400eb2e8`: `SYSVOL demoting registry values cannot be read at this time.`
- `0x1400eb21d`: `IsSysVolDeleted: %d`
- `0x1400eb851`: `FrsReplicator::DeleteSysVolContents`
- `0x1400eb4ca`: `[SYSVOL] Failed to remove sysvol root path from driver at this time. sysvolRootPath:%?`
- `0x1400eb3c9`: `[SYSVOL] Failed to get volume information from volume ID table against the sysvol path. sysvolRootPath:%?`
- `0x1400eb50f`: `[SYSVOL] Path already removed from Driver. sysvolRootPath:%?`
- `0x1400eb7cf`: `SYSVOL: Demoting SysVol subkeys are deleted.`
- `0x1400eb72f`: `SYSVOL: Demoting SysVol Commit Flag is deleted.`
- `0x1400eb813`: `SYSVOL: Failed to delete Demoting SysVol subkeys: %?`
- `0x1400eb774`: `Config::RegWriter::DeleteDemotingSysVolSubKeys`
- `0x1400eb6d0`: `Config::RegWriter::DeleteDemotingSysVolCommitFlag`
- `0x1400eb28b`: `Config::RegReader::ReadDemotingSysVolConfigValues`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
struct FrsStatus *__fastcall FrsReplicator::DeleteSysVolContents(struct TaskPool **this)
{
  Config::RegReader *v2; // rcx
  __int64 v3; // rbx
  Config::RegReader *v4; // rcx
  Config::RegWriter *v5; // rcx
  struct FrsStatus *SysVolConfigValues; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v8; // rcx
  struct FrsStatus *VolumeFromFilePath; // rdi
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rdx
  ConfigContext *v13; // rcx
  VolumeIdTable *VolumeTable; // rax
  struct FrsStatus *v15; // r14
  __int64 v16; // rcx
  FrsReadOnlyFilter *v17; // rcx
  __int64 v18; // rcx
  Config::RegWriter *v19; // rcx
  struct FrsStatus *v20; // rdi
  DWORD v21; // eax
  __int64 v22; // rcx
  struct FrsStatus *v23; // rdi
  DWORD v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rcx
  DWORD v28; // [rsp+38h] [rbp-C8h]
  DWORD v29; // [rsp+38h] [rbp-C8h]
  const wchar_t *v30; // [rsp+50h] [rbp-B0h] BYREF
  int v31; // [rsp+58h] [rbp-A8h]
  int v32; // [rsp+5Ch] [rbp-A4h]
  const wchar_t *v33; // [rsp+60h] [rbp-A0h]
  struct FrsStatus *v34; // [rsp+68h] [rbp-98h] BYREF
  void **v35; // [rsp+70h] [rbp-90h] BYREF
  int v36; // [rsp+78h] [rbp-88h] BYREF
  int v37; // [rsp+7Ch] [rbp-84h]
  const wchar_t *v38; // [rsp+80h] [rbp-80h]
  VolumeManager *v39; // [rsp+88h] [rbp-78h] BYREF
  struct Config::Volume *Volume; // [rsp+90h] [rbp-70h] BYREF
  LightVolumeManager *LightVolumeManager; // [rsp+98h] [rbp-68h] BYREF
  void **v42; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v43[3]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v44[16]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v45[16]; // [rsp+D0h] [rbp-30h] BYREF
  struct _GUID v46; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v47[8]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v48[40]; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v49[4]; // [rsp+140h] [rbp+40h] BYREF
  struct _GUID v50; // [rsp+160h] [rbp+60h] BYREF

  ScopedLock::ScopedLock((ScopedLock *)v44, (struct ScopedCS *)(this + 42));
  v43[1] = &Config::RegReader::`vftable';
  v43[2] = &Config::RegWriter::`vftable';
  Config::SYSVOL_PARAMETERS::SYSVOL_PARAMETERS((Config::SYSVOL_PARAMETERS *)v47);
  v3 = 0;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v35 = (void **)L"FrsReplicator::DeleteSysVolContents";
    v36 = 1485;
    v37 = 5;
    v38 = L"FREP";
    dbgobj::DbgPrint<unsigned short,int>(&v35, L"IsSysVolDeleted: %d", (char *)this + 332);
  }
  if ( !*((_DWORD *)this + 83) && (unsigned int)Config::RegReader::IsSysVolCommitFlagSet(v2, L"Demoting SysVols") )
  {
    SysVolConfigValues = Config::RegReader::ReadSysVolConfigValues(
                           v4,
                           L"Demoting SysVols",
                           (struct Config::SYSVOL_PARAMETERS *)v47);
    if ( SysVolConfigValues )
    {
      CurrentThreadId = GetCurrentThreadId();
      VolumeFromFilePath = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                 v8,
                                                 *((unsigned int *)SysVolConfigValues + 1),
                                                 *((unsigned int *)SysVolConfigValues + 2),
                                                 *(unsigned int *)SysVolConfigValues,
                                                 "base\\fs\\remotefs\\frs\\src\\config\\reg.h",
                                                 "Config::RegReader::ReadDemotingSysVolConfigValues",
                                                 445,
                                                 CurrentThreadId,
                                                 SysVolConfigValues);
    }
    else
    {
      VolumeFromFilePath = 0;
    }
    if ( VolumeFromFilePath )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v35 = (void **)L"FrsReplicator::DeleteSysVolContents";
        v36 = 1504;
        v37 = 2;
        v38 = L"FREP";
        dbgobj::DbgPrint<unsigned short>(&v35, L"SYSVOL demoting registry values cannot be read at this time.");
      }
      v28 = GetCurrentThreadId();
      v11 = FrsStatusList::PushNewError(
              v10,
              *((unsigned int *)VolumeFromFilePath + 1),
              *((unsigned int *)VolumeFromFilePath + 2),
              *(unsigned int *)VolumeFromFilePath,
              "base\\fs\\remotefs\\frs\\src\\sync\\frsreplicator.cpp",
              "FrsReplicator::DeleteSysVolContents",
              1505,
              v28,
              VolumeFromFilePath);
      goto LABEL_78;
    }
    if ( *(_QWORD *)(v49[0] + 8LL) )
    {
      VolumeId::VolumeId((VolumeId *)v45);
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v35 = (void **)L"FrsReplicator::DeleteSysVolContents";
        v36 = 1515;
        v37 = 4;
        v38 = L"FREP";
        dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,Guid>(&v35, v12, v49, &v50);
      }
      VolumeTable = ConfigContext::GetVolumeTable(v13);
      VolumeFromFilePath = (struct FrsStatus *)VolumeIdTable::FindVolumeFromFilePath(VolumeTable);
      if ( VolumeFromFilePath
        && g_DebugLog
        && LODWORD(g_DebugLog[1].LockSemaphore)
        && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v35 = (void **)L"FrsReplicator::DeleteSysVolContents";
        v36 = 1528;
        v37 = 2;
        v38 = L"FREP";
        dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
          &v35,
          L"[SYSVOL] Failed to get volume information from volume ID table against the sysvol path. sysvolRootPath:%?",
          v49);
      }
      if ( !VolumeFromFilePath )
      {
        Win32FilePath::Win32FilePath((Win32FilePath *)&v35);
        Win32FilePath::Win32FilePath((Win32FilePath *)&v42);
        VolumeFromFilePath = (struct FrsStatus *)Win32FilePath::SetNoConvert(&v35, v49);
        v34 = VolumeFromFilePath;
        v15 = VolumeFromFilePath;
        if ( !VolumeFromFilePath )
        {
          VolumeFromFilePath = Win32FilePath::GetVolumeMountPointRelativePath(
                                 (Win32FilePath *)&v35,
                                 (struct Win32FilePath *)&v42);
          v34 = VolumeFromFilePath;
          v15 = VolumeFromFilePath;
          if ( !VolumeFromFilePath )
          {
            FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(&v39, L"\\");
            FrsStringImpl<unsigned short,char>::Append(&v39, v43[0] + 18LL);
            VolumeFromFilePath = (struct FrsStatus *)FrsReadOnlyFilter::RemoveContentSetRoot(v16, v45, &v39);
            v15 = VolumeFromFilePath;
            v34 = VolumeFromFilePath;
            FrsStringImpl<char,unsigned short>::ReleaseBody(&v39);
            if ( !VolumeFromFilePath )
              goto LABEL_41;
          }
        }
        if ( *((_DWORD *)v15 + 1) == 3 )
        {
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            v30 = L"FrsReplicator::DeleteSysVolContents";
            v31 = 1560;
            v32 = 4;
            v33 = L"FREP";
            dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
              &v30,
              L"[SYSVOL] Path already removed from Driver. sysvolRootPath:%?",
              v49);
          }
          CLEAR_ERROR(&v34);
          VolumeFromFilePath = v34;
        }
        else if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
        {
          v30 = L"FrsReplicator::DeleteSysVolContents";
          v31 = 1555;
          v32 = 2;
          v33 = L"FREP";
          dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
            &v30,
            L"[SYSVOL] Failed to remove sysvol root path from driver at this time. sysvolRootPath:%?",
            v49);
        }
        if ( !VolumeFromFilePath )
        {
LABEL_41:
          LODWORD(v34) = 0;
          v39 = 0;
          if ( (unsigned int)VolumeManagerMap::Find((VolumeManagerMap *)(this + 1), (const struct VolumeId *)v45, &v39) )
          {
            VolumeFromFilePath = VolumeManager::GetNumberOfReadOnlyContentSetsInDb(v39, &v50, (unsigned int *)&v34);
          }
          else
          {
            LightVolumeManager = 0;
            Volume = 0;
            Volume = ConfigContext::GetVolume(g_ConfigContext, &v46);
            LightVolumeManager = FrsReplicator::CreateLightVolumeManager((const struct VolumeId *)v45, Volume, this[39]);
            LightVolumeManager::GetNumberOfReadOnlyContentSetsInDb(LightVolumeManager, &v50, (unsigned int *)&v34);
            ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&Volume);
            ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&LightVolumeManager);
          }
          if ( !VolumeFromFilePath && !(_DWORD)v34 )
          {
            VolumeFromFilePath = FrsReadOnlyFilter::DetachDriver(v17, (const struct VolumeId *)v45);
            if ( VolumeFromFilePath )
            {
              if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
              {
                v30 = L"FrsReplicator::DeleteSysVolContents";
                v31 = 1605;
                v32 = 2;
                v33 = L"FREP";
                dbgobj::DbgPrint<unsigned short,VolumeId,FrsStatus>(
                  &v30,
                  L"Failed DetachDriver for VolumeId:%? Error:%?",
                  v45,
                  VolumeFromFilePath);
              }
            }
          }
          ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v39);
        }
        v42 = &BaseFilePath::`vftable';
        FrsStringImpl<char,unsigned short>::ReleaseBody(v43);
        v35 = &BaseFilePath::`vftable';
        FrsStringImpl<char,unsigned short>::ReleaseBody(&v36);
        if ( !VolumeFromFilePath )
          VolumeFromFilePath = (struct FrsStatus *)Config::RegWriter::ClearDemotingSysvolValues(v18, v48);
      }
      VolumeId::~VolumeId((VolumeId *)v45);
    }
    if ( VolumeFromFilePath )
      goto LABEL_77;
    v20 = Config::RegWriter::DeleteSysVolCommitFlag(v5, L"Demoting SysVols");
    if ( v20 )
    {
      v21 = GetCurrentThreadId();
      VolumeFromFilePath = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                 v22,
                                                 *((unsigned int *)v20 + 1),
                                                 *((unsigned int *)v20 + 2),
                                                 *(unsigned int *)v20,
                                                 "base\\fs\\remotefs\\frs\\src\\config\\reg.h",
                                                 "Config::RegWriter::DeleteDemotingSysVolCommitFlag",
                                                 696,
                                                 v21,
                                                 v20);
    }
    else
    {
      VolumeFromFilePath = 0;
    }
    if ( VolumeFromFilePath )
      goto LABEL_82;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v30 = L"FrsReplicator::DeleteSysVolContents";
      v31 = 1651;
      v32 = 4;
      v33 = L"FREP";
      dbgobj::DbgPrint<unsigned short>(&v30, L"SYSVOL: Demoting SysVol Commit Flag is deleted.");
    }
    v23 = Config::RegWriter::DeleteSysVolSubKeys(v19, L"Demoting SysVols", 0);
    if ( v23 )
    {
      v24 = GetCurrentThreadId();
      VolumeFromFilePath = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                 v25,
                                                 *((unsigned int *)v23 + 1),
                                                 *((unsigned int *)v23 + 2),
                                                 *(unsigned int *)v23,
                                                 "base\\fs\\remotefs\\frs\\src\\config\\reg.h",
                                                 "Config::RegWriter::DeleteDemotingSysVolSubKeys",
                                                 767,
                                                 v24,
                                                 v23);
    }
    else
    {
      VolumeFromFilePath = 0;
    }
    if ( VolumeFromFilePath )
    {
LABEL_82:
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v30 = L"FrsReplicator::DeleteSysVolContents";
        v31 = 1659;
        v32 = 4;
        v33 = L"FREP";
        dbgobj::DbgPrint<unsigned short,FrsStatus>(
          &v30,
          L"SYSVOL: Failed to delete Demoting SysVol subkeys: %?",
          VolumeFromFilePath);
      }
    }
    else if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v30 = L"FrsReplicator::DeleteSysVolContents";
      v31 = 1656;
      v32 = 4;
      v33 = L"FREP";
      dbgobj::DbgPrint<unsigned short>(&v30, L"SYSVOL: Demoting SysVol subkeys are deleted.");
    }
    *((_DWORD *)this + 83) = 1;
    if ( VolumeFromFilePath )
    {
LABEL_77:
      v29 = GetCurrentThreadId();
      v11 = FrsStatusList::PushNewError(
              v26,
              *((unsigned int *)VolumeFromFilePath + 1),
              *((unsigned int *)VolumeFromFilePath + 2),
              *(unsigned int *)VolumeFromFilePath,
              "base\\fs\\remotefs\\frs\\src\\sync\\frsreplicator.cpp",
              "FrsReplicator::DeleteSysVolContents",
              1665,
              v29,
              VolumeFromFilePath);
LABEL_78:
      v3 = v11;
    }
  }
  Config::SYSVOL_PARAMETERS::~SYSVOL_PARAMETERS((Config::SYSVOL_PARAMETERS *)v47);
  ScopedLock::~ScopedLock((ScopedLock *)v44);
  return (struct FrsStatus *)v3;
}

```

## disassembly

```asm
0x1400eb170  mov     [rsp-8+arg_8], rbx
0x1400eb175  mov     [rsp-8+arg_10], rsi
0x1400eb17a  mov     [rsp-8+arg_18], rdi
0x1400eb17f  push    rbp
0x1400eb180  push    r12
0x1400eb182  push    r13
0x1400eb184  push    r14
0x1400eb186  push    r15
0x1400eb188  lea     rbp, [rsp-80h]
0x1400eb18d  sub     rsp, 180h
0x1400eb194  mov     rax, cs:__security_cookie
0x1400eb19b  xor     rax, rsp
0x1400eb19e  mov     [rbp+0A0h+var_30], rax
0x1400eb1a2  mov     r15, rcx
0x1400eb1a5  lea     rdx, [rcx+150h]; struct ScopedCS *
0x1400eb1ac  lea     rcx, [rbp+0A0h+var_E0]; this
0x1400eb1b0  call    ??0ScopedLock@@QEAA@AEAVScopedCS@@@Z; ScopedLock::ScopedLock(ScopedCS &)
0x1400eb1b5  nop
0x1400eb1b6  lea     rax, ??_7RegReader@Config@@6B@; const Config::RegReader::`vftable'
0x1400eb1bd  mov     [rbp+0A0h+var_F0], rax
0x1400eb1c1  lea     rax, ??_7RegWriter@Config@@6B@; const Config::RegWriter::`vftable'
0x1400eb1c8  mov     [rbp+0A0h+var_E8], rax
0x1400eb1cc  lea     rcx, [rbp+0A0h+var_90]; this
0x1400eb1d0  call    ??0SYSVOL_PARAMETERS@Config@@QEAA@XZ; Config::SYSVOL_PARAMETERS::SYSVOL_PARAMETERS(void)
0x1400eb1d5  nop
0x1400eb1d6  lea     r13, aFrsreplicatorD; "FrsReplicator::DeleteSysVolContents"
0x1400eb1dd  lea     r14, aFrep; "FREP"
0x1400eb1e4  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400eb1eb  xor     ebx, ebx
0x1400eb1ed  test    rax, rax
0x1400eb1f0  jz      short loc_1400EB22E
0x1400eb1f2  cmp     [rax+40h], ebx
0x1400eb1f5  jz      short loc_1400EB22E
0x1400eb1f7  cmp     dword ptr [rax+38h], 5
0x1400eb1fb  jl      short loc_1400EB22E
0x1400eb1fd  mov     [rsp+1A0h+var_130], r13
0x1400eb202  mov     [rsp+1A0h+var_128], 5CDh
0x1400eb20a  mov     [rsp+1A0h+var_124], 5
0x1400eb212  mov     [rbp+0A0h+var_120], r14
0x1400eb216  lea     r8, [r15+14Ch]
0x1400eb21d  lea     rdx, aIssysvoldelete; "IsSysVolDeleted: %d"
0x1400eb224  lea     rcx, [rsp+1A0h+var_130]
0x1400eb229  call    ??$DbgPrint@GH@dbgobj@@QEAA_KPEBGAEBH@Z; dbgobj::DbgPrint<ushort,int>(ushort const *,int const &)
0x1400eb22e  cmp     [r15+14Ch], ebx
0x1400eb235  jnz     loc_1400EB87B
0x1400eb23b  lea     rdx, aDemotingSysvol; "Demoting SysVols"
0x1400eb242  call    ?IsSysVolCommitFlagSet@RegReader@Config@@QEAAHPEBG@Z; Config::RegReader::IsSysVolCommitFlagSet(ushort const *)
0x1400eb247  test    eax, eax
0x1400eb249  jz      loc_1400EB87B
0x1400eb24f  lea     r8, [rbp+0A0h+var_90]; struct Config::SYSVOL_PARAMETERS *
0x1400eb253  lea     rdx, aDemotingSysvol; "Demoting SysVols"
0x1400eb25a  call    ?ReadSysVolConfigValues@RegReader@Config@@QEAAPEAVFrsStatus@@PEBGAEAUSYSVOL_PARAMETERS@2@@Z; Config::RegReader::ReadSysVolConfigValues(ushort const *,Config::SYSVOL_PARAMETERS &)
0x1400eb25f  mov     rdi, rax
0x1400eb262  lea     rsi, aBaseFsRemotefs_17; "base\\fs\\remotefs\\frs\\src\\config\\r"...
0x1400eb269  test    rax, rax
0x1400eb26c  jz      short loc_1400EB2B0
0x1400eb26e  call    cs:__imp_GetCurrentThreadId
0x1400eb275  nop     dword ptr [rax+rax+00h]
0x1400eb27a  mov     [rsp+1A0h+var_160], rdi
0x1400eb27f  mov     [rsp+1A0h+var_168], eax
0x1400eb283  mov     [rsp+1A0h+var_170], 1BDh
0x1400eb28b  lea     rax, aConfigRegreade_0; "Config::RegReader::ReadDemotingSysVolCo"...
0x1400eb292  mov     [rsp+1A0h+var_178], rax
0x1400eb297  mov     [rsp+1A0h+var_180], rsi
0x1400eb29c  mov     r9d, [rdi]
0x1400eb29f  mov     r8d, [rdi+8]
0x1400eb2a3  mov     edx, [rdi+4]
0x1400eb2a6  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400eb2ab  mov     rdi, rax
0x1400eb2ae  jmp     short loc_1400EB2B3
0x1400eb2b0  mov     rdi, rbx
0x1400eb2b3  test    rdi, rdi
0x1400eb2b6  jz      short loc_1400EB31B
0x1400eb2b8  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400eb2bf  test    rax, rax
0x1400eb2c2  jz      short loc_1400EB2F9
0x1400eb2c4  cmp     [rax+40h], ebx
0x1400eb2c7  jz      short loc_1400EB2F9
0x1400eb2c9  mov     esi, 2
0x1400eb2ce  cmp     [rax+38h], esi
0x1400eb2d1  jl      short loc_1400EB2F9
0x1400eb2d3  mov     [rsp+1A0h+var_130], r13
0x1400eb2d8  mov     [rsp+1A0h+var_128], 5E0h
0x1400eb2e0  mov     [rsp+1A0h+var_124], esi
0x1400eb2e4  mov     [rbp+0A0h+var_120], r14
0x1400eb2e8  lea     rdx, aSysvolDemoting_1; "SYSVOL demoting registry values cannot "...
0x1400eb2ef  lea     rcx, [rsp+1A0h+var_130]
0x1400eb2f4  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1400eb2f9  call    cs:__imp_GetCurrentThreadId
0x1400eb300  nop     dword ptr [rax+rax+00h]
0x1400eb305  mov     [rsp+1A0h+var_160], rdi
0x1400eb30a  mov     [rsp+1A0h+var_168], eax
0x1400eb30e  mov     [rsp+1A0h+var_170], 5E1h
0x1400eb316  jmp     loc_1400EB851
0x1400eb31b  mov     rax, [rbp+0A0h+var_60]
0x1400eb31f  mov     r12d, 4
0x1400eb325  cmp     [rax+8], rbx
0x1400eb329  jbe     loc_1400EB696
0x1400eb32f  lea     rcx, [rbp+0A0h+var_D0]; this
0x1400eb333  call    ??0VolumeId@@QEAA@XZ; VolumeId::VolumeId(void)
0x1400eb338  nop
0x1400eb339  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400eb340  test    rax, rax
0x1400eb343  jz      short loc_1400EB378
0x1400eb345  cmp     [rax+40h], ebx
0x1400eb348  jz      short loc_1400EB378
0x1400eb34a  cmp     [rax+38h], r12d
0x1400eb34e  jl      short loc_1400EB378
0x1400eb350  mov     [rsp+1A0h+var_130], r13
0x1400eb355  mov     [rsp+1A0h+var_128], 5EBh
0x1400eb35d  mov     [rsp+1A0h+var_124], r12d
0x1400eb362  mov     [rbp+0A0h+var_120], r14
0x1400eb366  lea     r9, [rbp+0A0h+var_40]
0x1400eb36a  lea     r8, [rbp+0A0h+var_60]
0x1400eb36e  lea     rcx, [rsp+1A0h+var_130]
0x1400eb373  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@VGuid@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@AEBVGuid@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>,Guid>(ushort const *,FrsStringImpl<ushort,char> const &,Guid const &)
0x1400eb378  call    ?GetVolumeTable@ConfigContext@@QEAAPEAVVolumeIdTable@@XZ; ConfigContext::GetVolumeTable(void)
0x1400eb37d  lea     r8, [rbp+0A0h+var_D0]
0x1400eb381  lea     rdx, [rbp+0A0h+var_60]
0x1400eb385  mov     rcx, rax; this
0x1400eb388  call    ?FindVolumeFromFilePath@VolumeIdTable@@QEAAPEAVFrsStatus@@AEBV?$FrsStringImpl@GD@@AEAVVolumeId@@@Z; VolumeIdTable::FindVolumeFromFilePath(FrsStringImpl<ushort,char> const &,VolumeId &)
0x1400eb38d  mov     rdi, rax
0x1400eb390  mov     esi, 2
0x1400eb395  test    rax, rax
0x1400eb398  jz      short loc_1400EB3DA
0x1400eb39a  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400eb3a1  test    rax, rax
0x1400eb3a4  jz      short loc_1400EB3DA
0x1400eb3a6  cmp     [rax+40h], ebx
0x1400eb3a9  jz      short loc_1400EB3DA
0x1400eb3ab  cmp     [rax+38h], esi
0x1400eb3ae  jl      short loc_1400EB3DA
0x1400eb3b0  mov     [rsp+1A0h+var_130], r13
0x1400eb3b5  mov     [rsp+1A0h+var_128], 5F8h
0x1400eb3bd  mov     [rsp+1A0h+var_124], esi
0x1400eb3c1  mov     [rbp+0A0h+var_120], r14
0x1400eb3c5  lea     r8, [rbp+0A0h+var_60]
0x1400eb3c9  lea     rdx, aSysvolFailedTo_9; "[SYSVOL] Failed to get volume informati"...
0x1400eb3d0  lea     rcx, [rsp+1A0h+var_130]
0x1400eb3d5  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>>(ushort const *,FrsStringImpl<ushort,char> const &)
0x1400eb3da  test    rdi, rdi
0x1400eb3dd  jnz     loc_1400EB686
0x1400eb3e3  lea     rcx, [rsp+1A0h+var_130]; this
0x1400eb3e8  call    ??0Win32FilePath@@QEAA@XZ; Win32FilePath::Win32FilePath(void)
0x1400eb3ed  nop
0x1400eb3ee  lea     rcx, [rbp+0A0h+var_100]; this
0x1400eb3f2  call    ??0Win32FilePath@@QEAA@XZ; Win32FilePath::Win32FilePath(void)
0x1400eb3f7  nop
0x1400eb3f8  lea     rdx, [rbp+0A0h+var_60]
0x1400eb3fc  lea     rcx, [rsp+1A0h+var_130]
0x1400eb401  call    ?SetNoConvert@Win32FilePath@@QEAAPEAVFrsStatus@@AEBV?$FrsStringImpl@GD@@@Z; Win32FilePath::SetNoConvert(FrsStringImpl<ushort,char> const &)
0x1400eb406  mov     rdi, rax
0x1400eb409  mov     [rsp+1A0h+var_138], rax
0x1400eb40e  mov     r14, rax
0x1400eb411  test    rax, rax
0x1400eb414  jnz     short loc_1400EB480
0x1400eb416  lea     rdx, [rbp+0A0h+var_100]; struct Win32FilePath *
0x1400eb41a  lea     rcx, [rsp+1A0h+var_130]; this
0x1400eb41f  call    ?GetVolumeMountPointRelativePath@Win32FilePath@@QEAAPEAVFrsStatus@@AEAV1@@Z; Win32FilePath::GetVolumeMountPointRelativePath(Win32FilePath &)
0x1400eb424  mov     rdi, rax
0x1400eb427  mov     [rsp+1A0h+var_138], rax
0x1400eb42c  mov     r14, rax
0x1400eb42f  test    rax, rax
0x1400eb432  jnz     short loc_1400EB480
0x1400eb434  lea     rdx, Delimiter; "\\"
0x1400eb43b  lea     rcx, [rbp+0A0h+var_118]
0x1400eb43f  call    ??0?$FrsStringImpl@GD@@QEAA@PEBG@Z; FrsStringImpl<ushort,char>::FrsStringImpl<ushort,char>(ushort const *)
0x1400eb444  nop
0x1400eb445  mov     rdx, [rbp+0A0h+var_F8]
0x1400eb449  add     rdx, 12h
0x1400eb44d  lea     rcx, [rbp+0A0h+var_118]
0x1400eb451  call    ?Append@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Append(ushort const *)
0x1400eb456  lea     r8, [rbp+0A0h+var_118]
0x1400eb45a  lea     rdx, [rbp+0A0h+var_D0]
0x1400eb45e  call    ?RemoveContentSetRoot@FrsReadOnlyFilter@@QEAAPEAVFrsStatus@@AEBVVolumeId@@AEAV?$FrsStringImpl@GD@@@Z; FrsReadOnlyFilter::RemoveContentSetRoot(VolumeId const &,FrsStringImpl<ushort,char> &)
0x1400eb463  mov     rdi, rax
0x1400eb466  mov     r14, rax
0x1400eb469  mov     [rsp+1A0h+var_138], rax
0x1400eb46e  lea     rcx, [rbp+0A0h+var_118]
0x1400eb472  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1400eb477  test    r14, r14
0x1400eb47a  jz      loc_1400EB54C
0x1400eb480  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400eb487  cmp     dword ptr [r14+4], 3
0x1400eb48c  jz      short loc_1400EB4DD
0x1400eb48e  test    rax, rax
0x1400eb491  jz      loc_1400EB53A
0x1400eb497  cmp     [rax+40h], ebx
0x1400eb49a  jz      loc_1400EB53A
0x1400eb4a0  lea     r14, aFrep; "FREP"
0x1400eb4a7  cmp     [rax+38h], esi
0x1400eb4aa  jl      loc_1400EB541
0x1400eb4b0  mov     [rsp+1A0h+var_150], r13
0x1400eb4b5  mov     [rsp+1A0h+var_148], 613h
0x1400eb4bd  mov     [rsp+1A0h+var_144], esi
0x1400eb4c1  mov     [rsp+1A0h+var_140], r14
0x1400eb4c6  lea     r8, [rbp+0A0h+var_60]
0x1400eb4ca  lea     rdx, aSysvolFailedTo_13; "[SYSVOL] Failed to remove sysvol root p"...
0x1400eb4d1  lea     rcx, [rsp+1A0h+var_150]
0x1400eb4d6  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>>(ushort const *,FrsStringImpl<ushort,char> const &)
0x1400eb4db  jmp     short loc_1400EB541
0x1400eb4dd  test    rax, rax
0x1400eb4e0  jz      short loc_1400EB522
0x1400eb4e2  cmp     [rax+40h], ebx
0x1400eb4e5  jz      short loc_1400EB522
0x1400eb4e7  lea     r14, aFrep; "FREP"
0x1400eb4ee  cmp     [rax+38h], r12d
0x1400eb4f2  jl      short loc_1400EB529
0x1400eb4f4  mov     [rsp+1A0h+var_150], r13
0x1400eb4f9  mov     [rsp+1A0h+var_148], 618h
0x1400eb501  mov     [rsp+1A0h+var_144], r12d
0x1400eb506  mov     [rsp+1A0h+var_140], r14
0x1400eb50b  lea     r8, [rbp+0A0h+var_60]
0x1400eb50f  lea     rdx, aSysvolPathAlre; "[SYSVOL] Path already removed from Driv"...
0x1400eb516  lea     rcx, [rsp+1A0h+var_150]
0x1400eb51b  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>>(ushort const *,FrsStringImpl<ushort,char> const &)
0x1400eb520  jmp     short loc_1400EB529
0x1400eb522  lea     r14, aFrep; "FREP"
0x1400eb529  lea     rcx, [rsp+1A0h+var_138]; struct FrsStatus **
0x1400eb52e  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1400eb533  mov     rdi, [rsp+1A0h+var_138]
0x1400eb538  jmp     short loc_1400EB541
0x1400eb53a  lea     r14, aFrep; "FREP"
0x1400eb541  test    rdi, rdi
0x1400eb544  jnz     loc_1400EB64A
0x1400eb54a  jmp     short loc_1400EB553
0x1400eb54c  lea     r14, aFrep; "FREP"
0x1400eb553  mov     dword ptr [rsp+1A0h+var_138], ebx
0x1400eb557  mov     [rbp+0A0h+var_118], rbx
0x1400eb55b  lea     rcx, [r15+8]; this
0x1400eb55f  lea     r8, [rbp+0A0h+var_118]; struct VolumeManager **
0x1400eb563  lea     rdx, [rbp+0A0h+var_D0]; struct VolumeId *
0x1400eb567  call    ?Find@VolumeManagerMap@@QEAAHAEBVVolumeId@@AEAPEAVVolumeManager@@@Z; VolumeManagerMap::Find(VolumeId const &,VolumeManager * &)
0x1400eb56c  test    eax, eax
0x1400eb56e  jnz     short loc_1400EB5CA
0x1400eb570  mov     [rbp+0A0h+var_108], rbx
0x1400eb574  mov     [rbp+0A0h+var_110], rbx
0x1400eb578  lea     rdx, [rbp+0A0h+var_C0]; struct _GUID *
0x1400eb57c  mov     rcx, cs:?g_ConfigContext@@3PEAVConfigContext@@EA; this
0x1400eb583  call    ?GetVolume@ConfigContext@@QEAAPEAVVolume@Config@@PEBU_GUID@@@Z; ConfigContext::GetVolume(_GUID const *)
0x1400eb588  mov     [rbp+0A0h+var_110], rax
0x1400eb58c  mov     r8, [r15+138h]; struct TaskPool *
0x1400eb593  mov     rdx, rax; struct Config::Volume *
0x1400eb596  lea     rcx, [rbp+0A0h+var_D0]; struct VolumeId *
0x1400eb59a  call    ?CreateLightVolumeManager@FrsReplicator@@KAPEAVLightVolumeManager@@AEBVVolumeId@@PEAVVolume@Config@@PEAVTaskPool@@@Z; FrsReplicator::CreateLightVolumeManager(VolumeId const &,Config::Volume *,TaskPool *)
0x1400eb59f  mov     [rbp+0A0h+var_108], rax
0x1400eb5a3  lea     r8, [rsp+1A0h+var_138]; unsigned int *
0x1400eb5a8  lea     rdx, [rbp+0A0h+var_40]; struct _GUID *
0x1400eb5ac  mov     rcx, rax; this
0x1400eb5af  call    ?GetNumberOfReadOnlyContentSetsInDb@LightVolumeManager@@QEAAPEAVFrsStatus@@AEBU_GUID@@AEAK@Z; LightVolumeManager::GetNumberOfReadOnlyContentSetsInDb(_GUID const &,ulong &)
0x1400eb5b4  nop
0x1400eb5b5  lea     rcx, [rbp+0A0h+var_110]
0x1400eb5b9  call    ??1?$ScopedRef@VReplicaSet@Config@@@@QEAA@XZ; ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(void)
0x1400eb5be  nop
0x1400eb5bf  lea     rcx, [rbp+0A0h+var_108]
0x1400eb5c3  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x1400eb5c8  jmp     short loc_1400EB5DF
0x1400eb5ca  lea     r8, [rsp+1A0h+var_138]; unsigned int *
0x1400eb5cf  lea     rdx, [rbp+0A0h+var_40]; struct _GUID *
0x1400eb5d3  mov     rcx, [rbp+0A0h+var_118]; this
0x1400eb5d7  call    ?GetNumberOfReadOnlyContentSetsInDb@VolumeManager@@QEAAPEAVFrsStatus@@AEBU_GUID@@AEAK@Z; VolumeManager::GetNumberOfReadOnlyContentSetsInDb(_GUID const &,ulong &)
0x1400eb5dc  mov     rdi, rax
0x1400eb5df  test    rdi, rdi
0x1400eb5e2  jnz     short loc_1400EB640
0x1400eb5e4  cmp     dword ptr [rsp+1A0h+var_138], ebx
0x1400eb5e8  jnz     short loc_1400EB640
0x1400eb5ea  lea     rdx, [rbp+0A0h+var_D0]; struct VolumeId *
0x1400eb5ee  call    ?DetachDriver@FrsReadOnlyFilter@@QEAAPEAVFrsStatus@@AEBVVolumeId@@@Z; FrsReadOnlyFilter::DetachDriver(VolumeId const &)
0x1400eb5f3  mov     rdi, rax
0x1400eb5f6  test    rax, rax
0x1400eb5f9  jz      short loc_1400EB640
0x1400eb5fb  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400eb602  test    rax, rax
0x1400eb605  jz      short loc_1400EB640
0x1400eb607  cmp     [rax+40h], ebx
0x1400eb60a  jz      short loc_1400EB640
0x1400eb60c  cmp     [rax+38h], esi
0x1400eb60f  jl      short loc_1400EB640
0x1400eb611  mov     [rsp+1A0h+var_150], r13
0x1400eb616  mov     [rsp+1A0h+var_148], 645h
0x1400eb61e  mov     [rsp+1A0h+var_144], esi
0x1400eb622  mov     [rsp+1A0h+var_140], r14
0x1400eb627  mov     r9, rdi
0x1400eb62a  lea     r8, [rbp+0A0h+var_D0]
0x1400eb62e  lea     rdx, aFailedDetachdr_0; "Failed DetachDriver for VolumeId:%? Err"...
0x1400eb635  lea     rcx, [rsp+1A0h+var_150]
0x1400eb63a  call    ??$DbgPrint@GVVolumeId@@VFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVVolumeId@@AEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,VolumeId,FrsStatus>(ushort const *,VolumeId const &,FrsStatus const &)
0x1400eb63f  nop
0x1400eb640  lea     rcx, [rbp+0A0h+var_118]
0x1400eb644  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x1400eb649  nop
0x1400eb64a  lea     rsi, ??_7BaseFilePath@@6B@; const BaseFilePath::`vftable'
0x1400eb651  mov     [rbp+0A0h+var_100], rsi
0x1400eb655  lea     rcx, [rbp+0A0h+var_F8]
0x1400eb659  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1400eb65e  nop
0x1400eb65f  mov     [rsp+1A0h+var_130], rsi
0x1400eb664  lea     rcx, [rsp+1A0h+var_128]
0x1400eb669  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1400eb66e  test    rdi, rdi
  ... truncated ...
```
