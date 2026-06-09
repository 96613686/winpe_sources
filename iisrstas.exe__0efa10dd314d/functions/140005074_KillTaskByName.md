# KillTaskByName

- ea: `0x140005074`
- end: `0x140005160`
- name: `KillTaskByName`
- size: `236`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140003674`

## callees

- `0x1400049b0`
- `0x140005074`
- `0x1400054c0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x14000511c`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x14000511c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400050c3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400050c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400050b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400050b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005122`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005122`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005131`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005131`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1400050da`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1400050da`

## string_xrefs

- `0x1400050d3`: `SeDebugPrivilege`

## pseudocode

```c
__int64 __fastcall KillTaskByName(__int64 a1, __int64 a2)
{
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-30h] BYREF
  _LUID Luid; // [rsp+38h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-20h] BYREF

  TokenHandle = 0;
  NewState = 0;
  Luid = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) && LookupPrivilegeValueW(0, L"SeDebugPrivilege", &Luid) )
  {
    NewState.Privileges[0].Luid = Luid;
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Attributes = 2;
    AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, 0, 0);
    GetLastError();
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return KillTask(a1, a2);
}

```

## disassembly

```asm
0x140005074  mov     [rsp-8+arg_10], rbx
0x140005079  mov     [rsp-8+arg_18], rdi
0x14000507e  push    rbp
0x14000507f  mov     rbp, rsp
0x140005082  sub     rsp, 60h
0x140005086  mov     rax, cs:__security_cookie
0x14000508d  xor     rax, rsp
0x140005090  mov     [rbp+var_10], rax
0x140005094  xorps   xmm0, xmm0
0x140005097  mov     [rbp+TokenHandle], 0
0x14000509f  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x1400050a3  mov     rdi, rdx
0x1400050a6  mov     qword ptr [rbp+Luid.LowPart], 0
0x1400050ae  mov     rbx, rcx
0x1400050b1  call    cs:__imp_GetCurrentProcess
0x1400050b7  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1400050bb  mov     edx, 28h ; '('; DesiredAccess
0x1400050c0  mov     rcx, rax; ProcessHandle
0x1400050c3  call    cs:__imp_OpenProcessToken
0x1400050c9  test    eax, eax
0x1400050cb  jz      short loc_140005128
0x1400050cd  lea     r8, [rbp+Luid]; lpLuid
0x1400050d1  xor     ecx, ecx; lpSystemName
0x1400050d3  lea     rdx, Name; "SeDebugPrivilege"
0x1400050da  call    cs:__imp_LookupPrivilegeValueW
0x1400050e0  test    eax, eax
0x1400050e2  jz      short loc_140005128
0x1400050e4  mov     rax, qword ptr [rbp+Luid.LowPart]
0x1400050e8  lea     r8, [rbp+NewState]; NewState
0x1400050ec  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1400050f0  mov     r9d, 10h; BufferLength
0x1400050f6  mov     [rsp+60h+ReturnLength], 0; ReturnLength
0x1400050ff  xor     edx, edx; DisableAllPrivileges
0x140005101  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x140005105  mov     [rbp+NewState.PrivilegeCount], 1
0x14000510c  mov     [rbp+NewState.Privileges.Attributes], 2
0x140005113  mov     [rsp+60h+PreviousState], 0; PreviousState
0x14000511c  call    cs:__imp_AdjustTokenPrivileges
0x140005122  call    cs:__imp_GetLastError
0x140005128  mov     rcx, [rbp+TokenHandle]; hObject
0x14000512c  test    rcx, rcx
0x14000512f  jz      short loc_140005137
0x140005131  call    cs:__imp_CloseHandle
0x140005137  mov     rdx, rdi
0x14000513a  mov     rcx, rbx
0x14000513d  call    KillTask
0x140005142  mov     rcx, [rbp+var_10]
0x140005146  xor     rcx, rsp; StackCookie
0x140005149  call    __security_check_cookie
0x14000514e  lea     r11, [rsp+60h+var_s0]
0x140005153  mov     rbx, [r11+20h]
0x140005157  mov     rdi, [r11+28h]
0x14000515b  mov     rsp, r11
0x14000515e  pop     rbp
0x14000515f  retn
```
