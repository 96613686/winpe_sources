# RecursiveCopyDirectory(ushort *,ushort *)

- ea: `0x18005ced0`
- end: `0x18005d386`
- name: `?RecursiveCopyDirectory@@YAJPEAG0@Z`
- size: `1206`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180055eb0`
- `0x18005ced0`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x180042410`
- `0x18004317c`
- `0x18005be88`
- `0x18005ced0`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cfd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d044`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d1bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cfd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d044`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d1bc`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18005d026`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18005d026`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005cfc8`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005cfc8`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18005d210`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18005d210`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18005d341`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18005d341`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18005d1b2`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18005d1b2`

## string_xrefs

- `0x18005cf79`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005cfe1`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005d035`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005d17e`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005d1c5`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005d223`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005d26b`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005d2ab`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005cff5`: `CreateDirectoryW`
- `0x18005cf94`: `CombinePaths`
- `0x18005d237`: `CombinePaths`
- `0x18005d27f`: `CombinePaths`
- `0x18005d199`: `RecursiveCopyDirectory`
- `0x18005d1e3`: `CopyFileW`

## pseudocode

```c
__int64 __fastcall RecursiveCopyDirectory(unsigned __int16 *a1, unsigned __int16 *a2)
{
  LPCWSTR v4; // r15
  LPCWSTR v5; // rdi
  LPCWSTR v6; // rsi
  __int64 FirstFile; // r13
  DWORD LastError; // ebx
  const char *v9; // r9
  const char *v10; // r9
  const char *v11; // rbx
  DWORD v12; // eax
  int v13; // edx
  int v14; // ecx
  const char *v15; // rax
  __int64 v16; // r8
  const char *v17; // rax
  unsigned int v18; // r10d
  __int64 v19; // r8
  const char *v20; // rax
  const char *v21; // rax
  const char *v22; // rax
  LPVOID lpSearchFilter; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpExistingFileName; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpPathName; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpFileName; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v28; // [rsp+58h] [rbp-A8h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF

  v28 = a1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v4 = 0;
  v5 = 0;
  v6 = 0;
  lpFileName = 0;
  FirstFile = -1;
  lpExistingFileName = 0;
  lpPathName = 0;
  if ( a1 && *a1 && a2 && *a2 )
  {
    LastError = CombinePaths(a1, L"*.*", (unsigned __int16 **)&lpFileName);
    if ( LastError )
    {
      v9 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LastError, v9, 3134, "CombinePaths", &Class);
LABEL_7:
      v4 = lpFileName;
      goto LABEL_37;
    }
    if ( !CreateDirectoryW(a2, 0) )
    {
      LastError = GetLastError();
      if ( LastError != 183 )
      {
        v10 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LastError, v10, 3144, "CreateDirectoryW", a2);
        goto LABEL_7;
      }
    }
    v4 = lpFileName;
    FirstFile = (__int64)FindFirstFileExW(lpFileName, FindExInfoStandard, &FindFileData, FindExSearchNameMatch, 0, 0);
    if ( FirstFile != -1 )
    {
      while ( 1 )
      {
        v13 = FindFileData.cFileName[0] - 46;
        if ( FindFileData.cFileName[0] == 46 )
          v13 = FindFileData.cFileName[1];
        if ( v13 )
        {
          v14 = FindFileData.cFileName[0] - 46;
          if ( FindFileData.cFileName[0] == 46 )
          {
            v14 = FindFileData.cFileName[1] - 46;
            if ( FindFileData.cFileName[1] == 46 )
              v14 = FindFileData.cFileName[2];
          }
          if ( v14 )
          {
            if ( v5 )
            {
              ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v5);
              lpExistingFileName = 0;
            }
            if ( v6 )
            {
              ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v6);
              v6 = 0;
              lpPathName = 0;
            }
            LastError = CombinePaths(v28, FindFileData.cFileName, (unsigned __int16 **)&lpExistingFileName);
            if ( LastError )
            {
              v21 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
              LODWORD(lpSearchFilter) = 3186;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LastError, v21, lpSearchFilter, "CombinePaths", &Class);
              v5 = lpExistingFileName;
              goto LABEL_37;
            }
            LastError = CombinePaths(a2, FindFileData.cFileName, (unsigned __int16 **)&lpPathName);
            if ( LastError )
            {
              v20 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
              LODWORD(lpSearchFilter) = 3189;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LastError, v20, lpSearchFilter, "CombinePaths", &Class);
              v5 = lpExistingFileName;
              v6 = lpPathName;
              goto LABEL_37;
            }
            v6 = lpPathName;
            v5 = lpExistingFileName;
            if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
            {
              if ( (unsigned int)RecursiveCopyDirectory(
                                   (unsigned __int16 *)lpExistingFileName,
                                   (unsigned __int16 *)lpPathName) )
              {
                v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
                LODWORD(lpSearchFilter) = 3194;
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v18, v15, lpSearchFilter, "RecursiveCopyDirectory", v16);
              }
            }
            else if ( !CopyFileW(lpExistingFileName, lpPathName, 0) )
            {
              GetLastError();
              v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
              LODWORD(lpSearchFilter) = 3201;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v18, v17, lpSearchFilter, "CopyFileW", v19);
            }
          }
        }
        if ( !FindNextFileW((HANDLE)FirstFile, &FindFileData) )
          goto LABEL_13;
      }
    }
    v11 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    v12 = GetLastError();
    LODWORD(lpSearchFilter) = 3159;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v11, lpSearchFilter, "FindFirstFileEx", &Class);
