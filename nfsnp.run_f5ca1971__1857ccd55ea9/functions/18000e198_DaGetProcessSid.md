# DaGetProcessSid

- ea: `0x18000e198`
- end: `0x18000e2d8`
- name: `DaGetProcessSid`
- size: `320`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180005c40`
- `0x18000c738`
- `0x18000d644`
- `0x18000d710`
- `0x18000da44`

## callees

- `0x18000e198`
- `0x180012e70`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x18000e210`
- `KERNEL32!GetCurrentProcess` at `0x18000e210`
- `KERNEL32!GetCurrentThread` at `0x18000e1ca`
- `KERNEL32!GetCurrentThread` at `0x18000e1ca`
- `KERNEL32!CloseHandle` at `0x18000e2ab`
- `KERNEL32!CloseHandle` at `0x18000e2ab`
- `KERNEL32!GetLastError` at `0x18000e1f6`
- `KERNEL32!GetLastError` at `0x18000e240`
- `KERNEL32!GetLastError` at `0x18000e1f6`
- `KERNEL32!GetLastError` at `0x18000e240`
- `ADVAPI32!GetSidLengthRequired` at `0x18000e27b`
- `ADVAPI32!GetSidLengthRequired` at `0x18000e27b`
- `ADVAPI32!CopySid` at `0x18000e290`
- `ADVAPI32!CopySid` at `0x18000e290`
- `ADVAPI32!GetTokenInformation` at `0x18000e269`
- `ADVAPI32!GetTokenInformation` at `0x18000e269`
- `ADVAPI32!OpenProcessToken` at `0x18000e228`
- `ADVAPI32!OpenProcessToken` at `0x18000e228`
- `ADVAPI32!OpenThreadToken` at `0x18000e1e6`
- `ADVAPI32!OpenThreadToken` at `0x18000e1e6`

## pseudocode

```c
DWORD __fastcall DaGetProcessSid(__int64 a1, void *a2)
{
  HANDLE CurrentThread; // rax
  DWORD result; // eax
  HANDLE CurrentProcess; // rax
  DWORD SidLengthRequired; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-49h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-41h] BYREF
  PSID TokenInformation[16]; // [rsp+40h] [rbp-39h] BYREF

  TokenHandle = (void *)-1LL;
  ReturnLength = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    result = GetLastError();
    ReturnLength = result;
    if ( result != 1008 )
      return result;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      TokenHandle = (void *)-1LL;
LABEL_5:
      result = GetLastError();
      goto LABEL_8;
    }
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x80u, &ReturnLength) )
    goto LABEL_5;
  SidLengthRequired = GetSidLengthRequired(0xFu);
  CopySid(SidLengthRequired, a2, TokenInformation[0]);
  result = 0;
LABEL_8:
  ReturnLength = result;
  if ( TokenHandle != (void *)-1LL )
  {
    CloseHandle(TokenHandle);
    return ReturnLength;
  }
  return result;
}

```

## disassembly

```asm
0x18000e198  mov     [rsp-8+arg_0], rbx
0x18000e19d  push    rbp
0x18000e19e  lea     rbp, [rsp-57h]
0x18000e1a3  sub     rsp, 0D0h
0x18000e1aa  mov     rax, cs:__security_cookie
0x18000e1b1  xor     rax, rsp
0x18000e1b4  mov     [rbp+57h+var_10], rax
0x18000e1b8  mov     rbx, rdx
0x18000e1bb  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18000e1c3  mov     [rbp+57h+var_A0], 0
0x18000e1ca  call    cs:__imp_GetCurrentThread
0x18000e1d1  nop     dword ptr [rax+rax+00h]
0x18000e1d6  mov     edx, 8; DesiredAccess
0x18000e1db  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18000e1df  mov     rcx, rax; ThreadHandle
0x18000e1e2  lea     r8d, [rdx-7]; OpenAsSelf
0x18000e1e6  call    cs:__imp_OpenThreadToken
0x18000e1ed  nop     dword ptr [rax+rax+00h]
0x18000e1f2  test    eax, eax
0x18000e1f4  jnz     short loc_18000E24E
0x18000e1f6  call    cs:__imp_GetLastError
0x18000e1fd  nop     dword ptr [rax+rax+00h]
0x18000e202  mov     [rbp+57h+var_A0], eax
0x18000e205  cmp     eax, 3F0h
0x18000e20a  jnz     loc_18000E2BA
0x18000e210  call    cs:__imp_GetCurrentProcess
0x18000e217  nop     dword ptr [rax+rax+00h]
0x18000e21c  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18000e220  mov     edx, 8; DesiredAccess
0x18000e225  mov     rcx, rax; ProcessHandle
0x18000e228  call    cs:__imp_OpenProcessToken
0x18000e22f  nop     dword ptr [rax+rax+00h]
0x18000e234  test    eax, eax
0x18000e236  jnz     short loc_18000E24E
0x18000e238  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18000e240  call    cs:__imp_GetLastError
0x18000e247  nop     dword ptr [rax+rax+00h]
0x18000e24c  jmp     short loc_18000E29E
0x18000e24e  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18000e252  lea     rax, [rbp+57h+var_A0]
0x18000e256  mov     r9d, 80h; TokenInformationLength
0x18000e25c  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x18000e261  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18000e265  lea     edx, [r9-7Fh]; TokenInformationClass
0x18000e269  call    cs:__imp_GetTokenInformation
0x18000e270  nop     dword ptr [rax+rax+00h]
0x18000e275  test    eax, eax
0x18000e277  jz      short loc_18000E240
0x18000e279  mov     cl, 0Fh; nSubAuthorityCount
0x18000e27b  call    cs:__imp_GetSidLengthRequired
0x18000e282  nop     dword ptr [rax+rax+00h]
0x18000e287  mov     r8, [rbp+57h+TokenInformation]; pSourceSid
0x18000e28b  mov     rdx, rbx; pDestinationSid
0x18000e28e  mov     ecx, eax; nDestinationSidLength
0x18000e290  call    cs:__imp_CopySid
0x18000e297  nop     dword ptr [rax+rax+00h]
0x18000e29c  xor     eax, eax
0x18000e29e  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18000e2a2  mov     [rbp+57h+var_A0], eax
0x18000e2a5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000e2a9  jz      short loc_18000E2BA
0x18000e2ab  call    cs:__imp_CloseHandle
0x18000e2b2  nop     dword ptr [rax+rax+00h]
0x18000e2b7  mov     eax, [rbp+57h+var_A0]
0x18000e2ba  mov     rcx, [rbp+57h+var_10]
0x18000e2be  xor     rcx, rsp; StackCookie
0x18000e2c1  call    __security_check_cookie
0x18000e2c6  mov     rbx, [rsp+0D0h+arg_0]
0x18000e2ce  add     rsp, 0D0h
0x18000e2d5  pop     rbp
0x18000e2d6  retn
```
