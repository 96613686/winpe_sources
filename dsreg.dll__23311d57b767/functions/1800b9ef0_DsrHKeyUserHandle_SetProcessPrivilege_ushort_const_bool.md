# DsrHKeyUserHandle::SetProcessPrivilege(ushort const *,bool)

- ea: `0x1800b9ef0`
- end: `0x1800ba096`
- name: `?SetProcessPrivilege@DsrHKeyUserHandle@@CAJPEBG_N@Z`
- size: `422`
- prototype: `__int64 __fastcall(LPCWSTR lpName, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800b9a34`

## callees

- `0x1800084f4`
- `0x18000bac0`
- `0x1800307c4`
- `0x180044300`
- `0x1800b9ef0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b9f7d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b9f7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b9f6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b9f6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9f87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9fbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba020`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9f87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9fbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba020`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800ba016`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800ba016`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ba05b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ba05b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800b9fb5`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800b9fb5`

## string_xrefs

- `0x1800ba039`: `AdjustTokenPrivileges`
- `0x1800b9fd8`: `LookupPrivilegeValue`
- `0x1800b9f2c`: `DsrHKeyUserHandle::SetProcessPrivilege`
- `0x1800b9f3c`: `Privilege`
- `0x1800b9f57`: `Privilege`

## pseudocode

```c
__int64 __fastcall DsrHKeyUserHandle::SetProcessPrivilege(LPCWSTR lpName, unsigned __int8 a2)
{
  int v2; // esi
  signed int v4; // ebx
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  const wchar_t *v7; // r8
  signed int v8; // eax
  signed int v9; // eax
  void *TokenHandle; // [rsp+30h] [rbp-30h] BYREF
  _LUID Luid; // [rsp+38h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-20h] BYREF

  v2 = a2;
  TokenHandle = 0;
  Luid = 0;
  NewState = 0;
  if ( !lpName )
  {
    v4 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"DsrHKeyUserHandle::SetProcessPrivilege", L"Privilege");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"DsrHKeyUserHandle::SetProcessPrivilege", L"Privilege");
    goto LABEL_19;
  }
  v4 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
    {
      v7 = L"GetCurrentProcess";
LABEL_18:
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"DsrHKeyUserHandle::SetProcessPrivilege",
        v7,
        (unsigned int)v4);
      goto LABEL_19;
    }
  }
  if ( !LookupPrivilegeValueW(0, lpName, &Luid) )
  {
    v8 = GetLastError();
    v4 = v8;
    if ( v8 > 0 )
      v4 = (unsigned __int16)v8 | 0x80070000;
    if ( v4 < 0 )
    {
      v7 = L"LookupPrivilegeValue";
      goto LABEL_18;
    }
  }
  NewState.Privileges[0].Luid = Luid;
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Attributes = 2 * v2;
  if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0) )
  {
    v9 = GetLastError();
    v4 = v9;
    if ( v9 > 0 )
      v4 = (unsigned __int16)v9 | 0x80070000;
    if ( v4 < 0 )
    {
      v7 = L"AdjustTokenPrivileges";
      goto LABEL_18;
    }
  }
