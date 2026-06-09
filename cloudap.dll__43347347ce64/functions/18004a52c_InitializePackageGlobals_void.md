# InitializePackageGlobals(void)

- ea: `0x18004a52c`
- end: `0x18004a85d`
- name: `?InitializePackageGlobals@@YAJXZ`
- size: `817`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004b1e0`

## callees

- `0x180007690`
- `0x180007fc0`
- `0x18000a600`
- `0x18001e080`
- `0x180042410`
- `0x18004a52c`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a56f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a6af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a738`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a7c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a56f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a6af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a738`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a7c1`
- `USERENV!__imp_GetUserProfileDirectoryForUserSidW` at `0x18004a563`
- `USERENV!__imp_GetUserProfileDirectoryForUserSidW` at `0x18004a563`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004a6a5`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004a72e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004a7b7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004a6a5`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004a72e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004a7b7`

## string_xrefs

- `0x18004a584`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004a5fc`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004a66c`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004a6cb`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004a706`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004a754`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004a78f`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004a7dd`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004a59f`: `GetUserProfileDirectoryForUserSidW`
- `0x18004a7fe`: `CreateDirectoryW`
- `0x18004a777`: `\CloudAPCache`

## pseudocode

```c
__int64 InitializePackageGlobals(void)
{
  signed int v0; // eax
  unsigned int v1; // ebx
  const char *v2; // r9
  __int64 v3; // rax
  unsigned int v4; // ebx
  unsigned __int16 *v5; // rdi
  const char *v6; // r9
  unsigned __int64 v7; // rsi
  const char *v8; // rax
  __int64 v9; // r8
  const char *v10; // r10
  __int64 v11; // r11
  int v12; // edx
  const char *v13; // r9
  const char *v14; // rcx
  const WCHAR *v15; // rax
  signed int v16; // eax
  const char *v17; // rax
  signed int v18; // eax
  signed int LastError; // eax
  __int64 v21; // [rsp+20h] [rbp-278h]
  int v22[4]; // [rsp+40h] [rbp-258h] BYREF
  _WORD v23[264]; // [rsp+50h] [rbp-248h] BYREF

  v22[0] = 261;
  if ( (unsigned int)GetUserProfileDirectoryForUserSidW(L"S-1-5-18", v23, v22) )
  {
    v3 = -1;
    do
      ++v3;
    while ( v23[v3] );
    v4 = 2 * v3 + 100;
    v5 = (unsigned __int16 *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(v4);
    if ( !v5 )
    {
      v1 = -1073741801;
      v6 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v6, 209, "AllocateLsaHeap", &Class);
      return v1;
    }
    v7 = (unsigned __int64)v4 >> 1;
    v1 = RtlStringCchPrintfW(v5, v7, L"%ws%ws%ws", L"\\\\?\\", v23, L"\\AppData\\Local\\Microsoft");
    if ( v1 )
    {
      v8 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      v12 = 219;
LABEL_12:
      v13 = v8;
      v14 = "RtlStringCchPrintfW";
      v15 = &Class;
LABEL_33:
      LODWORD(v21) = v12;
      WPPTraceLogA(v11, v10, v9, v13, v21, v14, v15);
      ((void (__fastcall *)(unsigned __int16 *))g_pLsaFunctionTable->FreeLsaHeap)(v5);
      return v1;
    }
    if ( CreateDirectoryW(v5, 0) || (v16 = GetLastError(), v1 = v16, v16 == 183) )
    {
      v1 = RtlStringCchCatW(v5, v7, L"\\Windows");
      if ( v1 )
      {
        v8 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        v12 = 237;
        goto LABEL_12;
      }
      if ( CreateDirectoryW(v5, 0) || (v18 = GetLastError(), v1 = v18, v18 == 183) )
      {
        v1 = RtlStringCchCatW(v5, v7, L"\\CloudAPCache");
        if ( v1 )
        {
          v8 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
          v12 = 255;
          goto LABEL_12;
        }
        if ( CreateDirectoryW(v5, 0) || (LastError = GetLastError(), v1 = LastError, LastError == 183) )
        {
          g_pwszCacheRootDirectory = v5;
          return 0;
        }
        if ( LastError > 0 )
          v1 = (unsigned __int16)LastError | 0xC0070000;
        v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        v12 = 265;
      }
      else
      {
        if ( v18 > 0 )
          v1 = (unsigned __int16)v18 | 0xC0070000;
        v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        v12 = 247;
      }
    }
    else
    {
      if ( v16 > 0 )
        v1 = (unsigned __int16)v16 | 0xC0070000;
      v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      v12 = 229;
    }
    v13 = v17;
    v14 = "CreateDirectoryW";
    v15 = v5;
    goto LABEL_33;
  }
  v0 = GetLastError();
  v1 = v0;
  if ( v0 > 0 )
    v1 = (unsigned __int16)v0 | 0xC0070000;
  v2 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v1, v2, 193, "GetUserProfileDirectoryForUserSidW", &Class);
  return v1;
}

