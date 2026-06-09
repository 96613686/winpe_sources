# CurrentProcessHasIncreasedPriorityPrivileges(void)

- ea: `0x18004b04c`
- end: `0x18004b134`
- name: `?CurrentProcessHasIncreasedPriorityPrivileges@@YA_NXZ`
- size: `232`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004a080`

## callees

- `0x180035e00`
- `0x18004b04c`
- `0x1800a9d20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004b06f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004b06f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004b081`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004b081`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b0f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b11f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b0f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b11f`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x18004b0e1`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x18004b0e1`
- `api-ms-win-security-lsalookup-ansi-l2-1-0!LookupPrivilegeValueA` at `0x18004b0ab`
- `api-ms-win-security-lsalookup-ansi-l2-1-0!LookupPrivilegeValueA` at `0x18004b0ab`

## string_xrefs

- `0x18004b09b`: `SeIncreaseBasePriorityPrivilege`

## pseudocode

```c
bool CurrentProcessHasIncreasedPriorityPrivileges(void)
{
  HANDLE CurrentProcess; // rax
  BOOL v1; // eax
  void *v2; // rcx
  BOOL v3; // eax
  bool v5; // bl
  void *TokenHandle; // [rsp+20h] [rbp-40h] BYREF
  WINBOOL pfResult; // [rsp+28h] [rbp-38h] BYREF
  _LUID Luid; // [rsp+30h] [rbp-30h] BYREF
  DWORD v9; // [rsp+38h] [rbp-28h]
  _PRIVILEGE_SET RequiredPrivileges; // [rsp+40h] [rbp-20h] BYREF

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    SafeHANDLE::~SafeHANDLE((SafeHANDLE *)&TokenHandle);
    return 0;
  }
  Luid = 0;
  v9 = 2;
  v1 = LookupPrivilegeValueA(0, "SeIncreaseBasePriorityPrivilege", &Luid);
  v2 = TokenHandle;
  if ( !v1
    || (pfResult = 0,
        RequiredPrivileges.PrivilegeCount = 1,
        RequiredPrivileges.Control = 1,
        RequiredPrivileges.Privilege[0].Luid = Luid,
        RequiredPrivileges.Privilege[0].Attributes = v9,
        v3 = PrivilegeCheck(TokenHandle, &RequiredPrivileges, &pfResult),
        v2 = TokenHandle,
        !v3) )
  {
    if ( v2 )
      CloseHandle(v2);
    return 0;
  }
  v5 = pfResult != 0;
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v5;
}

```

## disassembly

```asm
0x18004b04c  mov     [rsp-8+arg_0], rbx
0x18004b051  push    rbp
0x18004b052  mov     rbp, rsp
0x18004b055  sub     rsp, 60h
0x18004b059  mov     rax, cs:__security_cookie
0x18004b060  xor     rax, rsp
0x18004b063  mov     [rbp+var_8], rax
0x18004b067  mov     [rbp+TokenHandle], 0
0x18004b06f  call    cs:__imp_GetCurrentProcess
0x18004b075  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18004b079  mov     edx, 8; DesiredAccess
0x18004b07e  mov     rcx, rax; ProcessHandle
0x18004b081  call    cs:__imp_OpenProcessToken
0x18004b087  test    eax, eax
0x18004b089  jz      loc_18004B129
0x18004b08f  lea     r8, [rbp+Luid]; lpLuid
0x18004b093  mov     qword ptr [rbp+Luid.LowPart], 0
0x18004b09b  lea     rdx, Name; "SeIncreaseBasePriorityPrivilege"
0x18004b0a2  mov     [rbp+var_28], 2
0x18004b0a9  xor     ecx, ecx; lpSystemName
0x18004b0ab  call    cs:__imp_LookupPrivilegeValueA
0x18004b0b1  mov     rcx, [rbp+TokenHandle]; ClientToken
0x18004b0b5  test    eax, eax
0x18004b0b7  jz      short loc_18004B0EF
0x18004b0b9  mov     eax, 1
0x18004b0be  mov     [rbp+pfResult], 0
0x18004b0c5  mov     [rbp+RequiredPrivileges.PrivilegeCount], eax
0x18004b0c8  lea     r8, [rbp+pfResult]; pfResult
0x18004b0cc  mov     [rbp+RequiredPrivileges.Control], eax
0x18004b0cf  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x18004b0d3  mov     rax, qword ptr [rbp+Luid.LowPart]
0x18004b0d7  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.LowPart], rax
0x18004b0db  mov     eax, [rbp+var_28]
0x18004b0de  mov     [rbp+RequiredPrivileges.Privilege.Attributes], eax
0x18004b0e1  call    cs:__imp_PrivilegeCheck
0x18004b0e7  mov     rcx, [rbp+TokenHandle]; hObject
0x18004b0eb  test    eax, eax
0x18004b0ed  jnz     short loc_18004B113
0x18004b0ef  test    rcx, rcx
0x18004b0f2  jz      short loc_18004B0FA
0x18004b0f4  call    cs:__imp_CloseHandle
0x18004b0fa  xor     al, al
0x18004b0fc  mov     rcx, [rbp+var_8]
0x18004b100  xor     rcx, rsp; StackCookie
0x18004b103  call    __security_check_cookie
0x18004b108  mov     rbx, [rsp+60h+arg_0]
0x18004b10d  add     rsp, 60h
0x18004b111  pop     rbp
0x18004b112  retn
0x18004b113  cmp     [rbp+pfResult], 0
0x18004b117  setnz   bl
0x18004b11a  test    rcx, rcx
0x18004b11d  jz      short loc_18004B125
0x18004b11f  call    cs:__imp_CloseHandle
0x18004b125  mov     al, bl
0x18004b127  jmp     short loc_18004B0FC
0x18004b129  lea     rcx, [rbp+TokenHandle]; this
0x18004b12d  call    ??1SafeHANDLE@@QEAA@XZ; SafeHANDLE::~SafeHANDLE(void)
0x18004b132  jmp     short loc_18004B0FA
```
