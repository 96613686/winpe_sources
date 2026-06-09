# CTransactionToAuditLog::EnableAuditPrivilege(void)

- ea: `0x180022740`
- end: `0x180022810`
- name: `?EnableAuditPrivilege@CTransactionToAuditLog@@CAJXZ`
- size: `208`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800224ac`

## callees

- `0x180022740`
- `0x180055880`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002278b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002278b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800227f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800227f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022770`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022770`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180022781`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180022781`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800227d7`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800227d7`

## pseudocode

```c
__int64 CTransactionToAuditLog::EnableAuditPrivilege(void)
{
  unsigned int v0; // ebx
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-20h] BYREF

  v0 = 0;
  if ( !CTransactionToAuditLog::s_fPrivEnabled )
  {
    TokenHandle = 0;
    NewState = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle)
      && (NewState.PrivilegeCount = 1,
          NewState.Privileges[0].Attributes = 2,
          NewState.Privileges[0].Luid = (LUID)21LL,
          AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, 0, 0)) )
    {
      CTransactionToAuditLog::s_fPrivEnabled = 1;
    }
    else
    {
      LastError = GetLastError();
      v0 = LastError;
      if ( LastError > 0 )
        v0 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( TokenHandle )
      CloseHandle(TokenHandle);
  }
  return v0;
}

```

## disassembly

```asm
0x180022740  push    rbx
0x180022742  sub     rsp, 50h
0x180022746  mov     rax, cs:__security_cookie
0x18002274d  xor     rax, rsp
0x180022750  mov     [rsp+58h+var_10], rax
0x180022755  xor     ebx, ebx
0x180022757  cmp     cs:?s_fPrivEnabled@CTransactionToAuditLog@@0HA, ebx; int CTransactionToAuditLog::s_fPrivEnabled
0x18002275d  jnz     loc_1800227FB
0x180022763  xorps   xmm0, xmm0
0x180022766  mov     [rsp+58h+TokenHandle], rbx
0x18002276b  movups  xmmword ptr [rsp+58h+NewState.PrivilegeCount], xmm0
0x180022770  call    cs:__imp_GetCurrentProcess
0x180022776  mov     rcx, rax; ProcessHandle
0x180022779  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x18002277e  lea     edx, [rbx+28h]; DesiredAccess
0x180022781  call    cs:__imp_OpenProcessToken
0x180022787  test    eax, eax
0x180022789  jnz     short loc_1800227A2
0x18002278b  call    cs:__imp_GetLastError
0x180022791  mov     ebx, eax
0x180022793  test    eax, eax
0x180022795  jle     short loc_1800227EB
0x180022797  movzx   ebx, ax
0x18002279a  or      ebx, 80070000h
0x1800227a0  jmp     short loc_1800227EB
0x1800227a2  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x1800227a7  lea     r8, [rsp+58h+NewState]; NewState
0x1800227ac  mov     [rsp+58h+ReturnLength], rbx; ReturnLength
0x1800227b1  mov     r9d, 10h; BufferLength
0x1800227b7  xor     edx, edx; DisableAllPrivileges
0x1800227b9  mov     [rsp+58h+PreviousState], rbx; PreviousState
0x1800227be  mov     [rsp+58h+NewState.PrivilegeCount], 1
0x1800227c6  mov     [rsp+58h+NewState.Privileges.Attributes], 2
0x1800227ce  mov     qword ptr [rsp+58h+NewState.Privileges.Luid.LowPart], 15h
0x1800227d7  call    cs:__imp_AdjustTokenPrivileges
0x1800227dd  test    eax, eax
0x1800227df  jz      short loc_18002278B
0x1800227e1  mov     cs:?s_fPrivEnabled@CTransactionToAuditLog@@0HA, 1; int CTransactionToAuditLog::s_fPrivEnabled
0x1800227eb  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x1800227f0  test    rcx, rcx
0x1800227f3  jz      short loc_1800227FB
0x1800227f5  call    cs:__imp_CloseHandle
0x1800227fb  mov     eax, ebx
0x1800227fd  mov     rcx, [rsp+58h+var_10]
0x180022802  xor     rcx, rsp; StackCookie
0x180022805  call    __security_check_cookie
0x18002280a  add     rsp, 50h
0x18002280e  pop     rbx
0x18002280f  retn
```
