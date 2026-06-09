# ClusteredVolumeMarkAndSweepTask::Step(void)

- ea: `0x140141910`
- end: `0x14014230d`
- name: `?Step@ClusteredVolumeMarkAndSweepTask@@UEAA?AW4STEP_RESULT@Task@@XZ`
- size: `2557`
- prototype: ``
- caller_count: `0`
- callee_count: `39`
- tags: `reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1400036a0`
- `0x14000c910`
- `0x14000e34c`
- `0x14000ee94`
- `0x140011408`
- `0x14001c264`
- `0x14001c31c`
- `0x14001cfa0`
- `0x14001d07c`
- `0x14001d094`
- `0x14001d7bc`
- `0x14001e19c`
- `0x140023794`
- `0x14002383c`
- `0x1400238e4`
- `0x1400255c8`
- `0x14002a820`
- `0x140089080`
- `0x140141300`
- `0x14014140c`
- `0x140141910`
- `0x1401b3d14`
- `0x1401b9470`
- `0x1401b9494`
- `0x1401c0780`
- `0x1401c0b7c`
- `0x1401c1e48`
- `0x1401c27b4`
- `0x1401ccb8c`
- `0x1401cd328`
- `0x1401cd6c8`
- `0x1401cd9ac`
- `0x1401cdbf8`
- `0x1401cff90`
- `0x1401d02d8`
- `0x1401d2964`
- `0x1401d4808`
- `0x1401d59b0`
- `0x1401d6454`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140141c1f`
- `KERNEL32!GetCurrentThreadId` at `0x140141cf4`
- `KERNEL32!GetCurrentThreadId` at `0x140141e09`
- `KERNEL32!GetCurrentThreadId` at `0x140141f02`
- `KERNEL32!GetCurrentThreadId` at `0x140142047`
- `KERNEL32!GetCurrentThreadId` at `0x140141c1f`
- `KERNEL32!GetCurrentThreadId` at `0x140141cf4`
- `KERNEL32!GetCurrentThreadId` at `0x140141e09`
- `KERNEL32!GetCurrentThreadId` at `0x140141f02`
- `KERNEL32!GetCurrentThreadId` at `0x140142047`

## string_xrefs

- `0x140141d76`: `Replicated Folder Root Path`
- `0x140141df8`: `Failed to retrieve the DFS Replicated Folder resource's Replicated Folder Root Path property`
- `0x140141981`: `ClusteredVolumeMarkAndSweepTask::Step`
- `0x140141be6`: `ClusteredVolumeMarkAndSweepTask::Step`
- `0x140141cb7`: `ClusteredVolumeMarkAndSweepTask::Step`
- `0x140141dd3`: `ClusteredVolumeMarkAndSweepTask::Step`
- `0x140141ecc`: `ClusteredVolumeMarkAndSweepTask::Step`
- `0x140142007`: `ClusteredVolumeMarkAndSweepTask::Step`
- `0x1401420d1`: `ClusteredVolumeMarkAndSweepTask::Step`
- `0x14014221a`: `ClusteredVolumeMarkAndSweepTask::Step`
- `0x1401419d7`: `Clustered volume mark and sweep task for volId:%? volPath:%?`
- `0x140141c48`: `base\fs\remotefs\frs\src\sync\markandsweeptask.cpp`
- `0x140141d1d`: `base\fs\remotefs\frs\src\sync\markandsweeptask.cpp`
- `0x140141e33`: `base\fs\remotefs\frs\src\sync\markandsweeptask.cpp`
- `0x140141f2b`: `base\fs\remotefs\frs\src\sync\markandsweeptask.cpp`
- `0x140142070`: `base\fs\remotefs\frs\src\sync\markandsweeptask.cpp`
- `0x140141c3c`: `ClusteredVolumeMarkAndSweepTask::Step`
- `0x140141d11`: `ClusteredVolumeMarkAndSweepTask::Step`
- `0x140141e27`: `ClusteredVolumeMarkAndSweepTask::Step`
- `0x140141f1f`: `ClusteredVolumeMarkAndSweepTask::Step`
- `0x140142064`: `ClusteredVolumeMarkAndSweepTask::Step`
- `0x140142266`: `[CLUSTER] Cluster service is not installed or configured. Skipping the clustered mark and sweep.`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall ClusteredVolumeMarkAndSweepTask::Step(__int64 a1)
{
  char v2; // r14
  int v3; // r15d
  unsigned int v4; // r12d
  struct FrsReadOnlyFilter *v5; // rdx
  struct FrsStatus *ComputerNameW; // rdi
  char v7; // al
  int v8; // r13d
  int v9; // ecx
  const struct Cluster::ClusterResource *i; // rbx
  __int64 v11; // rax
  DWORD CurrentThreadId; // eax
  __int64 v13; // rcx
  DWORD v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  DWORD v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rax
  bool v21; // r14
  DWORD v22; // eax
  __int64 v23; // rcx
  DWORD v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rcx
  FrsReadOnlyFilter *v28; // rcx
  struct FrsStatus *v30; // [rsp+58h] [rbp-B0h] BYREF
  const wchar_t *v31; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+68h] [rbp-A0h]
  const wchar_t *v33; // [rsp+70h] [rbp-98h]
  int v34; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v35[8]; // [rsp+80h] [rbp-88h] BYREF
  const wchar_t *v36; // [rsp+88h] [rbp-80h] BYREF
  int v37; // [rsp+90h] [rbp-78h]
  int v38; // [rsp+94h] [rbp-74h]
  const wchar_t *v39; // [rsp+98h] [rbp-70h]
  unsigned __int16 *v40; // [rsp+A0h] [rbp-68h] BYREF
  unsigned __int16 *v41; // [rsp+A8h] [rbp-60h] BYREF
  unsigned __int16 *v42; // [rsp+B0h] [rbp-58h] BYREF
  void **v43; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v44[24]; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v45; // [rsp+D8h] [rbp-30h] BYREF
  unsigned __int16 *v46; // [rsp+E0h] [rbp-28h] BYREF
  void **v47; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v48; // [rsp+F0h] [rbp-18h] BYREF
  void **v49; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v50; // [rsp+100h] [rbp-8h] BYREF
  __int64 v51; // [rsp+108h] [rbp+0h] BYREF
  _BYTE v52[8]; // [rsp+110h] [rbp+8h] BYREF
  _BYTE v53[8]; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v54[8]; // [rsp+120h] [rbp+18h] BYREF
  FrsReadOnlyFilter *v55; // [rsp+128h] [rbp+20h] BYREF
  const wchar_t *v56; // [rsp+130h] [rbp+28h] BYREF
  int v57; // [rsp+138h] [rbp+30h]
  int v58; // [rsp+13Ch] [rbp+34h]
  const wchar_t *v59; // [rsp+140h] [rbp+38h]
  _BYTE v60[8]; // [rsp+148h] [rbp+40h] BYREF
  _BYTE v61[8]; // [rsp+150h] [rbp+48h] BYREF
  _BYTE v62[48]; // [rsp+158h] [rbp+50h] BYREF
  __int128 v63; // [rsp+188h] [rbp+80h] BYREF

  v2 = 0;
  v3 = 0;
  v34 = 0;
  v4 = 2;
  v30 = 0;
  v42 = &FrsStringImpl<unsigned short,char>::s_Empty;
  if ( !byte_140315A80 )
    _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v56 = L"ClusteredVolumeMarkAndSweepTask::Step";
    v57 = 653;
    v58 = 4;
    v59 = L"CMST";
    v51 = *(_QWORD *)(a1 + 240) + 18LL;
    dbgobj::DbgPrint<unsigned short,_GUID,unsigned short const *>(
      &v56,
      L"Clustered volume mark and sweep task for volId:%? volPath:%?",
      a1 + 248,
      &v51);
  }
  if ( !*(_DWORD *)(a1 + 48) )
  {
    ComputerNameW = (struct FrsStatus *)System::GetComputerNameW(&v42);
    v30 = ComputerNameW;
    if ( ComputerNameW )
      goto LABEL_114;
    if ( !*(_DWORD *)(a1 + 48) )
    {
      ScopedMarkAndSweepLock::ScopedMarkAndSweepLock((ScopedMarkAndSweepLock *)&v55, v5);
      if ( !*(_DWORD *)(a1 + 48) )
      {
        ComputerNameW = FrsReadOnlyFilter::SendStartPrefixConfig(
                          g_FrsReadOnlyFilter,
                          (const struct VolumeId *)(a1 + 232));
        v30 = ComputerNameW;
      }
      v46 = &FrsStringImpl<unsigned short,char>::s_Empty;
      v7 = byte_140315A80;
      if ( !byte_140315A80 )
      {
        _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
        ComputerNameW = v30;
        v7 = 0;
      }
      v41 = &FrsStringImpl<unsigned short,char>::s_Empty;
      if ( !v7 )
      {
        _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
        ComputerNameW = v30;
        v7 = byte_140315A80;
      }
      v40 = &FrsStringImpl<unsigned short,char>::s_Empty;
      if ( !v7 )
      {
        _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
        ComputerNameW = v30;
      }
      v34 = 0;
      v8 = 0;
      Win32FilePath::Win32FilePath((Win32FilePath *)&v49);
      v63 = 0;
      std::vector<VolumeInfo *>::vector<VolumeInfo *>(&v36);
      if ( !ComputerNameW )
      {
        Cluster::ClusterResourceFilter::ClusterResourceFilter(&v31, &v42);
        ComputerNameW = (struct FrsStatus *)Cluster::ClusterUtil::GetClusterResources(
                                              v9,
                                              1,
                                              (unsigned int)&v31,
                                              1,
                                              (__int64)&v36);
        v30 = ComputerNameW;
        Cluster::ClusterResourceFilter::~ClusterResourceFilter((Cluster::ClusterResourceFilter *)&v31);
        if ( !ComputerNameW )
        {
          for ( i = *(const struct Cluster::ClusterResource **)std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(
                                                                 &v36,
                                                                 v60);
                !ComputerNameW && !*(_DWORD *)(a1 + 48);
                i = (const struct Cluster::ClusterResource *)((char *)i + 48) )
          {
            if ( i == *(const struct Cluster::ClusterResource **)std::vector<ServiceInfo *>::end(&v36, v61) )
            {
              ComputerNameW = FrsReadOnlyFilter::SendStopPrefixConfig(
                                g_FrsReadOnlyFilter,
                                (const struct VolumeId *)(a1 + 232));
              v30 = ComputerNameW;
              if ( !ComputerNameW && !*(_DWORD *)(a1 + 48) && !v8 )
              {
                ComputerNameW = FrsReadOnlyFilter::DetachDriver(v28, (const struct VolumeId *)(a1 + 232));
                v30 = ComputerNameW;
              }
              break;
            }
            FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v35, L"\\");
            Cluster::ClusterResource::ClusterResource((Cluster::ClusterResource *)v62, i);
            Cluster::ResourcePrivatePropertyList::ResourcePrivatePropertyList((Cluster::ResourcePrivatePropertyList *)&v43);
            ComputerNameW = Cluster::ClusterResource::GetResourceProperties(
                              (Cluster::ClusterResource *)v62,
                              (struct Cluster::ResourcePrivatePropertyList *)&v43);
            v30 = ComputerNameW;
            if ( !ComputerNameW && !*(_DWORD *)(a1 + 48) )
            {
              v11 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v52, L"Volume ID");
              v3 |= 1u;
              if ( !(unsigned int)Cluster::ResourcePrivatePropertyList::GetStringPropertyValue(&v43, v11, &v41) )
                v2 = 1;
            }
            if ( (v3 & 1) != 0 )
            {
              v3 &= ~1u;
              FrsStringImpl<char,unsigned short>::ReleaseBody(v52);
            }
            if ( v2 )
            {
              v2 = 0;
              if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
              {
                v31 = L"ClusteredVolumeMarkAndSweepTask::Step";
                v32 = 0x3000002DELL;
                v33 = L"CMST";
                dbgobj::DbgPrint<unsigned short>(
                  &v31,
                  L"(Ignored) Failed to retrieve the resource's Volume ID property.");
              }
              CurrentThreadId = GetCurrentThreadId();
              ComputerNameW = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                    v13,
                                                    9230,
                                                    0,
                                                    3,
                                                    "base\\fs\\remotefs\\frs\\src\\sync\\markandsweeptask.cpp",
                                                    "ClusteredVolumeMarkAndSweepTask::Step",
                                                    736,
                                                    CurrentThreadId,
                                                    0);
              v30 = ComputerNameW;
            }
            else
            {
              v2 = 0;
            }
            if ( !ComputerNameW && !*(_DWORD *)(a1 + 48) )
            {
              if ( (unsigned int)Guid::StringToGuid(&v41, &v63) )
                goto LABEL_115;
              if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
              {
                v31 = L"ClusteredVolumeMarkAndSweepTask::Step";
                v32 = 0x3000002E6LL;
                v33 = L"CMST";
                dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
                  &v31,
                  L"(Ignored) The resource's Volume ID property contains an invalid GUID value. propVal:%?",
                  &v46);
              }
              v14 = GetCurrentThreadId();
              ComputerNameW = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                    v15,
                                                    9231,
                                                    0,
                                                    3,
                                                    "base\\fs\\remotefs\\frs\\src\\sync\\markandsweeptask.cpp",
                                                    "ClusteredVolumeMarkAndSweepTask::Step",
                                                    745,
                                                    v14,
                                                    0);
              v30 = ComputerNameW;
              if ( !ComputerNameW )
              {
LABEL_115:
                if ( !*(_DWORD *)(a1 + 48) )
                {
                  v16 = v63 - *(_QWORD *)(a1 + 248);
                  if ( (_QWORD)v63 == *(_QWORD *)(a1 + 248) )
                    v16 = *((_QWORD *)&v63 + 1) - *(_QWORD *)(a1 + 256);
                  if ( v16 )
                    goto LABEL_94;
                  v17 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(
                          v53,
                          L"Replicated Folder Root Path");
                  v3 |= 2u;
                  if ( !(unsigned int)Cluster::ResourcePrivatePropertyList::GetStringPropertyValue(&v43, v17, &v40) )
                    v2 = 1;
                }
              }
            }
            if ( (v3 & 2) != 0 )
            {
              v3 &= ~2u;
              FrsStringImpl<char,unsigned short>::ReleaseBody(v53);
            }
            if ( v2 )
            {
              if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
              {
                v31 = L"ClusteredVolumeMarkAndSweepTask::Step";
                v32 = 0x2000002FALL;
                v33 = L"CMST";
                dbgobj::DbgPrint<unsigned short>(
                  &v31,
                  L"Failed to retrieve the DFS Replicated Folder resource's Replicated Folder Root Path property");
              }
              v18 = GetCurrentThreadId();
              ComputerNameW = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                    v19,
                                                    9230,
                                                    0,
                                                    3,
                                                    "base\\fs\\remotefs\\frs\\src\\sync\\markandsweeptask.cpp",
                                                    "ClusteredVolumeMarkAndSweepTask::Step",
                                                    764,
                                                    v18,
                                                    0);
              v30 = ComputerNameW;
            }
            v21 = 0;
            if ( !ComputerNameW && !*(_DWORD *)(a1 + 48) )
            {
              v20 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(
                      v54,
                      L"Replicated Folder Flags");
              v3 |= 4u;
              if ( !(unsigned int)Cluster::ResourcePrivatePropertyList::GetDwordPropertyValue(&v43, v20, &v34) )
                v21 = 1;
            }
            if ( (v3 & 4) != 0 )
            {
              v3 &= ~4u;
              FrsStringImpl<char,unsigned short>::ReleaseBody(v54);
            }
            if ( v21 )
            {
              v2 = 0;
              if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
              {
                v31 = L"ClusteredVolumeMarkAndSweepTask::Step";
                v32 = 0x200000306LL;
                v33 = L"CMST";
                dbgobj::DbgPrint<unsigned short>(
                  &v31,
                  L"Failed to retrieve the DFS Replicated Folder resource's flags property");
              }
              v22 = GetCurrentThreadId();
              ComputerNameW = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                    v23,
                                                    9230,
                                                    0,
                                                    3,
                                                    "base\\fs\\remotefs\\frs\\src\\sync\\markandsweeptask.cpp",
                                                    "ClusteredVolumeMarkAndSweepTask::Step",
                                                    776,
                                                    v22,
                                                    0);
              v30 = ComputerNameW;
            }
            else
            {
              v2 = 0;
            }
            if ( !ComputerNameW && !*(_DWORD *)(a1 + 48) && (v34 & 1) != 0 )
            {
              Win32FilePath::Win32FilePath((Win32FilePath *)&v47);
              ComputerNameW = (struct FrsStatus *)Win32FilePath::SetNoConvert(&v47, &v40);
              v30 = ComputerNameW;
              if ( !ComputerNameW && !*(_DWORD *)(a1 + 48) )
              {
                FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(&v45, v48 + 18);
                if ( *(_QWORD *)(v45 + 8) )
                {
                  ComputerNameW = Win32FilePath::GetVolumeMountPointRelativePath(
                                    (Win32FilePath *)&v47,
                                    (struct Win32FilePath *)&v49);
                  v30 = ComputerNameW;
                  FrsStringImpl<unsigned short,char>::Append(v35, v50 + 18);
                }
                else
                {
                  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
                  {
                    v31 = L"ClusteredVolumeMarkAndSweepTask::Step";
                    v32 = 0x30000031DLL;
                    v33 = L"CMST";
                    dbgobj::DbgPrint<unsigned short,VolumeId>(
                      &v31,
                      L"Volume has a content set that is not yet initialized: volId:%?",
                      a1 + 232);
                  }
                  v24 = GetCurrentThreadId();
                  FrsStatusList::PushNewError(
                    v25,
                    9230,
                    0,
                    3,
                    "base\\fs\\remotefs\\frs\\src\\sync\\markandsweeptask.cpp",
                    "ClusteredVolumeMarkAndSweepTask::Step",
                    799,
                    v24,
                    0);
                }
                FrsStringImpl<char,unsigned short>::ReleaseBody(&v45);
              }
              v47 = &BaseFilePath::`vftable';
              FrsStringImpl<char,unsigned short>::ReleaseBody(&v48);
              if ( !ComputerNameW && !*(_DWORD *)(a1 + 48) )
              {
                if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
                {
                  v31 = L"ClusteredVolumeMarkAndSweepTask::Step";
                  v32 = 0x40000032DLL;
                  v33 = L"CMST";
                  dbgobj::DbgPrint<unsigned short,VolumeId,Win32FilePath>(&v31, v26, a1 + 232, &v49);
                }
                ComputerNameW = (struct FrsStatus *)FrsReadOnlyFilter::AddContentSetRoot(v27, a1 + 232, v35);
                v30 = ComputerNameW;
                if ( ComputerNameW )
                {
                  v43 = &ObjList<Cluster::ResourcePrivateProperty>::`vftable';
                  std::vector<Cluster::ResourcePrivateProperty>::_Tidy(v44);
                  Cluster::ClusterResource::~ClusterResource((Cluster::ClusterResource *)v62);
                  FrsStringImpl<char,unsigned short>::ReleaseBody(v35);
                  break;
                }
                ++v8;
              }
            }
