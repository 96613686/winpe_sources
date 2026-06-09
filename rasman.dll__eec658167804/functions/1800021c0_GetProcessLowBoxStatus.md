# GetProcessLowBoxStatus

- ea: `0x1800021c0`
- end: `0x18000225d`
- name: `GetProcessLowBoxStatus`
- size: `157`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001320`
- `0x18000b010`

## callees

- `0x1800021c0`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18000221b`
- `ntdll!NtQueryInformationToken` at `0x18000221b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800021df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800021df`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800021f2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800021f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000223d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000223d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000224b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000224b`

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
0x1800021c0  push    rbx
0x1800021c2  sub     rsp, 30h
0x1800021c6  xor     eax, eax
0x1800021c8  mov     [rsp+38h+arg_18], rdi
0x1800021cd  mov     [rsp+38h+TokenHandle], rax
0x1800021d2  mov     rdi, rcx
0x1800021d5  mov     [rsp+38h+arg_8], eax
0x1800021d9  mov     [rsp+38h+TokenInformation], eax
0x1800021dd  mov     [rcx], eax
0x1800021df  call    cs:__imp_GetCurrentProcess
0x1800021e5  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1800021ea  mov     edx, 8; DesiredAccess
0x1800021ef  mov     rcx, rax; ProcessHandle
0x1800021f2  call    cs:__imp_OpenProcessToken
0x1800021f8  test    eax, eax
0x1800021fa  jz      short loc_18000224B
0x1800021fc  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180002201  lea     rax, [rsp+38h+arg_8]
0x180002206  mov     r9d, 4; TokenInformationLength
0x18000220c  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180002211  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180002216  mov     edx, 1Dh; TokenInformationClass
0x18000221b  call    cs:__imp_NtQueryInformationToken
0x180002221  mov     ebx, eax
0x180002223  test    eax, eax
0x180002225  js      short loc_18000222E
0x180002227  cmp     [rsp+38h+TokenInformation], 0
0x18000222c  jnz     short loc_180002255
0x18000222e  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180002233  mov     rdi, [rsp+38h+arg_18]
0x180002238  test    rcx, rcx
0x18000223b  jz      short loc_180002243
0x18000223d  call    cs:__imp_CloseHandle
0x180002243  mov     eax, ebx
0x180002245  add     rsp, 30h
0x180002249  pop     rbx
0x18000224a  retn
0x18000224b  call    cs:__imp_GetLastError
0x180002251  mov     ebx, eax
0x180002253  jmp     short loc_18000222E
0x180002255  mov     dword ptr [rdi], 1
0x18000225b  jmp     short loc_18000222E
```
