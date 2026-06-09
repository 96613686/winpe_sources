# GetTokenILValue

- ea: `0x18002dd7c`
- end: `0x18002de6f`
- name: `GetTokenILValue`
- size: `243`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002dd20`

## callees

- `0x18002dd7c`
- `0x1800827c0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002de0f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002de0f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002de24`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002de24`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18002ddd4`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18002ddd4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002ddf9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002ddf9`

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
0x18002dd7c  mov     [rsp-8+arg_10], rbx
0x18002dd81  mov     [rsp-8+arg_18], rdi
0x18002dd86  push    rbp
0x18002dd87  lea     rbp, [rsp-57h]
0x18002dd8c  sub     rsp, 0B0h
0x18002dd93  mov     rax, cs:__security_cookie
0x18002dd9a  xor     rax, rsp
0x18002dd9d  mov     [rbp+57h+var_10], rax
0x18002dda1  mov     rdi, rdx
0x18002dda4  mov     dword ptr [rdx], 0
0x18002ddaa  mov     rbx, rcx
0x18002ddad  mov     [rbp+57h+TokenInformationLength], 58h ; 'X'
0x18002ddb4  lea     rax, [rbp+57h+Sid]
0x18002ddb8  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], 0
0x18002ddbf  lea     rdx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18002ddc3  mov     [rbp+57h+TokenInformation], rax
0x18002ddc7  lea     rcx, [rbp+57h+Sid]; Sid
0x18002ddcb  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 1000h
0x18002ddd1  mov     r8b, 1; nSubAuthorityCount
0x18002ddd4  call    cs:__imp_InitializeSid
0x18002dddb  nop     dword ptr [rax+rax+00h]
0x18002dde0  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x18002dde4  lea     rax, [rbp+57h+TokenInformationLength]
0x18002dde8  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18002ddec  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x18002ddf1  mov     edx, 19h; TokenInformationClass
0x18002ddf6  mov     rcx, rbx; TokenHandle
0x18002ddf9  call    cs:__imp_GetTokenInformation
0x18002de00  nop     dword ptr [rax+rax+00h]
0x18002de05  test    eax, eax
0x18002de07  jz      short loc_18002DE58
0x18002de09  mov     rcx, [rbp+57h+TokenInformation]; pSid
0x18002de0d  xor     ebx, ebx
0x18002de0f  call    cs:__imp_GetSidSubAuthorityCount
0x18002de16  nop     dword ptr [rax+rax+00h]
0x18002de1b  mov     rcx, [rbp+57h+TokenInformation]; pSid
0x18002de1f  movzx   edx, byte ptr [rax]
0x18002de22  dec     edx; nSubAuthority
0x18002de24  call    cs:__imp_GetSidSubAuthority
0x18002de2b  nop     dword ptr [rax+rax+00h]
0x18002de30  mov     ecx, [rax]
0x18002de32  mov     [rdi], ecx
0x18002de34  mov     eax, ebx
0x18002de36  mov     rcx, [rbp+57h+var_10]
0x18002de3a  xor     rcx, rsp; StackCookie
0x18002de3d  call    __security_check_cookie
0x18002de42  lea     r11, [rsp+0B0h+var_s0]
0x18002de4a  mov     rbx, [r11+20h]
0x18002de4e  mov     rdi, [r11+28h]
0x18002de52  mov     rsp, r11
0x18002de55  pop     rbp
0x18002de56  retn
0x18002de58  mov     ebx, gs:68h
0x18002de60  test    ebx, ebx
0x18002de62  jle     short loc_18002DE34
0x18002de64  movzx   ebx, bx
0x18002de67  or      ebx, 80070000h
0x18002de6d  jmp     short loc_18002DE34
```
