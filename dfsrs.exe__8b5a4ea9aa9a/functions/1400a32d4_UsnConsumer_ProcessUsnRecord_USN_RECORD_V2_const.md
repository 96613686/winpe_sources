# UsnConsumer::ProcessUsnRecord(USN_RECORD_V2 const &)

- ea: `0x1400a32d4`
- end: `0x1400a3e9e`
- name: `?ProcessUsnRecord@UsnConsumer@@AEAAPEAVFrsStatus@@AEBUUSN_RECORD_V2@@@Z`
- size: `3018`
- prototype: `struct FrsStatus *__fastcall(UsnConsumer *__hidden this, const struct USN_RECORD_V2 *)`
- caller_count: `1`
- callee_count: `24`
- tags: `reparse_path, registry_config, service_task, installer_update`

## callers

- `0x1400a09b0`

## callees

- `0x1400036a0`
- `0x14000e34c`
- `0x14002c1c0`
- `0x14006f224`
- `0x140088fd8`
- `0x1400896e8`
- `0x140089a78`
- `0x140091f78`
- `0x14009f978`
- `0x1400a0e34`
- `0x1400a2170`
- `0x1400a258c`
- `0x1400a2af4`
- `0x1400a2d5c`
- `0x1400a32d4`
- `0x1400a48c4`
- `0x1400a4ac0`
- `0x1400a58f0`
- `0x1400a6260`
- `0x1400a6aec`
- `0x1400b2380`
- `0x14011694c`
- `0x1401b9494`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400a3420`
- `KERNEL32!GetCurrentThreadId` at `0x1400a34c9`
- `KERNEL32!GetCurrentThreadId` at `0x1400a36f0`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3778`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3845`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3882`
- `KERNEL32!GetCurrentThreadId` at `0x1400a38c5`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3af1`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3b5f`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3be8`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3d0e`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3d4b`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3db4`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3dfe`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3e3b`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3e7b`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3420`
- `KERNEL32!GetCurrentThreadId` at `0x1400a34c9`
- `KERNEL32!GetCurrentThreadId` at `0x1400a36f0`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3778`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3845`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3882`
- `KERNEL32!GetCurrentThreadId` at `0x1400a38c5`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3af1`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3b5f`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3be8`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3d0e`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3d4b`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3db4`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3dfe`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3e3b`
- `KERNEL32!GetCurrentThreadId` at `0x1400a3e7b`

## string_xrefs

- `0x1400a3953`: `Skipping USN_RECORD with FILE_ATTRIBUTE_TEMPORARY flag:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct FrsStatus *__fastcall UsnConsumer::ProcessUsnRecord(UsnConsumer *this, const struct USN_RECORD_V2 *a2)
{
  DWORD Reason; // esi
  DWORD SourceInfo; // r12d
  int v6; // r13d
  __int64 v7; // rbx
  signed int v8; // esi
  __int64 v9; // rdx
  BOOL v10; // eax
  int v11; // eax
  unsigned int *v12; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v14; // rcx
  struct FrsStatus *v15; // rbx
  DWORD v16; // eax
  __int64 v17; // rcx
  int v19; // r15d
  USN Usn; // rax
  const wchar_t *v21; // rdx
  struct FrsStatus *updated; // rbx
  __int64 v23; // rcx
  __int64 v24; // rax
  struct FrsStatus *v25; // rbx
  __int64 v26; // rcx
  __int64 *v27; // rcx
  __int64 v28; // rax
  struct FrsStatus *v29; // rbx
  __int64 v30; // rcx
  struct FrsStatus *v31; // rbx
  __int64 v32; // rcx
  struct FrsStatus *v33; // rbx
  __int64 v34; // rcx
  int v35; // ecx
  unsigned __int64 v36; // r9
  struct FrsStatus *v37; // rbx
  __int64 v38; // rcx
  struct FrsStatus *v39; // rbx
  __int64 v40; // rcx
  unsigned int v41; // edx
  int v42; // r8d
  struct FrsStatus *v43; // rbx
  __int64 v44; // rcx
  struct FrsStatus *v45; // rdx
  struct FrsStatus *v46; // rbx
  __int64 v47; // rcx
  struct FrsStatus *v48; // rbx
  __int64 v49; // rcx
  struct FrsStatus *v50; // rbx
  __int64 v51; // rcx
  struct FrsStatus *v52; // rbx
  __int64 v53; // rcx
  struct FrsStatus *v54; // rbx
  __int64 v55; // rcx
  struct FrsStatus *v56; // rbx
  __int64 v57; // rcx
  DWORD v58; // [rsp+38h] [rbp-C8h]
  DWORD v59; // [rsp+38h] [rbp-C8h]
  DWORD v60; // [rsp+38h] [rbp-C8h]
  DWORD v61; // [rsp+38h] [rbp-C8h]
  DWORD v62; // [rsp+38h] [rbp-C8h]
  DWORD v63; // [rsp+38h] [rbp-C8h]
  DWORD v64; // [rsp+38h] [rbp-C8h]
  DWORD v65; // [rsp+38h] [rbp-C8h]
  DWORD v66; // [rsp+38h] [rbp-C8h]
  DWORD v67; // [rsp+38h] [rbp-C8h]
  DWORD v68; // [rsp+38h] [rbp-C8h]
  DWORD v69; // [rsp+38h] [rbp-C8h]
  DWORD v70; // [rsp+38h] [rbp-C8h]
  DWORD v71; // [rsp+38h] [rbp-C8h]
  int v72; // [rsp+60h] [rbp-A0h] BYREF
  int v73; // [rsp+64h] [rbp-9Ch]
  unsigned int v74; // [rsp+68h] [rbp-98h] BYREF
  const wchar_t *v75; // [rsp+70h] [rbp-90h] BYREF
  int v76; // [rsp+78h] [rbp-88h]
  int v77; // [rsp+7Ch] [rbp-84h]
  const wchar_t *v78; // [rsp+80h] [rbp-80h]
  unsigned int v79; // [rsp+88h] [rbp-78h]
  struct FrsStatus *v80; // [rsp+90h] [rbp-70h] BYREF
  int v81; // [rsp+98h] [rbp-68h] BYREF
  struct FrsStatus *ParentFileReferenceNumber; // [rsp+A0h] [rbp-60h] BYREF
  USN v83; // [rsp+A8h] [rbp-58h] BYREF
  struct _FILETIME v84; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v85; // [rsp+B8h] [rbp-48h] BYREF
  DWORDLONG FileReferenceNumber; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v87[2]; // [rsp+C8h] [rbp-38h] BYREF
  struct _GUID v88; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v89; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v90; // [rsp+F8h] [rbp-8h]
  _BYTE v91[16]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v92; // [rsp+110h] [rbp+10h]
  _BYTE v93[100]; // [rsp+130h] [rbp+30h] BYREF
  int v94; // [rsp+194h] [rbp+94h]
  USN v95; // [rsp+3A8h] [rbp+2A8h]
  _BYTE v96[32]; // [rsp+3B0h] [rbp+2B0h] BYREF
  _BYTE v97[720]; // [rsp+3D0h] [rbp+2D0h] BYREF

  v88 = 0;
  v89 = 0;
  v90 = 0;
  v84 = 0;
  v83 = 0;
  v72 = 0;
  v73 = 0;
  v79 = 0;
  v74 = 0;
  ID_RECORD::ID_RECORD((ID_RECORD *)v91);
  FileReferenceNumber = a2->FileReferenceNumber;
  ParentFileReferenceNumber = (struct FrsStatus *)a2->ParentFileReferenceNumber;
  v85 = 0;
  Reason = a2->Reason;
  SourceInfo = a2->SourceInfo;
  v81 = 0;
  std::set<DirWalkerTask::Job *>::set<DirWalkerTask::Job *>(v87);
  v6 = 0;
  v7 = 0;
  v80 = 0;
  v8 = Reason & 0xFFF7FFFF;
  v9 = 512;
  if ( (v8 & 0x100) == 0 )
    goto LABEL_5;
  v10 = (a2->FileAttributes & 0x10) == 0 && v8 >= 0;
  if ( (v8 & 0x200) != 0 )
    v8 = 512;
  if ( !v10 )
  {
LABEL_5:
    ++*((_QWORD *)this + 37);
    ++*((_DWORD *)this + 81);
    v11 = 0;
    if ( (SourceInfo & 4) == 0 )
      v11 = UsnConsumer::UidTunnelCache::NameRelated(
              (UsnConsumer *)((char *)this + 192),
              (const struct FileId *)&ParentFileReferenceNumber,
              &a2->TimeStamp,
              a2->FileName,
              a2->FileNameLength >> 1,
              (struct FileId *)&v85);
    v12 = (unsigned int *)UsnConsumer::LockRelevantFids(this, (struct FileId *)&v85, v11, (__int64)v87);
    if ( v12 )
    {
      CurrentThreadId = GetCurrentThreadId();
      v7 = FrsStatusList::PushNewError(
             v14,
             v12[1],
             v12[2],
             *v12,
             "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
             "UsnConsumer::ProcessUsnRecord",
             1100,
             CurrentThreadId,
             v12);
      if ( v7 )
        goto LABEL_14;
    }
    v15 = UsnConsumer::IsUsnInContentSet(
            this,
            &v81,
            a2,
            (struct Guid *)&v88,
            (struct UID *)&v89,
            &v84,
            (struct Usn *)&v83,
            &v72,
            (int *)&v74,
            (struct ID_RECORD *)v91,
            (struct FileId *)&v80);
    if ( v15 )
    {
      v16 = GetCurrentThreadId();
      v7 = FrsStatusList::PushNewError(
             v17,
             *((unsigned int *)v15 + 1),
             *((unsigned int *)v15 + 2),
             *(unsigned int *)v15,
             "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
             "UsnConsumer::ProcessUsnRecord",
             1121,
             v16,
             v15);
      if ( v7 )
      {
LABEL_11:
        v6 = 1;
        goto LABEL_12;
      }
    }
    else
    {
      v7 = 0;
    }
    if ( !v81 )
      goto LABEL_11;
    v19 = v72;
    if ( v72 )
    {
      Usn = a2->Usn;
      if ( Usn < v95 )
      {
        if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 5 )
          goto LABEL_11;
        v76 = 1135;
        goto LABEL_25;
      }
      if ( Usn == v95 )
      {
        v8 &= 0xFFFFDEFF;
        if ( (v8 & 0x7FFFFFFF) == 0 )
        {
          if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 5 )
            goto LABEL_11;
          v76 = 1194;
          goto LABEL_25;
        }
        if ( Usn <= v83 )
        {
          if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 5 )
            goto LABEL_11;
          v76 = 1201;
LABEL_25:
          v77 = 5;
          v21 = L"Skipping obsolete USN_RECORD:%?";
LABEL_26:
          v75 = L"UsnConsumer::ProcessUsnRecord";
          v78 = L"USNC";
          dbgobj::DbgPrint<unsigned short,USN_RECORD_V2>(&v75, v21, a2);
          goto LABEL_11;
        }
        LOBYTE(SourceInfo) = SourceInfo & 0xFB;
      }
    }
    if ( (*(unsigned int (__fastcall **)(UsnConsumer *, DWORDLONG *, struct FrsStatus **, __int128 *, DWORD))(*(_QWORD *)this + 48LL))(
           this,
           &FileReferenceNumber,
           &ParentFileReferenceNumber,
           &v89,
           a2->FileAttributes) )
    {
      goto LABEL_11;
    }
    if ( v19 && (v8 & 0x80000100) == -2147483392 && (a2->FileAttributes & 0x10) != 0 )
    {
      if ( (v8 & 0x368C77) == 0 )
      {
        updated = UsnConsumer::UpdateUsnOnly(this, (struct ID_RECORD *)v91, a2);
        if ( updated )
        {
          v58 = GetCurrentThreadId();
          v24 = FrsStatusList::PushNewError(
                  v23,
                  *((unsigned int *)updated + 1),
                  *((unsigned int *)updated + 2),
                  *(unsigned int *)updated,
                  "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                  "UsnConsumer::ProcessUsnRecord",
                  1248,
                  v58,
                  updated);
LABEL_67:
          v7 = v24;
          goto LABEL_12;
        }
        goto LABEL_45;
      }
      v8 &= ~0x100u;
    }
    if ( (SourceInfo & 5) != 0 )
    {
      if ( v19 && a2->Usn > v95 )
      {
        if ( (v8 & 0x200) != 0 && (unsigned int)ID_RECORD::Alive((ID_RECORD *)v91) )
        {
          v25 = UsnConsumer::TombstoneOrDelete(this, (struct ID_RECORD *)v91, a2, 0, 0, 0);
          if ( v25 )
          {
            v59 = GetCurrentThreadId();
            v24 = FrsStatusList::PushNewError(
                    v26,
                    *((unsigned int *)v25 + 1),
                    *((unsigned int *)v25 + 2),
                    *(unsigned int *)v25,
                    "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                    "UsnConsumer::ProcessUsnRecord",
                    1292,
                    v59,
                    v25);
            goto LABEL_67;
          }
          goto LABEL_45;
        }
        if ( (v8 & 0x2000) != 0 )
        {
          if ( (unsigned int)ID_RECORD::Alive((ID_RECORD *)v91) )
          {
            v72 = 0;
            ID_RECORD::ID_RECORD((ID_RECORD *)v97);
            v27 = (__int64 *)*((_QWORD *)this + 13);
            v28 = *v27;
            v84 = 0;
            v7 = (*(__int64 (__fastcall **)(__int64 *, int *, struct FrsStatus **, _BYTE *, struct _FILETIME *))(v28 + 40))(
                   v27,
                   &v72,
                   &ParentFileReferenceNumber,
                   v97,
                   &v84);
            if ( !v7 && !v72 )
            {
              if ( (a2->FileAttributes & 0x10) != 0 || ParentFileReferenceNumber != v80 )
              {
                v31 = UsnConsumer::TombstoneIdRecord(this, a2, (struct ID_RECORD *)v91, 0);
                if ( v31 )
                {
                  v61 = GetCurrentThreadId();
                  v24 = FrsStatusList::PushNewError(
                          v32,
                          *((unsigned int *)v31 + 1),
                          *((unsigned int *)v31 + 2),
                          *(unsigned int *)v31,
                          "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                          "UsnConsumer::ProcessUsnRecord",
                          1338,
                          v61,
                          v31);
                  goto LABEL_67;
                }
              }
              else
              {
                v29 = UsnConsumer::TombstoneOrDelete(this, (struct ID_RECORD *)v91, a2, 0, 0, 1);
                if ( v29 )
                {
                  v60 = GetCurrentThreadId();
                  v24 = FrsStatusList::PushNewError(
                          v30,
                          *((unsigned int *)v29 + 1),
                          *((unsigned int *)v29 + 2),
                          *(unsigned int *)v29,
                          "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                          "UsnConsumer::ProcessUsnRecord",
                          1335,
                          v60,
                          v29);
                  goto LABEL_67;
                }
              }
              goto LABEL_45;
            }
          }
        }
        if ( !v7 )
        {
          v33 = UsnConsumer::UpdateUsnOnly(this, (struct ID_RECORD *)v91, a2);
          if ( v33 )
          {
            v62 = GetCurrentThreadId();
            v24 = FrsStatusList::PushNewError(
                    v34,
                    *((unsigned int *)v33 + 1),
                    *((unsigned int *)v33 + 2),
                    *(unsigned int *)v33,
                    "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                    "UsnConsumer::ProcessUsnRecord",
                    1344,
                    v62,
                    v33);
            goto LABEL_67;
          }
          goto LABEL_45;
        }
LABEL_14:
        v9 = *((_QWORD *)this + 13);
        if ( *(_DWORD *)(v9 + 32) )
          FidLockMan::UnlockEx((FidLockMan *)(*(_QWORD *)(v9 + 8) + 8LL), (struct Db *)v9);
        goto LABEL_16;
      }
LABEL_12:
      if ( !v7 && !v6 )
        goto LABEL_16;
      goto LABEL_14;
    }
    if ( (a2->FileAttributes & 0x100) != 0 )
    {
      if ( !v19 )
      {
        if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 4 )
          goto LABEL_11;
        v76 = 1358;
        v77 = 4;
        v21 = L"Skipping USN_RECORD with FILE_ATTRIBUTE_TEMPORARY flag:%?";
        goto LABEL_26;
      }
      v35 = 1;
      v73 = 1;
    }
    else
    {
      v35 = v73;
    }
    if ( !Settings::EfsEnabled && (a2->FileAttributes & 0x4000) != 0 )
    {
      v36 = (unsigned __int64)a2->FileNameLength >> 1;
      v80 = (struct FrsStatus *)a2->ParentFileReferenceNumber;
      ContentSetManager::LogEncryptedFileEvent(
        *((struct VolumeManager **)this + 6),
        (const struct FileId *)&v80,
        a2->FileName,
        v36,
        &v88);
      if ( !v19 )
      {
        if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 4 )
          goto LABEL_11;
        v76 = 1377;
        v77 = 4;
        v21 = L"Skipping USN_RECORD with FILE_ATTRIBUTE_ENCRYPTED flag:%?";
        goto LABEL_26;
      }
      v35 = 1;
      v73 = 1;
    }
    if ( (v8 & 0x2000) == 0 || (v8 & 0x200) == 0 )
    {
      if ( (unsigned int)FilterMan::Match(
                           *((FilterMan **)this + 26),
                           &v88,
                           a2->FileName,
                           a2->FileNameLength >> 1,
                           (a2->FileAttributes >> 4) & 1,
                           (int)a2 + 60)
        && v92 != 1 )
      {
        if ( !v19 )
        {
          if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 4 )
            goto LABEL_11;
          v76 = 1407;
          v77 = 4;
          v21 = L"Filtered USN_RECORD:%?";
          goto LABEL_26;
        }
        v35 = 1;
        v9 = 1;
        goto LABEL_96;
      }
      v35 = v73;
    }
    v9 = v79;
