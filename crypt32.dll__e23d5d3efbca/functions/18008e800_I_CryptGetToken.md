# I_CryptGetToken

- ea: `0x18008e800`
- end: `0x18008e8a1`
- name: `I_CryptGetToken`
- size: `161`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180058b08`
- `0x180058cc0`
- `0x18005d484`

## callees

- `0x18008e800`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e838`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e86d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e838`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e86d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18011c002`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18011c002`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008e82e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008e865`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008e82e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008e865`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008e813`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008e852`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008e813`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008e852`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18008e848`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18008e848`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18008e875`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18008e875`

## pseudocode

```c
void *I_CryptGetToken()
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HANDLE v2; // rax
  BOOL v3; // ebx
  DWORD v4; // edi
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
LABEL_9:
    SetLastError(v6);
    return 0;
  }
  if ( ImpersonateSelf(SecurityImpersonation) )
  {
    v2 = GetCurrentThread();
    v3 = OpenThreadToken(v2, 8u, 1, &TokenHandle);
    v4 = GetLastError();
    RevertToSelf();
    if ( v3 )
      return TokenHandle;
    v6 = v4;
    goto LABEL_9;
  }
  return 0;
}

```

## disassembly

```asm
0x18008e800  mov     [rsp+arg_0], rbx
0x18008e805  push    rdi
0x18008e806  sub     rsp, 20h
0x18008e80a  mov     [rsp+28h+TokenHandle], 0
0x18008e813  call    cs:__imp_GetCurrentThread
0x18008e819  mov     ebx, 1
0x18008e81e  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18008e823  mov     rcx, rax; ThreadHandle
0x18008e826  mov     r8d, ebx; OpenAsSelf
0x18008e829  lea     edi, [rbx+7]
0x18008e82c  mov     edx, edi; DesiredAccess
0x18008e82e  call    cs:__imp_OpenThreadToken
0x18008e834  test    eax, eax
0x18008e836  jnz     short loc_18008E87F
0x18008e838  call    cs:__imp_GetLastError
0x18008e83e  cmp     eax, 3F0h
0x18008e843  jnz     short loc_18008E893
0x18008e845  lea     ecx, [rbx+1]; ImpersonationLevel
0x18008e848  call    cs:__imp_ImpersonateSelf
0x18008e84e  test    eax, eax
0x18008e850  jz      short loc_18008E88F
0x18008e852  call    cs:__imp_GetCurrentThread
0x18008e858  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18008e85d  mov     r8d, ebx; OpenAsSelf
0x18008e860  mov     rcx, rax; ThreadHandle
0x18008e863  mov     edx, edi; DesiredAccess
0x18008e865  call    cs:__imp_OpenThreadToken
0x18008e86b  mov     ebx, eax
0x18008e86d  call    cs:__imp_GetLastError
0x18008e873  mov     edi, eax
0x18008e875  call    cs:__imp_RevertToSelf
0x18008e87b  test    ebx, ebx
0x18008e87d  jz      short loc_18008E89A
0x18008e87f  mov     rax, [rsp+28h+TokenHandle]
0x18008e884  mov     rbx, [rsp+28h+arg_0]
0x18008e889  add     rsp, 20h
0x18008e88d  pop     rdi
0x18008e88e  retn
0x18008e88f  xor     eax, eax
0x18008e891  jmp     short loc_18008E884
0x18008e893  mov     ecx, eax; dwErrCode
0x18008e895  jmp     loc_18011C002
0x18008e89a  mov     ecx, edi
0x18008e89c  jmp     loc_18011C002
0x18011c002  call    cs:__imp_SetLastError
0x18011c008  nop
0x18011c009  jmp     loc_18008E88F
```
