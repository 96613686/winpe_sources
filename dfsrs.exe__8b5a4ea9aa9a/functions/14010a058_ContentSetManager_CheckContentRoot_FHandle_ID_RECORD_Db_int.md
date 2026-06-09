# ContentSetManager::CheckContentRoot(FHandle &,ID_RECORD &,Db *,int &)

- ea: `0x14010a058`
- end: `0x14010abed`
- name: `?CheckContentRoot@ContentSetManager@@AEAAPEAVFrsStatus@@AEAVFHandle@@AEAVID_RECORD@@PEAVDb@@AEAH@Z`
- size: `2965`
- prototype: `struct FrsStatus *(ContentSetManager *__hidden this, struct FHandle *, struct ID_RECORD *, struct Db *, int *)`
- caller_count: `1`
- callee_count: `33`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x1401127a4`

## callees

- `0x1400036a0`
- `0x1400046cc`
- `0x14000daa0`
- `0x14000e34c`
- `0x14000ee94`
- `0x140019358`
- `0x140022d1c`
- `0x1400248f4`
- `0x14002c1c0`
- `0x140031984`
- `0x140047e30`
- `0x140047e4c`
- `0x140055db4`
- `0x14005603c`
- `0x140057ddc`
- `0x140058888`
- `0x14006f224`
- `0x1400727e8`
- `0x1400a1ccc`
- `0x1400af320`
- `0x140100b64`
- `0x140106618`
- `0x140106ac4`
- `0x14010750c`
- `0x14010a058`
- `0x14010f2ec`
- `0x140116c5c`
- `0x1401b9494`
- `0x1401ba178`
- `0x1401ba218`
- `0x1401bf310`
- `0x1401bf3d0`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14010a196`
- `KERNEL32!GetCurrentThreadId` at `0x14010a57c`
- `KERNEL32!GetCurrentThreadId` at `0x14010a73c`
- `KERNEL32!GetCurrentThreadId` at `0x14010a8cb`
- `KERNEL32!GetCurrentThreadId` at `0x14010a91f`
- `KERNEL32!GetCurrentThreadId` at `0x14010ab8c`
- `KERNEL32!GetCurrentThreadId` at `0x14010a196`
- `KERNEL32!GetCurrentThreadId` at `0x14010a57c`
- `KERNEL32!GetCurrentThreadId` at `0x14010a73c`
- `KERNEL32!GetCurrentThreadId` at `0x14010a8cb`
- `KERNEL32!GetCurrentThreadId` at `0x14010a91f`
- `KERNEL32!GetCurrentThreadId` at `0x14010ab8c`

## string_xrefs

