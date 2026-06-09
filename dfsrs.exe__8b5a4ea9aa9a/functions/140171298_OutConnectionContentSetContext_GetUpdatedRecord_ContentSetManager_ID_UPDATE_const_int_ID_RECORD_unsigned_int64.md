# OutConnectionContentSetContext::GetUpdatedRecord(ContentSetManager *,ID_UPDATE const &,int,ID_RECORD &,unsigned __int64 &)

- ea: `0x140171298`
- end: `0x140172068`
- name: `?GetUpdatedRecord@OutConnectionContentSetContext@@AEAAPEAVFrsStatus@@PEAVContentSetManager@@AEBVID_UPDATE@@HAEAVID_RECORD@@AEA_K@Z`
- size: `3536`
- prototype: `struct FrsStatus *__fastcall(OutConnectionContentSetContext *__hidden this, struct ContentSetManager *, const struct ID_UPDATE *, int, struct ID_RECORD *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `37`
- tags: `reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140172518`

## callees

- `0x1400036a0`
- `0x1400173c0`
- `0x140024868`
- `0x140024be4`
- `0x140028fcc`
- `0x14002a6d0`
- `0x14002c1c0`
- `0x14002c2f4`
- `0x1400370bc`
- `0x1400391c4`
- `0x14006d538`
- `0x14006f224`
- `0x14007f9f4`
- `0x140082a04`
- `0x140084518`
- `0x1400923f8`
- `0x1400a6aec`
- `0x1400af320`
- `0x1400b2380`
- `0x1400bafac`
- `0x1400f8c08`
- `0x1400f9380`
- `0x140111380`
- `0x140115bd8`
- `0x140115e28`
- `0x14016e8f8`
- `0x14016e9b8`
- `0x14016ea90`
- `0x14016eb64`
- `0x14016ede4`
- `0x140171298`
- `0x140177284`
- `0x1401b3910`
- `0x1401b393c`
- `0x1401b9494`
- `0x1401bda10`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140171400`
- `KERNEL32!GetCurrentThreadId` at `0x140171e71`
- `KERNEL32!GetCurrentThreadId` at `0x140171e9c`
- `KERNEL32!GetCurrentThreadId` at `0x140171f7d`
- `KERNEL32!GetCurrentThreadId` at `0x140171fe4`
- `KERNEL32!GetCurrentThreadId` at `0x140171400`
- `KERNEL32!GetCurrentThreadId` at `0x140171e71`
- `KERNEL32!GetCurrentThreadId` at `0x140171e9c`
- `KERNEL32!GetCurrentThreadId` at `0x140171f7d`
- `KERNEL32!GetCurrentThreadId` at `0x140171fe4`

## string_xrefs

