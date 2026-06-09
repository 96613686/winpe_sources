# ConfigurationHelper::PollAdConfigNow(Config::ReplicaSetConfigList *,Config::VolumeConfigList *,Cluster::NodeNetworkNameList &,Config::ContentSetList &,ushort const *,EventThrottle *)

- ea: `0x1400c9710`
- end: `0x1400ca951`
- name: `?PollAdConfigNow@ConfigurationHelper@@SA?AW4_FRS_CONFIG_STATUS@@PEAVReplicaSetConfigList@Config@@PEAVVolumeConfigList@4@AEAVNodeNetworkNameList@Cluster@@AEAVContentSetList@4@PEBGPEAVEventThrottle@@@Z`
- size: `4673`
- prototype: ``
- caller_count: `2`
- callee_count: `73`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400c8d70`
- `0x1400cf6f8`

## callees

- `0x1400036a0`
- `0x14000c910`
- `0x14000cdc0`
- `0x14000daa0`
- `0x14000e34c`
- `0x14000ee94`
- `0x140019358`
- `0x14001b620`
- `0x14001cfa0`
- `0x14001dc80`
- `0x14001e0a0`
- `0x140029974`
- `0x140035304`
- `0x14003c1cc`
- `0x14003c280`
- `0x14003cda8`
- `0x14003d0ac`
- `0x14003de7c`
- `0x14003ee14`
- `0x14003f570`
- `0x140040ce4`
- `0x140041814`
- `0x140042d48`
- `0x14004485c`
- `0x14004567c`
- `0x1400466e0`
- `0x140047e14`
- `0x14004bc8c`
- `0x14004c3e0`
- `0x14004e00c`
- `0x14004ebbc`
- `0x140057260`
- `0x14005c620`
- `0x14005ee30`
- `0x14005f7e4`
- `0x14005fc84`
- `0x14006a550`
- `0x1400c4bbc`
- `0x1400c52cc`
- `0x1400c5bd8`
- `0x1400c91a4`
- `0x1400c9520`
- `0x1400c95bc`
- `0x1400c967c`
- `0x1400c9710`
- `0x1400eb170`
- `0x1400ee090`
- `0x1400ee164`
- `0x1400eeffc`
- `0x1401af7c0`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400c9bdd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400ca5e7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400c9bdd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400ca5e7`
- `KERNEL32!LeaveCriticalSection` at `0x1400c9c11`
- `KERNEL32!LeaveCriticalSection` at `0x1400ca620`
- `KERNEL32!LeaveCriticalSection` at `0x1400c9c11`
- `KERNEL32!LeaveCriticalSection` at `0x1400ca620`
- `KERNEL32!EnterCriticalSection` at `0x1400c9b5a`
- `KERNEL32!EnterCriticalSection` at `0x1400ca564`
- `KERNEL32!EnterCriticalSection` at `0x1400c9b5a`
- `KERNEL32!EnterCriticalSection` at `0x1400ca564`
- `KERNEL32!GetCurrentThreadId` at `0x1400ca43d`
- `KERNEL32!GetCurrentThreadId` at `0x1400ca463`
- `KERNEL32!GetCurrentThreadId` at `0x1400ca43d`
- `KERNEL32!GetCurrentThreadId` at `0x1400ca463`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400c995f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400c995f`

## string_xrefs

- `0x1400c979b`: `ConfigurationHelper::PollAdConfigNow`
- `0x1400c99d0`: `ConfigurationHelper::PollAdConfigNow`
- `0x1400c9b76`: `ConfigurationHelper::PollAdConfigNow`
- `0x1400c9cca`: `ConfigurationHelper::PollAdConfigNow`
- `0x1400c9e6b`: `ConfigurationHelper::PollAdConfigNow`
- `0x1400ca042`: `ConfigurationHelper::PollAdConfigNow`
- `0x1400ca28e`: `ConfigurationHelper::PollAdConfigNow`
- `0x1400ca31a`: `ConfigurationHelper::PollAdConfigNow`
- `0x1400ca4aa`: `ConfigurationHelper::PollAdConfigNow`
- `0x1400ca58f`: `ConfigurationHelper::PollAdConfigNow`
- `0x1400ca84b`: `ConfigurationHelper::PollAdConfigNow`
- `0x1400ca899`: `ConfigurationHelper::PollAdConfigNow`
- `0x1400c9baa`: `Update serviceInfoHistory`
- `0x1400ca5b7`: `Update serviceInfoHistory`
- `0x1400c9f5b`: `[CLUSTER] (Ignored) Failed to determine if this node owns the clustered volume's disk resource. Proceeding with registry key deletion. volId:%? Error:%?`
- `0x1400ca10d`: `[CLUSTER] (Ignored) Failed to determine if this node owns the clustered replica set's VCO resource. Proceeding with registry key deletion. rgId:%? Error:%?`
- `0x1400c9fe5`: `[CLUSTER] (Ignored) Failed to remove volume config from registry. volId:%? Error:%?`
- `0x1400ca2b9`: `(Ignored) Failed to register service principal name. Error:%?`
- `0x1400ca18d`: `[CLUSTER] (Ignored) Failed to remove replica set config from registry. rgId:%? Error:%?`
- `0x1400ca345`: `(Ignored) Failed to update version info. Error:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall ConfigurationHelper::PollAdConfigNow(
        struct Config::ReplicaSetConfigList *a1,
        struct FrsStatus *a2,
        struct Cluster::NodeNetworkNameList *a3,
        struct Config::ContentSetList *a4,
        unsigned __int16 *a5,
        EventThrottle *a6)
{
  struct Config::ContentSetList *v6; // r15
  struct Cluster::NodeNetworkNameList *v7; // r12
  struct FrsStatus *Computer; // rsi
  struct TaskPool **v9; // rcx
  const unsigned __int16 *ServerName; // rax
  __int64 v11; // rbx
  int v12; // r14d
  const unsigned __int16 *v13; // r8
  const unsigned __int16 *v14; // r9
  Config::AdConfig *v15; // rcx
  struct FrsStatus *v16; // rax
  ConfigContext *v17; // rcx
  struct Config::Machine *Machine; // r12
  unsigned int v19; // r15d
  __int64 v20; // rdi
  Dword *v21; // rbx
  unsigned int v22; // eax
  Dword *v23; // rax
  struct MonitorContext *v24; // rbx
  struct MonitorContext *v25; // rcx
  struct MonitorContext *v26; // rcx
  void **v27; // rcx
  unsigned int v28; // r13d
  ConfigContext *v29; // rbx
  int v30; // ecx
  const int *v31; // r8
  struct _GUID *v32; // rbx
  __int64 v33; // rax
  __int64 v34; // r15
  __int64 v35; // rcx
  int v36; // edi
  Config::RegWriter *v37; // rcx
  _OWORD *v38; // rbx
  __int64 v39; // rax
  __int64 v40; // r15
  BOOL v41; // edi
  __int64 v42; // rcx
  Config::RegWriter *v43; // rcx
  __int128 *v44; // rbx
  __int64 v45; // rax
  __int64 v46; // rdi
  ConfigContext *v47; // rbx
  ConfigContext *v48; // rbx
  __int64 v49; // rcx
  ConfigContext *v50; // rbx
  CREWLock *v51; // rdi
  DWORD CurrentThreadId; // eax
  DWORD v53; // eax
  Config::XmlReader *v54; // rcx
  struct Config::ReplicaSetConfigList *v55; // rbx
  struct Config::VolumeConfigList *v56; // rdi
  Config::XmlReader *v57; // rcx
  struct MonitorContext *v58; // rbx
  struct MonitorContext *v59; // rcx
  struct MonitorContext *v60; // rdx
  ConfigContext *v61; // rcx
  struct Config::Machine *v62; // rbx
  unsigned int v63; // eax
  Dword *v64; // rbx
  const unsigned __int16 *v65; // rax
  struct Config::Machine *v66; // rbx
  unsigned int v67; // eax
  Dword *v68; // rbx
  const unsigned __int16 *v69; // rax
  int v70; // r8d
  struct FrsStatus *v71; // rax
  struct FrsStatus *v72; // r8
  struct FrsStatus *v73; // rcx
  int v74; // ecx
  __int64 v75; // rcx
  struct Config::ContentSetList *v77; // [rsp+20h] [rbp-E0h]
  struct FrsStatus *v78; // [rsp+30h] [rbp-D0h] BYREF
  int v79; // [rsp+38h] [rbp-C8h]
  struct FrsStatus *v80; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v81; // [rsp+48h] [rbp-B8h] BYREF
  int v82; // [rsp+50h] [rbp-B0h]
  int v83; // [rsp+54h] [rbp-ACh]
  const wchar_t *v84; // [rsp+58h] [rbp-A8h]
  int v85[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v86; // [rsp+68h] [rbp-98h] BYREF
  int v87; // [rsp+70h] [rbp-90h] BYREF
  const unsigned __int16 *v88; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v89; // [rsp+80h] [rbp-80h] BYREF
  const wchar_t *v90; // [rsp+88h] [rbp-78h] BYREF
  int v91; // [rsp+90h] [rbp-70h]
  int v92; // [rsp+94h] [rbp-6Ch]
  const wchar_t *v93; // [rsp+98h] [rbp-68h]
  int v94; // [rsp+A0h] [rbp-60h]
  int v95; // [rsp+A4h] [rbp-5Ch]
  const wchar_t *v96; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v97; // [rsp+B0h] [rbp-50h]
  const wchar_t *v98; // [rsp+B8h] [rbp-48h]
  struct Config::ReplicaSetConfigList *v99; // [rsp+D0h] [rbp-30h]
  void **v100; // [rsp+D8h] [rbp-28h] BYREF
  int v101; // [rsp+E0h] [rbp-20h]
  void **v102; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v103[3]; // [rsp+F0h] [rbp-10h] BYREF
  const wchar_t *v104; // [rsp+108h] [rbp+8h] BYREF
  __int64 v105; // [rsp+110h] [rbp+10h]
  const wchar_t *v106; // [rsp+118h] [rbp+18h]
  void **v107; // [rsp+130h] [rbp+30h] BYREF
  void *EventOrDie; // [rsp+138h] [rbp+38h] BYREF
  int v109; // [rsp+140h] [rbp+40h]
  _QWORD v110[2]; // [rsp+148h] [rbp+48h] BYREF
  int v111; // [rsp+158h] [rbp+58h]
  _QWORD v112[2]; // [rsp+160h] [rbp+60h] BYREF
  int v113; // [rsp+170h] [rbp+70h]
  unsigned __int16 *v114; // [rsp+178h] [rbp+78h] BYREF
  const wchar_t *v115; // [rsp+180h] [rbp+80h] BYREF
  int v116; // [rsp+188h] [rbp+88h]
  int v117; // [rsp+18Ch] [rbp+8Ch]
  const wchar_t *v118; // [rsp+190h] [rbp+90h]
  const wchar_t *v119; // [rsp+198h] [rbp+98h] BYREF
  int v120; // [rsp+1A0h] [rbp+A0h]
  int v121; // [rsp+1A4h] [rbp+A4h]
  const wchar_t *v122; // [rsp+1A8h] [rbp+A8h]
  const wchar_t *v123; // [rsp+1B0h] [rbp+B0h] BYREF
  int v124; // [rsp+1B8h] [rbp+B8h]
  int v125; // [rsp+1BCh] [rbp+BCh]
  const wchar_t *v126; // [rsp+1C0h] [rbp+C0h]
  const wchar_t *v127; // [rsp+1C8h] [rbp+C8h] BYREF
  int v128; // [rsp+1D0h] [rbp+D0h]
  int v129; // [rsp+1D4h] [rbp+D4h]
  const wchar_t *v130; // [rsp+1D8h] [rbp+D8h]
  void **v131; // [rsp+1E0h] [rbp+E0h]
  int v132; // [rsp+1E8h] [rbp+E8h]
  void **v133; // [rsp+1F0h] [rbp+F0h] BYREF
  _QWORD v134[3]; // [rsp+1F8h] [rbp+F8h] BYREF
  void **v135; // [rsp+210h] [rbp+110h] BYREF
  _QWORD v136[3]; // [rsp+218h] [rbp+118h] BYREF
  _BYTE v137[96]; // [rsp+230h] [rbp+130h] BYREF
  struct Config::AdConnection *v138[24]; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v139[176]; // [rsp+350h] [rbp+250h] BYREF
  void *Block[2]; // [rsp+400h] [rbp+300h] BYREF
  struct _GUID v141; // [rsp+410h] [rbp+310h] BYREF
  __int128 v142; // [rsp+420h] [rbp+320h] BYREF
  _BYTE v143[48]; // [rsp+430h] [rbp+330h] BYREF
  _BYTE v144[48]; // [rsp+460h] [rbp+360h] BYREF

  v6 = a4;
  v89 = (unsigned __int16 *)a4;
  v7 = a3;
  v86 = (unsigned __int16 *)a3;
  v80 = a2;
  v99 = a1;
  v114 = a5;
  Computer = 0;
  v78 = 0;
  v79 = 40;
  std::vector<Cluster::NodeNetworkName>::clear((char *)a3 + 8);
  (*(void (__fastcall **)(struct Config::ContentSetList *))(*(_QWORD *)v6 + 72LL))(v6);
  v9 = (struct TaskPool **)*((_QWORD *)g_MonitorContext + 1);
  if ( v9 )
  {
    Computer = FrsReplicator::DeleteSysVolContents(v9);
    v78 = Computer;
    if ( Computer )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
      {
        v127 = L"ConfigurationHelper::PollAdConfigNow";
        v128 = 214;
        v129 = 3;
        v130 = L"W2CH";
        dbgobj::DbgPrint<unsigned short,FrsStatus>(
          &v127,
          L"SYSVOL: Failed to process sysvol cleanup after demotion: %?",
          Computer);
      }
      CLEAR_ERROR(&v78);
      Computer = v78;
    }
  }
  v113 = 0;
  v112[0] = &ReplicaSetConfigLock::`vftable';
  v112[1] = ReplicaSetConfigLock::lock;
  v111 = 0;
  v110[0] = &VolumeConfigLock::`vftable';
  v110[1] = VolumeConfigLock::lock;
  Guard<CREWLock>::AcquireWriteLock(v112);
  Guard<CREWLock>::AcquireWriteLock(v110);
  v94 = Config::AdConfig::anyReadErrors;
  v95 = Config::AdConfig::anyWriteErrors;
  Config::AdConfig::anyReadErrors = 0;
  Config::AdConfig::anyWriteErrors = 0;
  if ( (unsigned int)Config::AdConfig::IsConnected(*((Config::AdConfig **)g_ConfigContext + 76))
    && Config::AdSession::GetServerName(*(Config::AdSession **)(*((_QWORD *)g_ConfigContext + 76) + 40LL))
    && a5 )
  {
    ServerName = Config::AdSession::GetServerName(*(Config::AdSession **)(*((_QWORD *)g_ConfigContext + 76) + 40LL));
    FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v85, ServerName);
    v11 = *(_QWORD *)v85;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v115 = L"ConfigurationHelper::PollAdConfigNow";
      v116 = 244;
      v117 = 5;
      v118 = L"W2CH";
      *(_QWORD *)&v142 = *(_QWORD *)v85 + 18LL;
      dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short *>(
        &v115,
        L"Current DC Name: %?, Target DC Name: %?",
        &v142,
        &v114);
    }
    if ( (unsigned int)_o__wcsicmp(v11 + 18, a5) )
      Config::AdConfig::Disconnect(*((Config::AdConfig **)g_ConfigContext + 76));
    FrsStringImpl<char,unsigned short>::ReleaseBody(v85);
  }
  v12 = 1;
  if ( !Computer )
  {
    if ( (unsigned int)Config::AdConfig::IsConnected(*((Config::AdConfig **)g_ConfigContext + 76)) )
    {
      v79 = 0;
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v90 = L"ConfigurationHelper::PollAdConfigNow";
        v91 = 338;
        v92 = 4;
        v93 = L"W2CH";
        v27 = *(void ***)(*((_QWORD *)g_ConfigContext + 76) + 40LL);
        Block[0] = v27[2];
        v88 = Config::AdSession::GetServerName((Config::AdSession *)v27);
        dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short *>(
          &v90,
          L"Connection with AD is still active. adServer:%ws dsServer:%ws",
          &v88,
          Block);
      }
    }
    else
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v104 = L"ConfigurationHelper::PollAdConfigNow";
        v105 = 0x40000010ALL;
        v106 = L"W2CH";
        dbgobj::DbgPrint<unsigned short>(&v104, L"Trying to connect to AD");
      }
      v15 = (Config::AdConfig *)*((_QWORD *)g_ConfigContext + 76);
      if ( a5 )
        v16 = Config::AdConfig::Connect(v15, a5, v13, v14, (const unsigned __int16 *)v77);
      else
        v16 = Config::AdConfig::ConnectToLocalDc(v15, 0);
      Computer = v16;
      v78 = v16;
      if ( v16 )
        goto LABEL_30;
      Computer = Config::AdConfig::GetComputer(*((Config::AdConfig **)g_ConfigContext + 76));
      v78 = Computer;
      if ( Computer )
      {
        Config::AdConfig::Disconnect(*((Config::AdConfig **)g_ConfigContext + 76));
LABEL_30:
        v79 = 12;
        v88 = 0;
        Machine = ConfigContext::GetMachine(v17);
        v88 = (const unsigned __int16 *)Machine;
        v19 = *((_DWORD *)g_ConfigContext + 154) != 0 ? -2147482444 : -1073740622;
        if ( a6 && (unsigned int)EventThrottle::IsRipe(a6, 1, 0) )
        {
          v20 = *(_QWORD *)FrsStatusString::FrsStatusString((FrsStatusString *)Block, Computer);
          v21 = Dword::Dword((Dword *)v144, *((_DWORD *)Computer + 1), 10);
          v22 = Config::BoolParam::Get((struct Config::Machine *)((char *)Machine + 776));
          v23 = Dword::Dword((Dword *)v143, v22, 10);
          FrsEvent::Log(
            v19,
            *(_QWORD *)(*(_QWORD *)(*((_QWORD *)g_ConfigContext + 76) + 40LL) + 16LL),
            v23,
            v21,
            v20,
            0);
          operator delete[](Block[0]);
        }
        v24 = g_MonitorContext;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_MonitorContext + 184));
        *((_DWORD *)v24 + 44) = 1;
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v96 = L"ConfigurationHelper::PollAdConfigNow";
          v97 = 0x500000136LL;
          v98 = L"W2CH";
          dbgobj::DbgPrint<unsigned short>(&v96, L"Update serviceInfoHistory");
        }
        v25 = g_MonitorContext;
        *((_DWORD *)g_MonitorContext + 26) = 2;
        *((_DWORD *)v25 + 22) = 4;
        *((_DWORD *)v25 + 25) = (unsigned __int16)v19;
        GetSystemTimeAsFileTime((LPFILETIME)((char *)v25 + 92));
        StateHistory::Update(
          (struct MonitorContext *)((char *)g_MonitorContext + 120),
          (struct MonitorContext *)((char *)g_MonitorContext + 32));
        v26 = g_MonitorContext;
        *((_DWORD *)g_MonitorContext + 44) = 0;
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v26 + 184));
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
        {
          v81 = L"ConfigurationHelper::PollAdConfigNow";
          v82 = 318;
          v83 = 2;
          v84 = L"W2CH";
          dbgobj::DbgPrint<unsigned short,FrsStatus>(&v81, L"(Ignored) Failed to connect to AD. Error:%?", Computer);
        }
        CLEAR_ERROR(&v78);
        ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v88);
        Computer = v78;
        v6 = (struct Config::ContentSetList *)v89;
        v7 = (struct Cluster::NodeNetworkNameList *)v86;
        goto LABEL_49;
      }
      if ( a6 )
        *((_DWORD *)a6 + 2) = 0;
      v79 = 0;
      FrsEvent::Log(1073743030, *(_QWORD *)(*(_QWORD *)(*((_QWORD *)g_ConfigContext + 76) + 40LL) + 16LL));
    }
  }
LABEL_49:
  v28 = v79;
  if ( !v79 )
  {
    v29 = g_ConfigContext;
    ConfigContext::Initialize(g_ConfigContext);
    Config::AdReader::AdReader((Config::AdReader *)v138, *((struct Config::AdConnection **)v29 + 75));
    if ( Computer )
      goto LABEL_124;
    Computer = Config::AdConfig::SetRootNamingContextsAndComputerNameWithDns(
                 (Config::AdConfig *)v138,
                 *((struct Config::AdConfig **)g_ConfigContext + 76));
    v78 = Computer;
    if ( Computer )
      goto LABEL_124;
    Computer = Config::AdReader::Read(v138, v99, v80, v7, v6);
    v78 = Computer;
    if ( Computer )
      goto LABEL_124;
    if ( dword_1403167F8 )
    {
      ObjList<_GUID>::ObjList<_GUID>(&v102);
      ObjList<_GUID>::ObjList<_GUID>(&v135);
      ObjList<_GUID>::ObjList<_GUID>(&v133);
      ConfigContext::CleanupClusteredConfig(v30, (_DWORD)v7, (unsigned int)&v102, (unsigned int)&v135, (__int64)&v133);
      v131 = &Config::RegWriter::`vftable';
      v100 = &Config::RegReader::`vftable';
      v86 = &FrsStringImpl<unsigned short,char>::s_Empty;
      if ( !byte_140315A80 )
      {
        _InterlockedAdd((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty, 1u);
        Computer = v78;
      }
      v32 = (struct _GUID *)v103[0];
      v33 = (__int64)(v103[1] - v103[0]) >> 4;
      if ( (_DWORD)v33 )
      {
        v34 = (unsigned int)v33;
        do
        {
          v141 = *v32;
          FrsReplicator::RemoveStaleVolumeManager(*((FrsReplicator **)g_MonitorContext + 1), &v141, v31);
          v36 = 1;
          v89 = &FrsStringImpl<unsigned short,char>::s_Empty;
          if ( !byte_140315A80 )
            _InterlockedAdd((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty, 1u);
          Computer = (struct FrsStatus *)Config::RegReader::ReadVolumeConfigValues(v35, &v141, &v89, 0, &v86);
          v78 = Computer;
          if ( Computer
            || (v87 = 0,
                Computer = (struct FrsStatus *)Cluster::ClusterUtil::IsResourceOwnedByLocalNode(&v86, &v87),
                (v78 = Computer) != 0) )
          {
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
            {
              v119 = L"ConfigurationHelper::PollAdConfigNow";
              v120 = 470;
              v121 = 3;
              v122 = L"W2CH";
              dbgobj::DbgPrint<unsigned short,_GUID,FrsStatus>(
                &v119,
                L"[CLUSTER] (Ignored) Failed to determine if this node owns the clustered volume's disk resource. Proceedi"
                 "ng with registry key deletion. volId:%? Error:%?",
                &v141,
                Computer);
            }
            CLEAR_ERROR(&v78);
            Computer = v78;
          }
          else if ( v87 )
          {
            v36 = 0;
          }
          if ( v36 )
          {
            Computer = Config::RegWriter::DeleteVolumeConfigValues(v37, &v141);
            v78 = Computer;
          }
          if ( Computer )
          {
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
            {
              v123 = L"ConfigurationHelper::PollAdConfigNow";
              v124 = 484;
              v125 = 3;
              v126 = L"W2CH";
              dbgobj::DbgPrint<unsigned short,_GUID,FrsStatus>(
                &v123,
                L"[CLUSTER] (Ignored) Failed to remove volume config from registry. volId:%? Error:%?",
                &v141,
                Computer);
            }
            CLEAR_ERROR(&v78);
            Computer = v78;
          }
          FrsStringImpl<char,unsigned short>::ReleaseBody(&v89);
          ++v32;
          --v34;
        }
        while ( v34 );
        v28 = v79;
      }
      v38 = (_OWORD *)v136[0];
      v39 = (__int64)(v136[1] - v136[0]) >> 4;
      if ( (_DWORD)v39 )
      {
        v40 = (unsigned int)v39;
        do
        {
          *(_OWORD *)Block = *v38;
          FrsReplicator::RemoveStaleReplicaSetManager(
            *((FrsReplicator **)g_MonitorContext + 1),
            (const struct _GUID *)Block,
            v31);
          v41 = 1;
          Computer = (struct FrsStatus *)Config::RegReader::ReadReplicaConfigValues(v42, Block, 0, 0, &v86);
          v78 = Computer;
          if ( Computer
            || (v85[0] = 0,
                Computer = (struct FrsStatus *)Cluster::ClusterUtil::IsResourceOwnedByLocalNode(&v86, v85),
                (v78 = Computer) != 0) )
          {
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
            {
              v81 = L"ConfigurationHelper::PollAdConfigNow";
              v82 = 566;
              v83 = 3;
              v84 = L"W2CH";
              dbgobj::DbgPrint<unsigned short,_GUID,FrsStatus>(
                &v81,
                L"[CLUSTER] (Ignored) Failed to determine if this node owns the clustered replica set's VCO resource. Proc"
                 "eeding with registry key deletion. rgId:%? Error:%?",
                Block,
                Computer);
            }
            CLEAR_ERROR(&v78);
            Computer = v78;
          }
          else
          {
            v41 = v85[0] == 0;
          }
          if ( v41 )
          {
            Computer = Config::RegWriter::DeleteReplicaConfigValues(v43, (const struct _GUID *)Block);
            v78 = Computer;
          }
          if ( Computer )
          {
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
            {
              v81 = L"ConfigurationHelper::PollAdConfigNow";
              v82 = 580;
              v83 = 3;
              v84 = L"W2CH";
              dbgobj::DbgPrint<unsigned short,_GUID,FrsStatus>(
                &v81,
                L"[CLUSTER] (Ignored) Failed to remove replica set config from registry. rgId:%? Error:%?",
                Block,
                Computer);
            }
            CLEAR_ERROR(&v78);
            Computer = v78;
          }
          ++v38;
          --v40;
        }
        while ( v40 );
        v28 = v79;
      }
      v44 = (__int128 *)v134[0];
      v45 = (__int64)(v134[1] - v134[0]) >> 4;
      if ( (_DWORD)v45 )
      {
        v46 = (unsigned int)v45;
        do
        {
          v142 = *v44;
          FrsReplicator::SetContentSetStatus(*((_QWORD *)g_MonitorContext + 1), &v142, 1);
          ++v44;
          --v46;
        }
        while ( v46 );
      }
      FrsStringImpl<char,unsigned short>::ReleaseBody(&v86);
      v133 = &ObjList<_GUID>::`vftable';
      std::vector<_GUID>::_Tidy(v134);
      v135 = &ObjList<_GUID>::`vftable';
      std::vector<_GUID>::_Tidy(v136);
      v102 = &ObjList<_GUID>::`vftable';
      std::vector<_GUID>::_Tidy(v103);
      if ( Computer )
        goto LABEL_124;
    }
    Computer = Config::AdConfig::UpdateSpn((Config::AdConfig *)v138);
    v78 = Computer;
    if ( Computer )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v81 = L"ConfigurationHelper::PollAdConfigNow";
        v82 = 614;
        v83 = 2;
        v84 = L"W2CH";
        dbgobj::DbgPrint<unsigned short,FrsStatus>(
          &v81,
          L"(Ignored) Failed to register service principal name. Error:%?",
          Computer);
      }
      CLEAR_ERROR(&v78);
      Computer = v78;
    }
    if ( Computer )
      goto LABEL_124;
    Computer = Config::AdConfig::UpdateVersion((Config::AdConfig *)v138, (struct Config::AdSnapshot *)v139);
    v78 = Computer;
    if ( Computer )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v81 = L"ConfigurationHelper::PollAdConfigNow";
        v82 = 629;
        v83 = 2;
        v84 = L"W2CH";
        dbgobj::DbgPrint<unsigned short,FrsStatus>(&v81, L"(Ignored) Failed to update version info. Error:%?", Computer);
      }
      CLEAR_ERROR(&v78);
      Computer = v78;
    }
    if ( Computer )
    {
LABEL_124:
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v96 = L"ConfigurationHelper::PollAdConfigNow";
        v97 = 0x200000295LL;
        v98 = L"W2CH";
        dbgobj::DbgPrint<unsigned short,FrsStatus>(&v96, L"(Ignored) Error while polling %?", Computer);
      }
      CLEAR_ERROR(&v78);
    }
    else
    {
      WorkPathList::WorkPathList((WorkPathList *)&v102);
      Config::AdReader::ReadFrsWorkPaths((Config::AdReader *)v138, (struct WorkPathList *)&v102);
      v47 = g_ConfigContext;
      ConfigContext::Initialize(g_ConfigContext);
      WorkPathTable::Delete((char *)v47 + 400);
      v48 = g_ConfigContext;
      ConfigContext::Initialize(g_ConfigContext);
      WorkPathTable::Add((ConfigContext *)((char *)v48 + 400), (struct WorkPathList *)&v102);
      v102 = &WorkPathList::`vftable';
      RefList<WorkPath>::~RefList<WorkPath>(&v102);
      PtrList<_GUID>::PtrList<_GUID>(&v104);
      PtrList<_GUID>::PtrList<_GUID>(&v96);
      ConfigContext::GetClearPrimaryFlagCsGuids(v49, &v104);
      if ( (unsigned int)((__int64)&v106[v105 / 0xFFFFFFFFFFFFFFFEuLL] >> 3) )
      {
        Config::AdConfig::ClearPrimaryBit(v138, v139, &v104, &v96);
        if ( (unsigned int)(((__int64)v98 - v97) >> 3) )
        {
          v50 = g_ConfigContext;
          v51 = (ConfigContext *)((char *)g_ConfigContext + 496);
          CurrentThreadId = GetCurrentThreadId();
          CREWLock::AcquireWriteLock(v51, CurrentThreadId);
          Config::ContentSetList::Delete((char *)v50 + 728, &v96);
          v53 = GetCurrentThreadId();
          CREWLock::Release(v51, v53);
        }
      }
      PtrList<_GUID>::~PtrList<_GUID>(&v96);
      PtrList<_GUID>::~PtrList<_GUID>(&v104);
    }
    v132 = 1;
    v131 = &Config::XmlReader::`vftable';
    v55 = v99;
    Config::XmlReader::PostProcessReplicaSetConfig(v54, v99);
    v56 = v80;
    Config::XmlReader::PostProcessVolumeConfig(v57, v80);
    if ( (*(unsigned int (__fastcall **)(struct Config::ReplicaSetConfigList *))(*(_QWORD *)v55 + 40LL))(v55) )
    {
      v101 = 1;
      v100 = &Config::XmlWriter::`vftable';
      Config::XmlWriter::MergeAdConfig((Config::XmlWriter *)&v100, v55, v56);
      v100 = &Config::XmlConfig::`vftable';
    }
    v58 = g_MonitorContext;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_MonitorContext + 184));
    *((_DWORD *)v58 + 44) = 1;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v81 = L"ConfigurationHelper::PollAdConfigNow";
      v82 = 689;
      v83 = 5;
      v84 = L"W2CH";
      dbgobj::DbgPrint<unsigned short>(&v81, L"Update serviceInfoHistory");
    }
    v59 = g_MonitorContext;
    if ( *((_DWORD *)g_MonitorContext + 26) == 2 && *((_DWORD *)g_MonitorContext + 22) == 4 )
    {
      *((_DWORD *)g_MonitorContext + 22) = 0;
      *((_DWORD *)v59 + 25) = 0;
      GetSystemTimeAsFileTime((LPFILETIME)((char *)v59 + 92));
      v60 = g_MonitorContext;
      *((_DWORD *)g_MonitorContext + 26) = 1;
      StateHistory::Update((struct MonitorContext *)((char *)v60 + 120), (struct MonitorContext *)((char *)v60 + 32));
      v59 = g_MonitorContext;
    }
    *((_DWORD *)v59 + 44) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v59 + 184));
    Config::AdReader::~AdReader((Config::AdReader *)v138);
    if ( v94 && !Config::AdConfig::anyReadErrors )
    {
      v80 = 0;
      v62 = ConfigContext::GetMachine(v61);
      v80 = v62;
      FrsEvent::Reset(3221231474LL);
      FrsEvent::Reset(2147489652LL);
      FrsEvent::Reset(3221231478LL);
      FrsEvent::Reset(3221231480LL);
      FrsEvent::Reset(2147489658LL);
      FrsEvent::Reset(3221231484LL);
      v63 = Config::BoolParam::Get((struct Config::Machine *)((char *)v62 + 776));
      v64 = Dword::Dword((Dword *)v143, v63, 10);
      v65 = Config::AdSession::GetServerName(*(Config::AdSession **)(*((_QWORD *)g_ConfigContext + 76) + 40LL));
      FrsEvent::Log(1073747838, v65, v64);
      ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v80);
    }
    if ( v95 && !Config::AdConfig::anyWriteErrors )
    {
      v80 = 0;
      v66 = ConfigContext::GetMachine(v61);
      v80 = v66;
      FrsEvent::Reset(2147489664LL);
      v67 = Config::BoolParam::Get((struct Config::Machine *)((char *)v66 + 776));
      v68 = Dword::Dword((Dword *)v143, v67, 10);
      v69 = Config::AdSession::GetServerName(*(Config::AdSession **)(*((_QWORD *)g_ConfigContext + 76) + 40LL));
      FrsEvent::Log(1073747842, v69, v68);
      ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v80);
    }
  }
  Guard<CREWLock>::Release(v110);
  Guard<CREWLock>::Release(v112);
  v107 = &ShutdownObject::`vftable';
  v109 = 0;
  EventOrDie = CreateEventOrDie(1, 0);
  Migration::SysVolMigration::SysVolMigration((Migration::SysVolMigration *)v137, (struct ShutdownObject *)&v107, v70);
  v71 = Migration::SysVolMigration::IsLocalComputerLongHornLevelDc((Migration::SysVolMigration *)v137);
  v72 = v71;
  v80 = v71;
  v85[0] = 0;
  if ( v71 )
  {
    v12 = 0;
    v73 = v71;
  }
  else
  {
    v72 = Migration::SysVolMigration::ShouldExit((Migration::SysVolMigration *)v137, v85);
    v80 = v72;
    v73 = v72;
    if ( !v72 )
    {
      if ( v85[0] )
        goto LABEL_161;
      goto LABEL_159;
    }
  }
  v74 = *((_DWORD *)v73 + 1) - 9501;
  if ( !v74 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v90 = L"ConfigurationHelper::PollAdConfigNow";
      v91 = 769;
      v92 = 5;
      v93 = L"W2CH";
      dbgobj::DbgPrint<unsigned short>(&v90, L"Not Windows Server 2008 domain funcional level");
    }
    goto LABEL_157;
  }
  if ( v74 == 1 )
  {
LABEL_157:
    v12 = 0;
    goto LABEL_158;
  }
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
  {
    v90 = L"ConfigurationHelper::PollAdConfigNow";
    v91 = 779;
    v92 = 3;
    v93 = L"W2CH";
    dbgobj::DbgPrint<unsigned short,FrsStatus>(&v90, L"Failed to get migration status. Error:%?", v72);
  }
LABEL_158:
  CLEAR_ERROR(&v80);
  if ( !v12 )
    goto LABEL_161;
LABEL_159:
  v75 = *((_QWORD *)g_MonitorContext + 1);
  if ( v75 )
    Task::Schedule(*(Task **)(v75 + 504));
LABEL_161:
  Migration::SysVolMigration::~SysVolMigration((Migration::SysVolMigration *)v137);
  v107 = &ShutdownObject::`vftable';
  CloseHandleEx(&EventOrDie);
  Guard<CREWLock>::~Guard<CREWLock>(v110);
  Guard<CREWLock>::~Guard<CREWLock>(v112);
  return v28;
}

