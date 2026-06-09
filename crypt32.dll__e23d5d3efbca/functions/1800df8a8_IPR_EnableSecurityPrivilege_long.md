# IPR_EnableSecurityPrivilege(long)

- ea: `0x1800df8a8`
- end: `0x1800df9ef`
- name: `?IPR_EnableSecurityPrivilege@@YAHJ@Z`
- size: `327`
- prototype: `__int64 __fastcall(int)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180043070`
- `0x18005be80`
- `0x1800c83b0`
- `0x1800dfbd4`

## callees

- `0x1800bec20`
- `0x1800df8a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df95d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df9a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df9b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df95d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df9a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df9b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800df9c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800df9c9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800df8fa`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800df8fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800df8e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800df8e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800df9c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800df9c1`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800df957`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800df99c`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800df957`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800df99c`

## pseudocode

```c
__int64 __fastcall IPR_EnableSecurityPrivilege(int a1)
{
  LUID v1; // rbx
  HANDLE CurrentProcess; // rax
  unsigned int v3; // edi
  DWORD LastError; // eax
  DWORD v5; // ebx
  DWORD BufferLength[2]; // [rsp+30h] [rbp-40h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-38h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+40h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+50h] [rbp-20h] BYREF

  v1 = (LUID)a1;
  TokenHandle = 0;
  NewState = 0;
  BufferLength[0] = 0;
  PreviousState = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
    goto LABEL_6;
  NewState.Privileges[0].Attributes = 0;
  BufferLength[1] = v1.HighPart;
  v3 = 1;
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Luid = v1;
  BufferLength[0] = 16;
  PreviousState = 0;
  AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, &PreviousState, BufferLength);
  LastError = GetLastError();
  if ( LastError )
    goto LABEL_6;
  if ( PreviousState.PrivilegeCount )
    LastError = PreviousState.Privileges[0].Attributes;
  PreviousState.Privileges[0].Attributes = LastError | 2;
  PreviousState.PrivilegeCount = 1;
  PreviousState.Privileges[0].Luid = v1;
  AdjustTokenPrivileges(TokenHandle, 0, &PreviousState, BufferLength[0], 0, 0);
  if ( GetLastError() )
LABEL_6:
    v3 = 0;
  if ( TokenHandle )
  {
    v5 = GetLastError();
    CloseHandle(TokenHandle);
    SetLastError(v5);
  }
  return v3;
}

```

## disassembly

```asm
0x1800df8a8  mov     [rsp-8+arg_0], rbx
0x1800df8ad  mov     [rsp-8+arg_8], rdi
0x1800df8b2  push    rbp
0x1800df8b3  mov     rbp, rsp
0x1800df8b6  sub     rsp, 70h
0x1800df8ba  mov     rax, cs:__security_cookie
0x1800df8c1  xor     rax, rsp
0x1800df8c4  mov     [rbp+var_10], rax
0x1800df8c8  xorps   xmm0, xmm0
0x1800df8cb  movsxd  rbx, ecx
0x1800df8ce  xorps   xmm1, xmm1
0x1800df8d1  mov     [rbp+TokenHandle], 0
0x1800df8d9  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x1800df8dd  mov     [rbp+BufferLength], 0
0x1800df8e4  movups  xmmword ptr [rbp+var_30.PrivilegeCount], xmm1
0x1800df8e8  call    cs:__imp_GetCurrentProcess
0x1800df8ee  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800df8f2  mov     edx, 28h ; '('; DesiredAccess
0x1800df8f7  mov     rcx, rax; ProcessHandle
0x1800df8fa  call    cs:__imp_OpenProcessToken
0x1800df900  test    eax, eax
0x1800df902  jz      loc_1800DF9AC
0x1800df908  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800df90c  lea     r8, [rbp+NewState]; NewState
0x1800df910  mov     rax, rbx
0x1800df913  mov     [rbp+NewState.Privileges.Attributes], 0
0x1800df91a  mov     [rbp+BufferLength], eax
0x1800df91d  mov     edi, 1
0x1800df922  shr     rax, 20h
0x1800df926  xorps   xmm0, xmm0
0x1800df929  mov     [rbp+BufferLength+4], eax
0x1800df92c  xor     edx, edx; DisableAllPrivileges
0x1800df92e  mov     rbx, qword ptr [rbp+BufferLength]
0x1800df932  lea     rax, [rbp+BufferLength]
0x1800df936  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1800df93b  lea     r9d, [rdi+0Fh]; BufferLength
0x1800df93f  lea     rax, [rbp+var_30]
0x1800df943  mov     [rbp+NewState.PrivilegeCount], edi
0x1800df946  mov     [rsp+70h+PreviousState], rax; PreviousState
0x1800df94b  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rbx
0x1800df94f  mov     [rbp+BufferLength], r9d
0x1800df953  movups  xmmword ptr [rbp+var_30.PrivilegeCount], xmm0
0x1800df957  call    cs:__imp_AdjustTokenPrivileges
0x1800df95d  call    cs:__imp_GetLastError
0x1800df963  test    eax, eax
0x1800df965  jnz     short loc_1800DF9AC
0x1800df967  cmp     [rbp+var_30.PrivilegeCount], eax
0x1800df96a  jz      short loc_1800DF96F
0x1800df96c  mov     eax, [rbp+var_30.Privileges.Attributes]
0x1800df96f  mov     r9d, [rbp+BufferLength]; BufferLength
0x1800df973  lea     r8, [rbp+var_30]; NewState
0x1800df977  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800df97b  or      eax, 2
0x1800df97e  mov     [rsp+70h+ReturnLength], 0; ReturnLength
0x1800df987  xor     edx, edx; DisableAllPrivileges
0x1800df989  mov     [rbp+var_30.Privileges.Attributes], eax
0x1800df98c  mov     [rbp+var_30.PrivilegeCount], edi
0x1800df98f  mov     qword ptr [rbp+var_30.Privileges.Luid.LowPart], rbx
0x1800df993  mov     [rsp+70h+PreviousState], 0; PreviousState
0x1800df99c  call    cs:__imp_AdjustTokenPrivileges
0x1800df9a2  call    cs:__imp_GetLastError
0x1800df9a8  test    eax, eax
0x1800df9aa  jz      short loc_1800DF9AE
0x1800df9ac  xor     edi, edi
0x1800df9ae  cmp     [rbp+TokenHandle], 0
0x1800df9b3  jz      short loc_1800DF9CF
0x1800df9b5  call    cs:__imp_GetLastError
0x1800df9bb  mov     rcx, [rbp+TokenHandle]; hObject
0x1800df9bf  mov     ebx, eax
0x1800df9c1  call    cs:__imp_CloseHandle
0x1800df9c7  mov     ecx, ebx; dwErrCode
0x1800df9c9  call    cs:__imp_SetLastError
0x1800df9cf  mov     eax, edi
0x1800df9d1  mov     rcx, [rbp+var_10]
0x1800df9d5  xor     rcx, rsp; StackCookie
0x1800df9d8  call    __security_check_cookie
0x1800df9dd  lea     r11, [rsp+70h+var_s0]
0x1800df9e2  mov     rbx, [r11+10h]
0x1800df9e6  mov     rdi, [r11+18h]
0x1800df9ea  mov     rsp, r11
0x1800df9ed  pop     rbp
0x1800df9ee  retn
```