LABEL_94:
            v43 = &ObjList<Cluster::ResourcePrivateProperty>::`vftable';
            std::vector<Cluster::ResourcePrivateProperty>::_Tidy(v44);
            Cluster::ClusterResource::~ClusterResource((Cluster::ClusterResource *)v62);
            FrsStringImpl<char,unsigned short>::ReleaseBody(v35);
          }
        }
      }
      std::vector<Cluster::ClusterResource>::_Tidy(&v36);
      v49 = &BaseFilePath::`vftable';
      FrsStringImpl<char,unsigned short>::ReleaseBody(&v50);
      FrsStringImpl<char,unsigned short>::ReleaseBody(&v40);
      FrsStringImpl<char,unsigned short>::ReleaseBody(&v41);
      FrsStringImpl<char,unsigned short>::ReleaseBody(&v46);
      FrsReadOnlyFilter::ReleaseMarkAndSweepLock(v55);
      if ( ComputerNameW )
      {
LABEL_114:
        if ( (unsigned int)FrsStatus::IsErrorClusterNotExist(ComputerNameW) )
        {
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            v36 = L"ClusteredVolumeMarkAndSweepTask::Step";
            v37 = 854;
            v38 = 4;
            v39 = L"CMST";
            dbgobj::DbgPrint<unsigned short>(
              &v36,
              L"[CLUSTER] Cluster service is not installed or configured. Skipping the clustered mark and sweep.");
          }
        }
        else if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
        {
          v36 = L"ClusteredVolumeMarkAndSweepTask::Step";
          v37 = 857;
          v38 = 3;
          v39 = L"CMST";
          dbgobj::DbgPrint<unsigned short,VolumeId,FrsStatus>(
            &v36,
            L"Failed to mark and sweep: volId:%? Error:%?",
            a1 + 232,
            ComputerNameW);
        }
        CLEAR_ERROR(&v30);
        v4 = 1;
      }
    }
  }
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v42);
  return v4;
}

