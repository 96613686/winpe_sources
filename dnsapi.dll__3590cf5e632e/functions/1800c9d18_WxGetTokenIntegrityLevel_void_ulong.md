# WxGetTokenIntegrityLevel(void *,ulong *)

- ea: `0x1800c9d18`
- end: `0x1800c9e11`
- name: `?WxGetTokenIntegrityLevel@@YAJPEAXPEAK@Z`
- size: `249`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c9f20`

## callees

- `0x18008b5f0`
- `0x18008bf98`
- `0x1800c9d18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9d8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9d8f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c9d7f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c9d7f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800c9dc5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800c9dc5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800c9ddd`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800c9ddd`

## pseudocode

```c
__int64 __fastcall WxGetTokenIntegrityLevel(HANDLE TokenHandle, unsigned int *a2)
{
  signed int LastError; // eax
  signed int v5; // ebx
  PUCHAR SidSubAuthorityCount; // rax
  DWORD ReturnLength; // [rsp+30h] [rbp-98h] BYREF
  int v9; // [rsp+34h] [rbp-94h]
  PSID TokenInformation[14]; // [rsp+40h] [rbp-88h] BYREF

  v9 = 0;
  memset_0(TokenInformation, 0, 0x6Cu);
  ReturnLength = 108;
  *a2 = 4096;
  if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, TokenInformation, 0x6Cu, &ReturnLength) )
  {
    v5 = 0;
    SidSubAuthorityCount = GetSidSubAuthorityCount(TokenInformation[0]);
    *a2 = *GetSidSubAuthority(TokenInformation[0], (unsigned __int8)(*SidSubAuthorityCount - 1));
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v9 = 307;
    if ( v5 >= 0 )
      return (unsigned int)-2147418113;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800c9d18  mov     [rsp+arg_10], rbx
0x1800c9d1d  push    rdi
0x1800c9d1e  sub     rsp, 0C0h
0x1800c9d25  mov     rax, cs:__security_cookie
0x1800c9d2c  xor     rax, rsp
0x1800c9d2f  mov     [rsp+0C8h+var_18], rax
0x1800c9d37  mov     rdi, rdx
0x1800c9d3a  mov     [rsp+0C8h+var_94], 0
0x1800c9d42  xor     edx, edx; Val
0x1800c9d44  mov     rbx, rcx
0x1800c9d47  lea     rcx, [rsp+0C8h+TokenInformation]; void *
0x1800c9d4c  lea     r8d, [rdx+6Ch]; Size
0x1800c9d50  call    memset_0
0x1800c9d55  mov     r9d, 6Ch ; 'l'; TokenInformationLength
0x1800c9d5b  mov     [rsp+0C8h+var_98], 6Ch ; 'l'
0x1800c9d63  lea     rax, [rsp+0C8h+var_98]
0x1800c9d68  mov     dword ptr [rdi], 1000h
0x1800c9d6e  lea     r8, [rsp+0C8h+TokenInformation]; TokenInformation
0x1800c9d73  mov     [rsp+0C8h+ReturnLength], rax; ReturnLength
0x1800c9d78  mov     rcx, rbx; TokenHandle
0x1800c9d7b  lea     edx, [r9-53h]; TokenInformationClass
0x1800c9d7f  call    cs:__imp_GetTokenInformation
0x1800c9d86  nop     dword ptr [rax+rax+00h]
0x1800c9d8b  test    eax, eax
0x1800c9d8d  jnz     short loc_1800C9DBE
0x1800c9d8f  call    cs:__imp_GetLastError
0x1800c9d96  nop     dword ptr [rax+rax+00h]
0x1800c9d9b  mov     ebx, eax
0x1800c9d9d  test    eax, eax
0x1800c9d9f  jle     short loc_1800C9DAA
0x1800c9da1  movzx   ebx, ax
0x1800c9da4  or      ebx, 80070000h
0x1800c9daa  test    ebx, ebx
0x1800c9dac  mov     [rsp+0C8h+var_94], 133h
0x1800c9db4  mov     eax, 8000FFFFh
0x1800c9db9  cmovns  ebx, eax
0x1800c9dbc  jmp     short loc_1800C9DED
0x1800c9dbe  mov     rcx, [rsp+0C8h+TokenInformation]; pSid
0x1800c9dc3  xor     ebx, ebx
0x1800c9dc5  call    cs:__imp_GetSidSubAuthorityCount
0x1800c9dcc  nop     dword ptr [rax+rax+00h]
0x1800c9dd1  mov     cl, [rax]
0x1800c9dd3  dec     cl
0x1800c9dd5  movzx   edx, cl; nSubAuthority
0x1800c9dd8  mov     rcx, [rsp+0C8h+TokenInformation]; pSid
0x1800c9ddd  call    cs:__imp_GetSidSubAuthority
0x1800c9de4  nop     dword ptr [rax+rax+00h]
0x1800c9de9  mov     ecx, [rax]
0x1800c9deb  mov     [rdi], ecx
0x1800c9ded  mov     eax, ebx
0x1800c9def  mov     rcx, [rsp+0C8h+var_18]
0x1800c9df7  xor     rcx, rsp; StackCookie
0x1800c9dfa  call    __security_check_cookie
0x1800c9dff  mov     rbx, [rsp+0C8h+arg_10]
0x1800c9e07  add     rsp, 0C0h
0x1800c9e0e  pop     rdi
0x1800c9e0f  retn
```
