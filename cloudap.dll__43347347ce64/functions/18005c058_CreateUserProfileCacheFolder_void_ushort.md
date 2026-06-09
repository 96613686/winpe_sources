# CreateUserProfileCacheFolder(void *,ushort * *)

- ea: `0x18005c058`
- end: `0x18005c45b`
- name: `?CreateUserProfileCacheFolder@@YAJPEAXPEAPEAG@Z`
- size: `1027`
- prototype: `__int64 __fastcall(HANDLE hToken, LPCWSTR *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x1800554d8`
- `0x1800597ac`

## callees

- `0x180007690`
- `0x18001e080`
- `0x18003a5cc`
- `0x18003a8a8`
- `0x18003bf28`
- `0x180042410`
- `0x18004317c`
- `0x18005c058`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c29b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c341`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c3e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c29b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c341`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c3e7`
- `USERENV!GetUserProfileDirectoryW` at `0x18005c0d0`
- `USERENV!GetUserProfileDirectoryW` at `0x18005c0d0`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005c28c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005c337`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005c3dd`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005c28c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005c337`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005c3dd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005c20b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005c20b`

## string_xrefs

- `0x18005c0e1`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005c14c`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005c1d3`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005c252`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005c2ac`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005c2fd`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005c352`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005c3a3`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005c3f8`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18005c17e`: `\CloudAPCache`

## pseudocode

```c
__int64 __fastcall CreateUserProfileCacheFolder(HANDLE hToken, LPCWSTR *a2)
{
  const char *v4; // r9
  unsigned int LastError; // ebx
  unsigned __int64 v7; // rbx
  WCHAR *v8; // rax
  unsigned __int64 v9; // rbx
  int v10; // eax
  int v11; // eax
  const char *v12; // r9
  int v13; // eax
  const char *v14; // r9
  int v15; // eax
  const char *v16; // r9
  int v17; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchSize; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR *p_lpFileName; // [rsp+50h] [rbp-B0h]
  char v21; // [rsp+58h] [rbp-A8h]
  WCHAR ProfileDir[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  lpFileName = 0;
  *a2 = 0;
  p_lpFileName = &lpFileName;
  v21 = 1;
  memset_0(ProfileDir, 0, 0x20Au);
  cchSize = 261;
  if ( !GetUserProfileDirectoryW(hToken, ProfileDir, &cchSize) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xDAC,
                  (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\utils.cpp",
                  v4);
    if ( lpFileName )
      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
    return LastError;
  }
  v7 = 2 * cchSize + 100;
  v8 = (WCHAR *)((__int64 (__fastcall *)(unsigned __int64))g_pLsaFunctionTable->AllocateLsaHeap)(v7);
  lpFileName = v8;
  if ( !v8 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDB8,
      (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\utils.cpp",
      (const char *)0x8007000ELL,
      v17);
    if ( lpFileName )
      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
    return LastError;
  }
  v9 = v7 >> 1;
  v10 = RtlStringCchPrintfW(v8, v9, L"%ws%ws%ws%ws%ws", L"\\\\?\\");
  if ( v10 < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0xDC2,
                  (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\utils.cpp",
                  (const char *)(unsigned int)v10,
                  (int)ProfileDir);
    if ( lpFileName )
      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
    return LastError;
  }
  if ( GetFileAttributesW(lpFileName) == -1 )
  {
    v11 = RtlStringCchPrintfW((unsigned __int16 *)lpFileName, v9, L"%ws%ws%ws", L"\\\\?\\");
    if ( v11 < 0 )
    {
      LastError = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0xDCE,
                    (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\utils.cpp",
                    (const char *)(unsigned int)v11,
                    (int)ProfileDir);
      if ( lpFileName )
        ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
      return LastError;
    }
    if ( !CreateDirectoryW(lpFileName, 0) && GetLastError() != 183 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xDCF,
                    (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\utils.cpp",
                    v12);
      if ( lpFileName )
        ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
      return LastError;
    }
    v13 = RtlStringCchCatW((unsigned __int16 *)lpFileName, v9, L"\\Windows");
    if ( v13 < 0 )
    {
      LastError = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0xDD1,
                    (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\utils.cpp",
                    (const char *)(unsigned int)v13,
                    (int)ProfileDir);
      if ( lpFileName )
        ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
      return LastError;
    }
    if ( !CreateDirectoryW(lpFileName, 0) && GetLastError() != 183 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xDD2,
                    (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\utils.cpp",
                    v14);
      if ( lpFileName )
        ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
      return LastError;
    }
    v15 = RtlStringCchCatW((unsigned __int16 *)lpFileName, v9, L"\\CloudAPCache");
    if ( v15 < 0 )
    {
      LastError = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0xDD4,
                    (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\utils.cpp",
                    (const char *)(unsigned int)v15,
                    (int)ProfileDir);
      if ( lpFileName )
        ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
      return LastError;
    }
    if ( !CreateDirectoryW(lpFileName, 0) && GetLastError() != 183 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xDD5,
                    (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\utils.cpp",
                    v16);
      if ( lpFileName )
        ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
      return LastError;
    }
  }
  *a2 = lpFileName;
  return 0;
}

```

