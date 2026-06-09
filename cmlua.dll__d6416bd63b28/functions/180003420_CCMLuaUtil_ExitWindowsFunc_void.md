# CCMLuaUtil::ExitWindowsFunc(void)

- ea: `0x180003420`
- end: `0x18000353c`
- name: `?ExitWindowsFunc@CCMLuaUtil@@UEAAJXZ`
- size: `284`
- prototype: `__int64 __fastcall(CCMLuaUtil *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x180003420`
- `0x1800054b0`

## import_xrefs

- `ADVAPI32!LookupPrivilegeValueW` at `0x180003491`
- `ADVAPI32!LookupPrivilegeValueW` at `0x180003491`
- `ADVAPI32!InitiateSystemShutdownW` at `0x1800034e4`
- `ADVAPI32!InitiateSystemShutdownW` at `0x1800034e4`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1800034c5`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18000350e`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1800034c5`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18000350e`
- `ADVAPI32!OpenProcessToken` at `0x18000345c`
- `ADVAPI32!OpenProcessToken` at `0x18000345c`
- `KERNEL32!GetCurrentProcess` at `0x18000344a`
- `KERNEL32!GetCurrentProcess` at `0x18000344a`
- `KERNEL32!GetLastError` at `0x180003466`
- `KERNEL32!GetLastError` at `0x1800034cb`
- `KERNEL32!GetLastError` at `0x180003466`
- `KERNEL32!GetLastError` at `0x1800034cb`
- `KERNEL32!CloseHandle` at `0x18000351d`
- `KERNEL32!CloseHandle` at `0x18000351d`

## string_xrefs

- `0x18000348a`: `SeShutdownPrivilege`

## pseudocode

```c
__int64 __fastcall CCMLuaUtil::ExitWindowsFunc(CCMLuaUtil *this)
{
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int v3; // ebx
  HANDLE TokenHandle; // [rsp+30h] [rbp-20h] BYREF
  _LUID Luid[2]; // [rsp+38h] [rbp-18h] BYREF

  TokenHandle = 0;
  *(_OWORD *)&Luid[0].LowPart = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle)
    && (LookupPrivilegeValueW(0, L"SeShutdownPrivilege", (PLUID)&Luid[0].HighPart),
        Luid[0].LowPart = 1,
        Luid[1].HighPart = 2,
        AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)Luid, 0, 0, 0),
        !GetLastError())
    && InitiateSystemShutdownW(0, 0, 0x14u, 0, 1) )
  {
    v3 = 0;
    Luid[1].HighPart = 0;
    AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)Luid, 0, 0, 0);
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v3;
}

```

## disassembly

```asm
0x180003420  mov     [rsp-8+arg_0], rbx
0x180003425  push    rbp
0x180003426  mov     rbp, rsp
0x180003429  sub     rsp, 50h
0x18000342d  mov     rax, cs:__security_cookie
0x180003434  xor     rax, rsp
0x180003437  mov     [rbp+var_8], rax
0x18000343b  xorps   xmm0, xmm0
0x18000343e  mov     [rbp+TokenHandle], 0
0x180003446  movups  xmmword ptr [rbp+Luid.LowPart], xmm0
0x18000344a  call    cs:__imp_GetCurrentProcess
0x180003450  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180003454  mov     edx, 28h ; '('; DesiredAccess
0x180003459  mov     rcx, rax; ProcessHandle
0x18000345c  call    cs:__imp_OpenProcessToken
0x180003462  test    eax, eax
0x180003464  jnz     short loc_180003484
0x180003466  call    cs:__imp_GetLastError
0x18000346c  mov     ebx, eax
0x18000346e  test    eax, eax
0x180003470  jle     loc_180003514
0x180003476  movzx   ebx, ax
0x180003479  or      ebx, 80070000h
0x18000347f  jmp     loc_180003514
0x180003484  lea     r8, [rbp+Luid.HighPart]; lpLuid
0x180003488  xor     ecx, ecx; lpSystemName
0x18000348a  lea     rdx, Name; "SeShutdownPrivilege"
0x180003491  call    cs:__imp_LookupPrivilegeValueW
0x180003497  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000349b  lea     r8, [rbp+Luid]; NewState
0x18000349f  mov     ebx, 1
0x1800034a4  mov     [rsp+50h+ReturnLength], 0; ReturnLength
0x1800034ad  xor     r9d, r9d; BufferLength
0x1800034b0  mov     [rbp+Luid.LowPart], ebx
0x1800034b3  xor     edx, edx; DisableAllPrivileges
0x1800034b5  mov     [rbp+Luid.HighPart+8], 2
0x1800034bc  mov     [rsp+50h+PreviousState], 0; PreviousState
0x1800034c5  call    cs:__imp_AdjustTokenPrivileges
0x1800034cb  call    cs:__imp_GetLastError
0x1800034d1  test    eax, eax
0x1800034d3  jnz     short loc_180003466
0x1800034d5  xor     r9d, r9d; bForceAppsClosed
0x1800034d8  mov     dword ptr [rsp+50h+PreviousState], ebx; bRebootAfterShutdown
0x1800034dc  xor     edx, edx; lpMessage
0x1800034de  lea     r8d, [rbx+13h]; dwTimeout
0x1800034e2  xor     ecx, ecx; lpMachineName
0x1800034e4  call    cs:__imp_InitiateSystemShutdownW
0x1800034ea  test    eax, eax
0x1800034ec  jz      loc_180003466
0x1800034f2  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800034f6  lea     r8, [rbp+Luid]; NewState
0x1800034fa  xor     ebx, ebx
0x1800034fc  xor     r9d, r9d; BufferLength
0x1800034ff  mov     [rsp+50h+ReturnLength], rbx; ReturnLength
0x180003504  xor     edx, edx; DisableAllPrivileges
0x180003506  mov     [rsp+50h+PreviousState], rbx; PreviousState
0x18000350b  mov     [rbp+Luid.HighPart+8], ebx
0x18000350e  call    cs:__imp_AdjustTokenPrivileges
0x180003514  mov     rcx, [rbp+TokenHandle]; hObject
0x180003518  test    rcx, rcx
0x18000351b  jz      short loc_180003523
0x18000351d  call    cs:__imp_CloseHandle
0x180003523  mov     eax, ebx
0x180003525  mov     rcx, [rbp+var_8]
0x180003529  xor     rcx, rsp; StackCookie
0x18000352c  call    __security_check_cookie
0x180003531  mov     rbx, [rsp+50h+arg_0]
0x180003536  add     rsp, 50h
0x18000353a  pop     rbp
0x18000353b  retn
```
