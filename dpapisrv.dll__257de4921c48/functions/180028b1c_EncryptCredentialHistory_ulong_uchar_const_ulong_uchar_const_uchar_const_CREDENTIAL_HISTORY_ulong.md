# EncryptCredentialHistory(ulong,uchar * const,ulong,uchar * const,uchar * const,_CREDENTIAL_HISTORY * *,ulong *)

- ea: `0x180028b1c`
- end: `0x180028f06`
- name: `?EncryptCredentialHistory@@YAKKQEAEK00PEAPEAU_CREDENTIAL_HISTORY@@PEAK@Z`
- size: `1002`
- prototype: `__int64 __fastcall(char, unsigned __int8 *const, __int64, unsigned __int8 *const, unsigned __int8 *const, struct _CREDENTIAL_HISTORY **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800285dc`

## callees

- `0x180002480`
- `0x1800029d0`
- `0x180003080`
- `0x180007f10`
- `0x18000b638`
- `0x18001d810`
- `0x180028b1c`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180028c20`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180028c92`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180028c20`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180028c92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ba4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028be5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ba4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028be5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180028b94`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180028b94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180028b77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180028b77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028ea6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028ed0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028ea6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028ed0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028c38`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028c38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028ebc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028ebc`
- `bcrypt!BCryptEncrypt` at `0x180028e4e`
- `bcrypt!BCryptEncrypt` at `0x180028e4e`
- `bcrypt!BCryptGenRandom` at `0x180028cc1`
- `bcrypt!BCryptGenRandom` at `0x180028cc1`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180028dbc`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180028dbc`
- `bcrypt!BCryptDestroyKey` at `0x180028e61`
- `bcrypt!BCryptDestroyKey` at `0x180028e61`
- `ntdll!RtlNtStatusToDosError` at `0x180028cf0`
- `ntdll!RtlNtStatusToDosError` at `0x180028cf0`

## string_xrefs

- `0x180028bc1`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`
- `0x180028bf7`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`
- `0x180028cd9`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`
- `0x180028d4f`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`

## pseudocode

