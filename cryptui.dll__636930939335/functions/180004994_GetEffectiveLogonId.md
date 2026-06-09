# GetEffectiveLogonId

- ea: `0x180004994`
- end: `0x180004a7f`
- name: `GetEffectiveLogonId`
- size: `235`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003600`
- `0x1800052f0`

## callees

- `0x180004994`
- `0x18003e5c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049fa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004a3f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004a3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800049da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800049da`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180004a16`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180004a16`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004a07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004a07`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800049f0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800049f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a4b`

## pseudocode

```c
__int64 __fastcall GetEffectiveLogonId(_QWORD *a1)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  unsigned int v5; // ebx
  HANDLE TokenHandle; // [rsp+30h] [rbp-50h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-48h] BYREF
  _OWORD TokenInformation[3]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v9; // [rsp+70h] [rbp-10h]

  TokenHandle = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  v9 = 0;
  ReturnLength = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    if ( GetLastError() != 1008 )
      return 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      return 0;
  }
  v5 = GetTokenInformation(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength);
  CloseHandle(TokenHandle);
  if ( v5 )
    *a1 = *((_QWORD *)&TokenInformation[0] + 1);
  return v5;
}

```

## disassembly

```asm
0x180004994  mov     [rsp-8+arg_8], rbx
0x180004999  mov     [rsp-8+arg_10], rdi
0x18000499e  push    rbp
0x18000499f  mov     rbp, rsp
0x1800049a2  sub     rsp, 80h
0x1800049a9  mov     rax, cs:__security_cookie
0x1800049b0  xor     rax, rsp
0x1800049b3  mov     [rbp+var_8], rax
0x1800049b7  xorps   xmm0, xmm0
0x1800049ba  mov     [rbp+TokenHandle], 0
0x1800049c2  xor     eax, eax
0x1800049c4  mov     rdi, rcx
0x1800049c7  movups  [rbp+TokenInformation], xmm0
0x1800049cb  mov     [rbp+var_10], rax
0x1800049cf  movups  [rbp+var_30], xmm0
0x1800049d3  mov     [rbp+var_48], eax
0x1800049d6  movups  [rbp+var_20], xmm0
0x1800049da  call    cs:__imp_GetCurrentThread
0x1800049e0  xor     r8d, r8d; OpenAsSelf
0x1800049e3  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800049e7  mov     rcx, rax; ThreadHandle
0x1800049ea  lea     ebx, [r8+8]
0x1800049ee  mov     edx, ebx; DesiredAccess
0x1800049f0  call    cs:__imp_OpenThreadToken
0x1800049f6  test    eax, eax
0x1800049f8  jnz     short loc_180004A24
0x1800049fa  call    cs:__imp_GetLastError
0x180004a00  cmp     eax, 3F0h
0x180004a05  jnz     short loc_180004A20
0x180004a07  call    cs:__imp_GetCurrentProcess
0x180004a0d  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180004a11  mov     edx, ebx; DesiredAccess
0x180004a13  mov     rcx, rax; ProcessHandle
0x180004a16  call    cs:__imp_OpenProcessToken
0x180004a1c  test    eax, eax
0x180004a1e  jnz     short loc_180004A24
0x180004a20  xor     eax, eax
0x180004a22  jmp     short loc_180004A5E
0x180004a24  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180004a28  lea     rax, [rbp+var_48]
0x180004a2c  mov     r9d, 38h ; '8'; TokenInformationLength
0x180004a32  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x180004a37  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180004a3b  lea     edx, [r9-2Eh]; TokenInformationClass
0x180004a3f  call    cs:__imp_GetTokenInformation
0x180004a45  mov     rcx, [rbp+TokenHandle]; hObject
0x180004a49  mov     ebx, eax
0x180004a4b  call    cs:__imp_CloseHandle
0x180004a51  test    ebx, ebx
0x180004a53  jz      short loc_180004A5C
0x180004a55  mov     rcx, qword ptr [rbp+TokenInformation+8]
0x180004a59  mov     [rdi], rcx
0x180004a5c  mov     eax, ebx
0x180004a5e  mov     rcx, [rbp+var_8]
0x180004a62  xor     rcx, rsp; StackCookie
0x180004a65  call    __security_check_cookie
0x180004a6a  lea     r11, [rsp+80h+var_s0]
0x180004a72  mov     rbx, [r11+18h]
0x180004a76  mov     rdi, [r11+20h]
0x180004a7a  mov     rsp, r11
0x180004a7d  pop     rbp
0x180004a7e  retn
```
