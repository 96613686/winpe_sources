# Meet::InstallOverwrite(Db *,StageReader *,Meet::RelatedToUpdate &,Meet::RelatedToUpdate &,ID_RECORD const &)

- ea: `0x140183950`
- end: `0x1401842f5`
- name: `?InstallOverwrite@Meet@@AEAAPEAVFrsStatus@@PEAVDb@@PEAVStageReader@@AEAVRelatedToUpdate@1@2AEBVID_RECORD@@@Z`
- size: `2469`
- prototype: `struct FrsStatus *(Meet *__hidden this, struct Db *, struct StageReader *, struct Meet::RelatedToUpdate *, struct Meet::RelatedToUpdate *, const struct ID_RECORD *)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140185024`

## callees

- `0x1400036a0`
- `0x14000c910`
- `0x140088bf8`
- `0x1400923f8`
- `0x1400985ec`
- `0x1400b0780`
- `0x1400c0bb0`
- `0x140115e28`
- `0x14011efbc`
- `0x14012c9ac`
- `0x14014e03c`
- `0x140178920`
- `0x14017af28`
- `0x14017b008`
- `0x14017cb64`
- `0x140183950`
- `0x140187420`
- `0x14018842c`
- `0x140188594`
- `0x14018bdfc`
- `0x1401b2fac`
- `0x1401b393c`
- `0x1401b90b4`
- `0x1401b9494`
- `0x1401bda10`
- `0x1401c9600`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140183cc5`
- `KERNEL32!GetCurrentThreadId` at `0x140183faf`
- `KERNEL32!GetCurrentThreadId` at `0x14018427a`
- `KERNEL32!GetCurrentThreadId` at `0x140183cc5`
- `KERNEL32!GetCurrentThreadId` at `0x140183faf`
- `KERNEL32!GetCurrentThreadId` at `0x14018427a`

## string_xrefs

- `0x140184171`: `Updating database. updateName:%ws uid:%? gvsn:%? connId:%? csName:%?`
- `0x1401839c0`: `Meet::InstallOverwrite`
- `0x140183d46`: `Meet::InstallOverwrite`
- `0x140183e30`: `Meet::InstallOverwrite`
- `0x140183edd`: `Meet::InstallOverwrite`
- `0x140184103`: `Meet::InstallOverwrite`
- `0x1401841e0`: `Meet::InstallOverwrite`
- `0x140183ce2`: `Meet::InstallOverwrite`
- `0x140184297`: `Meet::InstallOverwrite`
- `0x140183a00`: `Open file handle in content set`
- `0x140183aed`: `Transferring content from staging to target updateName:%ws uid:%? gvsn:%? connId:%? csName:%?`
- `0x140183f4b`: `Updating database with the new content updateName:%ws uid:%? gvsn:%? connId:%? csName:%?`
- `0x14018425a`: `-> DONE Install-overwrite completed updateName:%ws uid:%? gvsn:%? connId:%? csName:%? csId:%?`
- `0x140183db4`: `Moving away content that is in the way updateName:%ws uid:%? gvsn:%? connId:%? csName:%?`
- `0x140183e9e`: `Move failed. Stamping new gvsn updateName:%ws uid:%? gvsn:%? connId:%? csName:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct FrsStatus *__fastcall Meet::InstallOverwrite(
        Meet *this,
        struct Db *a2,
        struct StageReader *a3,
        struct Meet::RelatedToUpdate *a4,
        struct Meet::RelatedToUpdate *a5,
        const struct ID_RECORD *a6)
{
  struct Meet::RelatedToUpdate *v6; // rsi
  __int64 v8; // r14
  XpressUncompressReader *UncompressReader; // r13
  struct FrsStatus *BackupUpdateWriter; // r12
  struct Writer *v11; // rbx
  unsigned int v12; // ecx
  void *v13; // rax
  __int64 v14; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v16; // rcx
  struct FrsStatus *v17; // rdi
  BOOL v18; // r13d
  LPCRITICAL_SECTION v19; // rax
  __int64 v20; // rsi
  __int64 (__fastcall *v21)(__int64, _OWORD *, _QWORD); // rdi
  DWORD v22; // eax
  FrsStatus *updated; // rdi
  int v24; // ecx
  Meet *v25; // rcx
  struct Db *v26; // rbx
  unsigned int v27; // eax
  __int64 v28; // rax
  DWORD v29; // eax
  __int64 v30; // rcx
  int v32; // [rsp+20h] [rbp-E0h]
  const wchar_t *v33; // [rsp+60h] [rbp-A0h] BYREF
  int v34; // [rsp+68h] [rbp-98h]
  int v35; // [rsp+6Ch] [rbp-94h]
  const wchar_t *v36; // [rsp+70h] [rbp-90h]
  struct _FILETIME v37; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v38; // [rsp+80h] [rbp-80h] BYREF
  union _LARGE_INTEGER v39; // [rsp+88h] [rbp-78h] BYREF
  struct Meet::RelatedToUpdate *v40; // [rsp+90h] [rbp-70h] BYREF
  __int64 v41; // [rsp+98h] [rbp-68h] BYREF
  struct Meet::RelatedToUpdate *v42; // [rsp+A0h] [rbp-60h] BYREF
  struct Db *v43; // [rsp+A8h] [rbp-58h]
  struct Writer *v44; // [rsp+B0h] [rbp-50h] BYREF
  struct ID_RECORD *v45; // [rsp+B8h] [rbp-48h]
  _OWORD v46[2]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v47[24]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v48[64]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v49[44]; // [rsp+138h] [rbp+38h] BYREF
  struct _FILETIME v50; // [rsp+164h] [rbp+64h] BYREF
  int v51; // [rsp+178h] [rbp+78h]
  unsigned int v52; // [rsp+3A0h] [rbp+2A0h]

  v6 = a4;
  v42 = a4;
  v43 = a2;
  v40 = a5;
  v45 = a6;
  v8 = 0;
  v41 = 0;
  UncompressReader = StageReader::GetUncompressReader(a3);
  v44 = 0;
  v37.dwLowDateTime = 0;
  v38 = 0;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v33 = L"Meet::InstallOverwrite";
    v34 = 3694;
    v35 = 5;
    v36 = L"MEET";
    dbgobj::DbgPrint<unsigned short>(&v33, L"Open file handle in content set");
  }
  BackupUpdateWriter = NtfsFileSystem::MakeBackupUpdateWriter(
                         (NtfsFileSystem *)Meet::fs,
                         (const struct VolumeId *)(*((_QWORD *)this + 99) + 208LL),
                         (struct Meet::RelatedToUpdate *)((char *)v6 + 688),
                         *((_DWORD *)this + 47),
                         &v44);
  Meet::ProcessSharingViolation(
    this,
    BackupUpdateWriter,
    (const unsigned __int16 *)v6 + 78,
    (struct Meet::RelatedToUpdate *)((char *)v6 + 688));
  v11 = v44;
  if ( !BackupUpdateWriter )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v33 = L"Meet::InstallOverwrite";
      v34 = 3709;
      v35 = 4;
      v36 = L"MEET";
      v39.QuadPart = *(_QWORD *)(*((_QWORD *)this + 99) + 200LL) + 18LL;
      dbgobj::DbgPrint<unsigned short,unsigned short [261],UID,GVSN,_GUID,unsigned short const *>(
        (unsigned int)&v33,
        (unsigned int)L"Transferring content from staging to target updateName:%ws uid:%? gvsn:%? connId:%? csName:%?",
        (_DWORD)this + 196,
        (_DWORD)this + 40,
        (__int64)this + 64,
        *((_QWORD *)this + 98) + 168LL,
        (__int64)&v39);
    }
    BackupUpdateWriter = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Writer *))(*(_QWORD *)v11 + 48LL))(v11);
    if ( !BackupUpdateWriter )
    {
      if ( (*((_BYTE *)this + 188) & 0x10) == 0 )
      {
        BackupUpdateWriter = XpressUncompressReader::GetNumberOfXpressBlocks(UncompressReader, &v38);
        if ( BackupUpdateWriter )
          goto LABEL_24;
        v39.QuadPart = v38 << 13;
        v13 = (void *)(*(__int64 (__fastcall **)(struct Writer *))(*(_QWORD *)v11 + 72LL))(v11);
        FileUtil::SetAllocationSize(v13, &v39);
      }
      BackupUpdateWriter = Transfer::Run(v12, UncompressReader, v11, (const volatile int *)&v37);
      if ( BackupUpdateWriter )
      {
        *((_DWORD *)this + 208) = 1;
        *((_DWORD *)this + 209) = 2;
        *((_DWORD *)this + 207) = 0;
      }
      else
      {
        BackupUpdateWriter = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Writer *))(*(_QWORD *)v11 + 24LL))(v11);
        if ( !BackupUpdateWriter )
        {
          BackupUpdateWriter = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Writer *, __int64 *))(*(_QWORD *)v11 + 64LL))(
                                                     v11,
                                                     &v41);
          if ( !BackupUpdateWriter && v41 < *((_QWORD *)v6 + 85) )
          {
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
            {
              v33 = L"Meet::InstallOverwrite";
              v34 = 3750;
              v35 = 2;
              v36 = L"MEET";
              v39.QuadPart = *(_QWORD *)(*((_QWORD *)this + 99) + 200LL) + 18LL;
              v14 = *((_QWORD *)this + 98) + 168LL;
              v38 = (*(__int64 (__fastcall **)(XpressUncompressReader *))(*(_QWORD *)UncompressReader + 32LL))(UncompressReader);
              v37 = (struct _FILETIME)(*(__int64 (__fastcall **)(struct Writer *))(*(_QWORD *)v11 + 16LL))(v11);
              dbgobj::DbgPrint<unsigned short,Usn,unsigned __int64,unsigned __int64,ID_RECORD,unsigned short [261],UID,GVSN,_GUID,unsigned short const *>(
                (unsigned int)&v33,
                (_DWORD)this + 196,
                (unsigned int)&v41,
                (unsigned int)&v37,
                (__int64)&v38,
                (__int64)v6,
                (__int64)this + 196,
                (__int64)this + 40,
                (__int64)this + 64,
                v14,
                (__int64)&v39);
            }
            CurrentThreadId = GetCurrentThreadId();
            BackupUpdateWriter = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                       v16,
                                                       1237,
                                                       1,
                                                       1,
                                                       "base\\fs\\remotefs\\frs\\src\\sync\\meet.cpp",
                                                       "Meet::InstallOverwrite",
                                                       3763,
                                                       CurrentThreadId,
                                                       0);
          }
        }
      }
    }
  }
