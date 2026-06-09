# DBClone::PreExport(FilePath &,int)

- ea: `0x1400362c0`
- end: `0x140036bd0`
- name: `?PreExport@DBClone@@AEAAPEAVFrsStatus@@AEAVFilePath@@H@Z`
- size: `2320`
- prototype: `struct FrsStatus *__fastcall(DBClone *__hidden this, struct FilePath *, int)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config`

## callers

- `0x14002ddb0`

## callees

- `0x14000d980`
- `0x14000dcc0`
- `0x14000ee94`
- `0x140019358`
- `0x14001c1ac`
- `0x1400248f4`
- `0x140028eec`
- `0x140029514`
- `0x1400362c0`
- `0x1400bdc18`
- `0x1400be2b8`
- `0x1401b9494`
- `0x1401be04c`
- `0x1401beb30`
- `0x1401beb7c`
- `0x1401bebec`
- `0x1401bf310`
- `0x140223010`

## import_xrefs

- `KERNEL32!CopyFileExW` at `0x1400367db`
- `KERNEL32!CopyFileExW` at `0x1400369aa`
- `KERNEL32!CopyFileExW` at `0x1400367db`
- `KERNEL32!CopyFileExW` at `0x1400369aa`
- `KERNEL32!GetLastError` at `0x1400367fd`
- `KERNEL32!GetLastError` at `0x1400369cc`
- `KERNEL32!GetLastError` at `0x1400367fd`
- `KERNEL32!GetLastError` at `0x1400369cc`
- `KERNEL32!GetCurrentThreadId` at `0x1400363b3`
- `KERNEL32!GetCurrentThreadId` at `0x1400364bd`
- `KERNEL32!GetCurrentThreadId` at `0x1400365dc`
- `KERNEL32!GetCurrentThreadId` at `0x1400366a1`
- `KERNEL32!GetCurrentThreadId` at `0x140036744`
- `KERNEL32!GetCurrentThreadId` at `0x1400367ef`
- `KERNEL32!GetCurrentThreadId` at `0x1400369be`
- `KERNEL32!GetCurrentThreadId` at `0x140036aee`
- `KERNEL32!GetCurrentThreadId` at `0x1400363b3`
- `KERNEL32!GetCurrentThreadId` at `0x1400364bd`
- `KERNEL32!GetCurrentThreadId` at `0x1400365dc`
- `KERNEL32!GetCurrentThreadId` at `0x1400366a1`
- `KERNEL32!GetCurrentThreadId` at `0x140036744`
- `KERNEL32!GetCurrentThreadId` at `0x1400367ef`
- `KERNEL32!GetCurrentThreadId` at `0x1400369be`
- `KERNEL32!GetCurrentThreadId` at `0x140036aee`
- `SHLWAPI!PathIsDirectoryW` at `0x140036444`
- `SHLWAPI!PathIsDirectoryW` at `0x140036444`

## string_xrefs

