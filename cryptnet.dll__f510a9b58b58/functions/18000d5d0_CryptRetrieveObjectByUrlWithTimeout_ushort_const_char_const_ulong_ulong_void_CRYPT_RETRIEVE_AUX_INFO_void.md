# CryptRetrieveObjectByUrlWithTimeout(ushort const *,char const *,ulong,ulong,void * *,_CRYPT_RETRIEVE_AUX_INFO *,void *)

- ea: `0x18000d5d0`
- end: `0x18000da9d`
- name: `?CryptRetrieveObjectByUrlWithTimeout@@YAHPEBGPEBDKKPEAPEAXPEAU_CRYPT_RETRIEVE_AUX_INFO@@PEAX@Z`
- size: `1229`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, const char *, int, DWORD, void **, struct _CRYPT_RETRIEVE_AUX_INFO *, const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000b090`

## callees

- `0x18000a990`
- `0x18000bb78`
- `0x18000d5d0`
- `0x180016ab0`
- `0x180017460`
- `0x180018f78`
- `0x180026552`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d66a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d694`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d6fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d66a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d694`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d6fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d670`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d670`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da55`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000d8a1`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000d8a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000d877`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000d877`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000d88f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000d88f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000d864`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000d864`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000d97a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000d97a`
- `CRYPT32!I_CertDiagControl` at `0x18000d74c`
- `CRYPT32!I_CertDiagControl` at `0x18000d949`
- `CRYPT32!I_CertDiagControl` at `0x18000da35`
- `CRYPT32!I_CertDiagControl` at `0x18000d74c`
- `CRYPT32!I_CertDiagControl` at `0x18000d949`
- `CRYPT32!I_CertDiagControl` at `0x18000da35`
- `CRYPT32!CryptMemFree` at `0x18000da7c`
- `CRYPT32!CryptMemFree` at `0x18000da87`
- `CRYPT32!CryptMemFree` at `0x18000da92`
- `CRYPT32!CryptMemFree` at `0x18000da7c`
- `CRYPT32!CryptMemFree` at `0x18000da87`
- `CRYPT32!CryptMemFree` at `0x18000da92`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d8d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d8d2`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000d816`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000d816`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000d8c5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000d8c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d901`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d9fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d901`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d9fa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000da71`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000da71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d76e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d8ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d98c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d9a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d76e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d8ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d98c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d9a6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d64b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d64b`

## string_xrefs

- `0x18000d6bb`: `CRYPTNET.DLL --> Url retrieval timeout: %d  error: %d (0x%x) for::\n  %S\n`
- `0x18000d9db`: `CRYPTNET.DLL --> CryptRetrieveObjectByUrl, %d timeout for : %S\n`
- `0x18000da5e`: `CRYPTNET.DLL --> SetThreadToken failed: %d (0x%x)\n`

## pseudocode

```c
__int64 __fastcall CryptRetrieveObjectByUrlWithTimeout(
        const unsigned __int16 *Src,
        const char *a2,
        int a3,
        DWORD a4,
        void **a5,
        struct _CRYPT_RETRIEVE_AUX_INFO *a6,
        const wchar_t *a7)
{
  __int64 v7; // rax
  unsigned int v9; // r14d
  __int64 v10; // rcx
  struct _CRYPT_RETRIEVE_AUX_INFO *v11; // r15
  __int64 v12; // rsi
  _QWORD *v13; // rax
  void **v14; // r13
  _QWORD *v15; // rdi
  const wchar_t *v16; // r12
  DWORD v17; // ecx
  DWORD LastError; // r14d
  unsigned int v19; // esi
  DWORD v20; // r12d
  LPWSTR pwszCacheFileNamePrefix; // rax
  _QWORD *v24; // rcx
  void *v25; // rcx
  HMODULE v26; // rcx
  void *v27; // rcx
  void *v28; // rcx
  void *v29; // rcx
  size_t v30; // rsi
  DWORD v31; // esi
  unsigned __int16 *v32; // rdx
  HANDLE EventA; // rax
  HANDLE CurrentThread; // rax
  void *v35; // rcx
  struct _CROBU_ENTRY *v36; // rax
  const wchar_t *v37; // r8
  int v38; // edx
  DWORD v39; // eax
  HANDLE hThread; // [rsp+30h] [rbp-51h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-49h] BYREF
  const wchar_t *v42; // [rsp+40h] [rbp-41h] BYREF
  int v43; // [rsp+48h] [rbp-39h]
  int v44; // [rsp+4Ch] [rbp-35h]
  __int128 v45; // [rsp+50h] [rbp-31h]
  __int128 v46; // [rsp+60h] [rbp-21h]
  _QWORD *v47; // [rsp+70h] [rbp-11h]
  DWORD ThreadId; // [rsp+D0h] [rbp+4Fh] BYREF
  const char *v49; // [rsp+D8h] [rbp+57h]
  int v50; // [rsp+E0h] [rbp+5Fh]
  DWORD dwMilliseconds; // [rsp+E8h] [rbp+67h]

  dwMilliseconds = a4;
  v50 = a3;
  v49 = a2;
  LODWORD(v7) = 0;
  hThread = 0;
  v9 = 0;
  TokenHandle = 0;
  v10 = -1;
  ThreadId = 0;
  if ( Src )
  {
    v7 = -1;
    do
      ++v7;
    while ( Src[v7] );
  }
  v11 = a6;
  v12 = (unsigned int)(v7 + 1);
  if ( a6 )
  {
    if ( a6->cbSize > 0x30 )
    {
      pwszCacheFileNamePrefix = a6->pwszCacheFileNamePrefix;
      if ( pwszCacheFileNamePrefix )
      {
        while ( pwszCacheFileNamePrefix[++v10] != 0 )
          ;
        v9 = v10 + 1;
      }
    }
  }
  v13 = LocalAlloc(0x40u, 2LL * ((unsigned int)v12 + v9) + 288);
  v14 = a5;
  v15 = v13;
  v16 = a7;
  if ( !v13 )
  {
    v17 = -2147024882;
LABEL_7:
    SetLastError(v17);
LABEL_8:
    LastError = GetLastError();
    v19 = 0;
    goto LABEL_9;
  }
  v30 = 2 * v12;
  *v13 = v13 + 36;
  memcpy_0(v13 + 36, Src, v30);
  if ( v9 )
  {
    v35 = (void *)(v30 + *v15);
    v15[1] = v35;
    memcpy_0(v35, v11->pwszCacheFileNamePrefix, 2LL * v9);
  }
  v31 = dwMilliseconds;
  v32 = (unsigned __int16 *)v15[1];
  v15[2] = v49;
  *((_DWORD *)v15 + 6) = v50;
  *((_DWORD *)v15 + 7) = v31;
  CryptRetrieveSetAuxInfo(v11, v32, (struct _CROBU_ENTRY *)v15);
  v15[34] = v16;
  EventA = CreateEventA(0, 0, 0, 0);
  v15[30] = EventA;
  if ( !EventA )
    goto LABEL_8;
  v15[29] = DuplicateLibrary();
  *((_DWORD *)v15 + 62) = 1;
  hThread = CreateThread(0, 0x8000u, CryptRetrieveObjectByUrlWithTimeoutThreadProc, v15, 4u, &ThreadId);
  if ( !hThread )
    goto LABEL_8;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    if ( !SetThreadToken(&hThread, TokenHandle) )
    {
      v39 = GetLastError();
      I_CryptNetDebugErrorPrintfA("CRYPTNET.DLL --> SetThreadToken failed: %d (0x%x)\n", v39, v39);
    }
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  ResumeThread(hThread);
  CloseHandle(hThread);
  hThread = 0;
  WaitForSingleObjectEx((HANDLE)v15[30], v31, 0);
  EnterCriticalSection(&CrobuCriticalSection);
  if ( *((_DWORD *)v15 + 62) != 2 )
  {
    CloseHandle((HANDLE)v15[30]);
    v36 = pCrobuPendingHead;
    v15[30] = 0;
    *((_DWORD *)v15 + 62) = 3;
    v15[34] = 0;
    if ( v36 )
    {
      *((_QWORD *)v36 + 33) = v15;
      v15[32] = v36;
    }
    v37 = (const wchar_t *)*v15;
    v38 = *((_DWORD *)v15 + 7);
    pCrobuPendingHead = (struct _CROBU_ENTRY *)v15;
    I_CryptNetDebugErrorPrintfA("CRYPTNET.DLL --> CryptRetrieveObjectByUrl, %d timeout for : %S\n", v38, v37);
    v15 = 0;
    LeaveCriticalSection(&CrobuCriticalSection);
    v43 = 1460;
    v42 = L"NetworkRetrievalTimeout";
    v44 = 3;
    v45 = 0;
    v46 = 0;
    I_CertDiagControl(11, &v42, 0);
    v17 = 1460;
    goto LABEL_7;
  }
  v19 = *((_DWORD *)v15 + 56);
  LastError = *((_DWORD *)v15 + 57);
  *v14 = (void *)v15[4];
  LeaveCriticalSection(&CrobuCriticalSection);
  if ( *((_DWORD *)v15 + 70) )
  {
    v43 = 0;
    v42 = L"NetworkRetrievalHasNestedEvents";
    v44 = 3;
    v45 = 0;
    v46 = 0;
    I_CertDiagControl(11, &v42, 0);
  }
LABEL_9:
  if ( v16 )
  {
    SetLastError(LastError);
    v42 = v16;
    v20 = dwMilliseconds;
    v24 = v15 + 5;
    v44 = 0;
    *((_QWORD *)&v45 + 1) = v49;
    LODWORD(v46) = v50;
    *((_QWORD *)&v46 + 1) = *v14;
    v43 = v19;
    *(_QWORD *)&v45 = Src;
    if ( !v15 )
      v24 = 0;
    DWORD1(v46) = dwMilliseconds;
    v47 = v24;
    I_CertDiagControl(8, &v42, 0);
  }
  else
  {
    v20 = dwMilliseconds;
  }
  if ( !v19 )
    I_CryptNetDebugErrorPrintfA(
      "CRYPTNET.DLL --> Url retrieval timeout: %d  error: %d (0x%x) for::\n  %S\n",
      v20,
      LastError,
      LastError,
      Src);
  if ( v15 )
  {
    CryptRetrieveGetAuxInfo((struct _CROBU_ENTRY *)v15, v11);
    v25 = (void *)v15[30];
    if ( v25 )
      CloseHandle(v25);
    v26 = (HMODULE)v15[29];
    if ( v26 )
      FreeLibrary(v26);
    v27 = (void *)v15[24];
    if ( v27 )
      CryptMemFree(v27);
    v28 = (void *)v15[25];
    if ( v28 )
      CryptMemFree(v28);
    v29 = (void *)v15[26];
    if ( v29 )
      CryptMemFree(v29);
    operator delete(v15);
  }
  SetLastError(LastError);
  return v19;
}