LABEL_24:
  v17 = BackupUpdateWriter;
  v18 = BackupUpdateWriter == 0;
  if ( BackupUpdateWriter )
    goto LABEL_31;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v33 = L"Meet::InstallOverwrite";
    v34 = 3772;
    v35 = 4;
    v36 = L"MEET";
    v39.QuadPart = *(_QWORD *)(*((_QWORD *)this + 99) + 200LL) + 18LL;
    dbgobj::DbgPrint<unsigned short,unsigned short [261],UID,GVSN,_GUID,unsigned short const *>(
      (unsigned int)&v33,
      (unsigned int)L"Moving away content that is in the way updateName:%ws uid:%? gvsn:%? connId:%? csName:%?",
      (_DWORD)this + 196,
      (_DWORD)this + 40,
      (__int64)this + 64,
      *((_QWORD *)this + 98) + 168LL,
      (__int64)&v39);
  }
  *((_QWORD *)v6 + 89) = v41;
  BackupUpdateWriter = Meet::Move(this, v43, v6, v40, v45, (struct Usn *)&v41);
  if ( BackupUpdateWriter )
  {
LABEL_31:
    v19 = g_DebugLog;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v33 = L"Meet::InstallOverwrite";
      v34 = 3781;
      v35 = 4;
      v36 = L"MEET";
      v40 = (struct Meet::RelatedToUpdate *)(*(_QWORD *)(*((_QWORD *)this + 99) + 200LL) + 18LL);
      dbgobj::DbgPrint<unsigned short,unsigned short [261],UID,GVSN,_GUID,unsigned short const *>(
        (unsigned int)&v33,
        (unsigned int)L"Move failed. Stamping new gvsn updateName:%ws uid:%? gvsn:%? connId:%? csName:%?",
        (_DWORD)this + 196,
        (_DWORD)this + 40,
        (__int64)this + 64,
        *((_QWORD *)this + 98) + 168LL,
        (__int64)&v40);
      v19 = g_DebugLog;
    }
    if ( v17 )
      goto LABEL_70;
  }
  else
  {
    v18 = 0;
    v19 = g_DebugLog;
  }
  if ( v19 && LODWORD(v19[1].LockSemaphore) && SLODWORD(v19[1].OwningThread) >= 5 )
  {
    v33 = L"Meet::InstallOverwrite";
    v34 = 3786;
    v35 = 5;
    v36 = L"MEET";
    v40 = (struct Meet::RelatedToUpdate *)(*(_QWORD *)(*((_QWORD *)this + 99) + 200LL) + 18LL);
    dbgobj::DbgPrint<unsigned short,unsigned short [261],UID,GVSN,_GUID,unsigned short const *>(
      (unsigned int)&v33,
      (unsigned int)L"Updating database with the new content updateName:%ws uid:%? gvsn:%? connId:%? csName:%?",
      (_DWORD)this + 196,
      (_DWORD)this + 40,
      (__int64)this + 64,
      *((_QWORD *)this + 98) + 168LL,
      (__int64)&v40);
  }
  v40 = (struct Meet::RelatedToUpdate *)*((_QWORD *)v6 + 86);
  if ( !v18 )
    v6 = (Meet *)((char *)this + 40);
  ID_RECORD::ID_RECORD((ID_RECORD *)v47, v6, (const struct FileId *)&v40, &v41);
  v46[0] = 0;
  v37.dwLowDateTime = Settings::GenericDwordSetting::operator()(&Settings::DirtyShutdownClockValue);
  v37.dwHighDateTime = 0;
  v20 = *((_QWORD *)this + 100);
  v21 = *(__int64 (__fastcall **)(__int64, _OWORD *, _QWORD))(*(_QWORD *)v20 + 32LL);
  v22 = GetCurrentThreadId();
  updated = (FrsStatus *)v21(v20, v46, v22);
  if ( updated )
    goto LABEL_63;
  if ( HASH::IsNull((HASH *)v49) )
  {
    updated = (FrsStatus *)(*(__int64 (__fastcall **)(struct Writer *, _BYTE *))(*(_QWORD *)v11 + 56LL))(v11, v49);
    if ( updated )
      goto LABEL_63;
  }
  if ( v18
    || (v24 = *((_DWORD *)v42 + 34),
        LODWORD(v38) = *((_DWORD *)v42 + 33),
        HIDWORD(v38) = v24,
        (unsigned __int8)operator<(&v38, &v37))
    || (unsigned int)ContentSetManager::IsSubordinate(*((ContentSetManager **)this + 99)) && (v52 & 0x100) != 0 )
  {
    v26 = v43;
    updated = Meet::NewGvsn(this, v43, (struct GVSN *)v48);
    if ( !(unsigned int)ContentSetManager::IsSubordinate(*((ContentSetManager **)this + 99)) )
      v52 |= 0x20u;
    if ( v18 )
    {
      ID_UPDATE::MakeGreaterThan((ID_UPDATE *)v47, (const struct ID_UPDATE *)v47);
      ID_UPDATE::MakeGreaterThan((ID_UPDATE *)v47, (Meet *)((char *)this + 40));
    }
    FileTime::Max(&v50, &v37);
    v51 &= ~0x10u;
    v27 = v52 & 0xFFFFFF7F;
    v52 &= ~0x80u;
    if ( *((_DWORD *)this + 9) )
      v52 = v27 & 0xFFFFFEFF;
    if ( updated )
      goto LABEL_63;
  }
  else
  {
    v26 = v43;
  }
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v33 = L"Meet::InstallOverwrite";
    v34 = 3841;
    v35 = 4;
    v36 = L"MEET";
    v42 = (struct Meet::RelatedToUpdate *)(*(_QWORD *)(*((_QWORD *)this + 99) + 200LL) + 18LL);
    dbgobj::DbgPrint<unsigned short,unsigned short [261],UID,GVSN,_GUID,unsigned short const *>(
      (unsigned int)&v33,
      (unsigned int)L"Updating database. updateName:%ws uid:%? gvsn:%? connId:%? csName:%?",
      (_DWORD)this + 196,
      (_DWORD)this + 40,
      (__int64)this + 64,
      *((_QWORD *)this + 98) + 168LL,
      (__int64)&v42);
  }
  updated = Meet::UpdateIdRecord(v25, v26, (const struct UID *)v47, (struct ID_RECORD *)v47, v32);
  if ( updated )
