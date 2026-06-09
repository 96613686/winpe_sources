# DBClone::DBExport(FilePath &,FilePath &,DBCloneInterface::VALIDATION_LEVEL,int)

- ea: `0x14002ddb0`
- end: `0x14002f624`
- name: `?DBExport@DBClone@@UEAAPEAVFrsStatus@@AEAVFilePath@@0W4VALIDATION_LEVEL@DBCloneInterface@@H@Z`
- size: `6260`
- prototype: ``
- caller_count: `0`
- callee_count: `82`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1400036a0`
- `0x1400036d0`
- `0x14000c910`
- `0x14000cb00`
- `0x14000cd1c`
- `0x14000d980`
- `0x14000daa0`
- `0x14000dcc0`
- `0x14000e34c`
- `0x14000ee94`
- `0x14000f83c`
- `0x140010680`
- `0x140010e70`
- `0x140011408`
- `0x140014df4`
- `0x140019358`
- `0x14001c6c0`
- `0x14001d960`
- `0x14001e704`
- `0x14001e710`
- `0x1400217d0`
- `0x140023b3c`
- `0x1400248f4`
- `0x1400249a4`
- `0x1400292e4`
- `0x140029688`
- `0x14002a6d0`
- `0x14002a820`
- `0x14002a97c`
- `0x14002be54`
- `0x14002c160`
- `0x14002c1c0`
- `0x14002c270`
- `0x14002c2bc`
- `0x14002c2f4`
- `0x14002ca74`
- `0x14002d600`
- `0x14002d6bc`
- `0x14002ddb0`
- `0x140030da8`
- `0x14003126c`
- `0x140031340`
- `0x140031b44`
- `0x140031c1c`
- `0x140034e28`
- `0x140035304`
- `0x140035378`
- `0x140035488`
- `0x1400357bc`
- `0x1400362c0`

## import_xrefs

- `KERNEL32!CreateThread` at `0x14002e9c0`
- `KERNEL32!CreateThread` at `0x14002e9c0`
- `KERNEL32!GetExitCodeThread` at `0x14002f07d`
- `KERNEL32!GetExitCodeThread` at `0x14002f07d`
- `KERNEL32!WaitForSingleObject` at `0x14002ef59`
- `KERNEL32!WaitForSingleObject` at `0x14002ef59`
- `KERNEL32!CloseHandle` at `0x14002f45e`
- `KERNEL32!CloseHandle` at `0x14002f45e`
- `KERNEL32!GetLastError` at `0x14002ea56`
- `KERNEL32!GetLastError` at `0x14002ef80`
- `KERNEL32!GetLastError` at `0x14002f00e`
- `KERNEL32!GetLastError` at `0x14002f09b`
- `KERNEL32!GetLastError` at `0x14002ea56`
- `KERNEL32!GetLastError` at `0x14002ef80`
- `KERNEL32!GetLastError` at `0x14002f00e`
- `KERNEL32!GetLastError` at `0x14002f09b`
- `KERNEL32!SetEvent` at `0x14002f4d4`
- `KERNEL32!SetEvent` at `0x14002f4d4`
- `KERNEL32!GetCurrentThreadId` at `0x14002df87`
- `KERNEL32!GetCurrentThreadId` at `0x14002dfd7`
- `KERNEL32!GetCurrentThreadId` at `0x14002e618`
- `KERNEL32!GetCurrentThreadId` at `0x14002ea48`
- `KERNEL32!GetCurrentThreadId` at `0x14002ee68`
- `KERNEL32!GetCurrentThreadId` at `0x14002ef72`
- `KERNEL32!GetCurrentThreadId` at `0x14002f08d`
- `KERNEL32!GetCurrentThreadId` at `0x14002f0e6`
- `KERNEL32!GetCurrentThreadId` at `0x14002f4e5`
- `KERNEL32!GetCurrentThreadId` at `0x14002f5d4`
- `KERNEL32!GetCurrentThreadId` at `0x14002df87`
- `KERNEL32!GetCurrentThreadId` at `0x14002dfd7`
- `KERNEL32!GetCurrentThreadId` at `0x14002e618`
- `KERNEL32!GetCurrentThreadId` at `0x14002ea48`
- `KERNEL32!GetCurrentThreadId` at `0x14002ee68`
- `KERNEL32!GetCurrentThreadId` at `0x14002ef72`
- `KERNEL32!GetCurrentThreadId` at `0x14002f08d`
- `KERNEL32!GetCurrentThreadId` at `0x14002f0e6`
- `KERNEL32!GetCurrentThreadId` at `0x14002f4e5`
- `KERNEL32!GetCurrentThreadId` at `0x14002f5d4`

## string_xrefs

- `0x14002e10f`: `Failed to get volume for path: %?, status: %?`
- `0x14002e29f`: `Source volume:%? DB Path:%?`
- `0x14002e488`: `Construct a temp DB path at:%?`
- `0x14002e607`: `The source DB is dirty. Source volume:%? DB Path:%?`
- `0x14002e6e0`: `$db_update$`
- `0x14002ea33`: `Starting the DB validation thread. %p`
- `0x14002ebe3`: `Starting the local DB update for csId:%?`
- `0x14002eee8`: `Finished the local DB update for csId:%?`
- `0x14002f182`: `Source DB manager deleted`
- `0x14002f1f3`: `Destination DB manager deleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall DBClone::DBExport(struct FrsStatus *a1, __int64 a2, __int64 a3, int a4, int a5)
{
  struct FrsStatus *v7; // r13
  __int64 v8; // r15
  struct FrsStatus *VolumeFromFilePath; // r12
  int v10; // edx
  DWORD CurrentThreadId; // eax
  __int64 v12; // rcx
  unsigned int *v13; // rbx
  DWORD v14; // eax
  __int64 v15; // rcx
  ConfigContext *v16; // rcx
  VolumeIdTable *VolumeTable; // rax
  __int64 DisplayPath; // rdi
  __int64 v19; // rbx
  _QWORD *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  struct FrsStatus *restarted; // r9
  DBClone *v24; // rcx
  __int64 v25; // rbx
  VolumeManager *v26; // rax
  DBClone *v27; // rcx
  const unsigned __int16 *v28; // rax
  const volatile int *v29; // r8
  DBClone *v30; // rcx
  __int64 v31; // rax
  DWORD v32; // eax
  __int64 v33; // rcx
  DBClone *v34; // rcx
  Dword *v35; // rsi
  Dword *v36; // rdi
  __int64 v37; // rbx
  _QWORD *v38; // rax
  HANDLE Thread; // rax
  DWORD v40; // ebx
  DWORD LastError; // eax
  struct Pdb *v42; // rbx
  char *v43; // rdi
  struct Pdb *v44; // rbx
  __int64 v45; // rax
  __int64 v46; // rax
  unsigned int v47; // r9d
  char v48; // bl
  LPCRITICAL_SECTION v49; // rbx
  unsigned __int16 Flags; // ax
  int v51; // r11d
  DWORD v52; // eax
  __int64 v53; // rcx
  char *v54; // rsi
  DWORD v55; // ebx
  DWORD v56; // eax
  __int64 v57; // rcx
  DWORD v58; // ebx
  DWORD v59; // eax
  __int64 v60; // rcx
  DWORD v61; // eax
  __int64 v62; // rcx
  void (__fastcall ***v63)(_QWORD, __int64); // rcx
  void (__fastcall ***v64)(_QWORD, __int64); // rcx
  int v65; // ebx
  __int64 v66; // rbx
  VolumeId *v67; // rax
  __int64 v68; // rdx
  __int64 v69; // rbx
  VolumeId *v70; // rax
  __int64 v71; // rdx
  __int64 v72; // rdi
  __int64 v73; // rbx
  _QWORD *v74; // rax
  __int64 v75; // r14
  Dword *v76; // rsi
  __int64 v77; // rdi
  __int64 v78; // rbx
  _QWORD *v79; // rax
  int v80; // eax
  DWORD v81; // eax
  __int64 v82; // rcx
  DWORD v84; // eax
  __int64 v85; // rcx
  int v86; // [rsp+50h] [rbp-B0h]
  unsigned int v87; // [rsp+54h] [rbp-ACh]
  unsigned int v88[2]; // [rsp+58h] [rbp-A8h] BYREF
  const wchar_t *v89; // [rsp+60h] [rbp-A0h] BYREF
  int v90; // [rsp+68h] [rbp-98h]
  int v91; // [rsp+6Ch] [rbp-94h]
  const wchar_t *v92; // [rsp+70h] [rbp-90h]
  struct FrsStatus *v93; // [rsp+78h] [rbp-88h] BYREF
  int v94; // [rsp+80h] [rbp-80h] BYREF
  int v95; // [rsp+88h] [rbp-78h] BYREF
  DWORD ExitCode[2]; // [rsp+90h] [rbp-70h] BYREF
  struct Pdb *v97; // [rsp+98h] [rbp-68h] BYREF
  VolumeManager *v98; // [rsp+A0h] [rbp-60h]
  const wchar_t *v99; // [rsp+A8h] [rbp-58h] BYREF
  int v100; // [rsp+B0h] [rbp-50h]
  int v101; // [rsp+B4h] [rbp-4Ch]
  const wchar_t *v102; // [rsp+B8h] [rbp-48h]
  int v103; // [rsp+C0h] [rbp-40h] BYREF
  int v104; // [rsp+C8h] [rbp-38h] BYREF
  int v105; // [rsp+CCh] [rbp-34h] BYREF
  int v106; // [rsp+D0h] [rbp-30h] BYREF
  union _LARGE_INTEGER v107; // [rsp+D8h] [rbp-28h] BYREF
  union _LARGE_INTEGER v108; // [rsp+E0h] [rbp-20h] BYREF
  struct Db *v109; // [rsp+E8h] [rbp-18h] BYREF
  HANDLE hHandle; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v111; // [rsp+F8h] [rbp-8h] BYREF
  void **v112; // [rsp+100h] [rbp+0h] BYREF
  __int64 v113; // [rsp+108h] [rbp+8h] BYREF
  const wchar_t *v114; // [rsp+110h] [rbp+10h] BYREF
  int v115; // [rsp+118h] [rbp+18h]
  int v116; // [rsp+11Ch] [rbp+1Ch]
  const wchar_t *v117; // [rsp+120h] [rbp+20h]
  void **v118; // [rsp+128h] [rbp+28h] BYREF
  __int64 v119; // [rsp+130h] [rbp+30h] BYREF
  struct Pdb *v120; // [rsp+138h] [rbp+38h] BYREF
  void **v121; // [rsp+140h] [rbp+40h] BYREF
  struct FrsStatus *v122; // [rsp+148h] [rbp+48h] BYREF
  char v123[8]; // [rsp+150h] [rbp+50h] BYREF
  const wchar_t *v124; // [rsp+158h] [rbp+58h] BYREF
  int v125; // [rsp+160h] [rbp+60h]
  int v126; // [rsp+164h] [rbp+64h]
  const wchar_t *v127; // [rsp+168h] [rbp+68h]
  __int64 v128; // [rsp+170h] [rbp+70h] BYREF
  struct Db *v129; // [rsp+178h] [rbp+78h] BYREF
  __int64 v130; // [rsp+180h] [rbp+80h] BYREF
  char v131[8]; // [rsp+188h] [rbp+88h] BYREF
  char v132[8]; // [rsp+190h] [rbp+90h] BYREF
  void *v133; // [rsp+198h] [rbp+98h] BYREF
  char v134[8]; // [rsp+1A0h] [rbp+A0h] BYREF
  const wchar_t *v135; // [rsp+1A8h] [rbp+A8h] BYREF
  int v136; // [rsp+1B0h] [rbp+B0h]
  int v137; // [rsp+1B4h] [rbp+B4h]
  const wchar_t *v138; // [rsp+1B8h] [rbp+B8h]
  const wchar_t *v139; // [rsp+1C0h] [rbp+C0h] BYREF
  int v140; // [rsp+1C8h] [rbp+C8h]
  int v141; // [rsp+1CCh] [rbp+CCh]
  const wchar_t *v142; // [rsp+1D0h] [rbp+D0h]
  const wchar_t *v143; // [rsp+1D8h] [rbp+D8h] BYREF
  int v144; // [rsp+1E0h] [rbp+E0h]
  int v145; // [rsp+1E4h] [rbp+E4h]
  const wchar_t *v146; // [rsp+1E8h] [rbp+E8h]
  _BYTE v147[64]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int128 v148; // [rsp+230h] [rbp+130h] BYREF
  __int128 v149; // [rsp+240h] [rbp+140h] BYREF
  struct _GUID v150; // [rsp+250h] [rbp+150h] BYREF
  __int128 v151; // [rsp+260h] [rbp+160h] BYREF
  __int64 v152; // [rsp+270h] [rbp+170h]
  _BYTE v153[56]; // [rsp+278h] [rbp+178h] BYREF
  char v154[48]; // [rsp+2B0h] [rbp+1B0h] BYREF
  _BYTE v155[124]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _QWORD v156[74]; // [rsp+35Ch] [rbp+25Ch] BYREF
  void *v157[2]; // [rsp+5B0h] [rbp+4B0h] BYREF
  char v158[768]; // [rsp+5C0h] [rbp+4C0h] BYREF
  _BYTE v159[720]; // [rsp+8C0h] [rbp+7C0h] BYREF
  void *Block; // [rsp+B90h] [rbp+A90h] BYREF
  void *v161; // [rsp+EA0h] [rbp+DA0h] BYREF
  void *v162; // [rsp+11B0h] [rbp+10B0h] BYREF

  v7 = a1;
  v122 = a1;
  v103 = a4;
  v95 = a5;
  v8 = 0;
  v87 = 0;
  VolumeFromFilePath = 0;
  v93 = 0;
  hHandle = (HANDLE)-1LL;
  FilePath::FilePath((FilePath *)&v118);
  v130 = 0;
  v111 = 0;
  Config::ConfigInstance<Config::Volume>::ConfigInstance<Config::Volume>(v147);
  v107.QuadPart = 0;
  v108.QuadPart = 0;
  v109 = 0;
  v129 = 0;
  v120 = 0;
  v97 = 0;
  v106 = 0;
  v94 = 0;
  v105 = 0;
  v104 = 0;
  v86 = 0;
  v149 = 0;
  v150 = 0;
  v121 = &NtfsFileSystem::`vftable';
  IDTable::iterator::iterator((IDTable::iterator *)v157);
  IDTable::iterator::iterator((IDTable::iterator *)&v162);
  FilePath::FilePath((FilePath *)&v112);
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v124 = L"DBClone::DBExport";
    v125 = 276;
    v126 = 4;
    v127 = L"DBCL";
    v128 = *(_QWORD *)(a3 + 8) + 18LL;
    *(_QWORD *)ExitCode = *(_QWORD *)(a2 + 8) + 18LL;
    dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short const *,enum DBCloneInterface::VALIDATION_LEVEL,int>(
      (unsigned int)&v124,
      v10,
      (unsigned int)ExitCode,
      (unsigned int)&v128,
      (__int64)&v103,
      (__int64)&v95);
  }
  ScopedLock::ScopedLock((ScopedLock *)&v148, (struct ScopedCS *)DBClone::cloneCS);
  if ( *((_DWORD *)v7 + 8) != 1 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v124 = L"DBClone::DBExport";
      v125 = 295;
      v126 = 2;
      v127 = L"DBCL";
      ExitCode[0] = 1;
      dbgobj::DbgPrint<unsigned short,enum DBCloneInterface::STATE,enum DBCloneInterface::STATE>(
        &v124,
        L"Failed to process DBExport.  Incorrect state: Current state:%? expected:%?",
        (char *)v7 + 32,
        ExitCode);
    }
    CurrentThreadId = GetCurrentThreadId();
    v13 = (unsigned int *)FrsStatusList::PushNewError(
                            v12,
                            9602,
                            0,
                            3,
                            "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                            "DBClone::DBExport",
                            299,
                            CurrentThreadId,
                            0);
    if ( v13 )
    {
      v14 = GetCurrentThreadId();
      v8 = FrsStatusList::PushNewError(
             v15,
             v13[1],
             v13[2],
             *v13,
             "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
             "DBClone::DBExport",
             300,
             v14,
             v13);
    }
    ScopedLock::~ScopedLock((ScopedLock *)&v148);
    goto LABEL_191;
  }
  *((_DWORD *)v7 + 8) = 2;
  DBClone::Initialize(v7);
  ScopedLock::~ScopedLock((ScopedLock *)&v148);
  *((_DWORD *)v7 + 37) = v103;
  FilePath::operator=((char *)v7 + 176, a2);
  FilePath::operator=((char *)v7 + 192, a3);
  if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*((_QWORD *)v7 + 15) + 48LL))((__int64)v7 + 120) )
  {
    *(_QWORD *)v88 = &FrsStringImpl<unsigned short,char>::s_Empty;
    if ( !byte_140315A80 )
      _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
    FrsStringImpl<unsigned short,char>::Set(v88, *((_QWORD *)v7 + 23) + 18LL);
    VolumeTable = ConfigContext::GetVolumeTable(v16);
    VolumeFromFilePath = (struct FrsStatus *)VolumeIdTable::FindVolumeFromFilePath(VolumeTable);
    if ( VolumeFromFilePath
      && g_DebugLog
      && LODWORD(g_DebugLog[1].LockSemaphore)
      && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v89 = L"DBClone::DBExport";
      v90 = 327;
      v91 = 2;
      v92 = L"DBCL";
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,FrsStatus>(
        &v89,
        L"Failed to get volume for path: %?, status: %?",
        v88,
        VolumeFromFilePath);
    }
    FrsStringImpl<char,unsigned short>::ReleaseBody(v88);
  }
  DisplayPath = FilePath::GetDisplayPath((char *)v7 + 200);
  v19 = FilePath::GetDisplayPath((char *)v7 + 184);
  v20 = (_QWORD *)FrsGUIDToStringW(v132, (char *)v7 + 224);
  FrsEvent::Log(1073744230, *v20 + 18LL, v19, DisplayPath);
  FrsStringImpl<char,unsigned short>::ReleaseBody(v132);
  if ( !VolumeFromFilePath
    && ((*(unsigned __int8 (__fastcall **)(__int64))(*((_QWORD *)v7 + 15) + 48LL))((__int64)v7 + 120)
     || (VolumeFromFilePath = NtfsFileSystem::GetSerialNumber(
                                (NtfsFileSystem *)&v121,
                                (struct FrsStatus *)((char *)v7 + 208),
                                &v107)) == 0) )
  {
    if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*((_QWORD *)v7 + 15) + 48LL))((__int64)v7 + 120) )
    {
      FilePath::Set((FilePath *)&v118, (const unsigned __int16 *)(*((_QWORD *)v7 + 23) + 18LL));
      FilePath::Append((FilePath *)&v118, L"System Volume Information");
      FilePath::Append((FilePath *)&v118, L"DFSR");
      DBClone::GetDBFullPath(v24, (struct FilePath *)&v118, &v107, (struct FrsStatus *)((char *)v7 + 160));
      if ( g_DebugLog )
      {
        if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v135 = L"DBClone::DBExport";
          v136 = 359;
          v137 = 4;
          v138 = L"DBCL";
          v93 = (struct FrsStatus *)(*((_QWORD *)v7 + 21) + 18LL);
          *(_QWORD *)v88 = *((_QWORD *)v7 + 27) + 18LL;
          dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short *>(
            &v135,
            L"Source volume:%? DB Path:%?",
            v88,
            &v93);
        }
      }
    }
    if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*((_QWORD *)v7 + 15) + 48LL))((__int64)v7 + 120) )
    {
      VolumeFromFilePath = FrsService::ShutdownVolumeManagerForCloning(
                             *((FrsService **)v7 + 5),
                             (struct FrsStatus *)((char *)v7 + 208));
      if ( VolumeFromFilePath )
        goto LABEL_73;
      v86 = 1;
    }
    if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*((_QWORD *)v7 + 15) + 48LL))((__int64)v7 + 120) )
    {
      v98 = (VolumeManager *)operator new(0x368u);
      v25 = Config::Volume::Volume(v98);
      v130 = v25;
      Config::DWordParam::Set((Config::DWordParam *)(v25 + 624), 0x64u);
      Config::PathParam::Set((Config::PathParam *)(v25 + 496), (const unsigned __int16 *)(v119 + 18));
      Config::ConfigInstance<Config::ReplicaSet>::Set(v147, v25);
      v98 = (VolumeManager *)operator new(0x690u);
      v26 = VolumeManager::VolumeManager(
              v98,
              (struct FrsStatus *)((char *)v7 + 208),
              (struct Config::Volume *)v25,
              0,
              0,
              *(struct TaskPool **)(*((_QWORD *)v7 + 5) + 1344LL),
              0,
              0);
      ScopedRef<VolumeManager::ShutdownRestartTask>::Set(&v111, v26);
      v98 = (VolumeManager *)operator new(0x258u);
      *((_QWORD *)v7 + 40) = LdbManager::LdbManager(v98, v147, v111);
      v98 = (VolumeManager *)operator new(0x258u);
      *((_QWORD *)v7 + 41) = LdbManager::LdbManager(v98, v147, v111);
    }
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*((_QWORD *)v7 + 15) + 48LL))((__int64)v7 + 120) )
      goto LABEL_51;
    v108.QuadPart = v107.QuadPart + 1;
    DBClone::GetDBFullPath(v27, (struct FilePath *)&v118, &v108, (struct FilePath *)&v112);
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v89 = L"DBClone::DBExport";
      v90 = 421;
      v91 = 4;
      v92 = L"DBCL";
      v93 = (struct FrsStatus *)(v113 + 18);
      dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v89, L"Construct a temp DB path at:%?", &v93);
    }
    (*(void (__fastcall **)(__int64))(*((_QWORD *)v7 + 15) + 40LL))((__int64)v7 + 120);
    v28 = (const unsigned __int16 *)FilePath::GetDisplayPath(&v113);
    VolumeFromFilePath = NtfsFileSystem::ForceMakeDirectory(
                           (NtfsFileSystem *)&v121,
                           (struct FrsStatus *)((char *)v7 + 208),
                           v28,
                           1,
                           1,
                           1,
                           v29);
    if ( !VolumeFromFilePath )
    {
      VolumeFromFilePath = DBClone::CreateDBFile(v30, L"$db_export$", (struct FilePath *)&v112);
      if ( !VolumeFromFilePath )
      {
LABEL_51:
        if ( (*(unsigned __int8 (__fastcall **)(__int64))(*((_QWORD *)v7 + 15) + 48LL))((__int64)v7 + 120)
          || (VolumeFromFilePath = DBClone::PreExport(v7, (struct FilePath *)&v112, v95)) == 0 )
        {
          if ( (*(unsigned __int8 (__fastcall **)(__int64))(*((_QWORD *)v7 + 15) + 48LL))((__int64)v7 + 120) )
            goto LABEL_198;
          v31 = (*(__int64 (__fastcall **)(_QWORD, union _LARGE_INTEGER *, _QWORD, int *, int *, int *, int *, __int128 *))(**((_QWORD **)v7 + 40) + 56LL))(
                  *((_QWORD *)v7 + 40),
                  &v107,
                  0,
                  &v106,
                  &v94,
                  &v105,
                  &v104,
                  &v149);
          VolumeFromFilePath = (struct FrsStatus *)v31;
          if ( v94 )
          {
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
            {
              v89 = L"DBClone::DBExport";
              v90 = 471;
              v91 = 4;
              v92 = L"DBCL";
              v93 = (struct FrsStatus *)(*((_QWORD *)v7 + 21) + 18LL);
              *(_QWORD *)v88 = *((_QWORD *)v7 + 27) + 18LL;
              dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short *>(
                &v89,
                L"The source DB is dirty. Source volume:%? DB Path:%?",
                v88,
                &v93);
            }
            v32 = GetCurrentThreadId();
            v31 = FrsStatusList::PushNewError(
                    v33,
                    9198,
                    0,
                    3,
                    "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                    "DBClone::DBExport",
                    474,
                    v32,
                    0);
            VolumeFromFilePath = (struct FrsStatus *)v31;
          }
          if ( !v31 )
          {
LABEL_198:
            if ( ((*(unsigned __int8 (__fastcall **)(__int64))(*((_QWORD *)v7 + 15) + 48LL))((__int64)v7 + 120)
               || (VolumeFromFilePath = (struct FrsStatus *)(*(__int64 (__fastcall **)(_QWORD, union _LARGE_INTEGER *, _QWORD, int *, int *, int *, int *, __int128 *))(**((_QWORD **)v7 + 41) + 56LL))(
                                                              *((_QWORD *)v7 + 41),
                                                              &v108,
                                                              0,
                                                              &v106,
                                                              &v94,
                                                              &v105,
                                                              &v104,
                                                              &v149)) == 0)
              && ((*(unsigned __int8 (__fastcall **)(__int64))(*((_QWORD *)v7 + 15) + 48LL))((__int64)v7 + 120)
               || (VolumeFromFilePath = DBClone::CreateDBFile(
                                          v34,
                                          L"$db_update$",
                                          (struct FrsStatus *)((char *)v7 + 160))) == 0)
              && ((*(unsigned __int8 (__fastcall **)(__int64))(*((_QWORD *)v7 + 15) + 48LL))((__int64)v7 + 120)
               || (VolumeFromFilePath = DBClone::GetDBInfo(v7, 1)) == 0)
              && ((*(unsigned __int8 (__fastcall **)(__int64))(*((_QWORD *)v7 + 15) + 48LL))((__int64)v7 + 120)
               || (VolumeFromFilePath = DBClone::GetSysvolContentSet(v7, &v150)) == 0)
              && ((*(unsigned __int8 (__fastcall **)(__int64))(*((_QWORD *)v7 + 15) + 48LL))((__int64)v7 + 120)
               || (VolumeFromFilePath = DBClone::GetSessionAndBeginTransaction(
                                          *((struct LdbManager **)v7 + 41),
                                          1,
                                          0,
                                          &v129,
                                          &v97)) == 0)
              && !(*(unsigned __int8 (__fastcall **)(__int64))(*((_QWORD *)v7 + 15) + 48LL))((__int64)v7 + 120) )
            {
              if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
              {
                v89 = L"DBClone::DBExport";
                v90 = 528;
                v91 = 5;
                v92 = L"DBCL";
                dbgobj::DbgPrint<unsigned short>(&v89, L"Before getting the DB statistics.");
              }
              VolumeFromFilePath = IDTable::GetTableInfo(v97, (unsigned int *)v7 + 88);
              if ( !VolumeFromFilePath )
              {
                if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
                {
                  v89 = L"DBClone::DBExport";
                  v90 = 533;
                  v91 = 5;
                  v92 = L"DBCL";
                  dbgobj::DbgPrint<unsigned short,unsigned int>(
                    &v89,
                    L"After getting the DB statistics. Total Number of Records: %d",
                    (char *)v7 + 352);
                }
                v35 = Dword::Dword((Dword *)v154, *((_DWORD *)v7 + 88), 10);
                v36 = Dword::Dword((Dword *)v153, 0, 10);
                v37 = FilePath::GetDisplayPath((char *)v7 + 184);
                v38 = (_QWORD *)FrsGUIDToStringW(v134, (char *)v7 + 224);
                FrsEvent::Log(1073744234, *v38 + 18LL, v37, v36, v35, 0);
                FrsStringImpl<char,unsigned short>::ReleaseBody(v134);
              }
            }
          }
        }
      }
    }
  }
LABEL_73:
  if ( v129 )
  {
    VolumeFromFilePath = DbUtil::CommitTransaction(v129, VolumeFromFilePath, 0);
    (*(void (__fastcall **)(_QWORD, struct Db **))(**((_QWORD **)v7 + 41) + 64LL))(*((_QWORD *)v7 + 41), &v129);
  }
  if ( !VolumeFromFilePath
    && ((*(unsigned __int8 (__fastcall **)(__int64))(*((_QWORD *)v7 + 15) + 48LL))((__int64)v7 + 120)
     || (VolumeFromFilePath = DBClone::CSTableExport(v7, &v150)) == 0)
    && ((*(unsigned __int8 (__fastcall **)(__int64))(*((_QWORD *)v7 + 15) + 48LL))((__int64)v7 + 120)
     || (VolumeFromFilePath = DBClone::EPTableExportUpdate(v7)) == 0) )
  {
    if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*((_QWORD *)v7 + 15) + 48LL))((__int64)v7 + 120)
      && *((_DWORD *)v7 + 37) )
    {
      Thread = CreateThread(0, 0, DBClone::CloneDBExportThread, v7, 0, 0);
      hHandle = Thread;
      if ( !Thread || Thread == (HANDLE)-1LL )
      {
        v40 = GetCurrentThreadId();
        LastError = GetLastError();
        VolumeFromFilePath = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                   "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                                   LastError,
                                                   0,
                                                   1,
                                                   "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                                   "DBClone::DBExport",
                                                   603,
                                                   v40,
                                                   0);
        if ( VolumeFromFilePath )
          goto LABEL_91;
      }
      else if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v139 = L"DBClone::DBExport";
        v140 = 606;
        v141 = 4;
        v142 = L"DBCL";
        dbgobj::DbgPrint<unsigned short,void *>(&v139, L"Starting the DB validation thread. %p", &hHandle);
      }
    }
    if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*((_QWORD *)v7 + 15) + 48LL))((__int64)v7 + 120) )
      VolumeFromFilePath = DBClone::GetSessionAndBeginTransaction(*((struct LdbManager **)v7 + 40), 1, 0, &v109, &v120);
  }
LABEL_91:
  v98 = (struct FrsStatus *)((char *)v7 + 88);
  v42 = (struct Pdb *)**((_QWORD **)v7 + 11);
  v97 = v42;
  if ( !VolumeFromFilePath )
  {
    v43 = (char *)v7 + 120;
LABEL_93:
    if ( !(*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v43 + 48LL))(v43)
      && v42 != *(struct Pdb **)std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(
                                  v98,
                                  v131) )
    {
      v88[0] = 0;
      v148 = *(_OWORD *)std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<UID const,UpdateReference *>>>>::operator*(&v97);
      v151 = 0;
      v152 = 0;
      v44 = v120;
      v45 = IDTable::begin(v120, &Block, &v148, &v151);
      IDTable::iterator::operator=(v157, v45);
      operator delete[](Block);
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v89 = L"DBClone::DBExport";
        v90 = 635;
        v91 = 4;
        v92 = L"DBCL";
        dbgobj::DbgPrint<unsigned short,_GUID>(&v89, L"Starting the local DB update for csId:%?", &v148);
      }
      while ( 1 )
      {
        if ( VolumeFromFilePath
          || (*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v43 + 48LL))(v43)
          || JErrToFrsStatus::Map(*((_DWORD *)v157[0] + 7)) != 9200 )
        {
          v47 = v87;
        }
        else
        {
          v46 = IDTable::end(v44, &v161);
          v87 |= 1u;
          if ( (unsigned int)FrsTableIterator::operator!=(v157, v46) )
          {
            v48 = 1;
            goto LABEL_106;
          }
        }
        v48 = 0;
LABEL_106:
        if ( (v47 & 1) != 0 )
        {
          v87 = v47 & 0xFFFFFFFE;
          operator delete[](v161);
        }
        if ( !v48 )
          goto LABEL_127;
        ID_RECORD::ID_RECORD((ID_RECORD *)v155, (const struct ID_RECORD *)v158);
        ID_RECORD::ID_RECORD((ID_RECORD *)v159);
        v49 = g_DebugLog;
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v99 = L"DBClone::DBExport";
          v100 = 650;
          v101 = 5;
          v102 = L"DBCL";
          dbgobj::DbgPrint<unsigned short,ID_RECORD>(&v99, L"Processing ID Record: %?", v155);
          v49 = g_DebugLog;
        }
        Flags = ID_RECORD::GetFlags((ID_RECORD *)v155);
        ID_RECORD::SetFlags((ID_RECORD *)v155, Flags | 4);
        if ( (unsigned __int8)operator==(v156, 0) )
        {
          if ( v49 && LODWORD(v49[1].LockSemaphore) && SLODWORD(v49[1].OwningThread) >= 2 )
          {
            v99 = L"DBClone::DBExport";
            v100 = 671;
            v101 = 2;
            v102 = L"DBCL";
            dbgobj::DbgPrint<unsigned short,ID_RECORD>(&v99, L"Record has improper fence value: %?", v155);
          }
          v52 = GetCurrentThreadId();
          VolumeFromFilePath = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                     v53,
                                                     9198,
                                                     0,
                                                     3,
                                                     "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                                     "DBClone::DBExport",
                                                     677,
                                                     v52,
                                                     0);
LABEL_127:
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            v99 = L"DBClone::DBExport";
            v100 = 716;
            v101 = 4;
            v102 = L"DBCL";
            dbgobj::DbgPrint<unsigned short,_GUID>(&v99, L"Finished the local DB update for csId:%?", &v148);
          }
          std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,VvCompactTask *>>>,std::_Iterator_base0>::operator++(&v97);
          if ( !VolumeFromFilePath )
          {
            v42 = v97;
            goto LABEL_93;
          }
          break;
        }
        if ( (unsigned __int8)operator==(v156, 2) )
        {
          v156[0] = 3;
        }
        else if ( (unsigned __int8)operator==(v156, 1)
               && v49
               && LODWORD(v49[1].LockSemaphore)
               && SLODWORD(v49[1].OwningThread) >= v51 )
        {
          v99 = L"DBClone::DBExport";
          v100 = 697;
          v101 = v51;
          v102 = L"DBCL";
          dbgobj::DbgPrint<unsigned short,ID_RECORD>(&v99, L"Record has initial sync fence: %?", v155);
        }
        v44 = v120;
        v93 = IDTable::Update(
                v120,
                (const struct UID *)v155,
                (const struct ID_RECORD *)v155,
                1,
                (struct ID_RECORD *)v159);
        DBClone::CommitBeginTransactionOrRollBack(v109, 0, v88[0] >= 0x20, v88, &v93, 0x23F0u);
        IDTable::iterator::operator++((IDTable::iterator *)v157);
        VolumeFromFilePath = v93;
      }
    }
    v7 = v122;
  }
  if ( v109 )
  {
    VolumeFromFilePath = DbUtil::CommitTransaction(v109, VolumeFromFilePath, 0);
    (*(void (__fastcall **)(_QWORD, struct Db **))(**((_QWORD **)v7 + 40) + 64LL))(*((_QWORD *)v7 + 40), &v109);
  }
  v54 = (char *)hHandle;
  if ( (char *)hHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL && WaitForSingleObject(hHandle, 0xFFFFFFFF) )
  {
    if ( VolumeFromFilePath )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v143 = L"DBClone::DBExport";
        v144 = 739;
        v145 = 2;
        v146 = L"DBCL";
        LODWORD(v128) = GetLastError();
        dbgobj::DbgPrint<unsigned short,unsigned int>(&v143, L"WaitForSingleObject failed. Error:%d", &v128);
      }
    }
    else
    {
      v55 = GetCurrentThreadId();
      v56 = GetLastError();
      VolumeFromFilePath = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                 v57,
                                                 v56,
                                                 0,
                                                 1,
                                                 "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                                 "DBClone::DBExport",
                                                 736,
                                                 v55,
                                                 0);
    }
  }
  if ( !VolumeFromFilePath
    && !(*(unsigned __int8 (__fastcall **)(__int64))(*((_QWORD *)v7 + 15) + 48LL))((__int64)v7 + 120)
    && (unsigned __int64)(v54 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    ExitCode[0] = 0;
    if ( GetExitCodeThread(v54, ExitCode)
      || (v58 = GetCurrentThreadId(),
          v59 = GetLastError(),
          (VolumeFromFilePath = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                      v60,
                                                      v59,
                                                      0,
                                                      1,
                                                      "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                                      "DBClone::DBExport",
                                                      751,
                                                      v58,
                                                      0)) == 0) )
    {
      if ( ExitCode[0] )
      {
        v61 = GetCurrentThreadId();
        VolumeFromFilePath = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                   v62,
                                                   9603,
                                                   0,
                                                   3,
                                                   "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                                   "DBClone::DBExport",
                                                   755,
                                                   v61,
                                                   0);
      }
    }
  }
  v63 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)v7 + 40);
  if ( v63 )
  {
    (**v63)(v63, 1);
    *((_QWORD *)v7 + 40) = 0;
    if ( g_DebugLog )
    {
      if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v114 = L"DBClone::DBExport";
        v115 = 765;
        v116 = 4;
        v117 = L"DBCL";
        dbgobj::DbgPrint<unsigned short>(&v114, L"Source DB manager deleted");
      }
    }
  }
  v64 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)v7 + 41);
  if ( v64 )
  {
    (**v64)(v64, 1);
    *((_QWORD *)v7 + 41) = 0;
    if ( g_DebugLog )
    {
      if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v114 = L"DBClone::DBExport";
        v115 = 771;
        v116 = 4;
        v117 = L"DBCL";
        dbgobj::DbgPrint<unsigned short>(&v114, L"Destination DB manager deleted");
      }
    }
  }
  if ( VolumeFromFilePath
    || !(*(unsigned __int8 (__fastcall **)(__int64))(*((_QWORD *)v7 + 15) + 48LL))((__int64)v7 + 120)
    && (VolumeFromFilePath = DBClone::PostExportSuccess(v7, (struct FilePath *)&v112, v95)) != 0 )
  {
    v65 = v86;
    goto LABEL_171;
  }
  v65 = v86;
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*((_QWORD *)v7 + 15) + 48LL))((__int64)v7 + 120) || !v86 )
  {
LABEL_168:
    if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*((_QWORD *)v7 + 15) + 48LL))((__int64)v7 + 120) )
      goto LABEL_178;
LABEL_171:
    if ( !v65 )
      goto LABEL_178;
    goto LABEL_172;
  }
  v66 = *((_QWORD *)v7 + 5);
  v67 = VolumeId::VolumeId((VolumeId *)v153, (struct FrsStatus *)((char *)v7 + 208));
  VolumeFromFilePath = (struct FrsStatus *)FrsService::RestartVolumeManagerAfterCloning(v66, v68, v67);
  if ( !VolumeFromFilePath )
  {
    v65 = 0;
    goto LABEL_168;
  }
LABEL_172:
  DBClone::PostExportFailure(v7, (struct FilePath *)&v112);
  v69 = *((_QWORD *)v7 + 5);
  v70 = VolumeId::VolumeId((VolumeId *)v153, (struct FrsStatus *)((char *)v7 + 208));
  restarted = (struct FrsStatus *)FrsService::RestartVolumeManagerAfterCloning(v69, v71, v70);
  v122 = restarted;
  if ( restarted )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v114 = L"DBClone::DBExport";
      v115 = 819;
      v116 = 2;
      v117 = L"DBCL";
      dbgobj::DbgPrint<unsigned short,VolumeId,FrsStatus>(
        &v114,
        L"Failed restart. Volume:%? error:%?",
        (char *)v7 + 208,
        restarted);
    }
    CLEAR_ERROR(&v122);
  }
LABEL_178:
  if ( !(*(unsigned __int8 (__fastcall **)(__int64, __int64, __int64, struct FrsStatus *))(*((_QWORD *)v7 + 15) + 48LL))(
          (__int64)v7 + 120,
          v21,
          v22,
          restarted) )
  {
    if ( VolumeFromFilePath )
    {
      v75 = *(_QWORD *)FrsStatusString::FrsStatusString((FrsStatusString *)&v133, VolumeFromFilePath);
      v76 = Dword::Dword((Dword *)v153, *((_DWORD *)VolumeFromFilePath + 1), 10);
      v77 = FilePath::GetDisplayPath((char *)v7 + 200);
      v78 = FilePath::GetDisplayPath((char *)v7 + 184);
      v79 = (_QWORD *)FrsGUIDToStringW(v123, (char *)v7 + 224);
      FrsEvent::Log(3221227880LL, *v79 + 18LL, v78, v77, v76, v75);
      FrsStringImpl<char,unsigned short>::ReleaseBody(v123);
      operator delete[](v133);
      v54 = (char *)hHandle;
    }
    else
    {
      v72 = FilePath::GetDisplayPath((char *)v7 + 200);
      v73 = FilePath::GetDisplayPath((char *)v7 + 184);
      v74 = (_QWORD *)FrsGUIDToStringW(v123, (char *)v7 + 224);
      FrsEvent::Log(1073744226, *v74 + 18LL, v73, v72);
      FrsStringImpl<char,unsigned short>::ReleaseBody(v123);
    }
  }
  if ( (unsigned __int64)(v54 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v54);
  ScopedLock::ScopedLock((ScopedLock *)&v124, (struct ScopedCS *)DBClone::cloneCS);
  v80 = *((_DWORD *)v7 + 8);
  if ( v80 != 2 && v80 != 4 )
  {
    if ( v80 != 6 )
    {
      if ( v80 == 7 )
      {
        *((_DWORD *)v7 + 8) = 0;
      }
      else if ( !VolumeFromFilePath )
      {
        v84 = GetCurrentThreadId();
        VolumeFromFilePath = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                   v85,
                                                   9602,
                                                   0,
                                                   3,
                                                   "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                                   "DBClone::DBExport",
                                                   891,
                                                   v84,
                                                   0);
      }
      goto LABEL_189;
    }
    (*(void (__fastcall **)(__int64))(*((_QWORD *)v7 + 15) + 8LL))((__int64)v7 + 120);
    *((_DWORD *)v7 + 36) = 0;
  }
  *((_DWORD *)v7 + 8) = 1;
LABEL_189:
  ScopedLock::~ScopedLock((ScopedLock *)&v124);
  SetEvent(*((HANDLE *)v7 + 45));
  if ( VolumeFromFilePath )
  {
    v81 = GetCurrentThreadId();
    v8 = FrsStatusList::PushNewError(
           v82,
           *((unsigned int *)VolumeFromFilePath + 1),
           *((unsigned int *)VolumeFromFilePath + 2),
           *(unsigned int *)VolumeFromFilePath,
           "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
           "DBClone::DBExport",
           901,
           v81,
           VolumeFromFilePath);
  }
LABEL_191:
  v112 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v113);
  operator delete[](v162);
  operator delete[](v157[0]);
  v121 = &FileSystem::`vftable';
  Config::ConfigInstance<Config::ReplicaSet>::~ConfigInstance<Config::ReplicaSet>(v147);
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v111);
  ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v130);
  v118 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v119);
  return v8;
}

