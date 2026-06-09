# EnablePrivilege(ulong,int,int *)

- ea: `0x18000cc18`
- end: `0x18000cd05`
- name: `?EnablePrivilege@@YAKKHPEAH@Z`
- size: `237`
- prototype: `unsigned int __fastcall(unsigned int, int, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800069e8`

## callees

- `0x18000cc18`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000ccbb`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000ccbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc76`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000cc6c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000cc6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000cc5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000cc5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ccdf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ccdf`

## pseudocode

```c
__int64 __fastcall EnablePrivilege(__int64 a1, int a2, DWORD *a3)
{
  HANDLE CurrentProcess; // rax
  DWORD LastError; // ebx
  DWORD ReturnLength; // [rsp+30h] [rbp-40h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-38h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+50h] [rbp-20h] BYREF

  TokenHandle = 0;
  ReturnLength = 0;
  NewState = 0;
  PreviousState = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle)
    && (NewState.PrivilegeCount = 1,
        NewState.Privileges[0].Luid = (LUID)8LL,
        NewState.Privileges[0].Attributes = a2 != 0 ? 2 : 0,
        AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &ReturnLength)) )
  {
    LastError = 0;
    if ( a3 )
      *a3 = (PreviousState.Privileges[0].Attributes >> 1) & 1;
  }
  else
  {
    LastError = GetLastError();
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x18000cc18  mov     [rsp-8+arg_0], rbx
0x18000cc1d  mov     [rsp-8+arg_8], rdi
0x18000cc22  push    rbp
0x18000cc23  mov     rbp, rsp
0x18000cc26  sub     rsp, 70h
0x18000cc2a  mov     rax, cs:__security_cookie
0x18000cc31  xor     rax, rsp
0x18000cc34  mov     [rbp+var_10], rax
0x18000cc38  xorps   xmm0, xmm0
0x18000cc3b  mov     [rbp+TokenHandle], 0
0x18000cc43  xorps   xmm1, xmm1
0x18000cc46  mov     [rbp+var_40], 0
0x18000cc4d  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x18000cc51  mov     rdi, r8
0x18000cc54  mov     ebx, edx
0x18000cc56  movups  xmmword ptr [rbp+var_20.PrivilegeCount], xmm1
0x18000cc5a  call    cs:__imp_GetCurrentProcess
0x18000cc60  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000cc64  mov     edx, 28h ; '('; DesiredAccess
0x18000cc69  mov     rcx, rax; ProcessHandle
0x18000cc6c  call    cs:__imp_OpenProcessToken
0x18000cc72  test    eax, eax
0x18000cc74  jnz     short loc_18000CC80
0x18000cc76  call    cs:__imp_GetLastError
0x18000cc7c  mov     ebx, eax
0x18000cc7e  jmp     short loc_18000CCD6
0x18000cc80  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000cc84  lea     r8, [rbp+NewState]; NewState
0x18000cc88  neg     ebx
0x18000cc8a  mov     [rbp+NewState.PrivilegeCount], 1
0x18000cc91  mov     r9d, 10h; BufferLength
0x18000cc97  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 8
0x18000cc9f  sbb     eax, eax
0x18000cca1  xor     edx, edx; DisableAllPrivileges
0x18000cca3  and     eax, 2
0x18000cca6  mov     [rbp+NewState.Privileges.Attributes], eax
0x18000cca9  lea     rax, [rbp+var_40]
0x18000ccad  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18000ccb2  lea     rax, [rbp+var_20]
0x18000ccb6  mov     [rsp+70h+PreviousState], rax; PreviousState
0x18000ccbb  call    cs:__imp_AdjustTokenPrivileges
0x18000ccc1  test    eax, eax
0x18000ccc3  jz      short loc_18000CC76
0x18000ccc5  xor     ebx, ebx
0x18000ccc7  test    rdi, rdi
0x18000ccca  jz      short loc_18000CCD6
0x18000cccc  mov     eax, [rbp+var_20.Privileges.Attributes]
0x18000cccf  shr     eax, 1
0x18000ccd1  and     eax, 1
0x18000ccd4  mov     [rdi], eax
0x18000ccd6  mov     rcx, [rbp+TokenHandle]; hObject
0x18000ccda  test    rcx, rcx
0x18000ccdd  jz      short loc_18000CCE5
0x18000ccdf  call    cs:__imp_CloseHandle
0x18000cce5  mov     eax, ebx
0x18000cce7  mov     rcx, [rbp+var_10]
0x18000cceb  xor     rcx, rsp; StackCookie
0x18000ccee  call    __security_check_cookie
0x18000ccf3  lea     r11, [rsp+70h+var_s0]
0x18000ccf8  mov     rbx, [r11+10h]
0x18000ccfc  mov     rdi, [r11+18h]
0x18000cd00  mov     rsp, r11
0x18000cd03  pop     rbp
0x18000cd04  retn
```
