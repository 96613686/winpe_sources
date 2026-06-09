# DaGetProcessSid

- ea: `0x18000d5d8`
- end: `0x18000d6db`
- name: `DaGetProcessSid`
- size: `259`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180005850`
- `0x18000be24`
- `0x18000cbe0`
- `0x18000cc98`
- `0x18000cf74`

## callees

- `0x18000d5d8`
- `0x180011ba0`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x18000d63e`
- `KERNEL32!GetCurrentProcess` at `0x18000d63e`
- `KERNEL32!GetCurrentThread` at `0x18000d60a`
- `KERNEL32!GetCurrentThread` at `0x18000d60a`
- `KERNEL32!CloseHandle` at `0x18000d6b5`
- `KERNEL32!CloseHandle` at `0x18000d6b5`
- `KERNEL32!GetLastError` at `0x18000d62a`
- `KERNEL32!GetLastError` at `0x18000d662`
- `KERNEL32!GetLastError` at `0x18000d62a`
- `KERNEL32!GetLastError` at `0x18000d662`
- `ADVAPI32!GetSidLengthRequired` at `0x18000d691`
- `ADVAPI32!GetSidLengthRequired` at `0x18000d691`
- `ADVAPI32!CopySid` at `0x18000d6a0`
- `ADVAPI32!CopySid` at `0x18000d6a0`
- `ADVAPI32!GetTokenInformation` at `0x18000d685`
- `ADVAPI32!GetTokenInformation` at `0x18000d685`
- `ADVAPI32!OpenProcessToken` at `0x18000d650`
- `ADVAPI32!OpenProcessToken` at `0x18000d650`
- `ADVAPI32!OpenThreadToken` at `0x18000d620`
- `ADVAPI32!OpenThreadToken` at `0x18000d620`

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
0x18000d5d8  mov     [rsp-8+arg_0], rbx
0x18000d5dd  push    rbp
0x18000d5de  lea     rbp, [rsp-57h]
0x18000d5e3  sub     rsp, 0D0h
0x18000d5ea  mov     rax, cs:__security_cookie
0x18000d5f1  xor     rax, rsp
0x18000d5f4  mov     [rbp+57h+var_10], rax
0x18000d5f8  mov     rbx, rdx
0x18000d5fb  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18000d603  mov     [rbp+57h+var_A0], 0
0x18000d60a  call    cs:__imp_GetCurrentThread
0x18000d610  mov     edx, 8; DesiredAccess
0x18000d615  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18000d619  mov     rcx, rax; ThreadHandle
0x18000d61c  lea     r8d, [rdx-7]; OpenAsSelf
0x18000d620  call    cs:__imp_OpenThreadToken
0x18000d626  test    eax, eax
0x18000d628  jnz     short loc_18000D66A
0x18000d62a  call    cs:__imp_GetLastError
0x18000d630  mov     [rbp+57h+var_A0], eax
0x18000d633  cmp     eax, 3F0h
0x18000d638  jnz     loc_18000D6BE
0x18000d63e  call    cs:__imp_GetCurrentProcess
0x18000d644  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18000d648  mov     edx, 8; DesiredAccess
0x18000d64d  mov     rcx, rax; ProcessHandle
0x18000d650  call    cs:__imp_OpenProcessToken
0x18000d656  test    eax, eax
0x18000d658  jnz     short loc_18000D66A
0x18000d65a  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18000d662  call    cs:__imp_GetLastError
0x18000d668  jmp     short loc_18000D6A8
0x18000d66a  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18000d66e  lea     rax, [rbp+57h+var_A0]
0x18000d672  mov     r9d, 80h; TokenInformationLength
0x18000d678  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x18000d67d  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18000d681  lea     edx, [r9-7Fh]; TokenInformationClass
0x18000d685  call    cs:__imp_GetTokenInformation
0x18000d68b  test    eax, eax
0x18000d68d  jz      short loc_18000D662
0x18000d68f  mov     cl, 0Fh; nSubAuthorityCount
0x18000d691  call    cs:__imp_GetSidLengthRequired
0x18000d697  mov     r8, [rbp+57h+TokenInformation]; pSourceSid
0x18000d69b  mov     rdx, rbx; pDestinationSid
0x18000d69e  mov     ecx, eax; nDestinationSidLength
0x18000d6a0  call    cs:__imp_CopySid
0x18000d6a6  xor     eax, eax
0x18000d6a8  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18000d6ac  mov     [rbp+57h+var_A0], eax
0x18000d6af  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000d6b3  jz      short loc_18000D6BE
0x18000d6b5  call    cs:__imp_CloseHandle
0x18000d6bb  mov     eax, [rbp+57h+var_A0]
0x18000d6be  mov     rcx, [rbp+57h+var_10]
0x18000d6c2  xor     rcx, rsp; StackCookie
0x18000d6c5  call    __security_check_cookie
0x18000d6ca  mov     rbx, [rsp+0D0h+arg_0]
0x18000d6d2  add     rsp, 0D0h
0x18000d6d9  pop     rbp
0x18000d6da  retn
```
