# SetPrivilege

- ea: `0x180033f2c`
- end: `0x180034008`
- name: `SetPrivilege`
- size: `220`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016920`
- `0x180027aa0`

## callees

- `0x180033f2c`
- `0x180043510`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180033f4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180033f4e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180033f5f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180033f5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033fc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033fe3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800457fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033fc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033fe3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800457fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033fd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800457f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033fd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800457f1`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180033fb9`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180033fb9`

## pseudocode

```c
__int64 __fastcall SetPrivilege(__int64 a1, int a2)
{
  DWORD LastError; // ebx
  HANDLE CurrentProcess; // rax
  void *TokenHandle[3]; // [rsp+38h] [rbp-40h] BYREF
  _TOKEN_PRIVILEGES NewState; // [rsp+50h] [rbp-28h] BYREF

  LastError = 0;
  TokenHandle[0] = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, TokenHandle)
    || (NewState.PrivilegeCount = 1,
        TokenHandle[2] = (void *)18,
        TokenHandle[1] = (void *)18,
        NewState.Privileges[0].Luid = (LUID)18LL,
        NewState.Privileges[0].Attributes = a2 != 0 ? 2 : 0,
        !AdjustTokenPrivileges(TokenHandle[0], 0, &NewState, 0, 0, 0)) )
  {
    LastError = GetLastError();
  }
  if ( TokenHandle[0] && !CloseHandle(TokenHandle[0]) )
    return GetLastError();
  return LastError;
}

```

## disassembly

```asm
0x180033f2c  mov     [rsp+arg_0], rbx
0x180033f31  push    rdi
0x180033f32  sub     rsp, 70h
0x180033f36  mov     rax, cs:__security_cookie
0x180033f3d  xor     rax, rsp
0x180033f40  mov     [rsp+78h+var_18], rax
0x180033f45  mov     edi, edx
0x180033f47  xor     ebx, ebx
0x180033f49  mov     [rsp+78h+TokenHandle], rbx
0x180033f4e  call    cs:__imp_GetCurrentProcess
0x180033f54  mov     rcx, rax; ProcessHandle
0x180033f57  lea     r8, [rsp+78h+TokenHandle]; TokenHandle
0x180033f5c  lea     edx, [rbx+28h]; DesiredAccess
0x180033f5f  call    cs:__imp_OpenProcessToken
0x180033f65  test    eax, eax
0x180033f67  jz      short loc_180033FC3
0x180033f69  xorps   xmm0, xmm0
0x180033f6c  movups  xmmword ptr [rsp+78h+NewState.PrivilegeCount], xmm0
0x180033f71  mov     [rsp+78h+NewState.PrivilegeCount], 1
0x180033f79  mov     [rsp+78h+var_38], rbx
0x180033f7e  mov     [rsp+78h+var_30], rbx
0x180033f83  lea     eax, [rbx+12h]
0x180033f86  mov     [rsp+78h+var_30], rax
0x180033f8b  mov     [rsp+78h+var_38], rax
0x180033f90  mov     qword ptr [rsp+78h+NewState.Privileges.Luid.LowPart], rax
0x180033f95  neg     edi
0x180033f97  sbb     eax, eax
0x180033f99  and     eax, 2
0x180033f9c  mov     [rsp+78h+NewState.Privileges.Attributes], eax
0x180033fa0  mov     [rsp+78h+ReturnLength], rbx; ReturnLength
0x180033fa5  mov     [rsp+78h+PreviousState], rbx; PreviousState
0x180033faa  xor     r9d, r9d; BufferLength
0x180033fad  lea     r8, [rsp+78h+NewState]; NewState
0x180033fb2  xor     edx, edx; DisableAllPrivileges
0x180033fb4  mov     rcx, [rsp+78h+TokenHandle]; TokenHandle
0x180033fb9  call    cs:__imp_AdjustTokenPrivileges
0x180033fbf  test    eax, eax
0x180033fc1  jnz     short loc_180033FCF
0x180033fc3  call    cs:__imp_GetLastError
0x180033fc9  mov     [rsp+78h+var_48], eax
0x180033fcd  mov     ebx, eax
0x180033fcf  mov     rcx, [rsp+78h+TokenHandle]; hObject
0x180033fd4  test    rcx, rcx
0x180033fd7  jz      short loc_180033FEB
0x180033fd9  call    cs:__imp_CloseHandle
0x180033fdf  test    eax, eax
0x180033fe1  jnz     short loc_180033FEB
0x180033fe3  call    cs:__imp_GetLastError
0x180033fe9  mov     ebx, eax
0x180033feb  mov     eax, ebx
0x180033fed  mov     rcx, [rsp+78h+var_18]
0x180033ff2  xor     rcx, rsp; StackCookie
0x180033ff5  call    __security_check_cookie
0x180033ffa  mov     rbx, [rsp+78h+arg_0]
0x180034002  add     rsp, 70h
0x180034006  pop     rdi
0x180034007  retn
0x1800457df  push    rbp
0x1800457e1  sub     rsp, 30h
0x1800457e5  mov     rbp, rdx
0x1800457e8  mov     rcx, [rbp+38h]; hObject
0x1800457ec  test    rcx, rcx
0x1800457ef  jz      short loc_180045804
0x1800457f1  call    cs:__imp_CloseHandle
0x1800457f7  test    eax, eax
0x1800457f9  jnz     short loc_180045804
0x1800457fb  call    cs:__imp_GetLastError
0x180045801  mov     [rbp+30h], eax
0x180045804  add     rsp, 30h
0x180045808  pop     rbp
0x180045809  retn
```