- `0x1401713a4`: `OutConnectionContentSetContext::GetUpdatedRecord`
- `0x140171451`: `OutConnectionContentSetContext::GetUpdatedRecord`
- `0x140171802`: `OutConnectionContentSetContext::GetUpdatedRecord`
- `0x1401718be`: `OutConnectionContentSetContext::GetUpdatedRecord`
- `0x14017193f`: `OutConnectionContentSetContext::GetUpdatedRecord`
- `0x140171a78`: `OutConnectionContentSetContext::GetUpdatedRecord`
- `0x140171b5e`: `OutConnectionContentSetContext::GetUpdatedRecord`
- `0x140171be4`: `OutConnectionContentSetContext::GetUpdatedRecord`
- `0x140171cfc`: `OutConnectionContentSetContext::GetUpdatedRecord`
- `0x140171e27`: `OutConnectionContentSetContext::GetUpdatedRecord`
- `0x140171f09`: `OutConnectionContentSetContext::GetUpdatedRecord`
- `0x140171df5`: `OutConnectionContentSetContext::GetUpdatedRecord`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
struct FrsStatus *__fastcall OutConnectionContentSetContext::GetUpdatedRecord(
        OutConnectionContentSetContext *this,
        struct ContentSetManager *a2,
        const struct ID_UPDATE *a3,
        int a4,
        struct ID_RECORD *a5,
        unsigned __int64 *a6)
{
  __int64 v8; // r14
  int v9; // r12d
  DWORD dwLowDateTime; // edi
  __int64 v11; // r8
  struct FrsStatus *VolumeManager; // rsi
  VolumeManager *v13; // rbx
  __int64 (__fastcall *v14)(VolumeManager *, __int128 *, _QWORD); // rdi
  DWORD CurrentThreadId; // eax
  ContentSetManager *v16; // rbx
  struct FrsStatus *FileInfo; // rax
  OutConnectionContentSetContext *v18; // rcx
  int v19; // eax
  __int64 v20; // rax
  __int64 v21; // r8
  int v22; // edx
  char v23; // r9
  __int64 v24; // rax
  const unsigned __int16 *v25; // rax
  int v26; // r8d
  __int64 v27; // r8
  ContentSetManager *v28; // rbx
  __int64 v29; // r8
  struct VsnManager *v30; // rdi
  VolumeManager *v31; // rbx
  ContentSetManager *v32; // rbx
  const unsigned __int16 *v33; // rax
  struct _FILETIME *v34; // rcx
  LPCRITICAL_SECTION v35; // rax
  const wchar_t *v36; // rdx
  __int64 v37; // r9
  const wchar_t *v38; // rdx
  int v39; // edx
  int v40; // ecx
  __int64 v41; // r8
  __int64 v42; // r9
  unsigned int v43; // eax
  __int64 v44; // rcx
  __int64 v45; // rax
  __int64 v46; // rcx
  __int64 v47; // r9
  ContentSetManager *v48; // rbx
  __int64 v49; // rcx
  DWORD v50; // eax
  __int64 v51; // rcx
  struct GVSN *v53; // [rsp+20h] [rbp-E0h]
  int v54; // [rsp+28h] [rbp-D8h]
  DWORD v55; // [rsp+38h] [rbp-C8h]
  DWORD v56; // [rsp+38h] [rbp-C8h]
  DWORD v57; // [rsp+38h] [rbp-C8h]
  const wchar_t *v58; // [rsp+50h] [rbp-B0h] BYREF
  int v59; // [rsp+58h] [rbp-A8h]
  int v60; // [rsp+5Ch] [rbp-A4h]
  const wchar_t *v61; // [rsp+60h] [rbp-A0h]
  __int64 v62; // [rsp+68h] [rbp-98h] BYREF
  struct Db *v63; // [rsp+70h] [rbp-90h] BYREF
  VolumeManager *v64; // [rsp+78h] [rbp-88h] BYREF
  ContentSetManager *v65; // [rsp+80h] [rbp-80h]
  int v66; // [rsp+88h] [rbp-78h] BYREF
  struct _FILETIME v67; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v68; // [rsp+98h] [rbp-68h] BYREF
  struct VsnManager *v69; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v70; // [rsp+A8h] [rbp-58h] BYREF
  VolumeManager *v71; // [rsp+B0h] [rbp-50h] BYREF
  OutConnectionContentSetContext *v72; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v73; // [rsp+C0h] [rbp-40h] BYREF
  const struct ID_UPDATE *v74; // [rsp+C8h] [rbp-38h]
  FilterMan *v75; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v76; // [rsp+D8h] [rbp-28h] BYREF
  int v77; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v78; // [rsp+F4h] [rbp-Ch]
  __int128 v79; // [rsp+104h] [rbp+4h]
  int v80; // [rsp+114h] [rbp+14h]
  _BYTE v81[16]; // [rsp+118h] [rbp+18h] BYREF
  unsigned int v82; // [rsp+128h] [rbp+28h]
  _OWORD v83[2]; // [rsp+138h] [rbp+38h] BYREF
  __int128 v84; // [rsp+158h] [rbp+58h]
  int v85; // [rsp+168h] [rbp+68h]
  __int128 v86; // [rsp+170h] [rbp+70h] BYREF
  __int64 v87; // [rsp+180h] [rbp+80h]
  int v88; // [rsp+208h] [rbp+108h]
  int v89; // [rsp+430h] [rbp+330h]

  LODWORD(v69) = a4;
  v74 = a3;
  v65 = a2;
  v72 = (OutConnectionContentSetContext *)a6;
  v8 = 0;
  v63 = 0;
  LODWORD(v62) = 0;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  memset(v83, 0, sizeof(v83));
  v84 = 0;
  v85 = 0;
  std::wstring::wstring(v81);
  v73 = 0;
  v66 = 0;
  ID_RECORD::ID_RECORD((ID_RECORD *)&v86);
  v9 = 1;
  dwLowDateTime = 1;
  v67.dwLowDateTime = 1;
  v70 = 0;
  v68 = 0;
  v75 = 0;
  v76 = 0;
  v64 = 0;
  VolumeManager = (struct FrsStatus *)ContentSetManager::GetVolumeManager(a2, &v64, v11);
  v13 = v64;
  if ( !VolumeManager )
  {
    if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugVolumeManagerRefCount)
      && g_DebugLog
      && LODWORD(g_DebugLog[1].LockSemaphore)
      && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v58 = L"OutConnectionContentSetContext::GetUpdatedRecord";
      v59 = 4167;
      v60 = 5;
      v61 = L"OUTC";
      v71 = v13;
      dbgobj::DbgPrint<unsigned short,unsigned __int64>(
        &v58,
        L"[VMREF] Added reference to volume manager. ptr:%p",
        &v71);
    }
    VolumeManager = (struct FrsStatus *)VolumeManager::GetFilterMan(v13);
    if ( !VolumeManager )
    {
      v14 = *(__int64 (__fastcall **)(VolumeManager *, __int128 *, _QWORD))(*(_QWORD *)v13 + 32LL);
      CurrentThreadId = GetCurrentThreadId();
      VolumeManager = (struct FrsStatus *)v14(v13, &v76, CurrentThreadId);
      dwLowDateTime = v67.dwLowDateTime;
    }
  }
  if ( v13 )
  {
    if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugVolumeManagerRefCount)
      && g_DebugLog
      && LODWORD(g_DebugLog[1].LockSemaphore)
      && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v58 = L"OutConnectionContentSetContext::GetUpdatedRecord";
      v59 = 4175;
      v60 = 5;
      v61 = L"OUTC";
      v71 = v13;
      dbgobj::DbgPrint<unsigned short,unsigned __int64>(
        &v58,
        L"[VMREF] Release reference to volume manager. ptr:%p",
        &v71);
    }
    ScopedRef<VolumeManager::ShutdownRestartTask>::Set(&v64, 0);
  }
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v64);
  if ( VolumeManager )
    goto LABEL_21;
  (*(void (__fastcall **)(_QWORD, struct Db **))(*(_QWORD *)v76 + 48LL))(v76, &v63);
  while ( 1 )
  {
    while ( 1 )
    {
      if ( !VolumeManager )
      {
        VolumeManager = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, _QWORD))(*(_QWORD *)v63 + 16LL))(
                                              v63,
                                              dwLowDateTime);
        if ( !VolumeManager )
          VolumeManager = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, __int64 *, const struct ID_UPDATE *, struct ID_RECORD *))(*(_QWORD *)v63 + 56LL))(
                                                v63,
                                                &v62,
                                                v74,
                                                a5);
      }
LABEL_21:
      if ( (_DWORD)v69 || !dwLowDateTime )
      {
        if ( !(_DWORD)v62 )
          goto LABEL_30;
        if ( !VolumeManager )
          VolumeManager = (struct FrsStatus *)DbUtil::LockRecord(v63, (__int64)&v62);
      }
      if ( !(_DWORD)v62 || !(unsigned int)ID_RECORD::Alive(a5) )
      {
LABEL_30:
        v16 = v65;
        goto LABEL_31;
      }
      if ( VolumeManager )
        goto LABEL_35;
      v16 = v65;
      FileInfo = (struct FrsStatus *)NtfsFileSystem::GetFileInfo(
                                       OutConnectionContentSetContext::fs,
                                       (char *)v65 + 208,
                                       (char *)a5 + 688,
                                       &v70,
                                       &v73,
                                       v81,
                                       0,
                                       v83,
                                       &v77,
                                       0);
      v18 = v72;
      *(_QWORD *)v72 = DWORD1(v84) | ((unsigned __int64)(unsigned int)v84 << 32);
      VolumeManager = OutConnectionContentSetContext::WrapFileNotFound(v18, FileInfo);
