# ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets(void)

- ea: `0x14002018c`
- end: `0x140020cab`
- name: `?BootstrapOnlineAndOnlinePendingContentSets@ServiceConfig@@IEAAXXZ`
- size: `2847`
- prototype: `void __fastcall(ServiceConfig *__hidden this)`
- caller_count: `1`
- callee_count: `37`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140039910`

## callees

- `0x1400036a0`
- `0x14000c910`
- `0x14000cdc0`
- `0x14000dfa0`
- `0x14000e34c`
- `0x14000ee94`
- `0x140011408`
- `0x14001c31c`
- `0x14001c3c4`
- `0x14001c480`
- `0x14001c548`
- `0x14001c608`
- `0x14001cfa0`
- `0x14001d07c`
- `0x14001d094`
- `0x14001d7bc`
- `0x14001e19c`
- `0x14002018c`
- `0x140022ce4`
- `0x140023794`
- `0x14002383c`
- `0x1400238e4`
- `0x1400e8e1c`
- `0x1400ebff4`
- `0x1400eeffc`
- `0x1401b3d14`
- `0x1401b9470`
- `0x1401b9494`
- `0x1401c0780`
- `0x1401cff90`
- `0x1401d02d8`
- `0x1401d1fc0`
- `0x1401d2964`
- `0x1401d5448`
- `0x1401d59b0`
- `0x1401d6454`
- `0x1401d862c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140020481`
- `KERNEL32!GetCurrentThreadId` at `0x140020541`
- `KERNEL32!GetCurrentThreadId` at `0x14002062f`
- `KERNEL32!GetCurrentThreadId` at `0x1400206ff`
- `KERNEL32!GetCurrentThreadId` at `0x1400207e6`
- `KERNEL32!GetCurrentThreadId` at `0x1400208b6`
- `KERNEL32!GetCurrentThreadId` at `0x140020481`
- `KERNEL32!GetCurrentThreadId` at `0x140020541`
- `KERNEL32!GetCurrentThreadId` at `0x14002062f`
- `KERNEL32!GetCurrentThreadId` at `0x1400206ff`
- `KERNEL32!GetCurrentThreadId` at `0x1400207e6`
- `KERNEL32!GetCurrentThreadId` at `0x1400208b6`

## string_xrefs

- `0x1400204aa`: `base\fs\remotefs\frs\src\main\serviceconfig.cpp`
- `0x14002056a`: `base\fs\remotefs\frs\src\main\serviceconfig.cpp`
- `0x140020658`: `base\fs\remotefs\frs\src\main\serviceconfig.cpp`
- `0x140020721`: `base\fs\remotefs\frs\src\main\serviceconfig.cpp`
- `0x14002080f`: `base\fs\remotefs\frs\src\main\serviceconfig.cpp`
- `0x1400208d8`: `base\fs\remotefs\frs\src\main\serviceconfig.cpp`
- `0x140020250`: `ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets`
- `0x140020428`: `ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets`
- `0x1400205f4`: `ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets`
- `0x1400206bf`: `ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets`
- `0x1400207ab`: `ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets`
- `0x140020876`: `ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets`
- `0x14002090c`: `ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets`
- `0x140020aaa`: `ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets`
- `0x140020b25`: `ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets`
- `0x140020b9d`: `ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets`
- `0x14002049e`: `ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets`
- `0x14002055e`: `ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets`
- `0x14002064c`: `ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets`
- `0x14002067e`: `ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets`
- `0x140020803`: `ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets`
- `0x140020835`: `ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets`
- `0x140020965`: `[CLUSTER] Bootstrapping DFS Replicated Folder resource. resName:%? csId:%? rgId:%? volId:%?`
- `0x140020a1f`: `[CLUSTER] (Ignored) Failed to bring the resource's content set online. resName:%? csId:%?`
- `0x140020adc`: `[CLUSTER] (Ignored) Failed to bootstrap DFS Replicated Folder resource. Failing the resource. resName:%? csId:%? Error:%?`
- `0x140020a7f`: `[CLUSTER] (Ignored) Failed to bootstrap DFS Replicated Folder resource. Failing the resource. resName:%? csId:%?`
- `0x140020bf3`: `[CLUSTER] Cluster service is not installed or running. Skipping clustered bootstrap operation.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets(ServiceConfig *this)
{
  int v2; // esi
  char v3; // al
  struct FrsStatus *ComputerNameW; // rdi
  int v5; // ecx
  FrsService *v6; // rcx
  const struct Cluster::ClusterResource *i; // rbx
  __int64 ResourceName; // rax
  __int64 v9; // rax
  char v10; // r14
  DWORD CurrentThreadId; // eax
  __int64 v12; // rcx
  DWORD v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rax
  char v16; // r14
  DWORD v17; // eax
  __int64 v18; // rcx
  DWORD v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rax
  char v22; // r14
  DWORD v23; // eax
  __int64 v24; // rcx
  DWORD v25; // eax
  __int64 v26; // rcx
  LPCRITICAL_SECTION v27; // rax
  unsigned __int16 *v28; // [rsp+58h] [rbp-B0h] BYREF
  const wchar_t *v29; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+68h] [rbp-A0h]
  const wchar_t *v31; // [rsp+70h] [rbp-98h]
  struct FrsStatus *v32; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int16 *v33; // [rsp+80h] [rbp-88h] BYREF
  int v34; // [rsp+88h] [rbp-80h] BYREF
  const wchar_t *v35; // [rsp+90h] [rbp-78h] BYREF
  int v36; // [rsp+98h] [rbp-70h]
  int v37; // [rsp+9Ch] [rbp-6Ch]
  const wchar_t *v38; // [rsp+A0h] [rbp-68h]
  unsigned __int16 *v39; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD v40[3]; // [rsp+B0h] [rbp-58h] BYREF
  _BYTE v41[8]; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v42[8]; // [rsp+D0h] [rbp-38h] BYREF
  _BYTE v43[8]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v44[8]; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE v45[16]; // [rsp+E8h] [rbp-20h] BYREF
  void **v46; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v47[24]; // [rsp+100h] [rbp-8h] BYREF
  const wchar_t *v48; // [rsp+118h] [rbp+10h] BYREF
  int v49; // [rsp+120h] [rbp+18h]
  int v50; // [rsp+124h] [rbp+1Ch]
  const wchar_t *v51; // [rsp+128h] [rbp+20h]
  const wchar_t *v52; // [rsp+130h] [rbp+28h] BYREF
  int v53; // [rsp+138h] [rbp+30h]
  int v54; // [rsp+13Ch] [rbp+34h]
  const wchar_t *v55; // [rsp+140h] [rbp+38h]
  _BYTE v56[8]; // [rsp+148h] [rbp+40h] BYREF
  _BYTE v57[8]; // [rsp+150h] [rbp+48h] BYREF
  _BYTE v58[48]; // [rsp+158h] [rbp+50h] BYREF
  struct _GUID v59; // [rsp+188h] [rbp+80h] BYREF
  __int128 v60; // [rsp+198h] [rbp+90h] BYREF
  __int128 v61; // [rsp+1A8h] [rbp+A0h] BYREF

  v2 = 0;
  v34 = 6;
  Cluster::ClusterResourceFilter::ClusterResourceFilter(v45, 0);
  std::vector<VolumeInfo *>::vector<VolumeInfo *>(v40);
  v39 = &FrsStringImpl<unsigned short,char>::s_Empty;
  v3 = byte_140315A80;
  if ( !byte_140315A80 )
  {
    _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
    v3 = 0;
  }
  v33 = &FrsStringImpl<unsigned short,char>::s_Empty;
  if ( !v3 )
  {
    _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
    v3 = byte_140315A80;
  }
  v28 = &FrsStringImpl<unsigned short,char>::s_Empty;
  if ( !v3 )
    _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
  v59 = 0;
  v61 = 0;
  v60 = 0;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v29 = L"ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets";
    v30 = 0x400000393LL;
    v31 = L"SCFS";
    dbgobj::DbgPrint<unsigned short>(
      &v29,
      L"[CLUSTER] Bootstrapping online / online-pending DFS Replicated Folder resources");
  }
  ComputerNameW = (struct FrsStatus *)System::GetComputerNameW(&v39);
  v32 = ComputerNameW;
  if ( ComputerNameW
    || (Cluster::ClusterResourceFilter::SetFilter(v45, &v39, 68),
        ComputerNameW = (struct FrsStatus *)Cluster::ClusterUtil::GetClusterResources(
                                              v5,
                                              1,
                                              (unsigned int)v45,
                                              2,
                                              (__int64)v40),
        (v32 = ComputerNameW) != 0)
    || v40[1] != v40[0] && (ComputerNameW = FrsService::ActivateService(v6), (v32 = ComputerNameW) != 0) )
  {
LABEL_99:
    if ( (unsigned int)FrsStatus::IsErrorClusterNotExist(ComputerNameW) )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v35 = L"ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets";
        v36 = 1124;
        v37 = 4;
        v38 = L"SCFS";
        dbgobj::DbgPrint<unsigned short>(
          &v35,
          L"[CLUSTER] Cluster service is not installed or running. Skipping clustered bootstrap operation.");
      }
    }
    else if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v35 = L"ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets";
      v36 = 1127;
      v37 = 3;
      v38 = L"SCFS";
      dbgobj::DbgPrint<unsigned short,FrsStatus>(
        &v35,
        L"[CLUSTER] (Ignored) Failed to bootstrap online / online-pending DFS Replicated Folder resources. Error:%?",
        ComputerNameW);
    }
    CLEAR_ERROR(&v32);
    goto LABEL_109;
  }
  for ( i = *(const struct Cluster::ClusterResource **)std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(
                                                         v40,
                                                         v56);
        i != *(const struct Cluster::ClusterResource **)std::vector<ServiceInfo *>::end(v40, v57);
        i = (const struct Cluster::ClusterResource *)((char *)i + 48) )
  {
    Cluster::ClusterResource::ClusterResource((Cluster::ClusterResource *)v58, i);
    ResourceName = Cluster::NodeNetworkName::GetResourceName(v58, v41);
    FrsStringImpl<unsigned short,char>::Set(&v28, ResourceName);
    FrsStringImpl<char,unsigned short>::ReleaseBody(v41);
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v29 = L"ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets";
      v30 = 0x4000003C7LL;
      v31 = L"SCFS";
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
        &v29,
        L"[CLUSTER] Found online / online-pending DFS Replicated Folder resource. resName:%?",
        &v28);
    }
    Cluster::ResourcePrivatePropertyList::ResourcePrivatePropertyList((Cluster::ResourcePrivatePropertyList *)&v46);
    ComputerNameW = Cluster::ClusterResource::GetResourceProperties(
                      (Cluster::ClusterResource *)v58,
                      (struct Cluster::ResourcePrivatePropertyList *)&v46);
    v32 = ComputerNameW;
    if ( ComputerNameW
      || (v9 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v42, L"Replicated Folder ID"),
          v2 |= 1u,
          v10 = 1,
          (unsigned int)Cluster::ResourcePrivatePropertyList::GetStringPropertyValue(&v46, v9, &v33)) )
    {
      v10 = 0;
    }
    if ( (v2 & 1) != 0 )
    {
      v2 &= ~1u;
      FrsStringImpl<char,unsigned short>::ReleaseBody(v42);
    }
    if ( v10 )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
      {
        v29 = L"ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets";
        v30 = 0x3000003D6LL;
        v31 = L"SCFS";
        dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
          &v29,
          L"[CLUSTER] (Ignored) Failed to retrieve the resource's Replicated Folder ID property. resName:%?",
          &v28);
      }
      CurrentThreadId = GetCurrentThreadId();
      ComputerNameW = (struct FrsStatus *)FrsStatusList::PushNewError(
                                            v12,
                                            9230,
                                            0,
                                            3,
                                            "base\\fs\\remotefs\\frs\\src\\main\\serviceconfig.cpp",
                                            "ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets",
                                            985,
                                            CurrentThreadId,
                                            0);
      v32 = ComputerNameW;
    }
    if ( ComputerNameW )
      goto LABEL_40;
    if ( !(unsigned int)Guid::StringToGuid(&v33, &v59) )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
      {
        v29 = L"ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets";
        v30 = 0x3000003DCLL;
        v31 = L"SCFS";
        dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,FrsStringImpl<unsigned short,char>>(
          &v29,
          L"[CLUSTER] (Ignored) The resource's Replicated Folder ID property contains an invalid GUID value. resName:%? propVal:%?",
          &v28,
          &v33);
      }
      v13 = GetCurrentThreadId();
      ComputerNameW = (struct FrsStatus *)FrsStatusList::PushNewError(
                                            v14,
                                            9231,
                                            0,
                                            3,
                                            "base\\fs\\remotefs\\frs\\src\\main\\serviceconfig.cpp",
                                            "ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets",
                                            992,
                                            v13,
                                            0);
      v32 = ComputerNameW;
      if ( ComputerNameW )
        goto LABEL_40;
    }
    v15 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v43, L"Replication Group ID");
    v2 |= 2u;
    v16 = 1;
    if ( (unsigned int)Cluster::ResourcePrivatePropertyList::GetStringPropertyValue(&v46, v15, &v33) )
LABEL_40:
      v16 = 0;
    if ( (v2 & 2) != 0 )
    {
      v2 &= ~2u;
      FrsStringImpl<char,unsigned short>::ReleaseBody(v43);
    }
    if ( v16 )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
      {
        v29 = L"ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets";
        v30 = 0x3000003E8LL;
        v31 = L"SCFS";
        dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
          &v29,
          L"[CLUSTER] (Ignored) Failed to retrieve the resource's Replication Group ID property. resName:%?",
          &v28);
      }
      v17 = GetCurrentThreadId();
      ComputerNameW = (struct FrsStatus *)FrsStatusList::PushNewError(
                                            v18,
                                            9230,
                                            0,
                                            3,
                                            "base\\fs\\remotefs\\frs\\src\\main\\serviceconfig.cpp",
                                            "ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets",
                                            1003,
                                            v17,
                                            0);
      v32 = ComputerNameW;
    }
    if ( ComputerNameW )
      goto LABEL_57;
    if ( !(unsigned int)Guid::StringToGuid(&v33, &v61) )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
      {
        v29 = L"ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets";
        v30 = 0x3000003EELL;
        v31 = L"SCFS";
        dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,FrsStringImpl<unsigned short,char>>(
          &v29,
          L"[CLUSTER] (Ignored) The resource's Replication Group ID property contains an invalid GUID value. resName:%? propVal:%?",
          &v28,
          &v33);
      }
      v19 = GetCurrentThreadId();
      ComputerNameW = (struct FrsStatus *)FrsStatusList::PushNewError(
                                            v20,
                                            9231,
                                            0,
                                            3,
                                            "base\\fs\\remotefs\\frs\\src\\main\\serviceconfig.cpp",
                                            "ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets",
                                            1010,
                                            v19,
                                            0);
      v32 = ComputerNameW;
      if ( ComputerNameW )
        goto LABEL_57;
    }
    v21 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v44, L"Volume ID");
    v2 |= 4u;
    v22 = 1;
    if ( (unsigned int)Cluster::ResourcePrivatePropertyList::GetStringPropertyValue(&v46, v21, &v33) )
LABEL_57:
      v22 = 0;
    if ( (v2 & 4) != 0 )
    {
      v2 &= ~4u;
      FrsStringImpl<char,unsigned short>::ReleaseBody(v44);
    }
    if ( v22 )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
      {
        v29 = L"ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets";
        v30 = 0x3000003FALL;
        v31 = L"SCFS";
        dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
          &v29,
          L"[CLUSTER] (Ignored) Failed to retrieve the resource's Volume ID property. resName:%?",
          &v28);
      }
      v23 = GetCurrentThreadId();
      ComputerNameW = (struct FrsStatus *)FrsStatusList::PushNewError(
                                            v24,
                                            9230,
                                            0,
                                            3,
                                            "base\\fs\\remotefs\\frs\\src\\main\\serviceconfig.cpp",
                                            "ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets",
                                            1021,
                                            v23,
                                            0);
      v32 = ComputerNameW;
    }
    if ( ComputerNameW )
      goto LABEL_88;
    if ( !(unsigned int)Guid::StringToGuid(&v33, &v60) )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
      {
        v29 = L"ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets";
        v30 = 0x300000400LL;
        v31 = L"SCFS";
        dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,FrsStringImpl<unsigned short,char>>(
          &v29,
          L"[CLUSTER] (Ignored) The resource's Volume ID property contains an invalid GUID value. resName:%? propVal:%?",
          &v28,
          &v33);
      }
      v25 = GetCurrentThreadId();
      ComputerNameW = (struct FrsStatus *)FrsStatusList::PushNewError(
                                            v26,
                                            9231,
                                            0,
                                            3,
                                            "base\\fs\\remotefs\\frs\\src\\main\\serviceconfig.cpp",
                                            "ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets",
                                            1028,
                                            v25,
                                            0);
      v32 = ComputerNameW;
      if ( ComputerNameW )
      {
LABEL_88:
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
        {
          v35 = L"ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets";
          v36 = 1079;
          v37 = 3;
          v38 = L"SCFS";
          dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,FrsStatus>(
            (unsigned int)&v35,
            (unsigned int)L"[CLUSTER] (Ignored) Failed to bootstrap DFS Replicated Folder resource. Failing the resource. "
                           "resName:%? csId:%? Error:%?",
            (unsigned int)&v28,
            (unsigned int)&v59,
            (__int64)ComputerNameW);
        }
        CLEAR_ERROR(&v32);
        goto LABEL_91;
      }
    }
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v48 = L"ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets";
      v49 = 1040;
      v50 = 4;
      v51 = L"SCFS";
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,_GUID,_GUID>(
        (unsigned int)&v48,
        (unsigned int)L"[CLUSTER] Bootstrapping DFS Replicated Folder resource. resName:%? csId:%? rgId:%? volId:%?",
        (unsigned int)&v28,
        (unsigned int)&v59,
        (__int64)&v61,
        (__int64)&v60);
    }
    FrsReplicator::SetContentSetStatus(*((_QWORD *)this + 93), &v59, 5);
    FrsReplicator::BringContentSetOnline(*((_QWORD *)this + 93), &v28, &v59, &v61, &v60);
    FrsReplicator::ContentSetStatusMap::Get(
      (FrsReplicator::ContentSetStatusMap *)(*((_QWORD *)this + 93) + 520LL),
      &v59,
      (enum FrsReplicator::ContentSetStatus *)&v34);
    if ( v34 != 3 )
    {
      v27 = g_DebugLog;
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
      {
        v52 = L"ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets";
        v53 = 1061;
        v54 = 3;
        v55 = L"SCFS";
        dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID>(
          &v52,
          L"[CLUSTER] (Ignored) Failed to bring the resource's content set online. resName:%? csId:%?",
          &v28,
          &v59);
        v27 = g_DebugLog;
      }
      if ( v27 && LODWORD(v27[1].LockSemaphore) && SLODWORD(v27[1].OwningThread) >= 3 )
      {
        v29 = L"ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets";
        v30 = 0x300000444LL;
        v31 = L"SCFS";
        dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID>(
          &v29,
          L"[CLUSTER] (Ignored) Failed to bootstrap DFS Replicated Folder resource. Failing the resource. resName:%? csId:%?",
          &v28,
          &v59);
      }
LABEL_91:
      ComputerNameW = (struct FrsStatus *)Cluster::ClusterUtil::FailResource(&v28);
      v32 = ComputerNameW;
      if ( ComputerNameW )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
        {
          v29 = L"ServiceConfig::BootstrapOnlineAndOnlinePendingContentSets";
          v30 = 0x30000044FLL;
          v31 = L"SCFS";
          dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,FrsStatus>(
            (unsigned int)&v29,
            (unsigned int)L"[CLUSTER] (Ignored) Failed to fail the resource. resName:%? cdId:%? Error:%?",
            (unsigned int)&v28,
            (unsigned int)&v59,
            (__int64)ComputerNameW);
        }
        CLEAR_ERROR(&v32);
        ComputerNameW = v32;
      }
    }
    v46 = &ObjList<Cluster::ResourcePrivateProperty>::`vftable';
    std::vector<Cluster::ResourcePrivateProperty>::_Tidy(v47);
    Cluster::ClusterResource::~ClusterResource((Cluster::ClusterResource *)v58);
  }
  if ( ComputerNameW )
    goto LABEL_99;
