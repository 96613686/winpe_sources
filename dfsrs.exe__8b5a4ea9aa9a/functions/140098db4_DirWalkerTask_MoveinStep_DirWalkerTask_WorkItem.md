# DirWalkerTask::MoveinStep(DirWalkerTask::WorkItem * &)

- ea: `0x140098db4`
- end: `0x1400996bd`
- name: `?MoveinStep@DirWalkerTask@@AEAAPEAVFrsStatus@@AEAPEAVWorkItem@1@@Z`
- size: `2313`
- prototype: `struct FrsStatus *__fastcall(DirWalkerTask *__hidden this, struct DirWalkerTask::WorkItem **)`
- caller_count: `1`
- callee_count: `35`
- tags: `service_task, installer_update`

## callers

- `0x14009af00`

## callees

- `0x1400036a0`
- `0x14000cd1c`
- `0x14000e34c`
- `0x140024868`
- `0x140024be4`
- `0x140028fcc`
- `0x14002a15c`
- `0x14002c110`
- `0x14002c160`
- `0x14002c1c0`
- `0x14002c2f4`
- `0x14002c688`
- `0x1400379f8`
- `0x140037a70`
- `0x140037be8`
- `0x1400384dc`
- `0x14005e8ec`
- `0x140085aa0`
- `0x14009789c`
- `0x140097d64`
- `0x1400981ac`
- `0x140098578`
- `0x1400987dc`
- `0x140098a00`
- `0x140098db4`
- `0x140099d38`
- `0x14009aaf8`
- `0x14009b188`
- `0x14009bb48`
- `0x14009be58`
- `0x1400f92bc`
- `0x140115dd4`
- `0x1401b9494`
- `0x1401bf3d0`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140098ee7`
- `KERNEL32!GetCurrentThreadId` at `0x140098f89`
- `KERNEL32!GetCurrentThreadId` at `0x1400991b4`
- `KERNEL32!GetCurrentThreadId` at `0x1400992d7`
- `KERNEL32!GetCurrentThreadId` at `0x140099632`
- `KERNEL32!GetCurrentThreadId` at `0x140098ee7`
- `KERNEL32!GetCurrentThreadId` at `0x140098f89`
- `KERNEL32!GetCurrentThreadId` at `0x1400991b4`
- `KERNEL32!GetCurrentThreadId` at `0x1400992d7`
- `KERNEL32!GetCurrentThreadId` at `0x140099632`

## string_xrefs

- `0x140098e58`: `DirWalkerTask::MoveinStep`
- `0x140099143`: `DirWalkerTask::MoveinStep`
- `0x14009920c`: `DirWalkerTask::MoveinStep`
- `0x140099542`: `DirWalkerTask::MoveinStep`
- `0x140098ed5`: `DirWalkerTask::MoveinStep`
- `0x1400991d1`: `DirWalkerTask::MoveinStep`
- `0x1400992f4`: `DirWalkerTask::MoveinStep`
- `0x14009964f`: `DirWalkerTask::MoveinStep`
- `0x140098ea4`: `Starting to process move-in job. uid:%?`
- `0x1400991a3`: `Ghosted file deleted:%ws (fid:%?)`
- `0x140098fa6`: `FHandle::GetFilePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct FrsStatus *__fastcall DirWalkerTask::MoveinStep(Db **this, struct DirWalkerTask::WorkItem **a2)
{
  struct DirWalkerTask::WorkItem *v3; // rsi
  char *v4; // r15
  __int64 v5; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v7; // rcx
  struct FrsStatus *UsnConsumer; // rbx
  LPCRITICAL_SECTION v9; // rcx
  DWORD v10; // eax
  __int64 v11; // rcx
  struct FrsStatus *v12; // rax
  FilePath *v13; // r15
  struct FrsStatus *FileInfo; // rax
  Db *v15; // rcx
  __int64 v16; // rax
  ContentSetManager *v17; // rcx
  DWORD v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rbx
  ID_RECORD *v21; // rax
  DWORD v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  DWORD v25; // eax
  __int64 v26; // rcx
  struct FrsStatus *v28; // [rsp+50h] [rbp-B0h] BYREF
  int v29; // [rsp+58h] [rbp-A8h] BYREF
  int v30[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v31; // [rsp+68h] [rbp-98h] BYREF
  const wchar_t *v32; // [rsp+70h] [rbp-90h] BYREF
  int v33; // [rsp+78h] [rbp-88h]
  int v34; // [rsp+7Ch] [rbp-84h]
  const wchar_t *v35; // [rsp+80h] [rbp-80h]
  struct DirWalkerTask::WorkItem *v36; // [rsp+88h] [rbp-78h] BYREF
  __int64 v37; // [rsp+90h] [rbp-70h] BYREF
  __int64 v38; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v39[8]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v40; // [rsp+A8h] [rbp-58h]
  struct DirWalkerTask::WorkItem **v41; // [rsp+B0h] [rbp-50h]
  _BYTE v42[712]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v43[20]; // [rsp+380h] [rbp+280h] BYREF
  __int128 v44; // [rsp+394h] [rbp+294h]
  int v45; // [rsp+3A4h] [rbp+2A4h]
  __int64 v46[5]; // [rsp+3A8h] [rbp+2A8h] BYREF
  __int128 v47; // [rsp+3D0h] [rbp+2D0h] BYREF
  __int64 v48; // [rsp+3E0h] [rbp+2E0h]
  _BYTE v49[720]; // [rsp+6A0h] [rbp+5A0h] BYREF

  v41 = a2;
  v3 = *a2;
  v4 = (char *)(this + 70);
  FHandle::FHandle((FHandle *)v39, (struct FileSystem *)(this + 70));
  v5 = 0;
  v29 = 0;
  memset(v43, 0, sizeof(v43));
  v44 = 0;
  v45 = 0;
  v38 = 0;
  std::wstring::wstring(v46);
  v37 = 0;
  ID_RECORD::ID_RECORD((ID_RECORD *)&v47);
  ID_RECORD::ID_RECORD((ID_RECORD *)v49);
  v31 = 0;
  if ( (*((_BYTE *)v3 + 76) & 4) != 0
    && g_DebugLog
    && LODWORD(g_DebugLog[1].LockSemaphore)
    && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v32 = L"DirWalkerTask::MoveinStep";
    v33 = 1198;
    v34 = 4;
    v35 = L"DIRW";
    dbgobj::DbgPrint<unsigned short,GVSN>(&v32, L"Starting to process move-in job. uid:%?", *((_QWORD *)v3 + 1) + 24LL);
  }
  LODWORD(v28) = 1;
  if ( !(unsigned int)Db::TryLock(
                        this[56],
                        (struct DirWalkerTask::WorkItem *)((char *)v3 + 48),
                        (const enum FidLockMan::Type *)&v28) )
  {
    CurrentThreadId = GetCurrentThreadId();
    UsnConsumer = (struct FrsStatus *)FrsStatusList::PushNewError(
                                        v7,
                                        9049,
                                        0,
                                        3,
                                        "base\\fs\\remotefs\\frs\\src\\db\\dirwalker.cpp",
                                        "DirWalkerTask::MoveinStep",
                                        1205,
                                        CurrentThreadId,
                                        0);
    v28 = UsnConsumer;
    if ( UsnConsumer )
      goto LABEL_67;
  }
  UsnConsumer = FHandle::OpenFileId(
                  (FHandle *)v39,
                  (const struct VolumeId *)(this + 28),
                  (struct DirWalkerTask::WorkItem *)((char *)v3 + 48),
                  (*((_DWORD *)v3 + 19) & 2) != 0 ? 0x80000000 : 128,
                  7u);
  v28 = UsnConsumer;
  if ( UsnConsumer )
    goto LABEL_67;
  if ( (*((_BYTE *)v3 + 76) & 4) == 0 )
    goto LABEL_15;
  if ( v40 )
  {
    v13 = (struct DirWalkerTask::WorkItem *)((char *)v3 + 56);
    v12 = (struct FrsStatus *)(*(__int64 (__fastcall **)(__int64, char *, __int64))(*(_QWORD *)v40 + 104LL))(
                                v40,
                                (char *)this + 224,
                                (__int64)v3 + 56);
  }
  else
  {
    v10 = GetCurrentThreadId();
    v12 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                v11,
                                14,
                                0,
                                1,
                                "base\\fs\\remotefs\\frs\\src\\fs\\FileSystem.h",
                                "FHandle::GetFilePath",
                                596,
                                v10,
                                0);
    v13 = (struct DirWalkerTask::WorkItem *)((char *)v3 + 56);
  }
  UsnConsumer = v12;
  v28 = v12;
  if ( v12 )
  {
LABEL_67:
    v9 = g_DebugLog;
    goto LABEL_68;
  }
  FilePath::TrimLongPathChars(v13);
  v4 = (char *)(this + 70);
LABEL_15:
  if ( (*((_BYTE *)v3 + 76) & 9) == 0 )
    goto LABEL_58;
  FileInfo = (struct FrsStatus *)DirWalkerTask::GetFileInfo(v9, v39, &v38, v43, v46, &v37);
  UsnConsumer = FileInfo;
  v28 = FileInfo;
  if ( !FileInfo )
  {
    if ( *((_QWORD *)v3 + 5) != 1 )
    {
      FileInfo = DirWalkerTask::LockGetParent(
                   (DirWalkerTask *)this,
                   (const struct FileId *)&v37,
                   (struct ID_RECORD *)v49);
      UsnConsumer = FileInfo;
      v28 = FileInfo;
    }
    if ( !FileInfo )
    {
      v15 = this[56];
      v16 = *(_QWORD *)v15;
      v36 = 0;
      UsnConsumer = (struct FrsStatus *)(*(__int64 (__fastcall **)(Db *, int *, __int64, __int128 *, struct DirWalkerTask::WorkItem **))(v16 + 40))(
                                          v15,
                                          &v29,
                                          (__int64)v3 + 48,
                                          &v47,
                                          &v36);
      v28 = UsnConsumer;
      if ( !UsnConsumer && !v29 && (WORD6(v44) & 0x400) != 0 )
      {
        UsnConsumer = FHandle::IsFileGhosted((FHandle *)v39, &v31);
        v28 = UsnConsumer;
        if ( !UsnConsumer )
        {
          if ( v31 )
          {
            v17 = *(ContentSetManager **)(*((_QWORD *)v3 + 1) + 8LL);
            if ( !v17 || (unsigned int)ContentSetManager::IsPrimary(v17) )
            {
              UsnConsumer = (struct FrsStatus *)(*(__int64 (__fastcall **)(char *, __int64, __int64, _QWORD))(*(_QWORD *)v4 + 128LL))(
                                                  v4,
                                                  (__int64)this[22] + 168,
                                                  (__int64)v3 + 48,
                                                  0);
              v28 = UsnConsumer;
              if ( !UsnConsumer )
              {
                if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
                {
                  v32 = L"DirWalkerTask::MoveinStep";
                  v33 = 1296;
                  v34 = 4;
                  v35 = L"DIRW";
                  v28 = (struct FrsStatus *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v46);
                  dbgobj::DbgPrint<unsigned short,unsigned short const *,FileId>(
                    &v32,
                    L"Ghosted file deleted:%ws (fid:%?)",
                    &v28,
                    (char *)v3 + 48);
                }
                v18 = GetCurrentThreadId();
                UsnConsumer = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                    v19,
                                                    2,
                                                    0,
                                                    1,
                                                    "base\\fs\\remotefs\\frs\\src\\db\\dirwalker.cpp",
                                                    "DirWalkerTask::MoveinStep",
                                                    1298,
                                                    v18,
                                                    0);
                v28 = UsnConsumer;
              }
            }
          }
        }
      }
    }
  }
  if ( UsnConsumer )
    goto LABEL_67;
  *(_QWORD *)v30 = 0;
  UsnConsumer = (struct FrsStatus *)VolumeManager::GetUsnConsumer(this[22], v30);
  v28 = UsnConsumer;
  if ( !UsnConsumer && (!v29 || v48 != 1) )
  {
    if ( (unsigned int)DirWalkerTask::NotToReplicate(
                         (_DWORD)this,
                         v30[0],
                         (unsigned int)v46,
                         (int)v3 + 48,
                         (struct FileId *)&v37,
                         (__int64)v49,
                         HIDWORD(v44),
                         (struct _GUID *)(*((_QWORD *)v3 + 1) + 80LL)) )
    {
      if ( !v29
        || (v20 = *((_QWORD *)v3 + 1),
            v21 = ID_RECORD::ID_RECORD((ID_RECORD *)v42, (const struct ID_RECORD *)&v47),
            UsnConsumer = (struct FrsStatus *)DirWalkerTask::TombstoneFilteredContent(this, v21, v20),
            (v28 = UsnConsumer) == 0) )
      {
        v22 = GetCurrentThreadId();
        UsnConsumer = (struct FrsStatus *)FrsStatusList::PushNewError(
                                            v23,
                                            2,
                                            0,
                                            1,
                                            "base\\fs\\remotefs\\frs\\src\\db\\dirwalker.cpp",
                                            "DirWalkerTask::MoveinStep",
                                            1331,
                                            v22,
                                            0);
        v28 = UsnConsumer;
      }
    }
  }
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(v30);
  if ( UsnConsumer )
    goto LABEL_67;
  if ( (*((_BYTE *)v3 + 76) & 8) != 0 )
  {
    if ( v29 )
    {
      UsnConsumer = (struct FrsStatus *)DirWalkerTask::Validate(
                                          (_DWORD)this,
                                          (_DWORD)v3,
                                          (unsigned int)v49,
                                          (unsigned int)&v47,
                                          (__int64)v43,
                                          (__int64)&v38,
                                          (__int64)v46,
                                          (__int64)&v29);
      v28 = UsnConsumer;
      v9 = g_DebugLog;
    }
    else
    {
      v9 = g_DebugLog;
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v32 = L"DirWalkerTask::MoveinStep";
        v33 = 1359;
        v34 = 4;
        v35 = L"DIRW";
        *(_QWORD *)v30 = *((_QWORD *)v3 + 8) + 18LL;
        dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v32, L"New resource found. name:%ws", v30);
        v9 = g_DebugLog;
      }
      *((_DWORD *)v3 + 19) &= ~8u;
      *((_DWORD *)v3 + 19) |= 1u;
    }
    if ( UsnConsumer )
      goto LABEL_68;
  }
  else
  {
    v9 = g_DebugLog;
  }
  if ( v29 )
  {
    *(_OWORD *)((char *)v3 + 24) = v47;
    *((_QWORD *)v3 + 5) = v48;
  }
  else
  {
    UsnConsumer = (struct FrsStatus *)DirWalkerTask::CreateOneRecord(
                                        (DirWalkerTask *)this,
                                        (__int64)v46,
                                        (__int64)&v38,
                                        (__int64)v43,
                                        v31,
                                        (__int64)v3 + 24);
    v28 = UsnConsumer;
    v9 = g_DebugLog;
  }
  if ( UsnConsumer )
  {
LABEL_68:
    if ( v9 && LODWORD(v9[1].LockSemaphore) && SLODWORD(v9[1].OwningThread) >= 2 )
    {
      v32 = L"DirWalkerTask::MoveinStep";
      v33 = 1418;
      v34 = 2;
      v35 = L"DIRW";
      dbgobj::DbgPrint<unsigned short,FileId,FrsStatus>(&v32, L"fid:%? Error:%?", (char *)v3 + 48, UsnConsumer);
    }
    if ( *((_DWORD *)UsnConsumer + 1) != 9014 )
    {
      if ( (unsigned int)FrsStatus::IsFileDeletedError(UsnConsumer) )
      {
        CLEAR_ERROR(&v28);
        UsnConsumer = DirWalkerTask::DeleteWorkItem((DirWalkerTask *)this, v41, 0);
        if ( !UsnConsumer )
          ++*((_DWORD *)this + 103);
      }
      else
      {
        v36 = v3;
        std::list<IUpdateTask *>::push_back(this + 41, &v36);
        ++*((_DWORD *)v3 + 18);
        ++*((_DWORD *)this + 102);
        CLEAR_ERROR(&v28);
        if ( *((_DWORD *)v3 + 18) == 4 )
          DirWalkerTask::LogEvent(v24, 2147487960LL, *((_QWORD *)v3 + 1) + 48LL, (char *)v3 + 24, (char *)v3 + 56);
        UsnConsumer = v28;
      }
    }
    goto LABEL_79;
  }
  *((_DWORD *)v3 + 19) &= ~1u;
