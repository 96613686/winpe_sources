# ContentSetManager::CreateRootRecord(FHandle &,Db *,UID const &,Usn const &,CONTENT_SET_STATE,_FILETIME const *,ID_RECORD &)

- ea: `0x14010cc98`
- end: `0x14010d97d`
- name: `?CreateRootRecord@ContentSetManager@@AEAAPEAVFrsStatus@@AEAVFHandle@@PEAVDb@@AEBVUID@@AEBVUsn@@W4CONTENT_SET_STATE@@PEBU_FILETIME@@AEAVID_RECORD@@@Z`
- size: `3301`
- prototype: `struct FrsStatus *__high(struct FHandle *, struct Db *, const struct UID *, const struct Usn *, enum CONTENT_SET_STATE, const struct _FILETIME *, struct ID_RECORD *)`
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1401127a4`

## callees

- `0x1400036a0`
- `0x1400046cc`
- `0x14000daa0`
- `0x1400173c0`
- `0x140022d1c`
- `0x140024868`
- `0x140024be4`
- `0x140028fcc`
- `0x14002a6d0`
- `0x14002c1c0`
- `0x14002c2f4`
- `0x140047e14`
- `0x140047e4c`
- `0x1400727e8`
- `0x14007b8d8`
- `0x140082a04`
- `0x1400844fc`
- `0x140085aa0`
- `0x14008e9d0`
- `0x140098138`
- `0x14009a478`
- `0x1400f9380`
- `0x140106618`
- `0x140106858`
- `0x140107968`
- `0x140107ea0`
- `0x14010cc98`
- `0x1401b3924`
- `0x1401b9494`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x14010d81e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14010d81e`
- `KERNEL32!GetCurrentThreadId` at `0x14010cf3d`
- `KERNEL32!GetCurrentThreadId` at `0x14010d8f2`
- `KERNEL32!GetCurrentThreadId` at `0x14010cf3d`
- `KERNEL32!GetCurrentThreadId` at `0x14010d8f2`

## string_xrefs

