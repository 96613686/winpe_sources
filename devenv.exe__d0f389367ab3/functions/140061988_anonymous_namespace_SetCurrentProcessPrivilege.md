# _anonymous_namespace_::SetCurrentProcessPrivilege

- ea: `0x140061988`
- end: `0x140061a54`
- name: `_anonymous_namespace_::SetCurrentProcessPrivilege`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400249e0`

## callees

- `0x140001020`
- `0x140061988`

## import_xrefs

- `ADVAPI32!AdjustTokenPrivileges` at `0x140061a1d`
- `ADVAPI32!AdjustTokenPrivileges` at `0x140061a1d`
- `ADVAPI32!LookupPrivilegeValueW` at `0x1400619db`
- `ADVAPI32!LookupPrivilegeValueW` at `0x1400619db`
- `ADVAPI32!OpenProcessToken` at `0x1400619bc`
- `ADVAPI32!OpenProcessToken` at `0x1400619bc`
- `KERNEL32!GetCurrentProcess` at `0x1400619a9`
- `KERNEL32!GetCurrentProcess` at `0x1400619a9`
- `KERNEL32!GetLastError` at `0x140061a27`
- `KERNEL32!GetLastError` at `0x140061a27`

## string_xrefs

- `0x1400619d2`: `SeBackupPrivilege`

## pseudocode

```c
bool __fastcall anonymous_namespace_::SetCurrentProcessPrivilege(__int64 a1, char a2)
{
  HANDLE CurrentProcess; // rax
  BOOL v4; // eax
  bool v5; // bl
  HANDLE v6; // rsi
  HANDLE TokenHandle; // [rsp+30h] [rbp-38h] BYREF
  _LUID Luid; // [rsp+38h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-28h] BYREF

  CurrentProcess = GetCurrentProcess();
  v4 = OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle);
  v5 = 0;
  if ( v4 )
  {
    v6 = TokenHandle;
    if ( LookupPrivilegeValueW(0, L"SeBackupPrivilege", &Luid) )
    {
      NewState.Privileges[0].Luid = Luid;
      NewState.PrivilegeCount = 1;
      NewState.Privileges[0].Attributes = a2 != 0 ? 2 : 0;
      if ( AdjustTokenPrivileges(v6, 0, &NewState, 0x10u, 0, 0) )
        v5 = GetLastError() != 1300;
    }
    LOBYTE(v4) = v5;
  }
  return v4;
}

```

## disassembly

```asm
0x140061988  mov     [rsp+arg_0], rbx
0x14006198d  mov     [rsp+arg_8], rsi
0x140061992  push    rdi
0x140061993  sub     rsp, 60h
0x140061997  mov     rax, cs:__security_cookie
0x14006199e  xor     rax, rsp
0x1400619a1  mov     [rsp+68h+var_18], rax
0x1400619a6  mov     dil, dl
0x1400619a9  call    cs:__imp_GetCurrentProcess
0x1400619af  lea     r8, [rsp+68h+TokenHandle]; TokenHandle
0x1400619b4  mov     edx, 28h ; '('; DesiredAccess
0x1400619b9  mov     rcx, rax; ProcessHandle
0x1400619bc  call    cs:__imp_OpenProcessToken
0x1400619c2  xor     ebx, ebx
0x1400619c4  test    eax, eax
0x1400619c6  jz      short loc_140061A37
0x1400619c8  mov     rsi, [rsp+68h+TokenHandle]
0x1400619cd  lea     r8, [rsp+68h+Luid]; lpLuid
0x1400619d2  lea     rdx, aSebackupprivil; "SeBackupPrivilege"
0x1400619d9  xor     ecx, ecx; lpSystemName
0x1400619db  call    cs:__imp_LookupPrivilegeValueW
0x1400619e1  test    eax, eax
0x1400619e3  jz      short loc_140061A35
0x1400619e5  mov     rax, qword ptr [rsp+68h+Luid.LowPart]
0x1400619ea  lea     r8, [rsp+68h+NewState]; NewState
0x1400619ef  mov     qword ptr [rsp+68h+NewState.Privileges.Luid.LowPart], rax
0x1400619f4  neg     dil
0x1400619f7  mov     [rsp+68h+ReturnLength], rbx; ReturnLength
0x1400619fc  mov     r9d, 10h; BufferLength
0x140061a02  sbb     eax, eax
0x140061a04  mov     [rsp+68h+NewState.PrivilegeCount], 1
0x140061a0c  and     eax, 2
0x140061a0f  mov     [rsp+68h+PreviousState], rbx; PreviousState
0x140061a14  xor     edx, edx; DisableAllPrivileges
0x140061a16  mov     [rsp+68h+NewState.Privileges.Attributes], eax
0x140061a1a  mov     rcx, rsi; TokenHandle
0x140061a1d  call    cs:__imp_AdjustTokenPrivileges
0x140061a23  test    eax, eax
0x140061a25  jz      short loc_140061A35
0x140061a27  call    cs:__imp_GetLastError
0x140061a2d  cmp     eax, 514h
0x140061a32  setnz   bl
0x140061a35  mov     al, bl
0x140061a37  mov     rcx, [rsp+68h+var_18]
0x140061a3c  xor     rcx, rsp; StackCookie
0x140061a3f  call    __security_check_cookie
0x140061a44  mov     rbx, [rsp+68h+arg_0]
0x140061a49  mov     rsi, [rsp+68h+arg_8]
0x140061a4e  add     rsp, 60h
0x140061a52  pop     rdi
0x140061a53  retn
```
