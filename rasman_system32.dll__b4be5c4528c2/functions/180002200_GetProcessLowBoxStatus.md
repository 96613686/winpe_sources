# GetProcessLowBoxStatus

- ea: `0x180002200`
- end: `0x1800022bc`
- name: `GetProcessLowBoxStatus`
- size: `188`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001250`
- `0x18000b230`

## callees

- `0x180002200`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180002267`
- `ntdll!NtQueryInformationToken` at `0x180002267`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000221f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000221f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180002238`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180002238`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000228f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000228f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022a4`

## pseudocode

```c
__int64 __fastcall GetProcessLowBoxStatus(_DWORD *a1)
{
  HANDLE CurrentProcess; // rax
  int LastError; // ebx
  int TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  ULONG ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  TokenHandle = 0;
  ReturnLength = 0;
  TokenInformation = 0;
  *a1 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    LastError = NtQueryInformationToken(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength);
    if ( LastError >= 0 && TokenInformation )
      *a1 = 1;
  }
  else
  {
    LastError = GetLastError();
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180002200  push    rbx
0x180002202  sub     rsp, 30h
0x180002206  xor     eax, eax
0x180002208  mov     [rsp+38h+arg_18], rdi
0x18000220d  mov     [rsp+38h+TokenHandle], rax
0x180002212  mov     rdi, rcx
0x180002215  mov     [rsp+38h+arg_8], eax
0x180002219  mov     [rsp+38h+TokenInformation], eax
0x18000221d  mov     [rcx], eax
0x18000221f  call    cs:__imp_GetCurrentProcess
0x180002226  nop     dword ptr [rax+rax+00h]
0x18000222b  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180002230  mov     edx, 8; DesiredAccess
0x180002235  mov     rcx, rax; ProcessHandle
0x180002238  call    cs:__imp_OpenProcessToken
0x18000223f  nop     dword ptr [rax+rax+00h]
0x180002244  test    eax, eax
0x180002246  jz      short loc_1800022A4
0x180002248  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18000224d  lea     rax, [rsp+38h+arg_8]
0x180002252  mov     r9d, 4; TokenInformationLength
0x180002258  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18000225d  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180002262  mov     edx, 1Dh; TokenInformationClass
0x180002267  call    cs:__imp_NtQueryInformationToken
0x18000226e  nop     dword ptr [rax+rax+00h]
0x180002273  mov     ebx, eax
0x180002275  test    eax, eax
0x180002277  js      short loc_180002280
0x180002279  cmp     [rsp+38h+TokenInformation], 0
0x18000227e  jnz     short loc_1800022B4
0x180002280  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180002285  mov     rdi, [rsp+38h+arg_18]
0x18000228a  test    rcx, rcx
0x18000228d  jz      short loc_18000229B
0x18000228f  call    cs:__imp_CloseHandle
0x180002296  nop     dword ptr [rax+rax+00h]
0x18000229b  mov     eax, ebx
0x18000229d  add     rsp, 30h
0x1800022a1  pop     rbx
0x1800022a2  retn
0x1800022a4  call    cs:__imp_GetLastError
0x1800022ab  nop     dword ptr [rax+rax+00h]
0x1800022b0  mov     ebx, eax
0x1800022b2  jmp     short loc_180002280
0x1800022b4  mov     dword ptr [rdi], 1
0x1800022ba  jmp     short loc_180002280
```
