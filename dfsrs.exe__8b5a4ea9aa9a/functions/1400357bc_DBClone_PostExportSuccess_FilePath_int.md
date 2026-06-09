# DBClone::PostExportSuccess(FilePath &,int)

- ea: `0x1400357bc`
- end: `0x140035ed4`
- name: `?PostExportSuccess@DBClone@@AEAAPEAVFrsStatus@@AEAVFilePath@@H@Z`
- size: `1816`
- prototype: `struct FrsStatus *(DBClone *__hidden this, struct FilePath *, int)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, installer_update`

## callers

- `0x14002ddb0`

## callees

- `0x14000cd1c`
- `0x14000e34c`
- `0x14000ee94`
- `0x140019358`
- `0x14001c1ac`
- `0x140029448`
- `0x140029514`
- `0x1400357bc`
- `0x140036d50`
- `0x1400aee70`
- `0x1401b9494`
- `0x1401be04c`
- `0x1401beb30`
- `0x1401bebec`
- `0x1401befb8`
- `0x140223010`

## import_xrefs

- `KERNEL32!CopyFileExW` at `0x14003594b`
- `KERNEL32!CopyFileExW` at `0x14003594b`
- `KERNEL32!DeleteFileW` at `0x140035c75`
- `KERNEL32!DeleteFileW` at `0x140035d9a`
- `KERNEL32!DeleteFileW` at `0x140035c75`
- `KERNEL32!DeleteFileW` at `0x140035d9a`
- `KERNEL32!GetLastError` at `0x14003596d`
- `KERNEL32!GetLastError` at `0x140035c97`
- `KERNEL32!GetLastError` at `0x140035dbc`
- `KERNEL32!GetLastError` at `0x14003596d`
- `KERNEL32!GetLastError` at `0x140035c97`
- `KERNEL32!GetLastError` at `0x140035dbc`
- `KERNEL32!GetCurrentThreadId` at `0x14003595f`
- `KERNEL32!GetCurrentThreadId` at `0x140035c89`
- `KERNEL32!GetCurrentThreadId` at `0x140035dae`
- `KERNEL32!GetCurrentThreadId` at `0x140035e68`
- `KERNEL32!GetCurrentThreadId` at `0x14003595f`
- `KERNEL32!GetCurrentThreadId` at `0x140035c89`
- `KERNEL32!GetCurrentThreadId` at `0x140035dae`
- `KERNEL32!GetCurrentThreadId` at `0x140035e68`

## string_xrefs

