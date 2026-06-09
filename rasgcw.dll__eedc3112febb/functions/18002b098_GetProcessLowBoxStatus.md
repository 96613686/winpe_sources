# GetProcessLowBoxStatus

- ea: `0x18002b098`
- end: `0x18002b13e`
- name: `GetProcessLowBoxStatus`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002af18`

## callees

- `0x18002b098`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b119`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b119`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002b0c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002b0c3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002b0d6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002b0d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b12b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b12b`
- `ntdll!NtQueryInformationToken` at `0x18002b0fe`
- `ntdll!NtQueryInformationToken` at `0x18002b0fe`

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
0x18002b098  mov     rax, rsp
0x18002b09b  mov     [rax+20h], rbx
0x18002b09f  push    rdi
0x18002b0a0  sub     rsp, 30h
0x18002b0a4  mov     rdi, rcx
0x18002b0a7  mov     qword ptr [rax+18h], 0
0x18002b0af  mov     dword ptr [rax+10h], 0
0x18002b0b6  mov     dword ptr [rax+8], 0
0x18002b0bd  mov     dword ptr [rcx], 0
0x18002b0c3  call    cs:__imp_GetCurrentProcess
0x18002b0c9  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18002b0ce  mov     edx, 8; DesiredAccess
0x18002b0d3  mov     rcx, rax; ProcessHandle
0x18002b0d6  call    cs:__imp_OpenProcessToken
0x18002b0dc  test    eax, eax
0x18002b0de  jz      short loc_18002B119
0x18002b0e0  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18002b0e5  lea     rax, [rsp+38h+arg_8]
0x18002b0ea  mov     r9d, 4; TokenInformationLength
0x18002b0f0  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18002b0f5  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18002b0fa  lea     edx, [r9+19h]; TokenInformationClass
0x18002b0fe  call    cs:__imp_NtQueryInformationToken
0x18002b104  mov     ebx, eax
0x18002b106  test    eax, eax
0x18002b108  js      short loc_18002B121
0x18002b10a  cmp     [rsp+38h+TokenInformation], 0
0x18002b10f  jz      short loc_18002B121
0x18002b111  mov     dword ptr [rdi], 1
0x18002b117  jmp     short loc_18002B121
0x18002b119  call    cs:__imp_GetLastError
0x18002b11f  mov     ebx, eax
0x18002b121  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18002b126  test    rcx, rcx
0x18002b129  jz      short loc_18002B131
0x18002b12b  call    cs:__imp_CloseHandle
0x18002b131  mov     eax, ebx
0x18002b133  mov     rbx, [rsp+38h+arg_18]
0x18002b138  add     rsp, 30h
0x18002b13c  pop     rdi
0x18002b13d  retn
```
