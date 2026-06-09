# EnableBackupPrivilege

- ea: `0x180017df8`
- end: `0x180017f27`
- name: `EnableBackupPrivilege`
- size: `303`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180025e20`
- `0x1800276c0`
- `0x1800294a4`

## callees

- `0x180017df8`
- `0x180051160`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017e2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017e2c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180017e6f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180017e6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180017e5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180017e5d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017e42`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017e42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ed0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017eeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ed0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017eeb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017ee1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017f03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017ee1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017f03`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180017ec6`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180017ec6`

## pseudocode

```c
DWORD __fastcall EnableBackupPrivilege(int a1, int a2)
{
  LUID v2; // rbx
  HANDLE CurrentThread; // rax
  DWORD result; // eax
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  void *v8; // rcx
  int v9; // ebx
  DWORD v10; // eax
  void *TokenHandle; // [rsp+30h] [rbp-20h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-18h] BYREF

  v2 = (LUID)a2;
  NewState = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x28u, 1, &TokenHandle) )
  {
    result = GetLastError();
    if ( result != 1008 )
      return result;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
      return GetLastError();
  }
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Luid = v2;
  NewState.Privileges[0].Attributes = 2;
  if ( !AdjustTokenPrivileges(TokenHandle, a1 == 0, &NewState, 0x10u, 0, 0) )
  {
    LastError = GetLastError();
    v8 = TokenHandle;
    v9 = LastError;
LABEL_7:
    if ( v8 )
      CloseHandle(v8);
    return v9;
  }
  v10 = GetLastError();
  v8 = TokenHandle;
  v9 = 1300;
  if ( v10 == 1300 )
    goto LABEL_7;
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x180017df8  mov     [rsp-8+arg_0], rbx
0x180017dfd  mov     [rsp-8+arg_8], rdi
0x180017e02  push    rbp
0x180017e03  mov     rbp, rsp
0x180017e06  sub     rsp, 50h
0x180017e0a  mov     rax, cs:__security_cookie
0x180017e11  xor     rax, rsp
0x180017e14  mov     [rbp+var_8], rax
0x180017e18  xorps   xmm0, xmm0
0x180017e1b  movsxd  rbx, edx
0x180017e1e  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x180017e22  mov     edi, ecx
0x180017e24  mov     [rbp+TokenHandle], 0
0x180017e2c  call    cs:__imp_GetCurrentThread
0x180017e32  mov     edx, 28h ; '('; DesiredAccess
0x180017e37  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180017e3b  mov     rcx, rax; ThreadHandle
0x180017e3e  lea     r8d, [rdx-27h]; OpenAsSelf
0x180017e42  call    cs:__imp_OpenThreadToken
0x180017e48  test    eax, eax
0x180017e4a  jnz     short loc_180017E84
0x180017e4c  call    cs:__imp_GetLastError
0x180017e52  cmp     eax, 3F0h
0x180017e57  jnz     loc_180017F0B
0x180017e5d  call    cs:__imp_GetCurrentProcess
0x180017e63  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180017e67  mov     edx, 28h ; '('; DesiredAccess
0x180017e6c  mov     rcx, rax; ProcessHandle
0x180017e6f  call    cs:__imp_OpenProcessToken
0x180017e75  test    eax, eax
0x180017e77  jnz     short loc_180017E84
0x180017e79  call    cs:__imp_GetLastError
0x180017e7f  jmp     loc_180017F0B
0x180017e84  xor     edx, edx
0x180017e86  mov     [rsp+50h+ReturnLength], 0; ReturnLength
0x180017e8f  mov     rcx, rbx
0x180017e92  mov     [rbp+NewState.PrivilegeCount], 1
0x180017e99  shr     rcx, 20h
0x180017e9d  lea     r8, [rbp+NewState]; NewState
0x180017ea1  mov     [rbp+NewState.Privileges.Luid.HighPart], ecx
0x180017ea4  test    edi, edi
0x180017ea6  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180017eaa  mov     r9d, 10h; BufferLength
0x180017eb0  setz    dl; DisableAllPrivileges
0x180017eb3  mov     [rbp+NewState.Privileges.Luid.LowPart], ebx
0x180017eb6  mov     [rbp+NewState.Privileges.Attributes], 2
0x180017ebd  mov     [rsp+50h+PreviousState], 0; PreviousState
0x180017ec6  call    cs:__imp_AdjustTokenPrivileges
0x180017ecc  test    eax, eax
0x180017ece  jnz     short loc_180017EEB
0x180017ed0  call    cs:__imp_GetLastError
0x180017ed6  mov     rcx, [rbp+TokenHandle]; hObject
0x180017eda  mov     ebx, eax
0x180017edc  test    rcx, rcx
0x180017edf  jz      short loc_180017EE7
0x180017ee1  call    cs:__imp_CloseHandle
0x180017ee7  mov     eax, ebx
0x180017ee9  jmp     short loc_180017F0B
0x180017eeb  call    cs:__imp_GetLastError
0x180017ef1  mov     rcx, [rbp+TokenHandle]; hObject
0x180017ef5  mov     ebx, 514h
0x180017efa  cmp     eax, ebx
0x180017efc  jz      short loc_180017EDC
0x180017efe  test    rcx, rcx
0x180017f01  jz      short loc_180017F09
0x180017f03  call    cs:__imp_CloseHandle
0x180017f09  xor     eax, eax
0x180017f0b  mov     rcx, [rbp+var_8]
0x180017f0f  xor     rcx, rsp; StackCookie
0x180017f12  call    __security_check_cookie
0x180017f17  mov     rbx, [rsp+50h+arg_0]
0x180017f1c  mov     rdi, [rsp+50h+arg_8]
0x180017f21  add     rsp, 50h
0x180017f25  pop     rbp
0x180017f26  retn
```