```

## disassembly

```asm
0x140141910  mov     rax, rsp
0x140141913  mov     [rax+10h], rbx
0x140141917  mov     [rax+18h], rsi
0x14014191b  mov     [rax+20h], rdi
0x14014191f  push    rbp
0x140141920  push    r12
0x140141922  push    r13
0x140141924  push    r14
0x140141926  push    r15
0x140141928  lea     rbp, [rax-0C8h]
0x14014192f  sub     rsp, 1A0h
0x140141936  mov     rax, cs:__security_cookie
0x14014193d  xor     rax, rsp
0x140141940  mov     [rbp+0C0h+var_30], rax
0x140141947  mov     rsi, rcx
0x14014194a  xor     r14d, r14d
0x14014194d  mov     r15d, r14d
0x140141950  mov     [rsp+1C0h+var_150], r14d
0x140141955  lea     r12d, [r14+2]
0x140141959  mov     edi, r14d
0x14014195c  mov     [rsp+1C0h+var_170], r14
0x140141961  lea     rbx, ?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x140141968  mov     [rbp+0C0h+var_118], rbx
0x14014196c  cmp     cs:byte_140315A80, r14b
0x140141973  jnz     short loc_140141981
0x140141975  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x14014197c  mov     rdi, [rsp+1C0h+var_170]
0x140141981  lea     r13, aClusteredvolum_1; "ClusteredVolumeMarkAndSweepTask::Step"
0x140141988  lea     rcx, aCmst; "CMST"
0x14014198f  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140141996  test    rax, rax
0x140141999  jz      short loc_1401419E7
0x14014199b  cmp     [rax+40h], r14d
0x14014199f  jz      short loc_1401419E7
0x1401419a1  cmp     dword ptr [rax+38h], 4
0x1401419a5  jl      short loc_1401419E7
0x1401419a7  mov     [rbp+0C0h+var_98], r13
0x1401419ab  mov     [rbp+0C0h+var_90], 28Dh
0x1401419b2  mov     [rbp+0C0h+var_8C], 4
0x1401419b9  mov     [rbp+0C0h+var_88], rcx
0x1401419bd  mov     rax, [rsi+0F0h]
0x1401419c4  add     rax, 12h
0x1401419c8  mov     [rbp+0C0h+var_C0], rax
0x1401419cc  lea     r8, [rsi+0F8h]
0x1401419d3  lea     r9, [rbp+0C0h+var_C0]
0x1401419d7  lea     rdx, aClusteredVolum; "Clustered volume mark and sweep task fo"...
0x1401419de  lea     rcx, [rbp+0C0h+var_98]
0x1401419e2  call    ??$DbgPrint@GU_GUID@@PEBG@dbgobj@@QEAA_KPEBGAEBU_GUID@@AEBQEBG@Z; dbgobj::DbgPrint<ushort,_GUID,ushort const *>(ushort const *,_GUID const &,ushort const * const &)
0x1401419e7  cmp     [rsi+30h], r14d
0x1401419eb  jnz     loc_1401422D0
0x1401419f1  lea     rcx, [rbp+0C0h+var_118]
0x1401419f5  call    ?GetComputerNameW@System@@SAPEAVFrsStatus@@AEAV?$FrsStringImpl@GD@@@Z; System::GetComputerNameW(FrsStringImpl<ushort,char> &)
0x1401419fa  mov     rdi, rax
0x1401419fd  mov     [rsp+1C0h+var_170], rax
0x140141a02  test    rax, rax
0x140141a05  jnz     loc_140142221
0x140141a0b  cmp     [rsi+30h], r14d
0x140141a0f  jnz     loc_1401422D0
0x140141a15  lea     rcx, [rbp+0C0h+var_A0]; this
0x140141a19  call    ??0ScopedMarkAndSweepLock@@QEAA@PEAVFrsReadOnlyFilter@@@Z; ScopedMarkAndSweepLock::ScopedMarkAndSweepLock(FrsReadOnlyFilter *)
0x140141a1e  nop
0x140141a1f  cmp     [rsi+30h], r14d
0x140141a23  jnz     short loc_140141A40
0x140141a25  lea     rdx, [rsi+0E8h]; struct VolumeId *
0x140141a2c  mov     rcx, cs:?g_FrsReadOnlyFilter@@3PEAVFrsReadOnlyFilter@@EA; this
0x140141a33  call    ?SendStartPrefixConfig@FrsReadOnlyFilter@@QEAAPEAVFrsStatus@@AEBVVolumeId@@@Z; FrsReadOnlyFilter::SendStartPrefixConfig(VolumeId const &)
0x140141a38  mov     rdi, rax
0x140141a3b  mov     [rsp+1C0h+var_170], rax
0x140141a40  mov     [rbp+0C0h+var_E8], rbx
0x140141a44  mov     al, cs:byte_140315A80
0x140141a4a  test    al, al
0x140141a4c  jnz     short loc_140141A60
0x140141a4e  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x140141a55  mov     rdi, [rsp+1C0h+var_170]
0x140141a5a  mov     al, cs:byte_140315A80
0x140141a60  mov     [rbp+0C0h+var_120], rbx
0x140141a64  test    al, al
0x140141a66  jnz     short loc_140141A7A
0x140141a68  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x140141a6f  mov     rdi, [rsp+1C0h+var_170]
0x140141a74  mov     al, cs:byte_140315A80
0x140141a7a  mov     [rbp+0C0h+var_128], rbx
0x140141a7e  test    al, al
0x140141a80  jnz     short loc_140141A8E
0x140141a82  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x140141a89  mov     rdi, [rsp+1C0h+var_170]
0x140141a8e  mov     [rsp+1C0h+var_150], r14d
0x140141a93  mov     r13d, r14d
0x140141a96  lea     rcx, [rbp+0C0h+var_D0]; this
0x140141a9a  call    ??0Win32FilePath@@QEAA@XZ; Win32FilePath::Win32FilePath(void)
0x140141a9f  nop
0x140141aa0  xorps   xmm0, xmm0
0x140141aa3  movups  [rbp+0C0h+var_40], xmm0
0x140141aaa  lea     rcx, [rbp+0C0h+var_140]
0x140141aae  call    ??0?$vector@PEAVVolumeInfo@@V?$allocator@PEAVVolumeInfo@@@std@@@std@@QEAA@XZ; std::vector<VolumeInfo *>::vector<VolumeInfo *>(void)
0x140141ab3  nop
0x140141ab4  test    rdi, rdi
0x140141ab7  jnz     loc_1401421CB
0x140141abd  lea     rdx, [rbp+0C0h+var_118]
0x140141ac1  lea     rcx, [rsp+1C0h+var_168]
0x140141ac6  call    ??0ClusterResourceFilter@Cluster@@QEAA@PEBV?$FrsStringImpl@GD@@K@Z; Cluster::ClusterResourceFilter::ClusterResourceFilter(FrsStringImpl<ushort,char> const *,ulong)
0x140141acb  nop
0x140141acc  lea     rax, [rbp+0C0h+var_140]
0x140141ad0  mov     [rsp+1C0h+var_1A0], rax
0x140141ad5  lea     eax, [rdi+1]
0x140141ad8  mov     r9d, eax
0x140141adb  lea     r8, [rsp+1C0h+var_168]
0x140141ae0  mov     edx, eax
0x140141ae2  call    ?GetClusterResources@ClusterUtil@Cluster@@SAPEAVFrsStatus@@PEBGW4_ClusterResourceType@2@PEAVClusterResourceFilter@2@W4RetrievalErrorPolicy@2@AEAV?$vector@VClusterResource@Cluster@@V?$allocator@VClusterResource@Cluster@@@std@@@std@@@Z; Cluster::ClusterUtil::GetClusterResources(ushort const *,Cluster::_ClusterResourceType,Cluster::ClusterResourceFilter *,Cluster::RetrievalErrorPolicy,std::vector<Cluster::ClusterResource> &)
0x140141ae7  mov     rdi, rax
0x140141aea  mov     [rsp+1C0h+var_170], rax
0x140141aef  lea     rcx, [rsp+1C0h+var_168]; this
0x140141af4  call    ??1ClusterResourceFilter@Cluster@@QEAA@XZ; Cluster::ClusterResourceFilter::~ClusterResourceFilter(void)
0x140141af9  test    rdi, rdi
0x140141afc  jnz     loc_1401421CB
0x140141b02  lea     rdx, [rbp+0C0h+var_80]
0x140141b06  lea     rcx, [rbp+0C0h+var_140]
0x140141b0a  call    ?end@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@@std@@@3@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(void)
0x140141b0f  mov     rbx, [rax]
0x140141b12  test    rdi, rdi
0x140141b15  jnz     loc_1401421CB
0x140141b1b  cmp     [rsi+30h], r14d
0x140141b1f  jnz     loc_1401421CB
0x140141b25  lea     rdx, [rbp+0C0h+var_78]
0x140141b29  lea     rcx, [rbp+0C0h+var_140]
0x140141b2d  call    ?end@?$vector@PEAVServiceInfo@@V?$allocator@PEAVServiceInfo@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAVServiceInfo@@@std@@@std@@@2@XZ; std::vector<ServiceInfo *>::end(void)
0x140141b32  cmp     rbx, [rax]
0x140141b35  jz      loc_14014218C
0x140141b3b  lea     rdx, Delimiter; "\\"
0x140141b42  lea     rcx, [rsp+1C0h+var_148]
0x140141b47  call    ??0?$FrsStringImpl@GD@@QEAA@PEBG@Z; FrsStringImpl<ushort,char>::FrsStringImpl<ushort,char>(ushort const *)
0x140141b4c  nop
0x140141b4d  mov     rdx, rbx; struct Cluster::ClusterResource *
0x140141b50  lea     rcx, [rbp+0C0h+var_70]; this
0x140141b54  call    ??0ClusterResource@Cluster@@QEAA@AEBV01@@Z; Cluster::ClusterResource::ClusterResource(Cluster::ClusterResource const &)
0x140141b59  nop
0x140141b5a  lea     rcx, [rbp+0C0h+var_110]; this
0x140141b5e  call    ??0ResourcePrivatePropertyList@Cluster@@QEAA@XZ; Cluster::ResourcePrivatePropertyList::ResourcePrivatePropertyList(void)
0x140141b63  nop
0x140141b64  lea     rdx, [rbp+0C0h+var_110]; struct Cluster::ResourcePrivatePropertyList *
0x140141b68  lea     rcx, [rbp+0C0h+var_70]; this
0x140141b6c  call    ?GetResourceProperties@ClusterResource@Cluster@@QEBAPEAVFrsStatus@@AEAVResourcePrivatePropertyList@2@@Z; Cluster::ClusterResource::GetResourceProperties(Cluster::ResourcePrivatePropertyList &)
0x140141b71  mov     rdi, rax
0x140141b74  mov     [rsp+1C0h+var_170], rax
0x140141b79  test    rax, rax
0x140141b7c  jnz     short loc_140141BAF
0x140141b7e  cmp     [rsi+30h], r14d
0x140141b82  jnz     short loc_140141BAF
0x140141b84  lea     rdx, aVolumeId; "Volume ID"
0x140141b8b  lea     rcx, [rbp+0C0h+var_B8]
0x140141b8f  call    ??0?$FrsStringImpl@GD@@QEAA@PEBG@Z; FrsStringImpl<ushort,char>::FrsStringImpl<ushort,char>(ushort const *)
0x140141b94  or      r15d, 1
0x140141b98  lea     r8, [rbp+0C0h+var_120]
0x140141b9c  mov     rdx, rax
0x140141b9f  lea     rcx, [rbp+0C0h+var_110]
0x140141ba3  call    ?GetStringPropertyValue@ResourcePrivatePropertyList@Cluster@@QEBAHAEBV?$FrsStringImpl@GD@@AEAV3@@Z; Cluster::ResourcePrivatePropertyList::GetStringPropertyValue(FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> &)
0x140141ba8  test    eax, eax
0x140141baa  jnz     short loc_140141BAF
0x140141bac  mov     r14b, 1
0x140141baf  test    r15b, 1
0x140141bb3  jz      short loc_140141BC2
0x140141bb5  and     r15d, 0FFFFFFFEh
0x140141bb9  lea     rcx, [rbp+0C0h+var_B8]
0x140141bbd  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x140141bc2  test    r14b, r14b
0x140141bc5  jz      loc_140141C71
0x140141bcb  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140141bd2  xor     r14d, r14d
0x140141bd5  test    rax, rax
0x140141bd8  jz      short loc_140141C1F
0x140141bda  cmp     [rax+40h], r14d
0x140141bde  jz      short loc_140141C1F
0x140141be0  cmp     dword ptr [rax+38h], 3
0x140141be4  jl      short loc_140141C1F
0x140141be6  lea     rax, aClusteredvolum_1; "ClusteredVolumeMarkAndSweepTask::Step"
0x140141bed  mov     [rsp+1C0h+var_168], rax
0x140141bf2  mov     dword ptr [rsp+1C0h+var_160], 2DEh
0x140141bfa  mov     dword ptr [rsp+1C0h+var_160+4], 3
0x140141c02  lea     rax, aCmst; "CMST"
0x140141c09  mov     [rsp+1C0h+var_158], rax
0x140141c0e  lea     rdx, aIgnoredFailedT_73; "(Ignored) Failed to retrieve the resour"...
0x140141c15  lea     rcx, [rsp+1C0h+var_168]
0x140141c1a  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140141c1f  call    cs:__imp_GetCurrentThreadId
0x140141c26  nop     dword ptr [rax+rax+00h]
0x140141c2b  mov     [rsp+1C0h+var_180], r14
0x140141c30  mov     dword ptr [rsp+1C0h+var_188], eax
0x140141c34  mov     [rsp+1C0h+var_190], 2E0h
0x140141c3c  lea     rax, aClusteredvolum; "ClusteredVolumeMarkAndSweepTask::Step"
0x140141c43  mov     qword ptr [rsp+1C0h+var_198], rax
0x140141c48  lea     rax, aBaseFsRemotefs_65; "base\\fs\\remotefs\\frs\\src\\sync\\mar"...
0x140141c4f  mov     [rsp+1C0h+var_1A0], rax
0x140141c54  mov     r9d, 3
0x140141c5a  xor     r8d, r8d
0x140141c5d  mov     edx, 240Eh
0x140141c62  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140141c67  mov     rdi, rax
0x140141c6a  mov     [rsp+1C0h+var_170], rax
0x140141c6f  jmp     short loc_140141C74
0x140141c71  xor     r14d, r14d
0x140141c74  test    rdi, rdi
0x140141c77  jnz     loc_140141DA0
0x140141c7d  cmp     [rsi+30h], r14d
0x140141c81  jnz     loc_140141DA0
0x140141c87  lea     rdx, [rbp+0C0h+var_40]
0x140141c8e  lea     rcx, [rbp+0C0h+var_120]
0x140141c92  call    ?StringToGuid@Guid@@SAHAEBV?$FrsStringImpl@GD@@AEAU_GUID@@@Z; Guid::StringToGuid(FrsStringImpl<ushort,char> const &,_GUID &)
0x140141c97  test    eax, eax
0x140141c99  jnz     loc_140141D49
0x140141c9f  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140141ca6  test    rax, rax
0x140141ca9  jz      short loc_140141CF4
0x140141cab  cmp     [rax+40h], r14d
0x140141caf  jz      short loc_140141CF4
0x140141cb1  cmp     dword ptr [rax+38h], 3
0x140141cb5  jl      short loc_140141CF4
0x140141cb7  lea     rax, aClusteredvolum_1; "ClusteredVolumeMarkAndSweepTask::Step"
0x140141cbe  mov     [rsp+1C0h+var_168], rax
0x140141cc3  mov     dword ptr [rsp+1C0h+var_160], 2E6h
0x140141ccb  mov     dword ptr [rsp+1C0h+var_160+4], 3
0x140141cd3  lea     rax, aCmst; "CMST"
0x140141cda  mov     [rsp+1C0h+var_158], rax
0x140141cdf  lea     r8, [rbp+0C0h+var_E8]
0x140141ce3  lea     rdx, aIgnoredTheReso; "(Ignored) The resource's Volume ID prop"...
0x140141cea  lea     rcx, [rsp+1C0h+var_168]
0x140141cef  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>>(ushort const *,FrsStringImpl<ushort,char> const &)
0x140141cf4  call    cs:__imp_GetCurrentThreadId
0x140141cfb  nop     dword ptr [rax+rax+00h]
0x140141d00  mov     [rsp+1C0h+var_180], r14
0x140141d05  mov     dword ptr [rsp+1C0h+var_188], eax
0x140141d09  mov     [rsp+1C0h+var_190], 2E9h
0x140141d11  lea     rax, aClusteredvolum; "ClusteredVolumeMarkAndSweepTask::Step"
0x140141d18  mov     qword ptr [rsp+1C0h+var_198], rax
0x140141d1d  lea     rax, aBaseFsRemotefs_65; "base\\fs\\remotefs\\frs\\src\\sync\\mar"...
0x140141d24  mov     [rsp+1C0h+var_1A0], rax
0x140141d29  mov     r9d, 3
0x140141d2f  xor     r8d, r8d
0x140141d32  mov     edx, 240Fh
0x140141d37  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140141d3c  mov     rdi, rax
0x140141d3f  mov     [rsp+1C0h+var_170], rax
0x140141d44  test    rax, rax
0x140141d47  jnz     short loc_140141DA0
0x140141d49  cmp     [rsi+30h], r14d
0x140141d4d  jnz     short loc_140141DA0
0x140141d4f  mov     rax, qword ptr [rbp+0C0h+var_40]
0x140141d56  sub     rax, [rsi+0F8h]
0x140141d5d  jnz     short loc_140141D6D
0x140141d5f  mov     rax, qword ptr [rbp+0C0h+var_40+8]
0x140141d66  sub     rax, [rsi+100h]
0x140141d6d  test    rax, rax
0x140141d70  jnz     loc_14014212F
0x140141d76  lea     rdx, aReplicatedFold_0; "Replicated Folder Root Path"
0x140141d7d  lea     rcx, [rbp+0C0h+var_B0]
0x140141d81  call    ??0?$FrsStringImpl@GD@@QEAA@PEBG@Z; FrsStringImpl<ushort,char>::FrsStringImpl<ushort,char>(ushort const *)
0x140141d86  or      r15d, r12d
0x140141d89  lea     r8, [rbp+0C0h+var_128]
0x140141d8d  mov     rdx, rax
0x140141d90  lea     rcx, [rbp+0C0h+var_110]
0x140141d94  call    ?GetStringPropertyValue@ResourcePrivatePropertyList@Cluster@@QEBAHAEBV?$FrsStringImpl@GD@@AEAV3@@Z; Cluster::ResourcePrivatePropertyList::GetStringPropertyValue(FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> &)
0x140141d99  test    eax, eax
0x140141d9b  jnz     short loc_140141DA0
0x140141d9d  mov     r14b, 1
0x140141da0  test    r12b, r15b
0x140141da3  jz      short loc_140141DB2
0x140141da5  and     r15d, 0FFFFFFFDh
0x140141da9  lea     rcx, [rbp+0C0h+var_B0]
0x140141dad  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x140141db2  test    r14b, r14b
0x140141db5  jz      loc_140141E5A
0x140141dbb  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140141dc2  test    rax, rax
0x140141dc5  jz      short loc_140141E09
0x140141dc7  cmp     dword ptr [rax+40h], 0
0x140141dcb  jz      short loc_140141E09
0x140141dcd  cmp     [rax+38h], r12d
0x140141dd1  jl      short loc_140141E09
0x140141dd3  lea     rax, aClusteredvolum_1; "ClusteredVolumeMarkAndSweepTask::Step"
0x140141dda  mov     [rsp+1C0h+var_168], rax
0x140141ddf  mov     dword ptr [rsp+1C0h+var_160], 2FAh
0x140141de7  mov     dword ptr [rsp+1C0h+var_160+4], r12d
0x140141dec  lea     rax, aCmst; "CMST"
0x140141df3  mov     [rsp+1C0h+var_158], rax
0x140141df8  lea     rdx, aFailedToRetrie_9; "Failed to retrieve the DFS Replicated F"...
0x140141dff  lea     rcx, [rsp+1C0h+var_168]
0x140141e04  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140141e09  call    cs:__imp_GetCurrentThreadId
0x140141e10  nop     dword ptr [rax+rax+00h]
0x140141e15  and     [rsp+1C0h+var_180], 0
0x140141e1b  mov     dword ptr [rsp+1C0h+var_188], eax
0x140141e1f  mov     [rsp+1C0h+var_190], 2FCh
0x140141e27  lea     rax, aClusteredvolum; "ClusteredVolumeMarkAndSweepTask::Step"
0x140141e2e  mov     qword ptr [rsp+1C0h+var_198], rax
0x140141e33  lea     rax, aBaseFsRemotefs_65; "base\\fs\\remotefs\\frs\\src\\sync\\mar"...
0x140141e3a  mov     [rsp+1C0h+var_1A0], rax
0x140141e3f  mov     r9d, 3
0x140141e45  xor     r8d, r8d
0x140141e48  mov     edx, 240Eh
0x140141e4d  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140141e52  mov     rdi, rax
  ... truncated ...
```