```c
__int64 __fastcall EncryptCredentialHistory(
        char a1,
        unsigned __int8 *const a2,
        __int64 a3,
        unsigned __int8 *const a4,
        unsigned __int8 *const a5,
        struct _CREDENTIAL_HISTORY **a6,
        unsigned int *a7)
{
  PSID v7; // rsi
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  __int64 v11; // rcx
  __int64 v12; // r9
  DWORD v13; // r15d
  char *v14; // rax
  char *v15; // rdi
  unsigned int IterationCount; // eax
  DWORD LengthSid; // eax
  int v18; // ebx
  __int64 v19; // r9
  __int64 v20; // r9
  __int64 v21; // r9
  void *BCryptProviderHandle; // rax
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  UCHAR *v25; // rax
  __int64 v26; // rcx
  PSID pSid; // [rsp+50h] [rbp-B0h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+58h] [rbp-A8h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int8 *v31; // [rsp+68h] [rbp-98h]
  unsigned __int8 *v32; // [rsp+70h] [rbp-90h]
  UCHAR pbIV[16]; // [rsp+78h] [rbp-88h] BYREF
  UCHAR pbInput[16]; // [rsp+88h] [rbp-78h] BYREF
  int v35; // [rsp+98h] [rbp-68h]
  __int128 v36; // [rsp+9Ch] [rbp-64h]
  int v37; // [rsp+ACh] [rbp-54h]
  UCHAR pbSecret[32]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v39; // [rsp+E0h] [rbp-20h]

  v7 = 0;
  v32 = a5;
  pSid = 0;
  v31 = a4;
  phKey = a2;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  LastError = 8;
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    v11 = LastError;
    v12 = 1243;
LABEL_3:
    DebugTraceError(v11, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp", v12);
    goto LABEL_29;
  }
  if ( !(unsigned int)GetTokenUserSid(TokenHandle, &pSid) )
  {
    LastError = GetLastError();
    DebugTraceError(LastError, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp", 1250);
    v7 = pSid;
    goto LABEL_29;
  }
  v7 = pSid;
  v13 = GetLengthSid(pSid) + 116;
  v14 = (char *)LocalAlloc(0x40u, v13);
  v15 = v14;
  if ( !v14 )
  {
    v12 = 1269;
    v11 = 8;
    goto LABEL_3;
  }
  *((_DWORD *)v14 + 6) = 1;
  *((_DWORD *)v14 + 7) = 32782;
  if ( (a1 & 1) != 0 )
    IterationCount = 1;
  else
    IterationCount = GetIterationCount(0x800Eu);
  *((_DWORD *)v15 + 8) = IterationCount;
  *((_DWORD *)v15 + 10) = 26128;
  *((_DWORD *)v15 + 11) = 20;
  *((_DWORD *)v15 + 12) = 20;
  LengthSid = GetLengthSid(v7);
  *((_DWORD *)v15 + 9) = LengthSid;
  memcpy_0(v15 + 68, v7, LengthSid);
  v18 = BCryptGenRandom(0, (PUCHAR)v15 + 52, 0x10u, 2u);
  if ( v18 < 0 )
  {
    v20 = 1309;
LABEL_13:
    DebugTraceError(
      (unsigned int)v18,
      "ntStatus",
      "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp",
      v20);
    LastError = RtlNtStatusToDosError(v18);
LABEL_28:
    LocalFree(v15);
    goto LABEL_29;
  }
  if ( !PKCS5DerivePBKDF2(
          (UCHAR *)phKey,
          0x14u,
          (__int128 *)(v15 + 52),
          v19,
          *((_DWORD *)v15 + 7),
          *((_DWORD *)v15 + 8),
          1,
          pbSecret,
          0x40u) )
  {
    v21 = 1326;
LABEL_16:
    LastError = 13;
    DebugTraceError(13, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp", v21);
    goto LABEL_28;
  }
  if ( *((_DWORD *)v15 + 10) != 26128 )
  {
    LastError = 13;
    goto LABEL_28;
  }
  phKey = 0;
  LODWORD(pSid) = 0;
  BCryptProviderHandle = (void *)GetBCryptProviderHandle(0x6610u);
  if ( !BCryptProviderHandle )
  {
    v21 = 1345;
    goto LABEL_16;
  }
  v18 = BCryptGenerateSymmetricKey(BCryptProviderHandle, &phKey, 0, 0, pbSecret, 0x20u, 0);
  if ( v18 < 0 )
  {
    v20 = 1359;
    goto LABEL_13;
  }
  *(_OWORD *)pbIV = v39;
  v23 = *(_OWORD *)v31;
  v35 = *((_DWORD *)v31 + 4);
  *(_OWORD *)pbInput = v23;
  v24 = *(_OWORD *)v32;
  v37 = *((_DWORD *)v32 + 4);
  v36 = v24;
  v18 = BCryptEncrypt(
          phKey,
          pbInput,
          0x30u,
          0,
          pbIV,
          0x10u,
          (PUCHAR)&v15[*((unsigned int *)v15 + 9) + 68],
          0x30u,
          (ULONG *)&pSid,
          0);
  BCryptDestroyKey(phKey);
  if ( v18 < 0 )
  {
    v20 = 1386;
    goto LABEL_13;
  }
  LastError = 0;
  v25 = pbInput;
  v26 = 56;
  do
  {
    *v25++ = 0;
    --v26;
  }
  while ( v26 );
  *a6 = (struct _CREDENTIAL_HISTORY *)v15;
  *a7 = v13;
LABEL_29:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v7 )
    LocalFree(v7);
  return LastError;
}

```

## disassembly