LABEL_96:
    if ( (v8 & 0x2200) == 0x2000 )
    {
      v37 = UsnConsumer::ProcessRename(
              this,
              a2,
              (const struct Guid *)&v88,
              (const struct UID *)&v89,
              &v84,
              (const struct Usn *)&v83,
              v19,
              v35,
              v74,
              (struct ID_RECORD *)v91);
      if ( v37 )
      {
        v63 = GetCurrentThreadId();
        v24 = FrsStatusList::PushNewError(
                v38,
                *((unsigned int *)v37 + 1),
                *((unsigned int *)v37 + 2),
                *(unsigned int *)v37,
                "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                "UsnConsumer::ProcessUsnRecord",
                1434,
                v63,
                v37);
        goto LABEL_67;
      }
      goto LABEL_45;
    }
    if ( v19 )
    {
      if ( (v8 & 0x200) != 0 || v35 )
      {
        v56 = UsnConsumer::TombstoneIdRecord(this, a2, (struct ID_RECORD *)v91, v9);
        if ( v56 )
        {
          v71 = GetCurrentThreadId();
          v24 = FrsStatusList::PushNewError(
                  v57,
                  *((unsigned int *)v56 + 1),
                  *((unsigned int *)v56 + 2),
                  *(unsigned int *)v56,
                  "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                  "UsnConsumer::ProcessUsnRecord",
                  1472,
                  v71,
                  v56);
          goto LABEL_67;
        }
        goto LABEL_45;
      }
      if ( (v8 & 0x368C77) == 0 )
      {
        v54 = UsnConsumer::UpdateUsnOnly(this, (struct ID_RECORD *)v91, a2);
        if ( v54 )
        {
          v70 = GetCurrentThreadId();
          v24 = FrsStatusList::PushNewError(
                  v55,
                  *((unsigned int *)v54 + 1),
                  *((unsigned int *)v54 + 2),
                  *(unsigned int *)v54,
                  "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                  "UsnConsumer::ProcessUsnRecord",
                  1615,
                  v70,
                  v54);
          goto LABEL_67;
        }
        goto LABEL_45;
      }
      v41 = 0;
      v74 = 0;
      v42 = v94;
      if ( (v8 & 0x360C77) != 0 || (v94 & 0xFFFFFF5F) != (a2->FileAttributes & 0xFFFFFF5F) )
      {
        if ( (a2->FileAttributes & 0x400) != 0 )
        {
          if ( Settings::GhostingEnabled )
          {
            v45 = NtfsFileSystem::ReparsePointCanBeMarshaled(
                    (NtfsFileSystem *)UsnConsumer::fs,
                    (const struct VolumeId *)(*((_QWORD *)this + 6) + 168LL),
                    (const struct FileId *)v96,
                    &v72,
                    &v74);
            v80 = v45;
            if ( v45 )
            {
              if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
              {
                v75 = L"UsnConsumer::ProcessUsnRecord";
                v76 = 1522;
                v77 = 2;
                v78 = L"USNC";
                dbgobj::DbgPrint<unsigned short,VolumeId,FileId,FrsStatus>(
                  (unsigned int)&v75,
                  (_DWORD)v45,
                  *((_QWORD *)this + 6) + 168,
                  (unsigned int)v96,
                  (__int64)v45);
              }
              CLEAR_ERROR(&v80);
            }
            v41 = v74;
            if ( v74 == -2147483630 )
            {
              if ( (v8 & 0x360C77) != 0 || (v94 & 0x1A2107) != (a2->FileAttributes & 0x1A2107) )
              {
                v48 = UsnConsumer::UpdateUsnOnly(this, (struct ID_RECORD *)v91, a2);
                if ( v48 )
                {
                  v67 = GetCurrentThreadId();
                  v24 = FrsStatusList::PushNewError(
                          v49,
                          *((unsigned int *)v48 + 1),
                          *((unsigned int *)v48 + 2),
                          *(unsigned int *)v48,
                          "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                          "UsnConsumer::ProcessUsnRecord",
                          1568,
                          v67,
                          v48);
                  goto LABEL_67;
                }
              }
              else
              {
                v46 = UsnConsumer::UpdateUsnOnly(this, (struct ID_RECORD *)v91, a2);
                if ( v46 )
                {
                  v66 = GetCurrentThreadId();
                  v24 = FrsStatusList::PushNewError(
                          v47,
                          *((unsigned int *)v46 + 1),
                          *((unsigned int *)v46 + 2),
                          *(unsigned int *)v46,
                          "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                          "UsnConsumer::ProcessUsnRecord",
                          1562,
                          v66,
                          v46);
                  goto LABEL_67;
                }
              }
              goto LABEL_45;
            }
            v42 = v94;
          }
          else
          {
            v41 = -2147483641;
          }
        }
        if ( (v8 & 0x7FFF7FFF) != 0
          || v41 != -2147483641 && v41 != -2147483629
          || ((a2->FileAttributes ^ v42) & 0xFFFFF95F) != 0 )
        {
          v52 = UsnConsumer::UpdateIdRecord(
                  this,
                  a2,
                  (struct ID_RECORD *)v91,
                  (const struct UID *)v93,
                  (const struct Usn *)&v83);
          if ( v52 )
          {
            v69 = GetCurrentThreadId();
            v24 = FrsStatusList::PushNewError(
                    v53,
                    *((unsigned int *)v52 + 1),
                    *((unsigned int *)v52 + 2),
                    *(unsigned int *)v52,
                    "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                    "UsnConsumer::ProcessUsnRecord",
                    1592,
                    v69,
                    v52);
            goto LABEL_67;
          }
        }
        else
        {
          v50 = UsnConsumer::UpdateUsnOnly(this, (struct ID_RECORD *)v91, a2);
          if ( v50 )
          {
            v68 = GetCurrentThreadId();
            v24 = FrsStatusList::PushNewError(
                    v51,
                    *((unsigned int *)v50 + 1),
                    *((unsigned int *)v50 + 2),
                    *(unsigned int *)v50,
                    "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                    "UsnConsumer::ProcessUsnRecord",
                    1587,
                    v68,
                    v50);
            goto LABEL_67;
          }
        }
        goto LABEL_45;
      }
      v43 = UsnConsumer::UpdateUsnOnly(this, (struct ID_RECORD *)v91, a2);
      if ( v43 )
      {
        v65 = GetCurrentThreadId();
        v24 = FrsStatusList::PushNewError(
                v44,
                *((unsigned int *)v43 + 1),
                *((unsigned int *)v43 + 2),
                *(unsigned int *)v43,
                "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                "UsnConsumer::ProcessUsnRecord",
                1505,
                v65,
                v43);
        goto LABEL_67;
      }
LABEL_45:
      v7 = 0;
      goto LABEL_12;
    }
    if ( (v8 & 0x368D77) != 0 && (v8 & 0x200) == 0 )
    {
      v39 = UsnConsumer::CreateIdRecord(
              this,
              a2,
              (const struct Guid *)&v88,
              (const struct UID *)&v89,
              &v84,
              (const struct Usn *)&v83);
      if ( v39 )
      {
        v64 = GetCurrentThreadId();
        v24 = FrsStatusList::PushNewError(
                v40,
                *((unsigned int *)v39 + 1),
                *((unsigned int *)v39 + 2),
                *(unsigned int *)v39,
                "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                "UsnConsumer::ProcessUsnRecord",
                1458,
                v64,
                v39);
        goto LABEL_67;
      }
      goto LABEL_45;
    }
    goto LABEL_12;
  }
