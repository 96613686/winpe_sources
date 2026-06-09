# Meet::Download(ShutdownObject &,Meet::RelatedToUpdate const &,Meet::RelatedToUpdate const &,FileId const &,int,StageReader * &,FileId &)

- ea: `0x14017e2e8`
- end: `0x14017f30c`
- name: `?Download@Meet@@AEAAPEAVFrsStatus@@AEAVShutdownObject@@AEBVRelatedToUpdate@1@1AEBVFileId@@HAEAPEAVStageReader@@AEAV5@@Z`
- size: `4132`
- prototype: `struct FrsStatus *__fastcall(Meet *__hidden this, struct ShutdownObject *, const struct Meet::RelatedToUpdate *, const struct Meet::RelatedToUpdate *, const struct FileId *, int, struct StageReader **, struct FileId *)`
- caller_count: `3`
- callee_count: `46`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14017f314`
- `0x140180328`
- `0x140185024`

## callees

- `0x1400036a0`
- `0x1400036d0`
- `0x14000c910`
- `0x14000cd1c`
- `0x14000daa0`
- `0x14000e34c`
- `0x140022d1c`
- `0x140024be4`
- `0x140028fcc`
- `0x1400370bc`
- `0x140047e14`
- `0x140047e4c`
- `0x140052d28`
- `0x14006a428`
- `0x14006a490`
- `0x14006d538`
- `0x1400727e8`
- `0x14009d478`
- `0x14009d5e0`
- `0x1400aebc0`
- `0x1401091e0`
- `0x140118934`
- `0x14011f074`
- `0x14011f974`
- `0x14014be98`
- `0x14014fa30`
- `0x1401648a4`
- `0x14016c694`
- `0x14016c85c`
- `0x140170738`
- `0x14017af28`
- `0x14017b008`
- `0x14017b310`
- `0x14017b7e4`
- `0x14017d1f0`
- `0x14017d58c`
- `0x14017ddf8`
- `0x14017dea8`
- `0x14017e2e8`
- `0x1401842fc`
- `0x140188594`
- `0x14018aa90`
- `0x1401b30b0`
- `0x1401b9390`
- `0x1401b9494`
- `0x140223010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14017e774`
- `KERNEL32!LeaveCriticalSection` at `0x14017e774`
- `KERNEL32!EnterCriticalSection` at `0x14017e6e0`
- `KERNEL32!EnterCriticalSection` at `0x14017e6e0`
- `KERNEL32!GetCurrentThreadId` at `0x14017e5bd`
- `KERNEL32!GetCurrentThreadId` at `0x14017ed05`
- `KERNEL32!GetCurrentThreadId` at `0x14017f050`
- `KERNEL32!GetCurrentThreadId` at `0x14017f26e`
- `KERNEL32!GetCurrentThreadId` at `0x14017e5bd`
- `KERNEL32!GetCurrentThreadId` at `0x14017ed05`
- `KERNEL32!GetCurrentThreadId` at `0x14017f050`
- `KERNEL32!GetCurrentThreadId` at `0x14017f26e`

## string_xrefs

- `0x14017e727`: `Update idUpdateInfoHistory`
- `0x14017e58a`: `File already staged - install it.  updateName:%ws uid:%? gvsn:%? connId:%? csName:%?`
- `0x14017ebf5`: `-> DONE File contents have changed since update was sent updateName:%ws uid:%? gvsn:%? connId:%? csName:%? csId:%?`
- `0x14017e6ac`: `Start Download updateName:%ws uid:%? gvsn:%? connId:%? csName:%? csId:%?`
- `0x14017edeb`: `Done downloading content updateName:%ws uid:%? gvsn:%? connId:%? csName:%?`
- `0x14017eec2`: `(Ignored) Failed to abort download.  updateName:%ws uid:%? gvsn:%? connId:%? csName:%? Error:%?`
- `0x14017eb2b`: `Update does not exist on upstream. Tombstone local content. updateName:%ws uid:%? gvsn:%? connId:%? csName:%? csId:%?`
- `0x14017ecd2`: `Aborting staging tombstoned update updateName:%ws uid:%? gvsn:%? connId:%? csName:%?`
- `0x14017ef9d`: `(Ignored) Failed to delete.  updateName:%ws uid:%? gvsn:%? connId:%? csName:%? Error:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
struct FrsStatus *__fastcall Meet::Download(
        Meet *this,
        struct ShutdownObject *a2,
        const struct Meet::RelatedToUpdate *a3,
        const wchar_t *a4,
        const struct FileId *a5,
        int a6,
        struct StageReader **a7,
        struct FileId *a8)
{
  __int128 v11; // xmm6
  __int64 v12; // rbx
  __int64 v13; // rsi
  __int64 v14; // rax
  struct FrsStatus *v15; // rdi
  __int64 v16; // r10
  RefCountObject *v17; // rcx
  __int64 v18; // rdx
  FrsStatus *v19; // r15
  Meet *v20; // rcx
  struct FrsStatus *v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  struct MonitorContext *v25; // rdi
  struct MonitorContext *v26; // rcx
  int v27; // eax
  unsigned __int64 v28; // rdx
  __int64 v29; // r8
  struct Connection *v30; // r11
  unsigned int v31; // eax
  struct ID_RECORD *v32; // r9
  unsigned __int64 v33; // rcx
  struct ID_RECORD *v34; // rax
  unsigned int v35; // eax
  __int64 v36; // r10
  __int64 v37; // r9
  int v38; // eax
  unsigned int v39; // eax
  struct ShutdownObject *v40; // r15
  const struct ID_RECORD *v41; // r9
  InConnection *v42; // rdi
  const volatile int *v43; // rax
  unsigned int RemoteErrorCode; // eax
  InConnection *v45; // rdi
  const volatile int *v46; // rax
  struct FrsStatus *v47; // rax
  unsigned int v48; // eax
  unsigned int v49; // eax
  __int64 v50; // rax
  __int64 v51; // rax
  DWORD v52; // eax
  __int64 v53; // rcx
  struct FrsStatus *v54; // rdx
  struct FileId *v55; // rax
  struct FrsStatus *v56; // rdx
  Meet *v57; // rcx
  DWORD v58; // eax
  __int64 v59; // rcx
  __int64 v60; // rax
  __int64 v61; // r10
  __int64 v62; // r8
  const wchar_t *v63; // rax
  const unsigned __int16 *v64; // rdi
  __int64 v65; // rax
  const unsigned __int16 *v66; // rbx
  __int64 v67; // rax
  const unsigned __int16 *v68; // rax
  __int64 v69; // rdx
  const unsigned __int16 *v70; // r9
  const unsigned __int16 *v71; // r10
  const unsigned __int16 *v72; // r11
  __int64 v73; // rcx
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C8h]
  DWORD v76; // [rsp+40h] [rbp-C8h]
  const unsigned __int16 *v77; // [rsp+50h] [rbp-B8h]
  const wchar_t *v78; // [rsp+58h] [rbp-B0h] BYREF
  const wchar_t *v79; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v80; // [rsp+68h] [rbp-A0h]
  const wchar_t *v81; // [rsp+70h] [rbp-98h]
  __int64 v82; // [rsp+78h] [rbp-90h]
  struct FrsStatus *v83; // [rsp+80h] [rbp-88h] BYREF
  FrsStatus *ReplicaSetConfig; // [rsp+88h] [rbp-80h] BYREF
  struct FileId *v85; // [rsp+90h] [rbp-78h]
  struct Connection *Connection; // [rsp+98h] [rbp-70h]
  struct ShutdownObject *v87; // [rsp+A0h] [rbp-68h]
  struct StageReader **v88; // [rsp+A8h] [rbp-60h]
  struct FrsStatus *v89; // [rsp+B0h] [rbp-58h] BYREF
  struct Meet::RelatedToUpdate *v90; // [rsp+B8h] [rbp-50h]
  __int64 v91; // [rsp+C0h] [rbp-48h] BYREF
  struct FrsStatus *v92; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v93; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v94; // [rsp+D8h] [rbp-30h] BYREF
  const wchar_t *v95; // [rsp+E0h] [rbp-28h] BYREF
  int v96; // [rsp+E8h] [rbp-20h]
  int v97; // [rsp+ECh] [rbp-1Ch]
  const wchar_t *v98; // [rsp+F0h] [rbp-18h]
  struct ID_RECORD *v99; // [rsp+F8h] [rbp-10h]
  _QWORD v100[5]; // [rsp+108h] [rbp+0h] BYREF
  int v101; // [rsp+130h] [rbp+28h]
  int v102; // [rsp+134h] [rbp+2Ch]
  __int128 v103; // [rsp+138h] [rbp+30h]
  int v104; // [rsp+148h] [rbp+40h]
  __int64 v105; // [rsp+150h] [rbp+48h]
  _DWORD v106[4]; // [rsp+158h] [rbp+50h] BYREF
  struct FrsStatus *v107; // [rsp+168h] [rbp+60h]
  __int64 v108; // [rsp+170h] [rbp+68h]
  __int128 v109; // [rsp+178h] [rbp+70h] BYREF
  __int64 v110; // [rsp+188h] [rbp+80h]
  _BYTE v111[784]; // [rsp+198h] [rbp+90h] BYREF

  v78 = a4;
  v90 = a3;
  v87 = a2;
  v88 = a7;
  v85 = a8;
  v11 = *((_OWORD *)this + 4);
  v109 = v11;
  v12 = *((_QWORD *)this + 10);
  v110 = v12;
  v13 = 0;
  v89 = 0;
  LODWORD(v82) = *((_DWORD *)this + 207);
  v93 = 0;
  Connection = 0;
  v99 = 0;
  v92 = 0;
  v91 = 0;
  v14 = Config::ConfigInstance<Config::ContentSet>::Get(*((_QWORD *)this + 99) + 1120LL);
  ScopedRef<Config::ContentSet>::Set(&v91, v14);
  v100[0] = &InstallingWriter::`vftable';
  v100[1] = this;
  v100[2] = (char *)this + 40;
  v100[3] = a3;
  v100[4] = a8;
  v101 = a6;
  v102 = 0;
  v103 = 0;
  v104 = 0;
  v105 = 0;
  v15 = (struct FrsStatus *)operator new(0x2E8u);
  v83 = v15;
  *(_QWORD *)v15 = &DownloadWriter::`vftable';
  *((_QWORD *)v15 + 1) = 0;
  ID_UPDATE::ID_UPDATE((struct FrsStatus *)((char *)v15 + 16), (Meet *)((char *)this + 40));
  *((_QWORD *)v15 + 87) = a2;
  *((_QWORD *)v15 + 88) = 0;
  *((_QWORD *)v15 + 89) = v16;
  *((_QWORD *)v15 + 90) = 0;
  *((_QWORD *)v15 + 91) = v100;
  *((_DWORD *)v15 + 184) = 1;
  v17 = (RefCountObject *)*((_QWORD *)this + 128);
  if ( v17 )
  {
    RefCountObject::AddRef(v17);
    v18 = *((_QWORD *)this + 128);
  }
  else
  {
    v18 = 0;
  }
  ScopedRef<VolumeManager::ShutdownRestartTask>::Set((char *)v15 + 720, v18);
  v92 = v15;
  ReplicaSetConfig = (FrsStatus *)InConnection::GetReplicaSetConfig(*((_QWORD *)this + 98), &v93);
  CLEAR_ERROR(&ReplicaSetConfig);
  if ( v93 )
    Connection = Config::MemberList::FindConnection(
                   (Config::MemberList *)(v93 + 904),
                   (const struct _GUID *)(*((_QWORD *)this + 98) + 168LL),
                   0);
  *((_DWORD *)this + 48) &= ~4u;
  if ( a6 )
  {
    v19 = Staging::Delete(*((Staging **)this + 128), (Meet *)((char *)this + 40), (Meet *)((char *)this + 64));
    ReplicaSetConfig = v19;
  }
  else
  {
    v19 = ReplicaSetConfig;
    if ( !ReplicaSetConfig )
    {
      v19 = Staging::OpenForRead(*((Staging **)this + 128), (Meet *)((char *)this + 40), v88);
      ReplicaSetConfig = v19;
      if ( !v19 )
      {
        if ( !Meet::InstallOverwriteEnabled(v20, v90) )
        {
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            v95 = L"Meet::Download";
            v96 = 2031;
            v97 = 4;
            v98 = L"MEET";
            v89 = (struct FrsStatus *)(*(_QWORD *)(*((_QWORD *)this + 99) + 200LL) + 18LL);
            dbgobj::DbgPrint<unsigned short,unsigned short [261],UID,GVSN,_GUID,unsigned short const *>(
              (unsigned int)&v95,
              (unsigned int)L"File already staged - install it.  updateName:%ws uid:%? gvsn:%? connId:%? csName:%?",
              (_DWORD)this + 196,
              (_DWORD)this + 40,
              (__int64)this + 64,
              *((_QWORD *)this + 98) + 168LL,
              (__int64)&v89);
          }
          v21 = Meet::TransferToInstalling(this, *v88, v87, v85);
          if ( v21 )
          {
            CurrentThreadId = GetCurrentThreadId();
            v23 = FrsStatusList::PushNewError(
                    v22,
                    *((unsigned int *)v21 + 1),
                    *((unsigned int *)v21 + 2),
                    *(unsigned int *)v21,
                    "base\\fs\\remotefs\\frs\\src\\sync\\meet.cpp",
                    "Meet::Download",
                    2034,
                    CurrentThreadId,
                    v21);
LABEL_143:
            v13 = v23;
            goto LABEL_144;
          }
        }
        goto LABEL_144;
      }
    }
    if ( *((_DWORD *)v19 + 1) == 2 )
    {
      CLEAR_ERROR(&ReplicaSetConfig);
      v19 = 0;
      ReplicaSetConfig = 0;
    }
  }
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v95 = L"Meet::Download";
    v96 = 2055;
    v97 = 5;
    v98 = L"MEET";
    v24 = *((_QWORD *)this + 99);
    v94 = *(_QWORD *)(v24 + 200) + 18LL;
    dbgobj::DbgPrint<unsigned short,unsigned short [261],UID,GVSN,_GUID,unsigned short const *,_GUID>(
      (unsigned int)&v95,
      (unsigned int)L"Start Download updateName:%ws uid:%? gvsn:%? connId:%? csName:%? csId:%?",
      (_DWORD)this + 196,
      (_DWORD)this + 40,
      (__int64)this + 64,
      *((_QWORD *)this + 98) + 168LL,
      (__int64)&v94,
      v24 + 168);
  }
  if ( v19 )
    goto LABEL_102;
  if ( *((_QWORD *)this + 123) )
  {
    v25 = g_MonitorContext;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_MonitorContext + 808));
    *((_DWORD *)v25 + 200) = 1;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v79 = L"Meet::Download";
      v80 = 0x50000080FLL;
      v81 = L"MEET";
      dbgobj::DbgPrint<unsigned short>(&v79, L"Update idUpdateInfoHistory");
    }
    *(_DWORD *)(*((_QWORD *)this + 123) + 72LL) = 3;
    IdUpdateInfoHistoryProcessor::Update(
      (struct MonitorContext *)((char *)g_MonitorContext + 744),
      *((struct HistoryRecord **)this + 123));
    v26 = g_MonitorContext;
    *((_DWORD *)g_MonitorContext + 200) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v26 + 808));
    v15 = v83;
  }
  if ( (_DWORD)v82 )
  {
    if ( !Connection
      || (v27 = Config::BoolParam::Get((struct Connection *)((char *)Connection + 720)), LODWORD(v82) = 1, v27 != 1) )
    {
      LODWORD(v82) = 0;
    }
  }
  (*(void (__fastcall **)(struct FrsStatus *))(*(_QWORD *)v15 + 64LL))(v15);
  v29 = (unsigned int)v82;
  v30 = Connection;
  if ( !(_DWORD)v82 )
    goto LABEL_44;
  if ( *((_DWORD *)v78 + 182) )
  {
    v31 = Config::BoolParam::Get((struct Connection *)((char *)Connection + 760));
    v28 = *((_QWORD *)v32 + 90) >> 10;
    v33 = v31;
    v34 = 0;
    if ( v28 >= v33 )
      v34 = v32;
    v99 = v34;
  }
  if ( *((_DWORD *)v90 + 182) && (*((_BYTE *)v90 + 152) & 1) != 0 )
  {
    v35 = Config::BoolParam::Get((struct Connection *)((char *)v30 + 760));
    v28 = *(_QWORD *)(v36 + 720) >> 10;
    v37 = 0;
    if ( v28 >= v35 )
      v37 = v36;
  }
  else
  {
LABEL_44:
    v37 = 0;
  }
  v38 = *((_DWORD *)this + 194);
  if ( v38 == 1 || v38 == 2 )
  {
    *((_OWORD *)this + 4) = 0;
    *((_QWORD *)this + 10) = 0;
  }
  if ( (_DWORD)v29 )
  {
    v106[0] = 0;
    v107 = v15;
    v108 = 0;
    v39 = Config::BoolParam::Get((struct Connection *)((char *)v30 + 760));
    v40 = v87;
    Rdc::SeedFile::SeedFile((Rdc::SeedFile *)v111, v87, a5, *((struct ContentSetManager **)this + 99), v39, v99, v41);
    v42 = (InConnection *)*((_QWORD *)this + 98);
    v43 = (const volatile int *)(*(__int64 (__fastcall **)(struct ShutdownObject *))(*(_QWORD *)v40 + 40LL))(v40);
    v19 = InConnection::TransportRdcGet(
            v42,
            (Meet *)((char *)this + 836),
            v43,
            (struct Rdc::SeedFile *)v111,
            (struct Rdc::TargetFile *)v106,
            (Meet *)((char *)this + 40));
    ReplicaSetConfig = v19;
    Rdc::SeedFile::~SeedFile((Rdc::SeedFile *)v111);
    v15 = v83;
    v29 = (unsigned int)v82;
  }
  RemoteErrorCode = 0;
  if ( v19 )
  {
    RemoteErrorCode = *((_DWORD *)v19 + 1);
    if ( RemoteErrorCode == 9027 )
      RemoteErrorCode = FrsStatus::GetRemoteErrorCode(v19);
  }
  if ( !(_DWORD)v29 )
    goto LABEL_56;
  if ( !v19 )
  {
LABEL_58:
    if ( *((_DWORD *)this + 194) == 1 && !(unsigned __int8)GVSN::operator==((char *)this + 64, &v109, v29) )
    {
      *((_DWORD *)this + 8) = 3;
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v79 = L"Meet::Download";
        v80 = 0x400000861LL;
        v81 = L"MEET";
        v78 = L"SlowSync";
        dbgobj::DbgPrint<unsigned short,unsigned short const *>(
          &v79,
          L"-> DONE File has changed since %s detected mismatch.",
          &v78);
      }
LABEL_64:
      v47 = DownloadWriter::AbortDownload(v83);
LABEL_127:
      v19 = v47;
      goto LABEL_128;
    }
    goto LABEL_86;
  }
  if ( RemoteErrorCode == 9035 )
  {
LABEL_56:
    CLEAR_ERROR(&ReplicaSetConfig);
    (*(void (__fastcall **)(struct FrsStatus *, _QWORD))(*(_QWORD *)v15 + 64LL))(v15, 0);
    v45 = (InConnection *)*((_QWORD *)this + 98);
    v46 = (const volatile int *)(*(__int64 (__fastcall **)(struct ShutdownObject *))(*(_QWORD *)v87 + 40LL))(v87);
    v19 = InConnection::TransportRawGet(
            v45,
            *((struct ContentSetManager **)this + 99),
            (Meet *)((char *)this + 836),
            v83,
            v46,
            (Meet *)((char *)this + 40));
    ReplicaSetConfig = v19;
  }
  if ( !v19 )
    goto LABEL_58;
  if ( *((_DWORD *)v19 + 1) == 9027 )
  {
    v48 = FrsStatus::GetRemoteErrorCode(v19) - 9029;
    if ( !v48 )
    {
      *((_DWORD *)this + 8) = 3;
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v79 = L"Meet::Download";
        v80 = 0x40000086DLL;
        v81 = L"MEET";
        v51 = *((_QWORD *)this + 99);
        v78 = (const wchar_t *)(*(_QWORD *)(v51 + 200) + 18LL);
        dbgobj::DbgPrint<unsigned short,unsigned short [261],UID,GVSN,_GUID,unsigned short const *,_GUID>(
          (unsigned int)&v79,
          (unsigned int)L"-> DONE File contents have changed since update was sent updateName:%ws uid:%? gvsn:%? connId:%?"
                         " csName:%? csId:%?",
          (_DWORD)this + 196,
          (_DWORD)this + 40,
          (__int64)this + 64,
          *((_QWORD *)this + 98) + 168LL,
          (__int64)&v78,
          v51 + 168);
      }
      CLEAR_ERROR(&ReplicaSetConfig);
      goto LABEL_64;
    }
    v49 = v48 - 30;
    if ( v49 )
    {
      if ( v49 == 19 )
        *((_DWORD *)this + 215) = 1;
      else
        Meet::ProcessSharingViolation(this, v19, (const unsigned __int16 *)this + 98, 0);
    }
    else if ( *((_DWORD *)this + 194) == 2 )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v79 = L"Meet::Download";
        v80 = 0x400000879LL;
        v81 = L"MEET";
        v50 = *((_QWORD *)this + 99);
        v78 = (const wchar_t *)(*(_QWORD *)(v50 + 200) + 18LL);
        dbgobj::DbgPrint<unsigned short,unsigned short [261],UID,GVSN,_GUID,unsigned short const *,_GUID>(
          (unsigned int)&v79,
          (unsigned int)L"Update does not exist on upstream. Tombstone local content. updateName:%ws uid:%? gvsn:%? connId"
                         ":%? csName:%? csId:%?",
          (_DWORD)this + 196,
          (_DWORD)this + 40,
          (__int64)this + 64,
          *((_QWORD *)this + 98) + 168LL,
          (__int64)&v78,
          v50 + 168);
      }
      *((_DWORD *)this + 48) &= ~1u;
      *((_OWORD *)this + 4) = v11;
      *((_QWORD *)this + 10) = v12;
      CLEAR_ERROR(&ReplicaSetConfig);
      v19 = ReplicaSetConfig;
    }
  }
  else if ( *((_DWORD *)v19 + 1) == 112 )
  {
    ContentSetManager::ReportDiskFull(*((ContentSetManager **)this + 99), ((v102 - 1) & 0xFFFFFFFD) != 0);
  }
  if ( v19 )
  {
LABEL_101:
    v15 = v83;
LABEL_102:
    v54 = DownloadWriter::AbortDownload(v15);
    v83 = v54;
    if ( v54 )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        v79 = L"Meet::Download";
        v80 = 0x5000008C1LL;
        v81 = L"MEET";
        v78 = (const wchar_t *)(*(_QWORD *)(*((_QWORD *)this + 99) + 200LL) + 18LL);
        dbgobj::DbgPrint<unsigned short,unsigned short [261],UID,GVSN,_GUID,unsigned short const *,FrsStatus>(
          (unsigned int)&v79,
          (unsigned int)L"(Ignored) Failed to abort download.  updateName:%ws uid:%? gvsn:%? connId:%? csName:%? Error:%?",
          (_DWORD)this + 196,
          (_DWORD)this + 40,
          (__int64)this + 64,
          *((_QWORD *)this + 98) + 168LL,
          (__int64)&v78,
          (__int64)v54);
      }
      CLEAR_ERROR(&v83);
    }
    v55 = v85;
    if ( *(_QWORD *)v85 )
    {
      v56 = NtfsFileSystem::Delete(
              (NtfsFileSystem *)Meet::fs,
              (const struct VolumeId *)(*((_QWORD *)this + 99) + 208LL),
              v85,
              0);
      v83 = v56;
      if ( v56 )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v79 = L"Meet::Download";
          v80 = 0x5000008CBLL;
          v81 = L"MEET";
          v78 = (const wchar_t *)(*(_QWORD *)(*((_QWORD *)this + 99) + 200LL) + 18LL);
          dbgobj::DbgPrint<unsigned short,unsigned short [261],UID,GVSN,_GUID,unsigned short const *,FrsStatus>(
            (unsigned int)&v79,
            (unsigned int)L"(Ignored) Failed to delete.  updateName:%ws uid:%? gvsn:%? connId:%? csName:%? Error:%?",
            (_DWORD)this + 196,
            (_DWORD)this + 40,
            (__int64)this + 64,
            *((_QWORD *)this + 98) + 168LL,
            (__int64)&v78,
            (__int64)v56);
        }
        CLEAR_ERROR(&v83);
      }
      v55 = v85;
    }
    *(_QWORD *)v55 = 0;
    goto LABEL_128;
  }
