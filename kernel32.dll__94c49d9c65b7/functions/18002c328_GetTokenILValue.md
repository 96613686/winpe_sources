# GetTokenILValue

- ea: `0x18002c328`
- end: `0x18002c402`
- name: `GetTokenILValue`
- size: `218`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002c2cc`

## callees

- `0x18002c328`
- `0x18007a840`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002c3af`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002c3af`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002c3be`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002c3be`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18002c380`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18002c380`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c39f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c39f`

## pseudocode

```c
__int64 __fastcall GetTokenILValue(HANDLE TokenHandle, DWORD *a2)
{
  signed int LastErrorValue; // ebx
  PUCHAR SidSubAuthorityCount; // rax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-29h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+34h] [rbp-25h] BYREF
  PSID TokenInformation[2]; // [rsp+40h] [rbp-19h] BYREF
  _BYTE Sid[80]; // [rsp+50h] [rbp-9h] BYREF

  *a2 = 0;
  TokenInformationLength = 88;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  TokenInformation[0] = Sid;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 4096;
  InitializeSid(Sid, &pIdentifierAuthority, 1u);
  if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, TokenInformation, 0x58u, &TokenInformationLength) )
  {
    LastErrorValue = 0;
    SidSubAuthorityCount = GetSidSubAuthorityCount(TokenInformation[0]);
    *a2 = *GetSidSubAuthority(TokenInformation[0], (unsigned int)*SidSubAuthorityCount - 1);
  }
  else
  {
    LastErrorValue = NtCurrentTeb()->LastErrorValue;
    if ( LastErrorValue > 0 )
      return (unsigned __int16)LastErrorValue | 0x80070000;
  }
  return (unsigned int)LastErrorValue;
}

```

## disassembly

```asm
0x18002c328  mov     [rsp-8+arg_10], rbx
0x18002c32d  mov     [rsp-8+arg_18], rdi
0x18002c332  push    rbp
0x18002c333  lea     rbp, [rsp-57h]
0x18002c338  sub     rsp, 0B0h
0x18002c33f  mov     rax, cs:__security_cookie
0x18002c346  xor     rax, rsp
0x18002c349  mov     [rbp+57h+var_10], rax
0x18002c34d  mov     rdi, rdx
0x18002c350  mov     dword ptr [rdx], 0
0x18002c356  mov     rbx, rcx
0x18002c359  mov     [rbp+57h+TokenInformationLength], 58h ; 'X'
0x18002c360  lea     rax, [rbp+57h+Sid]
0x18002c364  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], 0
0x18002c36b  lea     rdx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18002c36f  mov     [rbp+57h+TokenInformation], rax
0x18002c373  lea     rcx, [rbp+57h+Sid]; Sid
0x18002c377  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 1000h
0x18002c37d  mov     r8b, 1; nSubAuthorityCount
0x18002c380  call    cs:__imp_InitializeSid
0x18002c386  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x18002c38a  lea     rax, [rbp+57h+TokenInformationLength]
0x18002c38e  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18002c392  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x18002c397  mov     edx, 19h; TokenInformationClass
0x18002c39c  mov     rcx, rbx; TokenHandle
0x18002c39f  call    cs:__imp_GetTokenInformation
0x18002c3a5  test    eax, eax
0x18002c3a7  jz      short loc_18002C3EB
0x18002c3a9  mov     rcx, [rbp+57h+TokenInformation]; pSid
0x18002c3ad  xor     ebx, ebx
0x18002c3af  call    cs:__imp_GetSidSubAuthorityCount
0x18002c3b5  mov     rcx, [rbp+57h+TokenInformation]; pSid
0x18002c3b9  movzx   edx, byte ptr [rax]
0x18002c3bc  dec     edx; nSubAuthority
0x18002c3be  call    cs:__imp_GetSidSubAuthority
0x18002c3c4  mov     ecx, [rax]
0x18002c3c6  mov     [rdi], ecx
0x18002c3c8  mov     eax, ebx
0x18002c3ca  mov     rcx, [rbp+57h+var_10]
0x18002c3ce  xor     rcx, rsp; StackCookie
0x18002c3d1  call    __security_check_cookie
0x18002c3d6  lea     r11, [rsp+0B0h+var_s0]
0x18002c3de  mov     rbx, [r11+20h]
0x18002c3e2  mov     rdi, [r11+28h]
0x18002c3e6  mov     rsp, r11
0x18002c3e9  pop     rbp
0x18002c3ea  retn
0x18002c3eb  mov     ebx, gs:68h
0x18002c3f3  test    ebx, ebx
0x18002c3f5  jle     short loc_18002C3C8
0x18002c3f7  movzx   ebx, bx
0x18002c3fa  or      ebx, 80070000h
0x18002c400  jmp     short loc_18002C3C8
```
