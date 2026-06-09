# Join::SubmitUpdate(Db *,ID_RECORD &,IUpdateBuffer *)

- ea: `0x14019555c`
- end: `0x1401961e5`
- name: `?SubmitUpdate@Join@@AEAAPEAVFrsStatus@@PEAVDb@@AEAVID_RECORD@@PEAVIUpdateBuffer@@@Z`
- size: `3209`
- prototype: `struct FrsStatus *(Join *__hidden this, struct Db *, struct ID_RECORD *, struct IUpdateBuffer *)`
- caller_count: `1`
- callee_count: `35`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update`

## callers

- `0x1401947a8`

## callees

- `0x1400036a0`
- `0x14000cdc0`
- `0x14000daa0`
- `0x14000e34c`
- `0x140022d1c`
- `0x140024be4`
- `0x140028fcc`
- `0x14002a6d0`
- `0x14002c2f4`
- `0x140047e4c`
- `0x14006a428`
- `0x1400727e8`
- `0x140082a04`
- `0x1400844fc`
- `0x140084518`
- `0x1400985ec`
- `0x1400a6aec`
- `0x1400af320`
- `0x1400b2380`
- `0x1400bafac`
- `0x1400f8c08`
- `0x1400f9380`
- `0x140116c5c`
- `0x14011734c`
- `0x140117eb4`
- `0x14015d9b0`
- `0x14015e3dc`
- `0x140170738`
- `0x14019404c`
- `0x1401941e4`
- `0x14019555c`
- `0x1401961ec`
- `0x1401b2f94`
- `0x1401b9494`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140195901`
- `KERNEL32!GetCurrentThreadId` at `0x140195f5c`
- `KERNEL32!GetCurrentThreadId` at `0x140196170`
- `KERNEL32!GetCurrentThreadId` at `0x140195901`
- `KERNEL32!GetCurrentThreadId` at `0x140195f5c`
- `KERNEL32!GetCurrentThreadId` at `0x140196170`

## string_xrefs

