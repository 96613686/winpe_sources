# GetProcessLowBoxStatus

- ea: `0x1800113a0`
- end: `0x180011448`
- name: `GetProcessLowBoxStatus`
- size: `168`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180010d10`

## callees

- `0x1800113a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800113cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800113cb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800113de`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800113de`
- `ntdll!NtQueryInformationToken` at `0x180011406`
- `ntdll!NtQueryInformationToken` at `0x180011406`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011436`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011436`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011423`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011423`

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
0x1800113a0  mov     rax, rsp
0x1800113a3  mov     [rax+20h], rbx
0x1800113a7  push    rdi
0x1800113a8  sub     rsp, 30h
0x1800113ac  mov     rdi, rcx
0x1800113af  mov     qword ptr [rax+18h], 0
0x1800113b7  mov     dword ptr [rax+10h], 0
0x1800113be  mov     dword ptr [rax+8], 0
0x1800113c5  mov     dword ptr [rcx], 0
0x1800113cb  call    cs:__imp_GetCurrentProcess
0x1800113d1  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1800113d6  mov     edx, 8; DesiredAccess
0x1800113db  mov     rcx, rax; ProcessHandle
0x1800113de  call    cs:__imp_OpenProcessToken
0x1800113e4  test    eax, eax
0x1800113e6  jz      short loc_180011436
0x1800113e8  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800113ed  lea     rax, [rsp+38h+arg_8]
0x1800113f2  mov     r9d, 4; TokenInformationLength
0x1800113f8  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800113fd  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180011402  lea     edx, [r9+19h]; TokenInformationClass
0x180011406  call    cs:__imp_NtQueryInformationToken
0x18001140c  mov     ebx, eax
0x18001140e  test    eax, eax
0x180011410  js      short loc_180011419
0x180011412  cmp     [rsp+38h+TokenInformation], 0
0x180011417  jnz     short loc_180011440
0x180011419  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18001141e  test    rcx, rcx
0x180011421  jz      short loc_180011429
0x180011423  call    cs:__imp_CloseHandle
0x180011429  mov     eax, ebx
0x18001142b  mov     rbx, [rsp+38h+arg_18]
0x180011430  add     rsp, 30h
0x180011434  pop     rdi
0x180011435  retn
0x180011436  call    cs:__imp_GetLastError
0x18001143c  mov     ebx, eax
0x18001143e  jmp     short loc_180011419
0x180011440  mov     dword ptr [rdi], 1
0x180011446  jmp     short loc_180011419
```
