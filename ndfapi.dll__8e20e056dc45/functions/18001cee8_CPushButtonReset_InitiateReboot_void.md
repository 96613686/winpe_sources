# CPushButtonReset::InitiateReboot(void)

- ea: `0x18001cee8`
- end: `0x18001cff3`
- name: `?InitiateReboot@CPushButtonReset@@CAJXZ`
- size: `267`
- prototype: `signed int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001cc3c`

## callees

- `0x18001cee8`
- `0x18001f690`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x18001cf66`
- `ADVAPI32!OpenProcessToken` at `0x18001cf66`
- `KERNEL32!GetLastError` at `0x18001cf38`
- `KERNEL32!GetLastError` at `0x18001cf9b`
- `KERNEL32!GetLastError` at `0x18001cf38`
- `KERNEL32!GetLastError` at `0x18001cf9b`
- `KERNEL32!GetCurrentProcess` at `0x18001cf53`
- `KERNEL32!GetCurrentProcess` at `0x18001cf53`
- `KERNEL32!CloseHandle` at `0x18001cfd8`
- `KERNEL32!CloseHandle` at `0x18001cfd8`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x18001cfcb`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x18001cfcb`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18001cf91`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18001cf91`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18001cf2e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18001cf2e`

## string_xrefs

- `0x18001cf14`: `SeShutdownPrivilege`

## pseudocode

```c
signed int CPushButtonReset::InitiateReboot(void)
{
  signed int result; // eax
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int v3; // ebx
  HANDLE TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-20h] BYREF

  TokenHandle = 0;
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Luid = 0;
  NewState.Privileges[0].Attributes = 2;
  if ( LookupPrivilegeValueW(0, L"SeShutdownPrivilege", &NewState.Privileges[0].Luid)
    && (CurrentProcess = GetCurrentProcess(), OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle)) )
  {
    if ( AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0) )
    {
      InitiateSystemShutdownExW(0, 0, 0x12Cu, 0, 1, 0x14u);
      v3 = 0;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseHandle(TokenHandle);
    return v3;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18001cee8  push    rbx
0x18001ceea  sub     rsp, 50h
0x18001ceee  mov     rax, cs:__security_cookie
0x18001cef5  xor     rax, rsp
0x18001cef8  mov     [rsp+58h+var_10], rax
0x18001cefd  mov     ebx, 1
0x18001cf02  mov     [rsp+58h+TokenHandle], 0
0x18001cf0b  lea     r8, [rsp+58h+NewState.Privileges]; lpLuid
0x18001cf10  mov     [rsp+58h+NewState.PrivilegeCount], ebx
0x18001cf14  lea     rdx, Name; "SeShutdownPrivilege"
0x18001cf1b  mov     qword ptr [rsp+58h+NewState.Privileges.Luid.LowPart], 0
0x18001cf24  xor     ecx, ecx; lpSystemName
0x18001cf26  mov     [rsp+58h+NewState.Privileges.Attributes], 2
0x18001cf2e  call    cs:__imp_LookupPrivilegeValueW
0x18001cf34  test    eax, eax
0x18001cf36  jnz     short loc_18001CF53
0x18001cf38  call    cs:__imp_GetLastError
0x18001cf3e  test    eax, eax
0x18001cf40  jle     loc_18001CFE0
0x18001cf46  movzx   eax, ax
0x18001cf49  or      eax, 80070000h
0x18001cf4e  jmp     loc_18001CFE0
0x18001cf53  call    cs:__imp_GetCurrentProcess
0x18001cf59  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x18001cf5e  mov     edx, 28h ; '('; DesiredAccess
0x18001cf63  mov     rcx, rax; ProcessHandle
0x18001cf66  call    cs:__imp_OpenProcessToken
0x18001cf6c  test    eax, eax
0x18001cf6e  jz      short loc_18001CF38
0x18001cf70  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18001cf75  lea     r8, [rsp+58h+NewState]; NewState
0x18001cf7a  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x18001cf83  xor     r9d, r9d; BufferLength
0x18001cf86  xor     edx, edx; DisableAllPrivileges
0x18001cf88  mov     [rsp+58h+PreviousState], 0; PreviousState
0x18001cf91  call    cs:__imp_AdjustTokenPrivileges
0x18001cf97  test    eax, eax
0x18001cf99  jnz     short loc_18001CFB2
0x18001cf9b  call    cs:__imp_GetLastError
0x18001cfa1  mov     ebx, eax
0x18001cfa3  test    eax, eax
0x18001cfa5  jle     short loc_18001CFD3
0x18001cfa7  movzx   ebx, ax
0x18001cfaa  or      ebx, 80070000h
0x18001cfb0  jmp     short loc_18001CFD3
0x18001cfb2  mov     dword ptr [rsp+58h+ReturnLength], 14h; dwReason
0x18001cfba  xor     r9d, r9d; bForceAppsClosed
0x18001cfbd  xor     edx, edx; lpMessage
0x18001cfbf  mov     dword ptr [rsp+58h+PreviousState], ebx; bRebootAfterShutdown
0x18001cfc3  xor     ecx, ecx; lpMachineName
0x18001cfc5  mov     r8d, 12Ch; dwTimeout
0x18001cfcb  call    cs:__imp_InitiateSystemShutdownExW
0x18001cfd1  xor     ebx, ebx
0x18001cfd3  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18001cfd8  call    cs:__imp_CloseHandle
0x18001cfde  mov     eax, ebx
0x18001cfe0  mov     rcx, [rsp+58h+var_10]
0x18001cfe5  xor     rcx, rsp; StackCookie
0x18001cfe8  call    __security_check_cookie
0x18001cfed  add     rsp, 50h
0x18001cff1  pop     rbx
0x18001cff2  retn
```
