# I_CryptGetToken

- ea: `0x180006c94`
- end: `0x180006d33`
- name: `I_CryptGetToken`
- size: `159`
- prototype: `void *()`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003d30`
- `0x180006710`

## callees

- `0x180006c94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006d15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006d15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ccc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ccc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006ca7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006ce6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006ca7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006ce6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006cc2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006cf9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006cc2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006cf9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006d09`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006d09`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180006cdc`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180006cdc`

## pseudocode

```c
void *I_CryptGetToken()
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HANDLE v2; // rax
  BOOL v3; // ebx
  DWORD v4; // edi
  DWORD v5; // ecx
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
    {
      v5 = LastError;
      goto LABEL_6;
    }
    if ( !ImpersonateSelf(SecurityImpersonation) )
      return 0;
    v2 = GetCurrentThread();
    v3 = OpenThreadToken(v2, 8u, 1, &TokenHandle);
    v4 = GetLastError();
    RevertToSelf();
    if ( !v3 )
    {
      v5 = v4;
LABEL_6:
      SetLastError(v5);
      return 0;
    }
  }
  return TokenHandle;
}

```

## disassembly

```asm
0x180006c94  mov     [rsp+arg_0], rbx
0x180006c99  push    rdi
0x180006c9a  sub     rsp, 20h
0x180006c9e  mov     [rsp+28h+TokenHandle], 0
0x180006ca7  call    cs:__imp_GetCurrentThread
0x180006cad  mov     ebx, 1
0x180006cb2  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180006cb7  mov     rcx, rax; ThreadHandle
0x180006cba  mov     r8d, ebx; OpenAsSelf
0x180006cbd  lea     edi, [rbx+7]
0x180006cc0  mov     edx, edi; DesiredAccess
0x180006cc2  call    cs:__imp_OpenThreadToken
0x180006cc8  test    eax, eax
0x180006cca  jnz     short loc_180006D1F
0x180006ccc  call    cs:__imp_GetLastError
0x180006cd2  cmp     eax, 3F0h
0x180006cd7  jnz     short loc_180006D2F
0x180006cd9  lea     ecx, [rbx+1]; ImpersonationLevel
0x180006cdc  call    cs:__imp_ImpersonateSelf
0x180006ce2  test    eax, eax
0x180006ce4  jz      short loc_180006D1B
0x180006ce6  call    cs:__imp_GetCurrentThread
0x180006cec  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180006cf1  mov     r8d, ebx; OpenAsSelf
0x180006cf4  mov     rcx, rax; ThreadHandle
0x180006cf7  mov     edx, edi; DesiredAccess
0x180006cf9  call    cs:__imp_OpenThreadToken
0x180006cff  mov     ebx, eax
0x180006d01  call    cs:__imp_GetLastError
0x180006d07  mov     edi, eax
0x180006d09  call    cs:__imp_RevertToSelf
0x180006d0f  test    ebx, ebx
0x180006d11  jnz     short loc_180006D1F
0x180006d13  mov     ecx, edi; dwErrCode
0x180006d15  call    cs:__imp_SetLastError
0x180006d1b  xor     eax, eax
0x180006d1d  jmp     short loc_180006D24
0x180006d1f  mov     rax, [rsp+28h+TokenHandle]
0x180006d24  mov     rbx, [rsp+28h+arg_0]
0x180006d29  add     rsp, 20h
0x180006d2d  pop     rdi
0x180006d2e  retn
0x180006d2f  mov     ecx, eax
0x180006d31  jmp     short loc_180006D15
```