- `0x14003659d`: `config.xml`
- `0x140036370`: `Processing PreExport. DB Path:%? Destination:%?`
- `0x1400364ad`: `Failed to find the destination path:%? error:%?`
- `0x1400368a1`: `Failed to copy the backup DB file from:%? to:%? error:%?`
- `0x140036a70`: `Failed to copy the clone DB file from:%? to:%? error:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
struct FrsStatus *__fastcall DBClone::PreExport(DBClone *this, struct FilePath *a2, int a3)
{
  int v3; // r12d
  __int64 v5; // rdi
  struct FrsStatus *v6; // rbx
  __int64 v7; // rdx
  int v8; // eax
  DWORD CurrentThreadId; // eax
  __int64 v10; // rcx
  __int64 v11; // rax
  DWORD v13; // eax
  __int64 v14; // rcx
  struct FilePath *v15; // r15
  DWORD v16; // eax
  __int64 v17; // rcx
  DWORD v18; // eax
  __int64 v19; // rcx
  DWORD v20; // eax
  __int64 v21; // rcx
  char v22; // al
  __int64 v23; // r13
  __int64 v24; // r15
  DWORD v25; // ebx
  DWORD v26; // eax
  WINBOOL *pbCancel; // rcx
  __int64 v28; // r14
  DWORD v29; // ebx
  DWORD LastError; // eax
  DWORD v31; // eax
  __int64 v32; // rcx
  void **v34; // [rsp+50h] [rbp-49h] BYREF
  __int64 v35; // [rsp+58h] [rbp-41h] BYREF
  void **v36; // [rsp+60h] [rbp-39h] BYREF
  __int64 v37; // [rsp+68h] [rbp-31h] BYREF
  void **v38; // [rsp+70h] [rbp-29h] BYREF
  __int64 v39; // [rsp+78h] [rbp-21h] BYREF
  void **v40; // [rsp+80h] [rbp-19h] BYREF
  __int64 v41; // [rsp+88h] [rbp-11h] BYREF
  void **v42; // [rsp+90h] [rbp-9h] BYREF
  int v43; // [rsp+98h] [rbp-1h] BYREF
  int v44; // [rsp+9Ch] [rbp+3h]
  const wchar_t *v45; // [rsp+A0h] [rbp+7h]
  __int64 v46; // [rsp+100h] [rbp+67h] BYREF
  struct FilePath *v47; // [rsp+108h] [rbp+6Fh]
  int v48; // [rsp+110h] [rbp+77h]
  __int64 v49; // [rsp+118h] [rbp+7Fh] BYREF

  v48 = a3;
  v47 = a2;
  v3 = a3;
  v5 = 0;
  v6 = 0;
  FilePath::FilePath((FilePath *)&v38);
  FilePath::FilePath((FilePath *)&v40);
  FilePath::FilePath((FilePath *)&v36);
  FilePath::FilePath((FilePath *)&v34);
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v42 = (void **)L"DBClone::PreExport";
    v43 = 4518;
    v44 = 4;
    v45 = L"DBCL";
    v46 = *(_QWORD *)(v7 + 8) + 18LL;
    v49 = *((_QWORD *)this + 21) + 18LL;
    dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short *>(
      &v42,
      L"Processing PreExport. DB Path:%? Destination:%?",
      &v49,
      &v46);
  }
  ScopedLock::ScopedLock((ScopedLock *)&v42, (struct ScopedCS *)DBClone::cloneCS);
  v8 = *((_DWORD *)this + 8);
  if ( v8 == 2 )
  {
    *((_DWORD *)this + 8) = 4;
    goto LABEL_9;
  }
  if ( (unsigned int)(v8 - 6) > 1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v6 = (struct FrsStatus *)FrsStatusList::PushNewError(
                               v10,
                               9602,
                               0,
                               3,
                               "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                               "DBClone::PreExport",
                               4546,
                               CurrentThreadId,
                               0);
LABEL_9:
    ScopedLock::~ScopedLock((ScopedLock *)&v42);
    if ( v6 )
      goto LABEL_56;
    if ( !(*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120) )
    {
      v11 = *((_QWORD *)this + 25);
      if ( !*(_QWORD *)(v11 + 8) || !PathIsDirectoryW((LPCWSTR)(v11 + 18)) )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
        {
          v42 = (void **)L"DBClone::PreExport";
          v43 = 4554;
          v44 = 2;
          v45 = L"DBCL";
          v46 = *((_QWORD *)this + 25) + 18LL;
          dbgobj::DbgPrint<unsigned short,unsigned short const *,FrsStatus>(
            &v42,
            L"Failed to find the destination path:%? error:%?",
            &v46,
            0);
        }
        v13 = GetCurrentThreadId();
        v6 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                   v14,
                                   1168,
                                   0,
                                   1,
                                   "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                   "DBClone::PreExport",
                                   4557,
                                   v13,
                                   0);
        if ( v6 )
          goto LABEL_56;
      }
    }
    FilePath::Set((FilePath *)&v38, (const unsigned __int16 *)(*((_QWORD *)this + 21) + 18LL));
    LOWORD(v46) = 92;
    FrsStringImpl<unsigned short,char>::Append(&v39, &v46, 1);
    FilePath::operator=(&v40, &v38);
    FilePath::Append((FilePath *)&v38, L"dfsr.db");
    FilePath::Append((FilePath *)&v40, L"dfsr.db.backup");
    if ( !v3 )
    {
      LODWORD(v49) = 0;
      v15 = v47;
      FilePath::FilePath((FilePath *)&v42, v47);
      LOWORD(v46) = 92;
      FrsStringImpl<unsigned short,char>::Append(&v43, &v46, 1);
      FilePath::Append((FilePath *)&v42, L"config.xml");
      FileUtil::CreateWin32LongPath((const struct FilePath *)&v42, (struct FilePath *)&v34);
      v6 = FileUtil::FileExists((const unsigned __int16 *)(v35 + 18), (int *)&v49);
      if ( !v6 )
      {
        if ( !(_DWORD)v49
          || (v16 = GetCurrentThreadId(),
              (v6 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                          v17,
                                          183,
                                          0,
                                          1,
                                          "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                          "DBClone::PreExport",
                                          4589,
                                          v16,
                                          0)) == 0) )
        {
          LODWORD(v49) = 0;
          FilePath::Set((FilePath *)&v36, (const unsigned __int16 *)(*((_QWORD *)v15 + 1) + 18LL));
          LOWORD(v46) = 92;
          FrsStringImpl<unsigned short,char>::Append(&v37, &v46, 1);
          FilePath::Append((FilePath *)&v36, L"dfsr.db.clone");
          FrsStringImpl<unsigned short,char>::SetEmpty(&v35);
          FileUtil::CreateWin32LongPath((const struct FilePath *)&v36, (struct FilePath *)&v34);
          v6 = FileUtil::FileExists((const unsigned __int16 *)(v35 + 18), (int *)&v49);
          if ( !v6 )
          {
            if ( (_DWORD)v49 )
            {
              v18 = GetCurrentThreadId();
              v6 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                         v19,
                                         183,
                                         0,
                                         1,
                                         "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                         "DBClone::PreExport",
                                         4603,
                                         v18,
                                         0);
            }
          }
        }
      }
      v42 = &FilePath::`vftable';
      FrsStringImpl<char,unsigned short>::ReleaseBody(&v43);
      if ( v6 )
        goto LABEL_56;
      LODWORD(v46) = 0;
      FrsStringImpl<unsigned short,char>::SetEmpty(&v35);
      FileUtil::CreateWin32LongPath((const struct FilePath *)&v40, (struct FilePath *)&v34);
      v6 = FileUtil::FileExists((const unsigned __int16 *)(v35 + 18), (int *)&v46);
      if ( v6 )
        goto LABEL_56;
      if ( (_DWORD)v46 )
      {
        v20 = GetCurrentThreadId();
        v6 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                   v21,
                                   183,
                                   0,
                                   1,
                                   "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                   "DBClone::PreExport",
                                   4620,
                                   v20,
                                   0);
        if ( v6 )
          goto LABEL_56;
      }
    }
    v22 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120);
    v23 = v39;
    if ( v22 || *((_DWORD *)this + 36) )
      goto LABEL_44;
    v24 = v41 + 18;
    if ( CopyFileExW((LPCWSTR)(v39 + 18), (LPCWSTR)(v41 + 18), 0, 0, (LPBOOL)this + 36, 0) )
    {
      if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 4 )
      {
LABEL_43:
        v3 = v48;
LABEL_44:
        FilePath::Set((FilePath *)&v36, (const unsigned __int16 *)(*((_QWORD *)v47 + 1) + 18LL));
        LOWORD(v46) = 92;
        FrsStringImpl<unsigned short,char>::Append(&v37, &v46, 1);
        FilePath::Append((FilePath *)&v36, L"dfsr.db");
        if ( (*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120) )
          goto LABEL_57;
        pbCancel = (WINBOOL *)((char *)this + 144);
        if ( *((_DWORD *)this + 36) )
          goto LABEL_57;
        v28 = v37 + 18;
        if ( CopyFileExW((LPCWSTR)(v23 + 18), (LPCWSTR)(v37 + 18), 0, 0, pbCancel, v3 == 0) )
        {
          if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 4 )
            goto LABEL_57;
          v42 = (void **)L"DBClone::PreExport";
          v43 = 4676;
          v44 = 4;
          v45 = L"DBCL";
          v46 = v28;
          v49 = v23 + 18;
          dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short *>(
            &v42,
            L"Successfully copied the clone DB file from:%? to:%?",
            &v49,
            &v46);
        }
        else
        {
          v29 = GetCurrentThreadId();
          LastError = GetLastError();
          v6 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                     "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                     LastError,
                                     0,
                                     1,
                                     "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                     "DBClone::PreExport",
                                     4669,
                                     v29,
                                     0);
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
          {
            v42 = (void **)L"DBClone::PreExport";
            v43 = 4670;
            v44 = 2;
            v45 = L"DBCL";
            v46 = v28;
            v49 = v23 + 18;
            dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short const *,FrsStatus>(
              (unsigned int)&v42,
              (unsigned int)L"Failed to copy the clone DB file from:%? to:%? error:%?",
              (unsigned int)&v49,
              (unsigned int)&v46,
              (__int64)v6);
          }
        }
        if ( !v6 )
        {
LABEL_57:
          v34 = &FilePath::`vftable';
          FrsStringImpl<char,unsigned short>::ReleaseBody(&v35);
          v36 = &FilePath::`vftable';
          FrsStringImpl<char,unsigned short>::ReleaseBody(&v37);
          v40 = &FilePath::`vftable';
          FrsStringImpl<char,unsigned short>::ReleaseBody(&v41);
          v38 = &FilePath::`vftable';
          FrsStringImpl<char,unsigned short>::ReleaseBody(&v39);
          return (struct FrsStatus *)v5;
        }
