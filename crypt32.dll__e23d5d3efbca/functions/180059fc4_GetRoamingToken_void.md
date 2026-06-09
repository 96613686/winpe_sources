# GetRoamingToken(void)

- ea: `0x180059fc4`
- end: `0x18005a065`
- name: `?GetRoamingToken@@YAPEAXXZ`
- size: `161`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005a06c`

## callees

- `0x180059fc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059ffc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a031`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059ffc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a031`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180118f66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180118f66`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180059ff2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005a029`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180059ff2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005a029`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180059fd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005a016`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180059fd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005a016`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18005a00c`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18005a00c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005a039`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005a039`

## pseudocode

```c
void *GetRoamingToken(void)
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
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
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
    v3 = OpenThreadToken(v2, 0xCu, 1, &TokenHandle);
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
0x180059fc4  mov     [rsp+arg_8], rbx
0x180059fc9  push    rdi
0x180059fca  sub     rsp, 20h
0x180059fce  mov     [rsp+28h+TokenHandle], 0
0x180059fd7  call    cs:__imp_GetCurrentThread
0x180059fdd  mov     ebx, 1
0x180059fe2  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180059fe7  mov     rcx, rax; ThreadHandle
0x180059fea  mov     r8d, ebx; OpenAsSelf
0x180059fed  lea     edi, [rbx+0Bh]
0x180059ff0  mov     edx, edi; DesiredAccess
0x180059ff2  call    cs:__imp_OpenThreadToken
0x180059ff8  test    eax, eax
0x180059ffa  jnz     short loc_18005A043
0x180059ffc  call    cs:__imp_GetLastError
0x18005a002  cmp     eax, 3F0h
0x18005a007  jnz     short loc_18005A057
0x18005a009  lea     ecx, [rbx+1]; ImpersonationLevel
0x18005a00c  call    cs:__imp_ImpersonateSelf
0x18005a012  test    eax, eax
0x18005a014  jz      short loc_18005A053
0x18005a016  call    cs:__imp_GetCurrentThread
0x18005a01c  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18005a021  mov     r8d, ebx; OpenAsSelf
0x18005a024  mov     rcx, rax; ThreadHandle
0x18005a027  mov     edx, edi; DesiredAccess
0x18005a029  call    cs:__imp_OpenThreadToken
0x18005a02f  mov     ebx, eax
0x18005a031  call    cs:__imp_GetLastError
0x18005a037  mov     edi, eax
0x18005a039  call    cs:__imp_RevertToSelf
0x18005a03f  test    ebx, ebx
0x18005a041  jz      short loc_18005A05E
0x18005a043  mov     rax, [rsp+28h+TokenHandle]
0x18005a048  mov     rbx, [rsp+28h+arg_8]
0x18005a04d  add     rsp, 20h
0x18005a051  pop     rdi
0x18005a052  retn
0x18005a053  xor     eax, eax
0x18005a055  jmp     short loc_18005A048
0x18005a057  mov     ecx, eax; dwErrCode
0x18005a059  jmp     loc_180118F66
0x18005a05e  mov     ecx, edi
0x18005a060  jmp     loc_180118F66
0x180118f66  call    cs:__imp_SetLastError
0x180118f6c  nop
0x180118f6d  jmp     loc_18005A053
```
