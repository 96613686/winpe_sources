# DeleteAllFilesInDirectory

- ea: `0x18003a030`
- end: `0x18003a2db`
- name: `DeleteAllFilesInDirectory`
- size: `683`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180039f14`

## callees

- `0x18000bb60`
- `0x18001fb10`
- `0x18003a030`
- `0x18003ea2c`
- `0x180046650`
- `0x180047330`
- `0x1800ccbd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a142`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a1e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a142`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a1e3`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18003a114`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18003a114`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003a121`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003a121`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003a2a1`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003a2a1`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003a0ac`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003a0ac`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003a2b2`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003a2b2`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18003a1d5`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18003a1d5`

## string_xrefs

- `0x18003a1fc`: `DeleteAllFilesInDirectory`
- `0x18003a1f3`: `MoveFileEx %ws failed with error code %d`

## pseudocode

```c
__int64 __fastcall DeleteAllFilesInDirectory(__int64 a1, int a2)
{
  unsigned int v5; // ebx
  HANDLE FirstFileW; // rdi
  BOOL v7; // ebx
  DWORD LastError; // eax
  struct SplLogType *v9; // rax
  __int64 v10; // rbx
  struct SplLogType *v11; // rax
  WCHAR *cFileName; // [rsp+20h] [rbp-E0h]
  __int64 v13; // [rsp+28h] [rbp-D8h]
  const wchar_t *v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h]
  int v16; // [rsp+50h] [rbp-B0h]
  int v17; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v18; // [rsp+60h] [rbp-A0h]
  int v19; // [rsp+68h] [rbp-98h]
  int v20; // [rsp+70h] [rbp-90h] BYREF
  __int64 v21; // [rsp+78h] [rbp-88h]
  int v22; // [rsp+80h] [rbp-80h]
  const wchar_t *v23; // [rsp+88h] [rbp-78h] BYREF
  __int64 v24; // [rsp+90h] [rbp-70h]
  int v25; // [rsp+98h] [rbp-68h]
  _BYTE v26[32]; // [rsp+A0h] [rbp-60h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR FileName[264]; // [rsp+310h] [rbp+210h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( (unsigned int)StrNCatBuff(FileName, 260, a1, L"\\*") )
    return 0;
  v5 = 0;
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
  {
    do
    {
      if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      {
        v13 = 0;
        cFileName = FindFileData.cFileName;
        if ( !(unsigned int)StrNCatBuff(FileName, 260, a1, L"\\") )
        {
          if ( (FindFileData.dwFileAttributes & 1) != 0 )
            SetFileAttributesW(FileName, FindFileData.dwFileAttributes & 0xFFFFFFFE);
          v7 = DeleteFileW(FileName);
          if ( !v7 )
          {
            LODWORD(v14) = 104;
            v15 = 4;
            v16 = 0;
            LastError = GetLastError();
            v18 = 4;
            v17 = LastError;
            v19 = 0;
            v23 = L"-";
            v20 = 0;
            v21 = 4;
            v22 = 0;
            v24 = 4;
            v25 = 1;
            v9 = SplLogType::SplLogType((SplLogType *)v26, FileName);
            SplLogEvent2(&SPOOLER_DELETE_FILE_FAILED, v9, &v23, &v20, &v17, &v14, 0);
          }
          if ( (a2 || !v7) && !MoveFileExW(FileName, 0, 4u) )
          {
            v10 = GetLastError();
            LocalSpoolerTelemetry::WriteDbgTraceError(
              "DeleteAllFilesInDirectory",
              L"MoveFileEx %ws failed with error code %d",
              FileName,
              v10,
              cFileName,
              v13);
            LODWORD(v23) = 103;
            v14 = L"-";
            v24 = 4;
            v25 = 0;
            v20 = v10;
            v21 = 4;
            v22 = 0;
            v17 = 4;
            v18 = 4;
            v19 = 0;
            v15 = 4;
            v16 = 1;
            v11 = SplLogType::SplLogType((SplLogType *)v26, FileName);
            SplLogEvent2(&SPOOLER_MOVE_FILE_FAILED, v11, &v14, &v17, &v20, &v23, 0);
          }
        }
      }
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
    return FindClose(FirstFileW);
  }
  return v5;
}

