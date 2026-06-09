# ChainWinStationRegisterNotificationEvent

- ea: `0x18005566c`
- end: `0x18005576c`
- name: `ChainWinStationRegisterNotificationEvent`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800549c4`

## callees

- `0x18005566c`
- `0x180056de0`
- `0x1800bec20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055734`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055734`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055756`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055756`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800556b3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800556b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005569c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005569c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800556c5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180055743`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800556c5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180055743`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005574e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005574e`

## pseudocode

```c
__int64 __fastcall ChainWinStationRegisterNotificationEvent(__int64 a1, int a2, __int64 a3, __int64 *a4)
{
  HANDLE CurrentThread; // rax
  __int64 v8; // rdi
  DWORD LastError; // ebx
  void *TokenHandle; // [rsp+40h] [rbp-38h] BYREF
  __int128 v12; // [rsp+48h] [rbp-30h] BYREF

  TokenHandle = 0;
  v12 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
    SetThreadToken(0, 0);
  else
    TokenHandle = 0;
  DWORD2(v12) = a2;
  *(_QWORD *)&v12 = a1;
  v8 = (unsigned int)I_CertCltProtectFunction(1002, 0, 0, (unsigned int)&v12, 16, 0, 0) != 0;
  *a4 = a1 & -v8;
  if ( TokenHandle )
  {
    LastError = GetLastError();
    SetThreadToken(0, TokenHandle);
    CloseHandle(TokenHandle);
    SetLastError(LastError);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18005566c  push    rbx
0x18005566e  push    rsi
0x18005566f  push    rdi
0x180055670  sub     rsp, 60h
0x180055674  mov     rax, cs:__security_cookie
0x18005567b  xor     rax, rsp
0x18005567e  mov     [rsp+78h+var_20], rax
0x180055683  xorps   xmm0, xmm0
0x180055686  mov     [rsp+78h+TokenHandle], 0
0x18005568f  movups  [rsp+78h+var_30], xmm0
0x180055694  mov     rsi, r9
0x180055697  mov     edi, edx
0x180055699  mov     rbx, rcx
0x18005569c  call    cs:__imp_GetCurrentThread
0x1800556a2  mov     edx, 0Ch; DesiredAccess
0x1800556a7  lea     r9, [rsp+78h+TokenHandle]; TokenHandle
0x1800556ac  mov     rcx, rax; ThreadHandle
0x1800556af  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x1800556b3  call    cs:__imp_OpenThreadToken
0x1800556b9  test    eax, eax
0x1800556bb  jz      loc_18005575E
0x1800556c1  xor     edx, edx; Token
0x1800556c3  xor     ecx, ecx; Thread
0x1800556c5  call    cs:__imp_SetThreadToken
0x1800556cb  mov     [rsp+78h+var_48], 0
0x1800556d4  lea     r9, [rsp+78h+var_30]
0x1800556d9  mov     [rsp+78h+var_50], 0
0x1800556e2  xor     r8d, r8d
0x1800556e5  xor     edx, edx
0x1800556e7  mov     [rsp+78h+var_58], 10h
0x1800556ef  mov     ecx, 3EAh
0x1800556f4  mov     dword ptr [rsp+78h+var_30+8], edi
0x1800556f8  mov     qword ptr [rsp+78h+var_30], rbx
0x1800556fd  call    I_CertCltProtectFunction
0x180055702  xor     edi, edi
0x180055704  test    eax, eax
0x180055706  setnz   dil
0x18005570a  neg     eax
0x18005570c  sbb     rax, rax
0x18005570f  and     rax, rbx
0x180055712  mov     [rsi], rax
0x180055715  cmp     [rsp+78h+TokenHandle], 0
0x18005571b  jnz     short loc_180055734
0x18005571d  mov     eax, edi
0x18005571f  mov     rcx, [rsp+78h+var_20]
0x180055724  xor     rcx, rsp; StackCookie
0x180055727  call    __security_check_cookie
0x18005572c  add     rsp, 60h
0x180055730  pop     rdi
0x180055731  pop     rsi
0x180055732  pop     rbx
0x180055733  retn
0x180055734  call    cs:__imp_GetLastError
0x18005573a  mov     rdx, [rsp+78h+TokenHandle]; Token
0x18005573f  xor     ecx, ecx; Thread
0x180055741  mov     ebx, eax
0x180055743  call    cs:__imp_SetThreadToken
0x180055749  mov     rcx, [rsp+78h+TokenHandle]; hObject
0x18005574e  call    cs:__imp_CloseHandle
0x180055754  mov     ecx, ebx; dwErrCode
0x180055756  call    cs:__imp_SetLastError
0x18005575c  jmp     short loc_18005571D
0x18005575e  mov     [rsp+78h+TokenHandle], 0
0x180055767  jmp     loc_1800556CB
```
