# AddPrivilege

- ea: `0x18002a694`
- end: `0x18002a78e`
- name: `AddPrivilege`
- size: `250`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002cd1c`

## callees

- `0x180007f10`
- `0x1800136d4`
- `0x18001c808`
- `0x18001d810`
- `0x18002a694`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002a731`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002a731`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a741`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a741`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002a6ce`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002a6ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002a6b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002a6b5`

## string_xrefs

- `0x18002a6e3`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002a755`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AddPrivilege(LUID a1)
{
  HANDLE CurrentProcess; // rax
  const char *v3; // r9
  DWORD LastError; // ebx
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  TokenHandle = 0;
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
      DebugTraceError(LastError, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 7023);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1B5E,
                  (unsigned int)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
                  v3);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x18002a694  push    rbx
0x18002a696  sub     rsp, 50h
0x18002a69a  mov     rax, cs:__security_cookie
0x18002a6a1  xor     rax, rsp
0x18002a6a4  mov     [rsp+58h+var_10], rax
0x18002a6a9  mov     rbx, rcx
0x18002a6ac  mov     [rsp+58h+TokenHandle], 0
0x18002a6b5  call    cs:__imp_GetCurrentProcess
0x18002a6bc  nop     dword ptr [rax+rax+00h]
0x18002a6c1  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x18002a6c6  mov     edx, 28h ; '('; DesiredAccess
0x18002a6cb  mov     rcx, rax; ProcessHandle
0x18002a6ce  call    cs:__imp_OpenProcessToken
0x18002a6d5  nop     dword ptr [rax+rax+00h]
0x18002a6da  test    eax, eax
0x18002a6dc  jnz     short loc_18002A6F8
0x18002a6de  mov     rcx, [rsp+58h]; this
0x18002a6e3  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002a6ea  mov     edx, 1B5Eh; void *
0x18002a6ef  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002a6f4  mov     ebx, eax
0x18002a6f6  jmp     short loc_18002A76E
0x18002a6f8  mov     [rsp+58h+NewState.PrivilegeCount], 1
0x18002a700  mov     [rsp+58h+NewState.Privileges.Attributes], 2
0x18002a708  mov     qword ptr [rsp+58h+NewState.Privileges.Luid.LowPart], rbx
0x18002a70d  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x18002a716  mov     [rsp+58h+PreviousState], 0; PreviousState
0x18002a71f  mov     r9d, 10h; BufferLength
0x18002a725  lea     r8, [rsp+58h+NewState]; NewState
0x18002a72a  xor     edx, edx; DisableAllPrivileges
0x18002a72c  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18002a731  call    cs:__imp_AdjustTokenPrivileges
0x18002a738  nop     dword ptr [rax+rax+00h]
0x18002a73d  test    eax, eax
0x18002a73f  jnz     short loc_18002A76C
0x18002a741  call    cs:__imp_GetLastError
0x18002a748  nop     dword ptr [rax+rax+00h]
0x18002a74d  mov     ebx, eax
0x18002a74f  mov     r9d, 1B6Fh
0x18002a755  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002a75c  lea     rdx, aDwerror; "dwError"
0x18002a763  mov     ecx, eax
0x18002a765  call    DebugTraceError
0x18002a76a  jmp     short loc_18002A76E
0x18002a76c  xor     ebx, ebx
0x18002a76e  lea     rcx, [rsp+58h+TokenHandle]
0x18002a773  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002a778  mov     eax, ebx
0x18002a77a  mov     rcx, [rsp+58h+var_10]
0x18002a77f  xor     rcx, rsp; StackCookie
0x18002a782  call    __security_check_cookie
0x18002a787  add     rsp, 50h
0x18002a78b  pop     rbx
0x18002a78c  retn
```
