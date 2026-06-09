# GetClientIdentity(void)

- ea: `0x180006cbc`
- end: `0x180006d83`
- name: `?GetClientIdentity@@YAPEAXXZ`
- size: `199`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006688`

## callees

- `0x180006cbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d59`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180006d4f`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180006d4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006cd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006cd4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180006d36`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180006d36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006d13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006d13`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006cf3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006cf3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d72`

## pseudocode

```c
HANDLE GetClientIdentity(void)
{
  HANDLE CurrentThread; // rax
  void *v1; // rbx
  HANDLE CurrentProcess; // rax
  HANDLE ExistingTokenHandle; // [rsp+30h] [rbp+8h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  ExistingTokenHandle = 0;
  CurrentThread = GetCurrentThread();
  v1 = CurrentThread;
  if ( CurrentThread )
  {
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      goto LABEL_10;
    if ( GetLastError() != 1008 )
    {
LABEL_9:
      GetLastError();
      goto LABEL_10;
    }
    CloseHandle(v1);
  }
  CurrentProcess = GetCurrentProcess();
  v1 = CurrentProcess;
  if ( !CurrentProcess )
  {
    GetLastError();
    goto LABEL_11;
  }
  if ( !OpenProcessToken(CurrentProcess, 2u, &ExistingTokenHandle)
    || !DuplicateToken(ExistingTokenHandle, SecurityImpersonation, &TokenHandle) )
  {
    goto LABEL_9;
  }
LABEL_10:
  CloseHandle(v1);
LABEL_11:
  if ( ExistingTokenHandle )
    CloseHandle(ExistingTokenHandle);
  return TokenHandle;
}

```

## disassembly

```asm
0x180006cbc  push    rbx
0x180006cbe  sub     rsp, 20h
0x180006cc2  mov     [rsp+28h+TokenHandle], 0
0x180006ccb  mov     [rsp+28h+ExistingTokenHandle], 0
0x180006cd4  call    cs:__imp_GetCurrentThread
0x180006cda  mov     rbx, rax
0x180006cdd  test    rax, rax
0x180006ce0  jz      short loc_180006D13
0x180006ce2  mov     edx, 8; DesiredAccess
0x180006ce7  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180006cec  mov     rcx, rax; ThreadHandle
0x180006cef  lea     r8d, [rdx-7]; OpenAsSelf
0x180006cf3  call    cs:__imp_OpenThreadToken
0x180006cf9  test    eax, eax
0x180006cfb  jnz     short loc_180006D5F
0x180006cfd  call    cs:__imp_GetLastError
0x180006d03  cmp     eax, 3F0h
0x180006d08  jnz     short loc_180006D59
0x180006d0a  mov     rcx, rbx; hObject
0x180006d0d  call    cs:__imp_CloseHandle
0x180006d13  call    cs:__imp_GetCurrentProcess
0x180006d19  mov     rbx, rax
0x180006d1c  test    rax, rax
0x180006d1f  jnz     short loc_180006D29
0x180006d21  call    cs:__imp_GetLastError
0x180006d27  jmp     short loc_180006D68
0x180006d29  lea     r8, [rsp+28h+ExistingTokenHandle]; TokenHandle
0x180006d2e  mov     edx, 2; DesiredAccess
0x180006d33  mov     rcx, rax; ProcessHandle
0x180006d36  call    cs:__imp_OpenProcessToken
0x180006d3c  test    eax, eax
0x180006d3e  jz      short loc_180006D59
0x180006d40  mov     rcx, [rsp+28h+ExistingTokenHandle]; ExistingTokenHandle
0x180006d45  lea     r8, [rsp+28h+TokenHandle]; DuplicateTokenHandle
0x180006d4a  mov     edx, 2; ImpersonationLevel
0x180006d4f  call    cs:__imp_DuplicateToken
0x180006d55  test    eax, eax
0x180006d57  jnz     short loc_180006D5F
0x180006d59  call    cs:__imp_GetLastError
0x180006d5f  mov     rcx, rbx; hObject
0x180006d62  call    cs:__imp_CloseHandle
0x180006d68  mov     rcx, [rsp+28h+ExistingTokenHandle]; hObject
0x180006d6d  test    rcx, rcx
0x180006d70  jz      short loc_180006D78
0x180006d72  call    cs:__imp_CloseHandle
0x180006d78  mov     rax, [rsp+28h+TokenHandle]
0x180006d7d  add     rsp, 20h
0x180006d81  pop     rbx
0x180006d82  retn
```