LABEL_56:
        v31 = GetCurrentThreadId();
        v5 = FrsStatusList::PushNewError(
               v32,
               *((unsigned int *)v6 + 1),
               *((unsigned int *)v6 + 2),
               *(unsigned int *)v6,
               "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
               "DBClone::PreExport",
               4682,
               v31,
               v6);
        goto LABEL_57;
      }
      v42 = (void **)L"DBClone::PreExport";
      v43 = 4641;
      v44 = 4;
      v45 = L"DBCL";
      v46 = v24;
      v49 = v23 + 18;
      dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short *>(
        &v42,
        L"Successfully copied the backup DB file from:%? to:%?",
        &v49,
        &v46);
    }
    else
    {
      v25 = GetCurrentThreadId();
      v26 = GetLastError();
      v6 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                 "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                 v26,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                 "DBClone::PreExport",
                                 4634,
                                 v25,
                                 0);
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v42 = (void **)L"DBClone::PreExport";
        v43 = 4635;
        v44 = 2;
        v45 = L"DBCL";
        v46 = v24;
        v49 = v23 + 18;
        dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short const *,FrsStatus>(
          (unsigned int)&v42,
          (unsigned int)L"Failed to copy the backup DB file from:%? to:%? error:%?",
          (unsigned int)&v49,
          (unsigned int)&v46,
          (__int64)v6);
      }
    }
    if ( v6 )
      goto LABEL_56;
    goto LABEL_43;
  }
  ScopedLock::~ScopedLock((ScopedLock *)&v42);
  v34 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v35);
  v36 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v37);
  v40 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v41);
  v38 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v39);
  return 0;
}

