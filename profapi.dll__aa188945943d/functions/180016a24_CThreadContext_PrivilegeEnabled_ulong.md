# CThreadContext::PrivilegeEnabled(ulong)

- ea: `0x180016a24`
- end: `0x180016ac5`
- name: `?PrivilegeEnabled@CThreadContext@@QEAAHK@Z`
- size: `161`
- prototype: `__int64 __fastcall(CThreadContext *this, DWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ccec`

## callees

- `0x18000fa10`
- `0x180016a24`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016a66`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016a66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016a50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016a50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016aa5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016aa5`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x180016a9b`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x180016a9b`

## pseudocode

```c
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
0x180016a24  mov     [rsp-8+arg_0], rbx
0x180016a29  push    rbp
0x180016a2a  mov     rbp, rsp
0x180016a2d  sub     rsp, 50h
0x180016a31  mov     rax, cs:__security_cookie
0x180016a38  xor     rax, rsp
0x180016a3b  mov     [rbp+var_8], rax
0x180016a3f  mov     ebx, edx
0x180016a41  mov     [rbp+pfResult], 0
0x180016a48  mov     [rbp+TokenHandle], 0
0x180016a50  call    cs:__imp_GetCurrentThread
0x180016a56  mov     edx, 8; DesiredAccess
0x180016a5b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180016a5f  mov     rcx, rax; ThreadHandle
0x180016a62  lea     r8d, [rdx-7]; OpenAsSelf
0x180016a66  call    cs:__imp_OpenThreadToken
0x180016a6c  test    eax, eax
0x180016a6e  jz      short loc_180016AAB
0x180016a70  mov     rcx, [rbp+TokenHandle]; ClientToken
0x180016a74  lea     r8, [rbp+pfResult]; pfResult
0x180016a78  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x180016a7c  mov     [rbp+RequiredPrivileges.Control], 1
0x180016a83  mov     [rbp+RequiredPrivileges.PrivilegeCount], 1
0x180016a8a  mov     [rbp+RequiredPrivileges.Privilege.Luid.LowPart], ebx
0x180016a8d  mov     [rbp+RequiredPrivileges.Privilege.Luid.HighPart], 0
0x180016a94  mov     [rbp+RequiredPrivileges.Privilege.Attributes], 2
0x180016a9b  call    cs:__imp_PrivilegeCheck
0x180016aa1  mov     rcx, [rbp+TokenHandle]; hObject
0x180016aa5  call    cs:__imp_CloseHandle
0x180016aab  mov     eax, [rbp+pfResult]
0x180016aae  mov     rcx, [rbp+var_8]
0x180016ab2  xor     rcx, rsp; StackCookie
0x180016ab5  call    __security_check_cookie
0x180016aba  mov     rbx, [rsp+50h+arg_0]
0x180016abf  add     rsp, 50h
0x180016ac3  pop     rbp
0x180016ac4  retn
```
