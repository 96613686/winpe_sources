# UserIsUACAdmin(int *)

- ea: `0x1800018c0`
- end: `0x1800019e3`
- name: `?UserIsUACAdmin@@YAJPEAH@Z`
- size: `291`
- prototype: `__int64 __fastcall(PBOOL IsMember)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001670`

## callees

- `0x1800018c0`
- `0x18000250c`
- `0x1800049f4`
- `0x180009e40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800018eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800018eb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180001904`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180001904`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001994`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001994`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000195a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000195a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180001974`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180001974`

## pseudocode

```c
unsigned int __fastcall UserIsUACAdmin(PBOOL IsMember)
{
  HANDLE CurrentProcess; // rax
  int v2; // edi
  DWORD cbSid; // [rsp+20h] [rbp-78h]
  int v5; // [rsp+24h] [rbp-74h]
  void *TokenHandle; // [rsp+28h] [rbp-70h] BYREF

  *IsMember = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
  {
    v5 = 0;
    cbSid = 0;
    v2 = LUAIsElevatedToken(TokenHandle);
    CloseHandle(TokenHandle);
    return v2;
  }
  else if ( (int)GetLastErrorError() > 0 )
  {
    return (unsigned __int16)GetLastErrorError() | 0x80070000;
  }
  else
  {
    return GetLastErrorError();
  }
}

```

## disassembly

```asm
0x1800018c0  mov     [rsp+arg_8], rbx
0x1800018c5  push    rdi
0x1800018c6  sub     rsp, 90h
0x1800018cd  mov     rax, cs:__security_cookie
0x1800018d4  xor     rax, rsp
0x1800018d7  mov     [rsp+98h+var_18], rax
0x1800018df  xor     edi, edi
0x1800018e1  mov     rbx, rcx
0x1800018e4  mov     [rcx], edi
0x1800018e6  mov     [rsp+98h+TokenHandle], rdi
0x1800018eb  call    cs:__imp_GetCurrentProcess
0x1800018f2  nop     dword ptr [rax+rax+00h]
0x1800018f7  lea     r8, [rsp+98h+TokenHandle]; TokenHandle
0x1800018fc  mov     edx, 0Ah; DesiredAccess
0x180001901  mov     rcx, rax; ProcessHandle
0x180001904  call    cs:__imp_OpenProcessToken
0x18000190b  nop     dword ptr [rax+rax+00h]
0x180001910  test    eax, eax
0x180001912  jz      loc_1800019A4
0x180001918  mov     rcx, [rsp+98h+TokenHandle]; TokenHandle
0x18000191d  lea     r8, [rsp+98h+cbSid]
0x180001922  lea     rdx, [rsp+98h+var_74]
0x180001927  mov     [rsp+98h+var_74], edi
0x18000192b  mov     [rsp+98h+cbSid], edi
0x18000192f  call    LUAIsElevatedToken
0x180001934  mov     edi, eax
0x180001936  test    eax, eax
0x180001938  js      short loc_18000198F
0x18000193a  cmp     [rsp+98h+var_74], 0
0x18000193f  jz      short loc_180001982
0x180001941  lea     r9, [rsp+98h+cbSid]; cbSid
0x180001946  mov     [rsp+98h+cbSid], 44h ; 'D'
0x18000194e  lea     r8, [rsp+98h+pSid]; pSid
0x180001953  xor     edx, edx; DomainSid
0x180001955  mov     ecx, 1Ah; WellKnownSidType
0x18000195a  call    cs:__imp_CreateWellKnownSid
0x180001961  nop     dword ptr [rax+rax+00h]
0x180001966  test    eax, eax
0x180001968  jz      short loc_18000198F
0x18000196a  mov     r8, rbx; IsMember
0x18000196d  lea     rdx, [rsp+98h+pSid]; SidToCheck
0x180001972  xor     ecx, ecx; TokenHandle
0x180001974  call    cs:__imp_CheckTokenMembership
0x18000197b  nop     dword ptr [rax+rax+00h]
0x180001980  jmp     short loc_18000198F
0x180001982  cmp     [rsp+98h+cbSid], 0
0x180001987  jz      short loc_18000198F
0x180001989  mov     dword ptr [rbx], 1
0x18000198f  mov     rcx, [rsp+98h+TokenHandle]; hObject
0x180001994  call    cs:__imp_CloseHandle
0x18000199b  nop     dword ptr [rax+rax+00h]
0x1800019a0  mov     eax, edi
0x1800019a2  jmp     short loc_1800019C1
0x1800019a4  call    ?GetLastErrorError@@YAKXZ; GetLastErrorError(void)
0x1800019a9  test    eax, eax
0x1800019ab  jg      short loc_1800019B4
0x1800019ad  call    ?GetLastErrorError@@YAKXZ; GetLastErrorError(void)
0x1800019b2  jmp     short loc_1800019C1
0x1800019b4  call    ?GetLastErrorError@@YAKXZ; GetLastErrorError(void)
0x1800019b9  movzx   eax, ax
0x1800019bc  or      eax, 80070000h
0x1800019c1  mov     rcx, [rsp+98h+var_18]
0x1800019c9  xor     rcx, rsp; StackCookie
0x1800019cc  call    __security_check_cookie
0x1800019d1  mov     rbx, [rsp+98h+arg_8]
0x1800019d9  add     rsp, 90h
0x1800019e0  pop     rdi
0x1800019e1  retn
```