- `0x140035d7e`: `$db_update$`
- `0x140035a91`: `Failed to copy the clone DB file from:%? to:%? error:%?`
- `0x140035bb9`: `Failed to delete %? error:%?`
- `0x140035c11`: `Failed to delete %? error:%?`
- `0x140035d1e`: `Failed to delete %?. Error:%?`
- `0x140035e45`: `Failed to delete %?. Error:%?`
- `0x140035a13`: `The clone DB file already exists:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct FrsStatus *__fastcall DBClone::PostExportSuccess(DBClone *this, struct FilePath *a2, int a3)
{
  __int64 v6; // rdi
  struct FrsStatus *v7; // rbx
  struct FrsStatus *v8; // r14
  void **v9; // r12
  DWORD CurrentThreadId; // ebx
  DWORD LastError; // eax
  struct FrsStatus *v12; // rax
  struct FrsStatus *v13; // rax
  const struct FilePath *v14; // rsi
  const WCHAR *DisplayPath; // rax
  DWORD v16; // ebx
  DWORD v17; // eax
  const WCHAR *v18; // rax
  DWORD v19; // ebx
  DWORD v20; // eax
  DWORD v21; // eax
  __int64 v22; // rcx
  void **v24; // [rsp+58h] [rbp-19h] BYREF
  __int64 v25; // [rsp+60h] [rbp-11h] BYREF
  void **v26; // [rsp+68h] [rbp-9h] BYREF
  _BYTE v27[8]; // [rsp+70h] [rbp-1h] BYREF
  void **v28; // [rsp+78h] [rbp+7h] BYREF
  _QWORD v29[2]; // [rsp+80h] [rbp+Fh] BYREF
  const wchar_t *v30; // [rsp+90h] [rbp+1Fh] BYREF
  int v31; // [rsp+98h] [rbp+27h]
  int v32; // [rsp+9Ch] [rbp+2Bh]
  const wchar_t *v33; // [rsp+A0h] [rbp+2Fh]
  struct FrsStatus *v34; // [rsp+F0h] [rbp+7Fh] BYREF

  v6 = 0;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v28 = (void **)L"DBClone::PostExportSuccess";
    v29[0] = 0x4000012F2LL;
    v29[1] = L"DBCL";
    v34 = (struct FrsStatus *)(*((_QWORD *)this + 25) + 18LL);
    v24 = (void **)(*((_QWORD *)a2 + 1) + 18LL);
    v26 = (void **)(*((_QWORD *)this + 21) + 18LL);
    dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short const *,unsigned short const *,VolumeId>(
      (unsigned int)&v28,
      (_DWORD)a2,
      (unsigned int)&v26,
      (unsigned int)&v24,
      (__int64)&v34,
      (__int64)this + 208);
  }
  v7 = DBClone::SaveContentSetInfo(this);
  if ( v7 )
    goto LABEL_43;
  FilePath::FilePath((FilePath *)&v28, (DBClone *)((char *)this + 192));
  FilePath::FilePath((FilePath *)&v24, a2);
  LOWORD(v34) = 92;
  FrsStringImpl<unsigned short,char>::Append(v29, &v34, 1);
  FilePath::Append((FilePath *)&v28, L"dfsr.db.clone");
  LOWORD(v34) = 92;
  FrsStringImpl<unsigned short,char>::Append(&v25, &v34, 1);
  FilePath::Append((FilePath *)&v24, L"dfsr.db");
  if ( !(*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 15) + 48LL))((char *)this + 120)
    && !*((_DWORD *)this + 36) )
  {
    v8 = (struct FrsStatus *)(v29[0] + 18LL);
    v9 = (void **)(v25 + 18);
    if ( CopyFileExW((LPCWSTR)(v25 + 18), (LPCWSTR)(v29[0] + 18LL), 0, 0, (LPBOOL)this + 36, a3 == 0) )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v30 = L"DBClone::PostExportSuccess";
        v31 = 4901;
        v32 = 4;
        v33 = L"DBCL";
        v34 = v8;
        v26 = v9;
        dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short *>(
          &v30,
          L"Successfully copied the clone DB file from:%? to:%?",
          &v26,
          &v34);
      }
    }
    else
    {
      CurrentThreadId = GetCurrentThreadId();
      LastError = GetLastError();
      v12 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                  "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                  LastError,
                                  0,
                                  1,
                                  "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                  "DBClone::PostExportSuccess",
                                  4887,
                                  CurrentThreadId,
                                  0);
      v7 = v12;
      v34 = v12;
      if ( a3 || *((_DWORD *)v12 + 1) != 183 )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
        {
          v30 = L"DBClone::PostExportSuccess";
          v31 = 4894;
          v32 = 2;
          v33 = L"DBCL";
          v34 = v8;
          v26 = v9;
          dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short const *,FrsStatus>(
            (unsigned int)&v30,
            (unsigned int)L"Failed to copy the clone DB file from:%? to:%? error:%?",
            (unsigned int)&v26,
            (unsigned int)&v34,
            (__int64)v12);
        }
      }
      else
      {
        CLEAR_ERROR(&v34);
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v30 = L"DBClone::PostExportSuccess";
          v31 = 4890;
          v32 = 4;
          v33 = L"DBCL";
          v26 = (void **)v8;
          dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v30, L"The clone DB file already exists:%?", &v26);
          v7 = v34;
        }
        else
        {
          v7 = v34;
        }
      }
    }
  }
  v24 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v25);
  v28 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(v29);
  if ( v7 )
    goto LABEL_43;
  v26 = &NtfsFileSystem::`vftable';
  v13 = (struct FrsStatus *)NtfsFileSystem::DeleteDirectory(&v26, (char *)this + 208, *((_QWORD *)a2 + 1) + 18LL, 1);
  v7 = v13;
  v34 = v13;
  if ( v13 )
  {
    if ( (unsigned int)(*((_DWORD *)v13 + 1) - 2) > 1 )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v30 = L"DBClone::PostExportSuccess";
        v31 = 4925;
        v32 = 2;
        v33 = L"DBCL";
        v34 = (struct FrsStatus *)(*((_QWORD *)a2 + 1) + 18LL);
        dbgobj::DbgPrint<unsigned short,unsigned short const *,FrsStatus>(
          &v30,
          L"Failed to delete %? error:%?",
          &v34,
          v13);
      }
    }
    else
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
      {
        v30 = L"DBClone::PostExportSuccess";
        v31 = 4919;
        v32 = 3;
        v33 = L"DBCL";
        v24 = (void **)(*((_QWORD *)a2 + 1) + 18LL);
        dbgobj::DbgPrint<unsigned short,unsigned short const *,FrsStatus>(
          &v30,
          L"Failed to delete %? error:%?",
          &v24,
          v13);
      }
      CLEAR_ERROR(&v34);
      v7 = v34;
    }
  }
  if ( v7 )
  {
LABEL_43:
    v14 = (DBClone *)((char *)this + 160);
  }
  else
  {
    v14 = (DBClone *)((char *)this + 160);
    FilePath::FilePath((FilePath *)&v26, v14);
    LOWORD(v34) = 92;
    FrsStringImpl<unsigned short,char>::Append(v27, &v34, 1);
    FilePath::Append((FilePath *)&v26, L"dfsr.db.backup");
    DisplayPath = (const WCHAR *)FilePath::GetDisplayPath(v27);
    if ( !DeleteFileW(DisplayPath) )
    {
      v16 = GetCurrentThreadId();
      v17 = GetLastError();
      v7 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                 "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                 v17,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                 "DBClone::PostExportSuccess",
                                 4940,
                                 v16,
                                 0);
      if ( g_DebugLog )
      {
        if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
        {
          v30 = L"DBClone::PostExportSuccess";
          v31 = 4941;
          v32 = 2;
          v33 = L"DBCL";
          v34 = (struct FrsStatus *)FilePath::GetDisplayPath(v27);
          dbgobj::DbgPrint<unsigned short,unsigned short const *,FrsStatus>(
            &v30,
            L"Failed to delete %?. Error:%?",
            &v34,
            v7);
        }
      }
    }
    v26 = &FilePath::`vftable';
    FrsStringImpl<char,unsigned short>::ReleaseBody(v27);
  }
  if ( v7 )
    goto LABEL_51;
  FilePath::FilePath((FilePath *)&v26, v14);
  LOWORD(v34) = 92;
  FrsStringImpl<unsigned short,char>::Append(v27, &v34, 1);
  FilePath::Append((FilePath *)&v26, L"$db_update$");
  v18 = (const WCHAR *)FilePath::GetDisplayPath(v27);
  if ( !DeleteFileW(v18) )
  {
    v19 = GetCurrentThreadId();
    v20 = GetLastError();
    v7 = (struct FrsStatus *)FrsStatusList::PushNewError(
                               "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                               v20,
                               0,
                               1,
                               "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                               "DBClone::PostExportSuccess",
                               4961,
                               v19,
                               0);
    if ( g_DebugLog )
    {
      if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v30 = L"DBClone::PostExportSuccess";
        v31 = 4962;
        v32 = 2;
        v33 = L"DBCL";
        v34 = (struct FrsStatus *)FilePath::GetDisplayPath(v27);
        dbgobj::DbgPrint<unsigned short,unsigned short const *,FrsStatus>(
          &v30,
          L"Failed to delete %?. Error:%?",
          &v34,
          v7);
      }
    }
  }
  v26 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(v27);
  if ( v7 )
  {
LABEL_51:
    v21 = GetCurrentThreadId();
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v22,
                                 *((unsigned int *)v7 + 1),
                                 *((unsigned int *)v7 + 2),
                                 *(unsigned int *)v7,
                                 "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                 "DBClone::PostExportSuccess",
                                 4969,
                                 v21,
                                 v7);
  }
  return (struct FrsStatus *)v6;
}

```