LABEL_58:
  if ( *((_DWORD *)v3 + 18) >= 4u )
    DirWalkerTask::LogEvent(v9, 1073746132, *((_QWORD *)v3 + 1) + 48LL, (char *)v3 + 24, (char *)v3 + 56);
  v30[0] = 1;
  LODWORD(v28) = 0;
  if ( (*((_BYTE *)v3 + 76) & 2) == 0 )
    goto LABEL_64;
  UsnConsumer = DirWalkerTask::WalkImmediateChildren((DirWalkerTask *)this, v3, (struct FHandle *)v39, v30, (int *)&v28);
  if ( UsnConsumer )
  {
LABEL_80:
    v25 = GetCurrentThreadId();
    v5 = FrsStatusList::PushNewError(
           v26,
           *((unsigned int *)UsnConsumer + 1),
           *((unsigned int *)UsnConsumer + 2),
           *(unsigned int *)UsnConsumer,
           "base\\fs\\remotefs\\frs\\src\\db\\dirwalker.cpp",
           "DirWalkerTask::MoveinStep",
           1489,
           v25,
           UsnConsumer);
    goto LABEL_81;
  }
  if ( v30[0] )
  {
LABEL_64:
    UsnConsumer = DirWalkerTask::DeleteWorkItem((DirWalkerTask *)this, v41, 0);
  }
  else
  {
    v36 = v3;
    std::list<IUpdateTask *>::push_back(this + 41, &v36);
    ++*((_DWORD *)v3 + 18);
  }
  if ( (_DWORD)v28 )
    DirWalkerTask::ResetPass((DirWalkerTask *)this, 1);
