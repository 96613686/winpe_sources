# EfspEnablePrivilege(long)

- ea: `0x180008aec`
- end: `0x180008bc8`
- name: `?EfspEnablePrivilege@@YAKJ@Z`
- size: `220`
- prototype: `unsigned int __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009b2c`

## callees

- `0x1800064f4`
- `0x180008aec`
- `0x180012040`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008b12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008b12`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008b2b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008b2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008bad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008bad`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180008b95`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180008b95`

## pseudocode

```c
__int64 __fastcall EfspEnablePrivilege()
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  int v2; // ecx
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-20h] BYREF

  TokenHandle = 0;
  NewState = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x28u, 1, &TokenHandle) )
  {
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Attributes = 2;
    NewState.Privileges[0].Luid = (LUID)18LL;
    AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, 0, 0);
    LastError = GetLastError();
  }
  else
  {
    LastError = GetLastError();
    fnEfsLogTrace1(v2, (unsigned int)EFS_API_ERROR, LastError, 11, 241);
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x180008aec  push    rbx
0x180008aee  sub     rsp, 50h
0x180008af2  mov     rax, cs:__security_cookie
0x180008af9  xor     rax, rsp
0x180008afc  mov     [rsp+58h+var_10], rax
0x180008b01  xorps   xmm0, xmm0
0x180008b04  mov     [rsp+58h+TokenHandle], 0
0x180008b0d  movups  xmmword ptr [rsp+58h+NewState.PrivilegeCount], xmm0
0x180008b12  call    cs:__imp_GetCurrentThread
0x180008b18  mov     ebx, 1
0x180008b1d  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x180008b22  mov     rcx, rax; ThreadHandle
0x180008b25  mov     r8d, ebx; OpenAsSelf
0x180008b28  lea     edx, [rbx+27h]; DesiredAccess
0x180008b2b  call    cs:__imp_OpenThreadToken
0x180008b31  test    eax, eax
0x180008b33  jnz     short loc_180008B5C
0x180008b35  call    cs:__imp_GetLastError
0x180008b3b  mov     r9d, 0Bh
0x180008b41  mov     dword ptr [rsp+58h+PreviousState], 0BF1h
0x180008b49  mov     r8d, eax
0x180008b4c  lea     rdx, EFS_API_ERROR
0x180008b53  mov     ebx, eax
0x180008b55  call    fnEfsLogTrace1
0x180008b5a  jmp     short loc_180008BA3
0x180008b5c  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x180008b61  lea     r8, [rsp+58h+NewState]; NewState
0x180008b66  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x180008b6f  mov     r9d, 10h; BufferLength
0x180008b75  xor     edx, edx; DisableAllPrivileges
0x180008b77  mov     [rsp+58h+PreviousState], 0; PreviousState
0x180008b80  mov     [rsp+58h+NewState.PrivilegeCount], ebx
0x180008b84  mov     [rsp+58h+NewState.Privileges.Attributes], 2
0x180008b8c  mov     qword ptr [rsp+58h+NewState.Privileges.Luid.LowPart], 12h
0x180008b95  call    cs:__imp_AdjustTokenPrivileges
0x180008b9b  call    cs:__imp_GetLastError
0x180008ba1  mov     ebx, eax
0x180008ba3  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x180008ba8  test    rcx, rcx
0x180008bab  jz      short loc_180008BB3
0x180008bad  call    cs:__imp_CloseHandle
0x180008bb3  mov     eax, ebx
0x180008bb5  mov     rcx, [rsp+58h+var_10]
0x180008bba  xor     rcx, rsp; StackCookie
0x180008bbd  call    __security_check_cookie
0x180008bc2  add     rsp, 50h
0x180008bc6  pop     rbx
0x180008bc7  retn
```
