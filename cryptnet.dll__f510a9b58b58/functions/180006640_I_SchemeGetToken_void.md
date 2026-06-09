# I_SchemeGetToken(void)

- ea: `0x180006640`
- end: `0x180006700`
- name: `?I_SchemeGetToken@@YAPEAXXZ`
- size: `192`
- prototype: `void *(void)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001798`
- `0x180006290`
- `0x1800063b0`
- `0x180006420`

## callees

- `0x180006640`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800066e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800066e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006679`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006679`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000664d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000669a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000664d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000669a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006666`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800066b3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006666`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800066b3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800066c3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800066c3`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18000668b`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18000668b`

## pseudocode

```c
void *I_SchemeGetToken(void)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HANDLE v2; // rax
  BOOL v3; // ebx
  DWORD v4; // edi
  DWORD v6; // ecx
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError == 1008 )
    {
      if ( !ImpersonateSelf(SecurityImpersonation) )
        return 0;
      v2 = GetCurrentThread();
      v3 = OpenThreadToken(v2, 0xCu, 1, &TokenHandle);
      v4 = GetLastError();
      RevertToSelf();
      if ( v3 )
        return TokenHandle;
      v6 = v4;
    }
    else
    {
      v6 = LastError;
    }
    SetLastError(v6);
    return 0;
  }
  return TokenHandle;
}

```

## disassembly

```asm
0x180006640  sub     rsp, 28h
0x180006644  mov     [rsp+28h+TokenHandle], 0
0x18000664d  call    cs:__imp_GetCurrentThread
0x180006653  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180006658  mov     edx, 0Ch; DesiredAccess
0x18000665d  mov     rcx, rax; ThreadHandle
0x180006660  mov     r8d, 1; OpenAsSelf
0x180006666  call    cs:__imp_OpenThreadToken
0x18000666c  test    eax, eax
0x18000666e  jnz     loc_1800066F9
0x180006674  mov     [rsp+28h+var_8], rdi
0x180006679  call    cs:__imp_GetLastError
0x18000667f  cmp     eax, 3F0h
0x180006684  jnz     short loc_1800066F5
0x180006686  mov     ecx, 2; ImpersonationLevel
0x18000668b  call    cs:__imp_ImpersonateSelf
0x180006691  test    eax, eax
0x180006693  jz      short loc_1800066E9
0x180006695  mov     [rsp+28h+arg_8], rbx
0x18000669a  call    cs:__imp_GetCurrentThread
0x1800066a0  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800066a5  mov     edx, 0Ch; DesiredAccess
0x1800066aa  mov     rcx, rax; ThreadHandle
0x1800066ad  mov     r8d, 1; OpenAsSelf
0x1800066b3  call    cs:__imp_OpenThreadToken
0x1800066b9  mov     ebx, eax
0x1800066bb  call    cs:__imp_GetLastError
0x1800066c1  mov     edi, eax
0x1800066c3  call    cs:__imp_RevertToSelf
0x1800066c9  test    ebx, ebx
0x1800066cb  mov     rbx, [rsp+28h+arg_8]
0x1800066d0  jz      short loc_1800066E1
0x1800066d2  mov     rax, [rsp+28h+TokenHandle]
0x1800066d7  mov     rdi, [rsp+28h+var_8]
0x1800066dc  add     rsp, 28h
0x1800066e0  retn
0x1800066e1  mov     ecx, edi; dwErrCode
0x1800066e3  call    cs:__imp_SetLastError
0x1800066e9  mov     rdi, [rsp+28h+var_8]
0x1800066ee  xor     eax, eax
0x1800066f0  add     rsp, 28h
0x1800066f4  retn
0x1800066f5  mov     ecx, eax
0x1800066f7  jmp     short loc_1800066E3
0x1800066f9  mov     rax, [rsp+28h+TokenHandle]
0x1800066fe  jmp     short loc_1800066DC
```