LABEL_63:
    BackupUpdateWriter = FrsStatus::AppendError(updated, BackupUpdateWriter);
  if ( !BackupUpdateWriter )
  {
    *((_DWORD *)this + 8) = 3;
    if ( g_DebugLog )
    {
      if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v33 = L"Meet::InstallOverwrite";
        v34 = 3851;
        v35 = 4;
        v36 = L"MEET";
        v28 = *((_QWORD *)this + 99);
        v42 = (struct Meet::RelatedToUpdate *)(*(_QWORD *)(v28 + 200) + 18LL);
        dbgobj::DbgPrint<unsigned short,unsigned short [261],UID,GVSN,_GUID,unsigned short const *,_GUID>(
          (unsigned int)&v33,
          (unsigned int)L"-> DONE Install-overwrite completed updateName:%ws uid:%? gvsn:%? connId:%? csName:%? csId:%?",
          (_DWORD)this + 196,
          (_DWORD)this + 40,
          (__int64)this + 64,
          *((_QWORD *)this + 98) + 168LL,
          (__int64)&v42,
          v28 + 168);
      }
    }
  }
  DbManagerInstance::FinalizeDbManagerInstance((DbManagerInstance *)v46);
  if ( BackupUpdateWriter )
  {
LABEL_70:
    v29 = GetCurrentThreadId();
    v8 = FrsStatusList::PushNewError(
           v30,
           *((unsigned int *)BackupUpdateWriter + 1),
           *((unsigned int *)BackupUpdateWriter + 2),
           *(unsigned int *)BackupUpdateWriter,
           "base\\fs\\remotefs\\frs\\src\\sync\\meet.cpp",
           "Meet::InstallOverwrite",
           3854,
           v29,
           BackupUpdateWriter);
  }
  scoped_any<SimilarityTraitsTableDisk::TraitsDumpStateDisk *,close_delete,null_t,0>::~scoped_any<SimilarityTraitsTableDisk::TraitsDumpStateDisk *,close_delete,null_t,0>(&v44);
  return (struct FrsStatus *)v8;
}

