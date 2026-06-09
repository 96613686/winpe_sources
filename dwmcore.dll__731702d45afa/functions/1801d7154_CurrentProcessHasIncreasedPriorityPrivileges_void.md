# CurrentProcessHasIncreasedPriorityPrivileges(void)

- ea: `0x1801d7154`
- end: `0x1801d7232`
- name: `?CurrentProcessHasIncreasedPriorityPrivileges@@YA_NXZ`
- size: `222`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18027e594`

## callees

- `0x1801d7154`
- `0x1802284b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801d71b8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801d71b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801d71a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801d71a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801d71fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801d71fa`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x1801d71ee`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x1801d71ee`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1801d7190`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1801d7190`

## string_xrefs

- `0x1801d7180`: `SeIncreaseBasePriorityPrivilege`

## pseudocode

```c
char CurrentProcessHasIncreasedPriorityPrivileges(void)
{
  HANDLE CurrentProcess; // rax
  char v1; // di
  BOOL v2; // ebx
  WINBOOL pfResult; // [rsp+20h] [rbp-40h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-38h] BYREF
  _LUID Luid; // [rsp+30h] [rbp-30h] BYREF
  DWORD v7; // [rsp+38h] [rbp-28h]
  _PRIVILEGE_SET RequiredPrivileges; // [rsp+40h] [rbp-20h] BYREF

  Luid = 0;
  v7 = 2;
  if ( !LookupPrivilegeValueW(0, L"SeIncreaseBasePriorityPrivilege", &Luid) )
    return 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    return 0;
  RequiredPrivileges.Privilege[0].Luid = Luid;
  v1 = 1;
  RequiredPrivileges.Privilege[0].Attributes = v7;
  RequiredPrivileges.PrivilegeCount = 1;
  RequiredPrivileges.Control = 1;
  pfResult = 0;
  v2 = PrivilegeCheck(TokenHandle, &RequiredPrivileges, &pfResult);
  CloseHandle(TokenHandle);
  if ( !v2 || !pfResult )
    return 0;
  return v1;
}

```

## disassembly

```asm
0x1801d7154  mov     [rsp-8+arg_0], rbx
0x1801d7159  mov     [rsp-8+arg_8], rdi
0x1801d715e  push    rbp
0x1801d715f  mov     rbp, rsp
0x1801d7162  sub     rsp, 60h
0x1801d7166  mov     rax, cs:__security_cookie
0x1801d716d  xor     rax, rsp
0x1801d7170  mov     [rbp+var_8], rax
0x1801d7174  lea     r8, [rbp+Luid]; lpLuid
0x1801d7178  mov     qword ptr [rbp+Luid.LowPart], 0
0x1801d7180  lea     rdx, Name; "SeIncreaseBasePriorityPrivilege"
0x1801d7187  mov     [rbp+var_28], 2
0x1801d718e  xor     ecx, ecx; lpSystemName
0x1801d7190  call    cs:__imp_LookupPrivilegeValueW
0x1801d7196  test    eax, eax
0x1801d7198  jz      loc_1801D722E
0x1801d719e  mov     [rbp+TokenHandle], 0
0x1801d71a6  call    cs:__imp_GetCurrentProcess
0x1801d71ac  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1801d71b0  mov     edx, 8; DesiredAccess
0x1801d71b5  mov     rcx, rax; ProcessHandle
0x1801d71b8  call    cs:__imp_OpenProcessToken
0x1801d71be  test    eax, eax
0x1801d71c0  jz      short loc_1801D722E
0x1801d71c2  mov     rax, qword ptr [rbp+Luid.LowPart]
0x1801d71c6  lea     r8, [rbp+pfResult]; pfResult
0x1801d71ca  mov     rcx, [rbp+TokenHandle]; ClientToken
0x1801d71ce  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x1801d71d2  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.LowPart], rax
0x1801d71d6  mov     edi, 1
0x1801d71db  mov     eax, [rbp+var_28]
0x1801d71de  mov     [rbp+RequiredPrivileges.Privilege.Attributes], eax
0x1801d71e1  mov     [rbp+RequiredPrivileges.PrivilegeCount], edi
0x1801d71e4  mov     [rbp+RequiredPrivileges.Control], edi
0x1801d71e7  mov     [rbp+pfResult], 0
0x1801d71ee  call    cs:__imp_PrivilegeCheck
0x1801d71f4  mov     rcx, [rbp+TokenHandle]; hObject
0x1801d71f8  mov     ebx, eax
0x1801d71fa  call    cs:__imp_CloseHandle
0x1801d7200  test    ebx, ebx
0x1801d7202  jz      short loc_1801D7229
0x1801d7204  cmp     [rbp+pfResult], 0
0x1801d7208  jz      short loc_1801D7229
0x1801d720a  mov     al, dil
0x1801d720d  mov     rcx, [rbp+var_8]
0x1801d7211  xor     rcx, rsp; StackCookie
0x1801d7214  call    __security_check_cookie
0x1801d7219  mov     rbx, [rsp+60h+arg_0]
0x1801d721e  mov     rdi, [rsp+60h+arg_8]
0x1801d7223  add     rsp, 60h
0x1801d7227  pop     rbp
0x1801d7228  retn
0x1801d7229  xor     dil, dil
0x1801d722c  jmp     short loc_1801D720A
0x1801d722e  xor     al, al
0x1801d7230  jmp     short loc_1801D720D
```
