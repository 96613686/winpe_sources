# Config::AdReader::Read(Config::ReplicaSetConfigList *,Config::VolumeConfigList *,Cluster::NodeNetworkNameList &,Config::ContentSetList &)

- ea: `0x1401ec574`
- end: `0x1401ece4b`
- name: `?Read@AdReader@Config@@QEAAPEAVFrsStatus@@PEAVReplicaSetConfigList@2@PEAVVolumeConfigList@2@AEAVNodeNetworkNameList@Cluster@@AEAVContentSetList@2@@Z`
- size: `2263`
- prototype: `struct FrsStatus *__usercall@<rax>(Config::AdReader *__hidden this@<rcx>, struct Config::ReplicaSetConfigList *@<rdx>, struct Config::VolumeConfigList *@<r8>, struct Cluster::NodeNetworkNameList *@<r9>, struct Config::ContentSetList *)`
- caller_count: `1`
- callee_count: `35`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400c9710`

## callees

- `0x14000c910`
- `0x14000cd1c`
- `0x14000cdc0`
- `0x14000e34c`
- `0x14000ee94`
- `0x14001bf80`
- `0x14001c1ac`
- `0x14001cfa0`
- `0x14001d768`
- `0x14001dc18`
- `0x14001dcd8`
- `0x14001e644`
- `0x14002179c`
- `0x140048e60`
- `0x1400533fc`
- `0x1400546d4`
- `0x1400c91a4`
- `0x1400c967c`
- `0x1401b9494`
- `0x1401d6a00`
- `0x1401de1e0`
- `0x1401de698`
- `0x1401e1ee8`
- `0x1401e5638`
- `0x1401e56f0`
- `0x1401e9aa0`
- `0x1401eb3a0`
- `0x1401ec574`
- `0x1401ee9c8`
- `0x1401eeaa0`
- `0x1401ef978`
- `0x1401f3094`
- `0x140201420`
- `0x140203d04`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1401ec75d`
- `KERNEL32!GetCurrentThreadId` at `0x1401ec85e`
- `KERNEL32!GetCurrentThreadId` at `0x1401ec988`
- `KERNEL32!GetCurrentThreadId` at `0x1401eca2e`
- `KERNEL32!GetCurrentThreadId` at `0x1401ecb86`
- `KERNEL32!GetCurrentThreadId` at `0x1401ecdbb`
- `KERNEL32!GetCurrentThreadId` at `0x1401ecde7`
- `KERNEL32!GetCurrentThreadId` at `0x1401ec75d`
- `KERNEL32!GetCurrentThreadId` at `0x1401ec85e`
- `KERNEL32!GetCurrentThreadId` at `0x1401ec988`
- `KERNEL32!GetCurrentThreadId` at `0x1401eca2e`
- `KERNEL32!GetCurrentThreadId` at `0x1401ecb86`
- `KERNEL32!GetCurrentThreadId` at `0x1401ecdbb`
- `KERNEL32!GetCurrentThreadId` at `0x1401ecde7`

## string_xrefs