- `0x1401958b2`: `Record got deleted from the database. connId:%? csId:%? csName:%ws record:%?`
- `0x1401956e9`: `Join::SubmitUpdate`
- `0x14019585d`: `Join::SubmitUpdate`
- `0x140195a87`: `Join::SubmitUpdate`
- `0x140195b38`: `Join::SubmitUpdate`
- `0x140195ca2`: `Join::SubmitUpdate`
- `0x140195e04`: `Join::SubmitUpdate`
- `0x140195ef0`: `Join::SubmitUpdate`
- `0x140195f88`: `Join::SubmitUpdate`
- `0x140195b94`: `Failed connId:%? csId:%? csName:%ws Error:%?`
- `0x140195cfe`: `(Ignored) Failed to GetFileInfo connId:%? csId:%? csName:%ws Error:%?`
- `0x14019591e`: `Join::SubmitUpdate`
- `0x140196197`: `Join::SubmitUpdate`
- `0x140195ae3`: `Not replicating reparse point that cannot be marshaled. connId:%? csId:%? csName:%ws record:%?`
- `0x140195f4c`: `Failed. connId:%? csId:%? csName:%ws Error:%?`
- `0x140196015`: `Sent: uid:%? gvsn:%? name:%ws connId:%? csId:%? csName:%ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
struct FrsStatus *__fastcall Join::SubmitUpdate(
        Join *this,
        struct Db *a2,
        struct ID_RECORD *a3,
        struct IUpdateBuffer *a4)
{
  __int64 v8; // r14
  int v9; // ebx
  __int64 v10; // rax
  _BYTE *v11; // rsi
  char v12; // al
  unsigned __int8 v13; // r8
  __int64 v14; // rdi
  __int64 v15; // rbx
  struct FrsStatus *Hash; // rsi
  __int64 v17; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v19; // rcx
  const unsigned __int16 *v20; // r8
  struct FrsStatus *v21; // rbx
  __int64 v22; // r9
  struct FrsStatus *v23; // rsi
  __int64 v24; // rcx
  __int64 v25; // rcx
  struct FrsStatus *FileInfo; // rdx
  __int64 v27; // rcx
  struct FrsStatus *v28; // rbx
  int v29; // ecx
  unsigned int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rcx
  const unsigned __int16 *v35; // rsi
  __int64 v36; // rax
  const unsigned __int16 *v37; // rbx
  __int64 v38; // rax
  const unsigned __int16 *v39; // rax
  const unsigned __int16 *v40; // r9
  const unsigned __int16 *v41; // r10
  unsigned int *v42; // rbx
  __int64 v43; // rcx
  __int64 v44; // rcx
  int v46; // [rsp+28h] [rbp-D8h]
  DWORD v47; // [rsp+38h] [rbp-C8h]
  DWORD v48; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v49; // [rsp+48h] [rbp-B8h]
  struct FrsStatus *v50; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v51; // [rsp+58h] [rbp-A8h] BYREF
  struct FrsStatus *v52; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v53; // [rsp+68h] [rbp-98h] BYREF
  int v54; // [rsp+6Ch] [rbp-94h] BYREF
  __int64 v55; // [rsp+70h] [rbp-90h] BYREF
  struct IUpdateBuffer *v56; // [rsp+78h] [rbp-88h] BYREF
  const wchar_t *v57; // [rsp+80h] [rbp-80h] BYREF
  int v58; // [rsp+88h] [rbp-78h]
  int v59; // [rsp+8Ch] [rbp-74h]
  const wchar_t *v60; // [rsp+90h] [rbp-70h]
  __int128 v61; // [rsp+A0h] [rbp-60h] BYREF
  int v62; // [rsp+B0h] [rbp-50h]
  __int128 v63; // [rsp+B8h] [rbp-48h] BYREF
  _OWORD v64[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v65; // [rsp+E8h] [rbp-18h]

  v56 = a4;
  v8 = 0;
  v51 = 0x100000000LL;
  v9 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v54 = 0;
  v55 = 0;
  v10 = Config::ConfigInstance<Config::ContentSet>::Get(*((_QWORD *)this + 29) + 1120LL);
  ScopedRef<Config::ContentSet>::Set(&v55, v10);
  v53 = 0;
  LODWORD(v52) = 0;
  v11 = (char *)a3 + 704;
  if ( (*((_BYTE *)a3 + 152) & 1) == 0 && (*v11 & 0x10) != 0 )
    goto LABEL_116;
  if ( HASH::IsNull((struct ID_RECORD *)((char *)a3 + 88))
    && (*(unsigned int (__fastcall **)(struct IUpdateBuffer *))(*(_QWORD *)a4 + 48LL))(a4) )
  {
    v9 = 1;
  }
  v12 = operator==((char *)a3 + 124, 0);
  v14 = v55;
  if ( (v12
     || (v13 & *v11) == 0
     || !Settings::EfsEnabled && (*((_DWORD *)a3 + 37) & 0x4000) != 0
     || (*((_DWORD *)a3 + 37) & 0x400) != 0
     || v9)
    && v9 )
  {
    (*(void (__fastcall **)(struct Db *))(*(_QWORD *)a2 + 24LL))(a2);
    v15 = *((_QWORD *)a3 + 85);
    Hash = ContentSetManager::PreStageGetHash(
             *((ContentSetManager **)this + 29),
             a3,
             &v54,
             (struct HASH *)&v61,
             (struct RdcSimilarityData *)&v63);
    v50 = Hash;
    if ( Hash )
    {
      v61 = 0;
      v62 = 0;
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
      {
        v57 = L"Join::SubmitUpdate";
        v58 = 997;
        v59 = 3;
        v60 = L"JOIN";
        dbgobj::DbgPrint<unsigned short,FrsStatus>(&v57, L"(Ignored) Failed to get hash. Error:%?", Hash);
      }
      if ( *((_DWORD *)Hash + 1) == 32 )
        ContentSetManager::LogSharingViolationEvent(*((_QWORD *)this + 29), a3, (char *)a3 + 688, 2147487952LL, 0);
      CLEAR_ERROR(&v50);
      Hash = v50;
    }
    Db::Lock(a2, (struct ID_RECORD *)((char *)a3 + 688));
    if ( Hash )
      goto LABEL_66;
    Hash = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, _QWORD))(*(_QWORD *)a2 + 16LL))(a2, 0);
    if ( Hash )
      goto LABEL_66;
    Hash = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, __int64 *, struct ID_RECORD *, struct ID_RECORD *))(*(_QWORD *)a2 + 56LL))(
                                 a2,
                                 &v51,
                                 a3,
                                 a3);
    if ( Hash )
      goto LABEL_66;
    if ( !(_DWORD)v51 )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
      {
        v58 = 1018;
LABEL_37:
        v57 = L"Join::SubmitUpdate";
        v59 = 3;
        v60 = L"JOIN";
        v17 = *((_QWORD *)this + 29);
        v50 = (struct FrsStatus *)(*(_QWORD *)(v17 + 200) + 18LL);
        dbgobj::DbgPrint<unsigned short,_GUID,_GUID,unsigned short const *,ID_RECORD>(
          (unsigned int)&v57,
          (unsigned int)L"Record got deleted from the database. connId:%? csId:%? csName:%ws record:%?",
          *((_QWORD *)this + 28) + 32,
          v17 + 168,
          (__int64)&v50,
          (__int64)a3);
        goto LABEL_116;
      }
      goto LABEL_116;
    }
    if ( v15 != *((_QWORD *)a3 + 85) )
    {
      v61 = 0;
      v62 = 0;
      v63 = 0;
    }
  }
  Hash = (struct FrsStatus *)DbUtil::LockRecord(a2, (__int64)&v51);
  if ( Hash )
    goto LABEL_66;
  if ( (_DWORD)v51 )
  {
    if ( (*((_BYTE *)a3 + 152) & 1) != 0 )
    {
      if ( *((_QWORD *)a3 + 2) == 1 )
        goto LABEL_47;
      v50 = 0;
      Hash = (struct FrsStatus *)VolumeManager::GetFilterMan(*((VolumeManager **)this + 30));
      if ( Hash )
      {
        CurrentThreadId = GetCurrentThreadId();
        v8 = FrsStatusList::PushNewError(
               v19,
               *((unsigned int *)Hash + 1),
               *((unsigned int *)Hash + 2),
               *(unsigned int *)Hash,
               "base\\fs\\remotefs\\frs\\src\\sync\\join.cpp",
               "Join::SubmitUpdate",
               1059,
               CurrentThreadId,
               Hash);
        ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v50);
        goto LABEL_116;
      }
      v20 = (const unsigned __int16 *)((char *)a3 + 156);
      v21 = 0;
      v22 = -1;
      do
        ++v22;
      while ( v20[v22] );
      if ( (unsigned int)FilterMan::Match(
                           v50,
                           (const struct _GUID *)(*((_QWORD *)this + 29) + 168LL),
                           v20,
                           v22,
                           *((_DWORD *)a3 + 37) & 0x10,
                           v46) )
      {
        Hash = Join::TombstoneFilteredRecords(this, a2, a3);
        v21 = Hash;
      }
      ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v50);
      if ( !v21 )
      {
LABEL_47:
        if ( (*((_BYTE *)a3 + 152) & 1) != 0 )
        {
          if ( !Settings::EfsEnabled && (*((_DWORD *)a3 + 37) & 0x4000) != 0 )
          {
            ContentSetManager::LogEvent(v14 + 144, 3221229874LL, (char *)a3 + 156);
            HIDWORD(v51) = 0;
          }
          if ( (*((_BYTE *)a3 + 152) & 1) != 0 && (*((_DWORD *)a3 + 37) & 0x400) != 0 )
          {
            v23 = NtfsFileSystem::ReparsePointCanBeMarshaled(
                    (NtfsFileSystem *)&Join::fs,
                    (const struct VolumeId *)(*((_QWORD *)this + 29) + 208LL),
                    (struct ID_RECORD *)((char *)a3 + 688),
                    (int *)&v52,
                    &v53);
            v50 = v23;
            if ( !v23 && !(_DWORD)v52 )
            {
              if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
              {
                v57 = L"Join::SubmitUpdate";
                v58 = 1104;
                v59 = 3;
                v60 = L"JOIN";
                v24 = *((_QWORD *)this + 29);
                v52 = (struct FrsStatus *)(*(_QWORD *)(v24 + 200) + 18LL);
                dbgobj::DbgPrint<unsigned short,_GUID,_GUID,unsigned short const *,ID_RECORD>(
                  (unsigned int)&v57,
                  (unsigned int)L"Not replicating reparse point that cannot be marshaled. connId:%? csId:%? csName:%ws record:%?",
                  *((_QWORD *)this + 28) + 32,
                  v24 + 168,
                  (__int64)&v52,
                  (__int64)a3);
              }
              ContentSetManager::LogEvent(*((_QWORD *)this + 29) + 168LL, 3221229878LL, (char *)a3 + 156);
              HIDWORD(v51) = 0;
            }
            if ( !v23 )
              goto LABEL_67;
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
            {
              v57 = L"Join::SubmitUpdate";
              v58 = 1118;
              v59 = 3;
              v60 = L"JOIN";
              v25 = *((_QWORD *)this + 29);
              v52 = (struct FrsStatus *)(*(_QWORD *)(v25 + 200) + 18LL);
              dbgobj::DbgPrint<unsigned short,_GUID,_GUID,unsigned short const *,FrsStatus>(
                (unsigned int)&v57,
                (unsigned int)L"Failed connId:%? csId:%? csName:%ws Error:%?",
                *((_QWORD *)this + 28) + 32,
                v25 + 168,
                (__int64)&v52,
                (__int64)v23);
            }
            CLEAR_ERROR(&v50);
            Hash = v50;
          }
        }
      }
    }
LABEL_66:
    if ( Hash )
      goto LABEL_94;
LABEL_67:
    if ( HIDWORD(v51) && !(unsigned __int8)operator==((char *)a3 + 124, 0) )
    {
      if ( (*((_BYTE *)a3 + 704) & 1) == 0 )
        goto LABEL_72;
      if ( HASH::IsNull((HASH *)&v61) )
        goto LABEL_86;
    }
    if ( (*((_BYTE *)a3 + 704) & 1) != 0 )
    {
LABEL_80:
      *((_DWORD *)a3 + 176) |= 1u;
      if ( (unsigned __int8)operator==((char *)a3 + 124, 0) )
      {
        *(_QWORD *)((char *)a3 + 124) = 3;
        v50 = 0;
        Hash = (struct FrsStatus *)VolumeManager::GetVsnManager(*((VolumeManager **)this + 30));
        v28 = Hash;
        if ( !Hash )
        {
          GetNextVersion(
            v50,
            a2,
            (const struct _GUID *)(*((_QWORD *)this + 29) + 168LL),
            (struct ID_RECORD *)((char *)a3 + 40),
            (struct ID_RECORD *)((char *)a3 + 24));
          Hash = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, char *, __int64))(*(_QWORD *)a2 + 224LL))(
                                       a2,
                                       (char *)a3 + 40,
                                       *((_QWORD *)this + 29) + 168LL);
          v28 = Hash;
        }
        ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v50);
        if ( v28 )
        {
LABEL_94:
          if ( !HIDWORD(v51) )
            *((_DWORD *)a3 + 38) &= ~1u;
          if ( (unsigned int)MarshalContext::ReplicateReparseFile(v53) )
          {
            v30 = *((_DWORD *)a3 + 37) & 0xFFFFFBFF;
            *((_DWORD *)a3 + 37) = v30;
            if ( v29 == -2147483629 )
              *((_DWORD *)a3 + 37) = v30 & 0xFFFFFDFF;
          }
          if ( Hash )
          {
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
            {
              v57 = L"Join::SubmitUpdate";
              v58 = 1237;
              v59 = 2;
              v60 = L"JOIN";
              v31 = *((_QWORD *)this + 29);
              v50 = (struct FrsStatus *)(*(_QWORD *)(v31 + 200) + 18LL);
              dbgobj::DbgPrint<unsigned short,_GUID,_GUID,unsigned short const *,FrsStatus>(
                (unsigned int)&v57,
                (unsigned int)L"Failed. connId:%? csId:%? csName:%ws Error:%?",
                *((_QWORD *)this + 28) + 32,
                v31 + 168,
                (__int64)&v50,
                (__int64)Hash);
            }
            v47 = GetCurrentThreadId();
            v33 = FrsStatusList::PushNewError(
                    v32,
                    *((unsigned int *)Hash + 1),
                    *((unsigned int *)Hash + 2),
                    *(unsigned int *)Hash,
                    "base\\fs\\remotefs\\frs\\src\\sync\\join.cpp",
                    "Join::SubmitUpdate",
                    1241,
                    v47,
                    Hash);
          }
          else
          {
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
            {
              v57 = L"Join::SubmitUpdate";
              v58 = 1253;
              v59 = 4;
              v60 = L"JOIN";
              v34 = *((_QWORD *)this + 29);
              v50 = (struct FrsStatus *)(*(_QWORD *)(v34 + 200) + 18LL);
              dbgobj::DbgPrint<unsigned short,UID,GVSN,unsigned short [261],_GUID,_GUID,unsigned short const *>(
                (unsigned int)&v57,
                (unsigned int)L"Sent: uid:%? gvsn:%? name:%ws connId:%? csId:%? csName:%ws",
                (_DWORD)a3,
                (_DWORD)a3 + 24,
                (__int64)a3 + 156,
                *((_QWORD *)this + 28) + 32LL,
                v34 + 168,
                (__int64)&v50);
            }
            v35 = (const unsigned __int16 *)(*(_QWORD *)(*((_QWORD *)this + 28) + 48LL) + 18LL);
            v36 = GVSN::ToString((char *)a3 + 48, v64);
            v37 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v36);
            v38 = GVSN::ToString(a3, &v57);
            std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v38);
            v39 = Config::StringParam::Get((Config::StringParam *)(v14 + 240));
            FrsEvent::Audit(
              1,
              0x40001B5Eu,
              (const unsigned __int16 *)(*(_QWORD *)(v14 + 616) + 18LL),
              v39,
              v41,
              (const unsigned __int16 *)a3 + 78,
              v40,
              v37,
              v35,
              v49);
            std::wstring::~wstring(&v57);
            std::wstring::~wstring(v64);
            v42 = (unsigned int *)(*(__int64 (__fastcall **)(struct IUpdateBuffer *, struct ID_RECORD *))(*(_QWORD *)v56 + 8LL))(
                                    v56,
                                    a3);
            if ( !v42 )
              goto LABEL_116;
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
            {
              v57 = L"Join::SubmitUpdate";
              v58 = 1274;
              v59 = 2;
              v60 = L"JOIN";
              v43 = *((_QWORD *)this + 29);
              v56 = (struct IUpdateBuffer *)(*(_QWORD *)(v43 + 200) + 18LL);
              dbgobj::DbgPrint<unsigned short,UID,GVSN,_GUID,_GUID,unsigned short const *,FrsStatus>(
                (unsigned int)&v57,
                (unsigned int)&v56,
                (_DWORD)a3,
                (_DWORD)a3 + 24,
                *((_QWORD *)this + 28) + 32LL,
                v43 + 168,
                (__int64)&v56,
                (__int64)v42);
            }
            v48 = GetCurrentThreadId();
            v33 = FrsStatusList::PushNewError(
                    v44,
                    v42[1],
                    v42[2],
                    *v42,
                    "base\\fs\\remotefs\\frs\\src\\sync\\join.cpp",
                    "Join::SubmitUpdate",
                    1282,
                    v48,
                    v42);
          }
          v8 = v33;
          goto LABEL_116;
        }
      }
      if ( !HASH::IsNull((HASH *)&v61) )
      {
        *(_OWORD *)((char *)a3 + 88) = v61;
        *((_DWORD *)a3 + 26) = v62;
        *(_OWORD *)((char *)a3 + 108) = v63;
      }
LABEL_86:
      if ( *((_QWORD *)a3 + 2) == 2 )
        goto LABEL_92;
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v57 = L"Join::SubmitUpdate";
        v58 = 1201;
        v59 = 4;
        v60 = L"JOIN";
        dbgobj::DbgPrint<unsigned short,ID_RECORD>(&v57, L"LDB Updating ID Record:%?", a3);
      }
      Hash = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, struct ID_RECORD *, struct ID_RECORD *, _QWORD))(*(_QWORD *)a2 + 200LL))(
                                   a2,
                                   a3,
                                   a3,
                                   0);
      if ( !Hash )
      {
LABEL_92:
        Hash = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, _QWORD))(*(_QWORD *)a2 + 24LL))(a2, 0);
        if ( !Hash )
          Hash = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, _QWORD))(*(_QWORD *)a2 + 16LL))(a2, 0);
      }
      goto LABEL_94;
    }
LABEL_72:
    if ( (*((_BYTE *)a3 + 152) & 1) != 0 )
    {
      memset(v64, 0, sizeof(v64));
      v65 = 0;
      FileInfo = (struct FrsStatus *)NtfsFileSystem::GetFileInfo(
                                       &Join::fs,
                                       *((_QWORD *)this + 29) + 208LL,
                                       (char *)a3 + 688,
                                       0,
                                       0,
                                       0,
                                       0,
                                       0,
                                       v64,
                                       0);
      v52 = FileInfo;
      if ( FileInfo )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
        {
          v57 = L"Join::SubmitUpdate";
          v58 = 1157;
          v59 = 3;
          v60 = L"JOIN";
          v27 = *((_QWORD *)this + 29);
          v50 = (struct FrsStatus *)(*(_QWORD *)(v27 + 200) + 18LL);
          dbgobj::DbgPrint<unsigned short,_GUID,_GUID,unsigned short const *,FrsStatus>(
            (unsigned int)&v57,
            (unsigned int)L"(Ignored) Failed to GetFileInfo connId:%? csId:%? csName:%ws Error:%?",
            *((_QWORD *)this + 28) + 32,
            v27 + 168,
            (__int64)&v50,
            (__int64)FileInfo);
        }
        CLEAR_ERROR(&v52);
      }
      else
      {
        *(_QWORD *)((char *)a3 + 140) = *(_QWORD *)&v64[0];
      }
    }
    goto LABEL_80;
  }
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
  {
    v58 = 1040;
    goto LABEL_37;
  }
LABEL_116:
  ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v55);
  return (struct FrsStatus *)v8;
}

```

