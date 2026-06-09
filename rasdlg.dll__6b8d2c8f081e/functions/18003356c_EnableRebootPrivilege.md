# EnableRebootPrivilege

- ea: `0x18003356c`
- end: `0x180033689`
- name: `EnableRebootPrivilege`
- size: `285`
- prototype: `DWORD __fastcall(int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003395c`

## callees

- `0x18003356c`
- `0x18004d110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800335b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800335e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033637`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033652`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800335b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800335e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033637`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033652`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800335ae`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800335ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800335c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800335c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180033598`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180033598`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800335db`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800335db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033648`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003366a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033648`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003366a`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18003362d`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18003362d`

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
0x18003356c  mov     [rsp-8+arg_0], rbx
0x180033571  push    rbp
0x180033572  mov     rbp, rsp
0x180033575  sub     rsp, 50h
0x180033579  mov     rax, cs:__security_cookie
0x180033580  xor     rax, rsp
0x180033583  mov     [rbp+var_8], rax
0x180033587  xorps   xmm0, xmm0
0x18003358a  mov     [rbp+TokenHandle], 0
0x180033592  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x180033596  mov     ebx, ecx
0x180033598  call    cs:__imp_GetCurrentThread
0x18003359e  mov     edx, 28h ; '('; DesiredAccess
0x1800335a3  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800335a7  mov     rcx, rax; ThreadHandle
0x1800335aa  lea     r8d, [rdx-27h]; OpenAsSelf
0x1800335ae  call    cs:__imp_OpenThreadToken
0x1800335b4  test    eax, eax
0x1800335b6  jnz     short loc_1800335F0
0x1800335b8  call    cs:__imp_GetLastError
0x1800335be  cmp     eax, 3F0h
0x1800335c3  jnz     loc_180033672
0x1800335c9  call    cs:__imp_GetCurrentProcess
0x1800335cf  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800335d3  mov     edx, 28h ; '('; DesiredAccess
0x1800335d8  mov     rcx, rax; ProcessHandle
0x1800335db  call    cs:__imp_OpenProcessToken
0x1800335e1  test    eax, eax
0x1800335e3  jnz     short loc_1800335F0
0x1800335e5  call    cs:__imp_GetLastError
0x1800335eb  jmp     loc_180033672
0x1800335f0  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800335f4  lea     r8, [rbp+NewState]; NewState
0x1800335f8  xor     edx, edx
0x1800335fa  mov     [rsp+50h+ReturnLength], 0; ReturnLength
0x180033603  test    ebx, ebx
0x180033605  mov     [rbp+NewState.PrivilegeCount], 1
0x18003360c  mov     r9d, 10h; BufferLength
0x180033612  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 13h
0x18003361a  setz    dl; DisableAllPrivileges
0x18003361d  mov     [rbp+NewState.Privileges.Attributes], 2
0x180033624  mov     [rsp+50h+PreviousState], 0; PreviousState
0x18003362d  call    cs:__imp_AdjustTokenPrivileges
0x180033633  test    eax, eax
0x180033635  jnz     short loc_180033652
0x180033637  call    cs:__imp_GetLastError
0x18003363d  mov     rcx, [rbp+TokenHandle]; hObject
0x180033641  mov     ebx, eax
0x180033643  test    rcx, rcx
0x180033646  jz      short loc_18003364E
0x180033648  call    cs:__imp_CloseHandle
0x18003364e  mov     eax, ebx
0x180033650  jmp     short loc_180033672
0x180033652  call    cs:__imp_GetLastError
0x180033658  mov     rcx, [rbp+TokenHandle]; hObject
0x18003365c  mov     ebx, 514h
0x180033661  cmp     eax, ebx
0x180033663  jz      short loc_180033643
0x180033665  test    rcx, rcx
0x180033668  jz      short loc_180033670
0x18003366a  call    cs:__imp_CloseHandle
0x180033670  xor     eax, eax
0x180033672  mov     rcx, [rbp+var_8]
0x180033676  xor     rcx, rsp; StackCookie
0x180033679  call    __security_check_cookie
0x18003367e  mov     rbx, [rsp+50h+arg_0]
0x180033683  add     rsp, 50h
0x180033687  pop     rbp
0x180033688  retn
```