LABEL_109:
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v28);
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v33);
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v39);
  std::vector<Cluster::ClusterResource>::_Tidy(v40);
  Cluster::ClusterResourceFilter::~ClusterResourceFilter((Cluster::ClusterResourceFilter *)v45);
}

```

## disassembly

```asm
0x14002018c  mov     rax, rsp
0x14002018f  mov     [rax+10h], rbx
0x140020193  mov     [rax+18h], rsi
0x140020197  mov     [rax+20h], rdi
0x14002019b  push    rbp
0x14002019c  push    r12
0x14002019e  push    r13
0x1400201a0  push    r14
0x1400201a2  push    r15
0x1400201a4  lea     rbp, [rax-0E8h]
0x1400201ab  sub     rsp, 1C0h
0x1400201b2  mov     rax, cs:__security_cookie
0x1400201b9  xor     rax, rsp
0x1400201bc  mov     [rbp+0E0h+var_30], rax
0x1400201c3  mov     r15, rcx
0x1400201c6  xor     r12d, r12d
0x1400201c9  mov     esi, r12d
0x1400201cc  mov     [rbp+0E0h+var_160], r12d
0x1400201d0  mov     [rbp+0E0h+var_160], 6
0x1400201d7  xor     edx, edx
0x1400201d9  lea     rcx, [rbp+0E0h+var_100]
0x1400201dd  call    ??0ClusterResourceFilter@Cluster@@QEAA@PEBV?$FrsStringImpl@GD@@K@Z; Cluster::ClusterResourceFilter::ClusterResourceFilter(FrsStringImpl<ushort,char> const *,ulong)
0x1400201e2  nop
0x1400201e3  lea     rcx, [rbp+0E0h+var_138]
0x1400201e7  call    ??0?$vector@PEAVVolumeInfo@@V?$allocator@PEAVVolumeInfo@@@std@@@std@@QEAA@XZ; std::vector<VolumeInfo *>::vector<VolumeInfo *>(void)
0x1400201ec  nop
0x1400201ed  lea     rcx, ?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1400201f4  mov     [rbp+0E0h+var_140], rcx
0x1400201f8  mov     al, cs:byte_140315A80
0x1400201fe  test    al, al
0x140020200  jnz     short loc_14002020F
0x140020202  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x140020209  mov     al, cs:byte_140315A80
0x14002020f  mov     [rsp+1E0h+var_168], rcx
0x140020214  test    al, al
0x140020216  jnz     short loc_140020225
0x140020218  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x14002021f  mov     al, cs:byte_140315A80
0x140020225  mov     [rsp+1E0h+var_190], rcx
0x14002022a  test    al, al
0x14002022c  jnz     short loc_140020235
0x14002022e  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x140020235  xorps   xmm0, xmm0
0x140020238  movups  xmmword ptr [rbp+0E0h+var_60.Data1], xmm0
0x14002023f  xorps   xmm1, xmm1
0x140020242  movups  [rbp+0E0h+var_40], xmm1
0x140020249  movups  [rbp+0E0h+var_50], xmm0
0x140020250  lea     r14, aServiceconfigB; "ServiceConfig::BootstrapOnlineAndOnline"...
0x140020257  lea     rbx, aScfs; "SCFS"
0x14002025e  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140020265  test    rax, rax
0x140020268  jz      short loc_1400202A1
0x14002026a  cmp     [rax+40h], r12d
0x14002026e  jz      short loc_1400202A1
0x140020270  cmp     dword ptr [rax+38h], 4
0x140020274  jl      short loc_1400202A1
0x140020276  mov     [rsp+1E0h+var_188], r14
0x14002027b  mov     dword ptr [rsp+1E0h+var_180], 393h
0x140020283  mov     dword ptr [rsp+1E0h+var_180+4], 4
0x14002028b  mov     [rsp+1E0h+var_178], rbx
0x140020290  lea     rdx, aClusterBootstr; "[CLUSTER] Bootstrapping online / online"...
0x140020297  lea     rcx, [rsp+1E0h+var_188]
0x14002029c  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1400202a1  lea     rcx, [rbp+0E0h+var_140]
0x1400202a5  call    ?GetComputerNameW@System@@SAPEAVFrsStatus@@AEAV?$FrsStringImpl@GD@@@Z; System::GetComputerNameW(FrsStringImpl<ushort,char> &)
0x1400202aa  mov     rdi, rax
0x1400202ad  mov     [rsp+1E0h+var_170], rax
0x1400202b2  mov     r13d, 3
0x1400202b8  test    rax, rax
0x1400202bb  jnz     loc_140020BB9
0x1400202c1  lea     r8d, [rax+44h]
0x1400202c5  lea     rdx, [rbp+0E0h+var_140]
0x1400202c9  lea     rcx, [rbp+0E0h+var_100]
0x1400202cd  call    ?SetFilter@ClusterResourceFilter@Cluster@@QEAAXPEBV?$FrsStringImpl@GD@@K@Z; Cluster::ClusterResourceFilter::SetFilter(FrsStringImpl<ushort,char> const *,ulong)
0x1400202d2  lea     rax, [rbp+0E0h+var_138]
0x1400202d6  mov     [rsp+1E0h+var_1C0], rax
0x1400202db  lea     r9d, [rdi+2]
0x1400202df  lea     r8, [rbp+0E0h+var_100]
0x1400202e3  lea     edx, [rdi+1]
0x1400202e6  call    ?GetClusterResources@ClusterUtil@Cluster@@SAPEAVFrsStatus@@PEBGW4_ClusterResourceType@2@PEAVClusterResourceFilter@2@W4RetrievalErrorPolicy@2@AEAV?$vector@VClusterResource@Cluster@@V?$allocator@VClusterResource@Cluster@@@std@@@std@@@Z; Cluster::ClusterUtil::GetClusterResources(ushort const *,Cluster::_ClusterResourceType,Cluster::ClusterResourceFilter *,Cluster::RetrievalErrorPolicy,std::vector<Cluster::ClusterResource> &)
0x1400202eb  mov     rdi, rax
0x1400202ee  mov     [rsp+1E0h+var_170], rax
0x1400202f3  test    rax, rax
0x1400202f6  jnz     loc_140020BB9
0x1400202fc  mov     rax, [rbp+0E0h+var_130]
0x140020300  cmp     rax, [rbp+0E0h+var_138]
0x140020304  jz      short loc_14002031C
0x140020306  call    ?ActivateService@FrsService@@QEAAPEAVFrsStatus@@XZ; FrsService::ActivateService(void)
0x14002030b  mov     rdi, rax
0x14002030e  mov     [rsp+1E0h+var_170], rax
0x140020313  test    rax, rax
0x140020316  jnz     loc_140020BB9
0x14002031c  lea     rdx, [rbp+0E0h+var_A0]
0x140020320  lea     rcx, [rbp+0E0h+var_138]
0x140020324  call    ?end@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@@std@@@3@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(void)
0x140020329  mov     rbx, [rax]
0x14002032c  lea     rdx, [rbp+0E0h+var_98]
0x140020330  lea     rcx, [rbp+0E0h+var_138]
0x140020334  call    ?end@?$vector@PEAVServiceInfo@@V?$allocator@PEAVServiceInfo@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAVServiceInfo@@@std@@@std@@@2@XZ; std::vector<ServiceInfo *>::end(void)
0x140020339  cmp     rbx, [rax]
0x14002033c  jz      loc_140020BA9
0x140020342  mov     rdx, rbx; struct Cluster::ClusterResource *
0x140020345  lea     rcx, [rbp+0E0h+var_90]; this
0x140020349  call    ??0ClusterResource@Cluster@@QEAA@AEBV01@@Z; Cluster::ClusterResource::ClusterResource(Cluster::ClusterResource const &)
0x14002034e  nop
0x14002034f  lea     rdx, [rbp+0E0h+var_120]
0x140020353  lea     rcx, [rbp+0E0h+var_90]
0x140020357  call    ?GetResourceName@NodeNetworkName@Cluster@@QEAA?AV?$FrsStringImpl@GD@@XZ; Cluster::NodeNetworkName::GetResourceName(void)
0x14002035c  mov     rdx, rax
0x14002035f  lea     rcx, [rsp+1E0h+var_190]
0x140020364  call    ?Set@?$FrsStringImpl@GD@@QEAA_NAEBV1@@Z; FrsStringImpl<ushort,char>::Set(FrsStringImpl<ushort,char> const &)
0x140020369  lea     rcx, [rbp+0E0h+var_120]
0x14002036d  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x140020372  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140020379  test    rax, rax
0x14002037c  jz      short loc_1400203C1
0x14002037e  cmp     [rax+40h], r12d
0x140020382  jz      short loc_1400203C1
0x140020384  cmp     dword ptr [rax+38h], 4
0x140020388  jl      short loc_1400203C1
0x14002038a  mov     [rsp+1E0h+var_188], r14
0x14002038f  mov     dword ptr [rsp+1E0h+var_180], 3C7h
0x140020397  mov     dword ptr [rsp+1E0h+var_180+4], 4
0x14002039f  lea     rax, aScfs; "SCFS"
0x1400203a6  mov     [rsp+1E0h+var_178], rax
0x1400203ab  lea     r8, [rsp+1E0h+var_190]
0x1400203b0  lea     rdx, aClusterFoundOn; "[CLUSTER] Found online / online-pending"...
0x1400203b7  lea     rcx, [rsp+1E0h+var_188]
0x1400203bc  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>>(ushort const *,FrsStringImpl<ushort,char> const &)
0x1400203c1  lea     rcx, [rbp+0E0h+var_F0]; this
0x1400203c5  call    ??0ResourcePrivatePropertyList@Cluster@@QEAA@XZ; Cluster::ResourcePrivatePropertyList::ResourcePrivatePropertyList(void)
0x1400203ca  nop
0x1400203cb  lea     rdx, [rbp+0E0h+var_F0]; struct Cluster::ResourcePrivatePropertyList *
0x1400203cf  lea     rcx, [rbp+0E0h+var_90]; this
0x1400203d3  call    ?GetResourceProperties@ClusterResource@Cluster@@QEBAPEAVFrsStatus@@AEAVResourcePrivatePropertyList@2@@Z; Cluster::ClusterResource::GetResourceProperties(Cluster::ResourcePrivatePropertyList &)
0x1400203d8  mov     rdi, rax
0x1400203db  mov     [rsp+1E0h+var_170], rax
0x1400203e0  test    rax, rax
0x1400203e3  jnz     short loc_140020410
0x1400203e5  lea     rdx, aReplicatedFold_2; "Replicated Folder ID"
0x1400203ec  lea     rcx, [rbp+0E0h+var_118]
0x1400203f0  call    ??0?$FrsStringImpl@GD@@QEAA@PEBG@Z; FrsStringImpl<ushort,char>::FrsStringImpl<ushort,char>(ushort const *)
0x1400203f5  or      esi, 1
0x1400203f8  lea     r8, [rsp+1E0h+var_168]
0x1400203fd  mov     rdx, rax
0x140020400  lea     rcx, [rbp+0E0h+var_F0]
0x140020404  call    ?GetStringPropertyValue@ResourcePrivatePropertyList@Cluster@@QEBAHAEBV?$FrsStringImpl@GD@@AEAV3@@Z; Cluster::ResourcePrivatePropertyList::GetStringPropertyValue(FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> &)
0x140020409  test    eax, eax
0x14002040b  mov     r14b, 1
0x14002040e  jz      short loc_140020413
0x140020410  mov     r14b, r12b
0x140020413  test    sil, 1
0x140020417  jz      short loc_140020425
0x140020419  and     esi, 0FFFFFFFEh
0x14002041c  lea     rcx, [rbp+0E0h+var_118]
0x140020420  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x140020425  test    r14b, r14b
0x140020428  lea     r14, aServiceconfigB; "ServiceConfig::BootstrapOnlineAndOnline"...
0x14002042f  jz      loc_1400204CE
0x140020435  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14002043c  test    rax, rax
0x14002043f  jz      short loc_140020481
0x140020441  cmp     [rax+40h], r12d
0x140020445  jz      short loc_140020481
0x140020447  cmp     [rax+38h], r13d
0x14002044b  jl      short loc_140020481
0x14002044d  mov     [rsp+1E0h+var_188], r14
0x140020452  mov     dword ptr [rsp+1E0h+var_180], 3D6h
0x14002045a  mov     dword ptr [rsp+1E0h+var_180+4], r13d
0x14002045f  lea     rax, aScfs; "SCFS"
0x140020466  mov     [rsp+1E0h+var_178], rax
0x14002046b  lea     r8, [rsp+1E0h+var_190]
0x140020470  lea     rdx, aClusterIgnored_32; "[CLUSTER] (Ignored) Failed to retrieve "...
0x140020477  lea     rcx, [rsp+1E0h+var_188]
0x14002047c  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>>(ushort const *,FrsStringImpl<ushort,char> const &)
0x140020481  call    cs:__imp_GetCurrentThreadId
0x140020488  nop     dword ptr [rax+rax+00h]
0x14002048d  mov     [rsp+1E0h+var_1A0], r12
0x140020492  mov     dword ptr [rsp+1E0h+var_1A8], eax
0x140020496  mov     [rsp+1E0h+var_1B0], 3D9h
0x14002049e  lea     rax, aServiceconfigB_0; "ServiceConfig::BootstrapOnlineAndOnline"...
0x1400204a5  mov     qword ptr [rsp+1E0h+var_1B8], rax
0x1400204aa  lea     rax, aBaseFsRemotefs_29; "base\\fs\\remotefs\\frs\\src\\main\\ser"...
0x1400204b1  mov     [rsp+1E0h+var_1C0], rax
0x1400204b6  mov     r9d, r13d
0x1400204b9  xor     r8d, r8d
0x1400204bc  mov     edx, 240Eh
0x1400204c1  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400204c6  mov     rdi, rax
0x1400204c9  mov     [rsp+1E0h+var_170], rax
0x1400204ce  test    rdi, rdi
0x1400204d1  jnz     loc_1400205BE
0x1400204d7  lea     rdx, [rbp+0E0h+var_60]
0x1400204de  lea     rcx, [rsp+1E0h+var_168]
0x1400204e3  call    ?StringToGuid@Guid@@SAHAEBV?$FrsStringImpl@GD@@AEAU_GUID@@@Z; Guid::StringToGuid(FrsStringImpl<ushort,char> const &,_GUID &)
0x1400204e8  test    eax, eax
0x1400204ea  jnz     loc_140020593
0x1400204f0  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400204f7  test    rax, rax
0x1400204fa  jz      short loc_140020541
0x1400204fc  cmp     [rax+40h], r12d
0x140020500  jz      short loc_140020541
0x140020502  cmp     [rax+38h], r13d
0x140020506  jl      short loc_140020541
0x140020508  mov     [rsp+1E0h+var_188], r14
0x14002050d  mov     dword ptr [rsp+1E0h+var_180], 3DCh
0x140020515  mov     dword ptr [rsp+1E0h+var_180+4], r13d
0x14002051a  lea     rax, aScfs; "SCFS"
0x140020521  mov     [rsp+1E0h+var_178], rax
0x140020526  lea     r9, [rsp+1E0h+var_168]
0x14002052b  lea     r8, [rsp+1E0h+var_190]
0x140020530  lea     rdx, aClusterIgnored_26; "[CLUSTER] (Ignored) The resource's Repl"...
0x140020537  lea     rcx, [rsp+1E0h+var_188]
0x14002053c  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@V1@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@1@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>,FrsStringImpl<ushort,char>>(ushort const *,FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> const &)
0x140020541  call    cs:__imp_GetCurrentThreadId
0x140020548  nop     dword ptr [rax+rax+00h]
0x14002054d  mov     [rsp+1E0h+var_1A0], r12
0x140020552  mov     dword ptr [rsp+1E0h+var_1A8], eax
0x140020556  mov     [rsp+1E0h+var_1B0], 3E0h
0x14002055e  lea     rax, aServiceconfigB_0; "ServiceConfig::BootstrapOnlineAndOnline"...
0x140020565  mov     qword ptr [rsp+1E0h+var_1B8], rax
0x14002056a  lea     rax, aBaseFsRemotefs_29; "base\\fs\\remotefs\\frs\\src\\main\\ser"...
0x140020571  mov     [rsp+1E0h+var_1C0], rax
0x140020576  mov     r9d, r13d
0x140020579  xor     r8d, r8d
0x14002057c  mov     edx, 240Fh
0x140020581  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140020586  mov     rdi, rax
0x140020589  mov     [rsp+1E0h+var_170], rax
0x14002058e  test    rax, rax
0x140020591  jnz     short loc_1400205BE
0x140020593  lea     rdx, aReplicationGro_2; "Replication Group ID"
0x14002059a  lea     rcx, [rbp+0E0h+var_110]
0x14002059e  call    ??0?$FrsStringImpl@GD@@QEAA@PEBG@Z; FrsStringImpl<ushort,char>::FrsStringImpl<ushort,char>(ushort const *)
0x1400205a3  or      esi, 2
0x1400205a6  lea     r8, [rsp+1E0h+var_168]
0x1400205ab  mov     rdx, rax
0x1400205ae  lea     rcx, [rbp+0E0h+var_F0]
0x1400205b2  call    ?GetStringPropertyValue@ResourcePrivatePropertyList@Cluster@@QEBAHAEBV?$FrsStringImpl@GD@@AEAV3@@Z; Cluster::ResourcePrivatePropertyList::GetStringPropertyValue(FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> &)
0x1400205b7  test    eax, eax
0x1400205b9  mov     r14b, 1
0x1400205bc  jz      short loc_1400205C1
0x1400205be  mov     r14b, r12b
0x1400205c1  test    sil, 2
0x1400205c5  jz      short loc_1400205D3
0x1400205c7  and     esi, 0FFFFFFFDh
0x1400205ca  lea     rcx, [rbp+0E0h+var_110]
0x1400205ce  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1400205d3  test    r14b, r14b
0x1400205d6  jz      loc_14002067E
0x1400205dc  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400205e3  test    rax, rax
0x1400205e6  jz      short loc_14002062F
0x1400205e8  cmp     [rax+40h], r12d
0x1400205ec  jz      short loc_14002062F
0x1400205ee  cmp     [rax+38h], r13d
0x1400205f2  jl      short loc_14002062F
0x1400205f4  lea     rax, aServiceconfigB; "ServiceConfig::BootstrapOnlineAndOnline"...
0x1400205fb  mov     [rsp+1E0h+var_188], rax
0x140020600  mov     dword ptr [rsp+1E0h+var_180], 3E8h
0x140020608  mov     dword ptr [rsp+1E0h+var_180+4], r13d
0x14002060d  lea     rax, aScfs; "SCFS"
0x140020614  mov     [rsp+1E0h+var_178], rax
0x140020619  lea     r8, [rsp+1E0h+var_190]
0x14002061e  lea     rdx, aClusterIgnored_45; "[CLUSTER] (Ignored) Failed to retrieve "...
0x140020625  lea     rcx, [rsp+1E0h+var_188]
0x14002062a  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>>(ushort const *,FrsStringImpl<ushort,char> const &)
0x14002062f  call    cs:__imp_GetCurrentThreadId
0x140020636  nop     dword ptr [rax+rax+00h]
0x14002063b  mov     [rsp+1E0h+var_1A0], r12
0x140020640  mov     dword ptr [rsp+1E0h+var_1A8], eax
0x140020644  mov     [rsp+1E0h+var_1B0], 3EBh
0x14002064c  lea     r14, aServiceconfigB_0; "ServiceConfig::BootstrapOnlineAndOnline"...
0x140020653  mov     qword ptr [rsp+1E0h+var_1B8], r14
0x140020658  lea     rax, aBaseFsRemotefs_29; "base\\fs\\remotefs\\frs\\src\\main\\ser"...
0x14002065f  mov     [rsp+1E0h+var_1C0], rax
0x140020664  mov     r9d, r13d
0x140020667  xor     r8d, r8d
0x14002066a  mov     edx, 240Eh
0x14002066f  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140020674  mov     rdi, rax
0x140020677  mov     [rsp+1E0h+var_170], rax
0x14002067c  jmp     short loc_140020685
0x14002067e  lea     r14, aServiceconfigB_0; "ServiceConfig::BootstrapOnlineAndOnline"...
0x140020685  test    rdi, rdi
0x140020688  jnz     loc_140020775
0x14002068e  lea     rdx, [rbp+0E0h+var_40]
0x140020695  lea     rcx, [rsp+1E0h+var_168]
0x14002069a  call    ?StringToGuid@Guid@@SAHAEBV?$FrsStringImpl@GD@@AEAU_GUID@@@Z; Guid::StringToGuid(FrsStringImpl<ushort,char> const &,_GUID &)
0x14002069f  test    eax, eax
0x1400206a1  jnz     loc_14002074A
0x1400206a7  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400206ae  test    rax, rax
0x1400206b1  jz      short loc_1400206FF
0x1400206b3  cmp     [rax+40h], r12d
0x1400206b7  jz      short loc_1400206FF
0x1400206b9  cmp     [rax+38h], r13d
0x1400206bd  jl      short loc_1400206FF
0x1400206bf  lea     rax, aServiceconfigB; "ServiceConfig::BootstrapOnlineAndOnline"...
0x1400206c6  mov     [rsp+1E0h+var_188], rax
  ... truncated ...
```