## disassembly

```asm
0x14019555c  push    rbp
0x14019555e  push    rbx
0x14019555f  push    rsi
0x140195560  push    rdi
0x140195561  push    r12
0x140195563  push    r13
0x140195565  push    r14
0x140195567  push    r15
0x140195569  lea     rbp, [rsp-8]
0x14019556e  sub     rsp, 108h
0x140195575  mov     rax, cs:__security_cookie
0x14019557c  xor     rax, rsp
0x14019557f  mov     [rbp+40h+var_50], rax
0x140195583  mov     rdi, r9
0x140195586  mov     [rsp+140h+var_C8], r9
0x14019558b  mov     r15, r8
0x14019558e  mov     r12, rdx
0x140195591  mov     r13, rcx
0x140195594  xor     r14d, r14d
0x140195597  mov     dword ptr [rsp+140h+var_E8], r14d
0x14019559c  mov     ebx, r14d
0x14019559f  mov     dword ptr [rsp+140h+var_E8+4], 1
0x1401955a7  xorps   xmm0, xmm0
0x1401955aa  xor     eax, eax
0x1401955ac  movups  [rbp+40h+var_A0], xmm0
0x1401955b0  mov     [rbp+40h+var_90], eax
0x1401955b3  movups  [rbp+40h+var_88], xmm0
0x1401955b7  mov     [rsp+140h+var_D4], r14d
0x1401955bc  mov     [rsp+140h+var_D0], r14
0x1401955c1  mov     rcx, [rcx+0E8h]
0x1401955c8  add     rcx, 460h
0x1401955cf  call    ?Get@?$ConfigInstance@VContentSet@Config@@@Config@@QEAAPEAVContentSet@2@XZ; Config::ConfigInstance<Config::ContentSet>::Get(void)
0x1401955d4  mov     rdx, rax
0x1401955d7  lea     rcx, [rsp+140h+var_D0]
0x1401955dc  call    ?Set@?$ScopedRef@VContentSet@Config@@@@AEAAXPEAVContentSet@Config@@@Z; ScopedRef<Config::ContentSet>::Set(Config::ContentSet *)
0x1401955e1  mov     [rsp+140h+var_D8], r14d
0x1401955e6  mov     dword ptr [rsp+140h+var_E0], r14d
0x1401955eb  lea     rsi, [r15+2C0h]
0x1401955f2  lea     r8d, [r14+1]
0x1401955f6  test    [r15+98h], r8b
0x1401955fd  jnz     short loc_140195608
0x1401955ff  test    byte ptr [rsi], 10h
0x140195602  jnz     loc_1401961B7
0x140195608  lea     rcx, [r15+58h]; this
0x14019560c  call    ?IsNull@HASH@@QEBA_NXZ; HASH::IsNull(void)
0x140195611  test    al, al
0x140195613  jz      short loc_140195630
0x140195615  mov     rax, [rdi]
0x140195618  mov     rcx, rdi
0x14019561b  mov     rax, [rax+30h]
0x14019561f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140195624  test    eax, eax
0x140195626  mov     r8d, 1
0x14019562c  cmovnz  ebx, r8d
0x140195630  lea     rcx, [r15+7Ch]
0x140195634  xor     edx, edx
0x140195636  call    ??8@YA_NAEBU_FILETIME@@K@Z; operator==(_FILETIME const &,ulong)
0x14019563b  mov     rdi, [rsp+140h+var_D0]
0x140195640  test    al, al
0x140195642  jnz     short loc_140195674
0x140195644  test    [rsi], r8b
0x140195647  jz      short loc_140195674
0x140195649  cmp     cs:?EfsEnabled@Settings@@3VGenericBoolSetting@1@A, r14d; Settings::GenericBoolSetting Settings::EfsEnabled
0x140195650  jnz     short loc_14019565F
0x140195652  test    dword ptr [r15+94h], 4000h
0x14019565d  jnz     short loc_140195674
0x14019565f  test    dword ptr [r15+94h], 400h
0x14019566a  jnz     short loc_140195674
0x14019566c  test    ebx, ebx
0x14019566e  jz      loc_140195800
0x140195674  test    ebx, ebx
0x140195676  jz      loc_140195800
0x14019567c  mov     rax, [r12]
0x140195680  mov     rcx, r12
0x140195683  mov     rax, [rax+18h]
0x140195687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14019568c  mov     rbx, [r15+2A8h]
0x140195693  lea     rax, [rbp+40h+var_88]
0x140195697  mov     [rsp+140h+var_120], rax; struct RdcSimilarityData *
0x14019569c  lea     r9, [rbp+40h+var_A0]; struct HASH *
0x1401956a0  lea     r8, [rsp+140h+var_D4]; volatile int *
0x1401956a5  mov     rdx, r15; struct ID_RECORD *
0x1401956a8  mov     rcx, [r13+0E8h]; this
0x1401956af  call    ?PreStageGetHash@ContentSetManager@@QEAAPEAVFrsStatus@@AEBVID_RECORD@@AEDHAEAVHASH@@AEAVRdcSimilarityData@@@Z; ContentSetManager::PreStageGetHash(ID_RECORD const &,int const volatile &,HASH &,RdcSimilarityData &)
0x1401956b4  mov     rsi, rax
0x1401956b7  mov     [rsp+140h+var_F0], rax
0x1401956bc  test    rax, rax
0x1401956bf  jz      loc_140195756
0x1401956c5  xorps   xmm0, xmm0
0x1401956c8  xor     eax, eax
0x1401956ca  movups  [rbp+40h+var_A0], xmm0
0x1401956ce  mov     [rbp+40h+var_90], eax
0x1401956d1  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401956d8  test    rax, rax
0x1401956db  jz      short loc_140195720
0x1401956dd  cmp     [rax+40h], r14d
0x1401956e1  jz      short loc_140195720
0x1401956e3  cmp     dword ptr [rax+38h], 3
0x1401956e7  jl      short loc_140195720
0x1401956e9  lea     rax, aJoinSubmitupda_0; "Join::SubmitUpdate"
0x1401956f0  mov     [rbp+40h+var_C0], rax
0x1401956f4  mov     [rbp+40h+var_B8], 3E5h
0x1401956fb  mov     [rbp+40h+var_B4], 3
0x140195702  lea     rax, aJoin_0; "JOIN"
0x140195709  mov     [rbp+40h+var_B0], rax
0x14019570d  mov     r8, rsi
0x140195710  lea     rdx, aIgnoredFailedT_106; "(Ignored) Failed to get hash. Error:%?"
0x140195717  lea     rcx, [rbp+40h+var_C0]
0x14019571b  call    ??$DbgPrint@GVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStatus>(ushort const *,FrsStatus const &)
0x140195720  cmp     dword ptr [rsi+4], 20h ; ' '
0x140195724  jnz     short loc_140195747
0x140195726  lea     r8, [r15+2B0h]
0x14019572d  mov     [rsp+140h+var_120], r14
0x140195732  mov     r9d, 800010D0h
0x140195738  mov     rdx, r15
0x14019573b  mov     rcx, [r13+0E8h]
0x140195742  call    ?LogSharingViolationEvent@ContentSetManager@@QEAAXAEBVID_UPDATE@@AEBVFileId@@W4FrsEventsEnum8@@PEAVFilePath@@@Z; ContentSetManager::LogSharingViolationEvent(ID_UPDATE const &,FileId const &,FrsEventsEnum8,FilePath *)
0x140195747  lea     rcx, [rsp+140h+var_F0]; struct FrsStatus **
0x14019574c  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x140195751  mov     rsi, [rsp+140h+var_F0]
0x140195756  lea     rdx, [r15+2B0h]; struct FileId *
0x14019575d  mov     rcx, r12; this
0x140195760  call    ?Lock@Db@@QEAAXAEBVFileId@@@Z; Db::Lock(FileId const &)
0x140195765  test    rsi, rsi
0x140195768  jnz     loc_140195BB5
0x14019576e  mov     rax, [r12]
0x140195772  xor     edx, edx
0x140195774  mov     rcx, r12
0x140195777  mov     rax, [rax+10h]
0x14019577b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140195780  mov     rsi, rax
0x140195783  test    rax, rax
0x140195786  jnz     loc_140195BB5
0x14019578c  mov     rax, [r12]
0x140195790  mov     r9, r15
0x140195793  mov     r8, r15
0x140195796  lea     rdx, [rsp+140h+var_E8]
0x14019579b  mov     rcx, r12
0x14019579e  mov     rax, [rax+38h]
0x1401957a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401957a7  mov     rsi, rax
0x1401957aa  test    rax, rax
0x1401957ad  jnz     loc_140195BB5
0x1401957b3  cmp     dword ptr [rsp+140h+var_E8], r14d
0x1401957b8  jnz     short loc_1401957E7
0x1401957ba  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401957c1  test    rax, rax
0x1401957c4  jz      loc_1401961B7
0x1401957ca  cmp     [rax+40h], r14d
0x1401957ce  jz      loc_1401961B7
0x1401957d4  cmp     dword ptr [rax+38h], 3
0x1401957d8  jl      loc_1401961B7
0x1401957de  mov     [rbp+40h+var_B8], 3FAh
0x1401957e5  jmp     short loc_14019585D
0x1401957e7  cmp     rbx, [r15+2A8h]
0x1401957ee  jz      short loc_140195800
0x1401957f0  xorps   xmm0, xmm0
0x1401957f3  xor     eax, eax
0x1401957f5  movups  [rbp+40h+var_A0], xmm0
0x1401957f9  mov     [rbp+40h+var_90], eax
0x1401957fc  movups  [rbp+40h+var_88], xmm0
0x140195800  lea     rax, [rsp+140h+var_E8]
0x140195805  mov     [rsp+140h+var_120], rax; __int64
0x14019580a  xor     r9d, r9d
0x14019580d  xor     r8d, r8d
0x140195810  mov     rdx, r15
0x140195813  mov     rcx, r12; this
0x140195816  call    ?LockRecord@DbUtil@@SAPEAVFrsStatus@@PEAVDb@@AEAVID_RECORD@@PEAV?$DbIterator@VID_RECORD@@@@PEAH3@Z; DbUtil::LockRecord(Db *,ID_RECORD &,DbIterator<ID_RECORD> *,int *,int *)
0x14019581b  mov     rsi, rax
0x14019581e  test    rax, rax
0x140195821  jnz     loc_140195BB5
0x140195827  cmp     dword ptr [rsp+140h+var_E8], r14d
0x14019582c  jnz     loc_1401958C7
0x140195832  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140195839  test    rax, rax
0x14019583c  jz      loc_1401961B7
0x140195842  cmp     [rax+40h], r14d
0x140195846  jz      loc_1401961B7
0x14019584c  cmp     dword ptr [rax+38h], 3
0x140195850  jl      loc_1401961B7
0x140195856  mov     [rbp+40h+var_B8], 410h
0x14019585d  lea     rax, aJoinSubmitupda_0; "Join::SubmitUpdate"
0x140195864  mov     [rbp+40h+var_C0], rax
0x140195868  mov     [rbp+40h+var_B4], 3
0x14019586f  lea     rax, aJoin_0; "JOIN"
0x140195876  mov     [rbp+40h+var_B0], rax
0x14019587a  mov     rcx, [r13+0E8h]
0x140195881  mov     rax, [rcx+0C8h]
0x140195888  add     rax, 12h
0x14019588c  mov     [rsp+140h+var_F0], rax
0x140195891  lea     r9, [rcx+0A8h]
0x140195898  mov     r8, [r13+0E0h]
0x14019589f  add     r8, 20h ; ' '
0x1401958a3  mov     [rsp+140h+var_118], r15
0x1401958a8  lea     rax, [rsp+140h+var_F0]
0x1401958ad  mov     [rsp+140h+var_120], rax
0x1401958b2  lea     rdx, aRecordGotDelet; "Record got deleted from the database. c"...
0x1401958b9  lea     rcx, [rbp+40h+var_C0]
0x1401958bd  call    ??$DbgPrint@GU_GUID@@U1@PEBGVID_RECORD@@@dbgobj@@QEAA_KPEBGAEBU_GUID@@1AEBQEBGAEBVID_RECORD@@@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID,ushort const *,ID_RECORD>(ushort const *,_GUID const &,_GUID const &,ushort const * const &,ID_RECORD const &)
0x1401958c2  jmp     loc_1401961B7
0x1401958c7  mov     ebx, 1
0x1401958cc  test    [r15+98h], bl
0x1401958d3  jz      loc_140195BBA
0x1401958d9  cmp     [r15+10h], rbx
0x1401958dd  jz      loc_1401959C5
0x1401958e3  mov     [rsp+140h+var_F0], r14
0x1401958e8  lea     rdx, [rsp+140h+var_F0]
0x1401958ed  mov     rcx, [r13+0F0h]; this
0x1401958f4  call    ?GetFilterMan@VolumeManager@@QEAAPEAVFrsStatus@@AEAV?$ScopedRef@VFilterMan@@@@@Z; VolumeManager::GetFilterMan(ScopedRef<FilterMan> &)
0x1401958f9  mov     rsi, rax
0x1401958fc  test    rax, rax
0x1401958ff  jz      short loc_140195957
0x140195901  call    cs:__imp_GetCurrentThreadId
0x140195908  nop     dword ptr [rax+rax+00h]
0x14019590d  mov     [rsp+140h+var_100], rsi
0x140195912  mov     dword ptr [rsp+140h+var_108], eax
0x140195916  mov     dword ptr [rsp+140h+var_110], 423h
0x14019591e  lea     rax, aJoinSubmitupda; "Join::SubmitUpdate"
0x140195925  mov     [rsp+140h+var_118], rax
0x14019592a  lea     rax, aBaseFsRemotefs_74; "base\\fs\\remotefs\\frs\\src\\sync\\joi"...
0x140195931  mov     [rsp+140h+var_120], rax
0x140195936  mov     r9d, [rsi]
0x140195939  mov     r8d, [rsi+8]
0x14019593d  mov     edx, [rsi+4]
0x140195940  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140195945  mov     r14, rax
0x140195948  lea     rcx, [rsp+140h+var_F0]
0x14019594d  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x140195952  jmp     loc_1401961B7
0x140195957  mov     eax, [r15+94h]
0x14019595e  and     eax, 10h
0x140195961  mov     rdx, [r13+0E8h]
0x140195968  add     rdx, 0A8h; struct _GUID *
0x14019596f  lea     r8, [r15+9Ch]; unsigned __int16 *
0x140195976  mov     rbx, rsi
0x140195979  or      r9, 0FFFFFFFFFFFFFFFFh
0x14019597d  inc     r9; unsigned int
0x140195980  cmp     [r8+r9*2], r14w
0x140195985  jnz     short loc_14019597D
0x140195987  mov     dword ptr [rsp+140h+var_120], eax; int
0x14019598b  mov     rcx, [rsp+140h+var_F0]; this
0x140195990  call    ?Match@FilterMan@@QEAAHAEBU_GUID@@PEBGKHH@Z; FilterMan::Match(_GUID const &,ushort const *,ulong,int,int)
0x140195995  test    eax, eax
0x140195997  jz      short loc_1401959AD
0x140195999  mov     r8, r15; struct ID_RECORD *
0x14019599c  mov     rdx, r12; struct Db *
0x14019599f  mov     rcx, r13; this
0x1401959a2  call    ?TombstoneFilteredRecords@Join@@AEAAPEAVFrsStatus@@PEAVDb@@AEAVID_RECORD@@@Z; Join::TombstoneFilteredRecords(Db *,ID_RECORD &)
0x1401959a7  mov     rsi, rax
0x1401959aa  mov     rbx, rax
0x1401959ad  lea     rcx, [rsp+140h+var_F0]
0x1401959b2  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x1401959b7  test    rbx, rbx
0x1401959ba  mov     ebx, 1
0x1401959bf  jnz     loc_140195BBA
0x1401959c5  test    [r15+98h], bl
0x1401959cc  jz      loc_140195BBA
0x1401959d2  cmp     cs:?EfsEnabled@Settings@@3VGenericBoolSetting@1@A, r14d; Settings::GenericBoolSetting Settings::EfsEnabled
0x1401959d9  jnz     short loc_140195A05
0x1401959db  test    dword ptr [r15+94h], 4000h
0x1401959e6  jz      short loc_140195A05
0x1401959e8  lea     r8, [r15+9Ch]
0x1401959ef  lea     rcx, [rdi+90h]
0x1401959f6  mov     edx, 0C0001132h
0x1401959fb  call    ?LogEvent@ContentSetManager@@SAXAEBU_GUID@@W4FrsEventsEnum7@@PEBG@Z; ContentSetManager::LogEvent(_GUID const &,FrsEventsEnum7,ushort const *)
0x140195a00  mov     dword ptr [rsp+140h+var_E8+4], r14d
0x140195a05  test    [r15+98h], bl
0x140195a0c  jz      loc_140195BBA
0x140195a12  test    dword ptr [r15+94h], 400h
0x140195a1d  jz      loc_140195BBA
0x140195a23  lea     r8, [r15+2B0h]; struct FileId *
0x140195a2a  mov     rdx, [r13+0E8h]
0x140195a31  add     rdx, 0D0h; struct VolumeId *
0x140195a38  lea     rax, [rsp+140h+var_D8]
0x140195a3d  mov     [rsp+140h+var_120], rax; unsigned int *
0x140195a42  lea     r9, [rsp+140h+var_E0]; int *
0x140195a47  lea     rcx, ?fs@Join@@0VNtfsFileSystem@@A; this
0x140195a4e  call    ?ReparsePointCanBeMarshaled@NtfsFileSystem@@UEAAPEAVFrsStatus@@AEBVVolumeId@@AEBVFileId@@AEAHAEAK@Z; NtfsFileSystem::ReparsePointCanBeMarshaled(VolumeId const &,FileId const &,int &,ulong &)
0x140195a53  mov     rsi, rax
0x140195a56  mov     [rsp+140h+var_F0], rax
0x140195a5b  test    rax, rax
0x140195a5e  jnz     loc_140195B17
0x140195a64  cmp     dword ptr [rsp+140h+var_E0], r14d
0x140195a69  jnz     loc_140195B17
0x140195a6f  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140195a76  test    rax, rax
0x140195a79  jz      short loc_140195AF3
0x140195a7b  cmp     [rax+40h], r14d
0x140195a7f  jz      short loc_140195AF3
0x140195a81  cmp     dword ptr [rax+38h], 3
0x140195a85  jl      short loc_140195AF3
0x140195a87  lea     rax, aJoinSubmitupda_0; "Join::SubmitUpdate"
0x140195a8e  mov     [rbp+40h+var_C0], rax
0x140195a92  mov     [rbp+40h+var_B8], 450h
0x140195a99  mov     [rbp+40h+var_B4], 3
0x140195aa0  lea     rax, aJoin_0; "JOIN"
0x140195aa7  mov     [rbp+40h+var_B0], rax
0x140195aab  mov     rcx, [r13+0E8h]
0x140195ab2  mov     rax, [rcx+0C8h]
0x140195ab9  add     rax, 12h
  ... truncated ...
```
