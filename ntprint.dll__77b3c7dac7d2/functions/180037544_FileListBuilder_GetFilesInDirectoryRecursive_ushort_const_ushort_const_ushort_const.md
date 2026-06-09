# FileListBuilder::GetFilesInDirectoryRecursive(ushort const *,ushort const *,ushort const *)

- ea: `0x180037544`
- end: `0x180037ac1`
- name: `?GetFilesInDirectoryRecursive@FileListBuilder@@AEAAJPEBG00@Z`
- size: `1405`
- prototype: `__int64 __fastcall(FileListBuilder *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x180037320`
- `0x180037544`

## callees

- `0x180002300`
- `0x1800026f0`
- `0x180002f48`
- `0x1800078f0`
- `0x180007944`
- `0x18000d290`
- `0x180036a0c`
- `0x180036dec`
- `0x180036e1c`
- `0x180037544`
- `0x180037f94`
- `0x18003806c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003797c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180037996`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003797c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180037996`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180037871`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180037a97`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180037871`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180037a97`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003785b`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180037a67`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003785b`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180037a67`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18003767e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18003794c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18003767e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18003794c`

## string_xrefs

- `0x180037824`: `FileListBuilder::GetFilesInDirectoryRecursive`
- `0x180037843`: `FileListBuilder::GetFilesInDirectoryRecursive`
- `0x180037a2f`: `FileListBuilder::GetFilesInDirectoryRecursive`
- `0x180037a4a`: `FileListBuilder::GetFilesInDirectoryRecursive`
- `0x180037a83`: `FileListBuilder::GetFilesInDirectoryRecursive`
- `0x18003783c`: `Failed to build new path for file (%ws)`
- `0x180037816`: `Failed to a create new FileEntry for %ws!`
- `0x180037a28`: `GetFilesInDirectoryRecursive failed! hr: 0x%x`
- `0x180037a7c`: `Failed to build new path for sub directory (%ws)`

## pseudocode

```c
__int64 __fastcall FileListBuilder::GetFilesInDirectoryRecursive(
        FileListBuilder *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  unsigned __int16 *v6; // r13
  int v7; // ebx
  HANDLE FirstFile; // r14
  FileListBuilder *v9; // r13
  FileEntry *v10; // rax
  FileEntry *v11; // rdi
  unsigned int v12; // edx
  HANDLE v13; // rdi
  int FilesInDirectoryRecursive; // eax
  unsigned __int64 v16; // [rsp+30h] [rbp-D0h] BYREF
  FileListBuilder *v17; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v18; // [rsp+40h] [rbp-C0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v20[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR FileName[264]; // [rsp+4B0h] [rbp+3B0h] BYREF

  v17 = this;
  v18 = a4;
  v6 = a4;
  memset_0(FileName, 0, 0x208u);
  v7 = StringCchCopyW(FileName, 0x104u, a2);
  if ( v7 < 0 )
    return (unsigned int)v7;
  v16 = 0;
  v7 = StringCchLengthW(FileName, 0x104u, &v16);
  if ( v7 < 0 )
    return (unsigned int)v7;
  if ( v20[v16 + 263] != 92 )
  {
    v7 = StringCchCatW(FileName, 0x104u, L"\\");
    if ( v7 < 0 )
      return (unsigned int)v7;
  }
  v7 = StringCchCatW(FileName, 0x104u, a3);
  if ( v7 < 0 )
    return (unsigned int)v7;
  v7 = StringCchCatW(FileName, 0x104u, v6);
  if ( v7 < 0 )
    return (unsigned int)v7;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFile = FindFirstFileExW(FileName, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 0);
  if ( FirstFile == (HANDLE)-1LL )
  {
    SplLibTelemetry::WriteDbgTraceInfo(
      "FileListBuilder::GetFilesInDirectoryRecursive",
      L"No files for filter (%ws) found for %ws.",
      v6,
      a2);
    goto LABEL_28;
  }
  v9 = v17;
  while ( 1 )
  {
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
      goto LABEL_26;
    memset_0(v20, 0, 0x208u);
    v7 = StringCchCopyW(v20, 0x104u, a2);
    if ( v7 < 0 )
      break;
    v16 = 0;
    v7 = StringCchLengthW(v20, 0x104u, &v16);
    if ( v7 < 0 )
      break;
    if ( FindFileData.cAlternateFileName[v16 + 13] != 92 )
    {
      v7 = StringCchCatW(v20, 0x104u, L"\\");
      if ( v7 < 0 )
        break;
    }
    v7 = StringCchCatW(v20, 0x104u, a3);
    if ( v7 < 0 )
      break;
    v16 = 0;
    v7 = StringCchLengthW(v20, 0x104u, &v16);
    if ( v7 < 0 )
      break;
    if ( FindFileData.cAlternateFileName[v16 + 13] != 92 )
    {
      v7 = StringCchCatW(v20, 0x104u, L"\\");
      if ( v7 < 0 )
        break;
    }
    v7 = StringCchCatW(v20, 0x104u, FindFileData.cFileName);
    if ( v7 < 0 )
      break;
    v10 = (FileEntry *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
    v11 = v10;
    if ( !v10 )
    {
      SplLibTelemetry::WriteDbgTraceError(
        "FileListBuilder::GetFilesInDirectoryRecursive",
        L"Failed to a create new FileEntry for %ws!",
        v20);
      goto LABEL_23;
    }
    *(_DWORD *)v10 = 1735554163;
    *((_QWORD *)v10 + 1) = &TString::gszNullState;
    TString::bUpdate(v10, v20);
    if ( !(unsigned int)TDoubleList<FileEntry *,unsigned long>::AppendItem(v9, v11) )
    {
      FileEntry::`scalar deleting destructor'(v11, v12);
      SplLibTelemetry::WriteDbgTraceError(
        "FileListBuilder::GetFilesInDirectoryRecursive",
        L"Failed to append FileEntry to list for %ws!",
        v20);
