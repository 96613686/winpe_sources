# WicaPostInstallp_CreateSentinelFile(_ExeEntry *)

- ea: `0x1800ae378`
- end: `0x1800ae58e`
- name: `?WicaPostInstallp_CreateSentinelFile@@YAKPEAU_ExeEntry@@@Z`
- size: `534`
- prototype: `unsigned int __fastcall(struct _ExeEntry *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800ae6fc`

## callees

- `0x18000dc08`
- `0x180012920`
- `0x18001b320`
- `0x18007a9cf`
- `0x1800ae378`
- `0x1800f1f10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae408`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae457`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae4d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae408`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae457`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae4d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ae548`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ae548`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ae4ca`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ae4ca`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800ae44d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800ae44d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800ae3fe`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800ae3fe`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800ae43c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800ae43c`

## string_xrefs

- `0x1800ae41b`: `WicaPostInstallp_CreateSentinelFile`
- `0x1800ae50b`: `WicaPostInstallp_CreateSentinelFile`
- `0x1800ae55f`: `WicaPostInstallp_CreateSentinelFile`
- `0x1800ae528`: `Created sentinel file,%ls,%ls`
- `0x1800ae4df`: `CreateFile Failed [%d]`
- `0x1800ae4ff`: `Created sentinel file %ls.`
- `0x1800ae493`: `Failed to format sentinel file path.`
- `0x1800ae45d`: `CreateDirectory Failed [%d]`

## pseudocode

```c
__int64 __fastcall WicaPostInstallp_CreateSentinelFile(struct _ExeEntry *a1)
{
  unsigned int v2; // ebx
  __int64 v3; // rax
  DWORD LastError; // eax
  const char *v5; // r9
  int v6; // r8d
  const char *v7; // r9
  int v8; // r8d
  HANDLE FileW; // rbx
  WCHAR Dst[264]; // [rsp+40h] [rbp-458h] BYREF
  WCHAR FileName[264]; // [rsp+250h] [rbp-248h] BYREF

  v2 = 1359;
  memset_0(Dst, 0, 0x208u);
  memset_0(FileName, 0, 0x208u);
  if ( !a1 )
    goto LABEL_16;
  v3 = -1;
  do
    ++v3;
  while ( *((_WORD *)a1 + v3 + 3858) );
  if ( !v3 )
  {
LABEL_16:
    v7 = "NULL argument passed in.";
    v8 = 1191;
    goto LABEL_17;
  }
  if ( !ExpandEnvironmentStringsW(L"%APPDATA%\\Microsoft\\PostUpgrade", Dst, 0x104u) )
  {
    LastError = GetLastError();
    v5 = "ExpandEnvironmentStrings Failed [%d]";
    v6 = 1199;
    goto LABEL_7;
  }
  if ( !PathFileExistsW(Dst) && !CreateDirectoryW(Dst, 0) )
  {
    LastError = GetLastError();
    v5 = "CreateDirectory Failed [%d]";
    v6 = 1206;
    goto LABEL_7;
  }
  if ( StringCchPrintfW(FileName, 0x104u, L"%ls\\%ls.txt", Dst, (char *)a1 + 7716) < 0 )
  {
    v7 = "Failed to format sentinel file path.";
    v8 = 1216;
LABEL_17:
    AslLogCallPrintf(1, (unsigned int)"WicaPostInstallp_CreateSentinelFile", v8, (_DWORD)v7);
    return v2;
  }
  FileW = CreateFileW(FileName, 0, 0, 0, 2u, 0x80u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    AslLogCallPrintf(
      3,
      (unsigned int)"WicaPostInstallp_CreateSentinelFile",
      1228,
      (unsigned int)"Created sentinel file %ls.");
    PcaTracePrintf(
      "WicaPostUpgrade",
      0,
      0,
      "Created sentinel file,%ls,%ls",
      (const wchar_t *)a1 + 3078,
      (const wchar_t *)a1 + 3858);
    CloseHandle(FileW);
    return 0;
  }
  LastError = GetLastError();
  v5 = "CreateFile Failed [%d]";
  v6 = 1224;
LABEL_7:
  v2 = LastError;
  AslLogCallPrintf(1, (unsigned int)"WicaPostInstallp_CreateSentinelFile", v6, (_DWORD)v5);
  return v2;
}

```

