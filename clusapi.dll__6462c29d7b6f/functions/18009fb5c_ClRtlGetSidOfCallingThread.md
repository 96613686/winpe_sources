# ClRtlGetSidOfCallingThread

- ea: `0x18009fb5c`
- end: `0x18009fc53`
- name: `ClRtlGetSidOfCallingThread`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800795d0`

## callees

- `0x18009fb5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009fb9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009fb9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009fb7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009fb7d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18009fbbb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18009fbbb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009fb95`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009fb95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009fbac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009fbac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009fc02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009fc2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009fc02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009fc2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009fc38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009fc38`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009fbf0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009fbf0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009fbe5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009fc1f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009fbe5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009fc1f`

## pseudocode

```c
void *ClRtlGetSidOfCallingThread()
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  void *v2; // rcx
  HLOCAL v4; // rax
  void *v5; // rdi
  BOOL TokenInformation; // ebx
  DWORD TokenInformationLength; // [rsp+40h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+18h] BYREF

  TokenHandle = 0;
  TokenInformationLength = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    v2 = TokenHandle;
  }
  else
  {
    if ( GetLastError() == 1008 )
    {
      CurrentProcess = GetCurrentProcess();
      OpenProcessToken(CurrentProcess, 8u, &TokenHandle);
    }
    v2 = TokenHandle;
    if ( !TokenHandle )
      return 0;
  }
  GetTokenInformation(v2, TokenUser, 0, 0, &TokenInformationLength);
  v4 = LocalAlloc(0, TokenInformationLength);
  v5 = v4;
  if ( !v4 )
  {
    CloseHandle(TokenHandle);
    return 0;
  }
  TokenInformation = GetTokenInformation(TokenHandle, TokenUser, v4, TokenInformationLength, &TokenInformationLength);
  CloseHandle(TokenHandle);
  if ( !TokenInformation )
  {
    LocalFree(v5);
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x18009fb5c  mov     [rsp-8+arg_10], rbx
0x18009fb61  mov     [rsp-8+arg_18], rdi
0x18009fb66  push    rbp
0x18009fb67  mov     rbp, rsp
0x18009fb6a  sub     rsp, 30h
0x18009fb6e  mov     [rbp+TokenHandle], 0
0x18009fb76  mov     [rbp+TokenInformationLength], 0
0x18009fb7d  call    cs:__imp_GetCurrentThread
0x18009fb83  mov     ebx, 8
0x18009fb88  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18009fb8c  mov     rcx, rax; ThreadHandle
0x18009fb8f  mov     edx, ebx; DesiredAccess
0x18009fb91  lea     r8d, [rbx-7]; OpenAsSelf
0x18009fb95  call    cs:__imp_OpenThreadToken
0x18009fb9b  test    eax, eax
0x18009fb9d  jnz     short loc_18009FBCE
0x18009fb9f  call    cs:__imp_GetLastError
0x18009fba5  cmp     eax, 3F0h
0x18009fbaa  jnz     short loc_18009FBC1
0x18009fbac  call    cs:__imp_GetCurrentProcess
0x18009fbb2  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18009fbb6  mov     edx, ebx; DesiredAccess
0x18009fbb8  mov     rcx, rax; ProcessHandle
0x18009fbbb  call    cs:__imp_OpenProcessToken
0x18009fbc1  mov     rcx, [rbp+TokenHandle]
0x18009fbc5  test    rcx, rcx
0x18009fbc8  jnz     short loc_18009FBD2
0x18009fbca  xor     eax, eax
0x18009fbcc  jmp     short loc_18009FC43
0x18009fbce  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18009fbd2  xor     r9d, r9d; TokenInformationLength
0x18009fbd5  lea     rax, [rbp+TokenInformationLength]
0x18009fbd9  xor     r8d, r8d; TokenInformation
0x18009fbdc  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18009fbe1  lea     edx, [r9+1]; TokenInformationClass
0x18009fbe5  call    cs:__imp_GetTokenInformation
0x18009fbeb  mov     edx, [rbp+TokenInformationLength]; uBytes
0x18009fbee  xor     ecx, ecx; uFlags
0x18009fbf0  call    cs:__imp_LocalAlloc
0x18009fbf6  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18009fbfa  mov     rdi, rax
0x18009fbfd  test    rax, rax
0x18009fc00  jnz     short loc_18009FC0A
0x18009fc02  call    cs:__imp_CloseHandle
0x18009fc08  jmp     short loc_18009FBCA
0x18009fc0a  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18009fc0e  lea     rax, [rbp+TokenInformationLength]
0x18009fc12  mov     r8, rdi; TokenInformation
0x18009fc15  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18009fc1a  mov     edx, 1; TokenInformationClass
0x18009fc1f  call    cs:__imp_GetTokenInformation
0x18009fc25  mov     rcx, [rbp+TokenHandle]; hObject
0x18009fc29  mov     ebx, eax
0x18009fc2b  call    cs:__imp_CloseHandle
0x18009fc31  test    ebx, ebx
0x18009fc33  jnz     short loc_18009FC40
0x18009fc35  mov     rcx, rdi; hMem
0x18009fc38  call    cs:__imp_LocalFree
0x18009fc3e  jmp     short loc_18009FBCA
0x18009fc40  mov     rax, rdi
0x18009fc43  mov     rbx, [rsp+30h+arg_10]
0x18009fc48  mov     rdi, [rsp+30h+arg_18]
0x18009fc4d  add     rsp, 30h
0x18009fc51  pop     rbp
0x18009fc52  retn
```
