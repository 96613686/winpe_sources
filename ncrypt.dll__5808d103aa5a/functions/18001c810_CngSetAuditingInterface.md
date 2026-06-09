# CngSetAuditingInterface

- ea: `0x18001c810`
- end: `0x18001c93f`
- name: `CngSetAuditingInterface`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ba00`

## callees

- `0x18000e120`
- `0x18001c810`
- `0x18001f1b0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x18001c8c5`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x18001c8c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c862`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c86c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c876`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c8cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c8d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c8e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c862`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c86c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c876`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c8cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c8d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c8e3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001c858`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001c858`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001c846`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001c846`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c920`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c920`

## string_xrefs

- `0x18001c894`: `onecore\ds\security\cryptoapi\ncrypt\common\audit.c`

## pseudocode

```c
__int64 CngSetAuditingInterface()
{
  HANDLE CurrentProcess; // rax
  unsigned int LastError; // ebx
  __int64 v2; // r9
  __int64 v3; // rcx
  WINBOOL pfResult; // [rsp+20h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-28h] BYREF
  _PRIVILEGE_SET RequiredPrivileges; // [rsp+30h] [rbp-20h] BYREF

  TokenHandle = 0;
  pfResult = 0;
  memset(&RequiredPrivileges, 0, sizeof(RequiredPrivileges));
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0xC0070000;
    else
      LastError = GetLastError();
    v2 = 86;
LABEL_6:
    v3 = LastError;
LABEL_7:
    DebugTraceError(v3, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\audit.c", v2);
    goto LABEL_16;
  }
  *(_QWORD *)&RequiredPrivileges.PrivilegeCount = 1;
  RequiredPrivileges.Privilege[0].Luid = (LUID)7LL;
  RequiredPrivileges.Privilege[0].Attributes = 0;
  if ( !PrivilegeCheck(TokenHandle, &RequiredPrivileges, &pfResult) )
  {
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0xC0070000;
    else
      LastError = GetLastError();
    v2 = 100;
    goto LABEL_6;
  }
  if ( !pfResult )
  {
    LastError = -1073741727;
    v2 = 107;
    v3 = 3221225569LL;
    goto LABEL_7;
  }
  LastError = 0;
LABEL_16:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x18001c810  mov     [rsp-8+arg_0], rbx
0x18001c815  push    rbp
0x18001c816  mov     rbp, rsp
0x18001c819  sub     rsp, 50h
0x18001c81d  mov     rax, cs:__security_cookie
0x18001c824  xor     rax, rsp
0x18001c827  mov     [rbp+var_8], rax
0x18001c82b  xorps   xmm0, xmm0
0x18001c82e  mov     [rbp+TokenHandle], 0
0x18001c836  xor     eax, eax
0x18001c838  mov     [rbp+pfResult], 0
0x18001c83f  movups  xmmword ptr [rbp+RequiredPrivileges.PrivilegeCount], xmm0
0x18001c843  mov     [rbp+RequiredPrivileges.Privilege.Attributes], eax
0x18001c846  call    cs:__imp_GetCurrentProcess
0x18001c84c  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18001c850  mov     edx, 8; DesiredAccess
0x18001c855  mov     rcx, rax; ProcessHandle
0x18001c858  call    cs:__imp_OpenProcessToken
0x18001c85e  test    eax, eax
0x18001c860  jnz     short loc_18001C8A2
0x18001c862  call    cs:__imp_GetLastError
0x18001c868  test    eax, eax
0x18001c86a  jg      short loc_18001C876
0x18001c86c  call    cs:__imp_GetLastError
0x18001c872  mov     ebx, eax
0x18001c874  jmp     short loc_18001C885
0x18001c876  call    cs:__imp_GetLastError
0x18001c87c  movzx   ebx, ax
0x18001c87f  or      ebx, 0C0070000h
0x18001c885  mov     r9d, 56h ; 'V'
0x18001c88b  mov     ecx, ebx
0x18001c88d  lea     rdx, aStatus; "Status"
0x18001c894  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001c89b  call    DebugTraceError
0x18001c8a0  jmp     short loc_18001C917
0x18001c8a2  mov     rcx, [rbp+TokenHandle]; ClientToken
0x18001c8a6  lea     r8, [rbp+pfResult]; pfResult
0x18001c8aa  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x18001c8ae  mov     qword ptr [rbp+RequiredPrivileges.PrivilegeCount], 1
0x18001c8b6  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.LowPart], 7
0x18001c8be  mov     [rbp+RequiredPrivileges.Privilege.Attributes], 0
0x18001c8c5  call    cs:__imp_PrivilegeCheck
0x18001c8cb  test    eax, eax
0x18001c8cd  jnz     short loc_18001C8FA
0x18001c8cf  call    cs:__imp_GetLastError
0x18001c8d5  test    eax, eax
0x18001c8d7  jg      short loc_18001C8E3
0x18001c8d9  call    cs:__imp_GetLastError
0x18001c8df  mov     ebx, eax
0x18001c8e1  jmp     short loc_18001C8F2
0x18001c8e3  call    cs:__imp_GetLastError
0x18001c8e9  movzx   ebx, ax
0x18001c8ec  or      ebx, 0C0070000h
0x18001c8f2  mov     r9d, 64h ; 'd'
0x18001c8f8  jmp     short loc_18001C88B
0x18001c8fa  cmp     [rbp+pfResult], 0
0x18001c8fe  jnz     short loc_18001C915
0x18001c900  mov     ebx, 0C0000061h
0x18001c905  mov     r9d, 6Bh ; 'k'
0x18001c90b  mov     ecx, 0C0000061h
0x18001c910  jmp     loc_18001C88D
0x18001c915  xor     ebx, ebx
0x18001c917  mov     rcx, [rbp+TokenHandle]; hObject
0x18001c91b  test    rcx, rcx
0x18001c91e  jz      short loc_18001C926
0x18001c920  call    cs:__imp_CloseHandle
0x18001c926  mov     eax, ebx
0x18001c928  mov     rcx, [rbp+var_8]
0x18001c92c  xor     rcx, rsp; StackCookie
0x18001c92f  call    __security_check_cookie
0x18001c934  mov     rbx, [rsp+50h+arg_0]
0x18001c939  add     rsp, 50h
0x18001c93d  pop     rbp
0x18001c93e  retn
```
