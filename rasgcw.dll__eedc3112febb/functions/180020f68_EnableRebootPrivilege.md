# EnableRebootPrivilege

- ea: `0x180020f68`
- end: `0x180021085`
- name: `EnableRebootPrivilege`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021348`

## callees

- `0x180020f68`
- `0x18002f3b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020fb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020fe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021033`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002104e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020fb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020fe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021033`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002104e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180020f94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180020f94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180020fc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180020fc5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180020fd7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180020fd7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180020faa`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180020faa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021044`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021066`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021044`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021066`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180021029`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180021029`

## pseudocode

```c
DWORD __fastcall EnableRebootPrivilege(int a1)
{
  HANDLE CurrentThread; // rax
  DWORD result; // eax
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  void *v6; // rcx
  int v7; // ebx
  DWORD v8; // eax
  void *TokenHandle; // [rsp+30h] [rbp-20h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-18h] BYREF

  TokenHandle = 0;
  NewState = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x28u, 1, &TokenHandle) )
  {
    result = GetLastError();
    if ( result != 1008 )
      return result;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
      return GetLastError();
  }
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Luid = (LUID)19LL;
  NewState.Privileges[0].Attributes = 2;
  if ( !AdjustTokenPrivileges(TokenHandle, a1 == 0, &NewState, 0x10u, 0, 0) )
  {
    LastError = GetLastError();
    v6 = TokenHandle;
    v7 = LastError;
LABEL_7:
    if ( v6 )
      CloseHandle(v6);
    return v7;
  }
  v8 = GetLastError();
  v6 = TokenHandle;
  v7 = 1300;
  if ( v8 == 1300 )
    goto LABEL_7;
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x180020f68  mov     [rsp-8+arg_0], rbx
0x180020f6d  push    rbp
0x180020f6e  mov     rbp, rsp
0x180020f71  sub     rsp, 50h
0x180020f75  mov     rax, cs:__security_cookie
0x180020f7c  xor     rax, rsp
0x180020f7f  mov     [rbp+var_8], rax
0x180020f83  xorps   xmm0, xmm0
0x180020f86  mov     [rbp+TokenHandle], 0
0x180020f8e  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x180020f92  mov     ebx, ecx
0x180020f94  call    cs:__imp_GetCurrentThread
0x180020f9a  mov     edx, 28h ; '('; DesiredAccess
0x180020f9f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180020fa3  mov     rcx, rax; ThreadHandle
0x180020fa6  lea     r8d, [rdx-27h]; OpenAsSelf
0x180020faa  call    cs:__imp_OpenThreadToken
0x180020fb0  test    eax, eax
0x180020fb2  jnz     short loc_180020FEC
0x180020fb4  call    cs:__imp_GetLastError
0x180020fba  cmp     eax, 3F0h
0x180020fbf  jnz     loc_18002106E
0x180020fc5  call    cs:__imp_GetCurrentProcess
0x180020fcb  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180020fcf  mov     edx, 28h ; '('; DesiredAccess
0x180020fd4  mov     rcx, rax; ProcessHandle
0x180020fd7  call    cs:__imp_OpenProcessToken
0x180020fdd  test    eax, eax
0x180020fdf  jnz     short loc_180020FEC
0x180020fe1  call    cs:__imp_GetLastError
0x180020fe7  jmp     loc_18002106E
0x180020fec  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180020ff0  lea     r8, [rbp+NewState]; NewState
0x180020ff4  xor     edx, edx
0x180020ff6  mov     [rsp+50h+ReturnLength], 0; ReturnLength
0x180020fff  test    ebx, ebx
0x180021001  mov     [rbp+NewState.PrivilegeCount], 1
0x180021008  mov     r9d, 10h; BufferLength
0x18002100e  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 13h
0x180021016  setz    dl; DisableAllPrivileges
0x180021019  mov     [rbp+NewState.Privileges.Attributes], 2
0x180021020  mov     [rsp+50h+PreviousState], 0; PreviousState
0x180021029  call    cs:__imp_AdjustTokenPrivileges
0x18002102f  test    eax, eax
0x180021031  jnz     short loc_18002104E
0x180021033  call    cs:__imp_GetLastError
0x180021039  mov     rcx, [rbp+TokenHandle]; hObject
0x18002103d  mov     ebx, eax
0x18002103f  test    rcx, rcx
0x180021042  jz      short loc_18002104A
0x180021044  call    cs:__imp_CloseHandle
0x18002104a  mov     eax, ebx
0x18002104c  jmp     short loc_18002106E
0x18002104e  call    cs:__imp_GetLastError
0x180021054  mov     rcx, [rbp+TokenHandle]; hObject
0x180021058  mov     ebx, 514h
0x18002105d  cmp     eax, ebx
0x18002105f  jz      short loc_18002103F
0x180021061  test    rcx, rcx
0x180021064  jz      short loc_18002106C
0x180021066  call    cs:__imp_CloseHandle
0x18002106c  xor     eax, eax
0x18002106e  mov     rcx, [rbp+var_8]
0x180021072  xor     rcx, rsp; StackCookie
0x180021075  call    __security_check_cookie
0x18002107a  mov     rbx, [rsp+50h+arg_0]
0x18002107f  add     rsp, 50h
0x180021083  pop     rbp
0x180021084  retn
```
