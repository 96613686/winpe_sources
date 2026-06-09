# I_CryptGetToken

- ea: `0x1800092e0`
- end: `0x180009381`
- name: `I_CryptGetToken`
- size: `161`
- prototype: `void *()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008330`

## callees

- `0x1800092e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000935f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000935f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009373`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009373`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000930e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009357`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000930e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009357`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800092f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009344`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800092f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009344`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18000933a`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18000933a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180009367`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180009367`

## pseudocode

```c
void *I_CryptGetToken()
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HANDLE v3; // rax
  BOOL v4; // ebx
  DWORD v5; // edi
  DWORD v6; // ecx
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    return TokenHandle;
  LastError = GetLastError();
  if ( LastError != 1008 )
  {
    v6 = LastError;
LABEL_7:
    SetLastError(v6);
    return 0;
  }
  if ( ImpersonateSelf(SecurityImpersonation) )
  {
    v3 = GetCurrentThread();
    v4 = OpenThreadToken(v3, 8u, 1, &TokenHandle);
    v5 = GetLastError();
    RevertToSelf();
    if ( v4 )
      return TokenHandle;
    v6 = v5;
    goto LABEL_7;
  }
  return 0;
}

```

## disassembly

```asm
0x1800092e0  mov     [rsp+arg_0], rbx
0x1800092e5  push    rdi
0x1800092e6  sub     rsp, 20h
0x1800092ea  mov     [rsp+28h+TokenHandle], 0
0x1800092f3  call    cs:__imp_GetCurrentThread
0x1800092f9  mov     ebx, 1
0x1800092fe  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180009303  mov     rcx, rax; ThreadHandle
0x180009306  mov     r8d, ebx; OpenAsSelf
0x180009309  lea     edi, [rbx+7]
0x18000930c  mov     edx, edi; DesiredAccess
0x18000930e  call    cs:__imp_OpenThreadToken
0x180009314  test    eax, eax
0x180009316  jz      short loc_180009328
0x180009318  mov     rax, [rsp+28h+TokenHandle]
0x18000931d  mov     rbx, [rsp+28h+arg_0]
0x180009322  add     rsp, 20h
0x180009326  pop     rdi
0x180009327  retn
0x180009328  call    cs:__imp_GetLastError
0x18000932e  cmp     eax, 3F0h
0x180009333  jnz     short loc_18000937D
0x180009335  mov     ecx, 2; ImpersonationLevel
0x18000933a  call    cs:__imp_ImpersonateSelf
0x180009340  test    eax, eax
0x180009342  jz      short loc_180009379
0x180009344  call    cs:__imp_GetCurrentThread
0x18000934a  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18000934f  mov     r8d, ebx; OpenAsSelf
0x180009352  mov     rcx, rax; ThreadHandle
0x180009355  mov     edx, edi; DesiredAccess
0x180009357  call    cs:__imp_OpenThreadToken
0x18000935d  mov     ebx, eax
0x18000935f  call    cs:__imp_GetLastError
0x180009365  mov     edi, eax
0x180009367  call    cs:__imp_RevertToSelf
0x18000936d  test    ebx, ebx
0x18000936f  jnz     short loc_180009318
0x180009371  mov     ecx, edi; dwErrCode
0x180009373  call    cs:__imp_SetLastError
0x180009379  xor     eax, eax
0x18000937b  jmp     short loc_18000931D
0x18000937d  mov     ecx, eax
0x18000937f  jmp     short loc_180009373
```