## disassembly

```asm
0x1400357bc  mov     rax, rsp
0x1400357bf  mov     [rax+8], rbx
0x1400357c3  mov     [rax+10h], rsi
0x1400357c7  mov     [rax+18h], rdi
0x1400357cb  push    rbp
0x1400357cc  push    r12
0x1400357ce  push    r13
0x1400357d0  push    r14
0x1400357d2  push    r15
0x1400357d4  lea     rbp, [rax-5Fh]
0x1400357d8  sub     rsp, 0A0h
0x1400357df  mov     r13d, r8d
0x1400357e2  mov     r15, rdx
0x1400357e5  mov     rsi, rcx
0x1400357e8  lea     r14, aDbclonePostexp; "DBClone::PostExportSuccess"
0x1400357ef  lea     r12, aDbcl; "DBCL"
0x1400357f6  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400357fd  xor     edi, edi
0x1400357ff  test    rax, rax
0x140035802  jz      short loc_140035875
0x140035804  cmp     [rax+40h], edi
0x140035807  jz      short loc_140035875
0x140035809  cmp     dword ptr [rax+38h], 4
0x14003580d  jl      short loc_140035875
0x14003580f  mov     [rbp+57h+var_50], r14
0x140035813  mov     dword ptr [rbp+57h+var_48], 12F2h
0x14003581a  mov     dword ptr [rbp+57h+var_48+4], 4
0x140035821  mov     [rbp+57h+var_40], r12
0x140035825  mov     rax, [rcx+0C8h]
0x14003582c  add     rax, 12h
0x140035830  mov     [rbp+57h+arg_18], rax
0x140035834  mov     rax, [rdx+8]
0x140035838  add     rax, 12h
0x14003583c  mov     [rbp+57h+var_70], rax
0x140035840  mov     rax, [rcx+0A8h]
0x140035847  add     rax, 12h
0x14003584b  mov     [rbp+57h+var_60], rax
0x14003584f  lea     rax, [rcx+0D0h]
0x140035856  mov     qword ptr [rsp+0C0h+dwCopyFlags], rax
0x14003585b  lea     rax, [rbp+57h+arg_18]
0x14003585f  mov     [rsp+0C0h+pbCancel], rax
0x140035864  lea     r9, [rbp+57h+var_70]
0x140035868  lea     r8, [rbp+57h+var_60]
0x14003586c  lea     rcx, [rbp+57h+var_50]
0x140035870  call    ??$DbgPrint@GPEBGPEBGPEBGVVolumeId@@@dbgobj@@QEAA_KPEBGAEBQEBG11AEBVVolumeId@@@Z; dbgobj::DbgPrint<ushort,ushort const *,ushort const *,ushort const *,VolumeId>(ushort const *,ushort const * const &,ushort const * const &,ushort const * const &,VolumeId const &)
0x140035875  mov     rcx, rsi; this
0x140035878  call    ?SaveContentSetInfo@DBClone@@AEAAPEAVFrsStatus@@XZ; DBClone::SaveContentSetInfo(void)
0x14003587d  mov     rbx, rax
0x140035880  test    rax, rax
0x140035883  jnz     loc_140035D3E
0x140035889  lea     rdx, [rsi+0C0h]; struct FilePath *
0x140035890  lea     rcx, [rbp+57h+var_50]; this
0x140035894  call    ??0FilePath@@QEAA@AEBV0@@Z; FilePath::FilePath(FilePath const &)
0x140035899  nop
0x14003589a  mov     rdx, r15; struct FilePath *
0x14003589d  lea     rcx, [rbp+57h+var_70]; this
0x1400358a1  call    ??0FilePath@@QEAA@AEBV0@@Z; FilePath::FilePath(FilePath const &)
0x1400358a6  nop
0x1400358a7  lea     eax, [rbx+5Ch]
0x1400358aa  mov     word ptr [rbp+57h+arg_18], ax
0x1400358ae  lea     r8d, [rbx+1]
0x1400358b2  lea     rdx, [rbp+57h+arg_18]
0x1400358b6  lea     rcx, [rbp+57h+var_48]
0x1400358ba  call    ?Append@?$FrsStringImpl@GD@@QEAA_NPEBG_K@Z; FrsStringImpl<ushort,char>::Append(ushort const *,unsigned __int64)
0x1400358bf  lea     rdx, aDfsrDbClone; "dfsr.db.clone"
0x1400358c6  lea     rcx, [rbp+57h+var_50]; this
0x1400358ca  call    ?Append@FilePath@@QEAAXPEBG@Z; FilePath::Append(ushort const *)
0x1400358cf  lea     eax, [rbx+5Ch]
0x1400358d2  mov     word ptr [rbp+57h+arg_18], ax
0x1400358d6  lea     r8d, [rbx+1]
0x1400358da  lea     rdx, [rbp+57h+arg_18]
0x1400358de  lea     rcx, [rbp+57h+var_68]
0x1400358e2  call    ?Append@?$FrsStringImpl@GD@@QEAA_NPEBG_K@Z; FrsStringImpl<ushort,char>::Append(ushort const *,unsigned __int64)
0x1400358e7  lea     rdx, aDfsrDb; "dfsr.db"
0x1400358ee  lea     rcx, [rbp+57h+var_70]; this
0x1400358f2  call    ?Append@FilePath@@QEAAXPEBG@Z; FilePath::Append(ushort const *)
0x1400358f7  lea     rcx, [rsi+78h]
0x1400358fb  mov     rax, [rcx]
0x1400358fe  mov     rax, [rax+30h]
0x140035902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035907  test    al, al
0x140035909  jnz     loc_140035B0C
0x14003590f  lea     rcx, [rsi+90h]
0x140035916  cmp     [rcx], edi
0x140035918  jnz     loc_140035B0C
0x14003591e  mov     r14, [rbp+57h+var_48]
0x140035922  add     r14, 12h
0x140035926  mov     r12, [rbp+57h+var_68]
0x14003592a  add     r12, 12h
0x14003592e  mov     eax, edi
0x140035930  test    r13d, r13d
0x140035933  setz    al
0x140035936  mov     [rsp+0C0h+dwCopyFlags], eax; dwCopyFlags
0x14003593a  mov     [rsp+0C0h+pbCancel], rcx; pbCancel
0x14003593f  xor     r9d, r9d; lpData
0x140035942  xor     r8d, r8d; lpProgressRoutine
0x140035945  mov     rdx, r14; lpNewFileName
0x140035948  mov     rcx, r12; lpExistingFileName
0x14003594b  call    cs:__imp_CopyFileExW
0x140035952  nop     dword ptr [rax+rax+00h]
0x140035957  test    eax, eax
0x140035959  jnz     loc_140035AA3
0x14003595f  call    cs:__imp_GetCurrentThreadId
0x140035966  nop     dword ptr [rax+rax+00h]
0x14003596b  mov     ebx, eax
0x14003596d  call    cs:__imp_GetLastError
0x140035974  nop     dword ptr [rax+rax+00h]
0x140035979  mov     [rsp+0C0h+var_80], rdi
0x14003597e  mov     dword ptr [rsp+0C0h+var_88], ebx
0x140035982  mov     [rsp+0C0h+var_90], 1317h
0x14003598a  lea     rcx, aDbclonePostexp_0; "DBClone::PostExportSuccess"
0x140035991  mov     qword ptr [rsp+0C0h+dwCopyFlags], rcx
0x140035996  lea     rcx, aBaseFsRemotefs_5; "base\\fs\\remotefs\\frs\\src\\main\\dbc"...
0x14003599d  mov     [rsp+0C0h+pbCancel], rcx
0x1400359a2  mov     r9d, 1
0x1400359a8  xor     r8d, r8d
0x1400359ab  mov     edx, eax
0x1400359ad  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400359b2  mov     rbx, rax
0x1400359b5  mov     [rbp+57h+arg_18], rax
0x1400359b9  test    r13d, r13d
0x1400359bc  jnz     short loc_140035A35
0x1400359be  cmp     dword ptr [rax+4], 0B7h
0x1400359c5  jnz     short loc_140035A35
0x1400359c7  lea     rcx, [rbp+57h+arg_18]; struct FrsStatus **
0x1400359cb  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1400359d0  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400359d7  test    rax, rax
0x1400359da  jz      short loc_140035A2C
0x1400359dc  cmp     [rax+40h], edi
0x1400359df  jz      short loc_140035A2C
0x1400359e1  cmp     dword ptr [rax+38h], 4
0x1400359e5  jl      short loc_140035A2C
0x1400359e7  lea     rax, aDbclonePostexp; "DBClone::PostExportSuccess"
0x1400359ee  mov     [rbp+57h+var_38], rax
0x1400359f2  mov     [rbp+57h+var_30], 131Ah
0x1400359f9  mov     [rbp+57h+var_2C], 4
0x140035a00  lea     r12, aDbcl; "DBCL"
0x140035a07  mov     [rbp+57h+var_28], r12
0x140035a0b  mov     [rbp+57h+var_60], r14
0x140035a0f  lea     r8, [rbp+57h+var_60]
0x140035a13  lea     rdx, aTheCloneDbFile; "The clone DB file already exists:%?"
0x140035a1a  lea     rcx, [rbp+57h+var_38]
0x140035a1e  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x140035a23  mov     rbx, [rbp+57h+arg_18]
0x140035a27  jmp     loc_140035B05
0x140035a2c  mov     rbx, [rbp+57h+arg_18]
0x140035a30  jmp     loc_140035AFE
0x140035a35  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140035a3c  test    rax, rax
0x140035a3f  jz      loc_140035AFE
0x140035a45  cmp     [rax+40h], edi
0x140035a48  jz      loc_140035AFE
0x140035a4e  cmp     dword ptr [rax+38h], 2
0x140035a52  jl      loc_140035AFE
0x140035a58  lea     rax, aDbclonePostexp; "DBClone::PostExportSuccess"
0x140035a5f  mov     [rbp+57h+var_38], rax
0x140035a63  mov     [rbp+57h+var_30], 131Eh
0x140035a6a  mov     [rbp+57h+var_2C], 2
0x140035a71  lea     rax, aDbcl; "DBCL"
0x140035a78  mov     [rbp+57h+var_28], rax
0x140035a7c  mov     [rbp+57h+arg_18], r14
0x140035a80  mov     [rbp+57h+var_60], r12
0x140035a84  mov     [rsp+0C0h+pbCancel], rbx
0x140035a89  lea     r9, [rbp+57h+arg_18]
0x140035a8d  lea     r8, [rbp+57h+var_60]
0x140035a91  lea     rdx, aFailedToCopyTh_0; "Failed to copy the clone DB file from:%"...
0x140035a98  lea     rcx, [rbp+57h+var_38]
0x140035a9c  call    ??$DbgPrint@GPEBGPEBGVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBQEBG1AEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,ushort const *,ushort const *,FrsStatus>(ushort const *,ushort const * const &,ushort const * const &,FrsStatus const &)
0x140035aa1  jmp     short loc_140035AFE
0x140035aa3  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140035aaa  test    rax, rax
0x140035aad  jz      short loc_140035AFE
0x140035aaf  cmp     [rax+40h], edi
0x140035ab2  jz      short loc_140035AFE
0x140035ab4  cmp     dword ptr [rax+38h], 4
0x140035ab8  jl      short loc_140035AFE
0x140035aba  lea     rax, aDbclonePostexp; "DBClone::PostExportSuccess"
0x140035ac1  mov     [rbp+57h+var_38], rax
0x140035ac5  mov     [rbp+57h+var_30], 1325h
0x140035acc  mov     [rbp+57h+var_2C], 4
0x140035ad3  lea     rax, aDbcl; "DBCL"
0x140035ada  mov     [rbp+57h+var_28], rax
0x140035ade  mov     [rbp+57h+arg_18], r14
0x140035ae2  mov     [rbp+57h+var_60], r12
0x140035ae6  lea     r9, [rbp+57h+arg_18]
0x140035aea  lea     r8, [rbp+57h+var_60]
0x140035aee  lea     rdx, aSuccessfullyCo; "Successfully copied the clone DB file f"...
0x140035af5  lea     rcx, [rbp+57h+var_38]
0x140035af9  call    ??$DbgPrint@GPEBGPEAG@dbgobj@@QEAA_KPEBGAEBQEBGAEBQEAG@Z; dbgobj::DbgPrint<ushort,ushort const *,ushort *>(ushort const *,ushort const * const &,ushort * const &)
0x140035afe  lea     r12, aDbcl; "DBCL"
0x140035b05  lea     r14, aDbclonePostexp; "DBClone::PostExportSuccess"
0x140035b0c  lea     r13, ??_7FilePath@@6B@; const FilePath::`vftable'
0x140035b13  mov     [rbp+57h+var_70], r13
0x140035b17  lea     rcx, [rbp+57h+var_68]
0x140035b1b  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x140035b20  nop
0x140035b21  mov     [rbp+57h+var_50], r13
0x140035b25  lea     rcx, [rbp+57h+var_48]
0x140035b29  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x140035b2e  test    rbx, rbx
0x140035b31  jnz     loc_140035D45
0x140035b37  lea     rax, ??_7NtfsFileSystem@@6B@; const NtfsFileSystem::`vftable'
0x140035b3e  mov     [rbp+57h+var_60], rax
0x140035b42  mov     r8, [r15+8]
0x140035b46  add     r8, 12h
0x140035b4a  lea     rdx, [rsi+0D0h]
0x140035b51  lea     r9d, [rbx+1]
0x140035b55  lea     rcx, [rbp+57h+var_60]
0x140035b59  call    ?DeleteDirectory@NtfsFileSystem@@UEAAPEAVFrsStatus@@AEBVVolumeId@@PEBGW4CONTINUE_DELETE@FileSystem@@@Z; NtfsFileSystem::DeleteDirectory(VolumeId const &,ushort const *,FileSystem::CONTINUE_DELETE)
0x140035b5e  mov     rbx, rax
0x140035b61  mov     [rbp+57h+arg_18], rax
0x140035b65  test    rax, rax
0x140035b68  jz      loc_140035C22
0x140035b6e  mov     eax, [rax+4]
0x140035b71  sub     eax, 2
0x140035b74  cmp     eax, 1
0x140035b77  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140035b7e  ja      short loc_140035BD8
0x140035b80  test    rax, rax
0x140035b83  jz      short loc_140035BC9
0x140035b85  cmp     [rax+40h], edi
0x140035b88  jz      short loc_140035BC9
0x140035b8a  cmp     dword ptr [rax+38h], 3
0x140035b8e  jl      short loc_140035BC9
0x140035b90  mov     [rbp+57h+var_38], r14
0x140035b94  mov     [rbp+57h+var_30], 1337h
0x140035b9b  mov     [rbp+57h+var_2C], 3
0x140035ba2  mov     [rbp+57h+var_28], r12
0x140035ba6  mov     rax, [r15+8]
0x140035baa  add     rax, 12h
0x140035bae  mov     [rbp+57h+var_70], rax
0x140035bb2  mov     r9, rbx
0x140035bb5  lea     r8, [rbp+57h+var_70]
0x140035bb9  lea     rdx, aFailedToDelete_6; "Failed to delete %? error:%?"
0x140035bc0  lea     rcx, [rbp+57h+var_38]
0x140035bc4  call    ??$DbgPrint@GPEBGVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBQEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,ushort const *,FrsStatus>(ushort const *,ushort const * const &,FrsStatus const &)
0x140035bc9  lea     rcx, [rbp+57h+arg_18]; struct FrsStatus **
0x140035bcd  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x140035bd2  mov     rbx, [rbp+57h+arg_18]
0x140035bd6  jmp     short loc_140035C22
0x140035bd8  test    rax, rax
0x140035bdb  jz      short loc_140035C22
0x140035bdd  cmp     [rax+40h], edi
0x140035be0  jz      short loc_140035C22
0x140035be2  cmp     dword ptr [rax+38h], 2
0x140035be6  jl      short loc_140035C22
0x140035be8  mov     [rbp+57h+var_38], r14
0x140035bec  mov     [rbp+57h+var_30], 133Dh
0x140035bf3  mov     [rbp+57h+var_2C], 2
0x140035bfa  mov     [rbp+57h+var_28], r12
0x140035bfe  mov     rax, [r15+8]
0x140035c02  add     rax, 12h
0x140035c06  mov     [rbp+57h+arg_18], rax
0x140035c0a  mov     r9, rbx
0x140035c0d  lea     r8, [rbp+57h+arg_18]
0x140035c11  lea     rdx, aFailedToDelete_6; "Failed to delete %? error:%?"
0x140035c18  lea     rcx, [rbp+57h+var_38]
0x140035c1c  call    ??$DbgPrint@GPEBGVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBQEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,ushort const *,FrsStatus>(ushort const *,ushort const * const &,FrsStatus const &)
0x140035c21  nop
0x140035c22  test    rbx, rbx
0x140035c25  jnz     loc_140035D45
0x140035c2b  add     rsi, 0A0h
0x140035c32  mov     rdx, rsi; struct FilePath *
0x140035c35  lea     rcx, [rbp+57h+var_60]; this
0x140035c39  call    ??0FilePath@@QEAA@AEBV0@@Z; FilePath::FilePath(FilePath const &)
0x140035c3e  nop
0x140035c3f  lea     r15d, [rbx+5Ch]
0x140035c43  mov     word ptr [rbp+57h+arg_18], r15w
0x140035c48  lea     r8d, [rbx+1]
0x140035c4c  lea     rdx, [rbp+57h+arg_18]
0x140035c50  lea     rcx, [rbp+57h+var_58]
0x140035c54  call    ?Append@?$FrsStringImpl@GD@@QEAA_NPEBG_K@Z; FrsStringImpl<ushort,char>::Append(ushort const *,unsigned __int64)
0x140035c59  lea     rdx, aDfsrDbBackup; "dfsr.db.backup"
0x140035c60  lea     rcx, [rbp+57h+var_60]; this
0x140035c64  call    ?Append@FilePath@@QEAAXPEBG@Z; FilePath::Append(ushort const *)
0x140035c69  lea     rcx, [rbp+57h+var_58]
0x140035c6d  call    ?GetDisplayPath@FilePath@@SAPEBGAEBV?$FrsStringImpl@GD@@@Z; FilePath::GetDisplayPath(FrsStringImpl<ushort,char> const &)
0x140035c72  mov     rcx, rax; lpFileName
0x140035c75  call    cs:__imp_DeleteFileW
0x140035c7c  nop     dword ptr [rax+rax+00h]
0x140035c81  test    eax, eax
0x140035c83  jnz     loc_140035D2F
0x140035c89  call    cs:__imp_GetCurrentThreadId
0x140035c90  nop     dword ptr [rax+rax+00h]
0x140035c95  mov     ebx, eax
0x140035c97  call    cs:__imp_GetLastError
0x140035c9e  nop     dword ptr [rax+rax+00h]
0x140035ca3  mov     [rsp+0C0h+var_80], rdi
0x140035ca8  mov     dword ptr [rsp+0C0h+var_88], ebx
0x140035cac  mov     [rsp+0C0h+var_90], 134Ch
0x140035cb4  lea     rcx, aDbclonePostexp_0; "DBClone::PostExportSuccess"
0x140035cbb  mov     qword ptr [rsp+0C0h+dwCopyFlags], rcx
0x140035cc0  lea     rcx, aBaseFsRemotefs_5; "base\\fs\\remotefs\\frs\\src\\main\\dbc"...
0x140035cc7  mov     [rsp+0C0h+pbCancel], rcx
0x140035ccc  lea     r9d, [r15-5Bh]
0x140035cd0  xor     r8d, r8d
0x140035cd3  mov     edx, eax
0x140035cd5  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140035cda  mov     rbx, rax
  ... truncated ...
```