- `0x14010a4b1`: `Failed The database contains stale content. The content root has been replaced since DFSR was run last time. csId:%? csName:%? rootPath:%? state:%? ptr:%p csInfoHistoryGuid:%?`
- `0x14010a273`: `Volume serial numbers don't match. Configuration: %s actual: %s`
- `0x14010ab79`: `Failed. The database contains stale content. csId:%? csName:%? rootPath:%? state:%? ptr:%p csInfoHistoryGuid:%?`
- `0x14010aaa1`: `Root-root overlap detected in the database. csId:%? csName:%? rootPath:%? state:%? ptr:%p csInfoHistoryGuid:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
struct FrsStatus *__fastcall ContentSetManager::CheckContentRoot(
        ContentSetManager *this,
        struct FHandle *a2,
        struct ID_RECORD *a3,
        struct Db *a4,
        int *a5)
{
  __int64 v9; // rbx
  __int64 v10; // rax
  struct FrsStatus *Fid; // rdi
  __int64 v12; // r14
  DWORD CurrentThreadId; // eax
  __int64 v14; // rcx
  unsigned __int64 v15; // rax
  int v16; // r14d
  __int64 v17; // rax
  struct FrsStatus *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  DWORD v21; // eax
  __int64 v22; // rcx
  LPCRITICAL_SECTION v23; // rax
  __int64 v24; // rcx
  int v25; // edx
  int v26; // r9d
  DWORD v27; // eax
  __int64 v28; // rcx
  struct Config::ContentSet *v29; // rax
  int v30; // edx
  DWORD v31; // eax
  __int64 v32; // rcx
  DWORD v33; // eax
  __int64 v34; // rcx
  DWORD v36; // eax
  __int64 v37; // rcx
  struct FrsStatus *FileInfo; // [rsp+50h] [rbp-B0h] BYREF
  int v39; // [rsp+58h] [rbp-A8h] BYREF
  Ulonglong *v40; // [rsp+60h] [rbp-A0h] BYREF
  int v41; // [rsp+68h] [rbp-98h] BYREF
  const unsigned __int16 *v42; // [rsp+70h] [rbp-90h] BYREF
  const unsigned __int16 *v43; // [rsp+78h] [rbp-88h] BYREF
  __int64 v44; // [rsp+80h] [rbp-80h] BYREF
  const unsigned __int16 *v45; // [rsp+88h] [rbp-78h] BYREF
  __int64 v46; // [rsp+90h] [rbp-70h] BYREF
  ContentSetManager *v47; // [rsp+98h] [rbp-68h] BYREF
  __int64 v48; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v49; // [rsp+A8h] [rbp-58h] BYREF
  void **v50; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v51; // [rsp+B8h] [rbp-48h] BYREF
  const wchar_t *v52; // [rsp+C0h] [rbp-40h] BYREF
  int v53; // [rsp+C8h] [rbp-38h]
  int v54; // [rsp+CCh] [rbp-34h]
  const wchar_t *v55; // [rsp+D0h] [rbp-30h]
  const wchar_t *v56; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v57; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v58; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v59[128]; // [rsp+F0h] [rbp-10h] BYREF
  struct _BY_HANDLE_FILE_INFORMATION v60; // [rsp+170h] [rbp+70h] BYREF
  const wchar_t *v61; // [rsp+1A8h] [rbp+A8h] BYREF
  int v62; // [rsp+1B0h] [rbp+B0h]
  int v63; // [rsp+1B4h] [rbp+B4h]
  const wchar_t *v64; // [rsp+1B8h] [rbp+B8h]
  const wchar_t *v65; // [rsp+1D8h] [rbp+D8h] BYREF
  int v66; // [rsp+1E0h] [rbp+E0h]
  int v67; // [rsp+1E4h] [rbp+E4h]
  const wchar_t *v68; // [rsp+1E8h] [rbp+E8h]
  _QWORD v69[2]; // [rsp+210h] [rbp+110h] BYREF
  _BYTE v70[128]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v71[72]; // [rsp+2A0h] [rbp+1A0h] BYREF
  struct _GUID v72; // [rsp+2E8h] [rbp+1E8h] BYREF

  v9 = 0;
  ID_RECORD::ID_RECORD((ID_RECORD *)v71);
  v46 = 0;
  memset_0(v69, 0, 0x88u);
  v39 = 0;
  FilePath::FilePath((FilePath *)&v50);
  v56 = &pServiceName;
  memset(&v60, 0, sizeof(v60));
  v49 = 0;
  v44 = 0;
  v48 = 0;
  v58 = 0;
  v57 = 0;
  LODWORD(v47) = 0;
  v41 = 0;
  v10 = Config::ConfigInstance<Config::ContentSet>::Get((char *)this + 1120);
  ScopedRef<Config::ContentSet>::Set(&v44, v10);
  if ( *a5 )
    *((_QWORD *)this + 123) = *((_QWORD *)a3 + 86);
  Fid = FHandle::GetFid(a2, (struct FileId *)&v46);
  if ( !Fid )
  {
    Fid = FHandle::GetByHandleInfo(a2, &v60);
    if ( !Fid )
    {
      v12 = Config::ConfigInstance<Config::ContentSet>::Get(*((_QWORD *)this + 215) + 232LL);
      v49 = v12;
      if ( v60.dwVolumeSerialNumber != *(_DWORD *)(v12 + 320) )
      {
        CurrentThreadId = GetCurrentThreadId();
        Fid = (struct FrsStatus *)FrsStatusList::PushNewError(
                                    v14,
                                    9003,
                                    0,
                                    3,
                                    "base\\fs\\remotefs\\frs\\src\\sync\\contentsetmanager.cpp",
                                    "ContentSetManager::CheckContentRoot",
                                    5542,
                                    CurrentThreadId,
                                    0);
        if ( g_DebugLog )
        {
          if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
          {
            v52 = L"ContentSetManager::CheckContentRoot";
            v53 = 5544;
            v54 = 2;
            v55 = L"CSMG";
            FileInfo = Dword::Dword((Dword *)&v61, v60.dwVolumeSerialNumber, 16);
            v15 = Config::QWordParam::Get((Config::QWordParam *)(v12 + 288));
            v40 = Ulonglong::Ulonglong((Ulonglong *)&v65, v15, 16);
            dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short *>(
              &v52,
              L"Volume serial numbers don't match. Configuration: %s actual: %s",
              &v40,
              &FileInfo);
          }
        }
      }
    }
  }
  if ( !Fid )
  {
    v16 = 1;
    if ( !*a5 )
    {
      v17 = *(_QWORD *)a4;
      FileInfo = 0;
      v18 = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, int *, __int64 *, _BYTE *, struct FrsStatus **))(v17 + 40))(
                                  a4,
                                  a5,
                                  &v46,
                                  v71,
                                  &FileInfo);
      Fid = v18;
      if ( *a5 )
      {
        v41 = 1;
LABEL_35:
        if ( v18 || !v41 )
          goto LABEL_67;
LABEL_37:
        Fid = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, int *, struct _GUID *, _QWORD *))(*(_QWORD *)a4 + 80LL))(
                                    a4,
                                    &v39,
                                    &v72,
                                    v69);
        FileInfo = Fid;
        if ( Fid
          || !v39
          || v70[105]
          && (v21 = GetCurrentThreadId(),
              Fid = (struct FrsStatus *)FrsStatusList::PushNewError(
                                          v22,
                                          9099,
                                          0,
                                          3,
                                          "base\\fs\\remotefs\\frs\\src\\sync\\contentsetmanager.cpp",
                                          "ContentSetManager::CheckContentRoot",
                                          5680,
                                          v21,
                                          0),
              (FileInfo = Fid) != 0)
          || !v39
          || !v70[104] )
        {
          v23 = g_DebugLog;
          if ( !Fid )
          {
            if ( v39 )
            {
              if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
              {
                v65 = L"ContentSetManager::CheckContentRoot";
                v66 = 5695;
                v67 = 2;
                v68 = L"CSMG";
                v47 = this;
                v41 = *((_DWORD *)this + 148);
                v43 = (const unsigned __int16 *)(*(_QWORD *)(v44 + 616) + 18LL);
                v42 = Config::StringParam::Get((Config::StringParam *)(v44 + 240));
                dbgobj::DbgPrint<unsigned short,_GUID,unsigned short const *,unsigned short const *,enum CONTENT_SET_STATE,unsigned __int64,Guid>(
                  (unsigned int)&v65,
                  (unsigned int)L"Root-root overlap detected in the database. csId:%? csName:%? rootPath:%? state:%? ptr:%"
                                 "p csInfoHistoryGuid:%?",
                  (_DWORD)this + 168,
                  (unsigned int)&v42,
                  (__int64)&v43,
                  (__int64)&v41,
                  (__int64)&v47,
                  (__int64)this + 712);
                Fid = FileInfo;
                v23 = g_DebugLog;
              }
            }
            else
            {
              if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
              {
                v61 = L"ContentSetManager::CheckContentRoot";
                v62 = 5699;
                v63 = 2;
                v64 = L"CSMG";
                v43 = (const unsigned __int16 *)this;
                LODWORD(v40) = *((_DWORD *)this + 148);
                v42 = (const unsigned __int16 *)(*(_QWORD *)(v44 + 616) + 18LL);
                v45 = Config::StringParam::Get((Config::StringParam *)(v44 + 240));
                dbgobj::DbgPrint<unsigned short,_GUID,unsigned short const *,unsigned short const *,enum CONTENT_SET_STATE,unsigned __int64,Guid>(
                  (unsigned int)&v61,
                  (unsigned int)L"Failed. The database contains stale content. csId:%? csName:%? rootPath:%? state:%? ptr:"
                                 "%p csInfoHistoryGuid:%?",
                  (_DWORD)this + 168,
                  (unsigned int)&v45,
                  (__int64)&v42,
                  (__int64)&v40,
                  (__int64)&v43,
                  (__int64)this + 712);
              }
              v36 = GetCurrentThreadId();
              Fid = (struct FrsStatus *)FrsStatusList::PushNewError(
                                          v37,
                                          9003,
                                          0,
                                          3,
                                          "base\\fs\\remotefs\\frs\\src\\sync\\contentsetmanager.cpp",
                                          "ContentSetManager::CheckContentRoot",
                                          5702,
                                          v36,
                                          0);
              FileInfo = Fid;
              v23 = g_DebugLog;
              v16 = (int)v47;
            }
LABEL_45:
            if ( v39 )
            {
              if ( !Fid )
              {
LABEL_57:
                if ( v16 )
                {
                  Config::ContentSetList::ContentSetList((Config::ContentSetList *)v59);
                  Config::ContentSetList::GetAll(
                    (Config::ContentSetList *)(v49 + 744),
                    (struct Config::ContentSetList *)v59);
                  v29 = Config::ContentSetList::Find((Config::ContentSetList *)v59, &v72, 0);
                  ScopedRef<Config::ContentSet>::Set(&v48, v29);
                  if ( v48 )
                    v56 = (const wchar_t *)(*(_QWORD *)(v48 + 616) + 18LL);
                  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
                  {
                    v61 = L"ContentSetManager::CheckContentRoot";
                    v62 = 5745;
                    v63 = 2;
                    v64 = L"CSMG";
                    v43 = (const unsigned __int16 *)this;
                    LODWORD(v40) = *((_DWORD *)this + 148);
                    v42 = (const unsigned __int16 *)(*(_QWORD *)(v44 + 616) + 18LL);
                    v45 = Config::StringParam::Get((Config::StringParam *)(v44 + 240));
                    dbgobj::DbgPrint<unsigned short,_GUID,unsigned short const *,unsigned short const *,enum CONTENT_SET_STATE,unsigned __int64,Guid,_GUID,unsigned short const *>(
                      (unsigned int)&v61,
                      v30,
                      (_DWORD)this + 168,
                      (unsigned int)&v45,
                      (__int64)&v42,
                      (__int64)&v40,
                      (__int64)&v43,
                      (__int64)this + 712,
                      (__int64)&v72,
                      (__int64)&v56);
                    Fid = FileInfo;
                  }
                  if ( !Fid )
                  {
                    v31 = GetCurrentThreadId();
                    Fid = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                v32,
                                                9007,
                                                0,
                                                3,
                                                "base\\fs\\remotefs\\frs\\src\\sync\\contentsetmanager.cpp",
                                                "ContentSetManager::CheckContentRoot",
                                                5752,
                                                v31,
                                                0);
                  }
                  Config::ContentSetList::~ContentSetList((Config::ContentSetList *)v59);
                }
                goto LABEL_67;
              }
              if ( *((_DWORD *)Fid + 1) == 9099 )
              {
                v24 = v69[0] - *((_QWORD *)this + 21);
                if ( v69[0] == *((_QWORD *)this + 21) )
                  v24 = v69[1] - *((_QWORD *)this + 22);
                if ( v24 )
                {
                  if ( v23 && LODWORD(v23[1].LockSemaphore) && SLODWORD(v23[1].OwningThread) >= 4 )
                  {
                    v61 = L"ContentSetManager::CheckContentRoot";
                    v62 = 5719;
                    v63 = 4;
                    v64 = L"CSMG";
                    v43 = (const unsigned __int16 *)this;
                    LODWORD(v40) = *((_DWORD *)this + 148);
                    v42 = (const unsigned __int16 *)(*(_QWORD *)(v44 + 616) + 18LL);
                    v45 = Config::StringParam::Get((Config::StringParam *)(v44 + 240));
                    dbgobj::DbgPrint<unsigned short,_GUID,_GUID,unsigned short const *,unsigned short const *,enum CONTENT_SET_STATE,unsigned __int64,Guid>(
                      (unsigned int)&v61,
                      v25,
                      (unsigned int)v69,
                      v26,
                      (__int64)&v45,
                      (__int64)&v42,
                      (__int64)&v40,
                      (__int64)&v43,
                      (__int64)this + 712);
                    Fid = FileInfo;
                  }
                  v27 = GetCurrentThreadId();
                  Fid = (struct FrsStatus *)FrsStatusList::PushNewError(
                                              v28,
                                              9098,
                                              0,
                                              3,
                                              "base\\fs\\remotefs\\frs\\src\\sync\\contentsetmanager.cpp",
                                              "ContentSetManager::CheckContentRoot",
                                              5724,
                                              v27,
                                              Fid);
                  FileInfo = Fid;
                }
              }
            }
            if ( Fid )
              goto LABEL_67;
            goto LABEL_57;
          }
        }
        else
        {
          Fid = (struct FrsStatus *)VolumeManager::ScheduleRestartDeleteContentSet(
                                      *((_QWORD *)this + 215),
                                      (int)this + 200,
                                      (unsigned int)v69,
                                      (unsigned int)v70,
                                      1);
          FileInfo = Fid;
          v23 = g_DebugLog;
        }
        v16 = (int)v47;
        goto LABEL_45;
      }
      if ( v18 )
        goto LABEL_67;
      v18 = ContentSetManager::DeleteContainedTombstoneContentSets(this, a4, (struct FileId *)&v46);
LABEL_34:
      Fid = v18;
      goto LABEL_35;
    }
    if ( v46 == *((_QWORD *)this + 123) )
      goto LABEL_67;
    v19 = *(_QWORD *)a4;
    FileInfo = 0;
    FileInfo = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, int *, __int64 *, _BYTE *, struct FrsStatus **))(v19 + 40))(
                                     a4,
                                     &v39,
                                     &v46,
                                     v71,
                                     &FileInfo);
    if ( !FileInfo && v39 && (unsigned int)ID_RECORD::Alive((ID_RECORD *)v71) )
    {
      v20 = *(_QWORD *)&v72.Data1 - *((_QWORD *)this + 21);
      if ( *(_QWORD *)&v72.Data1 == *((_QWORD *)this + 21) )
        v20 = *(_QWORD *)v72.Data4 - *((_QWORD *)this + 22);
      if ( v20 )
        goto LABEL_37;
    }
    CLEAR_ERROR(&FileInfo);
    FileInfo = (struct FrsStatus *)NtfsFileSystem::GetFileInfo(
                                     ContentSetManager::fs,
                                     *((_QWORD *)this + 215) + 168LL,
                                     (char *)this + 984,
                                     0,
                                     0,
                                     0,
                                     &v50,
                                     0,
                                     0,
                                     0);
    if ( FileInfo )
    {
      FilePath::Set((FilePath *)&v50, (const unsigned __int16 *)a3 + 78);
      CLEAR_ERROR(&FileInfo);
    }
    else
    {
      FilePath::TrimLongPathChars((FilePath *)&v50);
    }
    if ( *((_DWORD *)this + 148) != 6 )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v52 = L"ContentSetManager::CheckContentRoot";
        v53 = 5642;
        v54 = 2;
        v55 = L"CSMG";
        v45 = (const unsigned __int16 *)this;
        LODWORD(v40) = *((_DWORD *)this + 148);
        v42 = (const unsigned __int16 *)(*(_QWORD *)(v44 + 616) + 18LL);
        v43 = Config::StringParam::Get((Config::StringParam *)(v44 + 240));
        dbgobj::DbgPrint<unsigned short,_GUID,unsigned short const *,unsigned short const *,enum CONTENT_SET_STATE,unsigned __int64,Guid>(
          (unsigned int)&v52,
          (unsigned int)L"Failed The database contains stale content. The content root has been replaced since DFSR was ru"
                         "n last time. csId:%? csName:%? rootPath:%? state:%? ptr:%p csInfoHistoryGuid:%?",
          (_DWORD)this + 168,
          (unsigned int)&v43,
          (__int64)&v42,
          (__int64)&v40,
          (__int64)&v45,
          (__int64)this + 712);
      }
      ContentSetManager::LogEvent((char *)this + 168, 2147490054LL, v51 + 18);
    }
    Fid = FileInfo;
    if ( !FileInfo )
    {
      v18 = (struct FrsStatus *)VolumeManager::ScheduleRestartDeleteContentSet(
                                  *((_QWORD *)this + 215),
                                  (int)this + 200,
                                  (int)this + 168,
                                  0,
                                  *((_DWORD *)this + 148) != 6);
      goto LABEL_34;
    }
  }
LABEL_67:
  *((_QWORD *)this + 123) = v46;
  if ( Fid )
  {
    v33 = GetCurrentThreadId();
    v9 = FrsStatusList::PushNewError(
           v34,
           *((unsigned int *)Fid + 1),
           *((unsigned int *)Fid + 2),
           *(unsigned int *)Fid,
           "base\\fs\\remotefs\\frs\\src\\sync\\contentsetmanager.cpp",
           "ContentSetManager::CheckContentRoot",
           5758,
           v33,
           Fid);
  }
  ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v57);
  ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v58);
  ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v48);
  ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v44);
  ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v49);
  v50 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v51);
  return (struct FrsStatus *)v9;
}

```

