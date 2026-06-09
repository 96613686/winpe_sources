# GetProcessLowBoxStatus

- ea: `0x18003b2a0`
- end: `0x18003b346`
- name: `GetProcessLowBoxStatus`
- size: `166`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003b128`

## callees

- `0x18003b2a0`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18003b306`
- `ntdll!NtQueryInformationToken` at `0x18003b306`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b321`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b321`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003b2cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003b2cb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003b2de`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003b2de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b333`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b333`

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
0x18003b2a0  mov     rax, rsp
0x18003b2a3  mov     [rax+20h], rbx
0x18003b2a7  push    rdi
0x18003b2a8  sub     rsp, 30h
0x18003b2ac  mov     rdi, rcx
0x18003b2af  mov     qword ptr [rax+18h], 0
0x18003b2b7  mov     dword ptr [rax+10h], 0
0x18003b2be  mov     dword ptr [rax+8], 0
0x18003b2c5  mov     dword ptr [rcx], 0
0x18003b2cb  call    cs:__imp_GetCurrentProcess
0x18003b2d1  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18003b2d6  mov     edx, 8; DesiredAccess
0x18003b2db  mov     rcx, rax; ProcessHandle
0x18003b2de  call    cs:__imp_OpenProcessToken
0x18003b2e4  test    eax, eax
0x18003b2e6  jz      short loc_18003B321
0x18003b2e8  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18003b2ed  lea     rax, [rsp+38h+arg_8]
0x18003b2f2  mov     r9d, 4; TokenInformationLength
0x18003b2f8  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18003b2fd  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18003b302  lea     edx, [r9+19h]; TokenInformationClass
0x18003b306  call    cs:__imp_NtQueryInformationToken
0x18003b30c  mov     ebx, eax
0x18003b30e  test    eax, eax
0x18003b310  js      short loc_18003B329
0x18003b312  cmp     [rsp+38h+TokenInformation], 0
0x18003b317  jz      short loc_18003B329
0x18003b319  mov     dword ptr [rdi], 1
0x18003b31f  jmp     short loc_18003B329
0x18003b321  call    cs:__imp_GetLastError
0x18003b327  mov     ebx, eax
0x18003b329  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18003b32e  test    rcx, rcx
0x18003b331  jz      short loc_18003B339
0x18003b333  call    cs:__imp_CloseHandle
0x18003b339  mov     eax, ebx
0x18003b33b  mov     rbx, [rsp+38h+arg_18]
0x18003b340  add     rsp, 30h
0x18003b344  pop     rdi
0x18003b345  retn
```