LABEL_79:
  if ( UsnConsumer )
    goto LABEL_80;
LABEL_81:
  std::wstring::~wstring(v46);
  FHandle::~FHandle((FHandle *)v39);
  return (struct FrsStatus *)v5;
}

```

## disassembly

```asm
0x140098db4  mov     [rsp-8+arg_10], rbx
0x140098db9  push    rbp
0x140098dba  push    rsi
0x140098dbb  push    rdi
0x140098dbc  push    r12
0x140098dbe  push    r13
0x140098dc0  push    r14
0x140098dc2  push    r15
0x140098dc4  lea     rbp, [rsp-880h]
0x140098dcc  sub     rsp, 980h
0x140098dd3  mov     rax, cs:__security_cookie
0x140098dda  xor     rax, rsp
0x140098ddd  mov     [rbp+8B0h+var_40], rax
0x140098de4  mov     [rbp+8B0h+var_900], rdx
0x140098de8  mov     r14, rcx
0x140098deb  mov     rsi, [rdx]
0x140098dee  lea     r15, [rcx+230h]
0x140098df5  mov     rdx, r15; struct FileSystem *
0x140098df8  lea     rcx, [rbp+8B0h+var_910]; this
0x140098dfc  call    ??0FHandle@@QEAA@PEAVFileSystem@@@Z; FHandle::FHandle(FileSystem *)
0x140098e01  nop
0x140098e02  xor     edi, edi
0x140098e04  mov     [rsp+9B0h+var_958], edi
0x140098e08  mov     dword ptr [rbp+8B0h+var_630], edi
0x140098e0e  xorps   xmm0, xmm0
0x140098e11  xor     eax, eax
0x140098e13  movups  xmmword ptr [rbp+8B0h+var_630+4], xmm0
0x140098e1a  movups  [rbp+8B0h+var_61C], xmm0
0x140098e21  mov     [rbp+8B0h+var_60C], eax
0x140098e27  mov     [rbp+8B0h+var_918], rdi
0x140098e2b  lea     rcx, [rbp+8B0h+var_608]
0x140098e32  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140098e37  nop
0x140098e38  mov     [rbp+8B0h+var_920], rdi
0x140098e3c  lea     rcx, [rbp+8B0h+var_5E0]; this
0x140098e43  call    ??0ID_RECORD@@QEAA@XZ; ID_RECORD::ID_RECORD(void)
0x140098e48  lea     rcx, [rbp+8B0h+var_310]; this
0x140098e4f  call    ??0ID_RECORD@@QEAA@XZ; ID_RECORD::ID_RECORD(void)
0x140098e54  mov     [rsp+9B0h+var_948], edi
0x140098e58  lea     rcx, aDirwalkertaskM_0; "DirWalkerTask::MoveinStep"
0x140098e5f  lea     rdx, aDirw; "DIRW"
0x140098e66  test    byte ptr [rsi+4Ch], 4
0x140098e6a  jz      short loc_140098EB5
0x140098e6c  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140098e73  test    rax, rax
0x140098e76  jz      short loc_140098EB5
0x140098e78  cmp     [rax+40h], edi
0x140098e7b  jz      short loc_140098EB5
0x140098e7d  cmp     dword ptr [rax+38h], 4
0x140098e81  jl      short loc_140098EB5
0x140098e83  mov     [rsp+9B0h+var_940], rcx
0x140098e88  mov     [rsp+9B0h+var_938], 4AEh
0x140098e90  mov     [rsp+9B0h+var_934], 4
0x140098e98  mov     [rbp+8B0h+var_930], rdx
0x140098e9c  mov     r8, [rsi+8]
0x140098ea0  add     r8, 18h
0x140098ea4  lea     rdx, aStartingToProc; "Starting to process move-in job. uid:%?"
0x140098eab  lea     rcx, [rsp+9B0h+var_940]
0x140098eb0  call    ??$DbgPrint@GVGVSN@@@dbgobj@@QEAA_KPEBGAEBVGVSN@@@Z; dbgobj::DbgPrint<ushort,GVSN>(ushort const *,GVSN const &)
0x140098eb5  mov     dword ptr [rsp+9B0h+var_960], 1
0x140098ebd  lea     r13, [rsi+30h]
0x140098ec1  lea     r8, [rsp+9B0h+var_960]; enum FidLockMan::Type *
0x140098ec6  mov     rdx, r13; struct FileId *
0x140098ec9  mov     rcx, [r14+1C0h]; this
0x140098ed0  call    ?TryLock@Db@@QEAAHAEBVFileId@@AEBW4Type@FidLockMan@@@Z; Db::TryLock(FileId const &,FidLockMan::Type const &)
0x140098ed5  lea     rbx, aDirwalkertaskM_1; "DirWalkerTask::MoveinStep"
0x140098edc  lea     r12, aBaseFsRemotefs_90; "base\\fs\\remotefs\\frs\\src\\db\\dirwa"...
0x140098ee3  test    eax, eax
0x140098ee5  jnz     short loc_140098F32
0x140098ee7  call    cs:__imp_GetCurrentThreadId
0x140098eee  nop     dword ptr [rax+rax+00h]
0x140098ef3  mov     [rsp+9B0h+var_970], rdi
0x140098ef8  mov     [rsp+9B0h+var_978], eax
0x140098efc  mov     dword ptr [rsp+9B0h+var_980], 4B5h
0x140098f04  mov     [rsp+9B0h+var_988], rbx
0x140098f09  mov     [rsp+9B0h+var_990], r12
0x140098f0e  mov     r9d, 3
0x140098f14  xor     r8d, r8d
0x140098f17  mov     edx, 2359h
0x140098f1c  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140098f21  mov     rbx, rax
0x140098f24  mov     [rsp+9B0h+var_960], rax
0x140098f29  test    rax, rax
0x140098f2c  jnz     loc_140099542
0x140098f32  lea     r12, [r14+0E0h]
0x140098f39  mov     eax, [rsi+4Ch]
0x140098f3c  and     al, 2
0x140098f3e  neg     al
0x140098f40  sbb     r9d, r9d
0x140098f43  and     r9d, 7FFFFF80h
0x140098f4a  sub     r9d, 0FFFFFF80h; unsigned int
0x140098f4e  mov     dword ptr [rsp+9B0h+var_990], 7; unsigned int
0x140098f56  mov     r8, r13; struct FileId *
0x140098f59  mov     rdx, r12; struct VolumeId *
0x140098f5c  lea     rcx, [rbp+8B0h+var_910]; this
0x140098f60  call    ?OpenFileId@FHandle@@QEAAPEAVFrsStatus@@AEBVVolumeId@@AEBVFileId@@KK@Z; FHandle::OpenFileId(VolumeId const &,FileId const &,ulong,ulong)
0x140098f65  mov     rbx, rax
0x140098f68  mov     [rsp+9B0h+var_960], rax
0x140098f6d  test    rax, rax
0x140098f70  jnz     loc_140099542
0x140098f76  test    byte ptr [rsi+4Ch], 4
0x140098f7a  jz      loc_140099009
0x140098f80  mov     rcx, [rbp+8B0h+var_908]
0x140098f84  test    rcx, rcx
0x140098f87  jnz     short loc_140098FD3
0x140098f89  call    cs:__imp_GetCurrentThreadId
0x140098f90  nop     dword ptr [rax+rax+00h]
0x140098f95  mov     [rsp+9B0h+var_970], rdi
0x140098f9a  mov     [rsp+9B0h+var_978], eax
0x140098f9e  mov     dword ptr [rsp+9B0h+var_980], 254h
0x140098fa6  lea     rax, aFhandleGetfile; "FHandle::GetFilePath"
0x140098fad  mov     [rsp+9B0h+var_988], rax
0x140098fb2  lea     rax, aBaseFsRemotefs_32; "base\\fs\\remotefs\\frs\\src\\fs\\FileS"...
0x140098fb9  mov     [rsp+9B0h+var_990], rax
0x140098fbe  lea     r9d, [rbx+1]
0x140098fc2  xor     r8d, r8d
0x140098fc5  lea     edx, [rbx+0Eh]
0x140098fc8  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140098fcd  lea     r15, [rsi+38h]
0x140098fd1  jmp     short loc_140098FE9
0x140098fd3  mov     rax, [rcx]
0x140098fd6  lea     r15, [rsi+38h]
0x140098fda  mov     r8, r15
0x140098fdd  mov     rdx, r12
0x140098fe0  mov     rax, [rax+68h]
0x140098fe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140098fe9  mov     rbx, rax
0x140098fec  mov     [rsp+9B0h+var_960], rax
0x140098ff1  test    rax, rax
0x140098ff4  jnz     loc_140099542
0x140098ffa  mov     rcx, r15; this
0x140098ffd  call    ?TrimLongPathChars@FilePath@@QEAAXXZ; FilePath::TrimLongPathChars(void)
0x140099002  lea     r15, [r14+230h]
0x140099009  test    byte ptr [rsi+4Ch], 9
0x14009900d  jz      loc_140099494
0x140099013  lea     rax, [rbp+8B0h+var_920]
0x140099017  mov     [rsp+9B0h+var_988], rax
0x14009901c  lea     rax, [rbp+8B0h+var_608]
0x140099023  mov     [rsp+9B0h+var_990], rax
0x140099028  lea     r9, [rbp+8B0h+var_630]
0x14009902f  lea     r8, [rbp+8B0h+var_918]
0x140099033  lea     rdx, [rbp+8B0h+var_910]
0x140099037  call    ?GetFileInfo@DirWalkerTask@@AEAAPEAVFrsStatus@@PEAVFHandle@@AEAVUsn@@AEAU_FILE_BASIC_INFORMATION@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVFileId@@@Z; DirWalkerTask::GetFileInfo(FHandle *,Usn &,_FILE_BASIC_INFORMATION &,std::wstring &,FileId &)
0x14009903c  mov     rbx, rax
0x14009903f  mov     [rsp+9B0h+var_960], rax
0x140099044  test    rax, rax
0x140099047  jnz     loc_140099205
0x14009904d  cmp     qword ptr [rsi+28h], 1
0x140099052  jz      short loc_14009906F
0x140099054  lea     r8, [rbp+8B0h+var_310]; struct ID_RECORD *
0x14009905b  lea     rdx, [rbp+8B0h+var_920]; struct FileId *
0x14009905f  mov     rcx, r14; this
0x140099062  call    ?LockGetParent@DirWalkerTask@@AEAAPEAVFrsStatus@@AEBVFileId@@AEAVID_RECORD@@@Z; DirWalkerTask::LockGetParent(FileId const &,ID_RECORD &)
0x140099067  mov     rbx, rax
0x14009906a  mov     [rsp+9B0h+var_960], rax
0x14009906f  test    rax, rax
0x140099072  jnz     loc_140099205
0x140099078  mov     rcx, [r14+1C0h]
0x14009907f  mov     rax, [rcx]
0x140099082  mov     [rbp+8B0h+var_928], rdi
0x140099086  lea     rdx, [rbp+8B0h+var_928]
0x14009908a  mov     [rsp+9B0h+var_990], rdx
0x14009908f  lea     r9, [rbp+8B0h+var_5E0]
0x140099096  mov     r8, r13
0x140099099  lea     rdx, [rsp+9B0h+var_958]
0x14009909e  mov     rax, [rax+28h]
0x1400990a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400990a7  mov     rbx, rax
0x1400990aa  mov     [rsp+9B0h+var_960], rax
0x1400990af  test    rax, rax
0x1400990b2  jnz     loc_140099205
0x1400990b8  cmp     [rsp+9B0h+var_958], edi
0x1400990bc  jnz     loc_140099205
0x1400990c2  test    dword ptr [rbp+8B0h+var_61C+0Ch], 400h
0x1400990cc  jz      loc_140099205
0x1400990d2  lea     rdx, [rsp+9B0h+var_948]; int *
0x1400990d7  lea     rcx, [rbp+8B0h+var_910]; this
0x1400990db  call    ?IsFileGhosted@FHandle@@QEAAPEAVFrsStatus@@AEAH@Z; FHandle::IsFileGhosted(int &)
0x1400990e0  mov     rbx, rax
0x1400990e3  mov     [rsp+9B0h+var_960], rax
0x1400990e8  test    rax, rax
0x1400990eb  jnz     loc_140099205
0x1400990f1  cmp     [rsp+9B0h+var_948], edi
0x1400990f5  jz      loc_140099205
0x1400990fb  mov     rax, [rsi+8]
0x1400990ff  mov     rcx, [rax+8]; this
0x140099103  test    rcx, rcx
0x140099106  jz      short loc_140099115
0x140099108  call    ?IsPrimary@ContentSetManager@@QEAAHXZ; ContentSetManager::IsPrimary(void)
0x14009910d  test    eax, eax
0x14009910f  jz      loc_140099205
0x140099115  mov     rax, [r15]
0x140099118  mov     rdx, [r14+0B0h]
0x14009911f  add     rdx, 0A8h
0x140099126  xor     r9d, r9d
0x140099129  mov     r8, r13
0x14009912c  mov     rcx, r15
0x14009912f  mov     rax, [rax+80h]
0x140099136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009913b  mov     rbx, rax
0x14009913e  mov     [rsp+9B0h+var_960], rax
0x140099143  lea     r15, aDirwalkertaskM_0; "DirWalkerTask::MoveinStep"
0x14009914a  lea     r12, aDirw; "DIRW"
0x140099151  test    rax, rax
0x140099154  jnz     loc_140099213
0x14009915a  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140099161  test    rax, rax
0x140099164  jz      short loc_1400991B4
0x140099166  cmp     [rax+40h], edi
0x140099169  jz      short loc_1400991B4
0x14009916b  cmp     dword ptr [rax+38h], 4
0x14009916f  jl      short loc_1400991B4
0x140099171  mov     [rsp+9B0h+var_940], r15
0x140099176  mov     [rsp+9B0h+var_938], 510h
0x14009917e  mov     [rsp+9B0h+var_934], 4
0x140099186  mov     [rbp+8B0h+var_930], r12
0x14009918a  lea     rcx, [rbp+8B0h+var_608]
0x140099191  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140099196  mov     [rsp+9B0h+var_960], rax
0x14009919b  mov     r9, r13
0x14009919e  lea     r8, [rsp+9B0h+var_960]
0x1400991a3  lea     rdx, aGhostedFileDel; "Ghosted file deleted:%ws (fid:%?)"
0x1400991aa  lea     rcx, [rsp+9B0h+var_940]
0x1400991af  call    ??$DbgPrint@GPEBGVFileId@@@dbgobj@@QEAA_KPEBGAEBQEBGAEBVFileId@@@Z; dbgobj::DbgPrint<ushort,ushort const *,FileId>(ushort const *,ushort const * const &,FileId const &)
0x1400991b4  call    cs:__imp_GetCurrentThreadId
0x1400991bb  nop     dword ptr [rax+rax+00h]
0x1400991c0  mov     [rsp+9B0h+var_970], rdi
0x1400991c5  mov     [rsp+9B0h+var_978], eax
0x1400991c9  mov     dword ptr [rsp+9B0h+var_980], 512h
0x1400991d1  lea     rax, aDirwalkertaskM_1; "DirWalkerTask::MoveinStep"
0x1400991d8  mov     [rsp+9B0h+var_988], rax
0x1400991dd  lea     rax, aBaseFsRemotefs_90; "base\\fs\\remotefs\\frs\\src\\db\\dirwa"...
0x1400991e4  mov     [rsp+9B0h+var_990], rax
0x1400991e9  mov     r9d, 1
0x1400991ef  xor     r8d, r8d
0x1400991f2  lea     edx, [r9+1]
0x1400991f6  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400991fb  mov     rbx, rax
0x1400991fe  mov     [rsp+9B0h+var_960], rax
0x140099203  jmp     short loc_140099213
0x140099205  lea     r12, aDirw; "DIRW"
0x14009920c  lea     r15, aDirwalkertaskM_0; "DirWalkerTask::MoveinStep"
0x140099213  test    rbx, rbx
0x140099216  jnz     loc_140099550
0x14009921c  mov     qword ptr [rsp+9B0h+var_950], rdi
0x140099221  lea     rdx, [rsp+9B0h+var_950]
0x140099226  mov     rcx, [r14+0B0h]
0x14009922d  call    ?GetUsnConsumer@VolumeManager@@QEAAPEAVFrsStatus@@AEAV?$ScopedRef@VUsnConsumerInterface@@@@@Z; VolumeManager::GetUsnConsumer(ScopedRef<UsnConsumerInterface> &)
0x140099232  mov     rbx, rax
0x140099235  mov     [rsp+9B0h+var_960], rax
0x14009923a  test    rax, rax
0x14009923d  jnz     loc_140099326
0x140099243  cmp     [rsp+9B0h+var_958], edi
0x140099247  jz      short loc_140099257
0x140099249  cmp     [rbp+8B0h+var_5D0], 1
0x140099251  jz      loc_140099326
0x140099257  mov     rax, [rsi+8]
0x14009925b  add     rax, 50h ; 'P'
0x14009925f  mov     qword ptr [rsp+9B0h+var_978], rax
0x140099264  mov     eax, dword ptr [rbp+8B0h+var_61C+0Ch]
0x14009926a  mov     dword ptr [rsp+9B0h+var_980], eax
0x14009926e  lea     rax, [rbp+8B0h+var_310]
0x140099275  mov     [rsp+9B0h+var_988], rax
0x14009927a  lea     rax, [rbp+8B0h+var_920]
0x14009927e  mov     [rsp+9B0h+var_990], rax
0x140099283  mov     r9, r13
0x140099286  lea     r8, [rbp+8B0h+var_608]
0x14009928d  mov     rdx, qword ptr [rsp+9B0h+var_950]
0x140099292  mov     rcx, r14
0x140099295  call    ?NotToReplicate@DirWalkerTask@@AEAAHPEAVUsnConsumerInterface@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVFileId@@2AEBVUID@@KAEBVContentSetFilter@@@Z; DirWalkerTask::NotToReplicate(UsnConsumerInterface *,std::wstring const &,FileId const &,FileId const &,UID const &,ulong,ContentSetFilter const &)
0x14009929a  test    eax, eax
0x14009929c  jz      loc_140099326
0x1400992a2  cmp     [rsp+9B0h+var_958], edi
0x1400992a6  jz      short loc_1400992D7
0x1400992a8  mov     rbx, [rsi+8]
0x1400992ac  lea     rdx, [rbp+8B0h+var_5E0]; struct ID_RECORD *
0x1400992b3  lea     rcx, [rbp+8B0h+var_8F8]; this
0x1400992b7  call    ??0ID_RECORD@@QEAA@AEBV0@@Z; ID_RECORD::ID_RECORD(ID_RECORD const &)
0x1400992bc  mov     r8, rbx
0x1400992bf  mov     rdx, rax
0x1400992c2  mov     rcx, r14
0x1400992c5  call    ?TombstoneFilteredContent@DirWalkerTask@@AEAAPEAVFrsStatus@@VID_RECORD@@PEBVJob@1@@Z; DirWalkerTask::TombstoneFilteredContent(ID_RECORD,DirWalkerTask::Job const *)
0x1400992ca  mov     rbx, rax
0x1400992cd  mov     [rsp+9B0h+var_960], rax
0x1400992d2  test    rax, rax
0x1400992d5  jnz     short loc_140099326
0x1400992d7  call    cs:__imp_GetCurrentThreadId
0x1400992de  nop     dword ptr [rax+rax+00h]
0x1400992e3  mov     [rsp+9B0h+var_970], rdi
0x1400992e8  mov     [rsp+9B0h+var_978], eax
0x1400992ec  mov     dword ptr [rsp+9B0h+var_980], 533h
0x1400992f4  lea     rax, aDirwalkertaskM_1; "DirWalkerTask::MoveinStep"
0x1400992fb  mov     [rsp+9B0h+var_988], rax
0x140099300  lea     rax, aBaseFsRemotefs_90; "base\\fs\\remotefs\\frs\\src\\db\\dirwa"...
0x140099307  mov     [rsp+9B0h+var_990], rax
0x14009930c  mov     r9d, 1
0x140099312  xor     r8d, r8d
0x140099315  lea     edx, [r9+1]
0x140099319  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14009931e  mov     rbx, rax
  ... truncated ...
```