- `0x14010d748`: `LDB Updating Content Set Record csId:%? csRec:%?`
- `0x14010d892`: `LDB Inserting Content Set Record csId:%? csRec:%?`
- `0x14010d213`: `Updating version vector. version:%? csId:%? csName:%? rootPath:%? state:%? ptr:%p csInfoHistoryGuid:%?`
- `0x14010cd6a`: `ContentSetManager::CreateRootRecord`
- `0x14010d18b`: `ContentSetManager::CreateRootRecord`
- `0x14010d2c1`: `ContentSetManager::CreateRootRecord`
- `0x14010d329`: `ContentSetManager::CreateRootRecord`
- `0x14010d383`: `ContentSetManager::CreateRootRecord`
- `0x14010d719`: `ContentSetManager::CreateRootRecord`
- `0x14010d866`: `ContentSetManager::CreateRootRecord`
- `0x14010cf5a`: `ContentSetManager::CreateRootRecord`
- `0x14010d90f`: `ContentSetManager::CreateRootRecord`
- `0x14010d561`: `dbLossRecover. Setting content set state from %? to %?. csId:%? csName:%? rootPath:%? state:%? ptr:%p csInfoHistoryGuid:%?`
- `0x14010d42b`: `startVersion:%? csId:%? csName:%? rootPath:%? state:%? ptr:%p csInfoHistoryGuid:%?`
- `0x14010d6c7`: `Read-only state change. Resetting content set state from %? to %?. csId:%? csName:%? rootPath:%? state:%? ptr:%p csInfoHistoryGuid:%?`
- `0x14010d611`: `Unexpected content set state. csId:%? csName:%? rootPath:%? state:%? ptr:%p csInfoHistoryGuid:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ContentSetManager::CreateRootRecord(
        __int64 a1,
        FHandle *a2,
        struct Db *a3,
        _OWORD *a4,
        __int64 *a5,
        int a6,
        _QWORD *a7,
        void *a8)
{
  int v9; // esi
  _OWORD *v11; // r13
  __int64 v12; // rdi
  __int64 v13; // rax
  _QWORD *v14; // rbx
  int v15; // edx
  struct FrsStatus *UsnData; // rsi
  int v17; // r12d
  DWORD CurrentThreadId; // eax
  __int64 v19; // rcx
  _OWORD *v20; // rdx
  const unsigned __int16 *v21; // rax
  __int64 v22; // rax
  LPCRITICAL_SECTION v23; // rdx
  Config::BoolParam *v24; // r9
  int v25; // r8d
  __int64 *v26; // r13
  LPCRITICAL_SECTION v27; // rdx
  DWORD v28; // eax
  __int64 v29; // rcx
  struct VsnManager *v31; // [rsp+50h] [rbp-B0h] BYREF
  FHandle *v32; // [rsp+58h] [rbp-A8h] BYREF
  const unsigned __int16 *v33; // [rsp+60h] [rbp-A0h] BYREF
  int v34; // [rsp+68h] [rbp-98h] BYREF
  const wchar_t *v35; // [rsp+70h] [rbp-90h] BYREF
  int v36; // [rsp+78h] [rbp-88h]
  int v37; // [rsp+7Ch] [rbp-84h]
  const wchar_t *v38; // [rsp+80h] [rbp-80h]
  int v39; // [rsp+88h] [rbp-78h] BYREF
  __int64 v40; // [rsp+90h] [rbp-70h] BYREF
  _OWORD *v41; // [rsp+98h] [rbp-68h] BYREF
  __int64 v42; // [rsp+A0h] [rbp-60h] BYREF
  const wchar_t *v43; // [rsp+A8h] [rbp-58h] BYREF
  int v44; // [rsp+B0h] [rbp-50h]
  int v45; // [rsp+B4h] [rbp-4Ch]
  const wchar_t *v46; // [rsp+B8h] [rbp-48h]
  int v47; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD *v48; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v49; // [rsp+D0h] [rbp-30h] BYREF
  __int64 *v50; // [rsp+D8h] [rbp-28h]
  __int64 v51; // [rsp+E0h] [rbp-20h] BYREF
  const wchar_t *v52; // [rsp+E8h] [rbp-18h] BYREF
  int v53; // [rsp+F0h] [rbp-10h]
  int v54; // [rsp+F4h] [rbp-Ch]
  const wchar_t *v55; // [rsp+F8h] [rbp-8h]
  const wchar_t *v56; // [rsp+100h] [rbp+0h] BYREF
  int v57; // [rsp+108h] [rbp+8h]
  int v58; // [rsp+10Ch] [rbp+Ch]
  const wchar_t *v59; // [rsp+110h] [rbp+10h]
  const wchar_t *v60; // [rsp+118h] [rbp+18h] BYREF
  int v61; // [rsp+120h] [rbp+20h]
  int v62; // [rsp+124h] [rbp+24h]
  const wchar_t *v63; // [rsp+128h] [rbp+28h]
  _OWORD v64[2]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v65; // [rsp+150h] [rbp+50h]
  _DWORD v66[10]; // [rsp+158h] [rbp+58h] BYREF
  __int64 v67; // [rsp+180h] [rbp+80h]
  __int64 v68; // [rsp+188h] [rbp+88h]
  __int64 v69; // [rsp+190h] [rbp+90h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+1A0h] [rbp+A0h] BYREF
  __int16 v71; // [rsp+1A8h] [rbp+A8h]
  char v72; // [rsp+1ABh] [rbp+ABh]
  _FILE_BASIC_INFORMATION v73; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v74[40]; // [rsp+1E8h] [rbp+E8h] BYREF
  _BYTE v75[720]; // [rsp+210h] [rbp+110h] BYREF

  v41 = a4;
  v9 = (int)a2;
  v32 = a2;
  v50 = a5;
  v11 = a8;
  std::wstring::wstring(v74);
  v12 = 0;
  memset(&v73, 0, sizeof(v73));
  v42 = 0;
  v40 = 0;
  v48 = 0;
  v49 = 0;
  memset_0(v64, 0, 0x88u);
  v34 = 0;
  v39 = 0;
  v13 = Config::ConfigInstance<Config::ContentSet>::Get(a1 + 1120);
  ScopedRef<Config::ContentSet>::Set(&v48, v13);
  memset_0(v11, 0, 0x2C8u);
  v14 = v48;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v52 = L"ContentSetManager::CreateRootRecord";
    v53 = 6583;
    v54 = 4;
    v55 = L"CSMG";
    v47 = Config::BoolParam::Get((Config::BoolParam *)(v48 + 120));
    v51 = a1;
    v31 = (struct VsnManager *)(v14[77] + 18LL);
    v33 = Config::StringParam::Get((Config::StringParam *)(v14 + 30));
    dbgobj::DbgPrint<unsigned short,_GUID,unsigned short const *,unsigned short const *,enum CONTENT_SET_STATE,unsigned __int64,Guid,int>(
      (unsigned int)&v52,
      v15,
      a1 + 168,
      (unsigned int)&v33,
      (__int64)&v31,
      (__int64)&a6,
      (__int64)&v51,
      a1 + 712,
      (__int64)&v47);
  }
  UsnData = (struct FrsStatus *)FHandle::ReadUsnData(v9, 0, (unsigned int)&v42, 0, 0);
  v17 = 1;
  if ( !UsnData )
  {
    UsnData = FHandle::GetBasicInfo(v32, &v73);
    if ( !UsnData )
    {
      LODWORD(v31) = 1;
      if ( (unsigned int)Db::TryLock(a3, (const struct FileId *)&v42, (const enum FidLockMan::Type *)&v31)
        || (UsnData = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, _QWORD))(*(_QWORD *)a3 + 24LL))(a3, 0)) == 0
        && (Db::Lock(a3, (const struct FileId *)&v42),
            (UsnData = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, _QWORD))(*(_QWORD *)a3 + 16LL))(
                                             a3,
                                             0)) == 0) )
      {
        UsnData = (struct FrsStatus *)FHandle::ReadUsnData((_DWORD)v32, (unsigned int)&v49, 0, 0, (__int64)v74);
        if ( !UsnData )
        {
          UsnData = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, int *, __int64, _OWORD *))(*(_QWORD *)a3 + 80LL))(
                                          a3,
                                          &v34,
                                          a1 + 168,
                                          v64);
          if ( !UsnData )
          {
            if ( !v34
              || !HIBYTE(v71)
              || (CurrentThreadId = GetCurrentThreadId(),
                  (UsnData = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                   v19,
                                                   9099,
                                                   0,
                                                   3,
                                                   "base\\fs\\remotefs\\frs\\src\\sync\\contentsetmanager.cpp",
                                                   "ContentSetManager::CreateRootRecord",
                                                   6623,
                                                   CurrentThreadId,
                                                   0)) == 0) )
            {
              v31 = 0;
              UsnData = (struct FrsStatus *)VolumeManager::GetVsnManager(*(VolumeManager **)(a1 + 1720));
              if ( !UsnData )
                v40 = *(_QWORD *)VsnManager::ResetContentSetStartVersion(v31, &v33, a1 + 168, &v40);
              ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v31);
              if ( !UsnData )
              {
                memset_0(v11, 0, 0x2C8u);
                v20 = v41;
                *v11 = *v41;
                *((_QWORD *)v11 + 2) = *((_QWORD *)v20 + 2);
                *((_DWORD *)v11 + 38) = *((_DWORD *)v11 + 38) & 0xFFFFFFFC | 1;
                *((_QWORD *)v11 + 85) = v49;
                *((_QWORD *)v11 + 86) = v42;
                *((_DWORD *)v11 + 176) = v11[44] & 0xFFFFFFF4 | 1;
                *((_DWORD *)v11 + 37) = v73.FileAttributes;
                *(_OWORD *)((char *)v11 + 24) = *v20;
                *((_QWORD *)v11 + 5) = *((_QWORD *)v20 + 2);
                v11[3] = 0;
                *((_QWORD *)v11 + 8) = 0;
                *(_OWORD *)((char *)v11 + 72) = *(_OWORD *)(a1 + 168);
                v21 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v74);
                StringCchCopyW((unsigned __int16 *)v11 + 78, 0x105u, v21);
                *(_QWORD *)((char *)v11 + 140) = v73.CreationTime.QuadPart;
                *(_QWORD *)((char *)v11 + 132) = v73.ChangeTime.QuadPart;
                if ( a7 )
                {
                  *(_QWORD *)((char *)v11 + 124) = *a7;
                  goto LABEL_35;
                }
                if ( (!v34 || v66[0] == 3)
                  && (unsigned int)Config::BoolParam::Get((Config::BoolParam *)(v14 + 145))
                  && a6 == 3 )
                {
                  *(_QWORD *)((char *)v11 + 124) = 2;
                  v31 = 0;
                  UsnData = (struct FrsStatus *)VolumeManager::GetVsnManager(*(VolumeManager **)(a1 + 1720));
                  if ( !UsnData )
                  {
                    GetNextVersion(
                      v31,
                      a3,
                      (const struct _GUID *)(a1 + 168),
                      (struct VERSION *)((char *)v11 + 40),
                      (struct GVSN *)((char *)v11 + 24));
                    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
                    {
                      v35 = L"ContentSetManager::CreateRootRecord";
                      v36 = 6692;
                      v37 = 5;
                      v38 = L"CSMG";
                      v41 = (_OWORD *)a1;
                      v33 = (const unsigned __int16 *)(v14[77] + 18LL);
                      v32 = (FHandle *)Config::StringParam::Get((Config::StringParam *)(v14 + 30));
                      dbgobj::DbgPrint<unsigned short,VERSION,_GUID,unsigned short const *,unsigned short const *,enum CONTENT_SET_STATE,unsigned __int64,Guid>(
                        (unsigned int)&v35,
                        (unsigned int)L"Updating version vector. version:%? csId:%? csName:%? rootPath:%? state:%? ptr:%p "
                                       "csInfoHistoryGuid:%?",
                        (_DWORD)v11 + 40,
                        a1 + 168,
                        (__int64)&v32,
                        (__int64)&v33,
                        (__int64)&a6,
                        (__int64)&v41,
                        a1 + 712);
                    }
                    UsnData = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, __int64, __int64))(*(_QWORD *)a3 + 224LL))(
                                                    a3,
                                                    (__int64)v11 + 40,
                                                    a1 + 168);
                  }
                  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v31);
                }
                else
                {
                  if ( *(_DWORD *)(a1 + 1112) )
                  {
                    *(_QWORD *)((char *)v11 + 124) = 3;
LABEL_35:
                    ID_RECORD::ID_RECORD((ID_RECORD *)v75);
                    UsnData = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, int *, _OWORD *, _BYTE *))(*(_QWORD *)a3 + 56LL))(
                                                    a3,
                                                    &v39,
                                                    v11,
                                                    v75);
                    if ( !UsnData )
                    {
                      if ( v39 )
                      {
                        if ( g_DebugLog
                          && LODWORD(g_DebugLog[1].LockSemaphore)
                          && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
                        {
                          v35 = L"ContentSetManager::CreateRootRecord";
                          v36 = 6719;
                          v37 = 4;
                          v38 = L"CSMG";
                          dbgobj::DbgPrint<unsigned short,ID_RECORD>(&v35, L"LDB Updating ID Record:%?", v11);
                        }
                        v22 = (*(__int64 (__fastcall **)(struct Db *, _OWORD *, _OWORD *, _QWORD))(*(_QWORD *)a3 + 200LL))(
                                a3,
                                v11,
                                v11,
                                0);
                      }
                      else
                      {
                        if ( g_DebugLog
                          && LODWORD(g_DebugLog[1].LockSemaphore)
                          && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
                        {
                          v35 = L"ContentSetManager::CreateRootRecord";
                          v36 = 6722;
                          v37 = 4;
                          v38 = L"CSMG";
                          dbgobj::DbgPrint<unsigned short,ID_RECORD>(&v35, L"LDB Inserting ID Record:%?", v11);
                        }
                        v22 = (*(__int64 (__fastcall **)(struct Db *, _OWORD *))(*(_QWORD *)a3 + 160LL))(a3, v11);
                      }
                      UsnData = (struct FrsStatus *)v22;
                    }
                    goto LABEL_48;
                  }
                  *(_QWORD *)((char *)v11 + 124) = 1;
                }
                if ( UsnData )
                  goto LABEL_48;
                goto LABEL_35;
              }
            }
          }
        }
      }
    }
  }
LABEL_48:
  v23 = g_DebugLog;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v35 = L"ContentSetManager::CreateRootRecord";
    v36 = 6726;
    v37 = 5;
    v38 = L"CSMG";
    v41 = (_OWORD *)a1;
    v33 = (const unsigned __int16 *)(v14[77] + 18LL);
    v32 = (FHandle *)Config::StringParam::Get((Config::StringParam *)(v14 + 30));
    dbgobj::DbgPrint<unsigned short,VERSION,_GUID,unsigned short const *,unsigned short const *,enum CONTENT_SET_STATE,unsigned __int64,Guid>(
      (unsigned int)&v35,
      (unsigned int)L"startVersion:%? csId:%? csName:%? rootPath:%? state:%? ptr:%p csInfoHistoryGuid:%?",
      (unsigned int)&v40,
      a1 + 168,
      (__int64)&v32,
      (__int64)&v33,
      (__int64)&a6,
      (__int64)&v41,
      a1 + 712);
    v23 = g_DebugLog;
  }
  if ( UsnData )
    goto LABEL_100;
  if ( v34 )
  {
    if ( v66[0] == 6 || v66[0] == 3 )
    {
LABEL_78:
      v65 = v40;
      v26 = v50;
      v67 = *v50;
      if ( v23 && LODWORD(v23[1].LockSemaphore) && SLODWORD(v23[1].OwningThread) >= 4 )
      {
        v43 = L"ContentSetManager::CreateRootRecord";
        v44 = 6779;
        v45 = 4;
        v46 = L"CSMG";
        dbgobj::DbgPrint<unsigned short,_GUID,CONTENT_SET_RECORD>(
          &v43,
          L"LDB Updating Content Set Record csId:%? csRec:%?",
          a1 + 168,
          v64);
      }
      UsnData = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, __int64, _OWORD *))(*(_QWORD *)a3 + 192LL))(
                                      a3,
                                      a1 + 168,
                                      v64);
      if ( UsnData )
        goto LABEL_100;
      if ( v34 )
        goto LABEL_98;
      goto LABEL_86;
    }
    if ( (unsigned int)Config::BoolParam::Get((Config::BoolParam *)(v14 + 150))
      && (unsigned int)FileTime::IsZero(&SystemTimeAsFileTime) )
    {
      v25 = 1;
    }
    else if ( !(unsigned int)Config::BoolParam::Get(v24) && !(unsigned int)FileTime::IsZero(&SystemTimeAsFileTime) )
    {
      v25 = 1;
    }
    if ( *(_DWORD *)(a1 + 1112) )
    {
      if ( !v23 || !LODWORD(v23[1].LockSemaphore) || SLODWORD(v23[1].OwningThread) < 4 )
        goto LABEL_77;
      v56 = L"ContentSetManager::CreateRootRecord";
      v57 = 6756;
      v58 = 4;
      v59 = L"CSMG";
      v33 = (const unsigned __int16 *)a1;
      v32 = (FHandle *)(v14[77] + 18LL);
      v31 = (struct VsnManager *)Config::StringParam::Get((Config::StringParam *)(v14 + 30));
      dbgobj::DbgPrint<unsigned short,enum CONTENT_SET_STATE,enum CONTENT_SET_STATE,_GUID,unsigned short const *,unsigned short const *,enum CONTENT_SET_STATE,unsigned __int64,Guid>(
        (unsigned int)&v56,
        (unsigned int)L"dbLossRecover. Setting content set state from %? to %?. csId:%? csName:%? rootPath:%? state:%? ptr"
                       ":%p csInfoHistoryGuid:%?",
        (unsigned int)v66,
        (unsigned int)&a6,
        a1 + 168,
        (__int64)&v31,
        (__int64)&v32,
        (__int64)&a6,
        (__int64)&v33,
        a1 + 712);
    }
    else if ( v25 )
    {
      if ( !v23 || !LODWORD(v23[1].LockSemaphore) || SLODWORD(v23[1].OwningThread) < 4 )
        goto LABEL_77;
      v43 = L"ContentSetManager::CreateRootRecord";
      v44 = 6766;
      v45 = 4;
      v46 = L"CSMG";
      v33 = (const unsigned __int16 *)a1;
      v32 = (FHandle *)(v14[77] + 18LL);
      v31 = (struct VsnManager *)Config::StringParam::Get((Config::StringParam *)(v14 + 30));
      dbgobj::DbgPrint<unsigned short,enum CONTENT_SET_STATE,enum CONTENT_SET_STATE,_GUID,unsigned short const *,unsigned short const *,enum CONTENT_SET_STATE,unsigned __int64,Guid>(
        (unsigned int)&v43,
        (unsigned int)L"Read-only state change. Resetting content set state from %? to %?. csId:%? csName:%? rootPath:%? s"
                       "tate:%? ptr:%p csInfoHistoryGuid:%?",
        (unsigned int)v66,
        (unsigned int)&a6,
        a1 + 168,
        (__int64)&v31,
        (__int64)&v32,
        (__int64)&a6,
        (__int64)&v33,
        a1 + 712);
    }
    else
    {
      if ( !v23 || !LODWORD(v23[1].LockSemaphore) || SLODWORD(v23[1].OwningThread) < 3 )
        goto LABEL_77;
      v60 = L"ContentSetManager::CreateRootRecord";
      v61 = 6763;
      v62 = 3;
      v63 = L"CSMG";
      v33 = (const unsigned __int16 *)a1;
      v32 = (FHandle *)(v14[77] + 18LL);
      v31 = (struct VsnManager *)Config::StringParam::Get((Config::StringParam *)(v14 + 30));
      dbgobj::DbgPrint<unsigned short,_GUID,unsigned short const *,unsigned short const *,enum CONTENT_SET_STATE,unsigned __int64,Guid>(
        (unsigned int)&v60,
        (unsigned int)L"Unexpected content set state. csId:%? csName:%? rootPath:%? state:%? ptr:%p csInfoHistoryGuid:%?",
        a1 + 168,
        (unsigned int)&v31,
        (__int64)&v32,
        (__int64)&a6,
        (__int64)&v33,
        a1 + 712);
    }
    v23 = g_DebugLog;
LABEL_77:
    v66[0] = a6;
    goto LABEL_78;
  }
  v26 = v50;
LABEL_86:
  v64[0] = *(_OWORD *)(a1 + 168);
  v64[1] = *(_OWORD *)(a1 + 184);
  v66[0] = a6;
  v67 = *v26;
  v71 = 0;
  v65 = v40;
  if ( Settings::GhostingEnabled && (unsigned int)Config::BoolParam::Get((Config::BoolParam *)(v14 + 120)) )
  {
    v72 = 1;
  }
  else
  {
    v72 = 0;
    v17 = 0;
  }
  *(_DWORD *)(a1 + 1636) = v17;
  if ( (unsigned int)Config::BoolParam::Get((Config::BoolParam *)(v14 + 150)) )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v27 = g_DebugLog;
  }
  else
  {
    SystemTimeAsFileTime = 0;
  }
  *(struct _FILETIME *)(a1 + 1512) = SystemTimeAsFileTime;
  v68 = 0;
  v69 = 0;
  if ( v27 && LODWORD(v27[1].LockSemaphore) && SLODWORD(v27[1].OwningThread) >= 4 )
  {
    v43 = L"ContentSetManager::CreateRootRecord";
    v44 = 6814;
    v45 = 4;
    v46 = L"CSMG";
    dbgobj::DbgPrint<unsigned short,_GUID,CONTENT_SET_RECORD>(
      &v43,
      L"LDB Inserting Content Set Record csId:%? csRec:%?",
      v64,
      v64);
  }
  UsnData = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, _OWORD *))(*(_QWORD *)a3 + 152LL))(a3, v64);
  if ( UsnData )
    goto LABEL_100;
LABEL_98:
  UsnData = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, _QWORD))(*(_QWORD *)a3 + 24LL))(a3, 0);
  if ( UsnData
    || (UsnData = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, _QWORD))(*(_QWORD *)a3 + 16LL))(a3, 0)) != 0 )
  {
LABEL_100:
    v28 = GetCurrentThreadId();
    v12 = FrsStatusList::PushNewError(
            v29,
            *((unsigned int *)UsnData + 1),
            *((unsigned int *)UsnData + 2),
            *(unsigned int *)UsnData,
            "base\\fs\\remotefs\\frs\\src\\sync\\contentsetmanager.cpp",
            "ContentSetManager::CreateRootRecord",
            6825,
            v28,
            UsnData);
  }
  ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v48);
  std::wstring::~wstring(v74);
  return v12;
}

```

