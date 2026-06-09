# SetPrivilege

- ea: `0x18005f94c`
- end: `0x18005fa71`
- name: `SetPrivilege`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005fa78`

## callees

- `0x18005f94c`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005f985`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005f985`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005f99b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005f99b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005fa48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005fa48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fa31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fa31`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18005f9e4`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18005fa21`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18005f9e4`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18005fa21`

## pseudocode

```c
__int64 SetPrivilege()
{
  HANDLE CurrentProcess; // rax
  DWORD LastError; // ebx
  DWORD BufferLength; // [rsp+30h] [rbp-40h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-38h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+40h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+50h] [rbp-20h] BYREF

  TokenHandle = 0;
  NewState = 0;
  BufferLength = 16;
  PreviousState = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle)
    || (NewState.PrivilegeCount = 1,
        NewState.Privileges[0].Luid = (LUID)9LL,
        NewState.Privileges[0].Attributes = 0,
        !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &BufferLength))
    || (LastError = 0,
        PreviousState.Privileges[0].Attributes |= 2u,
        PreviousState.PrivilegeCount = 1,
        PreviousState.Privileges[0].Luid = (LUID)9LL,
        !AdjustTokenPrivileges(TokenHandle, 0, &PreviousState, BufferLength, 0, 0)) )
  {
    LastError = GetLastError();
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x18005f94c  mov     [rsp-8+arg_0], rbx
0x18005f951  push    rbp
0x18005f952  mov     rbp, rsp
0x18005f955  sub     rsp, 70h
0x18005f959  mov     rax, cs:__security_cookie
0x18005f960  xor     rax, rsp
0x18005f963  mov     [rbp+var_10], rax
0x18005f967  xorps   xmm0, xmm0
0x18005f96a  mov     [rbp+TokenHandle], 0
0x18005f972  xorps   xmm1, xmm1
0x18005f975  mov     ebx, 10h
0x18005f97a  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x18005f97e  mov     [rbp+BufferLength], ebx
0x18005f981  movups  xmmword ptr [rbp+var_30.PrivilegeCount], xmm1
0x18005f985  call    cs:__imp_GetCurrentProcess
0x18005f98c  nop     dword ptr [rax+rax+00h]
0x18005f991  mov     rcx, rax; ProcessHandle
0x18005f994  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18005f998  lea     edx, [rbx+18h]; DesiredAccess
0x18005f99b  call    cs:__imp_OpenProcessToken
0x18005f9a2  nop     dword ptr [rax+rax+00h]
0x18005f9a7  test    eax, eax
0x18005f9a9  jz      loc_18005FA31
0x18005f9af  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18005f9b3  lea     rax, [rbp+BufferLength]
0x18005f9b7  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18005f9bc  lea     r8, [rbp+NewState]; NewState
0x18005f9c0  lea     rax, [rbp+var_30]
0x18005f9c4  mov     [rbp+NewState.PrivilegeCount], 1
0x18005f9cb  mov     r9d, ebx; BufferLength
0x18005f9ce  mov     [rsp+70h+PreviousState], rax; PreviousState
0x18005f9d3  xor     edx, edx; DisableAllPrivileges
0x18005f9d5  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 9
0x18005f9dd  mov     [rbp+NewState.Privileges.Attributes], 0
0x18005f9e4  call    cs:__imp_AdjustTokenPrivileges
0x18005f9eb  nop     dword ptr [rax+rax+00h]
0x18005f9f0  test    eax, eax
0x18005f9f2  jz      short loc_18005FA31
0x18005f9f4  mov     r9d, [rbp+BufferLength]; BufferLength
0x18005f9f8  lea     r8, [rbp+var_30]; NewState
0x18005f9fc  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18005fa00  xor     ebx, ebx
0x18005fa02  or      [rbp+var_30.Privileges.Attributes], 2
0x18005fa06  xor     edx, edx; DisableAllPrivileges
0x18005fa08  mov     [rsp+70h+ReturnLength], rbx; ReturnLength
0x18005fa0d  mov     [rsp+70h+PreviousState], rbx; PreviousState
0x18005fa12  mov     [rbp+var_30.PrivilegeCount], 1
0x18005fa19  mov     qword ptr [rbp+var_30.Privileges.Luid.LowPart], 9
0x18005fa21  call    cs:__imp_AdjustTokenPrivileges
0x18005fa28  nop     dword ptr [rax+rax+00h]
0x18005fa2d  test    eax, eax
0x18005fa2f  jnz     short loc_18005FA3F
0x18005fa31  call    cs:__imp_GetLastError
0x18005fa38  nop     dword ptr [rax+rax+00h]
0x18005fa3d  mov     ebx, eax
0x18005fa3f  mov     rcx, [rbp+TokenHandle]; hObject
0x18005fa43  test    rcx, rcx
0x18005fa46  jz      short loc_18005FA54
0x18005fa48  call    cs:__imp_CloseHandle
0x18005fa4f  nop     dword ptr [rax+rax+00h]
0x18005fa54  mov     eax, ebx
0x18005fa56  mov     rcx, [rbp+var_10]
0x18005fa5a  xor     rcx, rsp; StackCookie
0x18005fa5d  call    __security_check_cookie
0x18005fa62  mov     rbx, [rsp+70h+arg_0]
0x18005fa6a  add     rsp, 70h
0x18005fa6e  pop     rbp
0x18005fa6f  retn
```