- `0x1401ec885`: `Config::AdReader::Read`
- `0x1401ecba3`: `Config::AdReader::Read`
- `0x1401ece04`: `Config::AdReader::Read`
- `0x1401ec648`: `Config::AdReader::Read`
- `0x1401ec7fd`: `Config::AdReader::Read`
- `0x1401ec9f2`: `Config::AdReader::Read`
- `0x1401ecb48`: `Config::AdReader::Read`
- `0x1401ecc70`: `Config::AdReader::Read`
- `0x1401eca1d`: `Failed to ReadReplicationTopology(). Error:%?`
- `0x1401ec68f`: `[SYSVOL] (Ignored) Failed to create SysVol objects, Error:%?`
- `0x1401ec74c`: `Failed to ReadReplicationMembership() computerDn:%ws Error:%?`
- `0x1401ec84d`: `Failed to ReadReplicationMembership() computerDn:%ws Error:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
struct FrsStatus *__fastcall Config::AdReader::Read(
        struct Config::AdConnection **this,
        struct Config::ReplicaSetConfigList *a2,
        struct Config::VolumeConfigList *a3,
        struct Cluster::NodeNetworkNameList *a4,
        struct Config::ContentSetList *a5)
{
  struct FrsStatus *result; // rax
  const struct Config::AdObject *v9; // rdx
  struct FrsStatus *SysVolObjects; // rax
  struct FrsStatus *v11; // rcx
  const unsigned __int16 *Value; // rax
  struct FrsStatus *ReplicationMembership; // rbx
  __int64 v14; // rcx
  unsigned int i; // esi
  __int64 v16; // rax
  const unsigned __int16 *v17; // rax
  __int64 v18; // rax
  __int64 v19; // r9
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // rdi
  __int64 v23; // rsi
  unsigned int j; // r12d
  __int64 v25; // rax
  struct FrsStatus *SysVolGlobalFlags; // rbx
  unsigned int *ReplicationTopolgy; // rsi
  unsigned int k; // ebx
  __int64 v29; // r12
  const unsigned __int16 *v30; // rax
  __int64 v31; // rax
  DWORD v32; // eax
  __int64 v33; // rcx
  unsigned int v34; // ebx
  _QWORD *v35; // rsi
  struct FrsStatus *v36; // rax
  const unsigned __int16 *ServerName; // rax
  unsigned int m; // r12d
  __int64 v39; // rbx
  const unsigned __int16 *v40; // rax
  DWORD CurrentThreadId; // eax
  __int64 v42; // rcx
  int v43; // [rsp+38h] [rbp-D0h]
  DWORD v44; // [rsp+40h] [rbp-C8h]
  void *v45; // [rsp+48h] [rbp-C0h]
  const wchar_t *v46; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v47; // [rsp+60h] [rbp-A8h]
  const wchar_t *v48; // [rsp+68h] [rbp-A0h]
  __int64 v49; // [rsp+70h] [rbp-98h] BYREF
  __int64 v50; // [rsp+78h] [rbp-90h] BYREF
  _QWORD v51[5]; // [rsp+80h] [rbp-88h] BYREF
  _QWORD v52[10]; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD v53[30]; // [rsp+F8h] [rbp-10h] BYREF
  struct FrsStatus *v56; // [rsp+210h] [rbp+108h] BYREF

  std::vector<Cluster::NodeNetworkName>::clear((char *)a4 + 8);
  (*(void (__fastcall **)(struct Config::ContentSetList *))(*(_QWORD *)a5 + 72LL))(a5);
  Config::ReplicaSetList::ReplicaSetList((Config::ReplicaSetList *)v52);
  Config::ReplicaSetConfigList::Get(a2, (struct Config::ReplicaSetList *)v52);
  v52[0] = &Config::ReplicaSetList::`vftable';
  Config::ParamBlockRefList<Config::ReplicaSet,9>::~ParamBlockRefList<Config::ReplicaSet,9>(v52);
  result = Config::AdConfig::GetComputer((Config::AdConfig *)this);
  if ( result )
    return result;
  v9 = this[13];
  if ( !v9 )
  {
    CurrentThreadId = GetCurrentThreadId();
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v42,
                                 1168,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\ad\\ad.cpp",
                                 "Config::AdReader::Read",
                                 11567,
                                 CurrentThreadId,
                                 0);
  }
  Config::AdWriter::AdWriter((Config::AdWriter *)v53, v9, this[5]);
  SysVolObjects = Config::AdConfig::SetRootNamingContextsAndComputerNameWithDns(
                    (Config::AdConfig *)v53,
                    (struct Config::AdConfig *)this);
  v56 = SysVolObjects;
  v11 = SysVolObjects;
  if ( !SysVolObjects )
  {
    SysVolObjects = Config::AdWriter::CreateSysVolObjects((Config::AdWriter *)v53);
    v56 = SysVolObjects;
    v11 = SysVolObjects;
  }
  if ( v11 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v46 = L"Config::AdReader::Read";
      v47 = 0x200002D43LL;
      v48 = L"CFAD";
      dbgobj::DbgPrint<unsigned short,FrsStatus>(
        &v46,
        L"[SYSVOL] (Ignored) Failed to create SysVol objects, Error:%?",
        SysVolObjects);
    }
    CLEAR_ERROR(&v56);
  }
  std::vector<Cluster::NodeNetworkName>::operator=(this + 42, this + 20);
  *((_DWORD *)this + 90) = *((_DWORD *)this + 46);
  std::vector<Cluster::NodeNetworkName>::operator=((char *)a4 + 8, this + 20);
  *((_DWORD *)a4 + 8) = *((_DWORD *)this + 46);
  Value = Config::AdStrAttr::GetValue(*((Config::AdStrAttr **)this[13] + 5));
  ReplicationMembership = Config::AdSnapshot::ReadReplicationMembership(
                            (Config::AdSnapshot *)(this + 24),
                            Value,
                            (const struct Config::AdConfig *)this);
  if ( ReplicationMembership )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v46 = L"Config::AdReader::Read";
      v47 = 0x400002D58LL;
      v48 = L"CFAD";
      dbgobj::DbgPrint<unsigned short,unsigned short const *,FrsStatus>(
        &v46,
        L"Failed to ReadReplicationMembership() computerDn:%ws Error:%?",
        this + 3,
        ReplicationMembership);
    }
    v45 = ReplicationMembership;
    v44 = GetCurrentThreadId();
    v43 = 11611;
    goto LABEL_26;
  }
  for ( i = 0; i < (unsigned int)((this[16] - this[15]) >> 3); ++i )
  {
    v16 = std::vector<ShutdownObject *>::at(this + 15, i);
    v17 = Config::AdStrAttr::GetValue(*(Config::AdStrAttr **)(*(_QWORD *)v16 + 40LL));
    ReplicationMembership = Config::AdSnapshot::ReadReplicationMembership(
                              (Config::AdSnapshot *)(this + 24),
                              v17,
                              (const struct Config::AdConfig *)this);
    if ( ReplicationMembership )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v46 = L"Config::AdReader::Read";
        v47 = 0x400002D62LL;
        v48 = L"CFAD";
        v18 = std::vector<ShutdownObject *>::at(this + 15, i);
        a5 = (struct Config::ContentSetList *)Config::AdStrAttr::GetValue(*(Config::AdStrAttr **)(*(_QWORD *)v18 + 40LL));
        dbgobj::DbgPrint<unsigned short,unsigned short const *,FrsStatus>(
          &v46,
          L"Failed to ReadReplicationMembership() computerDn:%ws Error:%?",
          &a5,
          ReplicationMembership);
      }
      v45 = ReplicationMembership;
      v44 = GetCurrentThreadId();
      v43 = 11621;
