# ObtainPrivilege(_LUID)

- ea: `0x1800375a0`
- end: `0x18003769a`
- name: `?ObtainPrivilege@@YAKU_LUID@@@Z`
- size: `250`
- prototype: `__int64 __fastcall(LUID)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800376a0`

## callees

- `0x180007f10`
- `0x180013bec`
- `0x18001d810`
- `0x1800375a0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18003763d`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18003763d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800375f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003764d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800375f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003764d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800375e4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800375e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800375cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800375cb`

## string_xrefs

- `0x180037661`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`

## pseudocode

```c
__int64 __fastcall ObtainPrivilege(LUID a1)
{
  HANDLE CurrentProcess; // rax
  DWORD LastError; // ebx
  void *TokenHandle; // [rsp+30h] [rbp-38h] BYREF
  void **p_TokenHandle; // [rsp+38h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-28h] BYREF

  TokenHandle = 0;
  p_TokenHandle = &TokenHandle;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Attributes = 2;
    NewState.Privileges[0].Luid = a1;
    if ( AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, 0, 0) )
    {
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
      DebugTraceError(LastError, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp", 1330);
    }
  }
  else
  {
    LastError = GetLastError();
  }
  ScopedCloseHandle::~ScopedCloseHandle(&p_TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x1800375a0  push    rbx
0x1800375a2  sub     rsp, 60h
0x1800375a6  mov     rax, cs:__security_cookie
0x1800375ad  xor     rax, rsp
0x1800375b0  mov     [rsp+68h+var_18], rax
0x1800375b5  mov     rbx, rcx
0x1800375b8  mov     [rsp+68h+TokenHandle], 0
0x1800375c1  lea     rax, [rsp+68h+TokenHandle]
0x1800375c6  mov     [rsp+68h+var_30], rax
0x1800375cb  call    cs:__imp_GetCurrentProcess
0x1800375d2  nop     dword ptr [rax+rax+00h]
0x1800375d7  mov     rcx, rax; ProcessHandle
0x1800375da  lea     r8, [rsp+68h+TokenHandle]; TokenHandle
0x1800375df  mov     edx, 28h ; '('; DesiredAccess
0x1800375e4  call    cs:__imp_OpenProcessToken
0x1800375eb  nop     dword ptr [rax+rax+00h]
0x1800375f0  test    eax, eax
0x1800375f2  jnz     short loc_180037604
0x1800375f4  call    cs:__imp_GetLastError
0x1800375fb  nop     dword ptr [rax+rax+00h]
0x180037600  mov     ebx, eax
0x180037602  jmp     short loc_18003767A
0x180037604  mov     [rsp+68h+NewState.PrivilegeCount], 1
0x18003760c  mov     [rsp+68h+NewState.Privileges.Attributes], 2
0x180037614  mov     qword ptr [rsp+68h+NewState.Privileges.Luid.LowPart], rbx
0x180037619  mov     [rsp+68h+ReturnLength], 0; ReturnLength
0x180037622  mov     [rsp+68h+PreviousState], 0; PreviousState
0x18003762b  mov     r9d, 10h; BufferLength
0x180037631  lea     r8, [rsp+68h+NewState]; NewState
0x180037636  xor     edx, edx; DisableAllPrivileges
0x180037638  mov     rcx, [rsp+68h+TokenHandle]; TokenHandle
0x18003763d  call    cs:__imp_AdjustTokenPrivileges
0x180037644  nop     dword ptr [rax+rax+00h]
0x180037649  test    eax, eax
0x18003764b  jnz     short loc_180037678
0x18003764d  call    cs:__imp_GetLastError
0x180037654  nop     dword ptr [rax+rax+00h]
0x180037659  mov     ebx, eax
0x18003765b  mov     r9d, 532h
0x180037661  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180037668  lea     rdx, aDwerror; "dwError"
0x18003766f  mov     ecx, eax
0x180037671  call    DebugTraceError
0x180037676  jmp     short loc_18003767A
0x180037678  xor     ebx, ebx
0x18003767a  lea     rcx, [rsp+68h+var_30]; this
0x18003767f  call    ??1ScopedCloseHandle@@QEAA@XZ; ScopedCloseHandle::~ScopedCloseHandle(void)
0x180037684  mov     eax, ebx
0x180037686  mov     rcx, [rsp+68h+var_18]
0x18003768b  xor     rcx, rsp; StackCookie
0x18003768e  call    __security_check_cookie
0x180037693  add     rsp, 60h
0x180037697  pop     rbx
0x180037698  retn
```