```

## disassembly

```asm
0x18003a030  push    rbp
0x18003a032  push    rbx
0x18003a033  push    rsi
0x18003a034  push    rdi
0x18003a035  push    r12
0x18003a037  push    r14
0x18003a039  lea     rbp, [rsp-438h]
0x18003a041  sub     rsp, 538h
0x18003a048  mov     rax, cs:__security_cookie
0x18003a04f  xor     rax, rsp
0x18003a052  mov     [rbp+460h+var_40], rax
0x18003a059  mov     r14d, edx
0x18003a05c  mov     rsi, rcx
0x18003a05f  xor     edx, edx; Val
0x18003a061  lea     rcx, [rbp+460h+FindFileData]; void *
0x18003a065  mov     r8d, 250h; Size
0x18003a06b  call    memset_0
0x18003a070  lea     r9, asc_1800FF25C; "\\*"
0x18003a077  mov     [rsp+560h+var_540], 0
0x18003a080  mov     r8, rsi
0x18003a083  lea     rcx, [rbp+460h+FileName]
0x18003a08a  mov     edx, 104h
0x18003a08f  call    StrNCatBuff
0x18003a094  test    eax, eax
0x18003a096  jz      short loc_18003A09F
0x18003a098  xor     eax, eax
0x18003a09a  jmp     loc_18003A2BC
0x18003a09f  lea     rdx, [rbp+460h+FindFileData]; lpFindFileData
0x18003a0a3  xor     ebx, ebx
0x18003a0a5  lea     rcx, [rbp+460h+FileName]; lpFileName
0x18003a0ac  call    cs:__imp_FindFirstFileW
0x18003a0b2  mov     rdi, rax
0x18003a0b5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003a0b9  jz      loc_18003A2BA
0x18003a0bf  lea     r12d, [rbx+4]
0x18003a0c3  test    byte ptr [rbp+460h+FindFileData.dwFileAttributes], 10h
0x18003a0c7  jnz     loc_18003A29A
0x18003a0cd  lea     rax, [rbp+460h+FindFileData.cFileName]
0x18003a0d1  mov     [rsp+560h+var_538], 0
0x18003a0da  lea     r9, SubBlock; "\\"
0x18003a0e1  mov     [rsp+560h+var_540], rax
0x18003a0e6  mov     r8, rsi
0x18003a0e9  lea     rcx, [rbp+460h+FileName]
0x18003a0f0  mov     edx, 104h
0x18003a0f5  call    StrNCatBuff
0x18003a0fa  test    eax, eax
0x18003a0fc  jnz     loc_18003A29A
0x18003a102  mov     edx, [rbp+460h+FindFileData.dwFileAttributes]
0x18003a105  test    dl, 1
0x18003a108  jz      short loc_18003A11A
0x18003a10a  and     edx, 0FFFFFFFEh; dwFileAttributes
0x18003a10d  lea     rcx, [rbp+460h+FileName]; lpFileName
0x18003a114  call    cs:__imp_SetFileAttributesW
0x18003a11a  lea     rcx, [rbp+460h+FileName]; lpFileName
0x18003a121  call    cs:__imp_DeleteFileW
0x18003a127  mov     ebx, eax
0x18003a129  test    eax, eax
0x18003a12b  jnz     loc_18003A1BC
0x18003a131  mov     dword ptr [rsp+560h+var_520], 68h ; 'h'
0x18003a139  mov     [rsp+560h+var_518], r12
0x18003a13e  mov     [rsp+560h+var_510], eax
0x18003a142  call    cs:__imp_GetLastError
0x18003a148  lea     rdx, [rbp+460h+FileName]; unsigned __int16 *
0x18003a14f  mov     [rsp+560h+var_500], r12
0x18003a154  mov     [rsp+560h+var_508], eax
0x18003a158  lea     rcx, [rbp+460h+var_4C0]; this
0x18003a15c  lea     rax, asc_1800ECF90; "-"
0x18003a163  mov     [rsp+560h+var_4F8], ebx
0x18003a167  mov     [rbp+460h+var_4D8], rax
0x18003a16b  mov     [rsp+560h+var_4F0], ebx
0x18003a16f  mov     [rsp+560h+var_4E8], r12
0x18003a174  mov     [rbp+460h+var_4E0], ebx
0x18003a177  mov     [rbp+460h+var_4D0], r12
0x18003a17b  mov     [rbp+460h+var_4C8], 1
0x18003a182  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x18003a187  lea     rcx, [rsp+560h+var_520]
0x18003a18c  mov     [rsp+560h+var_530], 0
0x18003a195  mov     [rsp+560h+var_538], rcx
0x18003a19a  lea     r9, [rsp+560h+var_4F0]
0x18003a19f  lea     rcx, [rsp+560h+var_508]
0x18003a1a4  mov     rdx, rax; struct SplLogType *
0x18003a1a7  mov     [rsp+560h+var_540], rcx
0x18003a1ac  lea     r8, [rbp+460h+var_4D8]
0x18003a1b0  lea     rcx, SPOOLER_DELETE_FILE_FAILED; struct _EVENT_DESCRIPTOR *
0x18003a1b7  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x18003a1bc  test    r14d, r14d
0x18003a1bf  jnz     short loc_18003A1C9
0x18003a1c1  test    ebx, ebx
0x18003a1c3  jnz     loc_18003A29A
0x18003a1c9  mov     r8d, r12d; dwFlags
0x18003a1cc  lea     rcx, [rbp+460h+FileName]; lpExistingFileName
0x18003a1d3  xor     edx, edx; lpNewFileName
0x18003a1d5  call    cs:__imp_MoveFileExW
0x18003a1db  test    eax, eax
0x18003a1dd  jnz     loc_18003A29A
0x18003a1e3  call    cs:__imp_GetLastError
0x18003a1e9  mov     r9d, eax
0x18003a1ec  lea     r8, [rbp+460h+FileName]
0x18003a1f3  lea     rdx, aMovefileexWsFa; "MoveFileEx %ws failed with error code %"...
0x18003a1fa  mov     ebx, eax
0x18003a1fc  lea     rcx, aDeleteallfiles; "DeleteAllFilesInDirectory"
0x18003a203  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18003a208  lea     rax, asc_1800ECF90; "-"
0x18003a20f  mov     dword ptr [rbp+460h+var_4D8], 67h ; 'g'
0x18003a216  lea     rdx, [rbp+460h+FileName]; unsigned __int16 *
0x18003a21d  mov     [rsp+560h+var_520], rax
0x18003a222  lea     rcx, [rbp+460h+var_4C0]; this
0x18003a226  mov     [rbp+460h+var_4D0], r12
0x18003a22a  mov     [rbp+460h+var_4C8], 0
0x18003a231  mov     [rsp+560h+var_4F0], ebx
0x18003a235  mov     [rsp+560h+var_4E8], r12
0x18003a23a  mov     [rbp+460h+var_4E0], 0
0x18003a241  mov     [rsp+560h+var_508], r12d
0x18003a246  mov     [rsp+560h+var_500], r12
0x18003a24b  mov     [rsp+560h+var_4F8], 0
0x18003a253  mov     [rsp+560h+var_518], r12
0x18003a258  mov     [rsp+560h+var_510], 1
0x18003a260  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x18003a265  lea     rcx, [rbp+460h+var_4D8]
0x18003a269  mov     [rsp+560h+var_530], 0
0x18003a272  mov     [rsp+560h+var_538], rcx
0x18003a277  lea     r9, [rsp+560h+var_508]
0x18003a27c  lea     rcx, [rsp+560h+var_4F0]
0x18003a281  mov     rdx, rax; struct SplLogType *
0x18003a284  mov     [rsp+560h+var_540], rcx
0x18003a289  lea     r8, [rsp+560h+var_520]
0x18003a28e  lea     rcx, SPOOLER_MOVE_FILE_FAILED; struct _EVENT_DESCRIPTOR *
0x18003a295  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x18003a29a  lea     rdx, [rbp+460h+FindFileData]; lpFindFileData
0x18003a29e  mov     rcx, rdi; hFindFile
0x18003a2a1  call    cs:__imp_FindNextFileW
0x18003a2a7  test    eax, eax
0x18003a2a9  jnz     loc_18003A0C3
0x18003a2af  mov     rcx, rdi; hFindFile
0x18003a2b2  call    cs:__imp_FindClose
0x18003a2b8  mov     ebx, eax
0x18003a2ba  mov     eax, ebx
0x18003a2bc  mov     rcx, [rbp+460h+var_40]
0x18003a2c3  xor     rcx, rsp; StackCookie
0x18003a2c6  call    __security_check_cookie
0x18003a2cb  add     rsp, 538h
0x18003a2d2  pop     r14
0x18003a2d4  pop     r12
0x18003a2d6  pop     rdi
0x18003a2d7  pop     rsi
0x18003a2d8  pop     rbx
0x18003a2d9  pop     rbp
0x18003a2da  retn
```