LABEL_23:
      v7 = -2147024882;
      goto LABEL_27;
    }
LABEL_26:
    if ( !FindNextFileW(FirstFile, &FindFileData) )
      goto LABEL_27;
  }
  SplLibTelemetry::WriteDbgTraceError(
    "FileListBuilder::GetFilesInDirectoryRecursive",
    L"Failed to build new path for file (%ws)",
    FindFileData.cFileName);
LABEL_27:
  FindClose(FirstFile);
  v6 = v18;
  if ( v7 < 0 )
    return (unsigned int)v7;
LABEL_28:
  v7 = StringCchCopyW(FileName, 0x104u, a2);
  if ( v7 >= 0 )
  {
    v16 = 0;
    v7 = StringCchLengthW(FileName, 0x104u, &v16);
    if ( v7 >= 0 )
    {
      if ( v20[v16 + 263] == 92 || (v7 = StringCchCatW(FileName, 0x104u, L"\\"), v7 >= 0) )
      {
        v7 = StringCchCatW(FileName, 0x104u, a3);
        if ( v7 >= 0 )
          v7 = StringCchCatW(FileName, 0x104u, L"*");
      }
    }
  }
  v13 = FindFirstFileExW(FileName, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 0);
  if ( v13 == (HANDLE)-1LL )
    return (unsigned int)v7;
  while ( 2 )
  {
    if ( (FindFileData.dwFileAttributes & 0x10) == 0
      || !(unsigned int)_o__wcsicmp(FindFileData.cFileName, L".")
      || !(unsigned int)_o__wcsicmp(FindFileData.cFileName, L"..") )
    {
      if ( v7 < 0 )
        goto LABEL_48;
LABEL_45:
      if ( !FindNextFileW(v13, &FindFileData) )
        goto LABEL_48;
      continue;
    }
    break;
  }
  memset_0(v20, 0, 0x208u);
  if ( (int)StringCchCopyW(v20, 0x104u, a3) >= 0
    && StringCchCatW(v20, 0x104u, FindFileData.cFileName) >= 0
    && StringCchCatW(v20, 0x104u, L"\\") >= 0 )
  {
    FilesInDirectoryRecursive = FileListBuilder::GetFilesInDirectoryRecursive(v17, a2, v20, v6);
    v7 = FilesInDirectoryRecursive;
    if ( FilesInDirectoryRecursive < 0 )
    {
      SplLibTelemetry::WriteDbgTraceError(
        "FileListBuilder::GetFilesInDirectoryRecursive",
        L"GetFilesInDirectoryRecursive failed! hr: 0x%x",
        (unsigned int)FilesInDirectoryRecursive);
      goto LABEL_48;
    }
    goto LABEL_45;
  }
  SplLibTelemetry::WriteDbgTraceError(
    "FileListBuilder::GetFilesInDirectoryRecursive",
    L"Failed to build new path for sub directory (%ws)",
    FindFileData.cFileName);
  v7 = -2147467259;
LABEL_48:
  FindClose(v13);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180037544  push    rbp
