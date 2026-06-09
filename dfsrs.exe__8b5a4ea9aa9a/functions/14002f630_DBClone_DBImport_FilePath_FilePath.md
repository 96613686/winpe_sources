# DBClone::DBImport(FilePath &,FilePath &)

- ea: `0x14002f630`
- end: `0x140030d9f`
- name: `?DBImport@DBClone@@UEAAPEAVFrsStatus@@AEAVFilePath@@0@Z`
- size: `5999`
- prototype: `struct FrsStatus *__fastcall(DBClone *__hidden this, struct FilePath *, struct FilePath *)`
- caller_count: `0`
- callee_count: `66`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, installer_update`

## callees

- `0x1400036a0`
- `0x1400036d0`
- `0x1400046cc`
- `0x14000c910`
- `0x14000cd1c`
- `0x14000d980`
- `0x14000daa0`
- `0x14000dcc0`
- `0x14000ee94`
- `0x140014df4`
- `0x140019358`
- `0x14001d960`
- `0x1400248f4`
- `0x140029514`
- `0x14002a97c`
- `0x14002aa34`
- `0x14002ab94`
- `0x14002ac54`
- `0x14002ad08`
- `0x14002adc0`
- `0x14002be54`
- `0x14002c2bc`
- `0x14002c2f4`
- `0x14002cf7c`
- `0x14002d6bc`
- `0x14002d968`
- `0x14002f630`
- `0x1400310b0`
- `0x14003126c`
- `0x140031340`
- `0x140032a14`
- `0x140034e28`
- `0x140034ef4`
- `0x140035378`
- `0x140035edc`
- `0x1400360cc`
- `0x140036bd8`
- `0x140037058`
- `0x1400370bc`
- `0x140037180`
- `0x140048b44`
- `0x140048c10`
- `0x14007d188`
- `0x140089730`
- `0x140089ae4`
- `0x14008c050`
- `0x1400aef70`
- `0x1400afa10`
- `0x1400f3af0`
- `0x1401af7c0`

## import_xrefs

- `KERNEL32!FindFirstFileW` at `0x14002fbe3`
- `KERNEL32!FindFirstFileW` at `0x14002fc21`
- `KERNEL32!FindFirstFileW` at `0x14002fc42`
- `KERNEL32!FindFirstFileW` at `0x14002fbe3`
- `KERNEL32!FindFirstFileW` at `0x14002fc21`
- `KERNEL32!FindFirstFileW` at `0x14002fc42`
- `KERNEL32!FindClose` at `0x14002fc03`
- `KERNEL32!FindClose` at `0x14002fc62`
- `KERNEL32!FindClose` at `0x14002fc03`
- `KERNEL32!FindClose` at `0x14002fc62`
- `KERNEL32!CopyFileExW` at `0x140030184`
- `KERNEL32!CopyFileExW` at `0x140030184`
- `KERNEL32!GetLastError` at `0x1400301a6`
- `KERNEL32!GetLastError` at `0x1400301a6`
- `KERNEL32!SetEvent` at `0x140030c4f`
- `KERNEL32!SetEvent` at `0x140030c4f`
- `KERNEL32!GetCurrentThreadId` at `0x14002f7db`
- `KERNEL32!GetCurrentThreadId` at `0x14002f82b`
- `KERNEL32!GetCurrentThreadId` at `0x14002fd05`
- `KERNEL32!GetCurrentThreadId` at `0x140030198`
- `KERNEL32!GetCurrentThreadId` at `0x14003051e`
- `KERNEL32!GetCurrentThreadId` at `0x14003097b`
- `KERNEL32!GetCurrentThreadId` at `0x140030a34`
- `KERNEL32!GetCurrentThreadId` at `0x140030c60`
- `KERNEL32!GetCurrentThreadId` at `0x140030d4f`
- `KERNEL32!GetCurrentThreadId` at `0x14002f7db`
- `KERNEL32!GetCurrentThreadId` at `0x14002f82b`
- `KERNEL32!GetCurrentThreadId` at `0x14002fd05`
- `KERNEL32!GetCurrentThreadId` at `0x140030198`
- `KERNEL32!GetCurrentThreadId` at `0x14003051e`
- `KERNEL32!GetCurrentThreadId` at `0x14003097b`
- `KERNEL32!GetCurrentThreadId` at `0x140030a34`
- `KERNEL32!GetCurrentThreadId` at `0x140030c60`
- `KERNEL32!GetCurrentThreadId` at `0x140030d4f`

## string_xrefs

- `0x140030627`: `Source DB manager deleted`
- `0x140030694`: `Destination DB manager deleted`
- `0x14002fa45`: `Destination volume:%? DB Path:%?`
- `0x14002fab2`: `Create temp DB path:%?`
- `0x14002fcf4`: `This is not a clean volume. Database path exists:%? or temp DB path exists:%?`
- `0x14002fded`: `Failed to create volume's '\System Volume Information' directory. volPath:%?`
- `0x14002fe73`: `Create DFSR path:%?`
- `0x14002ff49`: `Create DB path:%?`
- `0x14003025b`: `Failed to copy the master DB file from:%? to:%? error:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
struct FrsStatus *__fastcall DBClone::DBImport(DBClone *this, struct FilePath *a2, struct FilePath *a3)
{
  __int64 v6; // r15
  struct FrsStatus *VolumeId; // r12
  __int64 v8; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v10; // rcx
  unsigned int *v11; // rbx
  DWORD v12; // eax
  __int64 v13; // rcx
  char *v14; // r14
  __int64 DisplayPath; // rsi
  __int64 v16; // rdi
  _QWORD *v17; // rax
  DBClone *v18; // rcx
  DBClone *v19; // rcx
  __int64 v20; // rdi
  char v21; // al
  __int64 v22; // r14
  __int64 v23; // rdx
  char *FirstFileW; // rax
  char *v25; // rax
  DWORD v26; // eax
  __int64 v27; // rcx
  const struct Win32FilePath *v28; // rdx
  const unsigned __int16 *v29; // rax
  const volatile int *v30; // r8
  const unsigned __int16 *v31; // rax
  const volatile int *v32; // r8
  DBClone *v33; // rcx
  const unsigned __int16 *v34; // rax
  const volatile int *v35; // r8
  DBClone *v36; // rcx
  VolumeManager *v37; // r14
  DWORD v38; // edi
  DWORD LastError; // eax
  VolumeManager *v40; // rax
  DWORD v41; // eax
  __int64 v42; // rcx
  __int64 v43; // rdx
  void (__fastcall ***v44)(_QWORD, __int64); // rcx
  void (__fastcall ***v45)(_QWORD, __int64); // rcx
  __int64 v46; // rdi
  __int64 v47; // rbx
  _QWORD *v48; // rax
  int v49; // edx
  DWORD v50; // eax
  __int64 v51; // rcx
  DWORD v52; // eax
  __int64 v53; // rcx
  int v54; // edx
  __int64 v55; // r14
  Dword *v56; // rsi
  __int64 v57; // rdi
  __int64 v58; // rbx
  _QWORD *v59; // rax
  int v60; // eax
  DWORD v61; // eax
  __int64 v62; // rcx
  DWORD v64; // eax
  __int64 v65; // rcx
  VolumeManager *v66; // [rsp+50h] [rbp-B0h] BYREF
  void **v67; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v68; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v69; // [rsp+68h] [rbp-98h]
  __int16 v70; // [rsp+70h] [rbp-90h] BYREF
  __int64 v71; // [rsp+78h] [rbp-88h] BYREF
  int v72; // [rsp+80h] [rbp-80h] BYREF
  int v73; // [rsp+84h] [rbp-7Ch]
  union _LARGE_INTEGER v74; // [rsp+88h] [rbp-78h] BYREF
  int v75; // [rsp+90h] [rbp-70h] BYREF
  int v76; // [rsp+94h] [rbp-6Ch] BYREF
  int v77; // [rsp+98h] [rbp-68h] BYREF
  int v78; // [rsp+9Ch] [rbp-64h] BYREF
  void **v79; // [rsp+A0h] [rbp-60h] BYREF
  void *Block; // [rsp+A8h] [rbp-58h] BYREF
  void **v81; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v82; // [rsp+B8h] [rbp-48h] BYREF
  void **v83; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v84; // [rsp+C8h] [rbp-38h] BYREF
  void **v85; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v86; // [rsp+D8h] [rbp-28h] BYREF
  const wchar_t *v87; // [rsp+E0h] [rbp-20h]
  union _LARGE_INTEGER v88; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v89; // [rsp+F0h] [rbp-10h] BYREF
  void **v90; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v91; // [rsp+100h] [rbp+0h] BYREF
  __int64 v92; // [rsp+108h] [rbp+8h] BYREF
  const wchar_t *v93; // [rsp+110h] [rbp+10h] BYREF
  int v94; // [rsp+118h] [rbp+18h]
  int v95; // [rsp+11Ch] [rbp+1Ch]
  const wchar_t *v96; // [rsp+120h] [rbp+20h]
  const wchar_t *v97; // [rsp+128h] [rbp+28h] BYREF
  int v98; // [rsp+130h] [rbp+30h]
  int v99; // [rsp+134h] [rbp+34h]
  const wchar_t *v100; // [rsp+138h] [rbp+38h]
  const wchar_t *v101; // [rsp+140h] [rbp+40h] BYREF
  int v102; // [rsp+148h] [rbp+48h]
  int v103; // [rsp+14Ch] [rbp+4Ch]
  const wchar_t *v104; // [rsp+150h] [rbp+50h]
  _BYTE v105[64]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v106[128]; // [rsp+1A0h] [rbp+A0h] BYREF
  const wchar_t *v107; // [rsp+220h] [rbp+120h] BYREF
  int v108; // [rsp+228h] [rbp+128h]
  int v109; // [rsp+22Ch] [rbp+12Ch]
  const wchar_t *v110; // [rsp+230h] [rbp+130h]
  USN_JOURNAL_DATA_V1 v111; // [rsp+250h] [rbp+150h] BYREF
  USN_JOURNAL_DATA_V1 v112; // [rsp+290h] [rbp+190h] BYREF
  __int128 v113; // [rsp+2D0h] [rbp+1D0h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+2E0h] [rbp+1E0h] BYREF

  v6 = 0;
  VolumeId = 0;
  FilePath::FilePath((FilePath *)&v83);
  FilePath::FilePath((FilePath *)&v81);
  Config::ConfigInstance<Config::Volume>::ConfigInstance<Config::Volume>(v105);
  v8 = 0;
  v92 = 0;
  v89 = 0;
  v74.QuadPart = 0;
  v88.QuadPart = 0;
  v78 = 0;
  v77 = 0;
  v76 = 0;
  v75 = 0;
  v73 = 0;
  v72 = 0;
  Win32FilePath::Win32FilePath((Win32FilePath *)&v90);
  v113 = 0;
  v79 = &NtfsFileSystem::`vftable';
  memset_0(&v111, 0, sizeof(v111));
  ChangeJournal::ChangeJournal((ChangeJournal *)v106);
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v67 = (void **)L"DBClone::DBImport";
    v68 = 0x4000003B7LL;
    v69 = L"DBCL";
    v71 = *((_QWORD *)a3 + 1) + 18LL;
    Block = (void *)(*((_QWORD *)a2 + 1) + 18LL);
    dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short *>(
      &v67,
      L"Starting DBImport. Source:%? Destination:%?",
      &Block,
      &v71);
  }
  ScopedLock::ScopedLock((ScopedLock *)&v67, (struct ScopedCS *)DBClone::cloneCS);
  if ( *((_DWORD *)this + 8) != 1 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v85 = (void **)L"DBClone::DBImport";
      v86 = 0x2000003C2LL;
      v87 = L"DBCL";
      v72 = 1;
      dbgobj::DbgPrint<unsigned short,enum DBCloneInterface::STATE,enum DBCloneInterface::STATE>(
        &v85,
        L"Failed to process DBImport.  Incorrect state: Current state:%? expected:%?",
        (char *)this + 32,
        &v72);
    }
    CurrentThreadId = GetCurrentThreadId();
    v11 = (unsigned int *)FrsStatusList::PushNewError(
                            v10,
                            9602,
                            0,
                            3,
                            "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                            "DBClone::DBImport",
                            966,
                            CurrentThreadId,
                            0);
    if ( v11 )
    {
      v12 = GetCurrentThreadId();
      v6 = FrsStatusList::PushNewError(
             v13,
             v11[1],
             v11[2],
             *v11,
             "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
             "DBClone::DBImport",
             967,
             v12,
             v11);
    }
    ScopedLock::~ScopedLock((ScopedLock *)&v67);
    goto LABEL_160;
  }
  *((_DWORD *)this + 8) = 3;
  DBClone::Initialize(this);
  ScopedLock::~ScopedLock((ScopedLock *)&v67);
  FilePath::operator=((char *)this + 176, a2);
  FilePath::operator=((char *)this + 192, a3);
  v14 = (char *)this + 120;
  if ( !(*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120) )
  {
    VolumeId = Win32FilePath::Set((Win32FilePath *)&v90, (const unsigned __int16 *)(*((_QWORD *)this + 25) + 18LL));
    if ( !VolumeId )
      VolumeId = Win32FilePath::GetVolumeId((Win32FilePath *)&v90, (DBClone *)((char *)this + 264));
  }
  DisplayPath = FilePath::GetDisplayPath((char *)this + 184);
  v16 = FilePath::GetDisplayPath((char *)this + 200);
  v17 = (_QWORD *)FrsGUIDToStringW(&Block, (char *)this + 280);
  FrsEvent::Log(1073744236, *v17 + 18LL, v16, DisplayPath);
  FrsStringImpl<char,unsigned short>::ReleaseBody(&Block);
  if ( !VolumeId
    && ((*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v14 + 48LL))((char *)this + 120)
     || (VolumeId = NtfsFileSystem::GetSerialNumber((NtfsFileSystem *)&v79, (DBClone *)((char *)this + 264), &v74)) == 0) )
  {
    if ( (*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v14 + 48LL))((char *)this + 120) )
      goto LABEL_28;
    FilePath::Set((FilePath *)&v83, (const unsigned __int16 *)(*((_QWORD *)this + 25) + 18LL));
    FilePath::Append((FilePath *)&v83, L"System Volume Information");
    FilePath::Append((FilePath *)&v83, L"DFSR");
    DBClone::GetDBFullPath(v18, (struct FilePath *)&v83, &v74, (DBClone *)((char *)this + 160));
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v67 = (void **)L"DBClone::DBImport";
      v68 = 0x400000404LL;
      v69 = L"DBCL";
      v71 = *((_QWORD *)this + 21) + 18LL;
      v66 = (VolumeManager *)(*((_QWORD *)this + 34) + 18LL);
      dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short *>(
        &v67,
        L"Destination volume:%? DB Path:%?",
        &v66,
        &v71);
    }
    v88.QuadPart = v74.QuadPart - 1;
    DBClone::GetDBFullPath(v19, (struct FilePath *)&v83, &v88, (struct FilePath *)&v81);
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v93 = L"DBClone::DBImport";
      v94 = 1038;
      v95 = 4;
      v96 = L"DBCL";
      v20 = v82;
      v66 = (VolumeManager *)(v82 + 18);
      dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v93, L"Create temp DB path:%?", &v66);
    }
    else
    {
LABEL_28:
      v20 = v82;
    }
    v21 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v14 + 48LL))((char *)this + 120);
    v22 = v84;
    if ( !v21 )
    {
      v66 = (VolumeManager *)operator new(0x368u);
      v8 = Config::Volume::Volume(v66);
      v92 = v8;
      Config::DWordParam::Set((Config::DWordParam *)(v8 + 624), 0x64u);
      Config::PathParam::Set((Config::PathParam *)(v8 + 496), (const unsigned __int16 *)(v22 + 18));
      Config::ConfigInstance<Config::ReplicaSet>::Set(v105, v8);
      VolumeId = (struct FrsStatus *)ChangeJournal::Query(v106, (char *)this + 264, v105, &v111);
      if ( VolumeId )
        goto LABEL_105;
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v97 = L"DBClone::DBImport";
        v98 = 1064;
        v99 = 4;
        v100 = L"DBCL";
        dbgobj::DbgPrint<unsigned short,unsigned __int64,__int64>(&v97, v23, &v111, &v111.NextUsn);
      }
    }
    if ( !(*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120) )
    {
      memset_0(&FindFileData, 0, sizeof(FindFileData));
      FirstFileW = (char *)FindFirstFileW((LPCWSTR)(v22 + 18), &FindFileData);
      if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        v72 = 1;
        FindClose(FirstFileW);
      }
      v25 = (char *)FindFirstFileW((LPCWSTR)(*((_QWORD *)this + 21) + 18LL), &FindFileData);
      if ( (unsigned __int64)(v25 - 1) <= 0xFFFFFFFFFFFFFFFDuLL
        || (v25 = (char *)FindFirstFileW((LPCWSTR)(v20 + 18), &FindFileData),
            (unsigned __int64)(v25 - 1) <= 0xFFFFFFFFFFFFFFFDuLL) )
      {
        v73 = 1;
        FindClose(v25);
      }
    }
    if ( (*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120) || !v73 )
      goto LABEL_167;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v67 = (void **)L"DBClone::DBImport";
      v68 = 0x200000462LL;
      v69 = L"DBCL";
      v66 = (VolumeManager *)(v20 + 18);
      v71 = *((_QWORD *)this + 21) + 18LL;
      dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short *>(
        &v67,
        L"This is not a clean volume. Database path exists:%? or temp DB path exists:%?",
        &v71,
        &v66);
    }
    v26 = GetCurrentThreadId();
    VolumeId = (struct FrsStatus *)FrsStatusList::PushNewError(
                                     v27,
                                     9605,
                                     0,
                                     3,
                                     "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                     "DBClone::DBImport",
                                     1126,
                                     v26,
                                     0);
    if ( !VolumeId )
    {
LABEL_167:
      if ( (*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120) )
        goto LABEL_56;
      VolumeId = Win32FilePath::ConvertToWin32NtPath((Win32FilePath *)&v90);
      if ( VolumeId )
        goto LABEL_105;
      VolumeId = Util::CreateSystemVolumeInformationDirectory((Util *)&v90, v28);
      if ( !VolumeId )
      {
LABEL_56:
        if ( !(*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120) && !v72 )
        {
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            v67 = (void **)L"DBClone::DBImport";
            v68 = 0x40000048DLL;
            v69 = L"DBCL";
            v66 = (VolumeManager *)(v22 + 18);
            dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v67, L"Create DFSR path:%?", &v66);
          }
          (*(void (__fastcall **)(char *))(*((_QWORD *)this + 15) + 40LL))((char *)this + 120);
          v29 = (const unsigned __int16 *)FilePath::GetDisplayPath(&v84);
          VolumeId = NtfsFileSystem::ForceMakeDirectory(
                       (NtfsFileSystem *)&v79,
                       (DBClone *)((char *)this + 264),
                       v29,
                       1,
                       1,
                       1,
                       v30);
        }
        if ( !VolumeId )
        {
          if ( (*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120) )
            goto LABEL_168;
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            v67 = (void **)L"DBClone::DBImport";
            v68 = 0x40000049BLL;
            v69 = L"DBCL";
            v66 = (VolumeManager *)(*((_QWORD *)this + 21) + 18LL);
            dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v67, L"Create DB path:%?", &v66);
          }
          (*(void (__fastcall **)(char *))(*((_QWORD *)this + 15) + 40LL))((char *)this + 120);
          v31 = (const unsigned __int16 *)FilePath::GetDisplayPath((char *)this + 168);
          VolumeId = NtfsFileSystem::ForceMakeDirectory(
                       (NtfsFileSystem *)&v79,
                       (DBClone *)((char *)this + 264),
                       v31,
                       1,
                       1,
                       1,
                       v32);
          if ( !VolumeId )
          {
LABEL_168:
            if ( (*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120)
              || (VolumeId = DBClone::CreateDBFile(v33, L"$db_import$", (DBClone *)((char *)this + 160))) == 0 )
            {
              if ( (*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120)
                || ((*(void (__fastcall **)(char *))(*((_QWORD *)this + 15) + 40LL))((char *)this + 120),
                    v34 = (const unsigned __int16 *)FilePath::GetDisplayPath(&v82),
                    (VolumeId = NtfsFileSystem::ForceMakeDirectory(
                                  (NtfsFileSystem *)&v79,
                                  (DBClone *)((char *)this + 264),
                                  v34,
                                  1,
                                  1,
                                  1,
                                  v35)) == 0) )
              {
                if ( ((*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120)
                   || (VolumeId = DBClone::CreateDBFile(v36, L"$db_export$", (struct FilePath *)&v81)) == 0)
                  && ((*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120)
                   || (VolumeId = DBClone::LoadContentSetInfo(this)) == 0) )
                {
                  if ( (*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120)
                    || *((_DWORD *)this + 36) )
                  {
                    goto LABEL_169;
                  }
                  FilePath::FilePath((FilePath *)&v67, (DBClone *)((char *)this + 176));
                  FilePath::FilePath((FilePath *)&v85, (const struct FilePath *)&v81);
                  v70 = 92;
                  FrsStringImpl<unsigned short,char>::Append(&v68, &v70, 1);
                  v70 = 92;
                  FrsStringImpl<unsigned short,char>::Append(&v86, &v70, 1);
                  FilePath::Append((FilePath *)&v67, L"dfsr.db.clone");
                  FilePath::Append((FilePath *)&v85, L"dfsr.db");
                  v37 = (VolumeManager *)(v86 + 18);
                  v71 = v68 + 18;
                  if ( CopyFileExW((LPCWSTR)(v68 + 18), (LPCWSTR)(v86 + 18), 0, 0, (LPBOOL)this + 36, 0) )
                  {
                    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
                    {
                      v107 = L"DBClone::DBImport";
                      v108 = 1255;
                      v109 = 4;
                      v110 = L"DBCL";
                      v66 = v37;
                      dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short *>(
                        &v107,
                        L"Successfully copied the master DB file from:%? to:%?",
                        &v71,
                        &v66);
                    }
                  }
                  else
                  {
                    v38 = GetCurrentThreadId();
                    LastError = GetLastError();
                    VolumeId = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                     "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                                     LastError,
                                                     0,
                                                     1,
                                                     "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                                     "DBClone::DBImport",
                                                     1248,
                                                     v38,
                                                     0);
                    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
                    {
                      v107 = L"DBClone::DBImport";
                      v108 = 1249;
                      v109 = 2;
                      v110 = L"DBCL";
                      v66 = v37;
                      dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short const *,FrsStatus>(
                        (unsigned int)&v107,
                        (unsigned int)L"Failed to copy the master DB file from:%? to:%? error:%?",
                        (unsigned int)&v71,
                        (unsigned int)&v66,
                        (__int64)VolumeId);
                    }
                  }
                  v85 = &FilePath::`vftable';
                  FrsStringImpl<char,unsigned short>::ReleaseBody(&v86);
                  v67 = &FilePath::`vftable';
                  FrsStringImpl<char,unsigned short>::ReleaseBody(&v68);
                  if ( !VolumeId )
                  {
LABEL_169:
                    if ( !(*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120) )
                    {
                      v66 = (VolumeManager *)operator new(0x690u);
                      v40 = VolumeManager::VolumeManager(
                              v66,
                              (DBClone *)((char *)this + 264),
                              (struct Config::Volume *)v8,
                              0,
                              0,
                              *(struct TaskPool **)(*((_QWORD *)this + 5) + 1344LL),
                              0,
                              0);
                      ScopedRef<VolumeManager::ShutdownRestartTask>::Set(&v89, v40);
                      v66 = (VolumeManager *)operator new(0x258u);
                      *((_QWORD *)this + 40) = LdbManager::LdbManager(v66, v105, v89);
                      v66 = (VolumeManager *)operator new(0x258u);
                      *((_QWORD *)this + 41) = LdbManager::LdbManager(v66, v105, v89);
                    }
                    if ( ((*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120)
                       || (VolumeId = DBClone::PreImport(this)) == 0)
                      && ((*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120)
                       || (VolumeId = (struct FrsStatus *)(*(__int64 (__fastcall **)(_QWORD, union _LARGE_INTEGER *, _QWORD, int *, int *, int *, int *, __int128 *))(**((_QWORD **)this + 40) + 56LL))(
                                                            *((_QWORD *)this + 40),
                                                            &v88,
                                                            0,
                                                            &v78,
                                                            &v77,
                                                            &v76,
                                                            &v75,
                                                            &v113)) == 0)
                      && ((*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120)
                       || (VolumeId = (struct FrsStatus *)(*(__int64 (__fastcall **)(_QWORD, union _LARGE_INTEGER *, __int64, int *, int *, int *, int *, __int128 *))(**((_QWORD **)this + 41) + 56LL))(
                                                            *((_QWORD *)this + 41),
                                                            &v74,
                                                            1,
                                                            &v78,
                                                            &v77,
                                                            &v76,
                                                            &v75,
                                                            &v113)) == 0) )
                    {
                      if ( (*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120) )
                        goto LABEL_170;
                      VolumeId = (struct FrsStatus *)ChangeJournal::Query(v106, (char *)this + 264, v105, &v111);
                      if ( !VolumeId )
                      {
                        if ( v111.NextUsn )
                          goto LABEL_170;
                        v41 = GetCurrentThreadId();
                        VolumeId = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                         v42,
                                                         9600,
                                                         0,
                                                         3,
                                                         "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                                         "DBClone::DBImport",
                                                         1334,
                                                         v41,
                                                         0);
                        if ( g_DebugLog
                          && LODWORD(g_DebugLog[1].LockSemaphore)
                          && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
                        {
                          v107 = L"DBClone::DBImport";
                          v108 = 1335;
                          v109 = 2;
                          v110 = L"DBCL";
                          dbgobj::DbgPrint<unsigned short,__int64,FrsStatus>(&v107, v43, &v111.NextUsn, VolumeId);
                        }
                        if ( !VolumeId )
                        {
LABEL_170:
                          if ( ((*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120)
                             || (VolumeId = DBClone::GetDBInfo(this, 0)) == 0)
                            && ((*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120)
                             || (VolumeId = DBClone::CSTableImportUpdate(this)) == 0) )
                          {
                            if ( (*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120)
                              || (v112 = v111, (VolumeId = DBClone::CreateJournalRecord(this, &v112)) == 0) )
                            {
                              if ( (*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120)
                                || (v112 = v111, (VolumeId = DBClone::IDTableImportUpdate(this, &v112)) == 0) )
                              {
                                if ( ((*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120)
                                   || *((_DWORD *)this + 38)
                                   || (VolumeId = DBClone::VCTableUpdate(this)) == 0)
                                  && ((*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120)
                                   || (VolumeId = DBClone::GITableUpdate(this, v74)) == 0)
                                  && !(*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120) )
                                {
                                  memset_0(&v112, 0, sizeof(v112));
                                  VolumeId = (struct FrsStatus *)ChangeJournal::Query(
                                                                   v106,
                                                                   (char *)this + 264,
                                                                   v105,
                                                                   &v112);
                                  if ( !VolumeId )
                                  {
                                    if ( v112.UsnJournalID == v111.UsnJournalID )
                                    {
                                      if ( v112.NextUsn >= v111.NextUsn )
                                      {
                                        if ( g_DebugLog
                                          && LODWORD(g_DebugLog[1].LockSemaphore)
                                          && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
                                        {
                                          v67 = (void **)L"DBClone::DBImport";
                                          v68 = 0x4000005A6LL;
                                          v69 = L"DBCL";
                                          dbgobj::DbgPrint<unsigned short,unsigned __int64,unsigned __int64,__int64,__int64>(
                                            (unsigned int)&v67,
                                            v49,
                                            (unsigned int)&v112,
                                            (unsigned int)&v111,
                                            (__int64)&v112.NextUsn,
                                            (__int64)&v111.NextUsn);
                                        }
                                      }
                                      else
                                      {
                                        v52 = GetCurrentThreadId();
                                        VolumeId = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                                         v53,
                                                                         9601,
                                                                         0,
                                                                         3,
                                                                         "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                                                         "DBClone::DBImport",
                                                                         1439,
                                                                         v52,
                                                                         0);
                                        if ( g_DebugLog
                                          && LODWORD(g_DebugLog[1].LockSemaphore)
                                          && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
                                        {
                                          v67 = (void **)L"DBClone::DBImport";
                                          v68 = 0x2000005A0LL;
                                          v69 = L"DBCL";
                                          dbgobj::DbgPrint<unsigned short,__int64,__int64,FrsStatus>(
                                            (unsigned int)&v67,
                                            v54,
                                            (unsigned int)&v112.NextUsn,
                                            (unsigned int)&v111.NextUsn,
                                            (__int64)VolumeId);
                                        }
                                      }
                                    }
                                    else
                                    {
                                      v50 = GetCurrentThreadId();
                                      VolumeId = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                                       v51,
                                                                       9600,
                                                                       0,
                                                                       3,
                                                                       "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                                                       "DBClone::DBImport",
                                                                       1430,
                                                                       v50,
                                                                       0);
                                      if ( g_DebugLog
                                        && LODWORD(g_DebugLog[1].LockSemaphore)
                                        && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
                                      {
                                        v67 = (void **)L"DBClone::DBImport";
                                        v68 = 0x200000597LL;
                                        v69 = L"DBCL";
                                        dbgobj::DbgPrint<unsigned short,unsigned __int64,unsigned __int64>(
                                          &v67,
                                          L"Journal wrap/loss. Current Journal ID:%? Previous ID:%?",
                                          &v112,
                                          &v111);
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
      else if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v101 = L"DBClone::DBImport";
        v102 = 1155;
        v103 = 2;
        v104 = L"DBCL";
        v66 = (VolumeManager *)(v91 + 18);
        dbgobj::DbgPrint<unsigned short,unsigned short const *>(
          &v101,
          L"Failed to create volume's '\\System Volume Information' directory. volPath:%?",
          &v66);
      }
    }
  }
LABEL_105:
  v44 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 40);
  if ( v44 )
  {
    (**v44)(v44, 1);
    *((_QWORD *)this + 40) = 0;
    if ( g_DebugLog )
    {
      if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v85 = (void **)L"DBClone::DBImport";
        v86 = 0x4000005B5LL;
        v87 = L"DBCL";
        dbgobj::DbgPrint<unsigned short>(&v85, L"Source DB manager deleted");
      }
    }
  }
  v45 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 41);
  if ( v45 )
  {
    (**v45)(v45, 1);
    *((_QWORD *)this + 41) = 0;
    if ( g_DebugLog )
    {
      if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v107 = L"DBClone::DBImport";
        v108 = 1467;
        v109 = 4;
        v110 = L"DBCL";
        dbgobj::DbgPrint<unsigned short>(&v107, L"Destination DB manager deleted");
      }
    }
  }
  if ( VolumeId
    || !(*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120)
    && (VolumeId = DBClone::PostImportSuccess(this, (struct FilePath *)&v81)) != 0
    || (*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120) )
  {
    DBClone::PostImportFailure(this, (struct FilePath *)&v83, (struct FilePath *)&v81, v72, v73);
  }
  if ( !(*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120) )
  {
    if ( VolumeId )
    {
      v55 = *(_QWORD *)FrsStatusString::FrsStatusString((FrsStatusString *)&Block, VolumeId);
      v56 = Dword::Dword((Dword *)&v107, *((_DWORD *)VolumeId + 1), 10);
      v57 = FilePath::GetDisplayPath((char *)this + 184);
      v58 = FilePath::GetDisplayPath((char *)this + 200);
      v59 = (_QWORD *)FrsGUIDToStringW(&v66, (char *)this + 280);
      FrsEvent::Log(3221227886LL, *v59 + 18LL, v58, v57, v56, v55);
      FrsStringImpl<char,unsigned short>::ReleaseBody(&v66);
      operator delete[](Block);
    }
    else
    {
      v46 = FilePath::GetDisplayPath((char *)this + 184);
      v47 = FilePath::GetDisplayPath((char *)this + 200);
      v48 = (_QWORD *)FrsGUIDToStringW(&v66, (char *)this + 280);
      FrsEvent::Log(1073744228, *v48 + 18LL, v47, v46);
      FrsStringImpl<char,unsigned short>::ReleaseBody(&v66);
    }
  }
  ScopedLock::ScopedLock((ScopedLock *)&v67, (struct ScopedCS *)DBClone::cloneCS);
  v60 = *((_DWORD *)this + 8);
  if ( v60 != 3 && v60 != 5 )
  {
    if ( v60 != 6 )
    {
      if ( v60 == 7 )
      {
        *((_DWORD *)this + 8) = 0;
      }
      else if ( !VolumeId )
      {
        v64 = GetCurrentThreadId();
        VolumeId = (struct FrsStatus *)FrsStatusList::PushNewError(
                                         v65,
                                         9602,
                                         0,
                                         3,
                                         "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                         "DBClone::DBImport",
                                         1543,
                                         v64,
                                         0);
      }
      goto LABEL_158;
    }
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 15) + 8LL))((char *)this + 120);
    *((_DWORD *)this + 36) = 0;
  }
  *((_DWORD *)this + 8) = 1;
LABEL_158:
  ScopedLock::~ScopedLock((ScopedLock *)&v67);
  SetEvent(*((HANDLE *)this + 45));
  if ( VolumeId )
  {
    v61 = GetCurrentThreadId();
    v6 = FrsStatusList::PushNewError(
           v62,
           *((unsigned int *)VolumeId + 1),
           *((unsigned int *)VolumeId + 2),
           *(unsigned int *)VolumeId,
           "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
           "DBClone::DBImport",
           1553,
           v61,
           VolumeId);
  }
LABEL_160:
  ChangeJournal::~ChangeJournal((ChangeJournal *)v106);
  v79 = &FileSystem::`vftable';
  v90 = &BaseFilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v91);
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v89);
  ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v92);
  Config::ConfigInstance<Config::ReplicaSet>::~ConfigInstance<Config::ReplicaSet>(v105);
  v81 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v82);
  v83 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v84);
  return (struct FrsStatus *)v6;
}

```

## disassembly

```asm
0x14002f630  mov     [rsp-8+arg_18], rbx
0x14002f635  push    rbp
0x14002f636  push    rsi
0x14002f637  push    rdi
0x14002f638  push    r12
0x14002f63a  push    r13
0x14002f63c  push    r14
0x14002f63e  push    r15
0x14002f640  lea     rbp, [rsp-440h]
0x14002f648  sub     rsp, 540h
0x14002f64f  mov     rax, cs:__security_cookie
0x14002f656  xor     rax, rsp
0x14002f659  mov     [rbp+470h+var_40], rax
0x14002f660  mov     rsi, r8
0x14002f663  mov     rdi, rdx
0x14002f666  mov     r13, rcx
0x14002f669  xor     r15d, r15d
0x14002f66c  mov     r12d, r15d
0x14002f66f  lea     rcx, [rbp+470h+var_4B0]; this
0x14002f673  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x14002f678  nop
0x14002f679  lea     rcx, [rbp+470h+var_4C0]; this
0x14002f67d  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x14002f682  nop
0x14002f683  lea     rcx, [rbp+470h+var_410]
0x14002f687  call    ??0?$ConfigInstance@VVolume@Config@@@Config@@QEAA@XZ; Config::ConfigInstance<Config::Volume>::ConfigInstance<Config::Volume>(void)
0x14002f68c  nop
0x14002f68d  mov     ebx, r15d
0x14002f690  mov     [rbp+470h+var_468], rbx
0x14002f694  mov     [rbp+470h+var_480], r15
0x14002f698  mov     qword ptr [rbp+470h+var_4E8], r15
0x14002f69c  mov     qword ptr [rbp+470h+var_488], r15
0x14002f6a0  mov     [rbp+470h+var_4D4], r15d
0x14002f6a4  mov     [rbp+470h+var_4D8], r15d
0x14002f6a8  mov     [rbp+470h+var_4DC], r15d
0x14002f6ac  mov     [rbp+470h+var_4E0], r15d
0x14002f6b0  mov     [rbp+470h+var_4EC], r15d
0x14002f6b4  mov     [rbp+470h+var_4F0], r15d
0x14002f6b8  lea     rcx, [rbp+470h+var_478]; this
0x14002f6bc  call    ??0Win32FilePath@@QEAA@XZ; Win32FilePath::Win32FilePath(void)
0x14002f6c1  nop
0x14002f6c2  xorps   xmm0, xmm0
0x14002f6c5  movups  [rbp+470h+var_2A0], xmm0
0x14002f6cc  lea     rax, ??_7NtfsFileSystem@@6B@; const NtfsFileSystem::`vftable'
0x14002f6d3  mov     [rbp+470h+var_4D0], rax
0x14002f6d7  xor     edx, edx; Val
0x14002f6d9  lea     r8d, [r15+40h]; Size
0x14002f6dd  lea     rcx, [rbp+470h+var_320]; void *
0x14002f6e4  call    memset_0
0x14002f6e9  lea     rcx, [rbp+470h+var_3D0]; this
0x14002f6f0  call    ??0ChangeJournal@@QEAA@XZ; ChangeJournal::ChangeJournal(void)
0x14002f6f5  nop
0x14002f6f6  lea     r14, aDbcloneDbimpor_0; "DBClone::DBImport"
0x14002f6fd  lea     rcx, aDbcl; "DBCL"
0x14002f704  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14002f70b  test    rax, rax
0x14002f70e  jz      short loc_14002F769
0x14002f710  cmp     [rax+40h], r15d
0x14002f714  jz      short loc_14002F769
0x14002f716  cmp     dword ptr [rax+38h], 4
0x14002f71a  jl      short loc_14002F769
0x14002f71c  mov     [rsp+570h+var_518], r14
0x14002f721  mov     dword ptr [rsp+570h+var_510], 3B7h
0x14002f729  mov     dword ptr [rsp+570h+var_510+4], 4
0x14002f731  mov     [rsp+570h+var_508], rcx
0x14002f736  mov     rax, [rsi+8]
0x14002f73a  add     rax, 12h
0x14002f73e  mov     [rsp+570h+var_4F8], rax
0x14002f743  mov     rax, [rdi+8]
0x14002f747  add     rax, 12h
0x14002f74b  mov     [rbp+470h+Block], rax
0x14002f74f  lea     r9, [rsp+570h+var_4F8]
0x14002f754  lea     r8, [rbp+470h+Block]
0x14002f758  lea     rdx, aStartingDbimpo; "Starting DBImport. Source:%? Destinatio"...
0x14002f75f  lea     rcx, [rsp+570h+var_518]
0x14002f764  call    ??$DbgPrint@GPEBGPEAG@dbgobj@@QEAA_KPEBGAEBQEBGAEBQEAG@Z; dbgobj::DbgPrint<ushort,ushort const *,ushort *>(ushort const *,ushort const * const &,ushort * const &)
0x14002f769  lea     rdx, ?cloneCS@DBClone@@2VScopedCS@@A; struct ScopedCS *
0x14002f770  lea     rcx, [rsp+570h+var_518]; this
0x14002f775  call    ??0ScopedLock@@QEAA@AEAVScopedCS@@@Z; ScopedLock::ScopedLock(ScopedCS &)
0x14002f77a  nop
0x14002f77b  lea     rcx, [r13+20h]
0x14002f77f  cmp     dword ptr [rcx], 1
0x14002f782  jz      loc_14002F873
0x14002f788  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14002f78f  test    rax, rax
0x14002f792  jz      short loc_14002F7DB
0x14002f794  cmp     [rax+40h], r15d
0x14002f798  jz      short loc_14002F7DB
0x14002f79a  mov     esi, 2
0x14002f79f  cmp     [rax+38h], esi
0x14002f7a2  jl      short loc_14002F7DB
0x14002f7a4  mov     [rbp+470h+var_4A0], r14
0x14002f7a8  mov     dword ptr [rbp+470h+var_498], 3C2h
0x14002f7af  mov     dword ptr [rbp+470h+var_498+4], esi
0x14002f7b2  lea     rax, aDbcl; "DBCL"
0x14002f7b9  mov     [rbp+470h+var_490], rax
0x14002f7bd  mov     [rbp+470h+var_4F0], 1
0x14002f7c4  lea     r9, [rbp+470h+var_4F0]
0x14002f7c8  mov     r8, rcx
0x14002f7cb  lea     rdx, aFailedToProces_23; "Failed to process DBImport.  Incorrect "...
0x14002f7d2  lea     rcx, [rbp+470h+var_4A0]
0x14002f7d6  call    ??$DbgPrint@GW4STATE@DBCloneInterface@@W412@@dbgobj@@QEAA_KPEBGAEBW4STATE@DBCloneInterface@@1@Z; dbgobj::DbgPrint<ushort,DBCloneInterface::STATE,DBCloneInterface::STATE>(ushort const *,DBCloneInterface::STATE const &,DBCloneInterface::STATE const &)
0x14002f7db  call    cs:__imp_GetCurrentThreadId
0x14002f7e2  nop     dword ptr [rax+rax+00h]
0x14002f7e7  mov     [rsp+570h+var_530], r15
0x14002f7ec  mov     dword ptr [rsp+570h+var_538], eax
0x14002f7f0  mov     dword ptr [rsp+570h+var_540], 3C6h
0x14002f7f8  lea     rdi, aDbcloneDbimpor; "DBClone::DBImport"
0x14002f7ff  mov     qword ptr [rsp+570h+dwCopyFlags], rdi
0x14002f804  lea     rsi, aBaseFsRemotefs_5; "base\\fs\\remotefs\\frs\\src\\main\\dbc"...
0x14002f80b  mov     [rsp+570h+pbCancel], rsi
0x14002f810  mov     r9d, 3
0x14002f816  xor     r8d, r8d
0x14002f819  mov     edx, 2582h
0x14002f81e  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14002f823  mov     rbx, rax
0x14002f826  test    rax, rax
0x14002f829  jz      short loc_14002F864
0x14002f82b  call    cs:__imp_GetCurrentThreadId
0x14002f832  nop     dword ptr [rax+rax+00h]
0x14002f837  mov     [rsp+570h+var_530], rbx
0x14002f83c  mov     dword ptr [rsp+570h+var_538], eax
0x14002f840  mov     dword ptr [rsp+570h+var_540], 3C7h
0x14002f848  mov     qword ptr [rsp+570h+dwCopyFlags], rdi
0x14002f84d  mov     [rsp+570h+pbCancel], rsi
0x14002f852  mov     r9d, [rbx]
0x14002f855  mov     r8d, [rbx+8]
0x14002f859  mov     edx, [rbx+4]
0x14002f85c  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14002f861  mov     r15, rax
0x14002f864  lea     rcx, [rsp+570h+var_518]; this
0x14002f869  call    ??1ScopedLock@@QEAA@XZ; ScopedLock::~ScopedLock(void)
0x14002f86e  jmp     loc_140030C9D
0x14002f873  mov     dword ptr [rcx], 3
0x14002f879  mov     rcx, r13; this
0x14002f87c  call    ?Initialize@DBClone@@AEAAXXZ; DBClone::Initialize(void)
0x14002f881  nop
0x14002f882  lea     rcx, [rsp+570h+var_518]; this
0x14002f887  call    ??1ScopedLock@@QEAA@XZ; ScopedLock::~ScopedLock(void)
0x14002f88c  lea     rcx, [r13+0B0h]
0x14002f893  mov     rdx, rdi
0x14002f896  call    ??4FilePath@@QEAAAEAV0@AEBV0@@Z; FilePath::operator=(FilePath const &)
0x14002f89b  lea     rcx, [r13+0C0h]
0x14002f8a2  mov     rdx, rsi
0x14002f8a5  call    ??4FilePath@@QEAAAEAV0@AEBV0@@Z; FilePath::operator=(FilePath const &)
0x14002f8aa  lea     r14, [r13+78h]
0x14002f8ae  mov     rax, [r14]
0x14002f8b1  mov     rcx, r14
0x14002f8b4  mov     rax, [rax+30h]
0x14002f8b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f8bd  test    al, al
0x14002f8bf  jnz     short loc_14002F8F0
0x14002f8c1  mov     rdx, [r13+0C8h]
0x14002f8c8  add     rdx, 12h; unsigned __int16 *
0x14002f8cc  lea     rcx, [rbp+470h+var_478]; this
0x14002f8d0  call    ?Set@Win32FilePath@@QEAAPEAVFrsStatus@@PEBG@Z; Win32FilePath::Set(ushort const *)
0x14002f8d5  mov     r12, rax
0x14002f8d8  test    rax, rax
0x14002f8db  jnz     short loc_14002F8F0
0x14002f8dd  lea     rdx, [r13+108h]; struct VolumeId *
0x14002f8e4  lea     rcx, [rbp+470h+var_478]; this
0x14002f8e8  call    ?GetVolumeId@Win32FilePath@@QEBAPEAVFrsStatus@@AEAVVolumeId@@@Z; Win32FilePath::GetVolumeId(VolumeId &)
0x14002f8ed  mov     r12, rax
0x14002f8f0  lea     rcx, [r13+0B8h]
0x14002f8f7  call    ?GetDisplayPath@FilePath@@SAPEBGAEBV?$FrsStringImpl@GD@@@Z; FilePath::GetDisplayPath(FrsStringImpl<ushort,char> const &)
0x14002f8fc  mov     rsi, rax
0x14002f8ff  lea     rcx, [r13+0C8h]
0x14002f906  call    ?GetDisplayPath@FilePath@@SAPEBGAEBV?$FrsStringImpl@GD@@@Z; FilePath::GetDisplayPath(FrsStringImpl<ushort,char> const &)
0x14002f90b  mov     rdi, rax
0x14002f90e  lea     rdx, [r13+118h]
0x14002f915  lea     rcx, [rbp+470h+Block]
0x14002f919  call    ?FrsGUIDToStringW@@YA?AV?$FrsStringImpl@GD@@AEBU_GUID@@@Z; FrsGUIDToStringW(_GUID const &)
0x14002f91e  nop
0x14002f91f  mov     rdx, [rax]
0x14002f922  add     rdx, 12h
0x14002f926  mov     r9, rsi
0x14002f929  mov     r8, rdi
0x14002f92c  mov     ecx, 4000096Ch
0x14002f931  call    ?Log@FrsEvent@@SAXW4FrsEventsEnum3@@PEBG11@Z; FrsEvent::Log(FrsEventsEnum3,ushort const *,ushort const *,ushort const *)
0x14002f936  nop
0x14002f937  lea     rcx, [rbp+470h+Block]
0x14002f93b  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x14002f940  test    r12, r12
0x14002f943  jnz     loc_1400305C8
0x14002f949  mov     rax, [r14]
0x14002f94c  mov     rcx, r14
0x14002f94f  mov     rax, [rax+30h]
0x14002f953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f958  test    al, al
0x14002f95a  jnz     short loc_14002F97C
0x14002f95c  lea     rdx, [r13+108h]; struct VolumeId *
0x14002f963  lea     r8, [rbp+470h+var_4E8]; union _LARGE_INTEGER *
0x14002f967  lea     rcx, [rbp+470h+var_4D0]; this
0x14002f96b  call    ?GetSerialNumber@NtfsFileSystem@@UEAAPEAVFrsStatus@@AEBVVolumeId@@AEAT_LARGE_INTEGER@@@Z; NtfsFileSystem::GetSerialNumber(VolumeId const &,_LARGE_INTEGER &)
0x14002f970  mov     r12, rax
0x14002f973  test    rax, rax
0x14002f976  jnz     loc_1400305C8
0x14002f97c  mov     rax, [r14]
0x14002f97f  mov     rcx, r14
0x14002f982  mov     rax, [rax+30h]
0x14002f986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f98b  test    al, al
0x14002f98d  jnz     loc_14002FAC4
0x14002f993  mov     rdx, [r13+0C8h]
0x14002f99a  add     rdx, 12h; unsigned __int16 *
0x14002f99e  lea     rcx, [rbp+470h+var_4B0]; this
0x14002f9a2  call    ?Set@FilePath@@QEAAXPEBG@Z; FilePath::Set(ushort const *)
0x14002f9a7  lea     rdx, aSystemVolumeIn_0; "System Volume Information"
0x14002f9ae  lea     rcx, [rbp+470h+var_4B0]; this
0x14002f9b2  call    ?Append@FilePath@@QEAAXPEBG@Z; FilePath::Append(ushort const *)
0x14002f9b7  lea     rdx, SourceName; "DFSR"
0x14002f9be  lea     rcx, [rbp+470h+var_4B0]; this
0x14002f9c2  call    ?Append@FilePath@@QEAAXPEBG@Z; FilePath::Append(ushort const *)
0x14002f9c7  lea     r9, [r13+0A0h]; struct FilePath *
0x14002f9ce  lea     r8, [rbp+470h+var_4E8]; union _LARGE_INTEGER *
0x14002f9d2  lea     rdx, [rbp+470h+var_4B0]; struct FilePath *
0x14002f9d6  call    ?GetDBFullPath@DBClone@@AEAAXAEAVFilePath@@AEBT_LARGE_INTEGER@@0@Z; DBClone::GetDBFullPath(FilePath &,_LARGE_INTEGER const &,FilePath &)
0x14002f9db  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14002f9e2  lea     rsi, aDbcloneDbimpor_0; "DBClone::DBImport"
0x14002f9e9  lea     rdi, aDbcl; "DBCL"
0x14002f9f0  test    rax, rax
0x14002f9f3  jz      short loc_14002FA56
0x14002f9f5  cmp     [rax+40h], r15d
0x14002f9f9  jz      short loc_14002FA56
0x14002f9fb  cmp     dword ptr [rax+38h], 4
0x14002f9ff  jl      short loc_14002FA56
0x14002fa01  mov     [rsp+570h+var_518], rsi
0x14002fa06  mov     dword ptr [rsp+570h+var_510], 404h
0x14002fa0e  mov     dword ptr [rsp+570h+var_510+4], 4
0x14002fa16  mov     [rsp+570h+var_508], rdi
0x14002fa1b  mov     rax, [r13+0A8h]
0x14002fa22  add     rax, 12h
0x14002fa26  mov     [rsp+570h+var_4F8], rax
0x14002fa2b  mov     rax, [r13+110h]
0x14002fa32  add     rax, 12h
0x14002fa36  mov     [rsp+570h+var_520], rax
0x14002fa3b  lea     r9, [rsp+570h+var_4F8]
0x14002fa40  lea     r8, [rsp+570h+var_520]
0x14002fa45  lea     rdx, aDestinationVol; "Destination volume:%? DB Path:%?"
0x14002fa4c  lea     rcx, [rsp+570h+var_518]
0x14002fa51  call    ??$DbgPrint@GPEBGPEAG@dbgobj@@QEAA_KPEBGAEBQEBGAEBQEAG@Z; dbgobj::DbgPrint<ushort,ushort const *,ushort *>(ushort const *,ushort const * const &,ushort * const &)
0x14002fa56  mov     rax, qword ptr [rbp+470h+var_4E8]
0x14002fa5a  dec     rax
0x14002fa5d  mov     qword ptr [rbp+470h+var_488], rax
0x14002fa61  lea     r9, [rbp+470h+var_4C0]; struct FilePath *
0x14002fa65  lea     r8, [rbp+470h+var_488]; union _LARGE_INTEGER *
0x14002fa69  lea     rdx, [rbp+470h+var_4B0]; struct FilePath *
0x14002fa6d  call    ?GetDBFullPath@DBClone@@AEAAXAEAVFilePath@@AEBT_LARGE_INTEGER@@0@Z; DBClone::GetDBFullPath(FilePath &,_LARGE_INTEGER const &,FilePath &)
0x14002fa72  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14002fa79  test    rax, rax
0x14002fa7c  jz      short loc_14002FAC4
0x14002fa7e  cmp     [rax+40h], r15d
0x14002fa82  jz      short loc_14002FAC4
0x14002fa84  cmp     dword ptr [rax+38h], 4
0x14002fa88  jl      short loc_14002FAC4
0x14002fa8a  mov     [rbp+470h+var_460], rsi
0x14002fa8e  mov     [rbp+470h+var_458], 40Eh
0x14002fa95  mov     [rbp+470h+var_454], 4
0x14002fa9c  mov     [rbp+470h+var_450], rdi
0x14002faa0  mov     rdi, [rbp+470h+var_4B8]
0x14002faa4  lea     rax, [rdi+12h]
0x14002faa8  mov     [rsp+570h+var_520], rax
0x14002faad  lea     r8, [rsp+570h+var_520]
0x14002fab2  lea     rdx, aCreateTempDbPa; "Create temp DB path:%?"
0x14002fab9  lea     rcx, [rbp+470h+var_460]
0x14002fabd  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x14002fac2  jmp     short loc_14002FACF
0x14002fac4  mov     rdi, [rbp+470h+var_4B8]
0x14002fac8  lea     rsi, aDbcloneDbimpor_0; "DBClone::DBImport"
0x14002facf  mov     rax, [r14]
0x14002fad2  mov     rcx, r14
0x14002fad5  mov     rax, [rax+30h]
0x14002fad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002fade  mov     r14, [rbp+470h+var_4A8]
0x14002fae2  test    al, al
0x14002fae4  jnz     loc_14002FBAB
0x14002faea  mov     ecx, 368h; Size
0x14002faef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002faf4  mov     [rsp+570h+var_520], rax
0x14002faf9  mov     rcx, rax; this
0x14002fafc  call    ??0Volume@Config@@QEAA@XZ; Config::Volume::Volume(void)
0x14002fb01  mov     rbx, rax
0x14002fb04  mov     [rbp+470h+var_468], rax
0x14002fb08  lea     rcx, [rax+270h]; this
0x14002fb0f  mov     edx, 64h ; 'd'; unsigned int
0x14002fb14  call    ?Set@DWordParam@Config@@QEAAHK@Z; Config::DWordParam::Set(ulong)
0x14002fb19  lea     rcx, [rbx+1F0h]; this
0x14002fb20  lea     rdx, [r14+12h]; unsigned __int16 *
0x14002fb24  call    ?Set@PathParam@Config@@QEAAHPEBG@Z; Config::PathParam::Set(ushort const *)
0x14002fb29  mov     rdx, rbx
0x14002fb2c  lea     rcx, [rbp+470h+var_410]
0x14002fb30  call    ?Set@?$ConfigInstance@VReplicaSet@Config@@@Config@@QEAAXPEAVReplicaSet@2@@Z; Config::ConfigInstance<Config::ReplicaSet>::Set(Config::ReplicaSet *)
0x14002fb35  lea     rdx, [r13+108h]
0x14002fb3c  lea     r9, [rbp+470h+var_320]
0x14002fb43  lea     r8, [rbp+470h+var_410]
0x14002fb47  lea     rcx, [rbp+470h+var_3D0]
0x14002fb4e  call    ?Query@ChangeJournal@@UEAAPEAVFrsStatus@@AEBVVolumeId@@AEAV?$ConfigInstance@VVolume@Config@@@Config@@AEAUUSN_JOURNAL_DATA_V1@@@Z; ChangeJournal::Query(VolumeId const &,Config::ConfigInstance<Config::Volume> &,USN_JOURNAL_DATA_V1 &)
0x14002fb53  mov     r12, rax
0x14002fb56  test    rax, rax
0x14002fb59  jnz     loc_1400305C8
  ... truncated ...
```