LABEL_26:
      v19 = *(unsigned int *)ReplicationMembership;
      v20 = *((unsigned int *)ReplicationMembership + 2);
      v21 = *((unsigned int *)ReplicationMembership + 1);
LABEL_27:
      v22 = FrsStatusList::PushNewError(
              v14,
              v21,
              v20,
              v19,
              "base\\fs\\remotefs\\frs\\src\\ad\\ad.cpp",
              "Config::AdReader::Read",
              v43,
              v44,
              v45);
      goto LABEL_57;
    }
  }
  Config::AdConfig::subscriptionsChecksum = 0;
  v23 = (this[26] - this[25]) >> 3;
  for ( j = 0; j < (unsigned int)v23; ++j )
  {
    Config::AdObjectList::AdObjectList(v51, 0);
    v25 = std::vector<ShutdownObject *>::at(this + 25, j);
    Config::AdObjectList::GetAllGrandChildren(
      *(Config::AdObjectList **)(*(_QWORD *)v25 + 80LL),
      (struct Config::AdObjectList *)v51);
    Config::AdConfig::subscriptionsChecksum += Config::AdObjectList::Checksum((Config::AdObjectList *)v51);
    v51[0] = &Config::AdObjectList::`vftable';
    PtrList<Config::AdObject>::~PtrList<Config::AdObject>(v51);
  }
  if ( *((_DWORD *)this[5] + 7) )
  {
    SysVolGlobalFlags = Config::AdReader::IsLocalComputerLongHornLevelDc((Config::AdReader *)this);
    v56 = SysVolGlobalFlags;
    ReplicationTopolgy = (unsigned int *)SysVolGlobalFlags;
    if ( SysVolGlobalFlags
      || (SysVolGlobalFlags = Config::AdReader::GetSysVolGlobalFlags(
                                (Config::AdReader *)this,
                                &Config::AdConfig::migrationGlobalStateFlags),
          v56 = SysVolGlobalFlags,
          (ReplicationTopolgy = (unsigned int *)SysVolGlobalFlags) != 0) )
    {
      if ( ReplicationTopolgy[1] != 2 && ReplicationTopolgy[1] != 1168 && ReplicationTopolgy[1] != 9501 )
      {
        v45 = SysVolGlobalFlags;
        v44 = GetCurrentThreadId();
        v43 = 11667;
        v19 = *(unsigned int *)SysVolGlobalFlags;
        v20 = *((unsigned int *)SysVolGlobalFlags + 2);
LABEL_79:
        v21 = ReplicationTopolgy[1];
        goto LABEL_27;
      }
      CLEAR_ERROR(&v56);
    }
  }
  ReplicationTopolgy = (unsigned int *)Config::AdSnapshot::ReadReplicationTopolgy(
                                         (Config::AdSnapshot *)(this + 24),
                                         (const struct Config::AdConfig *)this);
  v56 = (struct FrsStatus *)ReplicationTopolgy;
  if ( ReplicationTopolgy )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v46 = L"Config::AdReader::Read";
      v47 = 0x400002D9DLL;
      v48 = L"CFAD";
      dbgobj::DbgPrint<unsigned short,FrsStatus>(
        &v46,
        L"Failed to ReadReplicationTopology(). Error:%?",
        ReplicationTopolgy);
    }
    v45 = ReplicationTopolgy;
    v44 = GetCurrentThreadId();
    v43 = 11678;
LABEL_78:
    v20 = ReplicationTopolgy[2];
    v19 = *ReplicationTopolgy;
    goto LABEL_79;
  }
  for ( k = 0; k < (unsigned int)((this[26] - this[25]) >> 3); ++k )
  {
    v49 = (__int64)&FrsStringImpl<unsigned short,char>::s_Empty;
    if ( !byte_140315A80 )
      _InterlockedAdd((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty, 1u);
    v29 = *(_QWORD *)std::vector<ShutdownObject *>::at(this + 25, k);
    if ( k
      && (v30 = Config::AdStrAttr::GetValue(*(Config::AdStrAttr **)(v29 + 48)),
          v31 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(&v50, v30),
          ReplicationTopolgy = (unsigned int *)Cluster::NodeNetworkNameList::GetVcoResourceNameFromDns(
                                                 this + 19,
                                                 v31,
                                                 &v49),
          FrsStringImpl<char,unsigned short>::ReleaseBody(&v50),
          ReplicationTopolgy)
      || (ReplicationTopolgy = (unsigned int *)Config::AdReader::ReadSettings(
                                                 (Config::AdReader *)this,
                                                 (__int64)&v49,
                                                 (__int64)a5),
          (v56 = (struct FrsStatus *)ReplicationTopolgy) != 0) )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
      {
        v46 = L"Config::AdReader::Read";
        v47 = 0x300002DB9LL;
        v48 = L"CFAD";
        dbgobj::DbgPrint<unsigned short>(&v46, L"The connection to AD,DS was aborted. Retrying next cycle");
      }
      v32 = GetCurrentThreadId();
      v22 = FrsStatusList::PushNewError(
              v33,
              ReplicationTopolgy[1],
              ReplicationTopolgy[2],
              *ReplicationTopolgy,
              "base\\fs\\remotefs\\frs\\src\\ad\\ad.cpp",
              "Config::AdReader::Read",
              11706,
              v32,
              ReplicationTopolgy);
      FrsStringImpl<char,unsigned short>::ReleaseBody(&v49);
      goto LABEL_57;
    }
    FrsStringImpl<char,unsigned short>::ReleaseBody(&v49);
  }
  v34 = 0;
  while ( v34 < (*(unsigned int (__fastcall **)(struct Config::ReplicaSetConfigList *))(*(_QWORD *)a2 + 40LL))(a2) )
  {
    v35 = (_QWORD *)(*(__int64 (__fastcall **)(struct Config::ReplicaSetConfigList *, _QWORD))(*(_QWORD *)a2 + 48LL))(
                      a2,
                      v34);
    v36 = Config::ReplicaSetConfig::Validate((Config::ReplicaSetConfig *)v35, 1);
    v56 = v36;
    if ( !v36 )
      goto LABEL_69;
    if ( *((_DWORD *)v36 + 1) != 9109 )
    {
      if ( *((_DWORD *)v36 + 1) == 9110 )
        Config::AdConfig::anyReadErrors = 1;
LABEL_69:
      Config::StringParam::Set((Config::StringParam *)(v35 + 13), L"1.0");
      ServerName = Config::AdSession::GetServerName(this[5]);
      Config::StringParam::Set((Config::StringParam *)(v35[18] + 240LL), ServerName);
      ++v34;
      goto LABEL_70;
    }
    Config::AdConfig::anyReadErrors = 1;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v46 = L"Config::AdReader::Read";
      v47 = 0x300002DCELL;
      v48 = L"CFAD";
      a5 = (struct Config::ContentSetList *)(v35[18] + 368LL);
      dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v46, L"Dropping bad replication group. rgId:%ws", &a5);
    }
    v34 = (*(__int64 (__fastcall **)(struct Config::ReplicaSetConfigList *, _QWORD))(*(_QWORD *)a2 + 64LL))(a2, v34);
LABEL_70:
    CLEAR_ERROR(&v56);
    ReplicationTopolgy = (unsigned int *)v56;
  }
  for ( m = 0; m < (*(unsigned int (__fastcall **)(struct Config::VolumeConfigList *))(*(_QWORD *)a3 + 40LL))(a3); ++m )
  {
    v39 = (*(__int64 (__fastcall **)(struct Config::VolumeConfigList *, _QWORD))(*(_QWORD *)a3 + 48LL))(a3, m);
    Config::StringParam::Set((Config::StringParam *)(v39 + 104), L"1.0");
    v40 = Config::AdSession::GetServerName(this[5]);
    Config::StringParam::Set((Config::StringParam *)(*(_QWORD *)(v39 + 144) + 456LL), v40);
  }
  v22 = 0;
  if ( !Config::AdConfig::anyReadErrors )
    Config::AdConfig::anyReadErrors = *((_DWORD *)this + 81);
  if ( ReplicationTopolgy )
  {
    v45 = ReplicationTopolgy;
    v44 = GetCurrentThreadId();
    v43 = 11770;
    goto LABEL_78;
  }
LABEL_57:
  v53[0] = &Config::AdWriter::`vftable';
  Config::AdConfig::~AdConfig((Config::AdConfig *)v53);
  return (struct FrsStatus *)v22;
}