```

## disassembly

```asm
0x18004a52c  push    rbx
0x18004a52e  push    rbp
0x18004a52f  push    rsi
0x18004a530  push    rdi
0x18004a531  sub     rsp, 278h
0x18004a538  mov     rax, cs:__security_cookie
0x18004a53f  xor     rax, rsp
0x18004a542  mov     [rsp+298h+var_38], rax
0x18004a54a  lea     r8, [rsp+298h+var_258]
0x18004a54f  mov     [rsp+298h+var_258], 105h
0x18004a557  lea     rdx, [rsp+298h+var_248]
0x18004a55c  lea     rcx, aS1518; "S-1-5-18"
0x18004a563  call    cs:__imp_GetUserProfileDirectoryForUserSidW
0x18004a569  xor     ebp, ebp
0x18004a56b  test    eax, eax
0x18004a56d  jnz     short loc_18004A5C9
0x18004a56f  call    cs:__imp_GetLastError
0x18004a575  mov     ebx, eax
0x18004a577  test    eax, eax
0x18004a579  jle     short loc_18004A584
0x18004a57b  movzx   ebx, ax
0x18004a57e  or      ebx, 0C0070000h
0x18004a584  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004a58b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004a590  mov     r9, rax
0x18004a593  lea     rax, Class
0x18004a59a  mov     [rsp+298h+var_268], rax
0x18004a59f  lea     rax, aGetuserprofile; "GetUserProfileDirectoryForUserSidW"
0x18004a5a6  mov     [rsp+298h+var_270], rax
0x18004a5ab  mov     dword ptr [rsp+298h+var_278], 0C1h
0x18004a5b3  mov     r8d, ebx
0x18004a5b6  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004a5bd  xor     ecx, ecx
0x18004a5bf  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004a5c4  jmp     loc_18004A83F
0x18004a5c9  lea     rcx, [rsp+298h+var_248]
0x18004a5ce  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004a5d2  inc     rax
0x18004a5d5  cmp     [rcx+rax*2], bp
0x18004a5d9  jnz     short loc_18004A5D2
0x18004a5db  lea     ebx, ds:64h[rax*2]
0x18004a5e2  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18004a5e9  mov     ecx, ebx
0x18004a5eb  mov     rax, [rax+28h]
0x18004a5ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a5f4  mov     rdi, rax
0x18004a5f7  test    rax, rax
0x18004a5fa  jnz     short loc_18004A632
0x18004a5fc  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004a603  mov     ebx, 0C0000017h
0x18004a608  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004a60d  mov     r9, rax
0x18004a610  lea     rax, Class
0x18004a617  mov     [rsp+298h+var_268], rax
0x18004a61c  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x18004a623  mov     [rsp+298h+var_270], rax
0x18004a628  mov     dword ptr [rsp+298h+var_278], 0D1h
0x18004a630  jmp     short loc_18004A5B3
0x18004a632  lea     rax, aAppdataLocalMi; "\\AppData\\Local\\Microsoft"
0x18004a639  mov     esi, ebx
0x18004a63b  mov     [rsp+298h+var_270], rax
0x18004a640  lea     r9, asc_180086FE0; "\\\\?\\"
0x18004a647  lea     rax, [rsp+298h+var_248]
0x18004a64c  shr     rsi, 1
0x18004a64f  mov     rdx, rsi; unsigned __int64
0x18004a652  mov     [rsp+298h+var_278], rax
0x18004a657  lea     r8, aWsWsWs; "%ws%ws%ws"
0x18004a65e  mov     rcx, rdi; unsigned __int16 *
0x18004a661  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004a666  mov     ebx, eax
0x18004a668  test    eax, eax
0x18004a66a  jz      short loc_18004A6A0
0x18004a66c  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004a673  mov     r11, rbp
0x18004a676  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004a67d  mov     r8d, eax
0x18004a680  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004a685  mov     edx, 0DBh
0x18004a68a  mov     r9, rax
0x18004a68d  lea     rcx, aRtlstringcchpr; "RtlStringCchPrintfW"
0x18004a694  lea     rax, Class
0x18004a69b  jmp     loc_18004A808
0x18004a6a0  xor     edx, edx; lpSecurityAttributes
0x18004a6a2  mov     rcx, rdi; lpPathName
0x18004a6a5  call    cs:__imp_CreateDirectoryW
0x18004a6ab  test    eax, eax
0x18004a6ad  jnz     short loc_18004A6EE
0x18004a6af  call    cs:__imp_GetLastError
0x18004a6b5  mov     ebx, eax
0x18004a6b7  cmp     eax, 0B7h
0x18004a6bc  jz      short loc_18004A6EE
0x18004a6be  test    eax, eax
0x18004a6c0  jle     short loc_18004A6CB
0x18004a6c2  movzx   ebx, ax
0x18004a6c5  or      ebx, 0C0070000h
0x18004a6cb  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004a6d2  mov     r11, rbp
0x18004a6d5  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004a6dc  mov     r8d, ebx
0x18004a6df  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004a6e4  mov     edx, 0E5h
0x18004a6e9  jmp     loc_18004A7FB
0x18004a6ee  lea     r8, aWindows; "\\Windows"
0x18004a6f5  mov     rdx, rsi; unsigned __int64
0x18004a6f8  mov     rcx, rdi; unsigned __int16 *
0x18004a6fb  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004a700  mov     ebx, eax
0x18004a702  test    eax, eax
0x18004a704  jz      short loc_18004A729
0x18004a706  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004a70d  mov     r11, rbp
0x18004a710  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004a717  mov     r8d, eax
0x18004a71a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004a71f  mov     edx, 0EDh
0x18004a724  jmp     loc_18004A68A
0x18004a729  xor     edx, edx; lpSecurityAttributes
0x18004a72b  mov     rcx, rdi; lpPathName
0x18004a72e  call    cs:__imp_CreateDirectoryW
0x18004a734  test    eax, eax
0x18004a736  jnz     short loc_18004A777
0x18004a738  call    cs:__imp_GetLastError
0x18004a73e  mov     ebx, eax
0x18004a740  cmp     eax, 0B7h
0x18004a745  jz      short loc_18004A777
0x18004a747  test    eax, eax
0x18004a749  jle     short loc_18004A754
0x18004a74b  movzx   ebx, ax
0x18004a74e  or      ebx, 0C0070000h
0x18004a754  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004a75b  mov     r11, rbp
0x18004a75e  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004a765  mov     r8d, ebx
0x18004a768  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004a76d  mov     edx, 0F7h
0x18004a772  jmp     loc_18004A7FB
0x18004a777  lea     r8, aCloudapcache; "\\CloudAPCache"
0x18004a77e  mov     rdx, rsi; unsigned __int64
0x18004a781  mov     rcx, rdi; unsigned __int16 *
0x18004a784  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004a789  mov     ebx, eax
0x18004a78b  test    eax, eax
0x18004a78d  jz      short loc_18004A7B2
0x18004a78f  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004a796  mov     r11, rbp
0x18004a799  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004a7a0  mov     r8d, eax
0x18004a7a3  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004a7a8  mov     edx, 0FFh
0x18004a7ad  jmp     loc_18004A68A
0x18004a7b2  xor     edx, edx; lpSecurityAttributes
0x18004a7b4  mov     rcx, rdi; lpPathName
0x18004a7b7  call    cs:__imp_CreateDirectoryW
0x18004a7bd  test    eax, eax
0x18004a7bf  jnz     short loc_18004A836
0x18004a7c1  call    cs:__imp_GetLastError
0x18004a7c7  mov     ebx, eax
0x18004a7c9  cmp     eax, 0B7h
0x18004a7ce  jz      short loc_18004A836
0x18004a7d0  test    eax, eax
0x18004a7d2  jle     short loc_18004A7DD
0x18004a7d4  movzx   ebx, ax
0x18004a7d7  or      ebx, 0C0070000h
0x18004a7dd  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004a7e4  mov     r11, rbp
0x18004a7e7  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004a7ee  mov     r8d, ebx
0x18004a7f1  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004a7f6  mov     edx, 109h
0x18004a7fb  mov     r9, rax
0x18004a7fe  lea     rcx, aCreatedirector; "CreateDirectoryW"
0x18004a805  mov     rax, rdi
0x18004a808  mov     [rsp+298h+var_268], rax
0x18004a80d  mov     [rsp+298h+var_270], rcx
0x18004a812  mov     rcx, r11
0x18004a815  mov     dword ptr [rsp+298h+var_278], edx
0x18004a819  mov     rdx, r10
0x18004a81c  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004a821  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18004a828  mov     rcx, rdi
0x18004a82b  mov     rax, [rax+30h]
0x18004a82f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a834  jmp     short loc_18004A83F
0x18004a836  mov     cs:?g_pwszCacheRootDirectory@@3PEAGEA, rdi; ushort * g_pwszCacheRootDirectory
0x18004a83d  mov     ebx, ebp
0x18004a83f  mov     eax, ebx
0x18004a841  mov     rcx, [rsp+298h+var_38]
0x18004a849  xor     rcx, rsp; StackCookie
0x18004a84c  call    __security_check_cookie
0x18004a851  add     rsp, 278h
0x18004a858  pop     rdi
0x18004a859  pop     rsi
0x18004a85a  pop     rbp
0x18004a85b  pop     rbx
0x18004a85c  retn
```
