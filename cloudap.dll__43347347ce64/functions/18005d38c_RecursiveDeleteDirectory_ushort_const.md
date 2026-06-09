# RecursiveDeleteDirectory(ushort const *)

- ea: `0x18005d38c`
- end: `0x18005d76e`
- name: `?RecursiveDeleteDirectory@@YAJPEBG@Z`
- size: `994`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180055eb0`
- `0x18005d38c`
- `0x18005d774`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x180042410`
- `0x18004317c`
- `0x18005be88`
- `0x18005d38c`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d57c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d5d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d654`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d57c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d5d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d654`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18005d572`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18005d572`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18005d64a`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18005d64a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005d5c6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005d5c6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005d3dd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005d3dd`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18005d465`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18005d465`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18005d630`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18005d630`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18005d641`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18005d641`

## string_xrefs

- `0x18005d40e`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005d536`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005d594`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005d5e8`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005d669`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005d693`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005d6d7`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005d424`: `CombinePaths`
- `0x18005d6a7`: `CombinePaths`
- `0x18005d551`: `RecursiveDeleteDirectory`
- `0x18005d5ad`: `SetFileAttributesW`
- `0x18005d601`: `DeleteFileW`
- `0x18005d67d`: `RemoveDirectoryW`

## pseudocode

```c
__int64 __fastcall RecursiveDeleteDirectory(const unsigned __int16 *a1)
{
  LPCWSTR v2; // r15
  const WCHAR *v3; // rdi
  DWORD FileAttributesW; // eax
  unsigned int v5; // ebx
  const char *v6; // rax
  const WCHAR *FirstFileW; // rax
  WCHAR *v8; // rbx
  int v9; // edx
  int v10; // edx
  const char *v11; // rax
  unsigned int v12; // r10d
  __int64 v13; // r8
  const char *v14; // r9
  __int64 v15; // r8
  const char *v16; // r9
  __int64 v17; // r8
  signed int LastError; // eax
  const char *v19; // r9
  const char *v20; // rax
  const char *v21; // r9
  __int64 v23; // [rsp+20h] [rbp-E0h]
  LPCWSTR v24; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-B8h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF

  v2 = 0;
  v3 = 0;
  v24 = 0;
  lpFileName = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FileAttributesW = GetFileAttributesW(a1);
  if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
  {
    v5 = -1073741811;
    v21 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v21, 2703, "InvalidArg", &Class);
  }
  else
  {
    v5 = CombinePaths(a1, L"*.*", (unsigned __int16 **)&v24);
    if ( v5 )
    {
      v6 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v5, v6, 2710, "CombinePaths", &Class);
      v2 = v24;
      goto LABEL_34;
    }
    v2 = v24;
    FirstFileW = (const WCHAR *)FindFirstFileW(v24, &FindFileData);
    v24 = FirstFileW;
    if ( FirstFileW != (const WCHAR *)-1LL )
    {
      v8 = (WCHAR *)FirstFileW;
      while ( 1 )
      {
        v9 = FindFileData.cFileName[0] - 46;
        if ( FindFileData.cFileName[0] == 46 )
          v9 = FindFileData.cFileName[1];
        if ( v9 )
        {
          v10 = FindFileData.cFileName[0] - 46;
          if ( FindFileData.cFileName[0] == 46 )
          {
            v10 = FindFileData.cFileName[1] - 46;
            if ( FindFileData.cFileName[1] == 46 )
              v10 = FindFileData.cFileName[2];
          }
          if ( v10 )
          {
            if ( v3 )
            {
              ((void (__fastcall *)(const WCHAR *))g_pLsaFunctionTable->FreeLsaHeap)(v3);
              lpFileName = 0;
            }
            v5 = CombinePaths(a1, FindFileData.cFileName, (unsigned __int16 **)&lpFileName);
            if ( v5 )
            {
              v20 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
              LODWORD(v23) = 2735;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v5, v20, v23, "CombinePaths", &Class);
              v3 = lpFileName;
              goto LABEL_34;
            }
            v3 = lpFileName;
            if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
            {
              if ( (unsigned int)RecursiveDeleteDirectory(lpFileName) )
              {
                v11 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
                LODWORD(v23) = 2743;
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v11, v23, "RecursiveDeleteDirectory", v13);
              }
            }
            else if ( SetFileAttributesW(lpFileName, 0x80u) )
            {
              if ( !DeleteFileW(v3) )
              {
                GetLastError();
                v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
                LODWORD(v23) = 2762;
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v17, v16, v23, "DeleteFileW", FindFileData.cFileName);
              }
            }
            else
            {
              GetLastError();
              v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
              LODWORD(v23) = 2754;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v15, v14, v23, "SetFileAttributesW", FindFileData.cFileName);
            }
            v8 = (WCHAR *)v24;
          }
        }
        if ( !FindNextFileW(v8, &FindFileData) )
        {
          FindClose(v8);
          break;
        }
      }
    }
    if ( RemoveDirectoryW(a1) )
    {
      v5 = 0;
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0xC0070000;
      v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      LODWORD(v23) = 2776;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v5, v19, v23, "RemoveDirectoryW", &Class);
    }
  }
