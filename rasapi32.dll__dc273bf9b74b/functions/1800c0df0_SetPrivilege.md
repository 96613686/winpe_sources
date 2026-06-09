# SetPrivilege

- ea: `0x1800c0df0`
- end: `0x1800c0eec`
- name: `SetPrivilege`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c0ef4`

## callees

- `0x1800c0df0`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c0e29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c0e29`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800c0e39`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800c0e39`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800c0e78`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800c0eaf`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800c0e78`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800c0eaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0eb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0eb9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c0eca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c0eca`

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
0x1800c0df0  mov     [rsp-8+arg_0], rbx
0x1800c0df5  push    rbp
0x1800c0df6  mov     rbp, rsp
0x1800c0df9  sub     rsp, 70h
0x1800c0dfd  mov     rax, cs:__security_cookie
0x1800c0e04  xor     rax, rsp
0x1800c0e07  mov     [rbp+var_10], rax
0x1800c0e0b  xorps   xmm0, xmm0
0x1800c0e0e  mov     [rbp+TokenHandle], 0
0x1800c0e16  xorps   xmm1, xmm1
0x1800c0e19  mov     ebx, 10h
0x1800c0e1e  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x1800c0e22  mov     [rbp+BufferLength], ebx
0x1800c0e25  movups  xmmword ptr [rbp+var_30.PrivilegeCount], xmm1
0x1800c0e29  call    cs:__imp_GetCurrentProcess
0x1800c0e2f  mov     rcx, rax; ProcessHandle
0x1800c0e32  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800c0e36  lea     edx, [rbx+18h]; DesiredAccess
0x1800c0e39  call    cs:__imp_OpenProcessToken
0x1800c0e3f  test    eax, eax
0x1800c0e41  jz      short loc_1800C0EB9
0x1800c0e43  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800c0e47  lea     rax, [rbp+BufferLength]
0x1800c0e4b  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1800c0e50  lea     r8, [rbp+NewState]; NewState
0x1800c0e54  lea     rax, [rbp+var_30]
0x1800c0e58  mov     [rbp+NewState.PrivilegeCount], 1
0x1800c0e5f  mov     r9d, ebx; BufferLength
0x1800c0e62  mov     [rsp+70h+PreviousState], rax; PreviousState
0x1800c0e67  xor     edx, edx; DisableAllPrivileges
0x1800c0e69  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 9
0x1800c0e71  mov     [rbp+NewState.Privileges.Attributes], 0
0x1800c0e78  call    cs:__imp_AdjustTokenPrivileges
0x1800c0e7e  test    eax, eax
0x1800c0e80  jz      short loc_1800C0EB9
0x1800c0e82  mov     r9d, [rbp+BufferLength]; BufferLength
0x1800c0e86  lea     r8, [rbp+var_30]; NewState
0x1800c0e8a  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800c0e8e  xor     ebx, ebx
0x1800c0e90  or      [rbp+var_30.Privileges.Attributes], 2
0x1800c0e94  xor     edx, edx; DisableAllPrivileges
0x1800c0e96  mov     [rsp+70h+ReturnLength], rbx; ReturnLength
0x1800c0e9b  mov     [rsp+70h+PreviousState], rbx; PreviousState
0x1800c0ea0  mov     [rbp+var_30.PrivilegeCount], 1
0x1800c0ea7  mov     qword ptr [rbp+var_30.Privileges.Luid.LowPart], 9
0x1800c0eaf  call    cs:__imp_AdjustTokenPrivileges
0x1800c0eb5  test    eax, eax
0x1800c0eb7  jnz     short loc_1800C0EC1
0x1800c0eb9  call    cs:__imp_GetLastError
0x1800c0ebf  mov     ebx, eax
0x1800c0ec1  mov     rcx, [rbp+TokenHandle]; hObject
0x1800c0ec5  test    rcx, rcx
0x1800c0ec8  jz      short loc_1800C0ED0
0x1800c0eca  call    cs:__imp_CloseHandle
0x1800c0ed0  mov     eax, ebx
0x1800c0ed2  mov     rcx, [rbp+var_10]
0x1800c0ed6  xor     rcx, rsp; StackCookie
0x1800c0ed9  call    __security_check_cookie
0x1800c0ede  mov     rbx, [rsp+70h+arg_0]
0x1800c0ee6  add     rsp, 70h
0x1800c0eea  pop     rbp
0x1800c0eeb  retn
```