## disassembly

```asm
0x1800ae378  push    rbx
0x1800ae37a  push    rbp
0x1800ae37b  push    rsi
0x1800ae37c  push    rdi
0x1800ae37d  sub     rsp, 478h
0x1800ae384  mov     rax, cs:__security_cookie
0x1800ae38b  xor     rax, rsp
0x1800ae38e  mov     [rsp+498h+var_38], rax
0x1800ae396  mov     rsi, rcx
0x1800ae399  mov     edi, 208h
0x1800ae39e  mov     r8d, edi; Size
0x1800ae3a1  lea     rcx, [rsp+498h+Dst]; void *
0x1800ae3a6  xor     edx, edx; Val
0x1800ae3a8  mov     ebx, 54Fh
0x1800ae3ad  call    memset_0
0x1800ae3b2  mov     r8d, edi; Size
0x1800ae3b5  lea     rcx, [rsp+498h+FileName]; void *
0x1800ae3bd  xor     edx, edx; Val
0x1800ae3bf  call    memset_0
0x1800ae3c4  xor     ebp, ebp
0x1800ae3c6  test    rsi, rsi
0x1800ae3c9  jz      loc_1800AE552
0x1800ae3cf  lea     rdi, [rsi+1E24h]
0x1800ae3d6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ae3da  inc     rax
0x1800ae3dd  cmp     [rdi+rax*2], bp
0x1800ae3e1  jnz     short loc_1800AE3DA
0x1800ae3e3  test    rax, rax
0x1800ae3e6  jz      loc_1800AE552
0x1800ae3ec  mov     r8d, 104h; nSize
0x1800ae3f2  lea     rdx, [rsp+498h+Dst]; lpDst
0x1800ae3f7  lea     rcx, aAppdataMicroso; "%APPDATA%\\Microsoft\\PostUpgrade"
0x1800ae3fe  call    cs:__imp_ExpandEnvironmentStringsW
0x1800ae404  test    eax, eax
0x1800ae406  jnz     short loc_1800AE437
0x1800ae408  call    cs:__imp_GetLastError
0x1800ae40e  lea     r9, aExpandenvironm_2; "ExpandEnvironmentStrings Failed [%d]"
0x1800ae415  mov     r8d, 4AFh
0x1800ae41b  lea     rdx, aWicapostinstal_7; "WicaPostInstallp_CreateSentinelFile"
0x1800ae422  mov     [rsp+498h+dwCreationDisposition], eax
0x1800ae426  mov     ecx, 1
0x1800ae42b  mov     ebx, eax
0x1800ae42d  call    AslLogCallPrintf
0x1800ae432  jmp     loc_1800AE570
0x1800ae437  lea     rcx, [rsp+498h+Dst]; pszPath
0x1800ae43c  call    cs:__imp_PathFileExistsW
0x1800ae442  test    eax, eax
0x1800ae444  jnz     short loc_1800AE46C
0x1800ae446  xor     edx, edx; lpSecurityAttributes
0x1800ae448  lea     rcx, [rsp+498h+Dst]; lpPathName
0x1800ae44d  call    cs:__imp_CreateDirectoryW
0x1800ae453  test    eax, eax
0x1800ae455  jnz     short loc_1800AE46C
0x1800ae457  call    cs:__imp_GetLastError
0x1800ae45d  lea     r9, aCreatedirector; "CreateDirectory Failed [%d]"
0x1800ae464  mov     r8d, 4B6h
0x1800ae46a  jmp     short loc_1800AE41B
0x1800ae46c  lea     r9, [rsp+498h+Dst]
0x1800ae471  mov     qword ptr [rsp+498h+dwCreationDisposition], rdi
0x1800ae476  lea     r8, aLsLsTxt; "%ls\\%ls.txt"
0x1800ae47d  mov     edx, 104h; unsigned __int64
0x1800ae482  lea     rcx, [rsp+498h+FileName]; unsigned __int16 *
0x1800ae48a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ae48f  test    eax, eax
0x1800ae491  jns     short loc_1800AE4A5
0x1800ae493  lea     r9, aFailedToFormat_0; "Failed to format sentinel file path."
0x1800ae49a  mov     r8d, 4C0h
0x1800ae4a0  jmp     loc_1800AE55F
0x1800ae4a5  mov     [rsp+498h+hTemplateFile], rbp; hTemplateFile
0x1800ae4aa  lea     rcx, [rsp+498h+FileName]; lpFileName
0x1800ae4b2  mov     [rsp+498h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800ae4ba  xor     r9d, r9d; lpSecurityAttributes
0x1800ae4bd  xor     r8d, r8d; dwShareMode
0x1800ae4c0  mov     [rsp+498h+dwCreationDisposition], 2; dwCreationDisposition
0x1800ae4c8  xor     edx, edx; dwDesiredAccess
0x1800ae4ca  call    cs:__imp_CreateFileW
0x1800ae4d0  mov     rbx, rax
0x1800ae4d3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ae4d7  jnz     short loc_1800AE4F1
0x1800ae4d9  call    cs:__imp_GetLastError
0x1800ae4df  lea     r9, aCreatefileFail; "CreateFile Failed [%d]"
0x1800ae4e6  mov     r8d, 4C8h
0x1800ae4ec  jmp     loc_1800AE41B
0x1800ae4f1  lea     rax, [rsp+498h+FileName]
0x1800ae4f9  mov     r8d, 4CCh
0x1800ae4ff  lea     r9, aCreatedSentine_0; "Created sentinel file %ls."
0x1800ae506  mov     qword ptr [rsp+498h+dwCreationDisposition], rax
0x1800ae50b  lea     rdx, aWicapostinstal_7; "WicaPostInstallp_CreateSentinelFile"
0x1800ae512  mov     ecx, 3
0x1800ae517  call    AslLogCallPrintf
0x1800ae51c  lea     rax, [rsi+180Ch]
0x1800ae523  mov     qword ptr [rsp+498h+dwFlagsAndAttributes], rdi
0x1800ae528  lea     r9, aCreatedSentine; "Created sentinel file,%ls,%ls"
0x1800ae52f  mov     qword ptr [rsp+498h+dwCreationDisposition], rax
0x1800ae534  xor     r8d, r8d; unsigned int
0x1800ae537  lea     rcx, aWicapostupgrad; "WicaPostUpgrade"
0x1800ae53e  xor     edx, edx; unsigned int
0x1800ae540  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x1800ae545  mov     rcx, rbx; hObject
0x1800ae548  call    cs:__imp_CloseHandle
0x1800ae54e  mov     ebx, ebp
0x1800ae550  jmp     short loc_1800AE570
0x1800ae552  lea     r9, aNullArgumentPa; "NULL argument passed in."
0x1800ae559  mov     r8d, 4A7h
0x1800ae55f  lea     rdx, aWicapostinstal_7; "WicaPostInstallp_CreateSentinelFile"
0x1800ae566  mov     ecx, 1
0x1800ae56b  call    AslLogCallPrintf
0x1800ae570  mov     eax, ebx
0x1800ae572  mov     rcx, [rsp+498h+var_38]
0x1800ae57a  xor     rcx, rsp; StackCookie
0x1800ae57d  call    __security_check_cookie
0x1800ae582  add     rsp, 478h
0x1800ae589  pop     rdi
0x1800ae58a  pop     rsi
0x1800ae58b  pop     rbp
0x1800ae58c  pop     rbx
0x1800ae58d  retn
```