0x180037546  push    rbx
0x180037547  push    rdi
0x180037548  push    r12
0x18003754a  push    r13
0x18003754c  push    r14
0x18003754e  push    r15
0x180037550  lea     rbp, [rsp-5D0h]
0x180037558  sub     rsp, 6D0h
0x18003755f  mov     rax, cs:__security_cookie
0x180037566  xor     rax, rsp
0x180037569  mov     [rbp+600h+var_40], rax
0x180037570  mov     r12, r8
0x180037573  mov     [rsp+700h+var_6C8], rcx
0x180037578  mov     r15, rdx
0x18003757b  mov     [rsp+700h+var_6C0], r9
0x180037580  xor     edx, edx; Val
0x180037582  lea     rcx, [rbp+600h+FileName]; void *
0x180037589  mov     r8d, 208h; Size
0x18003758f  mov     r13, r9
0x180037592  call    memset_0
0x180037597  mov     edi, 104h
0x18003759c  lea     rcx, [rbp+600h+FileName]; unsigned __int16 *
0x1800375a3  mov     edx, edi; unsigned __int64
0x1800375a5  mov     r8, r15; unsigned __int16 *
0x1800375a8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800375ad  mov     ebx, eax
0x1800375af  test    eax, eax
0x1800375b1  js      loc_180037A9D
0x1800375b7  lea     r8, [rsp+700h+var_6D0]; unsigned __int64 *
0x1800375bc  mov     [rsp+700h+var_6D0], 0
0x1800375c5  mov     edx, edi; unsigned __int64
0x1800375c7  lea     rcx, [rbp+600h+FileName]; unsigned __int16 *
0x1800375ce  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800375d3  mov     ebx, eax
0x1800375d5  test    eax, eax
0x1800375d7  js      loc_180037A9D
0x1800375dd  mov     rax, [rsp+700h+var_6D0]
0x1800375e2  mov     ecx, 5Ch ; '\'
0x1800375e7  cmp     cx, [rbp+rax*2+600h+var_252]
0x1800375ef  jz      short loc_180037610
0x1800375f1  lea     r8, SubBlock; "\\"
0x1800375f8  mov     edx, edi; unsigned __int64
0x1800375fa  lea     rcx, [rbp+600h+FileName]; unsigned __int16 *
0x180037601  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180037606  mov     ebx, eax
0x180037608  test    eax, eax
0x18003760a  js      loc_180037A9D
0x180037610  mov     r8, r12; unsigned __int16 *
0x180037613  lea     rcx, [rbp+600h+FileName]; unsigned __int16 *
0x18003761a  mov     rdx, rdi; unsigned __int64
0x18003761d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180037622  mov     ebx, eax
0x180037624  test    eax, eax
0x180037626  js      loc_180037A9D
0x18003762c  mov     r8, r13; unsigned __int16 *
0x18003762f  lea     rcx, [rbp+600h+FileName]; unsigned __int16 *
0x180037636  mov     rdx, rdi; unsigned __int64
0x180037639  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003763e  mov     ebx, eax
0x180037640  test    eax, eax
0x180037642  js      loc_180037A9D
0x180037648  xor     edx, edx; Val
0x18003764a  lea     rcx, [rsp+700h+FindFileData]; void *
0x18003764f  mov     r8d, 250h; Size
0x180037655  call    memset_0
0x18003765a  xor     r9d, r9d; fSearchOp
0x18003765d  mov     [rsp+700h+dwAdditionalFlags], 0; dwAdditionalFlags
0x180037665  lea     r8, [rsp+700h+FindFileData]; lpFindFileData
0x18003766a  mov     [rsp+700h+lpSearchFilter], 0; lpSearchFilter
0x180037673  lea     rcx, [rbp+600h+FileName]; lpFileName
0x18003767a  lea     edx, [r9+1]; fInfoLevelId
0x18003767e  call    cs:__imp_FindFirstFileExW
0x180037684  mov     r14, rax
0x180037687  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003768b  jz      loc_180037A3D
0x180037691  mov     r13, [rsp+700h+var_6C8]
0x180037696  test    [rsp+700h+FindFileData], 10h
0x18003769b  jnz     loc_180037853
0x1800376a1  xor     edx, edx; Val
0x1800376a3  lea     rcx, [rbp+600h+var_460]; void *
0x1800376aa  mov     r8d, 208h; Size
0x1800376b0  call    memset_0
0x1800376b5  mov     r8, r15; unsigned __int16 *
0x1800376b8  lea     rcx, [rbp+600h+var_460]; unsigned __int16 *
0x1800376bf  mov     rdx, rdi; unsigned __int64
0x1800376c2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800376c7  mov     ebx, eax
0x1800376c9  test    eax, eax
0x1800376cb  js      loc_180037837
0x1800376d1  lea     r8, [rsp+700h+var_6D0]; unsigned __int64 *
0x1800376d6  mov     [rsp+700h+var_6D0], 0
0x1800376df  mov     rdx, rdi; unsigned __int64
0x1800376e2  lea     rcx, [rbp+600h+var_460]; unsigned __int16 *
0x1800376e9  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800376ee  mov     ebx, eax
0x1800376f0  test    eax, eax
0x1800376f2  js      loc_180037837
0x1800376f8  mov     rax, [rsp+700h+var_6D0]
0x1800376fd  mov     ecx, 5Ch ; '\'
0x180037702  cmp     cx, [rbp+rax*2+600h+var_462]
0x18003770a  jz      short loc_18003772C
0x18003770c  lea     r8, SubBlock; "\\"
0x180037713  mov     rdx, rdi; unsigned __int64
0x180037716  lea     rcx, [rbp+600h+var_460]; unsigned __int16 *
0x18003771d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180037722  mov     ebx, eax
0x180037724  test    eax, eax
0x180037726  js      loc_180037837
0x18003772c  mov     r8, r12; unsigned __int16 *
0x18003772f  lea     rcx, [rbp+600h+var_460]; unsigned __int16 *
0x180037736  mov     rdx, rdi; unsigned __int64
0x180037739  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003773e  mov     ebx, eax
0x180037740  test    eax, eax
0x180037742  js      loc_180037837
0x180037748  lea     r8, [rsp+700h+var_6D0]; unsigned __int64 *
0x18003774d  mov     [rsp+700h+var_6D0], 0
0x180037756  mov     rdx, rdi; unsigned __int64
0x180037759  lea     rcx, [rbp+600h+var_460]; unsigned __int16 *
0x180037760  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180037765  mov     ebx, eax
0x180037767  test    eax, eax
0x180037769  js      loc_180037837
0x18003776f  mov     rax, [rsp+700h+var_6D0]
0x180037774  mov     ecx, 5Ch ; '\'
0x180037779  cmp     cx, [rbp+rax*2+600h+var_462]
0x180037781  jz      short loc_1800377A3
0x180037783  lea     r8, SubBlock; "\\"
0x18003778a  mov     rdx, rdi; unsigned __int64
0x18003778d  lea     rcx, [rbp+600h+var_460]; unsigned __int16 *
0x180037794  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180037799  mov     ebx, eax
0x18003779b  test    eax, eax
0x18003779d  js      loc_180037837
0x1800377a3  lea     r8, [rsp+700h+var_684]; unsigned __int16 *
0x1800377a8  mov     rdx, rdi; unsigned __int64
0x1800377ab  lea     rcx, [rbp+600h+var_460]; unsigned __int16 *
0x1800377b2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800377b7  mov     ebx, eax
0x1800377b9  test    eax, eax
0x1800377bb  js      short loc_180037837
0x1800377bd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800377c4  mov     ecx, 10h; unsigned __int64
0x1800377c9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800377ce  mov     rdi, rax
0x1800377d1  test    rax, rax
0x1800377d4  jz      short loc_180037816
0x1800377d6  mov     dword ptr [rax], 67727473h
0x1800377dc  lea     rdx, [rbp+600h+var_460]; unsigned __int16 *
0x1800377e3  lea     rax, ?gszNullState@TString@@0PAGA; ushort near * TString::gszNullState
0x1800377ea  mov     rcx, rdi; this
0x1800377ed  mov     [rdi+8], rax
0x1800377f1  call    ?bUpdate@TString@@QEAAHPEBG@Z; TString::bUpdate(ushort const *)
0x1800377f6  mov     rdx, rdi
0x1800377f9  mov     rcx, r13
0x1800377fc  call    ?AppendItem@?$TDoubleList@PEAVFileEntry@@K@@QEAAHPEAVFileEntry@@@Z; TDoubleList<FileEntry *,ulong>::AppendItem(FileEntry *)
0x180037801  test    eax, eax
0x180037803  jnz     short loc_180037853
0x180037805  mov     rcx, rdi; this
0x180037808  call    ??_GFileEntry@@QEAAPEAXI@Z; FileEntry::`scalar deleting destructor'(uint)
0x18003780d  lea     rdx, aFailedToAppend; "Failed to append FileEntry to list for "...
0x180037814  jmp     short loc_18003781D
0x180037816  lea     rdx, aFailedToACreat; "Failed to a create new FileEntry for %w"...
0x18003781d  lea     r8, [rbp+600h+var_460]
0x180037824  lea     rcx, aFilelistbuilde_0; "FileListBuilder::GetFilesInDirectoryRec"...
0x18003782b  call    ?WriteDbgTraceError@SplLibTelemetry@@SAXPEADPEAGZZ; SplLibTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180037830  mov     ebx, 8007000Eh
0x180037835  jmp     short loc_18003784F
0x180037837  lea     r8, [rsp+700h+var_684]
0x18003783c  lea     rdx, aFailedToBuildN; "Failed to build new path for file (%ws)"
0x180037843  lea     rcx, aFilelistbuilde_0; "FileListBuilder::GetFilesInDirectoryRec"...
0x18003784a  call    ?WriteDbgTraceError@SplLibTelemetry@@SAXPEADPEAGZZ; SplLibTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18003784f  test    ebx, ebx
0x180037851  js      short loc_18003786E
0x180037853  lea     rdx, [rsp+700h+FindFileData]; lpFindFileData
0x180037858  mov     rcx, r14; hFindFile
0x18003785b  call    cs:__imp_FindNextFileW
0x180037861  mov     edi, 104h
0x180037866  test    eax, eax
0x180037868  jnz     loc_180037696
0x18003786e  mov     rcx, r14; hFindFile
0x180037871  call    cs:__imp_FindClose
0x180037877  mov     r13, [rsp+700h+var_6C0]
0x18003787c  test    ebx, ebx
0x18003787e  js      loc_180037A9D
0x180037884  mov     edi, 104h
0x180037889  mov     r8, r15; unsigned __int16 *
0x18003788c  lea     rcx, [rbp+600h+FileName]; unsigned __int16 *
0x180037893  mov     rdx, rdi; unsigned __int64
0x180037896  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003789b  mov     ebx, eax
0x18003789d  test    eax, eax
0x18003789f  js      loc_180037928
0x1800378a5  lea     r8, [rsp+700h+var_6D0]; unsigned __int64 *
0x1800378aa  mov     [rsp+700h+var_6D0], 0
0x1800378b3  mov     rdx, rdi; unsigned __int64
0x1800378b6  lea     rcx, [rbp+600h+FileName]; unsigned __int16 *
0x1800378bd  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800378c2  mov     ebx, eax
0x1800378c4  test    eax, eax
0x1800378c6  js      short loc_180037928
0x1800378c8  mov     rax, [rsp+700h+var_6D0]
0x1800378cd  mov     ecx, 5Ch ; '\'
0x1800378d2  cmp     cx, [rbp+rax*2+600h+var_252]
0x1800378da  jz      short loc_1800378F8
0x1800378dc  lea     r8, SubBlock; "\\"
0x1800378e3  mov     rdx, rdi; unsigned __int64
0x1800378e6  lea     rcx, [rbp+600h+FileName]; unsigned __int16 *
0x1800378ed  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800378f2  mov     ebx, eax
0x1800378f4  test    eax, eax
0x1800378f6  js      short loc_180037928
0x1800378f8  mov     r8, r12; unsigned __int16 *
0x1800378fb  lea     rcx, [rbp+600h+FileName]; unsigned __int16 *
0x180037902  mov     rdx, rdi; unsigned __int64
0x180037905  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003790a  mov     ebx, eax
0x18003790c  test    eax, eax
0x18003790e  js      short loc_180037928
0x180037910  lea     r8, asc_180047644; "*"
0x180037917  mov     rdx, rdi; unsigned __int64
0x18003791a  lea     rcx, [rbp+600h+FileName]; unsigned __int16 *
0x180037921  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180037926  mov     ebx, eax
0x180037928  xor     r9d, r9d; fSearchOp
0x18003792b  mov     [rsp+700h+dwAdditionalFlags], 0; dwAdditionalFlags
0x180037933  lea     r8, [rsp+700h+FindFileData]; lpFindFileData
0x180037938  mov     [rsp+700h+lpSearchFilter], 0; lpSearchFilter
0x180037941  lea     rcx, [rbp+600h+FileName]; lpFileName
0x180037948  lea     edx, [r9+1]; fInfoLevelId
0x18003794c  call    cs:__imp_FindFirstFileExW
0x180037952  mov     rdi, rax
0x180037955  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180037959  jz      loc_180037A9D
0x18003795f  mov     r14d, 104h
0x180037965  test    [rsp+700h+FindFileData], 10h
0x18003796a  jz      loc_180037A5B
0x180037970  lea     rdx, asc_18004D8A4; "."
0x180037977  lea     rcx, [rsp+700h+var_684]
0x18003797c  call    cs:__imp__o__wcsicmp
0x180037982  test    eax, eax
0x180037984  jz      loc_180037A5B
0x18003798a  lea     rdx, asc_18004D7DC; ".."
0x180037991  lea     rcx, [rsp+700h+var_684]
0x180037996  call    cs:__imp__o__wcsicmp
0x18003799c  test    eax, eax
0x18003799e  jz      loc_180037A5B
0x1800379a4  xor     edx, edx; Val
0x1800379a6  lea     rcx, [rbp+600h+var_460]; void *
0x1800379ad  mov     r8d, 208h; Size
0x1800379b3  call    memset_0
0x1800379b8  mov     r8, r12; unsigned __int16 *
0x1800379bb  lea     rcx, [rbp+600h+var_460]; unsigned __int16 *
0x1800379c2  mov     rdx, r14; unsigned __int64
0x1800379c5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800379ca  test    eax, eax
0x1800379cc  js      loc_180037A77
0x1800379d2  lea     r8, [rsp+700h+var_684]; unsigned __int16 *
0x1800379d7  mov     rdx, r14; unsigned __int64
0x1800379da  lea     rcx, [rbp+600h+var_460]; unsigned __int16 *
0x1800379e1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800379e6  test    eax, eax
0x1800379e8  js      loc_180037A77
0x1800379ee  lea     r8, SubBlock; "\\"
0x1800379f5  mov     rdx, r14; unsigned __int64
0x1800379f8  lea     rcx, [rbp+600h+var_460]; unsigned __int16 *
0x1800379ff  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180037a04  test    eax, eax
0x180037a06  js      short loc_180037A77
0x180037a08  mov     rcx, [rsp+700h+var_6C8]; this
0x180037a0d  lea     r8, [rbp+600h+var_460]; unsigned __int16 *
0x180037a14  mov     r9, r13; unsigned __int16 *
0x180037a17  mov     rdx, r15; unsigned __int16 *
0x180037a1a  call    ?GetFilesInDirectoryRecursive@FileListBuilder@@AEAAJPEBG00@Z; FileListBuilder::GetFilesInDirectoryRecursive(ushort const *,ushort const *,ushort const *)
0x180037a1f  mov     ebx, eax
0x180037a21  test    eax, eax
0x180037a23  jns     short loc_180037A5F
0x180037a25  mov     r8d, eax
0x180037a28  lea     rdx, aGetfilesindire_0; "GetFilesInDirectoryRecursive failed! hr"...
0x180037a2f  lea     rcx, aFilelistbuilde_0; "FileListBuilder::GetFilesInDirectoryRec"...
0x180037a36  call    ?WriteDbgTraceError@SplLibTelemetry@@SAXPEADPEAGZZ; SplLibTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180037a3b  jmp     short loc_180037A94
0x180037a3d  mov     r9, r15
0x180037a40  lea     rdx, aNoFilesForFilt; "No files for filter (%ws) found for %ws"...
0x180037a47  mov     r8, r13
0x180037a4a  lea     rcx, aFilelistbuilde_0; "FileListBuilder::GetFilesInDirectoryRec"...
0x180037a51  call    ?WriteDbgTraceInfo@SplLibTelemetry@@SAXPEADPEAGZZ; SplLibTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180037a56  jmp     loc_180037889
0x180037a5b  test    ebx, ebx
0x180037a5d  js      short loc_180037A94
0x180037a5f  lea     rdx, [rsp+700h+FindFileData]; lpFindFileData
0x180037a64  mov     rcx, rdi; hFindFile
0x180037a67  call    cs:__imp_FindNextFileW
0x180037a6d  test    eax, eax
0x180037a6f  jnz     loc_180037965
0x180037a75  jmp     short loc_180037A94
0x180037a77  lea     r8, [rsp+700h+var_684]
0x180037a7c  lea     rdx, aFailedToBuildN_0; "Failed to build new path for sub direct"...
0x180037a83  lea     rcx, aFilelistbuilde_0; "FileListBuilder::GetFilesInDirectoryRec"...
  ... truncated ...
```