## disassembly

```asm
0x18005c058  mov     [rsp-8+arg_10], rbx
0x18005c05d  push    rbp
0x18005c05e  push    rsi
0x18005c05f  push    rdi
0x18005c060  push    r14
0x18005c062  push    r15
0x18005c064  lea     rbp, [rsp-180h]
0x18005c06c  sub     rsp, 280h
0x18005c073  mov     rax, cs:__security_cookie
0x18005c07a  xor     rax, rsp
0x18005c07d  mov     [rbp+1A0h+var_30], rax
0x18005c084  mov     rdi, rdx
0x18005c087  mov     rbx, rcx
0x18005c08a  mov     [rsp+2A0h+lpFileName], 0
0x18005c093  mov     qword ptr [rdx], 0
0x18005c09a  lea     rax, [rsp+2A0h+lpFileName]
0x18005c09f  mov     [rsp+2A0h+var_250], rax
0x18005c0a4  mov     [rsp+2A0h+var_248], 1
0x18005c0a9  xor     edx, edx; Val
0x18005c0ab  mov     r8d, 20Ah; Size
0x18005c0b1  lea     rcx, [rsp+2A0h+ProfileDir]; void *
0x18005c0b6  call    memset_0
0x18005c0bb  mov     [rsp+2A0h+cchSize], 105h
0x18005c0c3  lea     r8, [rsp+2A0h+cchSize]; lpcchSize
0x18005c0c8  lea     rdx, [rsp+2A0h+ProfileDir]; lpProfileDir
0x18005c0cd  mov     rcx, rbx; hToken
0x18005c0d0  call    cs:__imp_GetUserProfileDirectoryW
0x18005c0d6  test    eax, eax
0x18005c0d8  jnz     short loc_18005C116
0x18005c0da  mov     rcx, [rbp+1A8h]; this
0x18005c0e1  lea     r8, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005c0e8  mov     edx, 0DACh; void *
0x18005c0ed  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005c0f2  mov     ebx, eax
0x18005c0f4  mov     rcx, [rsp+2A0h+lpFileName]
0x18005c0f9  test    rcx, rcx
0x18005c0fc  jz      short loc_18005C10F
0x18005c0fe  mov     rdx, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005c105  mov     rax, [rdx+30h]
0x18005c109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c10e  nop
0x18005c10f  mov     eax, ebx
0x18005c111  jmp     loc_18005C435
0x18005c116  mov     eax, [rsp+2A0h+cchSize]
0x18005c11a  lea     ebx, ds:64h[rax*2]
0x18005c121  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005c128  mov     ecx, ebx
0x18005c12a  mov     rax, [rax+28h]
0x18005c12e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c133  mov     [rsp+2A0h+lpFileName], rax
0x18005c138  test    rax, rax
0x18005c13b  jnz     short loc_18005C17B
0x18005c13d  mov     rcx, [rbp+1A8h]; this
0x18005c144  mov     ebx, 8007000Eh
0x18005c149  mov     r9d, ebx; char *
0x18005c14c  lea     r8, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005c153  mov     edx, 0DB8h; void *
0x18005c158  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c15d  nop
0x18005c15e  mov     rcx, [rsp+2A0h+lpFileName]
0x18005c163  test    rcx, rcx
0x18005c166  jz      short loc_18005C179
0x18005c168  mov     rdx, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005c16f  mov     rax, [rdx+30h]
0x18005c173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c178  nop
0x18005c179  jmp     short loc_18005C10F
0x18005c17b  shr     rbx, 1
0x18005c17e  lea     r15, aCloudapcache; "\\CloudAPCache"
0x18005c185  mov     [rsp+2A0h+var_268], r15
0x18005c18a  lea     r14, aWindows; "\\Windows"
0x18005c191  mov     [rsp+2A0h+var_270], r14
0x18005c196  lea     rsi, aAppdataLocalMi; "\\AppData\\Local\\Microsoft"
0x18005c19d  mov     [rsp+2A0h+var_278], rsi
0x18005c1a2  lea     rcx, [rsp+2A0h+ProfileDir]
0x18005c1a7  mov     qword ptr [rsp+2A0h+var_280], rcx; int
0x18005c1ac  lea     r9, asc_180086FE0; "\\\\?\\"
0x18005c1b3  lea     r8, aWsWsWsWsWs; "%ws%ws%ws%ws%ws"
0x18005c1ba  mov     rdx, rbx; unsigned __int64
0x18005c1bd  mov     rcx, rax; unsigned __int16 *
0x18005c1c0  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005c1c5  test    eax, eax
0x18005c1c7  jns     short loc_18005C206
0x18005c1c9  mov     rcx, [rbp+1A8h]; this
0x18005c1d0  mov     r9d, eax; char *
0x18005c1d3  lea     r8, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005c1da  mov     edx, 0DC2h; void *
0x18005c1df  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18005c1e4  mov     ebx, eax
0x18005c1e6  mov     rcx, [rsp+2A0h+lpFileName]
0x18005c1eb  test    rcx, rcx
0x18005c1ee  jz      short loc_18005C201
0x18005c1f0  mov     rdx, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005c1f7  mov     rax, [rdx+30h]
0x18005c1fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c200  nop
0x18005c201  jmp     loc_18005C10F
0x18005c206  mov     rcx, [rsp+2A0h+lpFileName]; lpFileName
0x18005c20b  call    cs:__imp_GetFileAttributesW
0x18005c211  cmp     eax, 0FFFFFFFFh
0x18005c214  jnz     loc_18005C42B
0x18005c21a  mov     [rsp+2A0h+var_278], rsi
0x18005c21f  lea     rax, [rsp+2A0h+ProfileDir]
0x18005c224  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x18005c229  lea     r9, asc_180086FE0; "\\\\?\\"
0x18005c230  lea     r8, aWsWsWs; "%ws%ws%ws"
0x18005c237  mov     rdx, rbx; unsigned __int64
0x18005c23a  mov     rcx, [rsp+2A0h+lpFileName]; unsigned __int16 *
0x18005c23f  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005c244  test    eax, eax
0x18005c246  jns     short loc_18005C285
0x18005c248  mov     rcx, [rbp+1A8h]; this
0x18005c24f  mov     r9d, eax; char *
0x18005c252  lea     r8, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005c259  mov     edx, 0DCEh; void *
0x18005c25e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18005c263  mov     ebx, eax
0x18005c265  mov     rcx, [rsp+2A0h+lpFileName]
0x18005c26a  test    rcx, rcx
0x18005c26d  jz      short loc_18005C280
0x18005c26f  mov     rdx, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005c276  mov     rax, [rdx+30h]
0x18005c27a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c27f  nop
0x18005c280  jmp     loc_18005C10F
0x18005c285  xor     edx, edx; lpSecurityAttributes
0x18005c287  mov     rcx, [rsp+2A0h+lpFileName]; lpPathName
0x18005c28c  call    cs:__imp_CreateDirectoryW
0x18005c292  mov     esi, 0B7h
0x18005c297  test    eax, eax
0x18005c299  jnz     short loc_18005C2DF
0x18005c29b  call    cs:__imp_GetLastError
0x18005c2a1  cmp     eax, esi
0x18005c2a3  jz      short loc_18005C2DF
0x18005c2a5  mov     rcx, [rbp+1A8h]; this
0x18005c2ac  lea     r8, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005c2b3  mov     edx, 0DCFh; void *
0x18005c2b8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005c2bd  mov     ebx, eax
0x18005c2bf  mov     rcx, [rsp+2A0h+lpFileName]
0x18005c2c4  test    rcx, rcx
0x18005c2c7  jz      short loc_18005C2DA
0x18005c2c9  mov     rdx, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005c2d0  mov     rax, [rdx+30h]
0x18005c2d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c2d9  nop
0x18005c2da  jmp     loc_18005C10F
0x18005c2df  mov     r8, r14; unsigned __int16 *
0x18005c2e2  mov     rdx, rbx; unsigned __int64
0x18005c2e5  mov     rcx, [rsp+2A0h+lpFileName]; unsigned __int16 *
0x18005c2ea  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005c2ef  test    eax, eax
0x18005c2f1  jns     short loc_18005C330
0x18005c2f3  mov     rcx, [rbp+1A8h]; this
0x18005c2fa  mov     r9d, eax; char *
0x18005c2fd  lea     r8, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005c304  mov     edx, 0DD1h; void *
0x18005c309  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18005c30e  mov     ebx, eax
0x18005c310  mov     rcx, [rsp+2A0h+lpFileName]
0x18005c315  test    rcx, rcx
0x18005c318  jz      short loc_18005C32B
0x18005c31a  mov     rdx, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005c321  mov     rax, [rdx+30h]
0x18005c325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c32a  nop
0x18005c32b  jmp     loc_18005C10F
0x18005c330  xor     edx, edx; lpSecurityAttributes
0x18005c332  mov     rcx, [rsp+2A0h+lpFileName]; lpPathName
0x18005c337  call    cs:__imp_CreateDirectoryW
0x18005c33d  test    eax, eax
0x18005c33f  jnz     short loc_18005C385
0x18005c341  call    cs:__imp_GetLastError
0x18005c347  cmp     eax, esi
0x18005c349  jz      short loc_18005C385
0x18005c34b  mov     rcx, [rbp+1A8h]; this
0x18005c352  lea     r8, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005c359  mov     edx, 0DD2h; void *
0x18005c35e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005c363  mov     ebx, eax
0x18005c365  mov     rcx, [rsp+2A0h+lpFileName]
0x18005c36a  test    rcx, rcx
0x18005c36d  jz      short loc_18005C380
0x18005c36f  mov     rdx, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005c376  mov     rax, [rdx+30h]
0x18005c37a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c37f  nop
0x18005c380  jmp     loc_18005C10F
0x18005c385  mov     r8, r15; unsigned __int16 *
0x18005c388  mov     rdx, rbx; unsigned __int64
0x18005c38b  mov     rcx, [rsp+2A0h+lpFileName]; unsigned __int16 *
0x18005c390  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005c395  test    eax, eax
0x18005c397  jns     short loc_18005C3D6
0x18005c399  mov     rcx, [rbp+1A8h]; this
0x18005c3a0  mov     r9d, eax; char *
0x18005c3a3  lea     r8, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005c3aa  mov     edx, 0DD4h; void *
0x18005c3af  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18005c3b4  mov     ebx, eax
0x18005c3b6  mov     rcx, [rsp+2A0h+lpFileName]
0x18005c3bb  test    rcx, rcx
0x18005c3be  jz      short loc_18005C3D1
0x18005c3c0  mov     rdx, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005c3c7  mov     rax, [rdx+30h]
0x18005c3cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c3d0  nop
0x18005c3d1  jmp     loc_18005C10F
0x18005c3d6  xor     edx, edx; lpSecurityAttributes
0x18005c3d8  mov     rcx, [rsp+2A0h+lpFileName]; lpPathName
0x18005c3dd  call    cs:__imp_CreateDirectoryW
0x18005c3e3  test    eax, eax
0x18005c3e5  jnz     short loc_18005C42B
0x18005c3e7  call    cs:__imp_GetLastError
0x18005c3ed  cmp     eax, esi
0x18005c3ef  jz      short loc_18005C42B
0x18005c3f1  mov     rcx, [rbp+1A8h]; this
0x18005c3f8  lea     r8, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18005c3ff  mov     edx, 0DD5h; void *
0x18005c404  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005c409  mov     ebx, eax
0x18005c40b  mov     rcx, [rsp+2A0h+lpFileName]
0x18005c410  test    rcx, rcx
0x18005c413  jz      short loc_18005C426
0x18005c415  mov     rdx, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005c41c  mov     rax, [rdx+30h]
0x18005c420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c425  nop
0x18005c426  jmp     loc_18005C10F
0x18005c42b  mov     rax, [rsp+2A0h+lpFileName]
0x18005c430  mov     [rdi], rax
0x18005c433  xor     eax, eax
0x18005c435  mov     rcx, [rbp+1A0h+var_30]
0x18005c43c  xor     rcx, rsp; StackCookie
0x18005c43f  call    __security_check_cookie
0x18005c444  mov     rbx, [rsp+2A0h+arg_10]
0x18005c44c  add     rsp, 280h
0x18005c453  pop     r15
0x18005c455  pop     r14
0x18005c457  pop     rdi
0x18005c458  pop     rsi
0x18005c459  pop     rbp
0x18005c45a  retn
```