LABEL_31:
      if ( !VolumeManager && (unsigned int)ID_RECORD::Alive(a5) && (*((_DWORD *)a5 + 37) & 0x400) != 0 )
        VolumeManager = NtfsFileSystem::ReparsePointCanBeMarshaled(
                          (NtfsFileSystem *)OutConnectionContentSetContext::fs,
                          (ContentSetManager *)((char *)v16 + 208),
                          (struct ID_RECORD *)((char *)a5 + 688),
                          (int *)&v67,
                          &v68);
LABEL_35:
      if ( (_DWORD)v62 && (unsigned int)ID_RECORD::Alive(a5) )
      {
        if ( VolumeManager )
          goto LABEL_129;
        if ( *((_QWORD *)a5 + 2) == 1 )
        {
          v86 = *((_OWORD *)a5 + 3);
          v87 = *((_QWORD *)a5 + 8);
          v88 |= 1u;
          v89 &= ~8u;
          v19 = 1;
          v66 = 1;
          goto LABEL_43;
        }
        v20 = *(_QWORD *)v63;
        v71 = 0;
        VolumeManager = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, int *, __int64 *, __int128 *, VolumeManager **))(v20 + 40))(
                                              v63,
                                              &v66,
                                              &v73,
                                              &v86,
                                              &v71);
      }
      if ( VolumeManager )
        goto LABEL_129;
      v19 = v66;
LABEL_43:
      if ( !(_DWORD)v62 || (*((_BYTE *)a5 + 152) & 1) == 0 )
        goto LABEL_130;
      if ( (*((_DWORD *)a5 + 176) & 8) != 0 )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v59 = 4243;
          v36 = L"The record is marked to be a tombstone. connId:%? rgName:%? record:%?";
LABEL_103:
          v58 = L"OutConnectionContentSetContext::GetUpdatedRecord";
          v37 = *((_QWORD *)this + 28);
          v60 = 5;
          v61 = L"OUTC";
          dbgobj::DbgPrint<unsigned short,_GUID,FrsStringImpl<unsigned short,char>,ID_RECORD>(
            (unsigned int)&v58,
            (_DWORD)v36,
            (_DWORD)this + 64,
            v37 + 72,
            (__int64)a5);
        }
LABEL_98:
        v9 = 0;
        goto LABEL_130;
      }
      if ( !v19 )
      {
        if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 5 )
          goto LABEL_98;
        v59 = 4250;
        v38 = L"Parent does not exist in the database. pid:%? connId:%? rgName:%? record:%?";
