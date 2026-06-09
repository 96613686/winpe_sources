# _CreateAutoLogInfo

- ea: `0x1800f33a8`
- end: `0x1800f34b6`
- name: `_CreateAutoLogInfo`
- size: `270`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180056214`
- `0x18005819c`

## callees

- `0x180028d60`
- `0x180046e10`
- `0x180058b60`
- `0x180058cc0`
- `0x18005d484`
- `0x1800965f4`
- `0x1800f33a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f33fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f33fd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f33ea`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f342b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f33ea`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f342b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f33d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f3417`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f33d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f3417`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f34a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f34a2`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1800f340d`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1800f340d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800f343e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800f343e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800f3461`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800f3461`

## pseudocode

```c
__int64 CreateAutoLogInfo()
{
  __int64 result; // rax
  __int64 v1; // rbx
  HANDLE CurrentThread; // rax
  HANDLE v3; // rax
  PSID *TokenUser; // rax
  PSID *v5; // rdi
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = 0;
  result = PkiZeroAlloc(0x18u);
  v1 = result;
  if ( result )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      TokenHandle = 0;
      if ( GetLastError() == 1008 )
      {
        if ( ImpersonateSelf(SecurityImpersonation) )
        {
          v3 = GetCurrentThread();
          if ( !OpenThreadToken(v3, 8u, 1, &TokenHandle) )
            TokenHandle = 0;
          RevertToSelf();
        }
      }
    }
    if ( TokenHandle )
    {
      TokenUser = (PSID *)CertDiagGetTokenUser(TokenHandle);
      v5 = TokenUser;
      if ( TokenUser )
      {
        ConvertSidToStringSidW(*TokenUser, (LPWSTR *)v1);
        PkiDefaultCryptFree(v5);
      }
      if ( (unsigned int)I_CryptIsAppContainerToken(TokenHandle) )
      {
        if ( (unsigned int)I_CryptGetTokenAppContainerStringSid(TokenHandle) )
          *(_QWORD *)(v1 + 16) = CertDiagGetAppContainerMoniker(TokenHandle);
      }
      CloseHandle(TokenHandle);
    }
    return v1;
  }
  return result;
}

```

## disassembly

```asm
0x1800f33a8  mov     [rsp+arg_8], rbx
0x1800f33ad  push    rdi
0x1800f33ae  sub     rsp, 20h
0x1800f33b2  mov     ecx, 18h; uBytes
0x1800f33b7  mov     [rsp+28h+TokenHandle], 0
0x1800f33c0  call    PkiZeroAlloc
0x1800f33c5  mov     rbx, rax
0x1800f33c8  test    rax, rax
0x1800f33cb  jz      loc_1800F34AB
0x1800f33d1  call    cs:__imp_GetCurrentThread
0x1800f33d7  mov     edi, 1
0x1800f33dc  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800f33e1  mov     rcx, rax; ThreadHandle
0x1800f33e4  mov     r8d, edi; OpenAsSelf
0x1800f33e7  lea     edx, [rdi+7]; DesiredAccess
0x1800f33ea  call    cs:__imp_OpenThreadToken
0x1800f33f0  test    eax, eax
0x1800f33f2  jnz     short loc_1800F3444
0x1800f33f4  mov     [rsp+28h+TokenHandle], 0
0x1800f33fd  call    cs:__imp_GetLastError
0x1800f3403  cmp     eax, 3F0h
0x1800f3408  jnz     short loc_1800F3444
0x1800f340a  lea     ecx, [rdi+1]; ImpersonationLevel
0x1800f340d  call    cs:__imp_ImpersonateSelf
0x1800f3413  test    eax, eax
0x1800f3415  jz      short loc_1800F3444
0x1800f3417  call    cs:__imp_GetCurrentThread
0x1800f341d  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800f3422  mov     r8d, edi; OpenAsSelf
0x1800f3425  mov     rcx, rax; ThreadHandle
0x1800f3428  lea     edx, [rdi+7]; DesiredAccess
0x1800f342b  call    cs:__imp_OpenThreadToken
0x1800f3431  test    eax, eax
0x1800f3433  jnz     short loc_1800F343E
0x1800f3435  mov     [rsp+28h+TokenHandle], 0
0x1800f343e  call    cs:__imp_RevertToSelf
0x1800f3444  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x1800f3449  test    rcx, rcx
0x1800f344c  jz      short loc_1800F34A8
0x1800f344e  call    CertDiagGetTokenUser
0x1800f3453  mov     rdi, rax
0x1800f3456  test    rax, rax
0x1800f3459  jz      short loc_1800F346F
0x1800f345b  mov     rcx, [rax]; Sid
0x1800f345e  mov     rdx, rbx; StringSid
0x1800f3461  call    cs:__imp_ConvertSidToStringSidW
0x1800f3467  mov     rcx, rdi; hMem
0x1800f346a  call    PkiDefaultCryptFree
0x1800f346f  mov     rcx, [rsp+28h+TokenHandle]
0x1800f3474  call    I_CryptIsAppContainerToken
0x1800f3479  test    eax, eax
0x1800f347b  jz      short loc_1800F349D
0x1800f347d  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x1800f3482  lea     rdx, [rbx+8]
0x1800f3486  call    I_CryptGetTokenAppContainerStringSid
0x1800f348b  test    eax, eax
0x1800f348d  jz      short loc_1800F349D
0x1800f348f  mov     rcx, [rsp+28h+TokenHandle]
0x1800f3494  call    CertDiagGetAppContainerMoniker
0x1800f3499  mov     [rbx+10h], rax
0x1800f349d  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x1800f34a2  call    cs:__imp_CloseHandle
0x1800f34a8  mov     rax, rbx
0x1800f34ab  mov     rbx, [rsp+28h+arg_8]
0x1800f34b0  add     rsp, 20h
0x1800f34b4  pop     rdi
0x1800f34b5  retn
```