LABEL_86:
  if ( (*((_BYTE *)this + 192) & 1) == 0 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v79 = L"Meet::Download";
      v80 = 0x50000089FLL;
      v81 = L"MEET";
      v78 = (const wchar_t *)(*(_QWORD *)(*((_QWORD *)this + 99) + 200LL) + 18LL);
      dbgobj::DbgPrint<unsigned short,unsigned short [261],UID,GVSN,_GUID,unsigned short const *>(
        (unsigned int)&v79,
        (unsigned int)L"Aborting staging tombstoned update updateName:%ws uid:%? gvsn:%? connId:%? csName:%?",
        (_DWORD)this + 196,
        (_DWORD)this + 40,
        (__int64)this + 64,
        *((_QWORD *)this + 98) + 168LL,
        (__int64)&v78);
    }
    goto LABEL_64;
  }
  if ( (*(unsigned __int8 (__fastcall **)(struct ShutdownObject *, unsigned __int64, __int64, __int64))(*(_QWORD *)v87 + 48LL))(
         v87,
         v28,
         v29,
         v37) )
  {
    v52 = GetCurrentThreadId();
    v19 = (FrsStatus *)FrsStatusList::PushNewError(
                         v53,
                         9032,
                         0,
                         3,
                         "base\\fs\\remotefs\\frs\\src\\sync\\meet.cpp",
                         "Meet::Download",
                         2214,
                         v52,
                         0);
    if ( v19 )
      goto LABEL_101;
  }
  if ( ((v102 - 1) & 0xFFFFFFFD) == 0 )
  {
    v47 = DownloadWriter::CompleteDownloadInstall(v83);
    goto LABEL_127;
  }
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v79 = L"Meet::Download";
    v80 = 0x5000008B0LL;
    v81 = L"MEET";
    v78 = (const wchar_t *)(*(_QWORD *)(*((_QWORD *)this + 99) + 200LL) + 18LL);
    dbgobj::DbgPrint<unsigned short,unsigned short [261],UID,GVSN,_GUID,unsigned short const *>(
      (unsigned int)&v79,
      (unsigned int)L"Done downloading content updateName:%ws uid:%? gvsn:%? connId:%? csName:%?",
      (_DWORD)this + 196,
      (_DWORD)this + 40,
      (__int64)this + 64,
      *((_QWORD *)this + 98) + 168LL,
      (__int64)&v78);
  }
  v15 = v83;
  v19 = DownloadWriter::CompleteDownloadStage(v83, v88, &v89, (Meet *)((char *)this + 64));
  if ( v19 )
    goto LABEL_102;
  close_delete::close<DbIterator<ID_RECORD>>(v15);
  v92 = 0;
  v19 = v89;
  if ( !v89 && !Meet::InstallOverwriteEnabled(v57, v90) && !a6 )
  {
    if ( *v88 )
    {
      v47 = Meet::TransferToInstalling(this, *v88, v87, v85);
    }
    else
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
      {
        v79 = L"Meet::Download";
        v80 = 0x3000008DFLL;
        v81 = L"MEET";
        dbgobj::DbgPrint<unsigned short>(&v79, L"Download succeeded with empty file");
      }
      v58 = GetCurrentThreadId();
      v47 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                  v59,
                                  9026,
                                  0,
                                  3,
                                  "base\\fs\\remotefs\\frs\\src\\sync\\meet.cpp",
                                  "Meet::Download",
                                  2272,
                                  v58,
                                  0);
    }
    goto LABEL_127;
  }