LABEL_120:
        v58 = L"OutConnectionContentSetContext::GetUpdatedRecord";
        v61 = L"OUTC";
        v53 = (struct GVSN *)(*((_QWORD *)this + 28) + 72LL);
        v60 = 5;
        dbgobj::DbgPrint<unsigned short,FileId,_GUID,FrsStringImpl<unsigned short,char>,ID_RECORD>(
          (unsigned int)&v58,
          (_DWORD)v38,
          (unsigned int)&v73,
          (_DWORD)this + 64,
          (__int64)v53,
          (__int64)a5);
        goto LABEL_98;
      }
      if ( !(unsigned int)ID_RECORD::Alive((ID_RECORD *)&v86) )
      {
        if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 5 )
          goto LABEL_98;
        v59 = 4260;
        v38 = L"Parent is a tombstone. pid:%? connId:%? rgName:%? record:%?";
        goto LABEL_120;
      }
      if ( !(unsigned __int8)GVSN::operator==(&v86, (char *)a5 + 48, v21) )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v59 = 4269;
          v36 = L"Database has a stale parent. connId:%? rgName:%? record:%?";
          goto LABEL_103;
        }
        goto LABEL_98;
      }
      if ( (v23 & 2) != 0 )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v59 = 4278;
          v36 = L"Record is marked pending journal wrap recovery. connId:%? rgName:%? record:%?";
          goto LABEL_103;
        }
        goto LABEL_98;
      }
      if ( (v23 & 4) != 0 )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v59 = 4286;
          v36 = L"Record is marked pending journal loss validation. connId:%? rgName:%? record:%?";
          goto LABEL_103;
        }
        goto LABEL_98;
      }
      if ( (v23 & 0x40) != 0 )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v59 = 4294;
          v36 = L"Record is marked pending dirty shutdown recovery. connId:%? rgName:%? record:%?";
          goto LABEL_103;
        }
        goto LABEL_98;
      }
      v24 = *((_QWORD *)a5 + 85);
      if ( v24 > v70 )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v58 = L"OutConnectionContentSetContext::GetUpdatedRecord";
          v59 = 4305;
          v60 = 5;
          v61 = L"OUTC";
          dbgobj::DbgPrint<unsigned short,_GUID,FrsStringImpl<unsigned short,char>,ID_RECORD,Usn>(
            (unsigned int)&v58,
            v22,
            (_DWORD)this + 64,
            *((_QWORD *)this + 28) + 72,
            (__int64)a5,
            (__int64)&v70);
        }
        goto LABEL_98;
      }
      if ( v24 != v70 )
        break;
      if ( (v23 & 1) != 0 )
        goto LABEL_130;
      if ( !dwLowDateTime )
      {
        v28 = v65;
        if ( !(unsigned int)ContentSetManager::IsSubordinate(v65)
          || !(unsigned int)ContentSetManager::IsLocalSubordinateUpdate(v28, (struct DbManagerInstance *)&v76, a5)
          || (unsigned __int8)GVSN::operator==((char *)v74 + 24, (char *)a5 + 24, v29) )
        {
          *((_DWORD *)a5 + 176) |= 1u;
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            v58 = L"OutConnectionContentSetContext::GetUpdatedRecord";
            v59 = 4332;
            v60 = 4;
            v61 = L"OUTC";
            dbgobj::DbgPrint<unsigned short,ID_RECORD>(&v58, L"LDB Updating ID Record:%?", a5);
          }
          VolumeManager = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, struct ID_RECORD *, struct ID_RECORD *, _QWORD))(*(_QWORD *)v63 + 200LL))(
                                                v63,
                                                a5,
                                                a5,
                                                0);
        }
        goto LABEL_130;
      }
      dwLowDateTime = 0;
      VolumeManager = DbUtil::CommitTransaction(v63, 0, 0);
    }
    v25 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v81);
    if ( (unsigned int)FilterMan::Match(v75, (const struct _GUID *)((char *)a5 + 72), v25, v82, v26, v54) )
    {
LABEL_129:
      v9 = 0;
      goto LABEL_130;
    }
    if ( !dwLowDateTime )
      break;
    VolumeManager = DbUtil::CommitTransaction(v63, 0, 0);
    dwLowDateTime = 0;
  }
  v67 = *(struct _FILETIME *)((char *)&v79 + 4);
  v30 = 0;
  v69 = 0;
  v64 = 0;
  VolumeManager = (struct FrsStatus *)ContentSetManager::GetVolumeManager(v65, &v64, v27);
  v31 = v64;
  if ( !VolumeManager )
  {
    if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugVolumeManagerRefCount)
      && g_DebugLog
      && LODWORD(g_DebugLog[1].LockSemaphore)
      && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v58 = L"OutConnectionContentSetContext::GetUpdatedRecord";
      v59 = 4367;
      v60 = 5;
      v61 = L"OUTC";
      v72 = v31;
      dbgobj::DbgPrint<unsigned short,unsigned __int64>(
        &v58,
        L"[VMREF] Added reference to volume manager. ptr:%p",
        &v72);
    }
    VolumeManager = (struct FrsStatus *)VolumeManager::GetVsnManager(v31);
    v30 = v69;
  }
  if ( v31 )
  {
    if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugVolumeManagerRefCount)
      && g_DebugLog
      && LODWORD(g_DebugLog[1].LockSemaphore)
      && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v58 = L"OutConnectionContentSetContext::GetUpdatedRecord";
      v59 = 4371;
      v60 = 5;
      v61 = L"OUTC";
      v72 = v31;
      dbgobj::DbgPrint<unsigned short,unsigned __int64>(
        &v58,
        L"[VMREF] Release reference to volume manager. ptr:%p",
        &v72);
    }
    ScopedRef<VolumeManager::ShutdownRestartTask>::Set(&v64, 0);
  }
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v64);
  if ( !VolumeManager )
  {
    v32 = v65;
    GetNextVersion(
      v30,
      v63,
      (const struct _GUID *)((char *)v65 + 168),
      (struct ID_RECORD *)((char *)a5 + 40),
      (struct ID_RECORD *)((char *)a5 + 24));
    *((_DWORD *)a5 + 37) = HIDWORD(v79);
    *((_QWORD *)a5 + 85) = v70;
    v33 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v81);
    StringCchCopyW((unsigned __int16 *)a5 + 78, 0x105u, v33);
    *(_OWORD *)((char *)a5 + 88) = 0;
    *((_DWORD *)a5 + 26) = 0;
    *(_OWORD *)((char *)a5 + 108) = 0;
    *((_DWORD *)a5 + 38) &= ~0x10u;
    *((_DWORD *)a5 + 176) = *((_DWORD *)a5 + 176) & 0xFFFFFE7E | 1;
    FileTime::Increment((struct _FILETIME *)((char *)a5 + 132));
    FileTime::Max(v34, &v67);
    VolumeManager = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, char *, __int64))(*(_QWORD *)v63 + 224LL))(
                                          v63,
                                          (char *)a5 + 40,
                                          (__int64)v32 + 168);
    if ( !VolumeManager )
    {
      v35 = g_DebugLog;
      if ( g_DebugLog )
      {
        if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          v58 = L"OutConnectionContentSetContext::GetUpdatedRecord";
          v59 = 4401;
          v60 = 5;
          v61 = L"OUTC";
          dbgobj::DbgPrint<unsigned short,_GUID,FrsStringImpl<unsigned short,char>,ID_RECORD>(
            (unsigned int)&v58,
            (unsigned int)L"Updating Record. connId:%? rgName:%? record:%?",
            (_DWORD)this + 64,
            *((_QWORD *)this + 28) + 72,
            (__int64)a5);
          v35 = g_DebugLog;
        }
        if ( v35 && LODWORD(v35[1].LockSemaphore) && SLODWORD(v35[1].OwningThread) >= 4 )
        {
          v58 = L"OutConnectionContentSetContext::GetUpdatedRecord";
          v59 = 4405;
          v60 = 4;
          v61 = L"OUTC";
          dbgobj::DbgPrint<unsigned short,ID_RECORD>(&v58, L"LDB Updating ID Record:%?", a5);
        }
      }
      VolumeManager = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, struct ID_RECORD *, struct ID_RECORD *, _QWORD))(*(_QWORD *)v63 + 200LL))(
                                            v63,
                                            a5,
                                            a5,
                                            0);
    }
  }
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v69);
LABEL_130:
  if ( (unsigned int)MarshalContext::ReplicateReparseFile(v68) )
  {
    v43 = *((_DWORD *)a5 + 37) & 0xFFFFFBFF;
    *((_DWORD *)a5 + 37) = v43;
    if ( v40 == -2147483629 )
      *((_DWORD *)a5 + 37) = v43 & 0xFFFFFDFF;
  }
  if ( !VolumeManager )
  {
    if ( v9 )
    {
      if ( !(_DWORD)v62 )
      {
        v56 = GetCurrentThreadId();
        v45 = FrsStatusList::PushNewError(
                v46,
                9059,
                0,
                3,
                "base\\fs\\remotefs\\frs\\src\\sync\\outconnection.cpp",
                "OutConnectionContentSetContext::GetUpdatedRecord",
                4438,
                v56,
                0);
        goto LABEL_142;
      }
      if ( !(unsigned __int8)GVSN::operator==((char *)v74 + 24, (char *)a5 + 24, v41) )
      {
        if ( v47 && *(_DWORD *)(v47 + 64) && *(int *)(v47 + 56) >= 4 )
        {
          v58 = L"OutConnectionContentSetContext::GetUpdatedRecord";
          v59 = 4443;
          v60 = 4;
          v61 = L"OUTC";
          dbgobj::DbgPrint<unsigned short,GVSN,_GUID,FrsStringImpl<unsigned short,char>>(
            (unsigned int)&v58,
            (unsigned int)L"Version has changed to gsvn:%? connId:%? rgName:%?",
            (_DWORD)a5 + 24,
            (_DWORD)this + 64,
            *((_QWORD *)this + 28) + 72LL);
        }
        v48 = v65;
        if ( (unsigned int)ContentSetManager::IsSubordinate(v65) )
        {
          if ( (unsigned int)ContentSetManager::IsLocalSubordinateUpdate(v48, (struct DbManagerInstance *)&v76, a5) )
          {
            v57 = GetCurrentThreadId();
            v45 = FrsStatusList::PushNewError(
                    v49,
                    9072,
                    0,
                    3,
                    "base\\fs\\remotefs\\frs\\src\\sync\\outconnection.cpp",
                    "OutConnectionContentSetContext::GetUpdatedRecord",
                    4450,
                    v57,
                    0);
            goto LABEL_142;
          }
        }
      }
    }
    else
    {
      if ( v42 && *(_DWORD *)(v42 + 64) && *(int *)(v42 + 56) >= 4 )
      {
        v58 = L"OutConnectionContentSetContext::GetUpdatedRecord";
        v59 = 4428;
        v60 = 4;
        v61 = L"OUTC";
        dbgobj::DbgPrint<unsigned short,UID,_GUID,FrsStringImpl<unsigned short,char>>(
          (unsigned int)&v58,
          v39,
          (_DWORD)v74,
          (_DWORD)this + 64,
          *((_QWORD *)this + 28) + 72LL);
      }
      v55 = GetCurrentThreadId();
      v45 = FrsStatusList::PushNewError(
              v44,
              9024,
              0,
              3,
              "base\\fs\\remotefs\\frs\\src\\sync\\outconnection.cpp",
              "OutConnectionContentSetContext::GetUpdatedRecord",
              4432,
              v55,
              0);
LABEL_142:
      VolumeManager = (struct FrsStatus *)v45;
    }
  }
  if ( v63 )
  {
    VolumeManager = DbUtil::CommitTransaction(v63, VolumeManager, 0);
    (*(void (__fastcall **)(_QWORD, struct Db **))(*(_QWORD *)v76 + 64LL))(v76, &v63);
  }
  if ( VolumeManager )
  {
    v50 = GetCurrentThreadId();
    v8 = FrsStatusList::PushNewError(
           v51,
           *((unsigned int *)VolumeManager + 1),
           *((unsigned int *)VolumeManager + 2),
           *(unsigned int *)VolumeManager,
           "base\\fs\\remotefs\\frs\\src\\sync\\outconnection.cpp",
           "OutConnectionContentSetContext::GetUpdatedRecord",
           4461,
           v50,
           VolumeManager);
  }
  DbManagerInstance::FinalizeDbManagerInstance((DbManagerInstance *)&v76);
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v75);
  std::wstring::~wstring(v81);
  return (struct FrsStatus *)v8;
}