```

## disassembly

```asm
0x14002ddb0  push    rbp
0x14002ddb2  push    rbx
0x14002ddb3  push    rsi
0x14002ddb4  push    rdi
0x14002ddb5  push    r12
0x14002ddb7  push    r13
0x14002ddb9  push    r14
0x14002ddbb  push    r15
0x14002ddbd  lea     rbp, [rsp-13D8h]
0x14002ddc5  mov     eax, 14D8h
0x14002ddca  call    _alloca_probe
0x14002ddcf  sub     rsp, rax
0x14002ddd2  mov     rax, cs:__security_cookie
0x14002ddd9  xor     rax, rsp
0x14002dddc  mov     [rbp+1410h+var_50], rax
0x14002dde3  mov     rdi, r8
0x14002dde6  mov     rbx, rdx
0x14002dde9  mov     r13, rcx
0x14002ddec  mov     [rbp+1410h+var_13C8], rcx
0x14002ddf0  mov     [rbp+1410h+var_1450], r9d
0x14002ddf4  mov     eax, [rbp+1410h+arg_20]
0x14002ddfa  mov     [rbp+1410h+var_1488], eax
0x14002ddfd  xor     r15d, r15d
0x14002de00  mov     [rsp+1510h+var_14BC], r15d
0x14002de05  mov     r12d, r15d
0x14002de08  mov     [rsp+1510h+var_1498], r15
0x14002de0d  or      [rbp+1410h+hHandle], 0FFFFFFFFFFFFFFFFh
0x14002de12  lea     rcx, [rbp+1410h+var_13E8]; this
0x14002de16  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x14002de1b  nop
0x14002de1c  mov     [rbp+1410h+var_1390], r15
0x14002de23  mov     [rbp+1410h+var_1418], r15
0x14002de27  lea     rcx, [rbp+1410h+var_1320]
0x14002de2e  call    ??0?$ConfigInstance@VVolume@Config@@@Config@@QEAA@XZ; Config::ConfigInstance<Config::Volume>::ConfigInstance<Config::Volume>(void)
0x14002de33  nop
0x14002de34  mov     qword ptr [rbp+1410h+var_1438], r15
0x14002de38  mov     qword ptr [rbp+1410h+var_1430], r15
0x14002de3c  mov     [rbp+1410h+var_1428], r15
0x14002de40  mov     [rbp+1410h+var_1398], r15
0x14002de44  mov     [rbp+1410h+var_13D8], r15
0x14002de48  mov     [rbp+1410h+var_1478], r15
0x14002de4c  mov     [rbp+1410h+var_1440], r15d
0x14002de50  mov     [rbp+1410h+var_1490], r15d
0x14002de54  mov     [rbp+1410h+var_1444], r15d
0x14002de58  mov     [rbp+1410h+var_1448], r15d
0x14002de5c  mov     [rsp+1510h+var_14C0], r15d
0x14002de61  xorps   xmm0, xmm0
0x14002de64  movups  [rbp+1410h+var_12D0], xmm0
0x14002de6b  xorps   xmm1, xmm1
0x14002de6e  movups  xmmword ptr [rbp+1410h+var_12C0.Data1], xmm1
0x14002de75  lea     rax, ??_7NtfsFileSystem@@6B@; const NtfsFileSystem::`vftable'
0x14002de7c  mov     [rbp+1410h+var_13D0], rax
0x14002de80  lea     rcx, [rbp+1410h+var_F60]; this
0x14002de87  call    ??0iterator@IDTable@@QEAA@XZ; IDTable::iterator::iterator(void)
0x14002de8c  nop
0x14002de8d  lea     rcx, [rbp+1410h+var_360]; this
0x14002de94  call    ??0iterator@IDTable@@QEAA@XZ; IDTable::iterator::iterator(void)
0x14002de99  nop
0x14002de9a  lea     rcx, [rbp+1410h+var_1410]; this
0x14002de9e  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x14002dea3  nop
0x14002dea4  lea     ecx, [r15+4]
0x14002dea8  lea     rsi, aDbcloneDbexpor_0; "DBClone::DBExport"
0x14002deaf  lea     r14, aDbcl; "DBCL"
0x14002deb6  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14002debd  test    rax, rax
0x14002dec0  jz      short loc_14002DF1A
0x14002dec2  cmp     [rax+40h], r15d
0x14002dec6  jz      short loc_14002DF1A
0x14002dec8  cmp     [rax+38h], ecx
0x14002decb  jl      short loc_14002DF1A
0x14002decd  mov     [rbp+1410h+var_13B8], rsi
0x14002ded1  mov     [rbp+1410h+var_13B0], 114h
0x14002ded8  mov     [rbp+1410h+var_13AC], ecx
0x14002dedb  mov     [rbp+1410h+var_13A8], r14
0x14002dedf  mov     rax, [rdi+8]
0x14002dee3  add     rax, 12h
0x14002dee7  mov     [rbp+1410h+var_13A0], rax
0x14002deeb  mov     rax, [rbx+8]
0x14002deef  add     rax, 12h
0x14002def3  mov     qword ptr [rbp+1410h+ExitCode], rax
0x14002def7  lea     rax, [rbp+1410h+var_1488]
0x14002defb  mov     [rsp+1510h+lpThreadId], rax
0x14002df00  lea     rax, [rbp+1410h+var_1450]
0x14002df04  mov     qword ptr [rsp+1510h+dwCreationFlags], rax
0x14002df09  lea     r9, [rbp+1410h+var_13A0]
0x14002df0d  lea     r8, [rbp+1410h+ExitCode]
0x14002df11  lea     rcx, [rbp+1410h+var_13B8]
0x14002df15  call    ??$DbgPrint@GPEBGPEBGW4VALIDATION_LEVEL@DBCloneInterface@@H@dbgobj@@QEAA_KPEBGAEBQEBG1AEBW4VALIDATION_LEVEL@DBCloneInterface@@AEBH@Z; dbgobj::DbgPrint<ushort,ushort const *,ushort const *,DBCloneInterface::VALIDATION_LEVEL,int>(ushort const *,ushort const * const &,ushort const * const &,DBCloneInterface::VALIDATION_LEVEL const &,int const &)
0x14002df1a  lea     rdx, ?cloneCS@DBClone@@2VScopedCS@@A; struct ScopedCS *
0x14002df21  lea     rcx, [rbp+1410h+var_12E0]; this
0x14002df28  call    ??0ScopedLock@@QEAA@AEAVScopedCS@@@Z; ScopedLock::ScopedLock(ScopedCS &)
0x14002df2d  nop
0x14002df2e  lea     rcx, [r13+20h]
0x14002df32  cmp     dword ptr [rcx], 1
0x14002df35  jz      loc_14002E021
0x14002df3b  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14002df42  test    rax, rax
0x14002df45  jz      short loc_14002DF87
0x14002df47  cmp     [rax+40h], r15d
0x14002df4b  jz      short loc_14002DF87
0x14002df4d  cmp     dword ptr [rax+38h], 2
0x14002df51  jl      short loc_14002DF87
0x14002df53  mov     [rbp+1410h+var_13B8], rsi
0x14002df57  mov     [rbp+1410h+var_13B0], 127h
0x14002df5e  mov     [rbp+1410h+var_13AC], 2
0x14002df65  mov     [rbp+1410h+var_13A8], r14
0x14002df69  mov     [rbp+1410h+ExitCode], 1
0x14002df70  lea     r9, [rbp+1410h+ExitCode]
0x14002df74  mov     r8, rcx
0x14002df77  lea     rdx, aFailedToProces_38; "Failed to process DBExport.  Incorrect "...
0x14002df7e  lea     rcx, [rbp+1410h+var_13B8]
0x14002df82  call    ??$DbgPrint@GW4STATE@DBCloneInterface@@W412@@dbgobj@@QEAA_KPEBGAEBW4STATE@DBCloneInterface@@1@Z; dbgobj::DbgPrint<ushort,DBCloneInterface::STATE,DBCloneInterface::STATE>(ushort const *,DBCloneInterface::STATE const &,DBCloneInterface::STATE const &)
0x14002df87  call    cs:__imp_GetCurrentThreadId
0x14002df8e  nop     dword ptr [rax+rax+00h]
0x14002df93  mov     [rsp+1510h+var_14D0], r15
0x14002df98  mov     dword ptr [rsp+1510h+var_14D8], eax
0x14002df9c  mov     dword ptr [rsp+1510h+var_14E0], 12Bh
0x14002dfa4  lea     rdi, aDbcloneDbexpor; "DBClone::DBExport"
0x14002dfab  mov     [rsp+1510h+lpThreadId], rdi
0x14002dfb0  lea     rsi, aBaseFsRemotefs_5; "base\\fs\\remotefs\\frs\\src\\main\\dbc"...
0x14002dfb7  mov     qword ptr [rsp+1510h+dwCreationFlags], rsi
0x14002dfbc  mov     r9d, 3
0x14002dfc2  xor     r8d, r8d
0x14002dfc5  mov     edx, 2582h
0x14002dfca  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14002dfcf  mov     rbx, rax
0x14002dfd2  test    rax, rax
0x14002dfd5  jz      short loc_14002E010
0x14002dfd7  call    cs:__imp_GetCurrentThreadId
0x14002dfde  nop     dword ptr [rax+rax+00h]
0x14002dfe3  mov     [rsp+1510h+var_14D0], rbx
0x14002dfe8  mov     dword ptr [rsp+1510h+var_14D8], eax
0x14002dfec  mov     dword ptr [rsp+1510h+var_14E0], 12Ch
0x14002dff4  mov     [rsp+1510h+lpThreadId], rdi
0x14002dff9  mov     qword ptr [rsp+1510h+dwCreationFlags], rsi
0x14002dffe  mov     r9d, [rbx]
0x14002e001  mov     r8d, [rbx+8]
0x14002e005  mov     edx, [rbx+4]
0x14002e008  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14002e00d  mov     r15, rax
0x14002e010  lea     rcx, [rbp+1410h+var_12E0]; this
0x14002e017  call    ??1ScopedLock@@QEAA@XZ; ScopedLock::~ScopedLock(void)
0x14002e01c  jmp     loc_14002F522
0x14002e021  mov     r14d, 2
0x14002e027  mov     [rcx], r14d
0x14002e02a  mov     rcx, r13; this
0x14002e02d  call    ?Initialize@DBClone@@AEAAXXZ; DBClone::Initialize(void)
0x14002e032  nop
0x14002e033  lea     rcx, [rbp+1410h+var_12E0]; this
0x14002e03a  call    ??1ScopedLock@@QEAA@XZ; ScopedLock::~ScopedLock(void)
0x14002e03f  mov     eax, [rbp+1410h+var_1450]
0x14002e042  mov     [r13+94h], eax
0x14002e049  lea     rcx, [r13+0B0h]
0x14002e050  mov     rdx, rbx
0x14002e053  call    ??4FilePath@@QEAAAEAV0@AEBV0@@Z; FilePath::operator=(FilePath const &)
0x14002e058  lea     rcx, [r13+0C0h]
0x14002e05f  mov     rdx, rdi
0x14002e062  call    ??4FilePath@@QEAAAEAV0@AEBV0@@Z; FilePath::operator=(FilePath const &)
0x14002e067  lea     rcx, [r13+78h]
0x14002e06b  mov     rax, [rcx]
0x14002e06e  mov     rax, [rax+30h]
0x14002e072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e077  test    al, al
0x14002e079  jnz     loc_14002E12B
0x14002e07f  lea     rax, ?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x14002e086  mov     qword ptr [rsp+1510h+var_14B8], rax
0x14002e08b  cmp     cs:byte_140315A80, r15b
0x14002e092  jnz     short loc_14002E09B
0x14002e094  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x14002e09b  mov     rdx, [r13+0B8h]
0x14002e0a2  add     rdx, 12h
0x14002e0a6  lea     rcx, [rsp+1510h+var_14B8]
0x14002e0ab  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x14002e0b0  call    ?GetVolumeTable@ConfigContext@@QEAAPEAVVolumeIdTable@@XZ; ConfigContext::GetVolumeTable(void)
0x14002e0b5  lea     r8, [r13+0D0h]
0x14002e0bc  lea     rdx, [rsp+1510h+var_14B8]
0x14002e0c1  mov     rcx, rax; this
0x14002e0c4  call    ?FindVolumeFromFilePath@VolumeIdTable@@QEAAPEAVFrsStatus@@AEBV?$FrsStringImpl@GD@@AEAVVolumeId@@@Z; VolumeIdTable::FindVolumeFromFilePath(FrsStringImpl<ushort,char> const &,VolumeId &)
0x14002e0c9  mov     r12, rax
0x14002e0cc  test    rax, rax
0x14002e0cf  jz      short loc_14002E121
0x14002e0d1  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14002e0d8  test    rax, rax
0x14002e0db  jz      short loc_14002E121
0x14002e0dd  cmp     [rax+40h], r15d
0x14002e0e1  jz      short loc_14002E121
0x14002e0e3  cmp     [rax+38h], r14d
0x14002e0e7  jl      short loc_14002E121
0x14002e0e9  mov     [rsp+1510h+var_14B0], rsi
0x14002e0ee  mov     [rsp+1510h+var_14A8], 147h
0x14002e0f6  mov     [rsp+1510h+var_14A4], r14d
0x14002e0fb  lea     rax, aDbcl; "DBCL"
0x14002e102  mov     [rsp+1510h+var_14A0], rax
0x14002e107  mov     r9, r12
0x14002e10a  lea     r8, [rsp+1510h+var_14B8]
0x14002e10f  lea     rdx, aFailedToGetVol_0; "Failed to get volume for path: %?, stat"...
0x14002e116  lea     rcx, [rsp+1510h+var_14B0]
0x14002e11b  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@VFrsStatus@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@AEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>,FrsStatus>(ushort const *,FrsStringImpl<ushort,char> const &,FrsStatus const &)
0x14002e120  nop
0x14002e121  lea     rcx, [rsp+1510h+var_14B8]
0x14002e126  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x14002e12b  lea     rcx, [r13+0C8h]
0x14002e132  call    ?GetDisplayPath@FilePath@@SAPEBGAEBV?$FrsStringImpl@GD@@@Z; FilePath::GetDisplayPath(FrsStringImpl<ushort,char> const &)
0x14002e137  mov     rdi, rax
0x14002e13a  lea     rsi, [r13+0B8h]
0x14002e141  mov     rcx, rsi
0x14002e144  call    ?GetDisplayPath@FilePath@@SAPEBGAEBV?$FrsStringImpl@GD@@@Z; FilePath::GetDisplayPath(FrsStringImpl<ushort,char> const &)
0x14002e149  mov     rbx, rax
0x14002e14c  lea     rdx, [r13+0E0h]
0x14002e153  lea     rcx, [rbp+1410h+var_1380]
0x14002e15a  call    ?FrsGUIDToStringW@@YA?AV?$FrsStringImpl@GD@@AEBU_GUID@@@Z; FrsGUIDToStringW(_GUID const &)
0x14002e15f  nop
0x14002e160  mov     rdx, [rax]
0x14002e163  add     rdx, 12h
0x14002e167  mov     r9, rdi
0x14002e16a  mov     r8, rbx
0x14002e16d  mov     ecx, 40000966h
0x14002e172  call    ?Log@FrsEvent@@SAXW4FrsEventsEnum3@@PEBG11@Z; FrsEvent::Log(FrsEventsEnum3,ushort const *,ushort const *,ushort const *)
0x14002e177  nop
0x14002e178  lea     rcx, [rbp+1410h+var_1380]
0x14002e17f  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x14002e184  lea     rdi, aDbcloneDbexpor; "DBClone::DBExport"
0x14002e18b  lea     rbx, aBaseFsRemotefs_5; "base\\fs\\remotefs\\frs\\src\\main\\dbc"...
0x14002e192  test    r12, r12
0x14002e195  jnz     loc_14002E8F2
0x14002e19b  mov     rax, [r13+78h]
0x14002e19f  lea     rcx, [r13+78h]
0x14002e1a3  mov     rax, [rax+30h]
0x14002e1a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e1ac  test    al, al
0x14002e1ae  jnz     short loc_14002E1D0
0x14002e1b0  lea     rdx, [r13+0D0h]; struct VolumeId *
0x14002e1b7  lea     r8, [rbp+1410h+var_1438]; union _LARGE_INTEGER *
0x14002e1bb  lea     rcx, [rbp+1410h+var_13D0]; this
0x14002e1bf  call    ?GetSerialNumber@NtfsFileSystem@@UEAAPEAVFrsStatus@@AEBVVolumeId@@AEAT_LARGE_INTEGER@@@Z; NtfsFileSystem::GetSerialNumber(VolumeId const &,_LARGE_INTEGER &)
0x14002e1c4  mov     r12, rax
0x14002e1c7  test    rax, rax
0x14002e1ca  jnz     loc_14002E8F2
0x14002e1d0  mov     rax, [r13+78h]
0x14002e1d4  lea     rcx, [r13+78h]
0x14002e1d8  mov     rax, [rax+30h]
0x14002e1dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e1e1  test    al, al
0x14002e1e3  jnz     loc_14002E2B4
0x14002e1e9  mov     rdx, [rsi]
0x14002e1ec  add     rdx, 12h; unsigned __int16 *
0x14002e1f0  lea     rcx, [rbp+1410h+var_13E8]; this
0x14002e1f4  call    ?Set@FilePath@@QEAAXPEBG@Z; FilePath::Set(ushort const *)
0x14002e1f9  lea     rdx, aSystemVolumeIn_0; "System Volume Information"
0x14002e200  lea     rcx, [rbp+1410h+var_13E8]; this
0x14002e204  call    ?Append@FilePath@@QEAAXPEBG@Z; FilePath::Append(ushort const *)
0x14002e209  lea     rdx, SourceName; "DFSR"
0x14002e210  lea     rcx, [rbp+1410h+var_13E8]; this
0x14002e214  call    ?Append@FilePath@@QEAAXPEBG@Z; FilePath::Append(ushort const *)
0x14002e219  lea     r9, [r13+0A0h]; struct FilePath *
0x14002e220  lea     r8, [rbp+1410h+var_1438]; union _LARGE_INTEGER *
0x14002e224  lea     rdx, [rbp+1410h+var_13E8]; struct FilePath *
0x14002e228  call    ?GetDBFullPath@DBClone@@AEAAXAEAVFilePath@@AEBT_LARGE_INTEGER@@0@Z; DBClone::GetDBFullPath(FilePath &,_LARGE_INTEGER const &,FilePath &)
0x14002e22d  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14002e234  mov     esi, 4
0x14002e239  test    rax, rax
0x14002e23c  jz      short loc_14002E2B9
0x14002e23e  cmp     [rax+40h], r15d
0x14002e242  jz      short loc_14002E2B9
0x14002e244  cmp     [rax+38h], esi
0x14002e247  jl      short loc_14002E2B9
0x14002e249  lea     rax, aDbcloneDbexpor_0; "DBClone::DBExport"
0x14002e250  mov     [rbp+1410h+var_1368], rax
0x14002e257  mov     [rbp+1410h+var_1360], 167h
0x14002e261  mov     [rbp+1410h+var_135C], esi
0x14002e267  lea     rax, aDbcl; "DBCL"
0x14002e26e  mov     [rbp+1410h+var_1358], rax
0x14002e275  mov     rax, [r13+0A8h]
0x14002e27c  add     rax, 12h
0x14002e280  mov     [rsp+1510h+var_1498], rax
0x14002e285  mov     rax, [r13+0D8h]
0x14002e28c  add     rax, 12h
0x14002e290  mov     qword ptr [rsp+1510h+var_14B8], rax
0x14002e295  lea     r9, [rsp+1510h+var_1498]
0x14002e29a  lea     r8, [rsp+1510h+var_14B8]
0x14002e29f  lea     rdx, aSourceVolumeDb; "Source volume:%? DB Path:%?"
0x14002e2a6  lea     rcx, [rbp+1410h+var_1368]
0x14002e2ad  call    ??$DbgPrint@GPEBGPEAG@dbgobj@@QEAA_KPEBGAEBQEBGAEBQEAG@Z; dbgobj::DbgPrint<ushort,ushort const *,ushort *>(ushort const *,ushort const * const &,ushort * const &)
0x14002e2b2  jmp     short loc_14002E2B9
0x14002e2b4  mov     esi, 4
0x14002e2b9  mov     rax, [r13+78h]
0x14002e2bd  lea     rcx, [r13+78h]
0x14002e2c1  mov     rax, [rax+30h]
0x14002e2c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e2ca  test    al, al
0x14002e2cc  jnz     short loc_14002E2F2
0x14002e2ce  lea     rdx, [r13+0D0h]; struct VolumeId *
0x14002e2d5  mov     rcx, [r13+28h]; this
0x14002e2d9  call    ?ShutdownVolumeManagerForCloning@FrsService@@QEAAPEAVFrsStatus@@AEAVVolumeId@@@Z; FrsService::ShutdownVolumeManagerForCloning(VolumeId &)
0x14002e2de  mov     r12, rax
0x14002e2e1  test    rax, rax
0x14002e2e4  jnz     loc_14002E8F2
0x14002e2ea  mov     [rsp+1510h+var_14C0], 1
0x14002e2f2  mov     rax, [r13+78h]
  ... truncated ...
```