```

## disassembly

```asm
0x140183950  push    rbp
0x140183952  push    rbx
0x140183953  push    rsi
0x140183954  push    rdi
0x140183955  push    r12
0x140183957  push    r13
0x140183959  push    r14
0x14018395b  push    r15
0x14018395d  lea     rbp, [rsp-2C8h]
0x140183965  sub     rsp, 3C8h
0x14018396c  mov     rax, cs:__security_cookie
0x140183973  xor     rax, rsp
0x140183976  mov     [rbp+300h+var_50], rax
0x14018397d  mov     rsi, r9
0x140183980  mov     [rbp+300h+var_360], r9
0x140183984  mov     [rbp+300h+var_358], rdx
0x140183988  mov     r15, rcx
0x14018398b  mov     rax, [rbp+300h+arg_20]
0x140183992  mov     [rbp+300h+var_370], rax
0x140183996  mov     rax, [rbp+300h+arg_28]
0x14018399d  mov     [rbp+300h+var_348], rax
0x1401839a1  xor     r14d, r14d
0x1401839a4  mov     [rbp+300h+var_368], r14
0x1401839a8  mov     rcx, r8; this
0x1401839ab  call    ?GetUncompressReader@StageReader@@QEAAPEAVXpressUncompressReader@@XZ; StageReader::GetUncompressReader(void)
0x1401839b0  mov     r13, rax
0x1401839b3  mov     [rbp+300h+var_350], r14
0x1401839b7  mov     [rsp+400h+var_388.dwLowDateTime], r14d
0x1401839bc  mov     [rbp+300h+var_380], r14
0x1401839c0  lea     rdi, aMeetInstallove; "Meet::InstallOverwrite"
0x1401839c7  lea     rax, aMeet; "MEET"
0x1401839ce  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401839d5  test    rcx, rcx
0x1401839d8  jz      short loc_140183A11
0x1401839da  cmp     [rcx+40h], r14d
0x1401839de  jz      short loc_140183A11
0x1401839e0  cmp     dword ptr [rcx+38h], 5
0x1401839e4  jl      short loc_140183A11
0x1401839e6  mov     [rsp+400h+var_3A0], rdi
0x1401839eb  mov     [rsp+400h+var_398], 0E6Eh
0x1401839f3  mov     [rsp+400h+var_394], 5
0x1401839fb  mov     [rsp+400h+var_390], rax
0x140183a00  lea     rdx, aOpenFileHandle; "Open file handle in content set"
0x140183a07  lea     rcx, [rsp+400h+var_3A0]
0x140183a0c  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140183a11  mov     rdx, [r15+318h]
0x140183a18  add     rdx, 0D0h; struct VolumeId *
0x140183a1f  lea     rbx, [rsi+2B0h]
0x140183a26  lea     rax, [rbp+300h+var_350]
0x140183a2a  mov     [rsp+400h+var_3E0], rax; struct IMarshalFileWriter **
0x140183a2f  mov     r9d, [r15+0BCh]; unsigned int
0x140183a36  mov     r8, rbx; struct FileId *
0x140183a39  lea     rcx, ?fs@Meet@@2VNtfsFileSystem@@A; this
0x140183a40  call    ?MakeBackupUpdateWriter@NtfsFileSystem@@UEAAPEAVFrsStatus@@AEBVVolumeId@@AEBVFileId@@KAEAPEAVIMarshalFileWriter@@@Z; NtfsFileSystem::MakeBackupUpdateWriter(VolumeId const &,FileId const &,ulong,IMarshalFileWriter * &)
0x140183a45  mov     r12, rax
0x140183a48  lea     r8, [rsi+9Ch]; unsigned __int16 *
0x140183a4f  mov     r9, rbx; struct FileId *
0x140183a52  mov     rdx, rax; struct FrsStatus *
0x140183a55  mov     rcx, r15; this
0x140183a58  call    ?ProcessSharingViolation@Meet@@AEAAXPEBVFrsStatus@@PEBGPEBVFileId@@@Z; Meet::ProcessSharingViolation(FrsStatus const *,ushort const *,FileId const *)
0x140183a5d  mov     rbx, [rbp+300h+var_350]
0x140183a61  test    r12, r12
0x140183a64  jnz     loc_140183D10
0x140183a6a  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140183a71  test    rax, rax
0x140183a74  jz      loc_140183AFE
0x140183a7a  cmp     [rax+40h], r14d
0x140183a7e  jz      short loc_140183AFE
0x140183a80  cmp     dword ptr [rax+38h], 4
0x140183a84  jl      short loc_140183AFE
0x140183a86  mov     [rsp+400h+var_3A0], rdi
0x140183a8b  mov     [rsp+400h+var_398], 0E7Dh
0x140183a93  mov     [rsp+400h+var_394], 4
0x140183a9b  lea     rax, aMeet; "MEET"
0x140183aa2  mov     [rsp+400h+var_390], rax
0x140183aa7  mov     rax, [r15+318h]
0x140183aae  mov     rcx, [rax+0C8h]
0x140183ab5  add     rcx, 12h
0x140183ab9  mov     qword ptr [rbp+300h+var_378], rcx
0x140183abd  mov     rcx, [r15+310h]
0x140183ac4  add     rcx, 0A8h
0x140183acb  lea     rax, [r15+40h]
0x140183acf  lea     r9, [r15+28h]
0x140183ad3  lea     r8, [r15+0C4h]
0x140183ada  lea     rdx, [rbp+300h+var_378]
0x140183ade  mov     [rsp+400h+var_3D0], rdx
0x140183ae3  mov     [rsp+400h+var_3D8], rcx
0x140183ae8  mov     [rsp+400h+var_3E0], rax
0x140183aed  lea     rdx, aTransferringCo; "Transferring content from staging to ta"...
0x140183af4  lea     rcx, [rsp+400h+var_3A0]
0x140183af9  call    ??$DbgPrint@G$$BY0BAF@GVUID@@VGVSN@@U_GUID@@PEBG@dbgobj@@QEAA_KPEBGAEAY0BAF@$$CBGAEBVUID@@AEBVGVSN@@AEBU_GUID@@AEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort [261],UID,GVSN,_GUID,ushort const *>(ushort const *,ushort const (&)[261],UID const &,GVSN const &,_GUID const &,ushort const * const &)
0x140183afe  mov     rax, [rbx]
0x140183b01  mov     rcx, rbx
0x140183b04  mov     rax, [rax+30h]
0x140183b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140183b0d  mov     r12, rax
0x140183b10  test    rax, rax
0x140183b13  jnz     loc_140183D10
0x140183b19  test    byte ptr [r15+0BCh], 10h
0x140183b21  jnz     short loc_140183B62
0x140183b23  lea     rdx, [rbp+300h+var_380]; unsigned __int64 *
0x140183b27  mov     rcx, r13; this
0x140183b2a  call    ?GetNumberOfXpressBlocks@XpressUncompressReader@@QEAAPEAVFrsStatus@@AEA_K@Z; XpressUncompressReader::GetNumberOfXpressBlocks(unsigned __int64 &)
0x140183b2f  mov     r12, rax
0x140183b32  test    rax, rax
0x140183b35  jnz     loc_140183D10
0x140183b3b  mov     rax, [rbp+300h+var_380]
0x140183b3f  shl     rax, 0Dh
0x140183b43  mov     qword ptr [rbp+300h+var_378], rax
0x140183b47  mov     rax, [rbx]
0x140183b4a  mov     rcx, rbx
0x140183b4d  mov     rax, [rax+48h]
0x140183b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140183b56  mov     rcx, rax; void *
0x140183b59  lea     rdx, [rbp+300h+var_378]; union _LARGE_INTEGER *
0x140183b5d  call    ?SetAllocationSize@FileUtil@@SAXPEAXPEAT_LARGE_INTEGER@@@Z; FileUtil::SetAllocationSize(void *,_LARGE_INTEGER *)
0x140183b62  lea     r9, [rsp+400h+var_388]; volatile int *
0x140183b67  mov     r8, rbx; struct Writer *
0x140183b6a  mov     rdx, r13; struct Reader *
0x140183b6d  call    ?Run@Transfer@@SAPEAVFrsStatus@@KPEAVReader@@PEAVWriter@@AEDH@Z; Transfer::Run(ulong,Reader *,Writer *,int const volatile &)
0x140183b72  mov     r12, rax
0x140183b75  test    rax, rax
0x140183b78  jz      short loc_140183B9C
0x140183b7a  mov     dword ptr [r15+340h], 1
0x140183b85  mov     dword ptr [r15+344h], 2
0x140183b90  mov     [r15+33Ch], r14d
0x140183b97  jmp     loc_140183D10
0x140183b9c  mov     rax, [rbx]
0x140183b9f  mov     rcx, rbx
0x140183ba2  mov     rax, [rax+18h]
0x140183ba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140183bab  mov     r12, rax
0x140183bae  test    rax, rax
0x140183bb1  jnz     loc_140183D10
0x140183bb7  mov     rax, [rbx]
0x140183bba  lea     rdx, [rbp+300h+var_368]
0x140183bbe  mov     rcx, rbx
0x140183bc1  mov     rax, [rax+40h]
0x140183bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140183bca  mov     r12, rax
0x140183bcd  test    rax, rax
0x140183bd0  jnz     loc_140183D10
0x140183bd6  mov     rax, [rsi+2A8h]
0x140183bdd  cmp     [rbp+300h+var_368], rax
0x140183be1  jge     loc_140183D10
0x140183be7  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140183bee  test    rax, rax
0x140183bf1  jz      loc_140183CC5
0x140183bf7  cmp     [rax+40h], r14d
0x140183bfb  jz      loc_140183CC5
0x140183c01  cmp     dword ptr [rax+38h], 2
0x140183c05  jl      loc_140183CC5
0x140183c0b  mov     [rsp+400h+var_3A0], rdi
0x140183c10  mov     [rsp+400h+var_398], 0EA6h
0x140183c18  mov     [rsp+400h+var_394], 2
0x140183c20  lea     rax, aMeet; "MEET"
0x140183c27  mov     [rsp+400h+var_390], rax
0x140183c2c  mov     rax, [r15+318h]
0x140183c33  mov     rcx, [rax+0C8h]
0x140183c3a  add     rcx, 12h
0x140183c3e  mov     qword ptr [rbp+300h+var_378], rcx
0x140183c42  mov     rdi, [r15+310h]
0x140183c49  add     rdi, 0A8h
0x140183c50  mov     rax, [r13+0]
0x140183c54  mov     rcx, r13
0x140183c57  mov     rax, [rax+20h]
0x140183c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140183c60  mov     [rbp+300h+var_380], rax
0x140183c64  mov     rax, [rbx]
0x140183c67  mov     rcx, rbx
0x140183c6a  mov     rax, [rax+10h]
0x140183c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140183c73  mov     qword ptr [rsp+400h+var_388.dwLowDateTime], rax
0x140183c78  lea     rax, [r15+40h]
0x140183c7c  lea     rcx, [r15+28h]
0x140183c80  lea     rdx, [r15+0C4h]
0x140183c87  lea     r8, [rbp+300h+var_378]
0x140183c8b  mov     [rsp+400h+var_3B0], r8
0x140183c90  mov     [rsp+400h+var_3B8], rdi
0x140183c95  mov     [rsp+400h+var_3C0], rax
0x140183c9a  mov     [rsp+400h+var_3C8], rcx
0x140183c9f  mov     [rsp+400h+var_3D0], rdx
0x140183ca4  mov     [rsp+400h+var_3D8], rsi
0x140183ca9  lea     rax, [rbp+300h+var_380]
0x140183cad  mov     [rsp+400h+var_3E0], rax
0x140183cb2  lea     r9, [rsp+400h+var_388]
0x140183cb7  lea     r8, [rbp+300h+var_368]
0x140183cbb  lea     rcx, [rsp+400h+var_3A0]
0x140183cc0  call    ??$DbgPrint@GVUsn@@_K_KVID_RECORD@@$$BY0BAF@GVUID@@VGVSN@@U_GUID@@PEBG@dbgobj@@QEAA_KPEBGAEBVUsn@@AEB_K2AEBVID_RECORD@@AEAY0BAF@$$CBGAEBVUID@@AEBVGVSN@@AEBU_GUID@@AEBQEBG@Z; dbgobj::DbgPrint<ushort,Usn,unsigned __int64,unsigned __int64,ID_RECORD,ushort [261],UID,GVSN,_GUID,ushort const *>(ushort const *,Usn const &,unsigned __int64 const &,unsigned __int64 const &,ID_RECORD const &,ushort const (&)[261],UID const &,GVSN const &,_GUID const &,ushort const * const &)
0x140183cc5  call    cs:__imp_GetCurrentThreadId
0x140183ccc  nop     dword ptr [rax+rax+00h]
0x140183cd1  mov     [rsp+400h+var_3C0], r14
0x140183cd6  mov     dword ptr [rsp+400h+var_3C8], eax
0x140183cda  mov     dword ptr [rsp+400h+var_3D0], 0EB3h
0x140183ce2  lea     rax, aMeetInstallove_0; "Meet::InstallOverwrite"
0x140183ce9  mov     [rsp+400h+var_3D8], rax
0x140183cee  lea     rax, aBaseFsRemotefs_7; "base\\fs\\remotefs\\frs\\src\\sync\\mee"...
0x140183cf5  mov     [rsp+400h+var_3E0], rax
0x140183cfa  mov     r8d, 1
0x140183d00  mov     r9d, r8d
0x140183d03  mov     edx, 4D5h
0x140183d08  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140183d0d  mov     r12, rax
0x140183d10  mov     rdi, r12
0x140183d13  mov     r13d, r14d
0x140183d16  test    r12, r12
0x140183d19  setz    r13b
0x140183d1d  test    r12, r12
0x140183d20  jnz     loc_140183E0C
0x140183d26  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140183d2d  test    rax, rax
0x140183d30  jz      loc_140183DC5
0x140183d36  cmp     [rax+40h], r14d
0x140183d3a  jz      loc_140183DC5
0x140183d40  cmp     dword ptr [rax+38h], 4
0x140183d44  jl      short loc_140183DC5
0x140183d46  lea     rax, aMeetInstallove; "Meet::InstallOverwrite"
0x140183d4d  mov     [rsp+400h+var_3A0], rax
0x140183d52  mov     [rsp+400h+var_398], 0EBCh
0x140183d5a  mov     [rsp+400h+var_394], 4
0x140183d62  lea     rax, aMeet; "MEET"
0x140183d69  mov     [rsp+400h+var_390], rax
0x140183d6e  mov     rax, [r15+318h]
0x140183d75  mov     rcx, [rax+0C8h]
0x140183d7c  add     rcx, 12h
0x140183d80  mov     qword ptr [rbp+300h+var_378], rcx
0x140183d84  mov     rcx, [r15+310h]
0x140183d8b  add     rcx, 0A8h
0x140183d92  lea     rax, [r15+40h]
0x140183d96  lea     r9, [r15+28h]
0x140183d9a  lea     r8, [r15+0C4h]
0x140183da1  lea     rdx, [rbp+300h+var_378]
0x140183da5  mov     [rsp+400h+var_3D0], rdx
0x140183daa  mov     [rsp+400h+var_3D8], rcx
0x140183daf  mov     [rsp+400h+var_3E0], rax
0x140183db4  lea     rdx, aMovingAwayCont; "Moving away content that is in the way "...
0x140183dbb  lea     rcx, [rsp+400h+var_3A0]
0x140183dc0  call    ??$DbgPrint@G$$BY0BAF@GVUID@@VGVSN@@U_GUID@@PEBG@dbgobj@@QEAA_KPEBGAEAY0BAF@$$CBGAEBVUID@@AEBVGVSN@@AEBU_GUID@@AEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort [261],UID,GVSN,_GUID,ushort const *>(ushort const *,ushort const (&)[261],UID const &,GVSN const &,_GUID const &,ushort const * const &)
0x140183dc5  mov     rax, [rbp+300h+var_368]
0x140183dc9  mov     [rsi+2C8h], rax
0x140183dd0  lea     rax, [rbp+300h+var_368]
0x140183dd4  mov     [rsp+400h+var_3D8], rax; struct Usn *
0x140183dd9  mov     rax, [rbp+300h+var_348]
0x140183ddd  mov     [rsp+400h+var_3E0], rax; struct ID_RECORD *
0x140183de2  mov     r9, [rbp+300h+var_370]; struct Meet::RelatedToUpdate *
0x140183de6  mov     r8, rsi; struct Meet::RelatedToUpdate *
0x140183de9  mov     rdx, [rbp+300h+var_358]; struct Db *
0x140183ded  mov     rcx, r15; this
0x140183df0  call    ?Move@Meet@@AEAAPEAVFrsStatus@@PEAVDb@@AEAVRelatedToUpdate@1@1AEBVID_RECORD@@AEAVUsn@@@Z; Meet::Move(Db *,Meet::RelatedToUpdate &,Meet::RelatedToUpdate &,ID_RECORD const &,Usn &)
0x140183df5  mov     r12, rax
0x140183df8  test    rax, rax
0x140183dfb  jnz     short loc_140183E0C
0x140183dfd  mov     r13d, r14d
0x140183e00  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140183e07  jmp     loc_140183EC4
0x140183e0c  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140183e13  test    rax, rax
0x140183e16  jz      loc_140183EB6
0x140183e1c  cmp     [rax+40h], r14d
0x140183e20  jz      loc_140183EB6
0x140183e26  cmp     dword ptr [rax+38h], 4
0x140183e2a  jl      loc_140183EB6
0x140183e30  lea     rax, aMeetInstallove; "Meet::InstallOverwrite"
0x140183e37  mov     [rsp+400h+var_3A0], rax
0x140183e3c  mov     [rsp+400h+var_398], 0EC5h
0x140183e44  mov     [rsp+400h+var_394], 4
0x140183e4c  lea     rax, aMeet; "MEET"
0x140183e53  mov     [rsp+400h+var_390], rax
0x140183e58  mov     rax, [r15+318h]
0x140183e5f  mov     rcx, [rax+0C8h]
0x140183e66  add     rcx, 12h
0x140183e6a  mov     [rbp+300h+var_370], rcx
0x140183e6e  mov     rcx, [r15+310h]
0x140183e75  add     rcx, 0A8h
0x140183e7c  lea     rax, [r15+40h]
0x140183e80  lea     r9, [r15+28h]
0x140183e84  lea     r8, [r15+0C4h]
0x140183e8b  lea     rdx, [rbp+300h+var_370]
0x140183e8f  mov     [rsp+400h+var_3D0], rdx
0x140183e94  mov     [rsp+400h+var_3D8], rcx
0x140183e99  mov     [rsp+400h+var_3E0], rax
0x140183e9e  lea     rdx, aMoveFailedStam; "Move failed. Stamping new gvsn updateNa"...
0x140183ea5  lea     rcx, [rsp+400h+var_3A0]
0x140183eaa  call    ??$DbgPrint@G$$BY0BAF@GVUID@@VGVSN@@U_GUID@@PEBG@dbgobj@@QEAA_KPEBGAEAY0BAF@$$CBGAEBVUID@@AEBVGVSN@@AEBU_GUID@@AEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort [261],UID,GVSN,_GUID,ushort const *>(ushort const *,ushort const (&)[261],UID const &,GVSN const &,_GUID const &,ushort const * const &)
0x140183eaf  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140183eb6  test    r12, r12
0x140183eb9  jz      short loc_140183EC4
0x140183ebb  test    rdi, rdi
0x140183ebe  jnz     loc_14018427A
0x140183ec4  test    rax, rax
0x140183ec7  jz      loc_140183F5C
0x140183ecd  cmp     [rax+40h], r14d
0x140183ed1  jz      loc_140183F5C
0x140183ed7  cmp     dword ptr [rax+38h], 5
0x140183edb  jl      short loc_140183F5C
0x140183edd  lea     rax, aMeetInstallove; "Meet::InstallOverwrite"
0x140183ee4  mov     [rsp+400h+var_3A0], rax
0x140183ee9  mov     [rsp+400h+var_398], 0ECAh
0x140183ef1  mov     [rsp+400h+var_394], 5
0x140183ef9  lea     rax, aMeet; "MEET"
  ... truncated ...
```