```

## disassembly

```asm
0x140171298  mov     [rsp-8+arg_18], rbx
0x14017129d  push    rbp
0x14017129e  push    rsi
0x14017129f  push    rdi
0x1401712a0  push    r12
0x1401712a2  push    r13
0x1401712a4  push    r14
0x1401712a6  push    r15
0x1401712a8  lea     rbp, [rsp-350h]
0x1401712b0  sub     rsp, 450h
0x1401712b7  mov     rax, cs:__security_cookie
0x1401712be  xor     rax, rsp
0x1401712c1  mov     [rbp+380h+var_40], rax
0x1401712c8  mov     dword ptr [rbp+380h+var_3E0], r9d
0x1401712cc  mov     [rbp+380h+var_3B8], r8
0x1401712d0  mov     rbx, rdx
0x1401712d3  mov     [rbp+380h+var_400], rdx
0x1401712d7  mov     r13, rcx
0x1401712da  mov     r15, [rbp+380h+arg_20]
0x1401712e1  mov     rax, [rbp+380h+arg_28]
0x1401712e8  mov     [rbp+380h+var_3C8], rax
0x1401712ec  xor     r14d, r14d
0x1401712ef  mov     [rsp+480h+var_410], r14
0x1401712f4  mov     dword ptr [rsp+480h+var_418], r14d
0x1401712f9  mov     [rbp+380h+var_390], r14d
0x1401712fd  xorps   xmm0, xmm0
0x140171300  xor     eax, eax
0x140171302  movups  [rbp+380h+var_38C], xmm0
0x140171306  movups  [rbp+380h+var_37C], xmm0
0x14017130a  mov     [rbp+380h+var_36C], eax
0x14017130d  xorps   xmm1, xmm1
0x140171310  movups  [rbp+380h+var_348], xmm1
0x140171314  movups  [rbp+380h+var_338], xmm1
0x140171318  movups  [rbp+380h+var_328], xmm1
0x14017131c  mov     [rbp+380h+var_318], eax
0x14017131f  lea     rcx, [rbp+380h+var_368]
0x140171323  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140171328  nop
0x140171329  mov     [rbp+380h+var_3C0], r14
0x14017132d  mov     [rbp+380h+var_3F8], r14d
0x140171331  lea     rcx, [rbp+380h+var_310]; this
0x140171335  call    ??0ID_RECORD@@QEAA@XZ; ID_RECORD::ID_RECORD(void)
0x14017133a  lea     r12d, [r14+1]
0x14017133e  mov     edi, r12d
0x140171341  mov     [rbp+380h+var_3F0.dwLowDateTime], r12d
0x140171345  mov     [rbp+380h+var_3D8], r14
0x140171349  mov     [rbp+380h+var_3E8], r14d
0x14017134d  mov     [rbp+380h+var_3B0], r14
0x140171351  xorps   xmm0, xmm0
0x140171354  movdqu  [rbp+380h+var_3A8], xmm0
0x140171359  mov     [rsp+480h+var_408], r14
0x14017135e  lea     rdx, [rsp+480h+var_408]
0x140171363  mov     rcx, rbx
0x140171366  call    ?GetVolumeManager@ContentSetManager@@QEAAPEAVFrsStatus@@AEAV?$ScopedRef@VVolumeManager@@@@@Z; ContentSetManager::GetVolumeManager(ScopedRef<VolumeManager> &)
0x14017136b  mov     rsi, rax
0x14017136e  mov     rbx, [rsp+480h+var_408]
0x140171373  test    rax, rax
0x140171376  jnz     loc_140171424
0x14017137c  lea     rcx, ?DebugVolumeManagerRefCount@Settings@@3VCDebugVolumeManagerRefCount@1@A; Settings::CDebugVolumeManagerRefCount Settings::DebugVolumeManagerRefCount
0x140171383  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x140171388  test    eax, eax
0x14017138a  jz      short loc_1401713E5
0x14017138c  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140171393  test    rax, rax
0x140171396  jz      short loc_1401713E5
0x140171398  cmp     [rax+40h], r14d
0x14017139c  jz      short loc_1401713E5
0x14017139e  cmp     dword ptr [rax+38h], 5
0x1401713a2  jl      short loc_1401713E5
0x1401713a4  lea     rax, aOutconnectionc; "OutConnectionContentSetContext::GetUpda"...
0x1401713ab  mov     [rsp+480h+var_430], rax
0x1401713b0  mov     [rsp+480h+var_428], 1047h
0x1401713b8  mov     [rsp+480h+var_424], 5
0x1401713c0  lea     rax, aOutc; "OUTC"
0x1401713c7  mov     [rsp+480h+var_420], rax
0x1401713cc  mov     [rbp+380h+var_3D0], rbx
0x1401713d0  lea     r8, [rbp+380h+var_3D0]
0x1401713d4  lea     rdx, aVmrefAddedRefe; "[VMREF] Added reference to volume manag"...
0x1401713db  lea     rcx, [rsp+480h+var_430]
0x1401713e0  call    ??$DbgPrint@G_K@dbgobj@@QEAA_KPEBGAEB_K@Z; dbgobj::DbgPrint<ushort,unsigned __int64>(ushort const *,unsigned __int64 const &)
0x1401713e5  lea     rdx, [rbp+380h+var_3B0]
0x1401713e9  mov     rcx, rbx; this
0x1401713ec  call    ?GetFilterMan@VolumeManager@@QEAAPEAVFrsStatus@@AEAV?$ScopedRef@VFilterMan@@@@@Z; VolumeManager::GetFilterMan(ScopedRef<FilterMan> &)
0x1401713f1  mov     rsi, rax
0x1401713f4  test    rax, rax
0x1401713f7  jnz     short loc_140171424
0x1401713f9  mov     rax, [rbx]
0x1401713fc  mov     rdi, [rax+20h]
0x140171400  call    cs:__imp_GetCurrentThreadId
0x140171407  nop     dword ptr [rax+rax+00h]
0x14017140c  mov     r8d, eax
0x14017140f  lea     rdx, [rbp+380h+var_3A8]
0x140171413  mov     rcx, rbx
0x140171416  mov     rax, rdi
0x140171419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14017141e  mov     rsi, rax
0x140171421  mov     edi, [rbp+380h+var_3F0.dwLowDateTime]
0x140171424  test    rbx, rbx
0x140171427  jz      short loc_14017149F
0x140171429  lea     rcx, ?DebugVolumeManagerRefCount@Settings@@3VCDebugVolumeManagerRefCount@1@A; Settings::CDebugVolumeManagerRefCount Settings::DebugVolumeManagerRefCount
0x140171430  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x140171435  test    eax, eax
0x140171437  jz      short loc_140171492
0x140171439  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140171440  test    rax, rax
0x140171443  jz      short loc_140171492
0x140171445  cmp     [rax+40h], r14d
0x140171449  jz      short loc_140171492
0x14017144b  cmp     dword ptr [rax+38h], 5
0x14017144f  jl      short loc_140171492
0x140171451  lea     rax, aOutconnectionc; "OutConnectionContentSetContext::GetUpda"...
0x140171458  mov     [rsp+480h+var_430], rax
0x14017145d  mov     [rsp+480h+var_428], 104Fh
0x140171465  mov     [rsp+480h+var_424], 5
0x14017146d  lea     rax, aOutc; "OUTC"
0x140171474  mov     [rsp+480h+var_420], rax
0x140171479  mov     [rbp+380h+var_3D0], rbx
0x14017147d  lea     r8, [rbp+380h+var_3D0]
0x140171481  lea     rdx, aVmrefReleaseRe; "[VMREF] Release reference to volume man"...
0x140171488  lea     rcx, [rsp+480h+var_430]
0x14017148d  call    ??$DbgPrint@G_K@dbgobj@@QEAA_KPEBGAEB_K@Z; dbgobj::DbgPrint<ushort,unsigned __int64>(ushort const *,unsigned __int64 const &)
0x140171492  xor     edx, edx
0x140171494  lea     rcx, [rsp+480h+var_408]
0x140171499  call    ?Set@?$ScopedRef@VShutdownRestartTask@VolumeManager@@@@AEAAXPEAVShutdownRestartTask@VolumeManager@@@Z; ScopedRef<VolumeManager::ShutdownRestartTask>::Set(VolumeManager::ShutdownRestartTask *)
0x14017149e  nop
0x14017149f  lea     rcx, [rsp+480h+var_408]
0x1401714a4  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x1401714a9  test    rsi, rsi
0x1401714ac  jnz     short loc_140171503
0x1401714ae  mov     rcx, qword ptr [rbp+380h+var_3A8]
0x1401714b2  mov     rax, [rcx]
0x1401714b5  lea     rdx, [rsp+480h+var_410]
0x1401714ba  mov     rax, [rax+30h]
0x1401714be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401714c3  test    rsi, rsi
0x1401714c6  jnz     short loc_140171503
0x1401714c8  mov     rcx, [rsp+480h+var_410]
0x1401714cd  mov     rax, [rcx]
0x1401714d0  mov     edx, edi
0x1401714d2  mov     rax, [rax+10h]
0x1401714d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401714db  mov     rsi, rax
0x1401714de  test    rax, rax
0x1401714e1  jnz     short loc_140171503
0x1401714e3  mov     rcx, [rsp+480h+var_410]
0x1401714e8  mov     rax, [rcx]
0x1401714eb  mov     r9, r15
0x1401714ee  mov     r8, [rbp+380h+var_3B8]
0x1401714f2  lea     rdx, [rsp+480h+var_418]
0x1401714f7  mov     rax, [rax+38h]
0x1401714fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140171500  mov     rsi, rax
0x140171503  cmp     dword ptr [rbp+380h+var_3E0], r14d
0x140171507  jnz     short loc_14017150D
0x140171509  test    edi, edi
0x14017150b  jnz     short loc_14017153E
0x14017150d  cmp     dword ptr [rsp+480h+var_418], r14d
0x140171512  jz      loc_1401715CF
0x140171518  test    rsi, rsi
0x14017151b  jnz     short loc_14017153E
0x14017151d  lea     rax, [rsp+480h+var_418]
0x140171522  mov     [rsp+480h+var_460], rax; __int64
0x140171527  lea     r9, [rbp+380h+var_3F0]
0x14017152b  xor     r8d, r8d
0x14017152e  mov     rdx, r15
0x140171531  mov     rcx, [rsp+480h+var_410]; this
0x140171536  call    ?LockRecord@DbUtil@@SAPEAVFrsStatus@@PEAVDb@@AEAVID_RECORD@@PEAV?$DbIterator@VID_RECORD@@@@PEAH3@Z; DbUtil::LockRecord(Db *,ID_RECORD &,DbIterator<ID_RECORD> *,int *,int *)
0x14017153b  mov     rsi, rax
0x14017153e  cmp     dword ptr [rsp+480h+var_418], r14d
0x140171543  jz      loc_1401715CF
0x140171549  mov     rcx, r15; this
0x14017154c  call    ?Alive@ID_RECORD@@QEBAHXZ; ID_RECORD::Alive(void)
0x140171551  test    eax, eax
0x140171553  jz      short loc_1401715CF
0x140171555  test    rsi, rsi
0x140171558  jnz     loc_14017161B
0x14017155e  lea     r8, [r15+2B0h]
0x140171565  mov     rbx, [rbp+380h+var_400]
0x140171569  lea     rdx, [rbx+0D0h]
0x140171570  mov     [rsp+480h+var_438], r14
0x140171575  lea     rax, [rbp+380h+var_390]
0x140171579  mov     [rsp+480h+var_440], rax
0x14017157e  lea     rax, [rbp+380h+var_348]
0x140171582  mov     [rsp+480h+var_448], rax
0x140171587  mov     [rsp+480h+var_450], r14
0x14017158c  lea     rax, [rbp+380h+var_368]
0x140171590  mov     [rsp+480h+var_458], rax
0x140171595  lea     rax, [rbp+380h+var_3C0]
0x140171599  mov     [rsp+480h+var_460], rax
0x14017159e  lea     r9, [rbp+380h+var_3D8]
0x1401715a2  lea     rcx, ?fs@OutConnectionContentSetContext@@0VNtfsFileSystem@@A; NtfsFileSystem OutConnectionContentSetContext::fs
0x1401715a9  call    ?GetFileInfo@NtfsFileSystem@@UEAAPEAVFrsStatus@@AEBVVolumeId@@AEBVFileId@@PEAVUsn@@PEAV4@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVFilePath@@PEAU_BY_HANDLE_FILE_INFORMATION@@PEAU_FILE_BASIC_INFORMATION@@PEAU_FILE_STANDARD_INFORMATION@@@Z; NtfsFileSystem::GetFileInfo(VolumeId const &,FileId const &,Usn *,FileId *,std::wstring *,FilePath *,_BY_HANDLE_FILE_INFORMATION *,_FILE_BASIC_INFORMATION *,_FILE_STANDARD_INFORMATION *)
0x1401715ae  mov     edx, dword ptr [rbp+380h+var_328]
0x1401715b1  shl     rdx, 20h
0x1401715b5  mov     ecx, dword ptr [rbp+380h+var_328+4]
0x1401715b8  or      rdx, rcx
0x1401715bb  mov     rcx, [rbp+380h+var_3C8]; this
0x1401715bf  mov     [rcx], rdx
0x1401715c2  mov     rdx, rax; struct FrsStatus *
0x1401715c5  call    ?WrapFileNotFound@OutConnectionContentSetContext@@AEAAPEAVFrsStatus@@PEAV2@@Z; OutConnectionContentSetContext::WrapFileNotFound(FrsStatus *)
0x1401715ca  mov     rsi, rax
0x1401715cd  jmp     short loc_1401715D3
0x1401715cf  mov     rbx, [rbp+380h+var_400]
0x1401715d3  test    rsi, rsi
0x1401715d6  jnz     short loc_14017161B
0x1401715d8  mov     rcx, r15; this
0x1401715db  call    ?Alive@ID_RECORD@@QEBAHXZ; ID_RECORD::Alive(void)
0x1401715e0  test    eax, eax
0x1401715e2  jz      short loc_14017161B
0x1401715e4  test    dword ptr [r15+94h], 400h
0x1401715ef  jz      short loc_14017161B
0x1401715f1  lea     r8, [r15+2B0h]; struct FileId *
0x1401715f8  lea     rdx, [rbx+0D0h]; struct VolumeId *
0x1401715ff  lea     rax, [rbp+380h+var_3E8]
0x140171603  mov     [rsp+480h+var_460], rax; unsigned int *
0x140171608  lea     r9, [rbp+380h+var_3F0]; int *
0x14017160c  lea     rcx, ?fs@OutConnectionContentSetContext@@0VNtfsFileSystem@@A; this
0x140171613  call    ?ReparsePointCanBeMarshaled@NtfsFileSystem@@UEAAPEAVFrsStatus@@AEBVVolumeId@@AEBVFileId@@AEAHAEAK@Z; NtfsFileSystem::ReparsePointCanBeMarshaled(VolumeId const &,FileId const &,int &,ulong &)
0x140171618  mov     rsi, rax
0x14017161b  cmp     dword ptr [rsp+480h+var_418], r14d
0x140171620  jz      short loc_140171695
0x140171622  mov     rcx, r15; this
0x140171625  call    ?Alive@ID_RECORD@@QEBAHXZ; ID_RECORD::Alive(void)
0x14017162a  test    eax, eax
0x14017162c  jz      short loc_140171695
0x14017162e  test    rsi, rsi
0x140171631  jnz     loc_140171DBA
0x140171637  cmp     [r15+10h], r12
0x14017163b  jnz     short loc_140171668
0x14017163d  movups  xmm0, xmmword ptr [r15+30h]
0x140171642  movdqu  [rbp+380h+var_310], xmm0
0x140171647  mov     rax, [r15+40h]
0x14017164b  mov     [rbp+380h+var_300], rax
0x140171652  or      [rbp+380h+var_278], r12d
0x140171659  and     [rbp+380h+var_50], 0FFFFFFF7h
0x140171660  mov     eax, r12d
0x140171663  mov     [rbp+380h+var_3F8], eax
0x140171666  jmp     short loc_1401716A1
0x140171668  mov     rcx, [rsp+480h+var_410]
0x14017166d  mov     rax, [rcx]
0x140171670  mov     [rbp+380h+var_3D0], r14
0x140171674  lea     rdx, [rbp+380h+var_3D0]
0x140171678  mov     [rsp+480h+var_460], rdx
0x14017167d  lea     r9, [rbp+380h+var_310]
0x140171681  lea     r8, [rbp+380h+var_3C0]
0x140171685  lea     rdx, [rbp+380h+var_3F8]
0x140171689  mov     rax, [rax+28h]
0x14017168d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140171692  mov     rsi, rax
0x140171695  test    rsi, rsi
0x140171698  jnz     loc_140171DBA
0x14017169e  mov     eax, [rbp+380h+var_3F8]
0x1401716a1  cmp     dword ptr [rsp+480h+var_418], r14d
0x1401716a6  jz      loc_140171DBD
0x1401716ac  test    [r15+98h], r12b
0x1401716b3  jz      loc_140171DBD
0x1401716b9  mov     r9d, [r15+2C0h]
0x1401716c0  test    r9b, 8
0x1401716c4  jnz     loc_140171D81
0x1401716ca  test    eax, eax
0x1401716cc  jz      loc_140171D48
0x1401716d2  lea     rcx, [rbp+380h+var_310]; this
0x1401716d6  call    ?Alive@ID_RECORD@@QEBAHXZ; ID_RECORD::Alive(void)
0x1401716db  test    eax, eax
0x1401716dd  jz      loc_140171CC8
0x1401716e3  lea     rdx, [r15+30h]
0x1401716e7  lea     rcx, [rbp+380h+var_310]
0x1401716eb  call    ??8GVSN@@QEBA_NAEBV0@@Z; GVSN::operator==(GVSN const &)
0x1401716f0  test    al, al
0x1401716f2  jz      loc_140171C8F
0x1401716f8  test    r9b, 2
0x1401716fc  jnz     loc_140171C56
0x140171702  test    r9b, 4
0x140171706  jnz     loc_140171C24
0x14017170c  test    r9b, 40h
0x140171710  jnz     loc_140171BBC
0x140171716  mov     rax, [r15+2A8h]
0x14017171d  cmp     rax, [rbp+380h+var_3D8]
0x140171721  jg      loc_140171B45
0x140171727  jnz     short loc_140171750
0x140171729  test    r12b, r9b
0x14017172c  jnz     loc_140171DBD
0x140171732  test    edi, edi
0x140171734  jz      short loc_1401717A7
0x140171736  mov     edi, r14d
0x140171739  xor     r8d, r8d; int
0x14017173c  xor     edx, edx; struct FrsStatus *
0x14017173e  mov     rcx, [rsp+480h+var_410]; struct Db *
0x140171743  call    ?CommitTransaction@DbUtil@@SAPEAVFrsStatus@@PEAVDb@@PEAV2@H@Z; DbUtil::CommitTransaction(Db *,FrsStatus *,int)
0x140171748  mov     rsi, rax
0x14017174b  jmp     loc_1401714C3
0x140171750  mov     r8d, [r15+94h]
0x140171757  and     r8d, 10h
0x14017175b  lea     rcx, [rbp+380h+var_368]
0x14017175f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140171764  lea     rdx, [r15+48h]; struct _GUID *
0x140171768  mov     dword ptr [rsp+480h+var_460], r8d; int
0x14017176d  mov     r9d, [rbp+380h+var_358]; unsigned int
0x140171771  mov     r8, rax; unsigned __int16 *
0x140171774  mov     rcx, [rbp+380h+var_3B0]; this
  ... truncated ...
```