## disassembly

```asm
0x14010cc98  mov     [rsp-8+arg_18], rbx
0x14010cc9d  push    rbp
0x14010cc9e  push    rsi
0x14010cc9f  push    rdi
0x14010cca0  push    r12
0x14010cca2  push    r13
0x14010cca4  push    r14
0x14010cca6  push    r15
0x14010cca8  lea     rbp, [rsp-3F0h]
0x14010ccb0  sub     rsp, 4F0h
0x14010ccb7  mov     rax, cs:__security_cookie
0x14010ccbe  xor     rax, rsp
0x14010ccc1  mov     [rbp+420h+var_40], rax
0x14010ccc8  mov     [rbp+420h+var_488], r9
0x14010cccc  mov     r15, r8
0x14010cccf  mov     rsi, rdx
0x14010ccd2  mov     [rsp+520h+var_4C8], rdx
0x14010ccd7  mov     r14, rcx
0x14010ccda  mov     rax, [rbp+420h+arg_20]
0x14010cce1  mov     [rbp+420h+var_448], rax
0x14010cce5  mov     r13, [rbp+420h+arg_38]
0x14010ccec  lea     rcx, [rbp+420h+var_338]
0x14010ccf3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x14010ccf8  nop
0x14010ccf9  xor     edi, edi
0x14010ccfb  mov     dword ptr [rbp+420h+var_360.CreationTime], edi
0x14010cd01  xorps   xmm0, xmm0
0x14010cd04  xor     eax, eax
0x14010cd06  movups  xmmword ptr [rbp+420h+var_360.CreationTime+4], xmm0
0x14010cd0d  movups  xmmword ptr [rbp+420h+var_360.LastWriteTime+4], xmm0
0x14010cd14  mov     dword ptr [rbp+420h+var_360+24h], eax
0x14010cd1a  mov     [rbp+420h+var_480], rdi
0x14010cd1e  mov     [rbp+420h+var_490], rdi
0x14010cd22  mov     [rbp+420h+var_458], rdi
0x14010cd26  mov     [rbp+420h+var_450], rdi
0x14010cd2a  xor     edx, edx; Val
0x14010cd2c  mov     r8d, 88h; Size
0x14010cd32  lea     rcx, [rbp+420h+var_3F0]; void *
0x14010cd36  call    memset_0
0x14010cd3b  mov     [rsp+520h+var_4B8], edi
0x14010cd3f  mov     [rbp+420h+var_498], edi
0x14010cd42  lea     rcx, [r14+460h]
0x14010cd49  call    ?Get@?$ConfigInstance@VContentSet@Config@@@Config@@QEAAPEAVContentSet@2@XZ; Config::ConfigInstance<Config::ContentSet>::Get(void)
0x14010cd4e  mov     rdx, rax
0x14010cd51  lea     rcx, [rbp+420h+var_458]
0x14010cd55  call    ?Set@?$ScopedRef@VContentSet@Config@@@@AEAAXPEAVContentSet@Config@@@Z; ScopedRef<Config::ContentSet>::Set(Config::ContentSet *)
0x14010cd5a  xor     edx, edx; Val
0x14010cd5c  mov     r8d, 2C8h; Size
0x14010cd62  mov     rcx, r13; void *
0x14010cd65  call    memset_0
0x14010cd6a  lea     rcx, aContentsetmana_58; "ContentSetManager::CreateRootRecord"
0x14010cd71  lea     rdx, aCsmg; "CSMG"
0x14010cd78  mov     rbx, [rbp+420h+var_458]
0x14010cd7c  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14010cd83  test    rax, rax
0x14010cd86  jz      loc_14010CE32
0x14010cd8c  cmp     [rax+40h], edi
0x14010cd8f  jz      loc_14010CE32
0x14010cd95  cmp     dword ptr [rax+38h], 4
0x14010cd99  jl      loc_14010CE32
0x14010cd9f  mov     [rbp+420h+var_438], rcx
0x14010cda3  mov     [rbp+420h+var_430], 19B7h
0x14010cdaa  mov     [rbp+420h+var_42C], 4
0x14010cdb1  mov     [rbp+420h+var_428], rdx
0x14010cdb5  lea     rcx, [rbx+3C0h]; this
0x14010cdbc  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x14010cdc1  mov     [rbp+420h+var_460], eax
0x14010cdc4  mov     [rbp+420h+var_440], r14
0x14010cdc8  mov     rax, [rbx+268h]
0x14010cdcf  add     rax, 12h
0x14010cdd3  mov     [rsp+520h+var_4D0], rax
0x14010cdd8  lea     rcx, [rbx+0F0h]; this
0x14010cddf  call    ?Get@StringParam@Config@@QEBAPEBGXZ; Config::StringParam::Get(void)
0x14010cde4  mov     [rsp+520h+var_4C0], rax
0x14010cde9  lea     rax, [r14+2C8h]
0x14010cdf0  lea     r8, [r14+0A8h]
0x14010cdf7  lea     rcx, [rbp+420h+var_460]
0x14010cdfb  mov     [rsp+520h+var_4E0], rcx
0x14010ce00  mov     [rsp+520h+var_4E8], rax
0x14010ce05  lea     rax, [rbp+420h+var_440]
0x14010ce09  mov     [rsp+520h+var_4F0], rax
0x14010ce0e  lea     rax, [rbp+420h+arg_28]
0x14010ce15  mov     [rsp+520h+var_4F8], rax
0x14010ce1a  lea     rax, [rsp+520h+var_4D0]
0x14010ce1f  mov     [rsp+520h+var_500], rax
0x14010ce24  lea     r9, [rsp+520h+var_4C0]
0x14010ce29  lea     rcx, [rbp+420h+var_438]
0x14010ce2d  call    ??$DbgPrint@GU_GUID@@PEBGPEBGW4CONTENT_SET_STATE@@_KVGuid@@H@dbgobj@@QEAA_KPEBGAEBU_GUID@@AEBQEBG2AEBW4CONTENT_SET_STATE@@AEB_KAEBVGuid@@AEBH@Z; dbgobj::DbgPrint<ushort,_GUID,ushort const *,ushort const *,CONTENT_SET_STATE,unsigned __int64,Guid,int>(ushort const *,_GUID const &,ushort const * const &,ushort const * const &,CONTENT_SET_STATE const &,unsigned __int64 const &,Guid const &,int const &)
0x14010ce32  mov     [rsp+520h+var_500], rdi
0x14010ce37  xor     r9d, r9d
0x14010ce3a  lea     r8, [rbp+420h+var_480]
0x14010ce3e  xor     edx, edx
0x14010ce40  mov     rcx, rsi
0x14010ce43  call    ?ReadUsnData@FHandle@@QEBAPEAVFrsStatus@@PEAVUsn@@PEAVFileId@@1PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; FHandle::ReadUsnData(Usn *,FileId *,FileId *,std::wstring *)
0x14010ce48  mov     rsi, rax
0x14010ce4b  mov     r12d, 1
0x14010ce51  test    rax, rax
0x14010ce54  jnz     loc_14010D37C
0x14010ce5a  lea     rdx, [rbp+420h+var_360]; struct _FILE_BASIC_INFORMATION *
0x14010ce61  mov     rcx, [rsp+520h+var_4C8]; this
0x14010ce66  call    ?GetBasicInfo@FHandle@@QEBAPEAVFrsStatus@@AEAU_FILE_BASIC_INFORMATION@@@Z; FHandle::GetBasicInfo(_FILE_BASIC_INFORMATION &)
0x14010ce6b  mov     rsi, rax
0x14010ce6e  test    rax, rax
0x14010ce71  jnz     loc_14010D37C
0x14010ce77  mov     dword ptr [rsp+520h+var_4D0], r12d
0x14010ce7c  lea     r8, [rsp+520h+var_4D0]; enum FidLockMan::Type *
0x14010ce81  lea     rdx, [rbp+420h+var_480]; struct FileId *
0x14010ce85  mov     rcx, r15; this
0x14010ce88  call    ?TryLock@Db@@QEAAHAEBVFileId@@AEBW4Type@FidLockMan@@@Z; Db::TryLock(FileId const &,FidLockMan::Type const &)
0x14010ce8d  test    eax, eax
0x14010ce8f  jnz     short loc_14010CED7
0x14010ce91  mov     rax, [r15]
0x14010ce94  xor     edx, edx
0x14010ce96  mov     rcx, r15
0x14010ce99  mov     rax, [rax+18h]
0x14010ce9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14010cea2  mov     rsi, rax
0x14010cea5  test    rax, rax
0x14010cea8  jnz     loc_14010D37C
0x14010ceae  lea     rdx, [rbp+420h+var_480]; struct FileId *
0x14010ceb2  mov     rcx, r15; this
0x14010ceb5  call    ?Lock@Db@@QEAAXAEBVFileId@@@Z; Db::Lock(FileId const &)
0x14010ceba  mov     rax, [r15]
0x14010cebd  xor     edx, edx
0x14010cebf  mov     rcx, r15
0x14010cec2  mov     rax, [rax+10h]
0x14010cec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14010cecb  mov     rsi, rax
0x14010cece  test    rax, rax
0x14010ced1  jnz     loc_14010D37C
0x14010ced7  lea     rax, [rbp+420h+var_338]
0x14010cede  mov     [rsp+520h+var_500], rax
0x14010cee3  xor     r9d, r9d
0x14010cee6  xor     r8d, r8d
0x14010cee9  lea     rdx, [rbp+420h+var_450]
0x14010ceed  mov     rcx, [rsp+520h+var_4C8]
0x14010cef2  call    ?ReadUsnData@FHandle@@QEBAPEAVFrsStatus@@PEAVUsn@@PEAVFileId@@1PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; FHandle::ReadUsnData(Usn *,FileId *,FileId *,std::wstring *)
0x14010cef7  mov     rsi, rax
0x14010cefa  test    rax, rax
0x14010cefd  jnz     loc_14010D37C
0x14010cf03  mov     rax, [r15]
0x14010cf06  lea     r8, [r14+0A8h]
0x14010cf0d  lea     r9, [rbp+420h+var_3F0]
0x14010cf11  lea     rdx, [rsp+520h+var_4B8]
0x14010cf16  mov     rcx, r15
0x14010cf19  mov     rax, [rax+50h]
0x14010cf1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14010cf22  mov     rsi, rax
0x14010cf25  test    rax, rax
0x14010cf28  jnz     loc_14010D37C
0x14010cf2e  cmp     [rsp+520h+var_4B8], edi
0x14010cf32  jz      short loc_14010CF8F
0x14010cf34  cmp     [rbp+420h+var_377], dil
0x14010cf3b  jz      short loc_14010CF8F
0x14010cf3d  call    cs:__imp_GetCurrentThreadId
0x14010cf44  nop     dword ptr [rax+rax+00h]
0x14010cf49  mov     [rsp+520h+var_4E0], rdi
0x14010cf4e  mov     dword ptr [rsp+520h+var_4E8], eax
0x14010cf52  mov     dword ptr [rsp+520h+var_4F0], 19DFh
0x14010cf5a  lea     rax, aContentsetmana_64; "ContentSetManager::CreateRootRecord"
0x14010cf61  mov     [rsp+520h+var_4F8], rax
0x14010cf66  lea     rax, aBaseFsRemotefs_85; "base\\fs\\remotefs\\frs\\src\\sync\\con"...
0x14010cf6d  mov     [rsp+520h+var_500], rax
0x14010cf72  lea     r9d, [rsi+3]
0x14010cf76  xor     r8d, r8d
0x14010cf79  mov     edx, 238Bh
0x14010cf7e  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14010cf83  mov     rsi, rax
0x14010cf86  test    rax, rax
0x14010cf89  jnz     loc_14010D37C
0x14010cf8f  mov     [rsp+520h+var_4D0], rdi
0x14010cf94  lea     rdx, [rsp+520h+var_4D0]
0x14010cf99  mov     rcx, [r14+6B8h]; this
0x14010cfa0  call    ?GetVsnManager@VolumeManager@@QEAAPEAVFrsStatus@@AEAV?$ScopedRef@VVsnManager@@@@@Z; VolumeManager::GetVsnManager(ScopedRef<VsnManager> &)
0x14010cfa5  mov     rsi, rax
0x14010cfa8  test    rax, rax
0x14010cfab  jnz     short loc_14010CFCE
0x14010cfad  lea     r9, [rbp+420h+var_490]
0x14010cfb1  lea     r8, [r14+0A8h]
0x14010cfb8  lea     rdx, [rsp+520h+var_4C0]
0x14010cfbd  mov     rcx, [rsp+520h+var_4D0]
0x14010cfc2  call    ?ResetContentSetStartVersion@VsnManager@@QEAA?AVVERSION@@AEBU_GUID@@AEBV2@@Z; VsnManager::ResetContentSetStartVersion(_GUID const &,VERSION const &)
0x14010cfc7  mov     rcx, [rax]
0x14010cfca  mov     [rbp+420h+var_490], rcx
0x14010cfce  lea     rcx, [rsp+520h+var_4D0]
0x14010cfd3  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x14010cfd8  test    rsi, rsi
0x14010cfdb  jnz     loc_14010D37C
0x14010cfe1  xor     edx, edx; Val
0x14010cfe3  mov     r8d, 2C8h; Size
0x14010cfe9  mov     rcx, r13; void *
0x14010cfec  call    memset_0
0x14010cff1  mov     rdx, [rbp+420h+var_488]
0x14010cff5  movups  xmm0, xmmword ptr [rdx]
0x14010cff8  movdqu  xmmword ptr [r13+0], xmm0
0x14010cffe  mov     rax, [rdx+10h]
0x14010d002  mov     [r13+10h], rax
0x14010d006  mov     eax, [r13+98h]
0x14010d00d  and     eax, 0FFFFFFFDh
0x14010d010  or      eax, r12d
0x14010d013  mov     [r13+98h], eax
0x14010d01a  mov     rax, [rbp+420h+var_450]
0x14010d01e  mov     [r13+2A8h], rax
0x14010d025  mov     rax, [rbp+420h+var_480]
0x14010d029  mov     [r13+2B0h], rax
0x14010d030  mov     eax, [r13+2C0h]
0x14010d037  and     eax, 0FFFFFFF5h
0x14010d03a  or      eax, r12d
0x14010d03d  mov     [r13+2C0h], eax
0x14010d044  mov     eax, [rbp+420h+var_360.FileAttributes]
0x14010d04a  mov     [r13+94h], eax
0x14010d051  movups  xmm0, xmmword ptr [rdx]
0x14010d054  movdqu  xmmword ptr [r13+18h], xmm0
0x14010d05a  mov     rax, [rdx+10h]
0x14010d05e  mov     [r13+28h], rax
0x14010d062  xorps   xmm0, xmm0
0x14010d065  movdqu  xmmword ptr [r13+30h], xmm0
0x14010d06b  mov     [r13+40h], rdi
0x14010d06f  movups  xmm0, xmmword ptr [r14+0A8h]
0x14010d077  movdqu  xmmword ptr [r13+48h], xmm0
0x14010d07d  lea     rcx, [rbp+420h+var_338]
0x14010d084  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14010d089  lea     rcx, [r13+9Ch]; unsigned __int16 *
0x14010d090  mov     r8, rax; unsigned __int16 *
0x14010d093  mov     edx, 105h; unsigned __int64
0x14010d098  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14010d09d  mov     eax, dword ptr [rbp+420h+var_360.CreationTime]
0x14010d0a3  mov     [r13+8Ch], eax
0x14010d0aa  mov     eax, dword ptr [rbp+420h+var_360.CreationTime+4]
0x14010d0b0  mov     [r13+90h], eax
0x14010d0b7  mov     eax, dword ptr [rbp+420h+var_360.ChangeTime]
0x14010d0bd  mov     [r13+84h], eax
0x14010d0c4  mov     eax, dword ptr [rbp+420h+var_360.ChangeTime+4]
0x14010d0ca  mov     [r13+88h], eax
0x14010d0d1  mov     rax, [rbp+420h+arg_30]
0x14010d0d8  test    rax, rax
0x14010d0db  jz      short loc_14010D0E9
0x14010d0dd  mov     rax, [rax]
0x14010d0e0  mov     [r13+7Ch], rax
0x14010d0e4  jmp     loc_14010D270
0x14010d0e9  cmp     [rsp+520h+var_4B8], edi
0x14010d0ed  jz      short loc_14010D0F9
0x14010d0ef  cmp     [rbp+420h+var_3C8], 3
0x14010d0f3  jnz     loc_14010D24C
0x14010d0f9  lea     rcx, [rbx+488h]; this
0x14010d100  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x14010d105  test    eax, eax
0x14010d107  jz      loc_14010D24C
0x14010d10d  cmp     [rbp+420h+arg_28], 3
0x14010d114  jnz     loc_14010D24C
0x14010d11a  mov     qword ptr [r13+7Ch], 2
0x14010d122  mov     [rsp+520h+var_4D0], rdi
0x14010d127  lea     rdx, [rsp+520h+var_4D0]
0x14010d12c  mov     rcx, [r14+6B8h]; this
0x14010d133  call    ?GetVsnManager@VolumeManager@@QEAAPEAVFrsStatus@@AEAV?$ScopedRef@VVsnManager@@@@@Z; VolumeManager::GetVsnManager(ScopedRef<VsnManager> &)
0x14010d138  mov     rsi, rax
0x14010d13b  test    rax, rax
0x14010d13e  jnz     loc_14010D240
0x14010d144  lea     r9, [r13+28h]; struct VERSION *
0x14010d148  lea     rcx, [r13+18h]
0x14010d14c  mov     [rsp+520h+var_500], rcx; struct GVSN *
0x14010d151  lea     rsi, [r14+0A8h]
0x14010d158  mov     r8, rsi; struct _GUID *
0x14010d15b  mov     rdx, r15; struct Db *
0x14010d15e  mov     rcx, [rsp+520h+var_4D0]; this
0x14010d163  call    ?GetNextVersion@@YAXPEAVVsnManager@@PEAVDb@@AEBU_GUID@@AEAVVERSION@@AEAVGVSN@@@Z; GetNextVersion(VsnManager *,Db *,_GUID const &,VERSION &,GVSN &)
0x14010d168  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14010d16f  test    rax, rax
0x14010d172  jz      loc_14010D224
0x14010d178  cmp     [rax+40h], edi
0x14010d17b  jz      loc_14010D224
0x14010d181  cmp     dword ptr [rax+38h], 5
0x14010d185  jl      loc_14010D224
0x14010d18b  lea     rax, aContentsetmana_58; "ContentSetManager::CreateRootRecord"
0x14010d192  mov     [rsp+520h+var_4B0], rax
0x14010d197  mov     [rsp+520h+var_4A8], 1A24h
0x14010d19f  mov     [rsp+520h+var_4A4], 5
0x14010d1a7  lea     rax, aCsmg; "CSMG"
0x14010d1ae  mov     [rbp+420h+var_4A0], rax
0x14010d1b2  mov     [rbp+420h+var_488], r14
0x14010d1b6  mov     rax, [rbx+268h]
0x14010d1bd  add     rax, 12h
0x14010d1c1  mov     [rsp+520h+var_4C0], rax
0x14010d1c6  lea     rcx, [rbx+0F0h]; this
0x14010d1cd  call    ?Get@StringParam@Config@@QEBAPEBGXZ; Config::StringParam::Get(void)
0x14010d1d2  mov     [rsp+520h+var_4C8], rax
0x14010d1d7  lea     rax, [r14+2C8h]
0x14010d1de  mov     [rsp+520h+var_4E0], rax
0x14010d1e3  lea     rax, [rbp+420h+var_488]
0x14010d1e7  mov     [rsp+520h+var_4E8], rax
0x14010d1ec  lea     rax, [rbp+420h+arg_28]
0x14010d1f3  mov     [rsp+520h+var_4F0], rax
0x14010d1f8  lea     rax, [rsp+520h+var_4C0]
0x14010d1fd  mov     [rsp+520h+var_4F8], rax
0x14010d202  lea     rax, [rsp+520h+var_4C8]
0x14010d207  mov     [rsp+520h+var_500], rax
0x14010d20c  mov     r9, rsi
0x14010d20f  lea     r8, [r13+28h]
0x14010d213  lea     rdx, aUpdatingVersio; "Updating version vector. version:%? csI"...
0x14010d21a  lea     rcx, [rsp+520h+var_4B0]
  ... truncated ...
```
