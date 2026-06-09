# UtilIsVirtualAccountToken(void *)

- ea: `0x18000e438`
- end: `0x18000e51d`
- name: `?UtilIsVirtualAccountToken@@YAJPEAX@Z`
- size: `229`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e7c0`

## callees

- `0x180002890`
- `0x18000e438`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e4a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e4a0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e496`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e496`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000e4be`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000e4be`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000e4e7`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000e4e7`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x18000e4cb`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x18000e4cb`

## pseudocode

```c
__int64 __fastcall UtilIsVirtualAccountToken(void *a1)
{
  unsigned int v1; // ebx
  signed int LastError; // eax
  PSID v3; // rdi
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rax
  DWORD ReturnLength; // [rsp+38h] [rbp-21h] BYREF
  PSID TokenInformation[12]; // [rsp+40h] [rbp-19h] BYREF

  ReturnLength = 0;
  if ( a1 )
  {
    v1 = 1;
    if ( GetTokenInformation(a1, TokenUser, TokenInformation, 0x54u, &ReturnLength) )
    {
      v3 = TokenInformation[0];
      if ( *GetSidSubAuthorityCount(TokenInformation[0]) )
      {
        SidIdentifierAuthority = GetSidIdentifierAuthority(v3);
        if ( !*(_DWORD *)SidIdentifierAuthority->Value && *(_WORD *)&SidIdentifierAuthority->Value[4] == 1280 )
          return *GetSidSubAuthority(v3, 0) - 80 > 0x1F;
      }
    }
    else
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v1;
}

```

## disassembly

```asm
0x18000e438  mov     [rsp-8+arg_8], rbx
0x18000e43d  mov     [rsp-8+arg_10], rdi
0x18000e442  push    rbp
0x18000e443  lea     rbp, [rsp-57h]
0x18000e448  sub     rsp, 0B0h
0x18000e44f  mov     rax, cs:__security_cookie
0x18000e456  xor     rax, rsp
0x18000e459  mov     [rbp+57h+var_10], rax
0x18000e45d  mov     [rbp+57h+var_78], 0
0x18000e464  mov     [rbp+57h+var_80], 0
0x18000e46b  mov     [rbp+57h+var_7C], 500h
0x18000e471  test    rcx, rcx
0x18000e474  jnz     short loc_18000E47D
0x18000e476  mov     ebx, 80070057h
0x18000e47b  jmp     short loc_18000E4FA
0x18000e47d  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18000e483  lea     rax, [rbp+57h+var_78]
0x18000e487  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18000e48b  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x18000e490  lea     ebx, [r9-53h]
0x18000e494  mov     edx, ebx; TokenInformationClass
0x18000e496  call    cs:__imp_GetTokenInformation
0x18000e49c  test    eax, eax
0x18000e49e  jnz     short loc_18000E4B7
0x18000e4a0  call    cs:__imp_GetLastError
0x18000e4a6  mov     ebx, eax
0x18000e4a8  test    eax, eax
0x18000e4aa  jle     short loc_18000E4FA
0x18000e4ac  movzx   ebx, ax
0x18000e4af  or      ebx, 80070000h
0x18000e4b5  jmp     short loc_18000E4FA
0x18000e4b7  mov     rdi, [rbp+57h+TokenInformation]
0x18000e4bb  mov     rcx, rdi; pSid
0x18000e4be  call    cs:__imp_GetSidSubAuthorityCount
0x18000e4c4  cmp     [rax], bl
0x18000e4c6  jb      short loc_18000E4FA
0x18000e4c8  mov     rcx, rdi; pSid
0x18000e4cb  call    cs:__imp_GetSidIdentifierAuthority
0x18000e4d1  mov     edx, [rax]
0x18000e4d3  cmp     edx, [rbp+57h+var_80]
0x18000e4d6  jnz     short loc_18000E4FA
0x18000e4d8  movzx   eax, word ptr [rax+4]
0x18000e4dc  cmp     ax, [rbp+57h+var_7C]
0x18000e4e0  jnz     short loc_18000E4FA
0x18000e4e2  xor     edx, edx; nSubAuthority
0x18000e4e4  mov     rcx, rdi; pSid
0x18000e4e7  call    cs:__imp_GetSidSubAuthority
0x18000e4ed  xor     ecx, ecx
0x18000e4ef  mov     edx, [rax]
0x18000e4f1  sub     edx, 50h ; 'P'
0x18000e4f4  cmp     edx, 1Fh
0x18000e4f7  cmovbe  ebx, ecx
0x18000e4fa  mov     eax, ebx
0x18000e4fc  mov     rcx, [rbp+57h+var_10]
0x18000e500  xor     rcx, rsp; StackCookie
0x18000e503  call    __security_check_cookie
0x18000e508  lea     r11, [rsp+0B0h+var_s0]
0x18000e510  mov     rbx, [r11+18h]
0x18000e514  mov     rdi, [r11+20h]
0x18000e518  mov     rsp, r11
0x18000e51b  pop     rbp
0x18000e51c  retn
```