```

## disassembly

```asm
0x1400c9710  push    rbp
0x1400c9712  push    rbx
0x1400c9713  push    rsi
0x1400c9714  push    rdi
0x1400c9715  push    r12
0x1400c9717  push    r13
0x1400c9719  push    r14
0x1400c971b  push    r15
0x1400c971d  lea     rbp, [rsp-3A8h]
0x1400c9725  sub     rsp, 4A8h
0x1400c972c  mov     rax, cs:__security_cookie
0x1400c9733  xor     rax, rsp
0x1400c9736  mov     [rbp+3E0h+var_50], rax
0x1400c973d  mov     r15, r9
0x1400c9740  mov     [rbp+3E0h+var_460], r9
0x1400c9744  mov     r12, r8
0x1400c9747  mov     [rsp+4E0h+var_478], r8
0x1400c974c  mov     [rsp+4E0h+var_4A0], rdx
0x1400c9751  mov     [rbp+3E0h+var_410], rcx
0x1400c9755  mov     rdi, [rbp+3E0h+arg_20]
0x1400c975c  mov     [rbp+3E0h+var_368], rdi
0x1400c9760  mov     r13, [rbp+3E0h+arg_28]
0x1400c9767  xor     ebx, ebx
0x1400c9769  mov     esi, ebx
0x1400c976b  mov     [rsp+4E0h+var_4B0], rbx
0x1400c9770  mov     [rsp+4E0h+var_4A8], 28h ; '('
0x1400c9778  lea     rcx, [r8+8]
0x1400c977c  call    ?clear@?$vector@VNodeNetworkName@Cluster@@V?$allocator@VNodeNetworkName@Cluster@@@std@@@std@@QEAAXXZ; std::vector<Cluster::NodeNetworkName>::clear(void)
0x1400c9781  mov     rax, [r15]
0x1400c9784  mov     rcx, r15
0x1400c9787  mov     rax, [rax+48h]
0x1400c978b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400c9790  mov     rax, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x1400c9797  mov     rcx, [rax+8]; this
0x1400c979b  lea     r14, aConfigurationh; "ConfigurationHelper::PollAdConfigNow"
0x1400c97a2  test    rcx, rcx
0x1400c97a5  jz      short loc_1400C981E
0x1400c97a7  call    ?DeleteSysVolContents@FrsReplicator@@QEAAPEAVFrsStatus@@XZ; FrsReplicator::DeleteSysVolContents(void)
0x1400c97ac  mov     rsi, rax
0x1400c97af  mov     [rsp+4E0h+var_4B0], rax
0x1400c97b4  test    rax, rax
0x1400c97b7  jz      short loc_1400C981E
0x1400c97b9  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400c97c0  test    rax, rax
0x1400c97c3  jz      short loc_1400C980F
0x1400c97c5  cmp     [rax+40h], ebx
0x1400c97c8  jz      short loc_1400C980F
0x1400c97ca  cmp     dword ptr [rax+38h], 3
0x1400c97ce  jl      short loc_1400C980F
0x1400c97d0  mov     [rbp+3E0h+var_318], r14
0x1400c97d7  mov     [rbp+3E0h+var_310], 0D6h
0x1400c97e1  mov     [rbp+3E0h+var_30C], 3
0x1400c97eb  lea     rax, aW2ch; "W2CH"
0x1400c97f2  mov     [rbp+3E0h+var_308], rax
0x1400c97f9  mov     r8, rsi
0x1400c97fc  lea     rdx, aSysvolFailedTo_19; "SYSVOL: Failed to process sysvol cleanu"...
0x1400c9803  lea     rcx, [rbp+3E0h+var_318]
0x1400c980a  call    ??$DbgPrint@GVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStatus>(ushort const *,FrsStatus const &)
0x1400c980f  lea     rcx, [rsp+4E0h+var_4B0]; struct FrsStatus **
0x1400c9814  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1400c9819  mov     rsi, [rsp+4E0h+var_4B0]
0x1400c981e  mov     [rbp+3E0h+var_370], ebx
0x1400c9821  lea     rax, ??_7ReplicaSetConfigLock@@6B@; const ReplicaSetConfigLock::`vftable'
0x1400c9828  mov     [rbp+3E0h+var_380], rax
0x1400c982c  mov     rax, cs:?lock@ReplicaSetConfigLock@@1PEAVCREWLock@@EA; CREWLock * ReplicaSetConfigLock::lock
0x1400c9833  mov     [rbp+3E0h+var_378], rax
0x1400c9837  mov     [rbp+3E0h+var_388], ebx
0x1400c983a  lea     rax, ??_7VolumeConfigLock@@6B@; const VolumeConfigLock::`vftable'
0x1400c9841  mov     [rbp+3E0h+var_398], rax
0x1400c9845  mov     rax, cs:?lock@VolumeConfigLock@@1PEAVCREWLock@@EA; CREWLock * VolumeConfigLock::lock
0x1400c984c  mov     [rbp+3E0h+var_390], rax
0x1400c9850  lea     rcx, [rbp+3E0h+var_380]
0x1400c9854  call    ?AcquireWriteLock@?$Guard@VCREWLock@@@@QEAAXXZ; Guard<CREWLock>::AcquireWriteLock(void)
0x1400c9859  lea     rcx, [rbp+3E0h+var_398]
0x1400c985d  call    ?AcquireWriteLock@?$Guard@VCREWLock@@@@QEAAXXZ; Guard<CREWLock>::AcquireWriteLock(void)
0x1400c9862  mov     eax, cs:?anyReadErrors@AdConfig@Config@@1HA; int Config::AdConfig::anyReadErrors
0x1400c9868  mov     [rbp+3E0h+var_440], eax
0x1400c986b  mov     eax, cs:?anyWriteErrors@AdConfig@Config@@1HA; int Config::AdConfig::anyWriteErrors
0x1400c9871  mov     [rbp+3E0h+var_43C], eax
0x1400c9874  mov     cs:?anyReadErrors@AdConfig@Config@@1HA, ebx; int Config::AdConfig::anyReadErrors
0x1400c987a  mov     cs:?anyWriteErrors@AdConfig@Config@@1HA, ebx; int Config::AdConfig::anyWriteErrors
0x1400c9880  mov     rcx, cs:?g_ConfigContext@@3PEAVConfigContext@@EA; ConfigContext * g_ConfigContext
0x1400c9887  mov     rcx, [rcx+260h]; this
0x1400c988e  call    ?IsConnected@AdConfig@Config@@QEAAHXZ; Config::AdConfig::IsConnected(void)
0x1400c9893  test    eax, eax
0x1400c9895  jz      loc_1400C998F
0x1400c989b  mov     rax, cs:?g_ConfigContext@@3PEAVConfigContext@@EA; ConfigContext * g_ConfigContext
0x1400c98a2  mov     rcx, [rax+260h]
0x1400c98a9  mov     rcx, [rcx+28h]; this
0x1400c98ad  call    ?GetServerName@AdSession@Config@@QEBAPEBGXZ; Config::AdSession::GetServerName(void)
0x1400c98b2  test    rax, rax
0x1400c98b5  jz      loc_1400C998F
0x1400c98bb  test    rdi, rdi
0x1400c98be  jz      loc_1400C998F
0x1400c98c4  mov     rax, cs:?g_ConfigContext@@3PEAVConfigContext@@EA; ConfigContext * g_ConfigContext
0x1400c98cb  mov     rcx, [rax+260h]
0x1400c98d2  mov     rcx, [rcx+28h]; this
0x1400c98d6  call    ?GetServerName@AdSession@Config@@QEBAPEBGXZ; Config::AdSession::GetServerName(void)
0x1400c98db  mov     rdx, rax
0x1400c98de  lea     rcx, [rsp+4E0h+var_480]
0x1400c98e3  call    ??0?$FrsStringImpl@GD@@QEAA@PEBG@Z; FrsStringImpl<ushort,char>::FrsStringImpl<ushort,char>(ushort const *)
0x1400c98e8  nop
0x1400c98e9  mov     rbx, qword ptr [rsp+4E0h+var_480]
0x1400c98ee  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400c98f5  test    rax, rax
0x1400c98f8  jz      short loc_1400C9958
0x1400c98fa  cmp     dword ptr [rax+40h], 0
0x1400c98fe  jz      short loc_1400C9958
0x1400c9900  cmp     dword ptr [rax+38h], 5
0x1400c9904  jl      short loc_1400C9958
0x1400c9906  mov     [rbp+3E0h+var_360], r14
0x1400c990d  mov     [rbp+3E0h+var_358], 0F4h
0x1400c9917  mov     [rbp+3E0h+var_354], 5
0x1400c9921  lea     rax, aW2ch; "W2CH"
0x1400c9928  mov     [rbp+3E0h+var_350], rax
0x1400c992f  lea     rax, [rbx+12h]
0x1400c9933  mov     qword ptr [rbp+3E0h+var_C0], rax
0x1400c993a  lea     r9, [rbp+3E0h+var_368]
0x1400c993e  lea     r8, [rbp+3E0h+var_C0]
0x1400c9945  lea     rdx, aCurrentDcNameT; "Current DC Name: %?, Target DC Name: %?"
0x1400c994c  lea     rcx, [rbp+3E0h+var_360]
0x1400c9953  call    ??$DbgPrint@GPEBGPEAG@dbgobj@@QEAA_KPEBGAEBQEBGAEBQEAG@Z; dbgobj::DbgPrint<ushort,ushort const *,ushort *>(ushort const *,ushort const * const &,ushort * const &)
0x1400c9958  lea     rcx, [rbx+12h]
0x1400c995c  mov     rdx, rdi
0x1400c995f  call    cs:__imp__o__wcsicmp
0x1400c9966  nop     dword ptr [rax+rax+00h]
0x1400c996b  xor     ebx, ebx
0x1400c996d  test    eax, eax
0x1400c996f  jz      short loc_1400C9985
0x1400c9971  mov     rcx, cs:?g_ConfigContext@@3PEAVConfigContext@@EA; ConfigContext * g_ConfigContext
0x1400c9978  mov     rcx, [rcx+260h]; this
0x1400c997f  call    ?Disconnect@AdConfig@Config@@QEAAXXZ; Config::AdConfig::Disconnect(void)
0x1400c9984  nop
0x1400c9985  lea     rcx, [rsp+4E0h+var_480]
0x1400c998a  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1400c998f  mov     r14d, 1
0x1400c9995  test    rsi, rsi
0x1400c9998  jnz     loc_1400C9D31
0x1400c999e  mov     rcx, cs:?g_ConfigContext@@3PEAVConfigContext@@EA; ConfigContext * g_ConfigContext
0x1400c99a5  mov     rcx, [rcx+260h]; this
0x1400c99ac  call    ?IsConnected@AdConfig@Config@@QEAAHXZ; Config::AdConfig::IsConnected(void)
0x1400c99b1  test    eax, eax
0x1400c99b3  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400c99ba  jnz     loc_1400C9CB6
0x1400c99c0  test    rax, rax
0x1400c99c3  jz      short loc_1400C9A04
0x1400c99c5  cmp     [rax+40h], ebx
0x1400c99c8  jz      short loc_1400C9A04
0x1400c99ca  cmp     dword ptr [rax+38h], 4
0x1400c99ce  jl      short loc_1400C9A04
0x1400c99d0  lea     rax, aConfigurationh; "ConfigurationHelper::PollAdConfigNow"
0x1400c99d7  mov     [rbp+3E0h+var_3D8], rax
0x1400c99db  mov     dword ptr [rbp+3E0h+var_3D0], 10Ah
0x1400c99e2  mov     dword ptr [rbp+3E0h+var_3D0+4], 4
0x1400c99e9  lea     rax, aW2ch; "W2CH"
0x1400c99f0  mov     [rbp+3E0h+var_3C8], rax
0x1400c99f4  lea     rdx, aTryingToConnec_0; "Trying to connect to AD"
0x1400c99fb  lea     rcx, [rbp+3E0h+var_3D8]
0x1400c99ff  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1400c9a04  mov     rax, cs:?g_ConfigContext@@3PEAVConfigContext@@EA; ConfigContext * g_ConfigContext
0x1400c9a0b  mov     rcx, [rax+260h]; this
0x1400c9a12  test    rdi, rdi
0x1400c9a15  jz      short loc_1400C9A21
0x1400c9a17  mov     rdx, rdi; unsigned __int16 *
0x1400c9a1a  call    ?Connect@AdConfig@Config@@QEAAPEAVFrsStatus@@PEBG000@Z; Config::AdConfig::Connect(ushort const *,ushort const *,ushort const *,ushort const *)
0x1400c9a1f  jmp     short loc_1400C9A28
0x1400c9a21  xor     edx, edx; int
0x1400c9a23  call    ?ConnectToLocalDc@AdConfig@Config@@QEAAPEAVFrsStatus@@H@Z; Config::AdConfig::ConnectToLocalDc(int)
0x1400c9a28  mov     rsi, rax
0x1400c9a2b  mov     [rsp+4E0h+var_4B0], rax
0x1400c9a30  test    rax, rax
0x1400c9a33  jnz     short loc_1400C9A6C
0x1400c9a35  mov     rcx, cs:?g_ConfigContext@@3PEAVConfigContext@@EA; ConfigContext * g_ConfigContext
0x1400c9a3c  mov     rcx, [rcx+260h]; this
0x1400c9a43  call    ?GetComputer@AdConfig@Config@@QEAAPEAVFrsStatus@@XZ; Config::AdConfig::GetComputer(void)
0x1400c9a48  mov     rsi, rax
0x1400c9a4b  mov     [rsp+4E0h+var_4B0], rax
0x1400c9a50  test    rax, rax
0x1400c9a53  jz      loc_1400C9C87
0x1400c9a59  mov     rcx, cs:?g_ConfigContext@@3PEAVConfigContext@@EA; ConfigContext * g_ConfigContext
0x1400c9a60  mov     rcx, [rcx+260h]; this
0x1400c9a67  call    ?Disconnect@AdConfig@Config@@QEAAXXZ; Config::AdConfig::Disconnect(void)
0x1400c9a6c  mov     [rsp+4E0h+var_4A8], 0Ch
0x1400c9a74  mov     [rsp+4E0h+var_468], rbx
0x1400c9a79  call    ?GetMachine@ConfigContext@@QEAAPEAVMachine@Config@@XZ; ConfigContext::GetMachine(void)
0x1400c9a7e  mov     r12, rax
0x1400c9a81  mov     [rsp+4E0h+var_468], rax
0x1400c9a86  mov     rax, cs:?g_ConfigContext@@3PEAVConfigContext@@EA; ConfigContext * g_ConfigContext
0x1400c9a8d  mov     edx, [rax+268h]
0x1400c9a93  neg     edx
0x1400c9a95  sbb     r15d, r15d
0x1400c9a98  and     r15d, 0C0000002h
0x1400c9a9f  add     r15d, 0C00004B2h
0x1400c9aa6  test    r13, r13
0x1400c9aa9  jz      loc_1400C9B4C
0x1400c9aaf  xor     r8d, r8d; unsigned int
0x1400c9ab2  mov     edx, r14d; int
0x1400c9ab5  mov     rcx, r13; this
0x1400c9ab8  call    ?IsRipe@EventThrottle@@QEAAHHK@Z; EventThrottle::IsRipe(int,ulong)
0x1400c9abd  test    eax, eax
0x1400c9abf  jz      loc_1400C9B4C
0x1400c9ac5  mov     rdx, rsi; struct FrsStatus *
0x1400c9ac8  lea     rcx, [rbp+3E0h+Block]; this
0x1400c9acf  call    ??0FrsStatusString@@QEAA@PEBVFrsStatus@@@Z; FrsStatusString::FrsStatusString(FrsStatus const *)
0x1400c9ad4  nop
0x1400c9ad5  mov     rdi, [rax]
0x1400c9ad8  mov     r13d, 0Ah
0x1400c9ade  mov     r8d, r13d; int
0x1400c9ae1  mov     edx, [rsi+4]; unsigned int
0x1400c9ae4  lea     rcx, [rbp+3E0h+var_80]; this
0x1400c9aeb  call    ??0Dword@@QEAA@KH@Z; Dword::Dword(ulong,int)
0x1400c9af0  mov     rbx, rax
0x1400c9af3  lea     rcx, [r12+308h]; this
0x1400c9afb  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x1400c9b00  mov     edx, eax; unsigned int
0x1400c9b02  mov     r8d, r13d; int
0x1400c9b05  lea     rcx, [rbp+3E0h+var_B0]; this
0x1400c9b0c  call    ??0Dword@@QEAA@KH@Z; Dword::Dword(ulong,int)
0x1400c9b11  mov     r8, rax
0x1400c9b14  mov     rax, cs:?g_ConfigContext@@3PEAVConfigContext@@EA; ConfigContext * g_ConfigContext
0x1400c9b1b  mov     rcx, [rax+260h]
0x1400c9b22  mov     rax, [rcx+28h]
0x1400c9b26  and     [rsp+4E0h+var_4B8], 0
0x1400c9b2b  mov     [rsp+4E0h+var_4C0], rdi
0x1400c9b30  mov     r9, rbx
0x1400c9b33  mov     rdx, [rax+10h]
0x1400c9b37  mov     ecx, r15d
0x1400c9b3a  call    ?Log@FrsEvent@@SAXW4FrsEventsEnum4@@PEBG111W4LogUseDebugLog@EventLog@@@Z; FrsEvent::Log(FrsEventsEnum4,ushort const *,ushort const *,ushort const *,ushort const *,EventLog::LogUseDebugLog)
0x1400c9b3f  nop
0x1400c9b40  mov     rcx, [rbp+3E0h+Block]; Block
0x1400c9b47  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x1400c9b4c  mov     rbx, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x1400c9b53  lea     rcx, [rbx+0B8h]; lpCriticalSection
0x1400c9b5a  call    cs:__imp_EnterCriticalSection
0x1400c9b61  nop     dword ptr [rax+rax+00h]
0x1400c9b66  mov     [rbx+0B0h], r14d
0x1400c9b6d  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400c9b74  xor     ebx, ebx
0x1400c9b76  lea     rdi, aConfigurationh; "ConfigurationHelper::PollAdConfigNow"
0x1400c9b7d  lea     r12, aW2ch; "W2CH"
0x1400c9b84  test    rax, rax
0x1400c9b87  jz      short loc_1400C9BBA
0x1400c9b89  cmp     [rax+40h], ebx
0x1400c9b8c  jz      short loc_1400C9BBA
0x1400c9b8e  cmp     dword ptr [rax+38h], 5
0x1400c9b92  jl      short loc_1400C9BBA
0x1400c9b94  mov     [rbp+3E0h+var_438], rdi
0x1400c9b98  mov     dword ptr [rbp+3E0h+var_430], 136h
0x1400c9b9f  mov     dword ptr [rbp+3E0h+var_430+4], 5
0x1400c9ba6  mov     [rbp+3E0h+var_428], r12
0x1400c9baa  lea     rdx, aUpdateServicei; "Update serviceInfoHistory"
0x1400c9bb1  lea     rcx, [rbp+3E0h+var_438]
0x1400c9bb5  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1400c9bba  mov     rcx, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x1400c9bc1  mov     r13d, 2
0x1400c9bc7  mov     [rcx+68h], r13d
0x1400c9bcb  mov     dword ptr [rcx+58h], 4
0x1400c9bd2  movzx   eax, r15w
0x1400c9bd6  mov     [rcx+64h], eax
0x1400c9bd9  add     rcx, 5Ch ; '\'; lpSystemTimeAsFileTime
0x1400c9bdd  call    cs:__imp_GetSystemTimeAsFileTime
0x1400c9be4  nop     dword ptr [rax+rax+00h]
0x1400c9be9  mov     rdx, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x1400c9bf0  lea     rcx, [rdx+78h]; this
0x1400c9bf4  add     rdx, 20h ; ' '; struct HistoryRecord *
0x1400c9bf8  call    ?Update@StateHistory@@MEAAXPEAVHistoryRecord@@@Z; StateHistory::Update(HistoryRecord *)
0x1400c9bfd  mov     rcx, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x1400c9c04  mov     [rcx+0B0h], ebx
0x1400c9c0a  add     rcx, 0B8h; lpCriticalSection
0x1400c9c11  call    cs:__imp_LeaveCriticalSection
0x1400c9c18  nop     dword ptr [rax+rax+00h]
0x1400c9c1d  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400c9c24  test    rax, rax
0x1400c9c27  jz      short loc_1400C9C5F
0x1400c9c29  cmp     [rax+40h], ebx
0x1400c9c2c  jz      short loc_1400C9C5F
0x1400c9c2e  cmp     [rax+38h], r13d
0x1400c9c32  jl      short loc_1400C9C5F
0x1400c9c34  mov     [rsp+4E0h+var_498], rdi
0x1400c9c39  mov     [rsp+4E0h+var_490], 13Eh
0x1400c9c41  mov     [rsp+4E0h+var_48C], r13d
0x1400c9c46  mov     [rsp+4E0h+var_488], r12
0x1400c9c4b  mov     r8, rsi
0x1400c9c4e  lea     rdx, aIgnoredFailedT_98; "(Ignored) Failed to connect to AD. Erro"...
0x1400c9c55  lea     rcx, [rsp+4E0h+var_498]
0x1400c9c5a  call    ??$DbgPrint@GVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStatus>(ushort const *,FrsStatus const &)
0x1400c9c5f  lea     rcx, [rsp+4E0h+var_4B0]; struct FrsStatus **
0x1400c9c64  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1400c9c69  nop
0x1400c9c6a  lea     rcx, [rsp+4E0h+var_468]
0x1400c9c6f  call    ??1?$ScopedRef@VReplicaSet@Config@@@@QEAA@XZ; ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(void)
0x1400c9c74  mov     rsi, [rsp+4E0h+var_4B0]
0x1400c9c79  mov     r15, [rbp+3E0h+var_460]
0x1400c9c7d  mov     r12, [rsp+4E0h+var_478]
0x1400c9c82  jmp     loc_1400C9D31
0x1400c9c87  test    r13, r13
0x1400c9c8a  jz      short loc_1400C9C90
0x1400c9c8c  mov     [r13+8], ebx
0x1400c9c90  mov     [rsp+4E0h+var_4A8], ebx
0x1400c9c94  mov     rax, cs:?g_ConfigContext@@3PEAVConfigContext@@EA; ConfigContext * g_ConfigContext
  ... truncated ...
```