LABEL_19:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"DsrHKeyUserHandle::SetProcessPrivilege", (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800b9ef0  mov     [rsp-18h+arg_8], rbx
0x1800b9ef5  mov     [rsp-18h+arg_10], rsi
0x1800b9efa  push    rbp
0x1800b9efb  push    rdi
0x1800b9efc  push    r15
0x1800b9efe  mov     rbp, rsp
0x1800b9f01  sub     rsp, 60h
0x1800b9f05  mov     rax, cs:__security_cookie
0x1800b9f0c  xor     rax, rsp
0x1800b9f0f  mov     [rbp+var_10], rax
0x1800b9f13  movzx   esi, dl
0x1800b9f16  xorps   xmm0, xmm0
0x1800b9f19  mov     [rbp+TokenHandle], 0
0x1800b9f21  mov     rdi, rcx
0x1800b9f24  mov     qword ptr [rbp+Luid.LowPart], 0
0x1800b9f2c  lea     r15, aDsrhkeyuserhan_0; "DsrHKeyUserHandle::SetProcessPrivilege"
0x1800b9f33  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x1800b9f37  test    rcx, rcx
0x1800b9f3a  jnz     short loc_1800B9F6B
0x1800b9f3c  lea     r8, aPrivilege; "Privilege"
0x1800b9f43  mov     rdx, r15
0x1800b9f46  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800b9f4d  mov     ebx, 80070057h
0x1800b9f52  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b9f57  lea     rdx, aPrivilege; "Privilege"
0x1800b9f5e  mov     rcx, r15; unsigned __int16 *
0x1800b9f61  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800b9f66  jmp     loc_1800BA052
0x1800b9f6b  xor     ebx, ebx
0x1800b9f6d  call    cs:__imp_GetCurrentProcess
0x1800b9f73  mov     rcx, rax; ProcessHandle
0x1800b9f76  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800b9f7a  lea     edx, [rbx+28h]; DesiredAccess
0x1800b9f7d  call    cs:__imp_OpenProcessToken
0x1800b9f83  test    eax, eax
0x1800b9f85  jnz     short loc_1800B9FAC
0x1800b9f87  call    cs:__imp_GetLastError
0x1800b9f8d  mov     ebx, eax
0x1800b9f8f  test    eax, eax
0x1800b9f91  jle     short loc_1800B9F9C
0x1800b9f93  movzx   ebx, ax
0x1800b9f96  or      ebx, 80070000h
0x1800b9f9c  test    ebx, ebx
0x1800b9f9e  jns     short loc_1800B9FAC
0x1800b9fa0  lea     r8, aGetcurrentproc; "GetCurrentProcess"
0x1800b9fa7  jmp     loc_1800BA040
0x1800b9fac  lea     r8, [rbp+Luid]; lpLuid
0x1800b9fb0  mov     rdx, rdi; lpName
0x1800b9fb3  xor     ecx, ecx; lpSystemName
0x1800b9fb5  call    cs:__imp_LookupPrivilegeValueW
0x1800b9fbb  test    eax, eax
0x1800b9fbd  jnz     short loc_1800B9FE1
0x1800b9fbf  call    cs:__imp_GetLastError
0x1800b9fc5  mov     ebx, eax
0x1800b9fc7  test    eax, eax
0x1800b9fc9  jle     short loc_1800B9FD4
0x1800b9fcb  movzx   ebx, ax
0x1800b9fce  or      ebx, 80070000h
0x1800b9fd4  test    ebx, ebx
0x1800b9fd6  jns     short loc_1800B9FE1
0x1800b9fd8  lea     r8, aLookupprivileg_0; "LookupPrivilegeValue"
0x1800b9fdf  jmp     short loc_1800BA040
0x1800b9fe1  mov     rax, qword ptr [rbp+Luid.LowPart]
0x1800b9fe5  lea     r8, [rbp+NewState]; NewState
0x1800b9fe9  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800b9fed  xor     r9d, r9d; BufferLength
0x1800b9ff0  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x1800b9ff4  xor     edx, edx; DisableAllPrivileges
0x1800b9ff6  mov     eax, esi
0x1800b9ff8  mov     [rsp+60h+ReturnLength], 0; ReturnLength
0x1800ba001  add     eax, eax
0x1800ba003  mov     [rbp+NewState.PrivilegeCount], 1
0x1800ba00a  mov     [rbp+NewState.Privileges.Attributes], eax
0x1800ba00d  mov     [rsp+60h+PreviousState], 0; PreviousState
0x1800ba016  call    cs:__imp_AdjustTokenPrivileges
0x1800ba01c  test    eax, eax
0x1800ba01e  jnz     short loc_1800BA052
0x1800ba020  call    cs:__imp_GetLastError
0x1800ba026  mov     ebx, eax
0x1800ba028  test    eax, eax
0x1800ba02a  jle     short loc_1800BA035
0x1800ba02c  movzx   ebx, ax
0x1800ba02f  or      ebx, 80070000h
0x1800ba035  test    ebx, ebx
0x1800ba037  jns     short loc_1800BA052
0x1800ba039  lea     r8, aAdjusttokenpri; "AdjustTokenPrivileges"
0x1800ba040  mov     r9d, ebx
0x1800ba043  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800ba04a  mov     rdx, r15
0x1800ba04d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800ba052  mov     rcx, [rbp+TokenHandle]; hObject
0x1800ba056  test    rcx, rcx
0x1800ba059  jz      short loc_1800BA061
0x1800ba05b  call    cs:__imp_CloseHandle
0x1800ba061  mov     r8d, ebx
0x1800ba064  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x1800ba06b  mov     rdx, r15
0x1800ba06e  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800ba073  mov     eax, ebx
0x1800ba075  mov     rcx, [rbp+var_10]
0x1800ba079  xor     rcx, rsp; StackCookie
0x1800ba07c  call    __security_check_cookie
0x1800ba081  lea     r11, [rsp+60h+var_s0]
0x1800ba086  mov     rbx, [r11+28h]
0x1800ba08a  mov     rsi, [r11+30h]
0x1800ba08e  mov     rsp, r11
0x1800ba091  pop     r15
0x1800ba093  pop     rdi
0x1800ba094  pop     rbp
0x1800ba095  retn
```
