# CngSetAuditingInterface

- ea: `0x180060fcc`
- end: `0x180061148`
- name: `CngSetAuditingInterface`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180046630`

## callees

- `0x18000af80`
- `0x180060fcc`
- `0x180062310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006102d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006103d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006104d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800610b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800610c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800610d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006102d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006103d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006104d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800610b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800610c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800610d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180061005`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180061005`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18006101d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18006101d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061122`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061122`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x1800610a5`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x1800610a5`

## string_xrefs

- `0x180061071`: `onecore\ds\security\cryptoapi\ncrypt\common\audit.c`

## pseudocode

```c
__int64 __fastcall CngSetAuditingInterface(__int64 a1)
{
  HANDLE CurrentProcess; // rax
  unsigned int LastError; // ebx
  __int64 v4; // r9
  __int64 v5; // rcx
  WINBOOL pfResult; // [rsp+20h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-28h] BYREF
  struct _PRIVILEGE_SET RequiredPrivileges; // [rsp+30h] [rbp-20h] BYREF

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
    v4 = 86;
LABEL_6:
    v5 = LastError;
LABEL_7:
    DebugTraceError(v5, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\audit.c", v4);
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
    v4 = 100;
    goto LABEL_6;
  }
  if ( !pfResult )
  {
    LastError = -1073741727;
    v4 = 107;
    v5 = 3221225569LL;
    goto LABEL_7;
  }
  g_pAuditingFuncs = a1;
  LastError = 0;
LABEL_16:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x180060fcc  mov     [rsp-8+arg_0], rbx
0x180060fd1  push    rbp
0x180060fd2  mov     rbp, rsp
0x180060fd5  sub     rsp, 50h
0x180060fd9  mov     rax, cs:__security_cookie
0x180060fe0  xor     rax, rsp
0x180060fe3  mov     [rbp+var_8], rax
0x180060fe7  xorps   xmm0, xmm0
0x180060fea  mov     [rbp+TokenHandle], 0
0x180060ff2  xor     eax, eax
0x180060ff4  mov     [rbp+pfResult], 0
0x180060ffb  movups  xmmword ptr [rbp+RequiredPrivileges.PrivilegeCount], xmm0
0x180060fff  mov     [rbp+RequiredPrivileges.Privilege.Attributes], eax
0x180061002  mov     rbx, rcx
0x180061005  call    cs:__imp_GetCurrentProcess
0x18006100c  nop     dword ptr [rax+rax+00h]
0x180061011  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180061015  mov     edx, 8; DesiredAccess
0x18006101a  mov     rcx, rax; ProcessHandle
0x18006101d  call    cs:__imp_OpenProcessToken
0x180061024  nop     dword ptr [rax+rax+00h]
0x180061029  test    eax, eax
0x18006102b  jnz     short loc_180061082
0x18006102d  call    cs:__imp_GetLastError
0x180061034  nop     dword ptr [rax+rax+00h]
0x180061039  test    eax, eax
0x18006103b  jg      short loc_18006104D
0x18006103d  call    cs:__imp_GetLastError
0x180061044  nop     dword ptr [rax+rax+00h]
0x180061049  mov     ebx, eax
0x18006104b  jmp     short loc_180061062
0x18006104d  call    cs:__imp_GetLastError
0x180061054  nop     dword ptr [rax+rax+00h]
0x180061059  movzx   ebx, ax
0x18006105c  or      ebx, 0C0070000h
0x180061062  mov     r9d, 56h ; 'V'
0x180061068  mov     ecx, ebx
0x18006106a  lea     rdx, aStatus; "Status"
0x180061071  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180061078  call    DebugTraceError
0x18006107d  jmp     loc_180061119
0x180061082  mov     rcx, [rbp+TokenHandle]; ClientToken
0x180061086  lea     r8, [rbp+pfResult]; pfResult
0x18006108a  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x18006108e  mov     qword ptr [rbp+RequiredPrivileges.PrivilegeCount], 1
0x180061096  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.LowPart], 7
0x18006109e  mov     [rbp+RequiredPrivileges.Privilege.Attributes], 0
0x1800610a5  call    cs:__imp_PrivilegeCheck
0x1800610ac  nop     dword ptr [rax+rax+00h]
0x1800610b1  test    eax, eax
0x1800610b3  jnz     short loc_1800610F5
0x1800610b5  call    cs:__imp_GetLastError
0x1800610bc  nop     dword ptr [rax+rax+00h]
0x1800610c1  test    eax, eax
0x1800610c3  jg      short loc_1800610D5
0x1800610c5  call    cs:__imp_GetLastError
0x1800610cc  nop     dword ptr [rax+rax+00h]
0x1800610d1  mov     ebx, eax
0x1800610d3  jmp     short loc_1800610EA
0x1800610d5  call    cs:__imp_GetLastError
0x1800610dc  nop     dword ptr [rax+rax+00h]
0x1800610e1  movzx   ebx, ax
0x1800610e4  or      ebx, 0C0070000h
0x1800610ea  mov     r9d, 64h ; 'd'
0x1800610f0  jmp     loc_180061068
0x1800610f5  cmp     [rbp+pfResult], 0
0x1800610f9  jnz     short loc_180061110
0x1800610fb  mov     ebx, 0C0000061h
0x180061100  mov     r9d, 6Bh ; 'k'
0x180061106  mov     ecx, 0C0000061h
0x18006110b  jmp     loc_18006106A
0x180061110  mov     cs:g_pAuditingFuncs, rbx
0x180061117  xor     ebx, ebx
0x180061119  mov     rcx, [rbp+TokenHandle]; hObject
0x18006111d  test    rcx, rcx
0x180061120  jz      short loc_18006112E
0x180061122  call    cs:__imp_CloseHandle
0x180061129  nop     dword ptr [rax+rax+00h]
0x18006112e  mov     eax, ebx
0x180061130  mov     rcx, [rbp+var_8]
0x180061134  xor     rcx, rsp; StackCookie
0x180061137  call    __security_check_cookie
0x18006113c  mov     rbx, [rsp+50h+arg_0]
0x180061141  add     rsp, 50h
0x180061145  pop     rbp
0x180061146  retn
```