```

## disassembly

```asm
0x1401ec574  mov     rax, rsp
0x1401ec577  mov     [rax+8], rbx
0x1401ec57b  mov     [rax+18h], r8
0x1401ec57f  mov     [rax+10h], rdx
0x1401ec583  push    rbp
0x1401ec584  push    rsi
0x1401ec585  push    rdi
0x1401ec586  push    r12
0x1401ec588  push    r13
0x1401ec58a  push    r14
0x1401ec58c  push    r15
0x1401ec58e  lea     rbp, [rax-0E8h]
0x1401ec595  sub     rsp, 1B0h
0x1401ec59c  mov     rsi, r9
0x1401ec59f  mov     rbx, rdx
0x1401ec5a2  mov     r14, rcx
0x1401ec5a5  lea     rcx, [r9+8]
0x1401ec5a9  call    ?clear@?$vector@VNodeNetworkName@Cluster@@V?$allocator@VNodeNetworkName@Cluster@@@std@@@std@@QEAAXXZ; std::vector<Cluster::NodeNetworkName>::clear(void)
0x1401ec5ae  mov     rcx, [rbp+0E0h+arg_20]
0x1401ec5b5  mov     rax, [rcx]
0x1401ec5b8  mov     rax, [rax+48h]
0x1401ec5bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ec5c1  lea     rcx, [rbp+0E0h+var_140]; this
0x1401ec5c5  call    ??0ReplicaSetList@Config@@QEAA@XZ; Config::ReplicaSetList::ReplicaSetList(void)
0x1401ec5ca  nop
0x1401ec5cb  lea     rdx, [rbp+0E0h+var_140]; struct Config::ReplicaSetList *
0x1401ec5cf  mov     rcx, rbx; this
0x1401ec5d2  call    ?Get@ReplicaSetConfigList@Config@@QEAAXPEAVReplicaSetList@2@@Z; Config::ReplicaSetConfigList::Get(Config::ReplicaSetList *)
0x1401ec5d7  nop
0x1401ec5d8  lea     rax, ??_7ReplicaSetList@Config@@6B@; const Config::ReplicaSetList::`vftable'
0x1401ec5df  mov     [rbp+0E0h+var_140], rax
0x1401ec5e3  lea     rcx, [rbp+0E0h+var_140]
0x1401ec5e7  call    ??1?$ParamBlockRefList@VReplicaSet@Config@@$08@Config@@UEAA@XZ; Config::ParamBlockRefList<Config::ReplicaSet,9>::~ParamBlockRefList<Config::ReplicaSet,9>(void)
0x1401ec5ec  mov     rcx, r14; this
0x1401ec5ef  call    ?GetComputer@AdConfig@Config@@QEAAPEAVFrsStatus@@XZ; Config::AdConfig::GetComputer(void)
0x1401ec5f4  xor     edi, edi
0x1401ec5f6  test    rax, rax
0x1401ec5f9  jnz     loc_1401ECE2F
0x1401ec5ff  mov     rdx, [r14+68h]; struct Config::AdObject *
0x1401ec603  test    rdx, rdx
0x1401ec606  jz      loc_1401ECDE7
0x1401ec60c  mov     r8, [r14+28h]; struct Config::AdConnection *
0x1401ec610  lea     rcx, [rbp+0E0h+var_F0]; this
0x1401ec614  call    ??0AdWriter@Config@@QEAA@PEBVAdObject@1@PEAVAdConnection@1@@Z; Config::AdWriter::AdWriter(Config::AdObject const *,Config::AdConnection *)
0x1401ec619  nop
0x1401ec61a  mov     rdx, r14; struct Config::AdConfig *
0x1401ec61d  lea     rcx, [rbp+0E0h+var_F0]; this
0x1401ec621  call    ?SetRootNamingContextsAndComputerNameWithDns@AdConfig@Config@@QEAAPEAVFrsStatus@@PEAV12@@Z; Config::AdConfig::SetRootNamingContextsAndComputerNameWithDns(Config::AdConfig *)
0x1401ec626  mov     [rbp+0E0h+arg_18], rax
0x1401ec62d  mov     rcx, rax
0x1401ec630  test    rax, rax
0x1401ec633  jnz     short loc_1401EC648
0x1401ec635  lea     rcx, [rbp+0E0h+var_F0]; this
0x1401ec639  call    ?CreateSysVolObjects@AdWriter@Config@@QEAAPEAVFrsStatus@@XZ; Config::AdWriter::CreateSysVolObjects(void)
0x1401ec63e  mov     [rbp+0E0h+arg_18], rax
0x1401ec645  mov     rcx, rax
0x1401ec648  lea     r12, aConfigAdreader_17; "Config::AdReader::Read"
0x1401ec64f  lea     rdx, aCfad; "CFAD"
0x1401ec656  test    rcx, rcx
0x1401ec659  jz      short loc_1401EC6AC
0x1401ec65b  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401ec662  test    rcx, rcx
0x1401ec665  jz      short loc_1401EC6A0
0x1401ec667  cmp     [rcx+40h], edi
0x1401ec66a  jz      short loc_1401EC6A0
0x1401ec66c  cmp     dword ptr [rcx+38h], 2
0x1401ec670  jl      short loc_1401EC6A0
0x1401ec672  mov     qword ptr [rsp+1E0h+var_190], r12
0x1401ec677  mov     dword ptr [rsp+1E0h+var_188], 2D43h
0x1401ec67f  mov     dword ptr [rsp+1E0h+var_188+4], 2
0x1401ec687  mov     [rsp+1E0h+var_180], rdx
0x1401ec68c  mov     r8, rax
0x1401ec68f  lea     rdx, aSysvolIgnoredF; "[SYSVOL] (Ignored) Failed to create Sys"...
0x1401ec696  lea     rcx, [rsp+1E0h+var_190]
0x1401ec69b  call    ??$DbgPrint@GVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStatus>(ushort const *,FrsStatus const &)
0x1401ec6a0  lea     rcx, [rbp+0E0h+arg_18]; struct FrsStatus **
0x1401ec6a7  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1401ec6ac  lea     rbx, [r14+0A0h]
0x1401ec6b3  lea     rcx, [r14+150h]
0x1401ec6ba  mov     rdx, rbx
0x1401ec6bd  call    ??4?$vector@VNodeNetworkName@Cluster@@V?$allocator@VNodeNetworkName@Cluster@@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<Cluster::NodeNetworkName>::operator=(std::vector<Cluster::NodeNetworkName> const &)
0x1401ec6c2  mov     eax, [r14+0B8h]
0x1401ec6c9  mov     [r14+168h], eax
0x1401ec6d0  mov     rdx, rbx
0x1401ec6d3  lea     rcx, [rsi+8]
0x1401ec6d7  call    ??4?$vector@VNodeNetworkName@Cluster@@V?$allocator@VNodeNetworkName@Cluster@@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<Cluster::NodeNetworkName>::operator=(std::vector<Cluster::NodeNetworkName> const &)
0x1401ec6dc  mov     eax, [r14+0B8h]
0x1401ec6e3  mov     [rsi+20h], eax
0x1401ec6e6  mov     rcx, [r14+68h]
0x1401ec6ea  mov     rcx, [rcx+28h]; this
0x1401ec6ee  call    ?GetValue@AdStrAttr@Config@@QEBAPEBGXZ; Config::AdStrAttr::GetValue(void)
0x1401ec6f3  mov     rdx, rax; unsigned __int16 *
0x1401ec6f6  mov     r8, r14; struct Config::AdConfig *
0x1401ec6f9  lea     rcx, [r14+0C0h]; this
0x1401ec700  call    ?ReadReplicationMembership@AdSnapshot@Config@@QEAAPEAVFrsStatus@@PEBGPEBVAdConfig@2@@Z; Config::AdSnapshot::ReadReplicationMembership(ushort const *,Config::AdConfig const *)
0x1401ec705  mov     rbx, rax
0x1401ec708  test    rax, rax
0x1401ec70b  jz      short loc_1401EC77F
0x1401ec70d  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401ec714  test    rax, rax
0x1401ec717  jz      short loc_1401EC75D
0x1401ec719  cmp     [rax+40h], edi
0x1401ec71c  jz      short loc_1401EC75D
0x1401ec71e  cmp     dword ptr [rax+38h], 4
0x1401ec722  jl      short loc_1401EC75D
0x1401ec724  mov     qword ptr [rsp+1E0h+var_190], r12
0x1401ec729  mov     dword ptr [rsp+1E0h+var_188], 2D58h
0x1401ec731  mov     dword ptr [rsp+1E0h+var_188+4], 4
0x1401ec739  lea     rax, aCfad; "CFAD"
0x1401ec740  mov     [rsp+1E0h+var_180], rax
0x1401ec745  lea     r8, [r14+18h]
0x1401ec749  mov     r9, rbx
0x1401ec74c  lea     rdx, aFailedToReadre_0; "Failed to ReadReplicationMembership() c"...
0x1401ec753  lea     rcx, [rsp+1E0h+var_190]
0x1401ec758  call    ??$DbgPrint@GPEBGVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBQEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,ushort const *,FrsStatus>(ushort const *,ushort const * const &,FrsStatus const &)
0x1401ec75d  call    cs:__imp_GetCurrentThreadId
0x1401ec764  nop     dword ptr [rax+rax+00h]
0x1401ec769  mov     [rsp+40h], rbx
0x1401ec76e  mov     dword ptr [rsp+1E0h+var_1A8], eax
0x1401ec772  mov     [rsp+1E0h+var_1B0], 2D5Bh
0x1401ec77a  jmp     loc_1401EC87B
0x1401ec77f  mov     esi, edi
0x1401ec781  mov     rcx, rbx
0x1401ec784  lea     r13, [r14+78h]
0x1401ec788  mov     r15d, 1
0x1401ec78e  mov     rax, [r13+8]
0x1401ec792  sub     rax, [r13+0]
0x1401ec796  sar     rax, 3
0x1401ec79a  cmp     esi, eax
0x1401ec79c  jnb     loc_1401EC8AA
0x1401ec7a2  test    rcx, rcx
0x1401ec7a5  jnz     loc_1401EC8AA
0x1401ec7ab  mov     r12d, esi
0x1401ec7ae  mov     edx, esi
0x1401ec7b0  mov     rcx, r13
0x1401ec7b3  call    ?at@?$vector@PEAVShutdownObject@@V?$allocator@PEAVShutdownObject@@@std@@@std@@QEAAAEAPEAVShutdownObject@@_K@Z; std::vector<ShutdownObject *>::at(unsigned __int64)
0x1401ec7b8  mov     rcx, [rax]
0x1401ec7bb  mov     rcx, [rcx+28h]; this
0x1401ec7bf  call    ?GetValue@AdStrAttr@Config@@QEBAPEBGXZ; Config::AdStrAttr::GetValue(void)
0x1401ec7c4  mov     rdx, rax; unsigned __int16 *
0x1401ec7c7  mov     r8, r14; struct Config::AdConfig *
0x1401ec7ca  lea     rcx, [r14+0C0h]; this
0x1401ec7d1  call    ?ReadReplicationMembership@AdSnapshot@Config@@QEAAPEAVFrsStatus@@PEBGPEBVAdConfig@2@@Z; Config::AdSnapshot::ReadReplicationMembership(ushort const *,Config::AdConfig const *)
0x1401ec7d6  mov     rbx, rax
0x1401ec7d9  test    rax, rax
0x1401ec7dc  jnz     short loc_1401EC7E6
0x1401ec7de  add     esi, r15d
0x1401ec7e1  mov     rcx, rdi
0x1401ec7e4  jmp     short loc_1401EC78E
0x1401ec7e6  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401ec7ed  test    rax, rax
0x1401ec7f0  jz      short loc_1401EC85E
0x1401ec7f2  cmp     [rax+40h], edi
0x1401ec7f5  jz      short loc_1401EC85E
0x1401ec7f7  cmp     dword ptr [rax+38h], 4
0x1401ec7fb  jl      short loc_1401EC85E
0x1401ec7fd  lea     rax, aConfigAdreader_17; "Config::AdReader::Read"
0x1401ec804  mov     qword ptr [rsp+1E0h+var_190], rax
0x1401ec809  mov     dword ptr [rsp+1E0h+var_188], 2D62h
0x1401ec811  mov     dword ptr [rsp+1E0h+var_188+4], 4
0x1401ec819  lea     rax, aCfad; "CFAD"
0x1401ec820  mov     [rsp+1E0h+var_180], rax
0x1401ec825  mov     rdx, r12
0x1401ec828  mov     rcx, r13
0x1401ec82b  call    ?at@?$vector@PEAVShutdownObject@@V?$allocator@PEAVShutdownObject@@@std@@@std@@QEAAAEAPEAVShutdownObject@@_K@Z; std::vector<ShutdownObject *>::at(unsigned __int64)
0x1401ec830  mov     rcx, [rax]
0x1401ec833  mov     rcx, [rcx+28h]; this
0x1401ec837  call    ?GetValue@AdStrAttr@Config@@QEBAPEBGXZ; Config::AdStrAttr::GetValue(void)
0x1401ec83c  mov     [rbp+0E0h+arg_20], rax
0x1401ec843  mov     r9, rbx
0x1401ec846  lea     r8, [rbp+0E0h+arg_20]
0x1401ec84d  lea     rdx, aFailedToReadre_0; "Failed to ReadReplicationMembership() c"...
0x1401ec854  lea     rcx, [rsp+1E0h+var_190]
0x1401ec859  call    ??$DbgPrint@GPEBGVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBQEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,ushort const *,FrsStatus>(ushort const *,ushort const * const &,FrsStatus const &)
0x1401ec85e  call    cs:__imp_GetCurrentThreadId
0x1401ec865  nop     dword ptr [rax+rax+00h]
0x1401ec86a  mov     [rsp+40h], rbx
0x1401ec86f  mov     dword ptr [rsp+1E0h+var_1A8], eax
0x1401ec873  mov     [rsp+1E0h+var_1B0], 2D65h
0x1401ec87b  mov     r9d, [rbx]
0x1401ec87e  mov     r8d, [rbx+8]
0x1401ec882  mov     edx, [rbx+4]
0x1401ec885  lea     rax, aConfigAdreader_14; "Config::AdReader::Read"
0x1401ec88c  mov     [rsp+1E0h+var_1B8], rax
0x1401ec891  lea     rax, aBaseFsRemotefs_10; "base\\fs\\remotefs\\frs\\src\\ad\\ad.cp"...
0x1401ec898  mov     [rsp+1E0h+var_1C0], rax
0x1401ec89d  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401ec8a2  mov     rdi, rax
0x1401ec8a5  jmp     loc_1401ECBD8
0x1401ec8aa  mov     cs:?subscriptionsChecksum@AdConfig@Config@@1_KA, rdi; unsigned __int64 Config::AdConfig::subscriptionsChecksum
0x1401ec8b1  lea     r13, [r14+0C8h]
0x1401ec8b8  mov     rsi, [r13+8]
0x1401ec8bc  sub     rsi, [r13+0]
0x1401ec8c0  sar     rsi, 3
0x1401ec8c4  mov     r12d, edi
0x1401ec8c7  test    esi, esi
0x1401ec8c9  jz      short loc_1401EC928
0x1401ec8cb  test    rbx, rbx
0x1401ec8ce  jnz     short loc_1401EC928
0x1401ec8d0  xor     edx, edx
0x1401ec8d2  lea     rcx, [rsp+1E0h+var_168]
0x1401ec8d7  call    ??0AdObjectList@Config@@QEAA@W4PtrListFreeStrategy@@@Z; Config::AdObjectList::AdObjectList(PtrListFreeStrategy)
0x1401ec8dc  nop
0x1401ec8dd  mov     edx, r12d
0x1401ec8e0  mov     rcx, r13
0x1401ec8e3  call    ?at@?$vector@PEAVShutdownObject@@V?$allocator@PEAVShutdownObject@@@std@@@std@@QEAAAEAPEAVShutdownObject@@_K@Z; std::vector<ShutdownObject *>::at(unsigned __int64)
0x1401ec8e8  mov     rcx, [rax]
0x1401ec8eb  lea     rdx, [rsp+1E0h+var_168]; struct Config::AdObjectList *
0x1401ec8f0  mov     rcx, [rcx+50h]; this
0x1401ec8f4  call    ?GetAllGrandChildren@AdObjectList@Config@@QEAAXPEAV12@@Z; Config::AdObjectList::GetAllGrandChildren(Config::AdObjectList *)
0x1401ec8f9  lea     rcx, [rsp+1E0h+var_168]; this
0x1401ec8fe  call    ?Checksum@AdObjectList@Config@@QEBA_KXZ; Config::AdObjectList::Checksum(void)
0x1401ec903  add     cs:?subscriptionsChecksum@AdConfig@Config@@1_KA, rax; unsigned __int64 Config::AdConfig::subscriptionsChecksum
0x1401ec90a  lea     rax, ??_7AdObjectList@Config@@6B@; const Config::AdObjectList::`vftable'
0x1401ec911  mov     [rsp+1E0h+var_168], rax
0x1401ec916  lea     rcx, [rsp+1E0h+var_168]
0x1401ec91b  call    ??1?$PtrList@VAdObject@Config@@@@UEAA@XZ; PtrList<Config::AdObject>::~PtrList<Config::AdObject>(void)
0x1401ec920  add     r12d, r15d
0x1401ec923  cmp     r12d, esi
0x1401ec926  jb      short loc_1401EC8CB
0x1401ec928  mov     rax, [r14+28h]
0x1401ec92c  cmp     [rax+1Ch], edi
0x1401ec92f  jz      loc_1401EC9BD
0x1401ec935  mov     rcx, r14; this
0x1401ec938  call    ?IsLocalComputerLongHornLevelDc@AdReader@Config@@QEAAPEAVFrsStatus@@XZ; Config::AdReader::IsLocalComputerLongHornLevelDc(void)
0x1401ec93d  mov     rbx, rax
0x1401ec940  mov     [rbp+0E0h+arg_18], rax
0x1401ec947  mov     rsi, rax
0x1401ec94a  test    rax, rax
0x1401ec94d  jnz     short loc_1401EC970
0x1401ec94f  lea     rdx, ?migrationGlobalStateFlags@AdConfig@Config@@1KA; unsigned int *
0x1401ec956  mov     rcx, r14; this
0x1401ec959  call    ?GetSysVolGlobalFlags@AdReader@Config@@QEAAPEAVFrsStatus@@AEAK@Z; Config::AdReader::GetSysVolGlobalFlags(ulong &)
0x1401ec95e  mov     rbx, rax
0x1401ec961  mov     [rbp+0E0h+arg_18], rax
0x1401ec968  mov     rsi, rax
0x1401ec96b  test    rax, rax
0x1401ec96e  jz      short loc_1401EC9BD
0x1401ec970  cmp     dword ptr [rsi+4], 2
0x1401ec974  jz      short loc_1401EC9B1
0x1401ec976  cmp     dword ptr [rsi+4], 490h
0x1401ec97d  jz      short loc_1401EC9B1
0x1401ec97f  cmp     dword ptr [rsi+4], 251Dh
0x1401ec986  jz      short loc_1401EC9B1
0x1401ec988  call    cs:__imp_GetCurrentThreadId
0x1401ec98f  nop     dword ptr [rax+rax+00h]
0x1401ec994  mov     [rsp+40h], rbx
0x1401ec999  mov     dword ptr [rsp+1E0h+var_1A8], eax
0x1401ec99d  mov     [rsp+1E0h+var_1B0], 2D93h
0x1401ec9a5  mov     r9d, [rbx]
0x1401ec9a8  mov     r8d, [rbx+8]
0x1401ec9ac  jmp     loc_1401ECDDF
0x1401ec9b1  lea     rcx, [rbp+0E0h+arg_18]; struct FrsStatus **
0x1401ec9b8  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1401ec9bd  mov     rdx, r14; struct Config::AdConfig *
0x1401ec9c0  lea     rcx, [r14+0C0h]; this
0x1401ec9c7  call    ?ReadReplicationTopolgy@AdSnapshot@Config@@QEAAPEAVFrsStatus@@PEBVAdConfig@2@@Z; Config::AdSnapshot::ReadReplicationTopolgy(Config::AdConfig const *)
0x1401ec9cc  mov     rsi, rax
0x1401ec9cf  mov     [rbp+0E0h+arg_18], rax
0x1401ec9d6  test    rax, rax
0x1401ec9d9  jz      short loc_1401ECA50
0x1401ec9db  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401ec9e2  test    rax, rax
0x1401ec9e5  jz      short loc_1401ECA2E
0x1401ec9e7  cmp     [rax+40h], edi
0x1401ec9ea  jz      short loc_1401ECA2E
0x1401ec9ec  cmp     dword ptr [rax+38h], 4
0x1401ec9f0  jl      short loc_1401ECA2E
0x1401ec9f2  lea     rax, aConfigAdreader_17; "Config::AdReader::Read"
0x1401ec9f9  mov     qword ptr [rsp+1E0h+var_190], rax
0x1401ec9fe  mov     dword ptr [rsp+1E0h+var_188], 2D9Dh
0x1401eca06  mov     dword ptr [rsp+1E0h+var_188+4], 4
0x1401eca0e  lea     rax, aCfad; "CFAD"
0x1401eca15  mov     [rsp+1E0h+var_180], rax
0x1401eca1a  mov     r8, rsi
0x1401eca1d  lea     rdx, aFailedToReadre; "Failed to ReadReplicationTopology(). Er"...
0x1401eca24  lea     rcx, [rsp+1E0h+var_190]
0x1401eca29  call    ??$DbgPrint@GVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStatus>(ushort const *,FrsStatus const &)
0x1401eca2e  call    cs:__imp_GetCurrentThreadId
0x1401eca35  nop     dword ptr [rax+rax+00h]
0x1401eca3a  mov     [rsp+40h], rsi
0x1401eca3f  mov     dword ptr [rsp+1E0h+var_1A8], eax
0x1401eca43  mov     [rsp+1E0h+var_1B0], 2D9Eh
0x1401eca4b  jmp     loc_1401ECDD8
0x1401eca50  mov     ebx, edi
0x1401eca52  mov     r12, rsi
0x1401eca55  mov     rax, [r13+8]
0x1401eca59  sub     rax, [r13+0]
0x1401eca5d  sar     rax, 3
0x1401eca61  cmp     ebx, eax
0x1401eca63  jnb     loc_1401ECBF4
0x1401eca69  test    r12, r12
0x1401eca6c  jnz     loc_1401ECBF4
0x1401eca72  lea     rax, ?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1401eca79  mov     [rsp+1E0h+var_178], rax
0x1401eca7e  cmp     cs:byte_140315A80, dil
0x1401eca85  jnz     short loc_1401ECA8F
0x1401eca87  lock add cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A, r15d; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1401eca8f  mov     edx, ebx
0x1401eca91  mov     rcx, r13
  ... truncated ...
```
