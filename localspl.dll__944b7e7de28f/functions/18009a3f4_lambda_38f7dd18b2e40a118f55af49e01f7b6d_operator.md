# _lambda_38f7dd18b2e40a118f55af49e01f7b6d_::operator()

- ea: `0x18009a3f4`
- end: `0x18009a73a`
- name: `_lambda_38f7dd18b2e40a118f55af49e01f7b6d_::operator()`
- size: `838`
- prototype: `DWORD __fastcall(__int64 **)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x18009a3b4`

## callees

- `0x18000a858`
- `0x18000bc0c`
- `0x18000c380`
- `0x180011f00`
- `0x18001fb10`
- `0x18003e5f8`
- `0x18003ea2c`
- `0x180046650`
- `0x180047330`
- `0x180073f78`
- `0x18009a3f4`
- `0x18009b118`
- `0x18009b8a4`
- `0x1800cc910`
- `0x1800ccbd8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18009a5fc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18009a5fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a610`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a637`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a64b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a610`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a637`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a64b`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18009a4a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18009a656`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18009a4a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18009a656`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009a6c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009a6c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18009a488`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18009a488`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18009a542`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18009a542`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18009a46f`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18009a46f`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryW` at `0x18009a49d`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryW` at `0x18009a6f1`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryW` at `0x18009a49d`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryW` at `0x18009a6f1`
- `SPOOLSS!RevertToPrinterSelf` at `0x18009a4b5`
- `SPOOLSS!RevertToPrinterSelf` at `0x18009a4b5`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18009a62d`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18009a62d`

## string_xrefs

- `0x18009a6d1`: `Failed to load the file copy module '%ws'.  Error %d`
- `0x18009a6db`: `SplLoadLibraryTheCopyFileModule::<lambda_38f7dd18b2e40a118f55af49e01f7b6d>::operator ()`

## pseudocode

