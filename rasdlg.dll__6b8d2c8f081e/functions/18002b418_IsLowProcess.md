# IsLowProcess

- ea: `0x18002b418`
- end: `0x18002b56f`
- name: `IsLowProcess`
- size: `343`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007b1c`
- `0x18000c9c8`
- `0x18000e360`

## callees

- `0x18002b418`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002b4a2`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002b4a2`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002b51b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002b51b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b48c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b4fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b535`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b48c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b4fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b535`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002b440`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002b440`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002b453`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002b453`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b52d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b52d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002b4d7`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002b4d7`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002b4e7`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002b4e7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002b47e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002b4ca`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002b47e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002b4ca`

## pseudocode

```c
__int64 IsLowProcess()
{
  HANDLE CurrentProcess; // rax
  unsigned int v1; // ebx
  PSID *v2; // rdi
  PUCHAR SidSubAuthorityCount; // rax
  signed int LastError; // eax
  signed int v5; // eax
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+10h] BYREF

  TokenHandle = 0;
  TokenInformationLength = 0;
  if ( dword_1800636F8 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      v1 = 1;
      if ( !GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength)
        && GetLastError() == 122 )
      {
        v2 = (PSID *)GlobalAlloc(0x40u, TokenInformationLength);
        if ( v2 )
        {
          if ( GetTokenInformation(
                 TokenHandle,
                 TokenIntegrityLevel,
                 v2,
                 TokenInformationLength,
                 &TokenInformationLength) )
          {
            SidSubAuthorityCount = GetSidSubAuthorityCount(*v2);
            v1 = *GetSidSubAuthority(*v2, (unsigned __int8)(*SidSubAuthorityCount - 1)) >= 0x2000;
          }
          else
          {
            LastError = GetLastError();
            if ( LastError != -1073741821 )
            {
              if ( LastError > 0 )
                v1 = (unsigned __int16)LastError | 0x80070000;
              else
                v1 = LastError;
            }
          }
          GlobalFree(v2);
        }
        else
        {
          v1 = -2147024888;
        }
      }
      CloseHandle(TokenHandle);
    }
    else
    {
      v5 = GetLastError();
      v1 = v5;
      if ( v5 > 0 )
        v1 = (unsigned __int16)v5 | 0x80070000;
    }
    dword_1800636F8 = 0;
    dword_1800636F4 = v1;
  }
  else
  {
    return (unsigned int)dword_1800636F4;
  }
  return v1;
}

```

## disassembly

```asm
0x18002b418  mov     [rsp+arg_10], rbx
0x18002b41d  push    rdi
0x18002b41e  sub     rsp, 30h
0x18002b422  cmp     cs:dword_1800636F8, 0
0x18002b429  mov     [rsp+38h+TokenHandle], 0
0x18002b432  mov     [rsp+38h+TokenInformationLength], 0
0x18002b43a  jz      loc_18002B55C
0x18002b440  call    cs:__imp_GetCurrentProcess
0x18002b446  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18002b44b  mov     edx, 8; DesiredAccess
0x18002b450  mov     rcx, rax; ProcessHandle
0x18002b453  call    cs:__imp_OpenProcessToken
0x18002b459  test    eax, eax
0x18002b45b  jz      loc_18002B535
0x18002b461  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18002b466  lea     rax, [rsp+38h+TokenInformationLength]
0x18002b46b  mov     ebx, 1
0x18002b470  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18002b475  xor     r9d, r9d; TokenInformationLength
0x18002b478  xor     r8d, r8d; TokenInformation
0x18002b47b  lea     edx, [rbx+18h]; TokenInformationClass
0x18002b47e  call    cs:__imp_GetTokenInformation
0x18002b484  test    eax, eax
0x18002b486  jnz     loc_18002B528
0x18002b48c  call    cs:__imp_GetLastError
0x18002b492  cmp     eax, 7Ah ; 'z'
0x18002b495  jnz     loc_18002B528
0x18002b49b  mov     edx, [rsp+38h+TokenInformationLength]; dwBytes
0x18002b49f  lea     ecx, [rbx+3Fh]; uFlags
0x18002b4a2  call    cs:__imp_GlobalAlloc
0x18002b4a8  mov     rdi, rax
0x18002b4ab  test    rax, rax
0x18002b4ae  jz      short loc_18002B523
0x18002b4b0  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18002b4b5  lea     rax, [rsp+38h+TokenInformationLength]
0x18002b4ba  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18002b4bf  lea     edx, [rbx+18h]; TokenInformationClass
0x18002b4c2  mov     r8, rdi; TokenInformation
0x18002b4c5  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18002b4ca  call    cs:__imp_GetTokenInformation
0x18002b4d0  test    eax, eax
0x18002b4d2  jz      short loc_18002B4FA
0x18002b4d4  mov     rcx, [rdi]; pSid
0x18002b4d7  call    cs:__imp_GetSidSubAuthorityCount
0x18002b4dd  mov     cl, [rax]
0x18002b4df  sub     cl, bl
0x18002b4e1  movzx   edx, cl; nSubAuthority
0x18002b4e4  mov     rcx, [rdi]; pSid
0x18002b4e7  call    cs:__imp_GetSidSubAuthority
0x18002b4ed  xor     ebx, ebx
0x18002b4ef  cmp     dword ptr [rax], 2000h
0x18002b4f5  setnb   bl
0x18002b4f8  jmp     short loc_18002B518
0x18002b4fa  call    cs:__imp_GetLastError
0x18002b500  cmp     eax, 0C0000003h
0x18002b505  jz      short loc_18002B518
0x18002b507  test    eax, eax
0x18002b509  jg      short loc_18002B50F
0x18002b50b  mov     ebx, eax
0x18002b50d  jmp     short loc_18002B518
0x18002b50f  movzx   ebx, ax
0x18002b512  or      ebx, 80070000h
0x18002b518  mov     rcx, rdi; hMem
0x18002b51b  call    cs:__imp_GlobalFree
0x18002b521  jmp     short loc_18002B528
0x18002b523  mov     ebx, 80070008h
0x18002b528  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18002b52d  call    cs:__imp_CloseHandle
0x18002b533  jmp     short loc_18002B54A
0x18002b535  call    cs:__imp_GetLastError
0x18002b53b  mov     ebx, eax
0x18002b53d  test    eax, eax
0x18002b53f  jle     short loc_18002B54A
0x18002b541  movzx   ebx, ax
0x18002b544  or      ebx, 80070000h
0x18002b54a  mov     cs:dword_1800636F8, 0
0x18002b554  mov     cs:dword_1800636F4, ebx
0x18002b55a  jmp     short loc_18002B562
0x18002b55c  mov     ebx, cs:dword_1800636F4
0x18002b562  mov     eax, ebx
0x18002b564  mov     rbx, [rsp+38h+arg_10]
0x18002b569  add     rsp, 30h
0x18002b56d  pop     rdi
0x18002b56e  retn
```
