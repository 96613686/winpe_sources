# CThreadContext::PrivilegeEnabled(ulong)

- ea: `0x18001997c`
- end: `0x180019a1d`
- name: `?PrivilegeEnabled@CThreadContext@@QEAAHK@Z`
- size: `161`
- prototype: `__int64 __fastcall(CThreadContext *this, DWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009a2c`

## callees

- `0x18000a520`
- `0x18001997c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800199a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800199a8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800199be`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800199be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800199fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800199fd`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x1800199f3`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x1800199f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CThreadContext::PrivilegeEnabled(CThreadContext *this, DWORD a2)
{
  HANDLE CurrentThread; // rax
  WINBOOL pfResult; // [rsp+20h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-28h] BYREF
  _PRIVILEGE_SET RequiredPrivileges; // [rsp+30h] [rbp-20h] BYREF

  pfResult = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    RequiredPrivileges.Control = 1;
    RequiredPrivileges.PrivilegeCount = 1;
    RequiredPrivileges.Privilege[0].Luid.LowPart = a2;
    RequiredPrivileges.Privilege[0].Luid.HighPart = 0;
    RequiredPrivileges.Privilege[0].Attributes = 2;
    PrivilegeCheck(TokenHandle, &RequiredPrivileges, &pfResult);
    CloseHandle(TokenHandle);
  }
  return (unsigned int)pfResult;
}

```

## disassembly

```asm
0x18001997c  mov     [rsp-8+arg_0], rbx
0x180019981  push    rbp
0x180019982  mov     rbp, rsp
0x180019985  sub     rsp, 50h
0x180019989  mov     rax, cs:__security_cookie
0x180019990  xor     rax, rsp
0x180019993  mov     [rbp+var_8], rax
0x180019997  mov     ebx, edx
0x180019999  mov     [rbp+pfResult], 0
0x1800199a0  mov     [rbp+TokenHandle], 0
0x1800199a8  call    cs:__imp_GetCurrentThread
0x1800199ae  mov     edx, 8; DesiredAccess
0x1800199b3  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800199b7  mov     rcx, rax; ThreadHandle
0x1800199ba  lea     r8d, [rdx-7]; OpenAsSelf
0x1800199be  call    cs:__imp_OpenThreadToken
0x1800199c4  test    eax, eax
0x1800199c6  jz      short loc_180019A03
0x1800199c8  mov     rcx, [rbp+TokenHandle]; ClientToken
0x1800199cc  lea     r8, [rbp+pfResult]; pfResult
0x1800199d0  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x1800199d4  mov     [rbp+RequiredPrivileges.Control], 1
0x1800199db  mov     [rbp+RequiredPrivileges.PrivilegeCount], 1
0x1800199e2  mov     [rbp+RequiredPrivileges.Privilege.Luid.LowPart], ebx
0x1800199e5  mov     [rbp+RequiredPrivileges.Privilege.Luid.HighPart], 0
0x1800199ec  mov     [rbp+RequiredPrivileges.Privilege.Attributes], 2
0x1800199f3  call    cs:__imp_PrivilegeCheck
0x1800199f9  mov     rcx, [rbp+TokenHandle]; hObject
0x1800199fd  call    cs:__imp_CloseHandle
0x180019a03  mov     eax, [rbp+pfResult]
0x180019a06  mov     rcx, [rbp+var_8]
0x180019a0a  xor     rcx, rsp; StackCookie
0x180019a0d  call    __security_check_cookie
0x180019a12  mov     rbx, [rsp+50h+arg_0]
0x180019a17  add     rsp, 50h
0x180019a1b  pop     rbp
0x180019a1c  retn
```