LABEL_13:
    LastError = 0;
  }
  else
  {
    LastError = 87;
    v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 87, v22, 3130, "Invalid Arg(s)", &Class);
  }
LABEL_37:
  if ( v4 )
    ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v4);
  if ( v5 )
    ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v5);
  if ( v6 )
    ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v6);
  if ( FirstFile != -1 )
    FindClose((HANDLE)FirstFile);
  if ( LastError )
  {
    if ( (int)LastError > 0 )
      return (unsigned __int16)LastError | 0xC0070000;
  }
  else
  {
    return 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x18005ced0  mov     [rsp-8+arg_10], rbx
0x18005ced5  push    rbp
0x18005ced6  push    rsi
0x18005ced7  push    rdi
0x18005ced8  push    r12
0x18005ceda  push    r13
0x18005cedc  push    r14
0x18005cede  push    r15
0x18005cee0  lea     rbp, [rsp-1C0h]
0x18005cee8  sub     rsp, 2C0h
0x18005ceef  mov     rax, cs:__security_cookie
0x18005cef6  xor     rax, rsp
0x18005cef9  mov     [rbp+1F0h+var_40], rax
0x18005cf00  mov     r12, rdx
0x18005cf03  mov     [rsp+2F0h+var_298], rcx
0x18005cf08  mov     rbx, rcx
0x18005cf0b  xor     edx, edx; Val
0x18005cf0d  lea     rcx, [rsp+2F0h+FindFileData]; void *
0x18005cf12  mov     r8d, 250h; Size
0x18005cf18  call    memset_0
0x18005cf1d  xor     r15d, r15d
0x18005cf20  xor     edi, edi
0x18005cf22  xor     esi, esi
0x18005cf24  mov     [rsp+2F0h+lpFileName], r15
0x18005cf29  or      r13, 0FFFFFFFFFFFFFFFFh
0x18005cf2d  mov     [rsp+2F0h+lpExistingFileName], rdi
0x18005cf32  mov     [rsp+2F0h+lpPathName], rsi
0x18005cf37  test    rbx, rbx
0x18005cf3a  jz      loc_18005D2AB
0x18005cf40  xor     eax, eax
0x18005cf42  cmp     ax, [rbx]
0x18005cf45  jz      loc_18005D2AB
0x18005cf4b  test    r12, r12
0x18005cf4e  jz      loc_18005D2AB
0x18005cf54  cmp     ax, [r12]
0x18005cf59  jz      loc_18005D2AB
0x18005cf5f  lea     r8, [rsp+2F0h+lpFileName]; unsigned __int16 **
0x18005cf64  mov     rcx, rbx; unsigned __int16 *
0x18005cf67  lea     rdx, asc_18008B060; "*.*"
0x18005cf6e  call    ?CombinePaths@@YAJPEBG0PEAPEAG@Z; CombinePaths(ushort const *,ushort const *,ushort * *)
0x18005cf73  mov     ebx, eax
0x18005cf75  test    eax, eax
0x18005cf77  jz      short loc_18005CFC3
0x18005cf79  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005cf80  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005cf85  mov     r9, rax
0x18005cf88  lea     r14, Class
0x18005cf8f  mov     [rsp+2F0h+var_2C0], r14
0x18005cf94  lea     rax, aCombinepaths; "CombinePaths"
0x18005cf9b  mov     qword ptr [rsp+2F0h+dwAdditionalFlags], rax
0x18005cfa0  mov     dword ptr [rsp+2F0h+lpSearchFilter], 0C3Eh
0x18005cfa8  mov     r8d, ebx
0x18005cfab  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005cfb2  xor     ecx, ecx
0x18005cfb4  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005cfb9  mov     r15, [rsp+2F0h+lpFileName]
0x18005cfbe  jmp     loc_18005D2F0
0x18005cfc3  xor     edx, edx; lpSecurityAttributes
0x18005cfc5  mov     rcx, r12; lpPathName
0x18005cfc8  call    cs:__imp_CreateDirectoryW
0x18005cfce  test    eax, eax
0x18005cfd0  jnz     short loc_18005D00B
0x18005cfd2  call    cs:__imp_GetLastError
0x18005cfd8  mov     ebx, eax
0x18005cfda  cmp     eax, 0B7h
0x18005cfdf  jz      short loc_18005D00B
0x18005cfe1  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005cfe8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005cfed  mov     [rsp+2F0h+var_2C0], r12
0x18005cff2  mov     r9, rax
0x18005cff5  lea     rax, aCreatedirector; "CreateDirectoryW"
0x18005cffc  mov     qword ptr [rsp+2F0h+dwAdditionalFlags], rax
0x18005d001  mov     dword ptr [rsp+2F0h+lpSearchFilter], 0C48h
0x18005d009  jmp     short loc_18005CFA8
0x18005d00b  mov     r15, [rsp+2F0h+lpFileName]
0x18005d010  lea     r8, [rsp+2F0h+FindFileData]; lpFindFileData
0x18005d015  mov     rcx, r15; lpFileName
0x18005d018  mov     [rsp+2F0h+dwAdditionalFlags], esi; dwAdditionalFlags
0x18005d01c  xor     r9d, r9d; fSearchOp
0x18005d01f  mov     [rsp+2F0h+lpSearchFilter], rsi; lpSearchFilter
0x18005d024  xor     edx, edx; fInfoLevelId
0x18005d026  call    cs:__imp_FindFirstFileExW
0x18005d02c  mov     r13, rax
0x18005d02f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005d033  jnz     short loc_18005D085
0x18005d035  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005d03c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005d041  mov     rbx, rax
0x18005d044  call    cs:__imp_GetLastError
0x18005d04a  lea     rcx, aFindfirstfilee; "FindFirstFileEx"
0x18005d051  mov     r9, rbx
0x18005d054  lea     r14, Class
0x18005d05b  mov     r8d, eax
0x18005d05e  mov     [rsp+2F0h+var_2C0], r14
0x18005d063  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005d06a  mov     qword ptr [rsp+2F0h+dwAdditionalFlags], rcx
0x18005d06f  xor     ecx, ecx
0x18005d071  mov     dword ptr [rsp+2F0h+lpSearchFilter], 0C57h
0x18005d079  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005d07e  xor     ebx, ebx
0x18005d080  jmp     loc_18005D2F0
0x18005d085  lea     r14, Class
0x18005d08c  movzx   edx, [rbp+1F0h+var_264]
0x18005d090  mov     r8d, 2Eh ; '.'
0x18005d096  movzx   eax, r8w
0x18005d09a  sub     edx, eax
0x18005d09c  jnz     short loc_18005D0A9
0x18005d09e  movzx   edx, [rbp+1F0h+var_262]
0x18005d0a2  xor     eax, eax
0x18005d0a4  movzx   ecx, ax
0x18005d0a7  sub     edx, ecx
0x18005d0a9  test    edx, edx
0x18005d0ab  jz      loc_18005D208
0x18005d0b1  movzx   ecx, [rbp+1F0h+var_264]
0x18005d0b5  movzx   eax, r8w
0x18005d0b9  sub     ecx, eax
0x18005d0bb  jnz     short loc_18005D0D4
0x18005d0bd  movzx   ecx, [rbp+1F0h+var_262]
0x18005d0c1  movzx   eax, r8w
0x18005d0c5  sub     ecx, eax
0x18005d0c7  jnz     short loc_18005D0D4
0x18005d0c9  movzx   ecx, [rbp+1F0h+var_260]
0x18005d0cd  xor     eax, eax
0x18005d0cf  movzx   edx, ax
0x18005d0d2  sub     ecx, edx
0x18005d0d4  test    ecx, ecx
0x18005d0d6  jz      loc_18005D208
0x18005d0dc  test    rdi, rdi
0x18005d0df  jz      short loc_18005D0FD
0x18005d0e1  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005d0e8  mov     rcx, rdi
0x18005d0eb  mov     rax, [rax+30h]
0x18005d0ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d0f4  mov     [rsp+2F0h+lpExistingFileName], 0
0x18005d0fd  test    rsi, rsi
0x18005d100  jz      short loc_18005D11C
0x18005d102  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005d109  mov     rcx, rsi
0x18005d10c  mov     rax, [rax+30h]
0x18005d110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d115  xor     esi, esi
0x18005d117  mov     [rsp+2F0h+lpPathName], rsi
0x18005d11c  mov     rcx, [rsp+2F0h+var_298]; unsigned __int16 *
0x18005d121  lea     r8, [rsp+2F0h+lpExistingFileName]; unsigned __int16 **
0x18005d126  lea     rdx, [rbp+1F0h+var_264]; unsigned __int16 *
0x18005d12a  call    ?CombinePaths@@YAJPEBG0PEAPEAG@Z; CombinePaths(ushort const *,ushort const *,ushort * *)
0x18005d12f  mov     ebx, eax
0x18005d131  test    eax, eax
0x18005d133  jnz     loc_18005D26B
0x18005d139  lea     r8, [rsp+2F0h+lpPathName]; unsigned __int16 **
0x18005d13e  mov     rcx, r12; unsigned __int16 *
0x18005d141  lea     rdx, [rbp+1F0h+var_264]; unsigned __int16 *
0x18005d145  call    ?CombinePaths@@YAJPEBG0PEAPEAG@Z; CombinePaths(ushort const *,ushort const *,ushort * *)
0x18005d14a  mov     ebx, eax
0x18005d14c  test    eax, eax
0x18005d14e  jnz     loc_18005D223
0x18005d154  test    [rsp+2F0h+FindFileData], 10h
0x18005d159  mov     rsi, [rsp+2F0h+lpPathName]
0x18005d15e  mov     rdi, [rsp+2F0h+lpExistingFileName]
0x18005d163  mov     rdx, rsi; unsigned __int16 *
0x18005d166  mov     rcx, rdi; unsigned __int16 *
0x18005d169  jz      short loc_18005D1AF
0x18005d16b  call    ?RecursiveCopyDirectory@@YAJPEAG0@Z; RecursiveCopyDirectory(ushort *,ushort *)
0x18005d170  mov     r10d, eax
0x18005d173  test    eax, eax
0x18005d175  jz      loc_18005D208
0x18005d17b  test    rdi, rdi
0x18005d17e  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005d185  mov     r8, r14
0x18005d188  cmovnz  r8, rdi
0x18005d18c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005d191  mov     [rsp+2F0h+var_2C0], r8
0x18005d196  mov     r9, rax
0x18005d199  lea     rax, aRecursivecopyd; "RecursiveCopyDirectory"
0x18005d1a0  mov     qword ptr [rsp+2F0h+dwAdditionalFlags], rax
0x18005d1a5  mov     dword ptr [rsp+2F0h+lpSearchFilter], 0C7Ah
0x18005d1ad  jmp     short loc_18005D1F7
0x18005d1af  xor     r8d, r8d; bFailIfExists
0x18005d1b2  call    cs:__imp_CopyFileW
0x18005d1b8  test    eax, eax
0x18005d1ba  jnz     short loc_18005D208
0x18005d1bc  call    cs:__imp_GetLastError
0x18005d1c2  test    rdi, rdi
0x18005d1c5  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005d1cc  mov     r8, r14
0x18005d1cf  mov     r10d, eax
0x18005d1d2  cmovnz  r8, rdi
0x18005d1d6  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005d1db  mov     [rsp+2F0h+var_2C0], r8
0x18005d1e0  mov     r9, rax
0x18005d1e3  lea     rax, aCopyfilew; "CopyFileW"
0x18005d1ea  mov     qword ptr [rsp+2F0h+dwAdditionalFlags], rax
0x18005d1ef  mov     dword ptr [rsp+2F0h+lpSearchFilter], 0C81h
0x18005d1f7  mov     r8d, r10d
0x18005d1fa  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005d201  xor     ecx, ecx
0x18005d203  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005d208  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x18005d20d  mov     rcx, r13; hFindFile
0x18005d210  call    cs:__imp_FindNextFileW
0x18005d216  test    eax, eax
0x18005d218  jz      loc_18005D07E
0x18005d21e  jmp     loc_18005D08C
0x18005d223  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005d22a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005d22f  mov     r9, rax
0x18005d232  mov     [rsp+2F0h+var_2C0], r14
0x18005d237  lea     rax, aCombinepaths; "CombinePaths"
0x18005d23e  mov     r8d, ebx
0x18005d241  mov     qword ptr [rsp+2F0h+dwAdditionalFlags], rax
0x18005d246  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005d24d  xor     ecx, ecx
0x18005d24f  mov     dword ptr [rsp+2F0h+lpSearchFilter], 0C75h
0x18005d257  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005d25c  mov     rdi, [rsp+2F0h+lpExistingFileName]
0x18005d261  mov     rsi, [rsp+2F0h+lpPathName]
0x18005d266  jmp     loc_18005D2F0
0x18005d26b  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005d272  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005d277  mov     r9, rax
0x18005d27a  mov     [rsp+2F0h+var_2C0], r14
0x18005d27f  lea     rax, aCombinepaths; "CombinePaths"
0x18005d286  mov     r8d, ebx
0x18005d289  mov     qword ptr [rsp+2F0h+dwAdditionalFlags], rax
0x18005d28e  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005d295  xor     ecx, ecx
0x18005d297  mov     dword ptr [rsp+2F0h+lpSearchFilter], 0C72h
0x18005d29f  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005d2a4  mov     rdi, [rsp+2F0h+lpExistingFileName]
0x18005d2a9  jmp     short loc_18005D2F0
0x18005d2ab  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005d2b2  mov     ebx, 57h ; 'W'
0x18005d2b7  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005d2bc  mov     r9, rax
0x18005d2bf  lea     r14, Class
0x18005d2c6  lea     rax, aInvalidArgS; "Invalid Arg(s)"
0x18005d2cd  mov     [rsp+2F0h+var_2C0], r14
0x18005d2d2  mov     qword ptr [rsp+2F0h+dwAdditionalFlags], rax
0x18005d2d7  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005d2de  mov     r8d, ebx
0x18005d2e1  mov     dword ptr [rsp+2F0h+lpSearchFilter], 0C3Ah
0x18005d2e9  xor     ecx, ecx
0x18005d2eb  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005d2f0  test    r15, r15
0x18005d2f3  jz      short loc_18005D308
0x18005d2f5  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005d2fc  mov     rcx, r15
0x18005d2ff  mov     rax, [rax+30h]
0x18005d303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d308  test    rdi, rdi
0x18005d30b  jz      short loc_18005D320
0x18005d30d  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005d314  mov     rcx, rdi
0x18005d317  mov     rax, [rax+30h]
0x18005d31b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d320  test    rsi, rsi
0x18005d323  jz      short loc_18005D338
0x18005d325  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005d32c  mov     rcx, rsi
0x18005d32f  mov     rax, [rax+30h]
0x18005d333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d338  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x18005d33c  jz      short loc_18005D347
0x18005d33e  mov     rcx, r13; hFindFile
0x18005d341  call    cs:__imp_FindClose
0x18005d347  test    ebx, ebx
0x18005d349  jz      short loc_18005D358
0x18005d34b  jle     short loc_18005D35A
0x18005d34d  movzx   ebx, bx
0x18005d350  or      ebx, 0C0070000h
0x18005d356  jmp     short loc_18005D35A
0x18005d358  xor     ebx, ebx
0x18005d35a  mov     eax, ebx
0x18005d35c  mov     rcx, [rbp+1F0h+var_40]
0x18005d363  xor     rcx, rsp; StackCookie
0x18005d366  call    __security_check_cookie
0x18005d36b  mov     rbx, [rsp+2F0h+arg_10]
0x18005d373  add     rsp, 2C0h
0x18005d37a  pop     r15
0x18005d37c  pop     r14
0x18005d37e  pop     r13
0x18005d380  pop     r12
0x18005d382  pop     rdi
0x18005d383  pop     rsi
0x18005d384  pop     rbp
0x18005d385  retn
```