```

## disassembly

```asm
0x1400362c0  mov     [rsp-8+arg_10], r8d
0x1400362c5  mov     [rsp-8+arg_8], rdx
0x1400362ca  push    rbp
0x1400362cb  push    rbx
0x1400362cc  push    rsi
0x1400362cd  push    rdi
0x1400362ce  push    r12
0x1400362d0  push    r13
0x1400362d2  push    r14
0x1400362d4  push    r15
0x1400362d6  lea     rbp, [rsp-1Fh]
0x1400362db  sub     rsp, 0B8h
0x1400362e2  mov     r12d, r8d
0x1400362e5  mov     r14, rcx
0x1400362e8  xor     edi, edi
0x1400362ea  mov     ebx, edi
0x1400362ec  lea     rcx, [rbp+57h+var_80]; this
0x1400362f0  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x1400362f5  nop
0x1400362f6  lea     rcx, [rbp+57h+var_70]; this
0x1400362fa  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x1400362ff  nop
0x140036300  lea     rcx, [rbp+57h+var_90]; this
0x140036304  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x140036309  nop
0x14003630a  lea     rcx, [rbp+57h+var_A0]; this
0x14003630e  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x140036313  nop
0x140036314  lea     esi, [rdi+4]
0x140036317  lea     rcx, aDbclonePreexpo_0; "DBClone::PreExport"
0x14003631e  lea     r8, aDbcl; "DBCL"
0x140036325  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14003632c  test    rax, rax
0x14003632f  jz      short loc_140036380
0x140036331  cmp     [rax+40h], edi
0x140036334  jz      short loc_140036380
0x140036336  cmp     [rax+38h], esi
0x140036339  jl      short loc_140036380
0x14003633b  mov     [rbp+57h+var_60], rcx
0x14003633f  mov     [rbp+57h+var_58], 11A6h
0x140036346  mov     [rbp+57h+var_54], esi
0x140036349  mov     [rbp+57h+var_50], r8
0x14003634d  mov     rax, [rdx+8]
0x140036351  add     rax, 12h
0x140036355  mov     [rbp+57h+arg_0], rax
0x140036359  mov     rax, [r14+0A8h]
0x140036360  add     rax, 12h
0x140036364  mov     [rbp+57h+arg_18], rax
0x140036368  lea     r9, [rbp+57h+arg_0]
0x14003636c  lea     r8, [rbp+57h+arg_18]
0x140036370  lea     rdx, aProcessingPree; "Processing PreExport. DB Path:%? Destin"...
0x140036377  lea     rcx, [rbp+57h+var_60]
0x14003637b  call    ??$DbgPrint@GPEBGPEAG@dbgobj@@QEAA_KPEBGAEBQEBGAEBQEAG@Z; dbgobj::DbgPrint<ushort,ushort const *,ushort *>(ushort const *,ushort const * const &,ushort * const &)
0x140036380  lea     rdx, ?cloneCS@DBClone@@2VScopedCS@@A; struct ScopedCS *
0x140036387  lea     rcx, [rbp+57h+var_60]; this
0x14003638b  call    ??0ScopedLock@@QEAA@AEAVScopedCS@@@Z; ScopedLock::ScopedLock(ScopedCS &)
0x140036390  nop
0x140036391  mov     eax, [r14+20h]
0x140036395  cmp     eax, 2
0x140036398  jnz     short loc_1400363A7
0x14003639a  mov     [r14+20h], esi
0x14003639e  lea     r15, aDbclonePreexpo; "DBClone::PreExport"
0x1400363a5  jmp     short loc_1400363FE
0x1400363a7  add     eax, 0FFFFFFFAh
0x1400363aa  cmp     eax, 1
0x1400363ad  jbe     loc_140036B71
0x1400363b3  call    cs:__imp_GetCurrentThreadId
0x1400363ba  nop     dword ptr [rax+rax+00h]
0x1400363bf  mov     [rsp+0F0h+var_B0], rdi
0x1400363c4  mov     [rsp+0F0h+var_B8], eax
0x1400363c8  mov     [rsp+0F0h+var_C0], 11C2h
0x1400363d0  lea     r15, aDbclonePreexpo; "DBClone::PreExport"
0x1400363d7  mov     qword ptr [rsp+0F0h+dwCopyFlags], r15
0x1400363dc  lea     rax, aBaseFsRemotefs_5; "base\\fs\\remotefs\\frs\\src\\main\\dbc"...
0x1400363e3  mov     [rsp+0F0h+pbCancel], rax
0x1400363e8  mov     r9d, 3
0x1400363ee  xor     r8d, r8d
0x1400363f1  mov     edx, 2582h
0x1400363f6  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400363fb  mov     rbx, rax
0x1400363fe  lea     rcx, [rbp+57h+var_60]; this
0x140036402  call    ??1ScopedLock@@QEAA@XZ; ScopedLock::~ScopedLock(void)
0x140036407  lea     rsi, ??_7FilePath@@6B@; const FilePath::`vftable'
0x14003640e  test    rbx, rbx
0x140036411  jnz     loc_140036AEE
0x140036417  lea     r13, [r14+78h]
0x14003641b  mov     rcx, [r13+0]
0x14003641f  mov     rax, [rcx+30h]
0x140036423  mov     rcx, r13
0x140036426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003642b  test    al, al
0x14003642d  jnz     loc_14003650A
0x140036433  mov     rax, [r14+0C8h]
0x14003643a  lea     rcx, [rax+12h]; pszPath
0x14003643e  cmp     [rax+8], rdi
0x140036442  jz      short loc_140036452
0x140036444  call    cs:__imp_PathIsDirectoryW
0x14003644b  nop     dword ptr [rax+rax+00h]
0x140036450  jmp     short loc_140036454
0x140036452  mov     eax, edi
0x140036454  test    eax, eax
0x140036456  jnz     loc_14003650A
0x14003645c  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140036463  test    rax, rax
0x140036466  jz      short loc_1400364BD
0x140036468  cmp     [rax+40h], edi
0x14003646b  jz      short loc_1400364BD
0x14003646d  cmp     dword ptr [rax+38h], 2
0x140036471  jl      short loc_1400364BD
0x140036473  lea     rax, aDbclonePreexpo_0; "DBClone::PreExport"
0x14003647a  mov     [rbp+57h+var_60], rax
0x14003647e  mov     [rbp+57h+var_58], 11CAh
0x140036485  mov     [rbp+57h+var_54], 2
0x14003648c  lea     rax, aDbcl; "DBCL"
0x140036493  mov     [rbp+57h+var_50], rax
0x140036497  mov     rax, [r14+0C8h]
0x14003649e  add     rax, 12h
0x1400364a2  mov     [rbp+57h+arg_0], rax
0x1400364a6  xor     r9d, r9d
0x1400364a9  lea     r8, [rbp+57h+arg_0]
0x1400364ad  lea     rdx, aFailedToFindTh; "Failed to find the destination path:%? "...
0x1400364b4  lea     rcx, [rbp+57h+var_60]
0x1400364b8  call    ??$DbgPrint@GPEBGVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBQEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,ushort const *,FrsStatus>(ushort const *,ushort const * const &,FrsStatus const &)
0x1400364bd  call    cs:__imp_GetCurrentThreadId
0x1400364c4  nop     dword ptr [rax+rax+00h]
0x1400364c9  mov     [rsp+0F0h+var_B0], rdi
0x1400364ce  mov     [rsp+0F0h+var_B8], eax
0x1400364d2  mov     [rsp+0F0h+var_C0], 11CDh
0x1400364da  mov     qword ptr [rsp+0F0h+dwCopyFlags], r15
0x1400364df  lea     rax, aBaseFsRemotefs_5; "base\\fs\\remotefs\\frs\\src\\main\\dbc"...
0x1400364e6  mov     [rsp+0F0h+pbCancel], rax
0x1400364eb  mov     r9d, 1
0x1400364f1  xor     r8d, r8d
0x1400364f4  mov     edx, 490h
0x1400364f9  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400364fe  mov     rbx, rax
0x140036501  test    rax, rax
0x140036504  jnz     loc_140036AEE
0x14003650a  mov     rdx, [r14+0A8h]
0x140036511  add     rdx, 12h; unsigned __int16 *
0x140036515  lea     rcx, [rbp+57h+var_80]; this
0x140036519  call    ?Set@FilePath@@QEAAXPEBG@Z; FilePath::Set(ushort const *)
0x14003651e  mov     eax, 5Ch ; '\'
0x140036523  mov     word ptr [rbp+57h+arg_0], ax
0x140036527  lea     r8d, [rax-5Bh]
0x14003652b  lea     rdx, [rbp+57h+arg_0]
0x14003652f  lea     rcx, [rbp+57h+var_78]
0x140036533  call    ?Append@?$FrsStringImpl@GD@@QEAA_NPEBG_K@Z; FrsStringImpl<ushort,char>::Append(ushort const *,unsigned __int64)
0x140036538  lea     rdx, [rbp+57h+var_80]
0x14003653c  lea     rcx, [rbp+57h+var_70]
0x140036540  call    ??4FilePath@@QEAAAEAV0@AEBV0@@Z; FilePath::operator=(FilePath const &)
0x140036545  lea     rdx, aDfsrDb; "dfsr.db"
0x14003654c  lea     rcx, [rbp+57h+var_80]; this
0x140036550  call    ?Append@FilePath@@QEAAXPEBG@Z; FilePath::Append(ushort const *)
0x140036555  lea     rdx, aDfsrDbBackup; "dfsr.db.backup"
0x14003655c  lea     rcx, [rbp+57h+var_70]; this
0x140036560  call    ?Append@FilePath@@QEAAXPEBG@Z; FilePath::Append(ushort const *)
0x140036565  test    r12d, r12d
0x140036568  jnz     loc_14003678F
0x14003656e  mov     dword ptr [rbp+57h+arg_18], edi
0x140036571  mov     r15, [rbp+57h+arg_8]
0x140036575  mov     rdx, r15; struct FilePath *
0x140036578  lea     rcx, [rbp+57h+var_60]; this
0x14003657c  call    ??0FilePath@@QEAA@AEBV0@@Z; FilePath::FilePath(FilePath const &)
0x140036581  nop
0x140036582  lea     eax, [r12+5Ch]
0x140036587  mov     word ptr [rbp+57h+arg_0], ax
0x14003658b  lea     r8d, [r12+1]
0x140036590  lea     rdx, [rbp+57h+arg_0]
0x140036594  lea     rcx, [rbp+57h+var_58]
0x140036598  call    ?Append@?$FrsStringImpl@GD@@QEAA_NPEBG_K@Z; FrsStringImpl<ushort,char>::Append(ushort const *,unsigned __int64)
0x14003659d  lea     rdx, aConfigXml; "config.xml"
0x1400365a4  lea     rcx, [rbp+57h+var_60]; this
0x1400365a8  call    ?Append@FilePath@@QEAAXPEBG@Z; FilePath::Append(ushort const *)
0x1400365ad  lea     rdx, [rbp+57h+var_A0]; struct FilePath *
0x1400365b1  lea     rcx, [rbp+57h+var_60]; struct FilePath *
0x1400365b5  call    ?CreateWin32LongPath@FileUtil@@SAXAEBVFilePath@@AEAV2@@Z; FileUtil::CreateWin32LongPath(FilePath const &,FilePath &)
0x1400365ba  mov     rcx, [rbp+57h+var_98]
0x1400365be  add     rcx, 12h; unsigned __int16 *
0x1400365c2  lea     rdx, [rbp+57h+arg_18]; int *
0x1400365c6  call    ?FileExists@FileUtil@@SAPEAVFrsStatus@@PEBGAEAH@Z; FileUtil::FileExists(ushort const *,int &)
0x1400365cb  mov     rbx, rax
0x1400365ce  test    rax, rax
0x1400365d1  jnz     loc_1400366EC
0x1400365d7  cmp     dword ptr [rbp+57h+arg_18], edi
0x1400365da  jz      short loc_14003662F
0x1400365dc  call    cs:__imp_GetCurrentThreadId
0x1400365e3  nop     dword ptr [rax+rax+00h]
0x1400365e8  mov     [rsp+0F0h+var_B0], rdi
0x1400365ed  mov     [rsp+0F0h+var_B8], eax
0x1400365f1  mov     [rsp+0F0h+var_C0], 11EDh
0x1400365f9  lea     rax, aDbclonePreexpo; "DBClone::PreExport"
0x140036600  mov     qword ptr [rsp+0F0h+dwCopyFlags], rax
0x140036605  lea     rax, aBaseFsRemotefs_5; "base\\fs\\remotefs\\frs\\src\\main\\dbc"...
0x14003660c  mov     [rsp+0F0h+pbCancel], rax
0x140036611  lea     r9d, [r12+1]
0x140036616  xor     r8d, r8d
0x140036619  mov     edx, 0B7h
0x14003661e  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140036623  mov     rbx, rax
0x140036626  test    rax, rax
0x140036629  jnz     loc_1400366EC
0x14003662f  mov     dword ptr [rbp+57h+arg_18], edi
0x140036632  mov     rdx, [r15+8]
0x140036636  add     rdx, 12h; unsigned __int16 *
0x14003663a  lea     rcx, [rbp+57h+var_90]; this
0x14003663e  call    ?Set@FilePath@@QEAAXPEBG@Z; FilePath::Set(ushort const *)
0x140036643  mov     eax, 5Ch ; '\'
0x140036648  mov     word ptr [rbp+57h+arg_0], ax
0x14003664c  lea     r8d, [rax-5Bh]
0x140036650  lea     rdx, [rbp+57h+arg_0]
0x140036654  lea     rcx, [rbp+57h+var_88]
0x140036658  call    ?Append@?$FrsStringImpl@GD@@QEAA_NPEBG_K@Z; FrsStringImpl<ushort,char>::Append(ushort const *,unsigned __int64)
0x14003665d  lea     rdx, aDfsrDbClone; "dfsr.db.clone"
0x140036664  lea     rcx, [rbp+57h+var_90]; this
0x140036668  call    ?Append@FilePath@@QEAAXPEBG@Z; FilePath::Append(ushort const *)
0x14003666d  lea     rcx, [rbp+57h+var_98]
0x140036671  call    ?SetEmpty@?$FrsStringImpl@GD@@QEAAXXZ; FrsStringImpl<ushort,char>::SetEmpty(void)
0x140036676  lea     rdx, [rbp+57h+var_A0]; struct FilePath *
0x14003667a  lea     rcx, [rbp+57h+var_90]; struct FilePath *
0x14003667e  call    ?CreateWin32LongPath@FileUtil@@SAXAEBVFilePath@@AEAV2@@Z; FileUtil::CreateWin32LongPath(FilePath const &,FilePath &)
0x140036683  mov     rcx, [rbp+57h+var_98]
0x140036687  add     rcx, 12h; unsigned __int16 *
0x14003668b  lea     rdx, [rbp+57h+arg_18]; int *
0x14003668f  call    ?FileExists@FileUtil@@SAPEAVFrsStatus@@PEBGAEAH@Z; FileUtil::FileExists(ushort const *,int &)
0x140036694  mov     rbx, rax
0x140036697  test    rax, rax
0x14003669a  jnz     short loc_1400366EC
0x14003669c  cmp     dword ptr [rbp+57h+arg_18], edi
0x14003669f  jz      short loc_1400366EC
0x1400366a1  call    cs:__imp_GetCurrentThreadId
0x1400366a8  nop     dword ptr [rax+rax+00h]
0x1400366ad  mov     [rsp+0F0h+var_B0], rdi
0x1400366b2  mov     [rsp+0F0h+var_B8], eax
0x1400366b6  mov     [rsp+0F0h+var_C0], 11FBh
0x1400366be  lea     r15, aDbclonePreexpo; "DBClone::PreExport"
0x1400366c5  mov     qword ptr [rsp+0F0h+dwCopyFlags], r15
0x1400366ca  lea     rax, aBaseFsRemotefs_5; "base\\fs\\remotefs\\frs\\src\\main\\dbc"...
0x1400366d1  mov     [rsp+0F0h+pbCancel], rax
0x1400366d6  lea     r9d, [rbx+1]
0x1400366da  xor     r8d, r8d
0x1400366dd  mov     edx, 0B7h
0x1400366e2  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400366e7  mov     rbx, rax
0x1400366ea  jmp     short loc_1400366F3
0x1400366ec  lea     r15, aDbclonePreexpo; "DBClone::PreExport"
0x1400366f3  mov     [rbp+57h+var_60], rsi
0x1400366f7  lea     rcx, [rbp+57h+var_58]
0x1400366fb  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x140036700  test    rbx, rbx
0x140036703  jnz     loc_140036AEE
0x140036709  mov     dword ptr [rbp+57h+arg_0], edi
0x14003670c  lea     rcx, [rbp+57h+var_98]
0x140036710  call    ?SetEmpty@?$FrsStringImpl@GD@@QEAAXXZ; FrsStringImpl<ushort,char>::SetEmpty(void)
0x140036715  lea     rdx, [rbp+57h+var_A0]; struct FilePath *
0x140036719  lea     rcx, [rbp+57h+var_70]; struct FilePath *
0x14003671d  call    ?CreateWin32LongPath@FileUtil@@SAXAEBVFilePath@@AEAV2@@Z; FileUtil::CreateWin32LongPath(FilePath const &,FilePath &)
0x140036722  mov     rcx, [rbp+57h+var_98]
0x140036726  add     rcx, 12h; unsigned __int16 *
0x14003672a  lea     rdx, [rbp+57h+arg_0]; int *
0x14003672e  call    ?FileExists@FileUtil@@SAPEAVFrsStatus@@PEBGAEAH@Z; FileUtil::FileExists(ushort const *,int &)
0x140036733  mov     rbx, rax
0x140036736  test    rax, rax
0x140036739  jnz     loc_140036AEE
0x14003673f  cmp     dword ptr [rbp+57h+arg_0], edi
0x140036742  jz      short loc_14003678F
0x140036744  call    cs:__imp_GetCurrentThreadId
0x14003674b  nop     dword ptr [rax+rax+00h]
0x140036750  mov     [rsp+0F0h+var_B0], rdi
0x140036755  mov     [rsp+0F0h+var_B8], eax
0x140036759  mov     [rsp+0F0h+var_C0], 120Ch
0x140036761  mov     qword ptr [rsp+0F0h+dwCopyFlags], r15
0x140036766  lea     rax, aBaseFsRemotefs_5; "base\\fs\\remotefs\\frs\\src\\main\\dbc"...
0x14003676d  mov     [rsp+0F0h+pbCancel], rax
0x140036772  lea     r9d, [rbx+1]
0x140036776  xor     r8d, r8d
0x140036779  mov     edx, 0B7h
0x14003677e  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140036783  mov     rbx, rax
0x140036786  test    rax, rax
0x140036789  jnz     loc_140036AEE
0x14003678f  mov     rax, [r13+0]
0x140036793  mov     rcx, r13
0x140036796  mov     rax, [rax+30h]
0x14003679a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003679f  mov     r13, [rbp+57h+var_78]
0x1400367a3  test    al, al
0x1400367a5  jnz     loc_14003691B
0x1400367ab  lea     rcx, [r14+90h]
0x1400367b2  cmp     [rcx], edi
0x1400367b4  jnz     loc_14003691B
0x1400367ba  mov     r15, [rbp+57h+var_68]
0x1400367be  add     r15, 12h
0x1400367c2  lea     r12, [r13+12h]
0x1400367c6  mov     [rsp+0F0h+dwCopyFlags], edi; dwCopyFlags
0x1400367ca  mov     [rsp+0F0h+pbCancel], rcx; pbCancel
0x1400367cf  xor     r9d, r9d; lpData
0x1400367d2  xor     r8d, r8d; lpProgressRoutine
0x1400367d5  mov     rdx, r15; lpNewFileName
0x1400367d8  mov     rcx, r12; lpExistingFileName
  ... truncated ...
```