```

## disassembly

```asm
0x18000d5d0  mov     [rsp-8+dwMilliseconds], r9d
0x18000d5d5  mov     [rsp-8+arg_10], r8d
0x18000d5da  mov     [rsp-8+arg_8], rdx
0x18000d5df  push    rbp
0x18000d5e0  push    rbx
0x18000d5e1  push    rsi
0x18000d5e2  push    rdi
0x18000d5e3  push    r12
0x18000d5e5  push    r13
0x18000d5e7  push    r14
0x18000d5e9  push    r15
0x18000d5eb  lea     rbp, [rsp-7]
0x18000d5f0  sub     rsp, 88h
0x18000d5f7  xor     eax, eax
0x18000d5f9  mov     rbx, rcx
0x18000d5fc  mov     [rbp+3Fh+hThread], rax
0x18000d600  mov     r14d, eax
0x18000d603  mov     [rbp+3Fh+TokenHandle], rax
0x18000d607  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000d60e  mov     [rbp+3Fh+ThreadId], eax
0x18000d611  test    rbx, rbx
0x18000d614  jz      short loc_18000D62A
0x18000d616  mov     rax, rcx
0x18000d619  nop     dword ptr [rax+00000000h]
0x18000d620  inc     rax
0x18000d623  cmp     [rbx+rax*2], r14w
0x18000d628  jnz     short loc_18000D620
0x18000d62a  mov     r15, [rbp+3Fh+arg_28]
0x18000d62e  lea     esi, [rax+1]
0x18000d631  test    r15, r15
0x18000d634  jnz     loc_18000D6CC
0x18000d63a  lea     eax, [rsi+r14]
0x18000d63e  mov     ecx, 40h ; '@'; uFlags
0x18000d643  lea     rdx, ds:120h[rax*2]; uBytes
0x18000d64b  call    cs:__imp_LocalAlloc
0x18000d651  mov     r13, [rbp+3Fh+arg_20]
0x18000d655  mov     rdi, rax
0x18000d658  mov     r12, [rbp+3Fh+arg_30]
0x18000d65c  test    rax, rax
0x18000d65f  jnz     loc_18000D7C1
0x18000d665  mov     ecx, 8007000Eh; dwErrCode
0x18000d66a  call    cs:__imp_SetLastError
0x18000d670  call    cs:__imp_GetLastError
0x18000d676  mov     r14d, eax
0x18000d679  xor     esi, esi
0x18000d67b  test    r12, r12
0x18000d67e  jnz     short loc_18000D6F8
0x18000d680  mov     r12d, [rbp+3Fh+dwMilliseconds]
0x18000d684  test    esi, esi
0x18000d686  jz      short loc_18000D6B0
0x18000d688  test    rdi, rdi
0x18000d68b  jnz     loc_18000D757
0x18000d691  mov     ecx, r14d; dwErrCode
0x18000d694  call    cs:__imp_SetLastError
0x18000d69a  mov     eax, esi
0x18000d69c  add     rsp, 88h
0x18000d6a3  pop     r15
0x18000d6a5  pop     r14
0x18000d6a7  pop     r13
0x18000d6a9  pop     r12
0x18000d6ab  pop     rdi
0x18000d6ac  pop     rsi
0x18000d6ad  pop     rbx
0x18000d6ae  pop     rbp
0x18000d6af  retn
0x18000d6b0  mov     r9d, r14d
0x18000d6b3  mov     qword ptr [rsp+0C0h+dwCreationFlags], rbx
0x18000d6b8  mov     r8d, r14d
0x18000d6bb  lea     rcx, aCryptnetDllUrl; "CRYPTNET.DLL --> Url retrieval timeout:"...
0x18000d6c2  mov     edx, r12d
0x18000d6c5  call    ?I_CryptNetDebugErrorPrintfA@@YAXPEBDZZ; I_CryptNetDebugErrorPrintfA(char const *,...)
0x18000d6ca  jmp     short loc_18000D688
0x18000d6cc  cmp     dword ptr [r15], 30h ; '0'
0x18000d6d0  jbe     loc_18000D63A
0x18000d6d6  mov     rax, [r15+30h]
0x18000d6da  test    rax, rax
0x18000d6dd  jz      loc_18000D63A
0x18000d6e3  cmp     [rax+rcx*2+2], r14w
0x18000d6e9  lea     rcx, [rcx+1]
0x18000d6ed  jnz     short loc_18000D6E3
0x18000d6ef  lea     r14d, [rcx+1]
0x18000d6f3  jmp     loc_18000D63A
0x18000d6f8  mov     ecx, r14d; dwErrCode
0x18000d6fb  call    cs:__imp_SetLastError
0x18000d701  xor     eax, eax
0x18000d703  mov     [rbp+3Fh+var_80], r12
0x18000d707  mov     r12d, [rbp+3Fh+dwMilliseconds]
0x18000d70b  lea     rcx, [rdi+28h]
0x18000d70f  mov     [rbp+3Fh+var_74], eax
0x18000d712  lea     rdx, [rbp+3Fh+var_80]
0x18000d716  mov     rax, [rbp+3Fh+arg_8]
0x18000d71a  mov     qword ptr [rbp+3Fh+var_70+8], rax
0x18000d71e  mov     eax, [rbp+3Fh+arg_10]
0x18000d721  mov     dword ptr [rbp+3Fh+var_60], eax
0x18000d724  mov     rax, [r13+0]
0x18000d728  mov     qword ptr [rbp+3Fh+var_60+8], rax
0x18000d72c  xor     eax, eax
0x18000d72e  test    rdi, rdi
0x18000d731  mov     [rbp+3Fh+var_78], esi
0x18000d734  mov     qword ptr [rbp+3Fh+var_70], rbx
0x18000d738  cmovz   rcx, rax
0x18000d73c  mov     dword ptr [rbp+3Fh+var_60+4], r12d
0x18000d740  mov     [rbp+3Fh+var_50], rcx
0x18000d744  xor     r8d, r8d
0x18000d747  mov     ecx, 8
0x18000d74c  call    cs:__imp_I_CertDiagControl
0x18000d752  jmp     loc_18000D684
0x18000d757  mov     rdx, r15; struct _CRYPT_RETRIEVE_AUX_INFO *
0x18000d75a  mov     rcx, rdi; struct _CROBU_ENTRY *
0x18000d75d  call    ?CryptRetrieveGetAuxInfo@@YAXPEAU_CROBU_ENTRY@@PEAU_CRYPT_RETRIEVE_AUX_INFO@@@Z; CryptRetrieveGetAuxInfo(_CROBU_ENTRY *,_CRYPT_RETRIEVE_AUX_INFO *)
0x18000d762  mov     rcx, [rdi+0F0h]; hObject
0x18000d769  test    rcx, rcx
0x18000d76c  jz      short loc_18000D774
0x18000d76e  call    cs:__imp_CloseHandle
0x18000d774  mov     rcx, [rdi+0E8h]; hLibModule
0x18000d77b  test    rcx, rcx
0x18000d77e  jnz     loc_18000DA71
0x18000d784  mov     rcx, [rdi+0C0h]; pv
0x18000d78b  test    rcx, rcx
0x18000d78e  jnz     loc_18000DA7C
0x18000d794  mov     rcx, [rdi+0C8h]; pv
0x18000d79b  test    rcx, rcx
0x18000d79e  jnz     loc_18000DA87
0x18000d7a4  mov     rcx, [rdi+0D0h]; pv
0x18000d7ab  test    rcx, rcx
0x18000d7ae  jnz     loc_18000DA92
0x18000d7b4  mov     rcx, rdi; hMem
0x18000d7b7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d7bc  jmp     loc_18000D691
0x18000d7c1  lea     rcx, [rax+120h]; void *
0x18000d7c8  add     rsi, rsi
0x18000d7cb  mov     r8, rsi; Size
0x18000d7ce  mov     [rax], rcx
0x18000d7d1  mov     rdx, rbx; Src
0x18000d7d4  call    memcpy_0
0x18000d7d9  test    r14d, r14d
0x18000d7dc  jnz     loc_18000D954
0x18000d7e2  mov     rax, [rbp+3Fh+arg_8]
0x18000d7e6  mov     r8, rdi; struct _CROBU_ENTRY *
0x18000d7e9  mov     esi, [rbp+3Fh+dwMilliseconds]
0x18000d7ec  mov     rcx, r15; struct _CRYPT_RETRIEVE_AUX_INFO *
0x18000d7ef  mov     rdx, [rdi+8]; unsigned __int16 *
0x18000d7f3  mov     [rdi+10h], rax
0x18000d7f7  mov     eax, [rbp+3Fh+arg_10]
0x18000d7fa  mov     [rdi+18h], eax
0x18000d7fd  mov     [rdi+1Ch], esi
0x18000d800  call    ?CryptRetrieveSetAuxInfo@@YAXPEAU_CRYPT_RETRIEVE_AUX_INFO@@PEAGPEAU_CROBU_ENTRY@@@Z; CryptRetrieveSetAuxInfo(_CRYPT_RETRIEVE_AUX_INFO *,ushort *,_CROBU_ENTRY *)
0x18000d805  xor     edx, edx; bManualReset
0x18000d807  mov     [rdi+110h], r12
0x18000d80e  xor     ecx, ecx; lpEventAttributes
0x18000d810  xor     r9d, r9d; lpName
0x18000d813  xor     r8d, r8d; bInitialState
0x18000d816  call    cs:__imp_CreateEventA
0x18000d81c  mov     [rdi+0F0h], rax
0x18000d823  test    rax, rax
0x18000d826  jz      loc_18000D670
0x18000d82c  call    DuplicateLibrary
0x18000d831  mov     [rdi+0E8h], rax
0x18000d838  lea     r8, ?CryptRetrieveObjectByUrlWithTimeoutThreadProc@@YAKPEAX@Z; lpStartAddress
0x18000d83f  lea     rax, [rbp+3Fh+ThreadId]
0x18000d843  mov     dword ptr [rdi+0F8h], 1
0x18000d84d  mov     [rsp+0C0h+lpThreadId], rax; lpThreadId
0x18000d852  mov     r9, rdi; lpParameter
0x18000d855  mov     edx, 8000h; dwStackSize
0x18000d85a  mov     [rsp+0C0h+dwCreationFlags], 4; dwCreationFlags
0x18000d862  xor     ecx, ecx; lpThreadAttributes
0x18000d864  call    cs:__imp_CreateThread
0x18000d86a  mov     [rbp+3Fh+hThread], rax
0x18000d86e  test    rax, rax
0x18000d871  jz      loc_18000D670
0x18000d877  call    cs:__imp_GetCurrentThread
0x18000d87d  lea     r9, [rbp+3Fh+TokenHandle]; TokenHandle
0x18000d881  mov     edx, 0Ch; DesiredAccess
0x18000d886  mov     rcx, rax; ThreadHandle
0x18000d889  mov     r8d, 1; OpenAsSelf
0x18000d88f  call    cs:__imp_OpenThreadToken
0x18000d895  test    eax, eax
0x18000d897  jnz     loc_18000D972
0x18000d89d  mov     rcx, [rbp+3Fh+hThread]; hThread
0x18000d8a1  call    cs:__imp_ResumeThread
0x18000d8a7  mov     rcx, [rbp+3Fh+hThread]; hObject
0x18000d8ab  call    cs:__imp_CloseHandle
0x18000d8b1  mov     [rbp+3Fh+hThread], 0
0x18000d8b9  xor     r8d, r8d; bAlertable
0x18000d8bc  mov     rcx, [rdi+0F0h]; hHandle
0x18000d8c3  mov     edx, esi; dwMilliseconds
0x18000d8c5  call    cs:__imp_WaitForSingleObjectEx
0x18000d8cb  lea     rcx, ?CrobuCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d8d2  call    cs:__imp_EnterCriticalSection
0x18000d8d8  cmp     dword ptr [rdi+0F8h], 2
0x18000d8df  jnz     loc_18000D99F
0x18000d8e5  mov     rax, [rdi+20h]
0x18000d8e9  lea     rcx, ?CrobuCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d8f0  mov     esi, [rdi+0E0h]
0x18000d8f6  mov     r14d, [rdi+0E4h]
0x18000d8fd  mov     [r13+0], rax
0x18000d901  call    cs:__imp_LeaveCriticalSection
0x18000d907  cmp     dword ptr [rdi+118h], 0
0x18000d90e  jz      loc_18000D67B
0x18000d914  lea     rax, aNetworkretriev; "NetworkRetrievalHasNestedEvents"
0x18000d91b  mov     [rbp+3Fh+var_78], 0
0x18000d922  xorps   xmm0, xmm0
0x18000d925  mov     [rbp+3Fh+var_80], rax
0x18000d929  xorps   xmm1, xmm1
0x18000d92c  mov     [rbp+3Fh+var_74], 3
0x18000d933  xor     r8d, r8d
0x18000d936  lea     rdx, [rbp+3Fh+var_80]
0x18000d93a  mov     ecx, 0Bh
0x18000d93f  movdqu  [rbp+3Fh+var_70], xmm0
0x18000d944  movdqu  [rbp+3Fh+var_60], xmm1
0x18000d949  call    cs:__imp_I_CertDiagControl
0x18000d94f  jmp     loc_18000D67B
0x18000d954  mov     rcx, [rdi]
0x18000d957  add     rcx, rsi; void *
0x18000d95a  mov     r8d, r14d
0x18000d95d  mov     [rdi+8], rcx
0x18000d961  add     r8, r8; Size
0x18000d964  mov     rdx, [r15+30h]; Src
0x18000d968  call    memcpy_0
0x18000d96d  jmp     loc_18000D7E2
0x18000d972  mov     rdx, [rbp+3Fh+TokenHandle]; Token
0x18000d976  lea     rcx, [rbp+3Fh+hThread]; Thread
0x18000d97a  call    cs:__imp_SetThreadToken
0x18000d980  test    eax, eax
0x18000d982  jz      loc_18000DA55
0x18000d988  mov     rcx, [rbp+3Fh+TokenHandle]; hObject
0x18000d98c  call    cs:__imp_CloseHandle
0x18000d992  mov     [rbp+3Fh+TokenHandle], 0
0x18000d99a  jmp     loc_18000D89D
0x18000d99f  mov     rcx, [rdi+0F0h]; hObject
0x18000d9a6  call    cs:__imp_CloseHandle
0x18000d9ac  mov     rax, cs:?pCrobuPendingHead@@3PEAU_CROBU_ENTRY@@EA; _CROBU_ENTRY * pCrobuPendingHead
0x18000d9b3  mov     qword ptr [rdi+0F0h], 0
0x18000d9be  mov     dword ptr [rdi+0F8h], 3
0x18000d9c8  mov     qword ptr [rdi+110h], 0
0x18000d9d3  test    rax, rax
0x18000d9d6  jnz     short loc_18000DA45
0x18000d9d8  mov     r8, [rdi]
0x18000d9db  lea     rcx, aCryptnetDllCry_0; "CRYPTNET.DLL --> CryptRetrieveObjectByU"...
0x18000d9e2  mov     edx, [rdi+1Ch]
0x18000d9e5  mov     cs:?pCrobuPendingHead@@3PEAU_CROBU_ENTRY@@EA, rdi; _CROBU_ENTRY * pCrobuPendingHead
0x18000d9ec  call    ?I_CryptNetDebugErrorPrintfA@@YAXPEBDZZ; I_CryptNetDebugErrorPrintfA(char const *,...)
0x18000d9f1  lea     rcx, ?CrobuCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d9f8  xor     edi, edi
0x18000d9fa  call    cs:__imp_LeaveCriticalSection
0x18000da00  lea     rax, aNetworkretriev_0; "NetworkRetrievalTimeout"
0x18000da07  mov     [rbp+3Fh+var_78], 5B4h
0x18000da0e  xorps   xmm0, xmm0
0x18000da11  mov     [rbp+3Fh+var_80], rax
0x18000da15  xorps   xmm1, xmm1
0x18000da18  mov     [rbp+3Fh+var_74], 3
0x18000da1f  xor     r8d, r8d
0x18000da22  lea     rdx, [rbp+3Fh+var_80]
0x18000da26  mov     ecx, 0Bh
0x18000da2b  movdqu  [rbp+3Fh+var_70], xmm0
0x18000da30  movdqu  [rbp+3Fh+var_60], xmm1
0x18000da35  call    cs:__imp_I_CertDiagControl
0x18000da3b  mov     ecx, 5B4h
0x18000da40  jmp     loc_18000D66A
0x18000da45  mov     [rax+108h], rdi
0x18000da4c  mov     [rdi+100h], rax
0x18000da53  jmp     short loc_18000D9D8
0x18000da55  call    cs:__imp_GetLastError
0x18000da5b  mov     r8d, eax
0x18000da5e  lea     rcx, aCryptnetDllSet; "CRYPTNET.DLL --> SetThreadToken failed:"...
0x18000da65  mov     edx, eax
0x18000da67  call    ?I_CryptNetDebugErrorPrintfA@@YAXPEBDZZ; I_CryptNetDebugErrorPrintfA(char const *,...)
0x18000da6c  jmp     loc_18000D988
0x18000da71  call    cs:__imp_FreeLibrary
0x18000da77  jmp     loc_18000D784
0x18000da7c  call    cs:__imp_CryptMemFree
0x18000da82  jmp     loc_18000D794
0x18000da87  call    cs:__imp_CryptMemFree
0x18000da8d  jmp     loc_18000D7A4
0x18000da92  call    cs:__imp_CryptMemFree
0x18000da98  jmp     loc_18000D7B4
```
