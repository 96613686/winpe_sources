# Microsoft::Diagnostics::ThreadPrivilegeManager::UpdatePrivilege(ulong,bool)

- ea: `0x1801d2b8c`
- end: `0x1801d2ca4`
- name: `?UpdatePrivilege@ThreadPrivilegeManager@Diagnostics@Microsoft@@QEAAJK_N@Z`
- size: `280`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle, unsigned int, bool)`
- caller_count: `7`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800e65f4`
- `0x180154658`
- `0x180164c0c`
- `0x180181d60`
- `0x18026eee4`
- `0x1802e4824`
- `0x18032cdf0`

## callees

- `0x180064e34`
- `0x180064e6c`
- `0x18008abf4`
- `0x1801d2b8c`
- `0x18020aac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d2c63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d2c63`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801d2c02`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801d2c02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801d2bef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801d2bef`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1801d2c5d`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1801d2c5d`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1801d2bbe`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1801d2bbe`

## string_xrefs

- `0x1801d2bcd`: `onecore\base\telemetry\utc\common\threadprivilegemanager.cpp`
- `0x1801d2c11`: `onecore\base\telemetry\utc\common\threadprivilegemanager.cpp`
- `0x1801d2c75`: `onecore\base\telemetry\utc\common\threadprivilegemanager.cpp`

## pseudocode

```c
int __fastcall Microsoft::Diagnostics::ThreadPrivilegeManager::UpdatePrivilege(void **TokenHandle)
{
  void *v2; // rcx
  const char *v3; // r9
  int result; // eax
  const char *v5; // r9
  HANDLE CurrentThread; // rax
  const char *v7; // r9
  DWORD LastError; // eax
  unsigned int PreviousState; // [rsp+20h] [rbp-38h]
  _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = *TokenHandle;
  if ( (((unsigned __int64)v2 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    if ( !*((_BYTE *)TokenHandle + 8) )
    {
      if ( !ImpersonateSelf(SecurityImpersonation) )
      {
        result = wil::details::in1diag3::Return_GetLastError(
                   retaddr,
                   (void *)0x2C,
                   (unsigned int)"onecore\\base\\telemetry\\utc\\common\\threadprivilegemanager.cpp",
                   v3);
        goto LABEL_14;
      }
      *((_BYTE *)TokenHandle + 8) = 1;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      TokenHandle,
      0);
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0x20u, 0, TokenHandle) )
    {
      result = wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x34,
                 (unsigned int)"onecore\\base\\telemetry\\utc\\common\\threadprivilegemanager.cpp",
                 v7);
      goto LABEL_14;
    }
    v2 = *TokenHandle;
  }
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Luid = (LUID)20LL;
  NewState.Privileges[0].Attributes = 2;
  AdjustTokenPrivileges(v2, 0, &NewState, 0x10u, 0, 0);
  LastError = GetLastError();
  if ( LastError )
    result = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x4D,
               (unsigned int)"onecore\\base\\telemetry\\utc\\common\\threadprivilegemanager.cpp",
               (const char *)LastError,
               PreviousState);
  else
    result = 0;
LABEL_14:
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      result = wil::details::in1diag3::Return_CaughtException(
                 retaddr,
                 (void *)0x51,
                 (unsigned int)"onecore\\base\\telemetry\\utc\\common\\threadprivilegemanager.cpp",
                 v5);
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x1801d2b8c  push    rbx
0x1801d2b8e  sub     rsp, 50h
0x1801d2b92  mov     rax, cs:__security_cookie
0x1801d2b99  xor     rax, rsp
0x1801d2b9c  mov     [rsp+58h+var_10], rax
0x1801d2ba1  mov     rbx, rcx
0x1801d2ba4  mov     rcx, [rcx]
0x1801d2ba7  lea     rax, [rcx+1]
0x1801d2bab  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801d2bb1  jnz     short loc_1801D2C25
0x1801d2bb3  cmp     byte ptr [rbx+8], 0
0x1801d2bb7  jnz     short loc_1801D2BE5
0x1801d2bb9  mov     ecx, 2; ImpersonationLevel
0x1801d2bbe  call    cs:__imp_ImpersonateSelf
0x1801d2bc4  test    eax, eax
0x1801d2bc6  jnz     short loc_1801D2BE1
0x1801d2bc8  mov     rcx, [rsp+58h]; this
0x1801d2bcd  lea     r8, aOnecoreBaseTel_30; "onecore\\base\\telemetry\\utc\\common\\"...
0x1801d2bd4  lea     edx, [rax+2Ch]; void *
0x1801d2bd7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801d2bdc  jmp     loc_1801D2C90
0x1801d2be1  mov     byte ptr [rbx+8], 1
0x1801d2be5  xor     edx, edx
0x1801d2be7  mov     rcx, rbx
0x1801d2bea  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1801d2bef  call    cs:__imp_GetCurrentThread
0x1801d2bf5  mov     r9, rbx; TokenHandle
0x1801d2bf8  xor     r8d, r8d; OpenAsSelf
0x1801d2bfb  lea     edx, [r8+20h]; DesiredAccess
0x1801d2bff  mov     rcx, rax; ThreadHandle
0x1801d2c02  call    cs:__imp_OpenThreadToken
0x1801d2c08  test    eax, eax
0x1801d2c0a  jnz     short loc_1801D2C22
0x1801d2c0c  mov     rcx, [rsp+58h]; this
0x1801d2c11  lea     r8, aOnecoreBaseTel_30; "onecore\\base\\telemetry\\utc\\common\\"...
0x1801d2c18  lea     edx, [rax+34h]; void *
0x1801d2c1b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801d2c20  jmp     short loc_1801D2C90
0x1801d2c22  mov     rcx, [rbx]; TokenHandle
0x1801d2c25  mov     [rsp+58h+NewState.PrivilegeCount], 1
0x1801d2c2d  mov     qword ptr [rsp+58h+NewState.Privileges.Luid.LowPart], 14h
0x1801d2c36  mov     [rsp+58h+NewState.Privileges.Attributes], 2
0x1801d2c3e  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x1801d2c47  mov     [rsp+58h+PreviousState], 0; unsigned int
0x1801d2c50  mov     r9d, 10h; BufferLength
0x1801d2c56  lea     r8, [rsp+58h+NewState]; NewState
0x1801d2c5b  xor     edx, edx; DisableAllPrivileges
0x1801d2c5d  call    cs:__imp_AdjustTokenPrivileges
0x1801d2c63  call    cs:__imp_GetLastError
0x1801d2c69  test    eax, eax
0x1801d2c6b  jz      short loc_1801D2C88
0x1801d2c6d  mov     rcx, [rsp+58h]; this
0x1801d2c72  mov     r9d, eax; char *
0x1801d2c75  lea     r8, aOnecoreBaseTel_30; "onecore\\base\\telemetry\\utc\\common\\"...
0x1801d2c7c  mov     edx, 4Dh ; 'M'; void *
0x1801d2c81  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801d2c86  jmp     short loc_1801D2C90
0x1801d2c88  xor     eax, eax
0x1801d2c8a  jmp     short loc_1801D2C90
0x1801d2c8c  mov     eax, [rsp+58h+var_28]
0x1801d2c90  mov     rcx, [rsp+58h+var_10]
0x1801d2c95  xor     rcx, rsp; StackCookie
0x1801d2c98  call    __security_check_cookie
0x1801d2c9d  add     rsp, 50h
0x1801d2ca1  pop     rbx
0x1801d2ca2  retn
```