```asm
0x180028b1c  mov     [rsp-8+arg_0], rbx
0x180028b21  push    rbp
0x180028b22  push    rsi
0x180028b23  push    rdi
0x180028b24  push    r12
0x180028b26  push    r13
0x180028b28  push    r14
0x180028b2a  push    r15
0x180028b2c  lea     rbp, [rsp-10h]
0x180028b31  sub     rsp, 110h
0x180028b38  mov     rax, cs:__security_cookie
0x180028b3f  xor     rax, rsp
0x180028b42  mov     [rbp+40h+var_40], rax
0x180028b46  mov     rax, [rbp+40h+arg_20]
0x180028b4a  xor     esi, esi
0x180028b4c  mov     r12, [rbp+40h+arg_28]
0x180028b50  mov     r14d, ecx
0x180028b53  mov     r13, [rbp+40h+arg_30]
0x180028b5a  mov     [rsp+140h+var_D0], rax
0x180028b5f  mov     [rsp+140h+pSid], rsi
0x180028b64  mov     [rsp+140h+var_D8], r9
0x180028b69  mov     [rsp+140h+phKey], rdx
0x180028b6e  mov     [rsp+140h+TokenHandle], 0
0x180028b77  call    cs:__imp_GetCurrentThread
0x180028b7e  nop     dword ptr [rax+rax+00h]
0x180028b83  lea     ebx, [rsi+8]
0x180028b86  mov     rcx, rax; ThreadHandle
0x180028b89  mov     edx, ebx; DesiredAccess
0x180028b8b  lea     r9, [rsp+140h+TokenHandle]; TokenHandle
0x180028b90  lea     r8d, [rsi+1]; OpenAsSelf
0x180028b94  call    cs:__imp_OpenThreadToken
0x180028b9b  nop     dword ptr [rax+rax+00h]
0x180028ba0  test    eax, eax
0x180028ba2  jnz     short loc_180028BD2
0x180028ba4  call    cs:__imp_GetLastError
0x180028bab  nop     dword ptr [rax+rax+00h]
0x180028bb0  mov     ebx, eax
0x180028bb2  mov     ecx, eax
0x180028bb4  mov     r9d, 4DBh
0x180028bba  lea     rdx, aDwlasterror; "dwLastError"
0x180028bc1  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180028bc8  call    DebugTraceError
0x180028bcd  jmp     loc_180028EB2
0x180028bd2  mov     rcx, [rsp+140h+TokenHandle]
0x180028bd7  lea     rdx, [rsp+140h+pSid]
0x180028bdc  call    GetTokenUserSid
0x180028be1  test    eax, eax
0x180028be3  jnz     short loc_180028C18
0x180028be5  call    cs:__imp_GetLastError
0x180028bec  nop     dword ptr [rax+rax+00h]
0x180028bf1  mov     r9d, 4E2h
0x180028bf7  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180028bfe  mov     ecx, eax
0x180028c00  lea     rdx, aDwlasterror; "dwLastError"
0x180028c07  mov     ebx, eax
0x180028c09  call    DebugTraceError
0x180028c0e  mov     rsi, [rsp+140h+pSid]
0x180028c13  jmp     loc_180028EB2
0x180028c18  mov     rsi, [rsp+140h+pSid]
0x180028c1d  mov     rcx, rsi; pSid
0x180028c20  call    cs:__imp_GetLengthSid
0x180028c27  nop     dword ptr [rax+rax+00h]
0x180028c2c  mov     ecx, 40h ; '@'; uFlags
0x180028c31  lea     r15d, [rax+74h]
0x180028c35  mov     edx, r15d; uBytes
0x180028c38  call    cs:__imp_LocalAlloc
0x180028c3f  nop     dword ptr [rax+rax+00h]
0x180028c44  mov     rdi, rax
0x180028c47  test    rax, rax
0x180028c4a  jnz     short loc_180028C59
0x180028c4c  mov     r9d, 4F5h
0x180028c52  mov     ecx, ebx
0x180028c54  jmp     loc_180028BBA
0x180028c59  mov     dword ptr [rax+18h], 1
0x180028c60  mov     ecx, 800Eh; unsigned int
0x180028c65  mov     [rax+1Ch], ecx
0x180028c68  test    r14b, 1
0x180028c6c  jnz     short loc_180028C75
0x180028c6e  call    ?GetIterationCount@@YAKI@Z; GetIterationCount(uint)
0x180028c73  jmp     short loc_180028C7A
0x180028c75  mov     eax, 1
0x180028c7a  mov     [rdi+20h], eax
0x180028c7d  mov     rcx, rsi; pSid
0x180028c80  mov     eax, 14h
0x180028c85  mov     dword ptr [rdi+28h], 6610h
0x180028c8c  mov     [rdi+2Ch], eax
0x180028c8f  mov     [rdi+30h], eax
0x180028c92  call    cs:__imp_GetLengthSid
0x180028c99  nop     dword ptr [rax+rax+00h]
0x180028c9e  mov     r8d, eax; Size
0x180028ca1  lea     rcx, [rdi+44h]; void *
0x180028ca5  mov     rdx, rsi; Src
0x180028ca8  mov     [rdi+24h], r8d
0x180028cac  call    memcpy_0
0x180028cb1  mov     r9d, 2; dwFlags
0x180028cb7  lea     rdx, [rdi+34h]; pbBuffer
0x180028cbb  xor     ecx, ecx; hAlgorithm
0x180028cbd  lea     r8d, [r9+0Eh]; cbBuffer
0x180028cc1  call    cs:__imp_BCryptGenRandom
0x180028cc8  nop     dword ptr [rax+rax+00h]
0x180028ccd  mov     ebx, eax
0x180028ccf  test    eax, eax
0x180028cd1  jns     short loc_180028D03
0x180028cd3  mov     r9d, 51Dh
0x180028cd9  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180028ce0  mov     ecx, ebx
0x180028ce2  lea     rdx, aNtstatus; "ntStatus"
0x180028ce9  call    DebugTraceError
0x180028cee  mov     ecx, ebx; Status
0x180028cf0  call    cs:__imp_RtlNtStatusToDosError
0x180028cf7  nop     dword ptr [rax+rax+00h]
0x180028cfc  mov     ebx, eax
0x180028cfe  jmp     loc_180028EA3
0x180028d03  mov     rcx, [rsp+140h+phKey]; int
0x180028d08  lea     rax, [rbp+40h+var_80]
0x180028d0c  mov     dword ptr [rsp+140h+pcbResult], 40h ; '@'; int
0x180028d14  lea     r8, [rdi+34h]; int
0x180028d18  mov     qword ptr [rsp+140h+cbOutput], rax; PUCHAR
0x180028d1d  mov     edx, 14h; int
0x180028d22  mov     eax, [rdi+20h]
0x180028d25  mov     [rsp+140h+dwFlags], 1; char
0x180028d2d  mov     [rsp+140h+cbSecret], eax; int
0x180028d31  mov     eax, [rdi+1Ch]
0x180028d34  mov     dword ptr [rsp+140h+pbSecret], eax; unsigned int
0x180028d38  call    PKCS5DerivePBKDF2
0x180028d3d  xor     r14d, r14d
0x180028d40  test    eax, eax
0x180028d42  jnz     short loc_180028D69
0x180028d44  mov     r9d, 52Eh
0x180028d4a  mov     ebx, 0Dh
0x180028d4f  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180028d56  mov     ecx, ebx
0x180028d58  lea     rdx, aDwlasterror; "dwLastError"
0x180028d5f  call    DebugTraceError
0x180028d64  jmp     loc_180028EA3
0x180028d69  mov     ecx, 6610h; unsigned int
0x180028d6e  cmp     [rdi+28h], ecx
0x180028d71  jnz     loc_180028E9E
0x180028d77  xor     r8d, r8d
0x180028d7a  mov     [rsp+140h+phKey], r14
0x180028d7f  xor     edx, edx
0x180028d81  mov     dword ptr [rsp+140h+pSid], r14d
0x180028d86  call    GetBCryptProviderHandle
0x180028d8b  test    rax, rax
0x180028d8e  jnz     short loc_180028D98
0x180028d90  mov     r9d, 541h
0x180028d96  jmp     short loc_180028D4A
0x180028d98  mov     [rsp+140h+dwFlags], r14d; dwFlags
0x180028d9d  lea     rcx, [rbp+40h+var_80]
0x180028da1  mov     [rsp+140h+cbSecret], 20h ; ' '; cbSecret
0x180028da9  lea     rdx, [rsp+140h+phKey]; phKey
0x180028dae  mov     [rsp+140h+pbSecret], rcx; pbSecret
0x180028db3  xor     r9d, r9d; cbKeyObject
0x180028db6  mov     rcx, rax; hAlgorithm
0x180028db9  xor     r8d, r8d; pbKeyObject
0x180028dbc  call    cs:__imp_BCryptGenerateSymmetricKey
0x180028dc3  nop     dword ptr [rax+rax+00h]
0x180028dc8  mov     ebx, eax
0x180028dca  test    eax, eax
0x180028dcc  jns     short loc_180028DD9
0x180028dce  mov     r9d, 54Fh
0x180028dd4  jmp     loc_180028CD9
0x180028dd9  mov     rax, [rsp+140h+var_D8]
0x180028dde  lea     rdx, [rbp+40h+pbInput]; pbInput
0x180028de2  movaps  xmm0, [rbp+40h+var_60]
0x180028de6  mov     r8d, 30h ; '0'; cbInput
0x180028dec  mov     [rsp+140h+var_F8], r14d; dwFlags
0x180028df1  xor     r9d, r9d; pPaddingInfo
0x180028df4  movdqu  xmmword ptr [rsp+140h+pbIV], xmm0
0x180028dfa  movups  xmm1, xmmword ptr [rax]
0x180028dfd  mov     eax, [rax+10h]
0x180028e00  mov     [rbp+40h+var_A8], eax
0x180028e03  mov     rax, [rsp+140h+var_D0]
0x180028e08  movups  xmmword ptr [rbp+40h+pbInput], xmm1
0x180028e0c  movups  xmm0, xmmword ptr [rax]
0x180028e0f  mov     eax, [rax+10h]
0x180028e12  mov     [rbp+40h+var_94], eax
0x180028e15  lea     rax, [rsp+140h+pSid]
0x180028e1a  mov     [rsp+140h+pcbResult], rax; pcbResult
0x180028e1f  lea     rax, [rsp+140h+pbIV]
0x180028e24  mov     [rsp+140h+cbOutput], r8d; cbOutput
0x180028e29  movups  [rbp+40h+var_A4], xmm0
0x180028e2d  mov     ecx, [rdi+24h]
0x180028e30  add     rcx, 44h ; 'D'
0x180028e34  add     rcx, rdi
0x180028e37  mov     qword ptr [rsp+140h+dwFlags], rcx; pbOutput
0x180028e3c  mov     rcx, [rsp+140h+phKey]; hKey
0x180028e41  mov     [rsp+140h+cbSecret], 10h; cbIV
0x180028e49  mov     [rsp+140h+pbSecret], rax; pbIV
0x180028e4e  call    cs:__imp_BCryptEncrypt
0x180028e55  nop     dword ptr [rax+rax+00h]
0x180028e5a  mov     rcx, [rsp+140h+phKey]; hKey
0x180028e5f  mov     ebx, eax
0x180028e61  call    cs:__imp_BCryptDestroyKey
0x180028e68  nop     dword ptr [rax+rax+00h]
0x180028e6d  test    ebx, ebx
0x180028e6f  jns     short loc_180028E7C
0x180028e71  mov     r9d, 56Ah
0x180028e77  jmp     loc_180028CD9
0x180028e7c  mov     ebx, r14d
0x180028e7f  lea     rax, [rbp+40h+pbInput]
0x180028e83  mov     ecx, 38h ; '8'
0x180028e88  mov     [rax], r14b
0x180028e8b  inc     rax
0x180028e8e  sub     rcx, 1
0x180028e92  jnz     short loc_180028E88
0x180028e94  mov     [r12], rdi
0x180028e98  mov     [r13+0], r15d
0x180028e9c  jmp     short loc_180028EB2
0x180028e9e  mov     ebx, 0Dh
0x180028ea3  mov     rcx, rdi; hMem
0x180028ea6  call    cs:__imp_LocalFree
0x180028ead  nop     dword ptr [rax+rax+00h]
0x180028eb2  mov     rcx, [rsp+140h+TokenHandle]; hObject
0x180028eb7  test    rcx, rcx
0x180028eba  jz      short loc_180028EC8
0x180028ebc  call    cs:__imp_CloseHandle
0x180028ec3  nop     dword ptr [rax+rax+00h]
0x180028ec8  test    rsi, rsi
0x180028ecb  jz      short loc_180028EDC
0x180028ecd  mov     rcx, rsi; hMem
0x180028ed0  call    cs:__imp_LocalFree
0x180028ed7  nop     dword ptr [rax+rax+00h]
0x180028edc  mov     eax, ebx
0x180028ede  mov     rcx, [rbp+40h+var_40]
0x180028ee2  xor     rcx, rsp; StackCookie
0x180028ee5  call    __security_check_cookie
0x180028eea  mov     rbx, [rsp+140h+arg_0]
0x180028ef2  add     rsp, 110h
0x180028ef9  pop     r15
0x180028efb  pop     r14
0x180028efd  pop     r13
0x180028eff  pop     r12
0x180028f01  pop     rdi
0x180028f02  pop     rsi
0x180028f03  pop     rbp
0x180028f04  retn
```