LABEL_128:
  if ( *((_DWORD *)this + 194) == 1 )
  {
    *((_OWORD *)this + 4) = v11;
    *((_QWORD *)this + 10) = v12;
  }
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v79 = L"Meet::Download";
    v80 = 0x4000008EELL;
    v81 = L"MEET";
    v60 = *((_QWORD *)this + 99);
    v61 = v60 + 168;
    v78 = (const wchar_t *)(*(_QWORD *)(v60 + 200) + 18LL);
    v62 = *((_QWORD *)this + 98) + 168LL;
    v63 = L"false";
    if ( !v19 )
      v63 = L"true";
    v94 = (__int64)v63;
    dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short [261],UID,GVSN,_GUID,unsigned short const *,_GUID>(
      (unsigned int)&v79,
      (_DWORD)this + 40,
      (unsigned int)&v94,
      (_DWORD)this + 196,
      (__int64)this + 40,
      (__int64)this + 64,
      v62,
      (__int64)&v78,
      v61);
  }
  if ( Connection )
    v64 = Config::StringParam::Get((struct Connection *)((char *)Connection + 480));
  else
    v64 = 0;
  v65 = GVSN::ToString((char *)this + 88, &v109);
  v66 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v65);
  v67 = GVSN::ToString((char *)this + 40, v106);
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v67);
  v68 = Config::StringParam::Get((Config::StringParam *)(v91 + 240));
  FrsEvent::Audit(
    v19 == 0,
    0x40001B5Cu,
    (const unsigned __int16 *)(*(_QWORD *)(v69 + 616) + 18LL),
    v68,
    v70,
    v72,
    v71,
    v66,
    v64,
    v77);
  std::wstring::~wstring(v106);
  std::wstring::~wstring(&v109);
  if ( v19 )
  {
    if ( *((_DWORD *)v19 + 1) == 9048 )
    {
      *(_QWORD *)v85 = 0;
      *((_DWORD *)this + 208) = 1;
      *((_DWORD *)this + 209) = 2;
      *((_DWORD *)this + 207) = 0;
    }
    v76 = GetCurrentThreadId();
    v23 = FrsStatusList::PushNewError(
            v73,
            *((unsigned int *)v19 + 1),
            *((unsigned int *)v19 + 2),
            *(unsigned int *)v19,
            "base\\fs\\remotefs\\frs\\src\\sync\\meet.cpp",
            "Meet::Download",
            2306,
            v76,
            v19);
    goto LABEL_143;
  }