LABEL_16:
  std::_Tree<std::_Tset_traits<FileId,std::less<FileId>,std::allocator<FileId>,0>>::~_Tree<std::_Tset_traits<FileId,std::less<FileId>,std::allocator<FileId>,0>>(
    v87,
    v9);
  return (struct FrsStatus *)v7;
}

```

## disassembly

```asm
0x1400a32d4  mov     [rsp-8+arg_10], rbx
0x1400a32d9  push    rbp
0x1400a32da  push    rsi
0x1400a32db  push    rdi
0x1400a32dc  push    r12
0x1400a32de  push    r13
0x1400a32e0  push    r14
0x1400a32e2  push    r15
0x1400a32e4  lea     rbp, [rsp-5B0h]
0x1400a32ec  sub     rsp, 6B0h
0x1400a32f3  mov     rax, cs:__security_cookie
0x1400a32fa  xor     rax, rsp
0x1400a32fd  mov     [rbp+5E0h+var_40], rax
0x1400a3304  mov     rdi, rdx
0x1400a3307  mov     r14, rcx
0x1400a330a  xorps   xmm0, xmm0
0x1400a330d  movups  xmmword ptr [rbp+5E0h+var_608.Data1], xmm0
0x1400a3311  xorps   xmm1, xmm1
0x1400a3314  movups  [rbp+5E0h+var_5F8], xmm1
0x1400a3318  and     [rbp+5E0h+var_5E8], 0
0x1400a331d  and     qword ptr [rbp+5E0h+var_630.dwLowDateTime], 0
0x1400a3322  and     [rbp+5E0h+var_638], 0
0x1400a3327  and     [rsp+6E0h+var_680], 0
0x1400a332c  and     [rsp+6E0h+var_67C], 0
0x1400a3331  and     [rbp+5E0h+var_658], 0
0x1400a3335  and     [rsp+6E0h+var_678], 0
0x1400a333a  lea     rcx, [rbp+5E0h+var_5E0]; this
0x1400a333e  call    ??0ID_RECORD@@QEAA@XZ; ID_RECORD::ID_RECORD(void)
0x1400a3343  mov     rax, [rdi+8]
0x1400a3347  mov     [rbp+5E0h+var_620], rax
0x1400a334b  mov     rax, [rdi+10h]
0x1400a334f  mov     [rbp+5E0h+var_640], rax
0x1400a3353  and     [rbp+5E0h+var_628], 0
0x1400a3358  mov     esi, [rdi+28h]
0x1400a335b  mov     r12d, [rdi+2Ch]
0x1400a335f  and     [rbp+5E0h+var_648], 0
0x1400a3363  lea     rcx, [rbp+5E0h+var_618]
0x1400a3367  call    ??0?$set@PEAVJob@DirWalkerTask@@U?$less@PEAVJob@DirWalkerTask@@@std@@V?$allocator@PEAVJob@DirWalkerTask@@@4@@std@@QEAA@XZ; std::set<DirWalkerTask::Job *>::set<DirWalkerTask::Job *>(void)
0x1400a336c  nop
0x1400a336d  xor     r13d, r13d
0x1400a3370  xor     ebx, ebx
0x1400a3372  and     [rbp+5E0h+var_650], rbx
0x1400a3376  btr     esi, 13h
0x1400a337a  mov     edx, 200h
0x1400a337f  bt      esi, 8
0x1400a3383  jnb     short loc_1400A33A8
0x1400a3385  test    byte ptr [rdi+34h], 10h
0x1400a3389  setz    cl
0x1400a338c  bt      esi, 1Fh
0x1400a3390  setnb   al
0x1400a3393  test    al, cl
0x1400a3395  mov     eax, ebx
0x1400a3397  setnz   al
0x1400a339a  test    edx, esi
0x1400a339c  jz      short loc_1400A33A0
0x1400a339e  mov     esi, edx
0x1400a33a0  test    eax, eax
0x1400a33a2  jnz     loc_1400A353A
0x1400a33a8  inc     qword ptr [r14+128h]
0x1400a33af  inc     dword ptr [r14+144h]
0x1400a33b6  xor     eax, eax
0x1400a33b8  test    r12b, 4
0x1400a33bc  jnz     short loc_1400A33E9
0x1400a33be  lea     rcx, [r14+0C0h]; this
0x1400a33c5  movzx   eax, word ptr [rdi+38h]
0x1400a33c9  shr     eax, 1
0x1400a33cb  lea     r9, [rdi+3Ch]; unsigned __int16 *
0x1400a33cf  lea     r8, [rdi+20h]; union _LARGE_INTEGER *
0x1400a33d3  lea     rdx, [rbp+5E0h+var_628]
0x1400a33d7  mov     [rsp+6E0h+var_6B8], rdx; struct FileId *
0x1400a33dc  mov     dword ptr [rsp+6E0h+var_6C0], eax; int
0x1400a33e0  lea     rdx, [rbp+5E0h+var_640]; struct FileId *
0x1400a33e4  call    ?NameRelated@UidTunnelCache@UsnConsumer@@QEAAHAEBVFileId@@AEBT_LARGE_INTEGER@@PEBGHAEAV3@@Z; UsnConsumer::UidTunnelCache::NameRelated(FileId const &,_LARGE_INTEGER const &,ushort const *,int,FileId &)
0x1400a33e9  lea     rcx, [rbp+5E0h+var_618]
0x1400a33ed  mov     [rsp+6E0h+var_6B0], rcx; __int64
0x1400a33f2  mov     dword ptr [rsp+6E0h+var_6B8], eax; int
0x1400a33f6  lea     rax, [rbp+5E0h+var_628]
0x1400a33fa  mov     [rsp+6E0h+var_6C0], rax; struct FileId *
0x1400a33ff  lea     r9, [rbp+5E0h+var_640]
0x1400a3403  lea     r8, [rbp+5E0h+var_620]
0x1400a3407  mov     edx, esi
0x1400a3409  mov     rcx, r14; this
0x1400a340c  call    ?LockRelevantFids@UsnConsumer@@AEAAPEAVFrsStatus@@KAEBVFileId@@00HAEAV?$set@VFileId@@U?$less@VFileId@@@std@@V?$allocator@VFileId@@@3@@std@@@Z; UsnConsumer::LockRelevantFids(ulong,FileId const &,FileId const &,FileId const &,int,std::set<FileId> &)
0x1400a3411  mov     rbx, rax
0x1400a3414  lea     r15, aUsnconsumerPro; "UsnConsumer::ProcessUsnRecord"
0x1400a341b  test    rax, rax
0x1400a341e  jz      short loc_1400A3469
0x1400a3420  call    cs:__imp_GetCurrentThreadId
0x1400a3427  nop     dword ptr [rax+rax+00h]
0x1400a342c  mov     [rsp+6E0h+var_6A0], rbx
0x1400a3431  mov     dword ptr [rsp+6E0h+var_6A8], eax
0x1400a3435  mov     dword ptr [rsp+6E0h+var_6B0], 44Ch
0x1400a343d  mov     [rsp+6E0h+var_6B8], r15
0x1400a3442  lea     rax, aBaseFsRemotefs_51; "base\\fs\\remotefs\\frs\\src\\db\\usnco"...
0x1400a3449  mov     [rsp+6E0h+var_6C0], rax
0x1400a344e  mov     r9d, [rbx]
0x1400a3451  mov     r8d, [rbx+8]
0x1400a3455  mov     edx, [rbx+4]
0x1400a3458  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400a345d  mov     rbx, rax
0x1400a3460  test    rax, rax
0x1400a3463  jnz     loc_1400A351E
0x1400a3469  lea     rax, [rbp+5E0h+var_650]
0x1400a346d  mov     [rsp+6E0h+var_690], rax; struct FileId *
0x1400a3472  lea     rax, [rbp+5E0h+var_5E0]
0x1400a3476  mov     [rsp+6E0h+var_698], rax; struct ID_RECORD *
0x1400a347b  lea     rax, [rsp+6E0h+var_678]
0x1400a3480  mov     [rsp+6E0h+var_6A0], rax; int *
0x1400a3485  lea     rax, [rsp+6E0h+var_680]
0x1400a348a  mov     [rsp+6E0h+var_6A8], rax; int *
0x1400a348f  lea     rax, [rbp+5E0h+var_638]
0x1400a3493  mov     [rsp+6E0h+var_6B0], rax; struct Usn *
0x1400a3498  lea     rax, [rbp+5E0h+var_630]
0x1400a349c  mov     [rsp+6E0h+var_6B8], rax; struct _FILETIME *
0x1400a34a1  lea     rax, [rbp+5E0h+var_5F8]
0x1400a34a5  mov     [rsp+6E0h+var_6C0], rax; struct UID *
0x1400a34aa  lea     r9, [rbp+5E0h+var_608]; struct Guid *
0x1400a34ae  mov     r8, rdi; struct USN_RECORD_V2 *
0x1400a34b1  lea     rdx, [rbp+5E0h+var_648]; int *
0x1400a34b5  mov     rcx, r14; this
0x1400a34b8  call    ?IsUsnInContentSet@UsnConsumer@@AEAAPEAVFrsStatus@@AEAHAEBUUSN_RECORD_V2@@AEAVGuid@@AEAVUID@@AEAU_FILETIME@@AEAVUsn@@00AEAVID_RECORD@@AEAVFileId@@@Z; UsnConsumer::IsUsnInContentSet(int &,USN_RECORD_V2 const &,Guid &,UID &,_FILETIME &,Usn &,int &,int &,ID_RECORD &,FileId &)
0x1400a34bd  mov     rbx, rax
0x1400a34c0  test    rax, rax
0x1400a34c3  jz      loc_1400A3571
0x1400a34c9  call    cs:__imp_GetCurrentThreadId
0x1400a34d0  nop     dword ptr [rax+rax+00h]
0x1400a34d5  mov     [rsp+6E0h+var_6A0], rbx
0x1400a34da  mov     dword ptr [rsp+6E0h+var_6A8], eax
0x1400a34de  mov     dword ptr [rsp+6E0h+var_6B0], 461h
0x1400a34e6  mov     [rsp+6E0h+var_6B8], r15
0x1400a34eb  lea     rax, aBaseFsRemotefs_51; "base\\fs\\remotefs\\frs\\src\\db\\usnco"...
0x1400a34f2  mov     [rsp+6E0h+var_6C0], rax
0x1400a34f7  mov     r9d, [rbx]
0x1400a34fa  mov     r8d, [rbx+8]
0x1400a34fe  mov     edx, [rbx+4]
0x1400a3501  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400a3506  mov     rbx, rax
0x1400a3509  test    rax, rax
0x1400a350c  jz      short loc_1400A3573
0x1400a350e  mov     r13d, 1
0x1400a3514  test    rbx, rbx
0x1400a3517  jnz     short loc_1400A351E
0x1400a3519  test    r13d, r13d
0x1400a351c  jz      short loc_1400A353A
0x1400a351e  mov     rdx, [r14+68h]; struct Db *
0x1400a3522  cmp     dword ptr [rdx+20h], 0
0x1400a3526  jz      short loc_1400A353A
0x1400a3528  mov     rcx, [rdx+8]
0x1400a352c  add     rcx, 8; this
0x1400a3530  lea     r8, [rbp+5E0h+var_618]
0x1400a3534  call    ?UnlockEx@FidLockMan@@QEAAXPEBVDb@@AEBV?$set@VFileId@@U?$less@VFileId@@@std@@V?$allocator@VFileId@@@3@@std@@@Z; FidLockMan::UnlockEx(Db const *,std::set<FileId> const &)
0x1400a3539  nop
0x1400a353a  lea     rcx, [rbp+5E0h+var_618]
0x1400a353e  call    ??1?$_Tree@V?$_Tset_traits@VFileId@@U?$less@VFileId@@@std@@V?$allocator@VFileId@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<FileId,std::less<FileId>,std::allocator<FileId>,0>>::~_Tree<std::_Tset_traits<FileId,std::less<FileId>,std::allocator<FileId>,0>>(void)
0x1400a3543  mov     rax, rbx
0x1400a3546  mov     rcx, [rbp+5E0h+var_40]
0x1400a354d  xor     rcx, rsp; StackCookie
0x1400a3550  call    __security_check_cookie
0x1400a3555  mov     rbx, [rsp+6E0h+arg_10]
0x1400a355d  add     rsp, 6B0h
0x1400a3564  pop     r15
0x1400a3566  pop     r14
0x1400a3568  pop     r13
0x1400a356a  pop     r12
0x1400a356c  pop     rdi
0x1400a356d  pop     rsi
0x1400a356e  pop     rbp
0x1400a356f  retn
0x1400a3571  xor     ebx, ebx
0x1400a3573  cmp     [rbp+5E0h+var_648], r13d
0x1400a3577  jz      short loc_1400A350E
0x1400a3579  mov     r15d, [rsp+6E0h+var_680]
0x1400a357e  test    r15d, r15d
0x1400a3581  jz      loc_1400A3671
0x1400a3587  mov     rax, [rdi+18h]
0x1400a358b  cmp     rax, [rbp+5E0h+var_338]
0x1400a3592  jge     short loc_1400A35F8
0x1400a3594  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400a359b  test    rax, rax
0x1400a359e  jz      loc_1400A350E
0x1400a35a4  cmp     [rax+40h], r13d
0x1400a35a8  jz      loc_1400A350E
0x1400a35ae  cmp     dword ptr [rax+38h], 5
0x1400a35b2  jl      loc_1400A350E
0x1400a35b8  mov     [rsp+6E0h+var_668], 46Fh
0x1400a35c0  mov     [rsp+6E0h+var_664], 5
0x1400a35c8  lea     rdx, aSkippingObsole; "Skipping obsolete USN_RECORD:%?"
0x1400a35cf  lea     rax, aUsnconsumerPro_2; "UsnConsumer::ProcessUsnRecord"
0x1400a35d6  mov     [rsp+6E0h+var_670], rax
0x1400a35db  lea     rax, aUsnc; "USNC"
0x1400a35e2  mov     r8, rdi
0x1400a35e5  mov     [rbp+5E0h+var_660], rax
0x1400a35e9  lea     rcx, [rsp+6E0h+var_670]
0x1400a35ee  call    ??$DbgPrint@GUUSN_RECORD_V2@@@dbgobj@@QEAA_KPEBGAEBUUSN_RECORD_V2@@@Z; dbgobj::DbgPrint<ushort,USN_RECORD_V2>(ushort const *,USN_RECORD_V2 const &)
0x1400a35f3  jmp     loc_1400A350E
0x1400a35f8  jnz     short loc_1400A3671
0x1400a35fa  and     esi, 0FFFFDEFFh
0x1400a3600  test    esi, 7FFFFFFFh
0x1400a3606  jnz     short loc_1400A3636
0x1400a3608  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400a360f  test    rax, rax
0x1400a3612  jz      loc_1400A350E
0x1400a3618  cmp     [rax+40h], r13d
0x1400a361c  jz      loc_1400A350E
0x1400a3622  cmp     dword ptr [rax+38h], 5
0x1400a3626  jl      loc_1400A350E
0x1400a362c  mov     [rsp+6E0h+var_668], 4AAh
0x1400a3634  jmp     short loc_1400A35C0
0x1400a3636  cmp     rax, [rbp+5E0h+var_638]
0x1400a363a  jg      short loc_1400A366D
0x1400a363c  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400a3643  test    rax, rax
0x1400a3646  jz      loc_1400A350E
0x1400a364c  cmp     [rax+40h], r13d
0x1400a3650  jz      loc_1400A350E
0x1400a3656  cmp     dword ptr [rax+38h], 5
0x1400a365a  jl      loc_1400A350E
0x1400a3660  mov     [rsp+6E0h+var_668], 4B1h
0x1400a3668  jmp     loc_1400A35C0
0x1400a366d  and     r12d, 0FFFFFFFBh
0x1400a3671  mov     rax, [r14]
0x1400a3674  mov     r10, [rax+30h]
0x1400a3678  lea     rcx, [rdi+3Ch]
0x1400a367c  movzx   eax, word ptr [rdi+38h]
0x1400a3680  shr     rax, 1
0x1400a3683  mov     [rsp+6E0h+var_6B0], rax
0x1400a3688  mov     [rsp+6E0h+var_6B8], rcx; int
0x1400a368d  mov     eax, [rdi+34h]
0x1400a3690  mov     dword ptr [rsp+6E0h+var_6C0], eax; int
0x1400a3694  lea     r9, [rbp+5E0h+var_5F8]
0x1400a3698  lea     r8, [rbp+5E0h+var_640]
0x1400a369c  lea     rdx, [rbp+5E0h+var_620]
0x1400a36a0  mov     rcx, r14
0x1400a36a3  mov     rax, r10
0x1400a36a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a36ab  test    eax, eax
0x1400a36ad  jnz     loc_1400A350E
0x1400a36b3  test    r15d, r15d
0x1400a36b6  jz      short loc_1400A371D
0x1400a36b8  mov     eax, esi
0x1400a36ba  mov     ecx, 80000100h
0x1400a36bf  and     eax, ecx
0x1400a36c1  cmp     eax, ecx
0x1400a36c3  setz    cl
0x1400a36c6  test    byte ptr [rdi+34h], 10h
0x1400a36ca  setnz   al
0x1400a36cd  test    al, cl
0x1400a36cf  jz      short loc_1400A371D
0x1400a36d1  test    esi, 368C77h
0x1400a36d7  jnz     short loc_1400A3719
0x1400a36d9  mov     r8, rdi; struct USN_RECORD_V2 *
0x1400a36dc  lea     rdx, [rbp+5E0h+var_5E0]; struct ID_RECORD *
0x1400a36e0  mov     rcx, r14; this
0x1400a36e3  call    ?UpdateUsnOnly@UsnConsumer@@AEAAPEAVFrsStatus@@AEAVID_RECORD@@AEBUUSN_RECORD_V2@@@Z; UsnConsumer::UpdateUsnOnly(ID_RECORD &,USN_RECORD_V2 const &)
0x1400a36e8  mov     rbx, rax
0x1400a36eb  test    rax, rax
0x1400a36ee  jz      short loc_1400A3712
0x1400a36f0  call    cs:__imp_GetCurrentThreadId
0x1400a36f7  nop     dword ptr [rax+rax+00h]
0x1400a36fc  mov     [rsp+6E0h+var_6A0], rbx
0x1400a3701  mov     dword ptr [rsp+6E0h+var_6A8], eax
0x1400a3705  mov     dword ptr [rsp+6E0h+var_6B0], 4E0h
0x1400a370d  jmp     loc_1400A38E2
0x1400a3712  xor     ebx, ebx
0x1400a3714  jmp     loc_1400A3514
0x1400a3719  btr     esi, 8
0x1400a371d  test    r12b, 5
0x1400a3721  jz      loc_1400A3911
0x1400a3727  test    r15d, r15d
0x1400a372a  jz      loc_1400A3514
0x1400a3730  mov     rax, [rbp+5E0h+var_338]
0x1400a3737  cmp     [rdi+18h], rax
0x1400a373b  jle     loc_1400A3514
0x1400a3741  bt      esi, 9
0x1400a3745  jnb     short loc_1400A379A
0x1400a3747  lea     rcx, [rbp+5E0h+var_5E0]; this
0x1400a374b  call    ?Alive@ID_RECORD@@QEBAHXZ; ID_RECORD::Alive(void)
0x1400a3750  test    eax, eax
0x1400a3752  jz      short loc_1400A379A
0x1400a3754  and     dword ptr [rsp+6E0h+var_6B8], r13d
0x1400a3759  and     dword ptr [rsp+6E0h+var_6C0], r13d
0x1400a375e  xor     r9d, r9d; int
0x1400a3761  mov     r8, rdi; struct USN_RECORD_V2 *
0x1400a3764  lea     rdx, [rbp+5E0h+var_5E0]; struct ID_RECORD *
0x1400a3768  mov     rcx, r14; this
0x1400a376b  call    ?TombstoneOrDelete@UsnConsumer@@AEAAPEAVFrsStatus@@AEAVID_RECORD@@AEBUUSN_RECORD_V2@@HHH@Z; UsnConsumer::TombstoneOrDelete(ID_RECORD &,USN_RECORD_V2 const &,int,int,int)
0x1400a3770  mov     rbx, rax
0x1400a3773  test    rax, rax
0x1400a3776  jz      short loc_1400A3712
0x1400a3778  call    cs:__imp_GetCurrentThreadId
0x1400a377f  nop     dword ptr [rax+rax+00h]
0x1400a3784  mov     [rsp+6E0h+var_6A0], rbx
0x1400a3789  mov     dword ptr [rsp+6E0h+var_6A8], eax
0x1400a378d  mov     dword ptr [rsp+6E0h+var_6B0], 50Ch
0x1400a3795  jmp     loc_1400A38E2
0x1400a379a  bt      esi, 0Dh
0x1400a379e  jnb     loc_1400A38A1
0x1400a37a4  lea     rcx, [rbp+5E0h+var_5E0]; this
0x1400a37a8  call    ?Alive@ID_RECORD@@QEBAHXZ; ID_RECORD::Alive(void)
0x1400a37ad  test    eax, eax
  ... truncated ...
```