```c
DWORD __fastcall lambda_38f7dd18b2e40a118f55af49e01f7b6d_::operator()(__int64 **a1)
{
  __int64 v2; // r14
  DWORD result; // eax
  UINT v4; // r12d
  int v5; // edx
  HANDLE v6; // r15
  __int64 v7; // r14
  DWORD LastError; // edi
  __int64 v9; // r12
  __int64 *v10; // rax
  __int64 v11; // r13
  unsigned int v12; // r8d
  HMODULE *v13; // rbx
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // r8d
  HMODULE *v17; // rbx
  DWORD v18; // eax
  const unsigned __int16 **v19; // rdx
  struct SplLogType *v20; // rax
  unsigned int v21; // [rsp+20h] [rbp-E0h]
  UINT v22; // [rsp+30h] [rbp-D0h]
  __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  int v24; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h]
  int v26; // [rsp+50h] [rbp-B0h]
  DWORD v27; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+68h] [rbp-98h]
  char v30[32]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR LibFileName[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v32[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v33[264]; // [rsp+4B0h] [rbp+3B0h] BYREF
  WCHAR PathName[264]; // [rsp+6C0h] [rbp+5C0h] BYREF
  WCHAR Buffer[264]; // [rsp+8D0h] [rbp+7D0h] BYREF
  char v36; // [rsp+AE0h] [rbp+9E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D48h] [rbp+C48h]

  v2 = *(_QWORD *)(*(_QWORD *)(**a1 + 64) + 280LL);
  v23 = v2;
  memset_0(Buffer, 0, 0x20Au);
  memset_0(PathName, 0, 0x20Au);
  result = GetCurrentDirectoryW(0x105u, Buffer);
  if ( result )
  {
    result = GetSystemDirectoryW(PathName, 0x105u);
    if ( result )
    {
      SetCurrentDirectoryW(PathName);
      v4 = SetErrorMode(0x8001u);
      v22 = v4;
      v6 = RevertToPrinterSelf();
      if ( v6 )
      {
        v7 = *(_QWORD *)(v2 + 48);
        LastError = 0;
        if ( v7 )
        {
          v9 = v23;
          do
          {
            if ( *a1[1] )
              break;
            v10 = *a1;
            v23 = 0;
            v11 = *v10;
            if ( (unsigned int)GetDriverDirectory((unsigned int)&v36, v5, v7, 0, v9) )
            {
              if ( MakeCanonicalPath((const unsigned __int16 *)*a1[2], LibFileName, v12)
                && (unsigned int)IsModuleFilePathAllowed(LibFileName) )
              {
                v13 = (HMODULE *)a1[1];
                *v13 = LoadLibraryW(LibFileName);
              }
              if ( !*a1[1] )
              {
                if ( (unsigned int)GetIniDriverAndDirForThisMachineEx(
                                     *(_QWORD *)(v11 + 64),
                                     v5,
                                     (unsigned int)v33,
                                     (unsigned int)&v23,
                                     v7) )
                {
                  v14 = StringCchCopyW(v32, 0x104u, v33);
                  LastError = StatusFromHResult(v14);
                  if ( !LastError )
                  {
                    v15 = StringCchCatW(v32, 0x104u, (const unsigned __int16 *)*a1[2]);
                    LastError = StatusFromHResult(v15);
                    if ( !LastError )
                    {
                      if ( MakeCanonicalPath(v32, LibFileName, v16) )
                      {
                        if ( (unsigned int)IsModuleFilePathAllowed(LibFileName) )
                        {
                          v17 = (HMODULE *)a1[1];
                          *v17 = LoadLibraryExW(LibFileName, 0, LastError + 8);
                          if ( !*a1[1] )
                            LastError = GetLastError();
                        }
                      }
                    }
                  }
                }
              }
            }
            v7 = *(_QWORD *)(v7 + 8);
          }
          while ( v7 );
          v4 = v22;
        }
        if ( !ImpersonatePrinterClient(v6) )
        {
          v18 = GetLastError();
          ForceProcessShutdown(0x69u, v18);
        }
      }
      else
      {
        LastError = GetLastError();
      }
      SetErrorMode(v4);
      if ( !*a1[1] )
      {
        v19 = (const unsigned __int16 **)a1[2];
        v24 = 101;
        v26 = 0;
        v29 = 0;
        if ( !LastError )
          LastError = 126;
        v25 = 4;
        v28 = 4;
        v27 = LastError;
        v20 = SplLogType::SplLogType((SplLogType *)v30, *v19);
        v21 = 0;
        SplLogEvent2(&LOAD_PLUGIN_FAILED_EVENT, v20, &v27, &v24);
        SetLastError(LastError);
        LocalSpoolerTelemetry::WriteDbgTraceError(
          "SplLoadLibraryTheCopyFileModule::<lambda_38f7dd18b2e40a118f55af49e01f7b6d>::operator ()",
          L"Failed to load the file copy module '%ws'.  Error %d",
          *a1[2],
          LastError);
      }
      result = SetCurrentDirectoryW(Buffer);
      if ( LastError )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x147,
          (unsigned int)"printscan\\print\\spooler\\localspl\\files.c",
          (const char *)LastError,
          v21);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18009a3f4  push    rbp
0x18009a3f6  push    rbx
0x18009a3f7  push    rsi
0x18009a3f8  push    rdi
0x18009a3f9  push    r12
0x18009a3fb  push    r13
0x18009a3fd  push    r14
0x18009a3ff  push    r15
0x18009a401  lea     rbp, [rsp-0C08h]
0x18009a409  sub     rsp, 0D08h
0x18009a410  mov     rax, cs:__security_cookie
0x18009a417  xor     rax, rsp
0x18009a41a  mov     [rbp+0C40h+var_50], rax
0x18009a421  mov     rax, [rcx]
0x18009a424  mov     rsi, rcx
0x18009a427  mov     ebx, 20Ah
0x18009a42c  lea     rcx, [rbp+0C40h+Buffer]; void *
0x18009a433  mov     r8d, ebx; Size
0x18009a436  mov     rdx, [rax]
0x18009a439  mov     rax, [rdx+40h]
0x18009a43d  xor     edx, edx; Val
0x18009a43f  mov     r14, [rax+118h]
0x18009a446  mov     [rsp+0D40h+var_D08], r14
0x18009a44b  call    memset_0
0x18009a450  mov     r8d, ebx; Size
0x18009a453  lea     rcx, [rbp+0C40h+PathName]; void *
0x18009a45a  xor     edx, edx; Val
0x18009a45c  call    memset_0
0x18009a461  mov     edi, 105h
0x18009a466  lea     rdx, [rbp+0C40h+Buffer]; lpBuffer
0x18009a46d  mov     ecx, edi; nBufferLength
0x18009a46f  call    cs:__imp_GetCurrentDirectoryW
0x18009a475  xor     ebx, ebx
0x18009a477  test    eax, eax
0x18009a479  jz      loc_18009A6FB
0x18009a47f  mov     edx, edi; uSize
0x18009a481  lea     rcx, [rbp+0C40h+PathName]; lpBuffer
0x18009a488  call    cs:__imp_GetSystemDirectoryW
0x18009a48e  test    eax, eax
0x18009a490  jz      loc_18009A6FB
0x18009a496  lea     rcx, [rbp+0C40h+PathName]; lpPathName
0x18009a49d  call    cs:__imp_SetCurrentDirectoryW
0x18009a4a3  mov     ecx, 8001h; uMode
0x18009a4a8  call    cs:__imp_SetErrorMode
0x18009a4ae  mov     r12d, eax
0x18009a4b1  mov     [rsp+0D40h+var_D10], eax
0x18009a4b5  call    cs:__imp_RevertToPrinterSelf
0x18009a4bb  mov     r15, rax
0x18009a4be  test    rax, rax
0x18009a4c1  jz      loc_18009A64B
0x18009a4c7  mov     r14, [r14+30h]
0x18009a4cb  mov     edi, ebx
0x18009a4cd  test    r14, r14
0x18009a4d0  jz      loc_18009A62A
0x18009a4d6  mov     r12, [rsp+0D40h+var_D08]
0x18009a4db  mov     rax, [rsi+8]
0x18009a4df  cmp     [rax], rbx
0x18009a4e2  jnz     loc_18009A625
0x18009a4e8  mov     rax, [rsi]
0x18009a4eb  lea     rcx, [rbp+0C40h+var_260]
0x18009a4f2  xor     r9d, r9d
0x18009a4f5  mov     [rsp+0D40h+var_D08], rbx
0x18009a4fa  mov     r8, r14
0x18009a4fd  mov     qword ptr [rsp+0D40h+var_D20], r12
0x18009a502  mov     r13, [rax]
0x18009a505  call    GetDriverDirectory
0x18009a50a  test    eax, eax
0x18009a50c  jz      loc_18009A618
0x18009a512  mov     rcx, [rsi+10h]
0x18009a516  lea     rdx, [rbp+0C40h+LibFileName]; unsigned __int16 *
0x18009a51a  mov     rcx, [rcx]; unsigned __int16 *
0x18009a51d  call    ?MakeCanonicalPath@@YAHPEBGPEAGK@Z; MakeCanonicalPath(ushort const *,ushort *,ulong)
0x18009a522  test    eax, eax
0x18009a524  jz      short loc_18009A54D
0x18009a526  lea     rdx, [rbp+0C40h+var_260]
0x18009a52d  lea     rcx, [rbp+0C40h+LibFileName]; pszFirst
0x18009a531  call    IsModuleFilePathAllowed
0x18009a536  test    eax, eax
0x18009a538  jz      short loc_18009A54D
0x18009a53a  mov     rbx, [rsi+8]
0x18009a53e  lea     rcx, [rbp+0C40h+LibFileName]; lpLibFileName
0x18009a542  call    cs:__imp_LoadLibraryW
0x18009a548  mov     [rbx], rax
0x18009a54b  xor     ebx, ebx
0x18009a54d  mov     rax, [rsi+8]
0x18009a551  cmp     [rax], rbx
0x18009a554  jnz     loc_18009A618
0x18009a55a  mov     rcx, [r13+40h]
0x18009a55e  lea     r9, [rsp+0D40h+var_D08]
0x18009a563  lea     r8, [rbp+0C40h+var_890]
0x18009a56a  mov     qword ptr [rsp+0D40h+var_D20], r14
0x18009a56f  call    GetIniDriverAndDirForThisMachineEx
0x18009a574  test    eax, eax
0x18009a576  jz      loc_18009A618
0x18009a57c  lea     r8, [rbp+0C40h+var_890]; unsigned __int16 *
0x18009a583  mov     edx, 104h; unsigned __int64
0x18009a588  lea     rcx, [rbp+0C40h+var_AA0]; unsigned __int16 *
0x18009a58f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009a594  mov     ecx, eax
0x18009a596  call    StatusFromHResult
0x18009a59b  mov     edi, eax
0x18009a59d  test    eax, eax
0x18009a59f  jnz     short loc_18009A618
0x18009a5a1  mov     r8, [rsi+10h]
0x18009a5a5  lea     rcx, [rbp+0C40h+var_AA0]; unsigned __int16 *
0x18009a5ac  mov     edx, 104h; unsigned __int64
0x18009a5b1  mov     r8, [r8]; unsigned __int16 *
0x18009a5b4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18009a5b9  mov     ecx, eax
0x18009a5bb  call    StatusFromHResult
0x18009a5c0  mov     edi, eax
0x18009a5c2  test    eax, eax
0x18009a5c4  jnz     short loc_18009A618
0x18009a5c6  lea     rdx, [rbp+0C40h+LibFileName]; unsigned __int16 *
0x18009a5ca  lea     rcx, [rbp+0C40h+var_AA0]; unsigned __int16 *
0x18009a5d1  call    ?MakeCanonicalPath@@YAHPEBGPEAGK@Z; MakeCanonicalPath(ushort const *,ushort *,ulong)
0x18009a5d6  test    eax, eax
0x18009a5d8  jz      short loc_18009A618
0x18009a5da  lea     rdx, [rbp+0C40h+var_890]
0x18009a5e1  lea     rcx, [rbp+0C40h+LibFileName]; pszFirst
0x18009a5e5  call    IsModuleFilePathAllowed
0x18009a5ea  test    eax, eax
0x18009a5ec  jz      short loc_18009A618
0x18009a5ee  mov     rbx, [rsi+8]
0x18009a5f2  lea     r8d, [rdi+8]; dwFlags
0x18009a5f6  xor     edx, edx; hFile
0x18009a5f8  lea     rcx, [rbp+0C40h+LibFileName]; lpLibFileName
0x18009a5fc  call    cs:__imp_LoadLibraryExW
0x18009a602  mov     [rbx], rax
0x18009a605  xor     ebx, ebx
0x18009a607  mov     rax, [rsi+8]
0x18009a60b  cmp     [rax], rbx
0x18009a60e  jnz     short loc_18009A618
0x18009a610  call    cs:__imp_GetLastError
0x18009a616  mov     edi, eax
0x18009a618  mov     r14, [r14+8]
0x18009a61c  test    r14, r14
0x18009a61f  jnz     loc_18009A4DB
0x18009a625  mov     r12d, [rsp+0D40h+var_D10]
0x18009a62a  mov     rcx, r15; hToken
0x18009a62d  call    cs:__imp_ImpersonatePrinterClient
0x18009a633  test    eax, eax
0x18009a635  jnz     short loc_18009A653
0x18009a637  call    cs:__imp_GetLastError
0x18009a63d  mov     edx, eax; unsigned int
0x18009a63f  mov     ecx, 69h ; 'i'; unsigned int
0x18009a644  call    ?ForceProcessShutdown@@YAXKK@Z; ForceProcessShutdown(ulong,ulong)
0x18009a649  jmp     short loc_18009A653
0x18009a64b  call    cs:__imp_GetLastError
0x18009a651  mov     edi, eax
0x18009a653  mov     ecx, r12d; uMode
0x18009a656  call    cs:__imp_SetErrorMode
0x18009a65c  mov     rax, [rsi+8]
0x18009a660  cmp     [rax], rbx
0x18009a663  jnz     loc_18009A6EA
0x18009a669  mov     rdx, [rsi+10h]
0x18009a66d  lea     rcx, [rsp+0D40h+var_CD0]; this
0x18009a672  mov     eax, 7Eh ; '~'
0x18009a677  mov     [rsp+0D40h+var_D00], 65h ; 'e'
0x18009a67f  mov     [rsp+0D40h+var_CF0], ebx
0x18009a683  test    edi, edi
0x18009a685  mov     [rsp+0D40h+var_CD8], ebx
0x18009a689  cmovz   edi, eax
0x18009a68c  mov     eax, 4
0x18009a691  mov     [rsp+0D40h+var_CF8], rax
0x18009a696  mov     [rsp+0D40h+var_CE0], rax
0x18009a69b  mov     [rsp+0D40h+var_CE8], edi
0x18009a69f  mov     rdx, [rdx]; unsigned __int16 *
0x18009a6a2  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x18009a6a7  lea     r9, [rsp+0D40h+var_D00]
0x18009a6ac  mov     qword ptr [rsp+0D40h+var_D20], rbx; unsigned int
0x18009a6b1  lea     r8, [rsp+0D40h+var_CE8]
0x18009a6b6  mov     rdx, rax; struct SplLogType *
0x18009a6b9  lea     rcx, LOAD_PLUGIN_FAILED_EVENT; struct _EVENT_DESCRIPTOR *
0x18009a6c0  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x18009a6c5  mov     ecx, edi; dwErrCode
0x18009a6c7  call    cs:__imp_SetLastError
0x18009a6cd  mov     r8, [rsi+10h]
0x18009a6d1  lea     rdx, aFailedToLoadTh_0; "Failed to load the file copy module '%w"...
0x18009a6d8  mov     r9d, edi
0x18009a6db  lea     rcx, aSplloadlibrary_1; "SplLoadLibraryTheCopyFileModule::<lambd"...
0x18009a6e2  mov     r8, [r8]
0x18009a6e5  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18009a6ea  lea     rcx, [rbp+0C40h+Buffer]; lpPathName
0x18009a6f1  call    cs:__imp_SetCurrentDirectoryW
0x18009a6f7  test    edi, edi
0x18009a6f9  jnz     short loc_18009A71E
0x18009a6fb  mov     rcx, [rbp+0C40h+var_50]
0x18009a702  xor     rcx, rsp; StackCookie
0x18009a705  call    __security_check_cookie
0x18009a70a  add     rsp, 0D08h
0x18009a711  pop     r15
0x18009a713  pop     r14
0x18009a715  pop     r13
0x18009a717  pop     r12
0x18009a719  pop     rdi
0x18009a71a  pop     rsi
0x18009a71b  pop     rbx
0x18009a71c  pop     rbp
0x18009a71d  retn
0x18009a71e  mov     rcx, [rbp+0C48h]; this
0x18009a725  lea     r8, aPrintscanPrint_20; "printscan\\print\\spooler\\localspl\\fi"...
0x18009a72c  mov     r9d, edi; char *
0x18009a72f  mov     edx, 147h; void *
0x18009a734  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