LABEL_144:
  InstallingWriter::~InstallingWriter((InstallingWriter *)v100);
  ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v91);
  scoped_any<Rdc::RDCIndexReader *,close_delete,null_t,0>::~scoped_any<Rdc::RDCIndexReader *,close_delete,null_t,0>(&v92);
  ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v93);
  return (struct FrsStatus *)v13;
}

```

## disassembly

```asm
0x14017e2e8  mov     rax, rsp
0x14017e2eb  push    rbp
0x14017e2ec  push    rbx
0x14017e2ed  push    rsi
0x14017e2ee  push    rdi
0x14017e2ef  push    r12
0x14017e2f1  push    r13
0x14017e2f3  push    r14
0x14017e2f5  push    r15
0x14017e2f7  lea     rbp, [rax-408h]
0x14017e2fe  sub     rsp, 4C8h
0x14017e305  movaps  xmmword ptr [rax-58h], xmm6
0x14017e309  mov     rax, cs:__security_cookie
0x14017e310  xor     rax, rsp
0x14017e313  mov     [rbp+400h+var_60], rax
0x14017e31a  mov     [rsp+500h+var_4B0], r9
0x14017e31f  mov     rdi, r8
0x14017e322  mov     [rbp+400h+var_450], r8
0x14017e326  mov     r15, rdx
0x14017e329  mov     [rbp+400h+var_468], rdx
0x14017e32d  mov     r14, rcx
0x14017e330  mov     rax, [rbp+400h+arg_30]
0x14017e337  mov     [rbp+400h+var_460], rax
0x14017e33b  mov     rax, [rbp+400h+arg_38]
0x14017e342  mov     [rbp+400h+var_478], rax
0x14017e346  movups  xmm6, xmmword ptr [rcx+40h]
0x14017e34a  movups  [rbp+400h+var_390], xmm6
0x14017e34e  mov     rbx, [rcx+50h]
0x14017e352  mov     [rbp+400h+var_380], rbx
0x14017e359  xor     esi, esi
0x14017e35b  mov     [rbp+400h+var_458], rsi
0x14017e35f  mov     eax, [rcx+33Ch]
0x14017e365  mov     dword ptr [rsp+500h+var_490], eax
0x14017e369  mov     [rbp+400h+var_438], rsi
0x14017e36d  mov     [rbp+400h+var_470], rsi
0x14017e371  mov     [rbp+400h+var_410], rsi
0x14017e375  mov     [rbp+400h+var_440], rsi
0x14017e379  mov     [rbp+400h+var_448], rsi
0x14017e37d  mov     rcx, [rcx+318h]
0x14017e384  add     rcx, 460h
0x14017e38b  call    ?Get@?$ConfigInstance@VContentSet@Config@@@Config@@QEAAPEAVContentSet@2@XZ; Config::ConfigInstance<Config::ContentSet>::Get(void)
0x14017e390  mov     rdx, rax
0x14017e393  lea     rcx, [rbp+400h+var_448]
0x14017e397  call    ?Set@?$ScopedRef@VContentSet@Config@@@@AEAAXPEAVContentSet@Config@@@Z; ScopedRef<Config::ContentSet>::Set(Config::ContentSet *)
0x14017e39c  lea     rax, ??_7InstallingWriter@@6B@; const InstallingWriter::`vftable'
0x14017e3a3  mov     [rbp+400h+var_400], rax
0x14017e3a7  mov     [rbp+400h+var_3F8], r14
0x14017e3ab  lea     r12, [r14+28h]
0x14017e3af  mov     [rbp+400h+var_3F0], r12
0x14017e3b3  mov     [rbp+400h+var_3E8], rdi
0x14017e3b7  mov     rax, [rbp+400h+var_478]
0x14017e3bb  mov     [rbp+400h+var_3E0], rax
0x14017e3bf  mov     eax, [rbp+400h+arg_28]
0x14017e3c5  mov     [rbp+400h+var_3D8], eax
0x14017e3c8  mov     [rbp+400h+var_3D4], esi
0x14017e3cb  xorps   xmm0, xmm0
0x14017e3ce  movdqa  [rbp+400h+var_3D0], xmm0
0x14017e3d3  mov     [rbp+400h+var_3C0], esi
0x14017e3d6  mov     [rbp+400h+var_3B8], rsi
0x14017e3da  mov     ecx, 2E8h; Size
0x14017e3df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14017e3e4  mov     rdi, rax
0x14017e3e7  mov     [rsp+500h+var_488], rax
0x14017e3ec  mov     r10, [r14+318h]
0x14017e3f3  lea     rax, ??_7DownloadWriter@@6B@; const DownloadWriter::`vftable'
0x14017e3fa  mov     [rdi], rax
0x14017e3fd  mov     [rdi+8], rsi
0x14017e401  lea     rcx, [rdi+10h]; this
0x14017e405  mov     rdx, r12; struct ID_UPDATE *
0x14017e408  call    ??0ID_UPDATE@@QEAA@AEBV0@@Z; ID_UPDATE::ID_UPDATE(ID_UPDATE const &)
0x14017e40d  mov     [rdi+2B8h], r15
0x14017e414  mov     [rdi+2C0h], rsi
0x14017e41b  mov     [rdi+2C8h], r10
0x14017e422  lea     r15, [rdi+2D0h]
0x14017e429  mov     [r15], rsi
0x14017e42c  lea     rax, [rbp+400h+var_400]
0x14017e430  mov     [rdi+2D8h], rax
0x14017e437  mov     dword ptr [rdi+2E0h], 1
0x14017e441  mov     rcx, [r14+400h]; this
0x14017e448  test    rcx, rcx
0x14017e44b  jnz     short loc_14017E451
0x14017e44d  xor     edx, edx
0x14017e44f  jmp     short loc_14017E45D
0x14017e451  call    ?AddRef@RefCountObject@@QEAAJXZ; RefCountObject::AddRef(void)
0x14017e456  mov     rdx, [r14+400h]
0x14017e45d  mov     rcx, r15
0x14017e460  call    ?Set@?$ScopedRef@VShutdownRestartTask@VolumeManager@@@@AEAAXPEAVShutdownRestartTask@VolumeManager@@@Z; ScopedRef<VolumeManager::ShutdownRestartTask>::Set(VolumeManager::ShutdownRestartTask *)
0x14017e465  nop
0x14017e466  mov     [rbp+400h+var_440], rdi
0x14017e46a  lea     rdx, [rbp+400h+var_438]
0x14017e46e  mov     rcx, [r14+310h]
0x14017e475  call    ?GetReplicaSetConfig@InConnection@@QEAAPEAVFrsStatus@@AEAV?$ScopedRef@VReplicaSet@Config@@@@@Z; InConnection::GetReplicaSetConfig(ScopedRef<Config::ReplicaSet> &)
0x14017e47a  mov     [rbp+400h+var_480], rax
0x14017e47e  lea     rcx, [rbp+400h+var_480]; struct FrsStatus **
0x14017e482  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x14017e487  mov     rax, [rbp+400h+var_438]
0x14017e48b  test    rax, rax
0x14017e48e  jz      short loc_14017E4B1
0x14017e490  lea     rcx, [rax+388h]; this
0x14017e497  mov     rdx, [r14+310h]
0x14017e49e  add     rdx, 0A8h; struct _GUID *
0x14017e4a5  xor     r8d, r8d; struct Member **
0x14017e4a8  call    ?FindConnection@MemberList@Config@@QEBAPEAVConnection@2@PEBU_GUID@@PEAPEAVMember@2@@Z; Config::MemberList::FindConnection(_GUID const *,Config::Member * *)
0x14017e4ad  mov     [rbp+400h+var_470], rax
0x14017e4b1  and     dword ptr [r14+0C0h], 0FFFFFFFBh
0x14017e4b9  cmp     [rbp+400h+arg_28], esi
0x14017e4bf  jnz     loc_14017E602
0x14017e4c5  mov     r15, [rbp+400h+var_480]
0x14017e4c9  test    r15, r15
0x14017e4cc  jnz     loc_14017E5E9
0x14017e4d2  mov     r8, [rbp+400h+var_460]; struct StageReader **
0x14017e4d6  mov     rdx, r12; struct ID_UPDATE *
0x14017e4d9  mov     rcx, [r14+400h]; this
0x14017e4e0  call    ?OpenForRead@Staging@@QEAAPEAVFrsStatus@@AEBVID_UPDATE@@AEAPEAVStageReader@@@Z; Staging::OpenForRead(ID_UPDATE const &,StageReader * &)
0x14017e4e5  mov     r15, rax
0x14017e4e8  mov     [rbp+400h+var_480], rax
0x14017e4ec  test    rax, rax
0x14017e4ef  jnz     loc_14017E5E9
0x14017e4f5  mov     rdx, [rbp+400h+var_450]; struct Meet::RelatedToUpdate *
0x14017e4f9  call    ?InstallOverwriteEnabled@Meet@@AEAAHAEBVRelatedToUpdate@1@@Z; Meet::InstallOverwriteEnabled(Meet::RelatedToUpdate const &)
0x14017e4fe  test    eax, eax
0x14017e500  jnz     loc_14017F2B6
0x14017e506  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14017e50d  test    rax, rax
0x14017e510  jz      loc_14017E59A
0x14017e516  cmp     [rax+40h], esi
0x14017e519  jz      short loc_14017E59A
0x14017e51b  cmp     dword ptr [rax+38h], 4
0x14017e51f  jl      short loc_14017E59A
0x14017e521  lea     r12, aMeetDownload; "Meet::Download"
0x14017e528  mov     [rbp+400h+var_428], r12
0x14017e52c  mov     [rbp+400h+var_420], 7EFh
0x14017e533  mov     [rbp+400h+var_41C], 4
0x14017e53a  lea     r13, aMeet; "MEET"
0x14017e541  mov     [rbp+400h+var_418], r13
0x14017e545  mov     rax, [r14+318h]
0x14017e54c  mov     rcx, [rax+0C8h]
0x14017e553  add     rcx, 12h
0x14017e557  mov     [rbp+400h+var_458], rcx
0x14017e55b  mov     rax, [r14+310h]
0x14017e562  add     rax, 0A8h
0x14017e568  lea     r8, [r14+0C4h]
0x14017e56f  lea     rcx, [rbp+400h+var_458]
0x14017e573  mov     [rsp+500h+var_4D0], rcx
0x14017e578  mov     [rsp+500h+var_4D8], rax
0x14017e57d  lea     rax, [r14+40h]
0x14017e581  mov     [rsp+500h+var_4E0], rax
0x14017e586  lea     r9, [r14+28h]
0x14017e58a  lea     rdx, aFileAlreadySta; "File already staged - install it.  upda"...
0x14017e591  lea     rcx, [rbp+400h+var_428]
0x14017e595  call    ??$DbgPrint@G$$BY0BAF@GVUID@@VGVSN@@U_GUID@@PEBG@dbgobj@@QEAA_KPEBGAEAY0BAF@$$CBGAEBVUID@@AEBVGVSN@@AEBU_GUID@@AEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort [261],UID,GVSN,_GUID,ushort const *>(ushort const *,ushort const (&)[261],UID const &,GVSN const &,_GUID const &,ushort const * const &)
0x14017e59a  mov     r9, [rbp+400h+var_478]; struct FileId *
0x14017e59e  mov     r8, [rbp+400h+var_468]; struct ShutdownObject *
0x14017e5a2  mov     rax, [rbp+400h+var_460]
0x14017e5a6  mov     rdx, [rax]; struct StageReader *
0x14017e5a9  mov     rcx, r14; this
0x14017e5ac  call    ?TransferToInstalling@Meet@@AEAAPEAVFrsStatus@@PEAVStageReader@@AEAVShutdownObject@@AEAVFileId@@@Z; Meet::TransferToInstalling(StageReader *,ShutdownObject &,FileId &)
0x14017e5b1  mov     rbx, rax
0x14017e5b4  test    rax, rax
0x14017e5b7  jz      loc_14017F2B6
0x14017e5bd  call    cs:__imp_GetCurrentThreadId
0x14017e5c4  nop     dword ptr [rax+rax+00h]
0x14017e5c9  mov     qword ptr [rsp+500h+var_4C8+8], rbx
0x14017e5ce  mov     [rsp+500h+var_4C8], eax
0x14017e5d2  mov     dword ptr [rsp+500h+var_4D0], 7F2h
0x14017e5da  mov     r9d, [rbx]
0x14017e5dd  mov     r8d, [rbx+8]
0x14017e5e1  mov     edx, [rbx+4]
0x14017e5e4  jmp     loc_14017F296
0x14017e5e9  cmp     dword ptr [r15+4], 2
0x14017e5ee  jnz     short loc_14017E61C
0x14017e5f0  lea     rcx, [rbp+400h+var_480]; struct FrsStatus **
0x14017e5f4  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x14017e5f9  mov     r15, rsi
0x14017e5fc  mov     [rbp+400h+var_480], rsi
0x14017e600  jmp     short loc_14017E61C
0x14017e602  lea     r8, [r14+40h]; struct GVSN *
0x14017e606  mov     rdx, r12; struct UID *
0x14017e609  mov     rcx, [r14+400h]; this
0x14017e610  call    ?Delete@Staging@@QEAAPEAVFrsStatus@@AEBVUID@@AEBVGVSN@@@Z; Staging::Delete(UID const &,GVSN const &)
0x14017e615  mov     r15, rax
0x14017e618  mov     [rbp+400h+var_480], rax
0x14017e61c  lea     r12, aMeetDownload; "Meet::Download"
0x14017e623  lea     r13, aMeet; "MEET"
0x14017e62a  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14017e631  test    rax, rax
0x14017e634  jz      loc_14017E6BC
0x14017e63a  cmp     [rax+40h], esi
0x14017e63d  jz      short loc_14017E6BC
0x14017e63f  cmp     dword ptr [rax+38h], 5
0x14017e643  jl      short loc_14017E6BC
0x14017e645  mov     [rbp+400h+var_428], r12
0x14017e649  mov     [rbp+400h+var_420], 807h
0x14017e650  mov     [rbp+400h+var_41C], 5
0x14017e657  mov     [rbp+400h+var_418], r13
0x14017e65b  mov     rax, [r14+318h]
0x14017e662  lea     rdx, [rax+0A8h]
0x14017e669  mov     rcx, [rax+0C8h]
0x14017e670  add     rcx, 12h
0x14017e674  mov     [rbp+400h+var_430], rcx
0x14017e678  mov     rax, [r14+310h]
0x14017e67f  add     rax, 0A8h
0x14017e685  lea     r8, [r14+0C4h]
0x14017e68c  mov     qword ptr [rsp+500h+var_4C8], rdx
0x14017e691  lea     rcx, [rbp+400h+var_430]
0x14017e695  mov     [rsp+500h+var_4D0], rcx
0x14017e69a  mov     [rsp+500h+var_4D8], rax
0x14017e69f  lea     rax, [r14+40h]
0x14017e6a3  mov     [rsp+500h+var_4E0], rax
0x14017e6a8  lea     r9, [r14+28h]
0x14017e6ac  lea     rdx, aStartDownloadU; "Start Download updateName:%ws uid:%? gv"...
0x14017e6b3  lea     rcx, [rbp+400h+var_428]
0x14017e6b7  call    ??$DbgPrint@G$$BY0BAF@GVUID@@VGVSN@@U_GUID@@PEBGU3@@dbgobj@@QEAA_KPEBGAEAY0BAF@$$CBGAEBVUID@@AEBVGVSN@@AEBU_GUID@@AEBQEBG4@Z; dbgobj::DbgPrint<ushort,ushort [261],UID,GVSN,_GUID,ushort const *,_GUID>(ushort const *,ushort const (&)[261],UID const &,GVSN const &,_GUID const &,ushort const * const &,_GUID const &)
0x14017e6bc  test    r15, r15
0x14017e6bf  jnz     loc_14017EE27
0x14017e6c5  cmp     [r14+3D8h], rsi
0x14017e6cc  jz      loc_14017E785
0x14017e6d2  mov     rdi, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x14017e6d9  lea     rcx, [rdi+328h]; lpCriticalSection
0x14017e6e0  call    cs:__imp_EnterCriticalSection
0x14017e6e7  nop     dword ptr [rax+rax+00h]
0x14017e6ec  mov     dword ptr [rdi+320h], 1
0x14017e6f6  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14017e6fd  test    rax, rax
0x14017e700  jz      short loc_14017E738
0x14017e702  cmp     [rax+40h], esi
0x14017e705  jz      short loc_14017E738
0x14017e707  cmp     dword ptr [rax+38h], 5
0x14017e70b  jl      short loc_14017E738
0x14017e70d  mov     qword ptr [rsp+500h+var_4A8], r12
0x14017e712  mov     dword ptr [rsp+500h+var_4A0], 80Fh
0x14017e71a  mov     dword ptr [rsp+500h+var_4A0+4], 5
0x14017e722  mov     [rsp+500h+var_498], r13
0x14017e727  lea     rdx, aUpdateIdupdate; "Update idUpdateInfoHistory"
0x14017e72e  lea     rcx, [rsp+500h+var_4A8]
0x14017e733  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x14017e738  mov     rax, [r14+3D8h]
0x14017e73f  mov     dword ptr [rax+48h], 3
0x14017e746  mov     rcx, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x14017e74d  add     rcx, 2E8h; this
0x14017e754  mov     rdx, [r14+3D8h]; struct HistoryRecord *
0x14017e75b  call    ?Update@IdUpdateInfoHistoryProcessor@@MEAAXPEAVHistoryRecord@@@Z; IdUpdateInfoHistoryProcessor::Update(HistoryRecord *)
0x14017e760  mov     rcx, cs:?g_MonitorContext@@3PEAVMonitorContext@@EA; MonitorContext * g_MonitorContext
0x14017e767  mov     [rcx+320h], esi
0x14017e76d  add     rcx, 328h; lpCriticalSection
0x14017e774  call    cs:__imp_LeaveCriticalSection
0x14017e77b  nop     dword ptr [rax+rax+00h]
0x14017e780  mov     rdi, [rsp+500h+var_488]
0x14017e785  mov     edx, dword ptr [rsp+500h+var_490]
0x14017e789  test    edx, edx
0x14017e78b  jz      short loc_14017E7B7
0x14017e78d  mov     rax, [rbp+400h+var_470]
0x14017e791  test    rax, rax
0x14017e794  jz      short loc_14017E7AF
0x14017e796  lea     rcx, [rax+2D0h]; this
0x14017e79d  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x14017e7a2  cmp     eax, 1
0x14017e7a5  mov     dword ptr [rsp+500h+var_490], 1
0x14017e7ad  jz      short loc_14017E7B3
0x14017e7af  mov     dword ptr [rsp+500h+var_490], esi
0x14017e7b3  mov     edx, dword ptr [rsp+500h+var_490]
0x14017e7b7  mov     rax, [rdi]
0x14017e7ba  mov     rcx, rdi
0x14017e7bd  mov     rax, [rax+40h]
0x14017e7c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14017e7c6  mov     r8d, dword ptr [rsp+500h+var_490]
0x14017e7cb  mov     r11, [rbp+400h+var_470]
0x14017e7cf  test    r8d, r8d
0x14017e7d2  jz      short loc_14017E845
0x14017e7d4  mov     r9, [rsp+500h+var_4B0]
0x14017e7d9  cmp     [r9+2D8h], esi
0x14017e7e0  jz      short loc_14017E809
0x14017e7e2  lea     rcx, [r11+2F8h]; this
0x14017e7e9  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x14017e7ee  mov     rdx, [r9+2D0h]
0x14017e7f5  shr     rdx, 0Ah
0x14017e7f9  mov     ecx, eax
0x14017e7fb  mov     rax, rsi
0x14017e7fe  cmp     rdx, rcx
0x14017e801  cmovnb  rax, r9
0x14017e805  mov     [rbp+400h+var_410], rax
0x14017e809  mov     r10, [rbp+400h+var_450]
0x14017e80d  cmp     [r10+2D8h], esi
0x14017e814  jz      short loc_14017E845
0x14017e816  test    byte ptr [r10+98h], 1
0x14017e81e  jz      short loc_14017E845
0x14017e820  lea     rcx, [r11+2F8h]; this
0x14017e827  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x14017e82c  mov     rdx, [r10+2D0h]
0x14017e833  shr     rdx, 0Ah
0x14017e837  mov     ecx, eax
0x14017e839  mov     r9, rsi
0x14017e83c  cmp     rdx, rcx
0x14017e83f  cmovnb  r9, r10
0x14017e843  jmp     short loc_14017E848
0x14017e845  mov     r9, rsi
0x14017e848  mov     eax, [r14+308h]
0x14017e84f  cmp     eax, 1
0x14017e852  jz      short loc_14017E859
0x14017e854  cmp     eax, 2
  ... truncated ...
```