LABEL_34:
  if ( v2 )
    ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v2);
  if ( v3 )
    ((void (__fastcall *)(const WCHAR *))g_pLsaFunctionTable->FreeLsaHeap)(v3);
  return v5;
}

```

## disassembly

```asm
0x18005d38c  push    rbp
0x18005d38e  push    rbx
0x18005d38f  push    rdi
0x18005d390  push    r12
0x18005d392  push    r13
0x18005d394  push    r15
0x18005d396  lea     rbp, [rsp-1B8h]
0x18005d39e  sub     rsp, 2B8h
0x18005d3a5  mov     rax, cs:__security_cookie
0x18005d3ac  xor     rax, rsp
0x18005d3af  mov     [rbp+1E0h+var_40], rax
0x18005d3b6  mov     r13, rcx
0x18005d3b9  xor     r15d, r15d
0x18005d3bc  xor     edi, edi
0x18005d3be  mov     [rsp+2E0h+var_2A0], r15
0x18005d3c3  lea     rcx, [rsp+2E0h+FindFileData]; void *
0x18005d3c8  mov     [rsp+2E0h+lpFileName], rdi
0x18005d3cd  xor     edx, edx; Val
0x18005d3cf  mov     r8d, 250h; Size
0x18005d3d5  call    memset_0
0x18005d3da  mov     rcx, r13; lpFileName
0x18005d3dd  call    cs:__imp_GetFileAttributesW
0x18005d3e3  cmp     eax, 0FFFFFFFFh
0x18005d3e6  jz      loc_18005D6D7
0x18005d3ec  test    al, 10h
0x18005d3ee  jz      loc_18005D6D7
0x18005d3f4  lea     r8, [rsp+2E0h+var_2A0]; unsigned __int16 **
0x18005d3f9  mov     rcx, r13; unsigned __int16 *
0x18005d3fc  lea     rdx, asc_18008B060; "*.*"
0x18005d403  call    ?CombinePaths@@YAJPEBG0PEAPEAG@Z; CombinePaths(ushort const *,ushort const *,ushort * *)
0x18005d408  mov     ebx, eax
0x18005d40a  test    eax, eax
0x18005d40c  jz      short loc_18005D458
0x18005d40e  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005d415  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005d41a  mov     r9, rax
0x18005d41d  lea     r12, Class
0x18005d424  lea     rax, aCombinepaths; "CombinePaths"
0x18005d42b  mov     [rsp+2E0h+var_2B0], r12
0x18005d430  mov     [rsp+2E0h+var_2B8], rax
0x18005d435  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005d43c  mov     r8d, ebx
0x18005d43f  mov     dword ptr [rsp+2E0h+var_2C0], 0A96h
0x18005d447  xor     ecx, ecx
0x18005d449  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005d44e  mov     r15, [rsp+2E0h+var_2A0]
0x18005d453  jmp     loc_18005D71C
0x18005d458  mov     r15, [rsp+2E0h+var_2A0]
0x18005d45d  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x18005d462  mov     rcx, r15; lpFileName
0x18005d465  call    cs:__imp_FindFirstFileW
0x18005d46b  mov     [rsp+2E0h+var_2A0], rax
0x18005d470  lea     r12, Class
0x18005d477  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005d47b  jz      loc_18005D647
0x18005d481  mov     rbx, rax
0x18005d484  movzx   edx, [rsp+2E0h+FindFileData.cFileName]
0x18005d489  mov     ecx, 2Eh ; '.'
0x18005d48e  movzx   eax, cx
0x18005d491  sub     edx, eax
0x18005d493  jnz     short loc_18005D4A4
0x18005d495  movzx   edx, [rsp+2E0h+FindFileData.cFileName+2]
0x18005d49a  xor     eax, eax
0x18005d49c  movzx   ecx, ax
0x18005d49f  sub     edx, ecx
0x18005d4a1  lea     ecx, [rax+2Eh]
0x18005d4a4  test    edx, edx
0x18005d4a6  jz      loc_18005D628
0x18005d4ac  movzx   edx, [rsp+2E0h+FindFileData.cFileName]
0x18005d4b1  movzx   eax, cx
0x18005d4b4  sub     edx, eax
0x18005d4b6  jnz     short loc_18005D4CF
0x18005d4b8  movzx   edx, [rsp+2E0h+FindFileData.cFileName+2]
0x18005d4bd  movzx   eax, cx
0x18005d4c0  sub     edx, eax
0x18005d4c2  jnz     short loc_18005D4CF
0x18005d4c4  movzx   edx, [rbp+1E0h+FindFileData.cFileName+4]
0x18005d4c8  xor     eax, eax
0x18005d4ca  movzx   ecx, ax
0x18005d4cd  sub     edx, ecx
0x18005d4cf  test    edx, edx
0x18005d4d1  jz      loc_18005D628
0x18005d4d7  test    rdi, rdi
0x18005d4da  jz      short loc_18005D4F8
0x18005d4dc  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005d4e3  mov     rcx, rdi
0x18005d4e6  mov     rax, [rax+30h]
0x18005d4ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d4ef  mov     [rsp+2E0h+lpFileName], 0
0x18005d4f8  lea     r8, [rsp+2E0h+lpFileName]; unsigned __int16 **
0x18005d4fd  mov     rcx, r13; unsigned __int16 *
0x18005d500  lea     rdx, [rsp+2E0h+FindFileData.cFileName]; unsigned __int16 *
0x18005d505  call    ?CombinePaths@@YAJPEBG0PEAPEAG@Z; CombinePaths(ushort const *,ushort const *,ushort * *)
0x18005d50a  mov     ebx, eax
0x18005d50c  test    eax, eax
0x18005d50e  jnz     loc_18005D693
0x18005d514  test    byte ptr [rsp+2E0h+FindFileData.dwFileAttributes], 10h
0x18005d519  mov     rdi, [rsp+2E0h+lpFileName]
0x18005d51e  mov     rcx, rdi; unsigned __int16 *
0x18005d521  jz      short loc_18005D56D
0x18005d523  call    ?RecursiveDeleteDirectory@@YAJPEBG@Z; RecursiveDeleteDirectory(ushort const *)
0x18005d528  mov     r10d, eax
0x18005d52b  test    eax, eax
0x18005d52d  jz      loc_18005D623
0x18005d533  test    rdi, rdi
0x18005d536  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005d53d  mov     r8, r12
0x18005d540  cmovnz  r8, rdi
0x18005d544  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005d549  mov     [rsp+2E0h+var_2B0], r8
0x18005d54e  mov     r9, rax
0x18005d551  lea     rax, aRecursivedelet; "RecursiveDeleteDirectory"
0x18005d558  mov     r8d, r10d
0x18005d55b  mov     [rsp+2E0h+var_2B8], rax
0x18005d560  mov     dword ptr [rsp+2E0h+var_2C0], 0AB7h
0x18005d568  jmp     loc_18005D615
0x18005d56d  mov     edx, 80h; dwFileAttributes
0x18005d572  call    cs:__imp_SetFileAttributesW
0x18005d578  test    eax, eax
0x18005d57a  jnz     short loc_18005D5C3
0x18005d57c  call    cs:__imp_GetLastError
0x18005d582  mov     r8d, eax
0x18005d585  test    eax, eax
0x18005d587  jle     short loc_18005D594
0x18005d589  movzx   r8d, ax
0x18005d58d  or      r8d, 0C0070000h
0x18005d594  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005d59b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005d5a0  mov     r9, rax
0x18005d5a3  lea     rax, [rsp+2E0h+FindFileData.cFileName]
0x18005d5a8  mov     [rsp+2E0h+var_2B0], rax
0x18005d5ad  lea     rax, aSetfileattribu; "SetFileAttributesW"
0x18005d5b4  mov     [rsp+2E0h+var_2B8], rax
0x18005d5b9  mov     dword ptr [rsp+2E0h+var_2C0], 0AC2h
0x18005d5c1  jmp     short loc_18005D615
0x18005d5c3  mov     rcx, rdi; lpFileName
0x18005d5c6  call    cs:__imp_DeleteFileW
0x18005d5cc  test    eax, eax
0x18005d5ce  jnz     short loc_18005D623
0x18005d5d0  call    cs:__imp_GetLastError
0x18005d5d6  mov     r8d, eax
0x18005d5d9  test    eax, eax
0x18005d5db  jle     short loc_18005D5E8
0x18005d5dd  movzx   r8d, ax
0x18005d5e1  or      r8d, 0C0070000h
0x18005d5e8  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005d5ef  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005d5f4  mov     r9, rax
0x18005d5f7  lea     rax, [rsp+2E0h+FindFileData.cFileName]
0x18005d5fc  mov     [rsp+2E0h+var_2B0], rax
0x18005d601  lea     rax, aDeletefilew; "DeleteFileW"
0x18005d608  mov     [rsp+2E0h+var_2B8], rax
0x18005d60d  mov     dword ptr [rsp+2E0h+var_2C0], 0ACAh
0x18005d615  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005d61c  xor     ecx, ecx
0x18005d61e  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005d623  mov     rbx, [rsp+2E0h+var_2A0]
0x18005d628  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x18005d62d  mov     rcx, rbx; hFindFile
0x18005d630  call    cs:__imp_FindNextFileW
0x18005d636  test    eax, eax
0x18005d638  jnz     loc_18005D484
0x18005d63e  mov     rcx, rbx; hFindFile
0x18005d641  call    cs:__imp_FindClose
0x18005d647  mov     rcx, r13; lpPathName
0x18005d64a  call    cs:__imp_RemoveDirectoryW
0x18005d650  test    eax, eax
0x18005d652  jnz     short loc_18005D6D3
0x18005d654  call    cs:__imp_GetLastError
0x18005d65a  mov     ebx, eax
0x18005d65c  test    eax, eax
0x18005d65e  jle     short loc_18005D669
0x18005d660  movzx   ebx, ax
0x18005d663  or      ebx, 0C0070000h
0x18005d669  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005d670  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005d675  mov     [rsp+2E0h+var_2B0], r12
0x18005d67a  mov     r9, rax
0x18005d67d  lea     rax, aRemovedirector; "RemoveDirectoryW"
0x18005d684  mov     [rsp+2E0h+var_2B8], rax
0x18005d689  mov     dword ptr [rsp+2E0h+var_2C0], 0AD8h
0x18005d691  jmp     short loc_18005D70B
0x18005d693  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005d69a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005d69f  mov     r9, rax
0x18005d6a2  mov     [rsp+2E0h+var_2B0], r12
0x18005d6a7  lea     rax, aCombinepaths; "CombinePaths"
0x18005d6ae  mov     r8d, ebx
0x18005d6b1  mov     [rsp+2E0h+var_2B8], rax
0x18005d6b6  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005d6bd  xor     ecx, ecx
0x18005d6bf  mov     dword ptr [rsp+2E0h+var_2C0], 0AAFh
0x18005d6c7  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005d6cc  mov     rdi, [rsp+2E0h+lpFileName]
0x18005d6d1  jmp     short loc_18005D71C
0x18005d6d3  xor     ebx, ebx
0x18005d6d5  jmp     short loc_18005D71C
0x18005d6d7  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005d6de  mov     ebx, 0C000000Dh
0x18005d6e3  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005d6e8  mov     r9, rax
0x18005d6eb  lea     r12, Class
0x18005d6f2  mov     [rsp+2E0h+var_2B0], r12
0x18005d6f7  lea     rax, aInvalidarg; "InvalidArg"
0x18005d6fe  mov     [rsp+2E0h+var_2B8], rax
0x18005d703  mov     dword ptr [rsp+2E0h+var_2C0], 0A8Fh
0x18005d70b  mov     r8d, ebx
0x18005d70e  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005d715  xor     ecx, ecx
0x18005d717  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005d71c  test    r15, r15
0x18005d71f  jz      short loc_18005D734
0x18005d721  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005d728  mov     rcx, r15
0x18005d72b  mov     rax, [rax+30h]
0x18005d72f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d734  test    rdi, rdi
0x18005d737  jz      short loc_18005D74C
0x18005d739  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005d740  mov     rcx, rdi
0x18005d743  mov     rax, [rax+30h]
0x18005d747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d74c  mov     eax, ebx
0x18005d74e  mov     rcx, [rbp+1E0h+var_40]
0x18005d755  xor     rcx, rsp; StackCookie
0x18005d758  call    __security_check_cookie
0x18005d75d  add     rsp, 2B8h
0x18005d764  pop     r15
0x18005d766  pop     r13
0x18005d768  pop     r12
0x18005d76a  pop     rdi
0x18005d76b  pop     rbx
0x18005d76c  pop     rbp
0x18005d76d  retn
```