## disassembly

```asm
0x14010a058  push    rbp
0x14010a05a  push    rbx
0x14010a05b  push    rsi
0x14010a05c  push    rdi
0x14010a05d  push    r12
0x14010a05f  push    r13
0x14010a061  push    r14
0x14010a063  push    r15
0x14010a065  lea     rbp, [rsp-488h]
0x14010a06d  sub     rsp, 588h
0x14010a074  mov     rax, cs:__security_cookie
0x14010a07b  xor     rax, rsp
0x14010a07e  mov     [rbp+4C0h+var_50], rax
0x14010a085  mov     r12, r9
0x14010a088  mov     r13, r8
0x14010a08b  mov     r14, rdx
0x14010a08e  mov     rsi, rcx
0x14010a091  mov     r15, [rbp+4C0h+arg_20]
0x14010a098  xor     ebx, ebx
0x14010a09a  lea     rcx, [rbp+4C0h+var_320]; this
0x14010a0a1  call    ??0ID_RECORD@@QEAA@XZ; ID_RECORD::ID_RECORD(void)
0x14010a0a6  mov     [rbp+4C0h+var_530], rbx
0x14010a0aa  xor     edx, edx; Val
0x14010a0ac  mov     r8d, 88h; Size
0x14010a0b2  lea     rcx, [rbp+4C0h+var_3B0]; void *
0x14010a0b9  call    memset_0
0x14010a0be  mov     [rsp+5C0h+var_568], ebx
0x14010a0c2  lea     rcx, [rbp+4C0h+var_510]; this
0x14010a0c6  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x14010a0cb  nop
0x14010a0cc  lea     rax, pServiceName
0x14010a0d3  mov     [rbp+4C0h+var_4E8], rax
0x14010a0d7  xorps   xmm0, xmm0
0x14010a0da  xor     eax, eax
0x14010a0dc  movups  xmmword ptr [rbp+4C0h+var_450.dwFileAttributes], xmm0
0x14010a0e0  movups  xmmword ptr [rbp+4C0h+var_450.ftLastAccessTime.dwHighDateTime], xmm0
0x14010a0e7  movups  xmmword ptr [rbp+4C0h+var_450.nFileSizeHigh], xmm0
0x14010a0ee  mov     [rbp+4C0h+var_450.nFileIndexLow], eax
0x14010a0f4  mov     [rbp+4C0h+var_518], rbx
0x14010a0f8  mov     [rbp+4C0h+var_540], rbx
0x14010a0fc  mov     [rbp+4C0h+var_520], rbx
0x14010a100  mov     [rbp+4C0h+var_4D8], rbx
0x14010a104  mov     [rbp+4C0h+var_4E0], rbx
0x14010a108  mov     dword ptr [rbp+4C0h+var_528], ebx
0x14010a10b  mov     [rsp+5C0h+var_558], ebx
0x14010a10f  lea     rcx, [rsi+460h]
0x14010a116  call    ?Get@?$ConfigInstance@VContentSet@Config@@@Config@@QEAAPEAVContentSet@2@XZ; Config::ConfigInstance<Config::ContentSet>::Get(void)
0x14010a11b  mov     rdx, rax
0x14010a11e  lea     rcx, [rbp+4C0h+var_540]
0x14010a122  call    ?Set@?$ScopedRef@VContentSet@Config@@@@AEAAXPEAVContentSet@Config@@@Z; ScopedRef<Config::ContentSet>::Set(Config::ContentSet *)
0x14010a127  cmp     [r15], ebx
0x14010a12a  jz      short loc_14010A13A
0x14010a12c  mov     rax, [r13+2B0h]
0x14010a133  mov     [rsi+3D8h], rax
0x14010a13a  lea     rdx, [rbp+4C0h+var_530]; struct FileId *
0x14010a13e  mov     rcx, r14; this
0x14010a141  call    ?GetFid@FHandle@@QEBAPEAVFrsStatus@@AEAVFileId@@@Z; FHandle::GetFid(FileId &)
0x14010a146  mov     rdi, rax
0x14010a149  test    rax, rax
0x14010a14c  jnz     loc_14010A283
0x14010a152  lea     rdx, [rbp+4C0h+var_450]; struct _BY_HANDLE_FILE_INFORMATION *
0x14010a156  mov     rcx, r14; this
0x14010a159  call    ?GetByHandleInfo@FHandle@@QEBAPEAVFrsStatus@@AEAU_BY_HANDLE_FILE_INFORMATION@@@Z; FHandle::GetByHandleInfo(_BY_HANDLE_FILE_INFORMATION &)
0x14010a15e  mov     rdi, rax
0x14010a161  test    rax, rax
0x14010a164  jnz     loc_14010A283
0x14010a16a  mov     rcx, [rsi+6B8h]
0x14010a171  add     rcx, 0E8h
0x14010a178  call    ?Get@?$ConfigInstance@VContentSet@Config@@@Config@@QEAAPEAVContentSet@2@XZ; Config::ConfigInstance<Config::ContentSet>::Get(void)
0x14010a17d  mov     r14, rax
0x14010a180  mov     [rbp+4C0h+var_518], rax
0x14010a184  mov     ecx, [rax+140h]
0x14010a18a  cmp     [rbp+4C0h+var_450.dwVolumeSerialNumber], ecx
0x14010a190  jz      loc_14010A283
0x14010a196  call    cs:__imp_GetCurrentThreadId
0x14010a19d  nop     dword ptr [rax+rax+00h]
0x14010a1a2  mov     [rsp+5C0h+var_580], rbx
0x14010a1a7  mov     dword ptr [rsp+5C0h+var_588], eax
0x14010a1ab  mov     dword ptr [rsp+5C0h+var_590], 15A6h
0x14010a1b3  lea     rax, aContentsetmana_19; "ContentSetManager::CheckContentRoot"
0x14010a1ba  mov     [rsp+5C0h+var_598], rax
0x14010a1bf  lea     rax, aBaseFsRemotefs_85; "base\\fs\\remotefs\\frs\\src\\sync\\con"...
0x14010a1c6  mov     [rsp+5C0h+var_5A0], rax
0x14010a1cb  lea     r9d, [rdi+3]
0x14010a1cf  xor     r8d, r8d
0x14010a1d2  mov     edx, 232Bh
0x14010a1d7  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14010a1dc  mov     rdi, rax
0x14010a1df  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14010a1e6  test    rax, rax
0x14010a1e9  jz      loc_14010A283
0x14010a1ef  cmp     [rax+40h], ebx
0x14010a1f2  jz      loc_14010A283
0x14010a1f8  cmp     dword ptr [rax+38h], 2
0x14010a1fc  jl      loc_14010A283
0x14010a202  lea     rax, aContentsetmana_57; "ContentSetManager::CheckContentRoot"
0x14010a209  mov     [rbp+4C0h+var_500], rax
0x14010a20d  mov     [rbp+4C0h+var_4F8], 15A8h
0x14010a214  mov     [rbp+4C0h+var_4F4], 2
0x14010a21b  lea     rax, aCsmg; "CSMG"
0x14010a222  mov     [rbp+4C0h+var_4F0], rax
0x14010a226  mov     r8d, 10h; int
0x14010a22c  mov     edx, [rbp+4C0h+var_450.dwVolumeSerialNumber]; unsigned int
0x14010a232  lea     rcx, [rbp+4C0h+var_418]; this
0x14010a239  call    ??0Dword@@QEAA@KH@Z; Dword::Dword(ulong,int)
0x14010a23e  mov     [rsp+5C0h+var_570], rax
0x14010a243  lea     rcx, [r14+120h]; this
0x14010a24a  call    ?Get@QWordParam@Config@@QEBA_KXZ; Config::QWordParam::Get(void)
0x14010a24f  mov     rdx, rax; unsigned __int64
0x14010a252  mov     r8d, 10h; int
0x14010a258  lea     rcx, [rbp+4C0h+var_3E8]; this
0x14010a25f  call    ??0Ulonglong@@QEAA@_KH@Z; Ulonglong::Ulonglong(unsigned __int64,int)
0x14010a264  mov     [rsp+5C0h+var_560], rax
0x14010a269  lea     r9, [rsp+5C0h+var_570]
0x14010a26e  lea     r8, [rsp+5C0h+var_560]
0x14010a273  lea     rdx, aVolumeSerialNu; "Volume serial numbers don't match. Conf"...
0x14010a27a  lea     rcx, [rbp+4C0h+var_500]
0x14010a27e  call    ??$DbgPrint@GPEBGPEAG@dbgobj@@QEAA_KPEBGAEBQEBGAEBQEAG@Z; dbgobj::DbgPrint<ushort,ushort const *,ushort *>(ushort const *,ushort const * const &,ushort * const &)
0x14010a283  test    rdi, rdi
0x14010a286  jnz     loc_14010A90F
0x14010a28c  lea     r14d, [rdi+1]
0x14010a290  cmp     [r15], ebx
0x14010a293  jnz     short loc_14010A2F1
0x14010a295  mov     rax, [r12]
0x14010a299  mov     [rsp+5C0h+var_570], rbx
0x14010a29e  lea     rcx, [rsp+5C0h+var_570]
0x14010a2a3  mov     [rsp+5C0h+var_5A0], rcx
0x14010a2a8  lea     r9, [rbp+4C0h+var_320]
0x14010a2af  lea     r8, [rbp+4C0h+var_530]
0x14010a2b3  mov     rdx, r15
0x14010a2b6  mov     rcx, r12
0x14010a2b9  mov     rax, [rax+28h]
0x14010a2bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14010a2c2  mov     rdi, rax
0x14010a2c5  cmp     [r15], ebx
0x14010a2c8  jz      short loc_14010A2D4
0x14010a2ca  mov     [rsp+5C0h+var_558], r14d
0x14010a2cf  jmp     loc_14010A51D
0x14010a2d4  test    rax, rax
0x14010a2d7  jnz     loc_14010A90F
0x14010a2dd  lea     r8, [rbp+4C0h+var_530]; struct FileId *
0x14010a2e1  mov     rdx, r12; struct Db *
0x14010a2e4  mov     rcx, rsi; this
0x14010a2e7  call    ?DeleteContainedTombstoneContentSets@ContentSetManager@@AEAAPEAVFrsStatus@@PEAVDb@@AEAVFileId@@@Z; ContentSetManager::DeleteContainedTombstoneContentSets(Db *,FileId &)
0x14010a2ec  jmp     loc_14010A51A
0x14010a2f1  mov     rax, [rsi+3D8h]
0x14010a2f8  cmp     [rbp+4C0h+var_530], rax
0x14010a2fc  jz      loc_14010A90F
0x14010a302  mov     rax, [r12]
0x14010a306  mov     [rsp+5C0h+var_570], rbx
0x14010a30b  lea     rcx, [rsp+5C0h+var_570]
0x14010a310  mov     [rsp+5C0h+var_5A0], rcx
0x14010a315  lea     r9, [rbp+4C0h+var_320]
0x14010a31c  lea     r8, [rbp+4C0h+var_530]
0x14010a320  lea     rdx, [rsp+5C0h+var_568]
0x14010a325  mov     rcx, r12
0x14010a328  mov     rax, [rax+28h]
0x14010a32c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14010a331  mov     [rsp+5C0h+var_570], rax
0x14010a336  test    rax, rax
0x14010a339  jnz     short loc_14010A378
0x14010a33b  cmp     [rsp+5C0h+var_568], ebx
0x14010a33f  jz      short loc_14010A378
0x14010a341  lea     rcx, [rbp+4C0h+var_320]; this
0x14010a348  call    ?Alive@ID_RECORD@@QEBAHXZ; ID_RECORD::Alive(void)
0x14010a34d  test    eax, eax
0x14010a34f  jz      short loc_14010A378
0x14010a351  mov     rax, qword ptr [rbp+4C0h+var_2D8.Data1]
0x14010a358  sub     rax, [rsi+0A8h]
0x14010a35f  jnz     short loc_14010A36F
0x14010a361  mov     rax, qword ptr [rbp+4C0h+var_2D8.Data4]
0x14010a368  sub     rax, [rsi+0B0h]
0x14010a36f  test    rax, rax
0x14010a372  jnz     loc_14010A530
0x14010a378  lea     rcx, [rsp+5C0h+var_570]; struct FrsStatus **
0x14010a37d  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x14010a382  mov     rdx, [rsi+6B8h]
0x14010a389  lea     r8, [rsi+3D8h]
0x14010a390  add     rdx, 0A8h
0x14010a397  mov     [rsp+5C0h+var_578], rbx
0x14010a39c  mov     [rsp+5C0h+var_580], rbx
0x14010a3a1  mov     [rsp+5C0h+var_588], rbx
0x14010a3a6  lea     rax, [rbp+4C0h+var_510]
0x14010a3aa  mov     [rsp+5C0h+var_590], rax
0x14010a3af  mov     [rsp+5C0h+var_598], rbx
0x14010a3b4  mov     [rsp+5C0h+var_5A0], rbx
0x14010a3b9  xor     r9d, r9d
0x14010a3bc  lea     rcx, ?fs@ContentSetManager@@0VNtfsFileSystem@@A; NtfsFileSystem ContentSetManager::fs
0x14010a3c3  call    ?GetFileInfo@NtfsFileSystem@@UEAAPEAVFrsStatus@@AEBVVolumeId@@AEBVFileId@@PEAVUsn@@PEAV4@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVFilePath@@PEAU_BY_HANDLE_FILE_INFORMATION@@PEAU_FILE_BASIC_INFORMATION@@PEAU_FILE_STANDARD_INFORMATION@@@Z; NtfsFileSystem::GetFileInfo(VolumeId const &,FileId const &,Usn *,FileId *,std::wstring *,FilePath *,_BY_HANDLE_FILE_INFORMATION *,_FILE_BASIC_INFORMATION *,_FILE_STANDARD_INFORMATION *)
0x14010a3c8  mov     [rsp+5C0h+var_570], rax
0x14010a3cd  lea     rcx, [rbp+4C0h+var_510]; this
0x14010a3d1  test    rax, rax
0x14010a3d4  jnz     short loc_14010A3DD
0x14010a3d6  call    ?TrimLongPathChars@FilePath@@QEAAXXZ; FilePath::TrimLongPathChars(void)
0x14010a3db  jmp     short loc_14010A3F3
0x14010a3dd  lea     rdx, [r13+9Ch]; unsigned __int16 *
0x14010a3e4  call    ?Set@FilePath@@QEAAXPEBG@Z; FilePath::Set(ushort const *)
0x14010a3e9  lea     rcx, [rsp+5C0h+var_570]; struct FrsStatus **
0x14010a3ee  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x14010a3f3  mov     eax, [rsi+250h]
0x14010a3f9  cmp     eax, 6
0x14010a3fc  jz      loc_14010A4DA
0x14010a402  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14010a409  test    rax, rax
0x14010a40c  jz      loc_14010A4C1
0x14010a412  cmp     [rax+40h], ebx
0x14010a415  jz      loc_14010A4C1
0x14010a41b  cmp     dword ptr [rax+38h], 2
0x14010a41f  jl      loc_14010A4C1
0x14010a425  lea     rax, aContentsetmana_57; "ContentSetManager::CheckContentRoot"
0x14010a42c  mov     [rbp+4C0h+var_500], rax
0x14010a430  mov     [rbp+4C0h+var_4F8], 160Ah
0x14010a437  mov     [rbp+4C0h+var_4F4], 2
0x14010a43e  lea     rax, aCsmg; "CSMG"
0x14010a445  mov     [rbp+4C0h+var_4F0], rax
0x14010a449  mov     [rbp+4C0h+var_538], rsi
0x14010a44d  mov     eax, [rsi+250h]
0x14010a453  mov     dword ptr [rsp+5C0h+var_560], eax
0x14010a457  mov     rcx, [rbp+4C0h+var_540]
0x14010a45b  mov     rax, [rcx+268h]
0x14010a462  add     rax, 12h
0x14010a466  mov     [rsp+5C0h+var_550], rax
0x14010a46b  add     rcx, 0F0h; this
0x14010a472  call    ?Get@StringParam@Config@@QEBAPEBGXZ; Config::StringParam::Get(void)
0x14010a477  mov     [rsp+5C0h+var_548], rax
0x14010a47c  lea     rax, [rsi+2C8h]
0x14010a483  lea     r8, [rsi+0A8h]
0x14010a48a  mov     [rsp+5C0h+var_588], rax
0x14010a48f  lea     rax, [rbp+4C0h+var_538]
0x14010a493  mov     [rsp+5C0h+var_590], rax
0x14010a498  lea     rax, [rsp+5C0h+var_560]
0x14010a49d  mov     [rsp+5C0h+var_598], rax
0x14010a4a2  lea     rax, [rsp+5C0h+var_550]
0x14010a4a7  mov     [rsp+5C0h+var_5A0], rax
0x14010a4ac  lea     r9, [rsp+5C0h+var_548]
0x14010a4b1  lea     rdx, aFailedTheDatab_0; "Failed The database contains stale cont"...
0x14010a4b8  lea     rcx, [rbp+4C0h+var_500]
0x14010a4bc  call    ??$DbgPrint@GU_GUID@@PEBGPEBGW4CONTENT_SET_STATE@@_KVGuid@@@dbgobj@@QEAA_KPEBGAEBU_GUID@@AEBQEBG2AEBW4CONTENT_SET_STATE@@AEB_KAEBVGuid@@@Z; dbgobj::DbgPrint<ushort,_GUID,ushort const *,ushort const *,CONTENT_SET_STATE,unsigned __int64,Guid>(ushort const *,_GUID const &,ushort const * const &,ushort const * const &,CONTENT_SET_STATE const &,unsigned __int64 const &,Guid const &)
0x14010a4c1  mov     r8, [rbp+4C0h+var_508]
0x14010a4c5  add     r8, 12h
0x14010a4c9  lea     rcx, [rsi+0A8h]
0x14010a4d0  mov     edx, 80001906h
0x14010a4d5  call    ?LogEvent@ContentSetManager@@SAXAEBU_GUID@@W4FrsEventsEnum7@@PEBG@Z; ContentSetManager::LogEvent(_GUID const &,FrsEventsEnum7,ushort const *)
0x14010a4da  mov     rdi, [rsp+5C0h+var_570]
0x14010a4df  test    rdi, rdi
0x14010a4e2  jnz     loc_14010A90F
0x14010a4e8  mov     rcx, [rsi+6B8h]
0x14010a4ef  mov     eax, [rsi+250h]
0x14010a4f5  mov     r9d, ebx
0x14010a4f8  cmp     eax, 6
0x14010a4fb  setnz   r9b
0x14010a4ff  lea     r8, [rsi+0A8h]
0x14010a506  lea     rdx, [rsi+0C8h]
0x14010a50d  mov     dword ptr [rsp+5C0h+var_5A0], r9d
0x14010a512  xor     r9d, r9d
0x14010a515  call    ?ScheduleRestartDeleteContentSet@VolumeManager@@QEAAPEAVFrsStatus@@AEAV?$FrsStringImpl@GD@@AEBU_GUID@@PEBU4@H@Z; VolumeManager::ScheduleRestartDeleteContentSet(FrsStringImpl<ushort,char> &,_GUID const &,_GUID const *,int)
0x14010a51a  mov     rdi, rax
0x14010a51d  test    rax, rax
0x14010a520  jnz     loc_14010A90F
0x14010a526  cmp     [rsp+5C0h+var_558], ebx
0x14010a52a  jz      loc_14010A90F
0x14010a530  mov     rax, [r12]
0x14010a534  lea     r9, [rbp+4C0h+var_3B0]
0x14010a53b  lea     r8, [rbp+4C0h+var_2D8]
0x14010a542  lea     rdx, [rsp+5C0h+var_568]
0x14010a547  mov     rcx, r12
0x14010a54a  mov     rax, [rax+50h]
0x14010a54e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14010a553  mov     rdi, rax
0x14010a556  mov     [rsp+5C0h+var_570], rax
0x14010a55b  mov     r15d, 238Bh
0x14010a561  test    rax, rax
0x14010a564  jnz     loc_14010A9D3
0x14010a56a  cmp     [rsp+5C0h+var_568], ebx
0x14010a56e  jz      loc_14010A9D3
0x14010a574  cmp     [rbp+4C0h+var_337], bl
0x14010a57a  jz      short loc_14010A5D1
0x14010a57c  call    cs:__imp_GetCurrentThreadId
0x14010a583  nop     dword ptr [rax+rax+00h]
0x14010a588  mov     [rsp+5C0h+var_580], rbx
0x14010a58d  mov     dword ptr [rsp+5C0h+var_588], eax
0x14010a591  mov     dword ptr [rsp+5C0h+var_590], 1630h
0x14010a599  lea     rax, aContentsetmana_19; "ContentSetManager::CheckContentRoot"
0x14010a5a0  mov     [rsp+5C0h+var_598], rax
0x14010a5a5  lea     rax, aBaseFsRemotefs_85; "base\\fs\\remotefs\\frs\\src\\sync\\con"...
0x14010a5ac  mov     [rsp+5C0h+var_5A0], rax
0x14010a5b1  lea     r9d, [rdi+3]
0x14010a5b5  xor     r8d, r8d
0x14010a5b8  mov     edx, r15d
0x14010a5bb  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14010a5c0  mov     rdi, rax
0x14010a5c3  mov     [rsp+5C0h+var_570], rax
0x14010a5c8  test    rax, rax
0x14010a5cb  jnz     loc_14010A9D3
0x14010a5d1  cmp     [rsp+5C0h+var_568], ebx
0x14010a5d5  jz      loc_14010A9D3
0x14010a5db  cmp     [rbp+4C0h+var_338], bl
0x14010a5e1  jz      loc_14010A9D3
0x14010a5e7  lea     rdx, [rsi+0C8h]
0x14010a5ee  mov     dword ptr [rsp+5C0h+var_5A0], r14d
  ... truncated ...
```
