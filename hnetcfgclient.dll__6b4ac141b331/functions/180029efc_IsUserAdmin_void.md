# IsUserAdmin(void)

- ea: `0x180029efc`
- end: `0x180029fa8`
- name: `?IsUserAdmin@@YAHXZ`
- size: `172`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e900`
- `0x180010be0`
- `0x1800268c0`

## callees

- `0x180029efc`
- `0x18002d200`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180029f5d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180029f5d`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180029f71`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180029f71`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180029f82`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180029f82`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 IsUserAdmin(void)
{
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  IsMember = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
      IsMember = 0;
    FreeSid(SidToCheck);
  }
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x180029efc  mov     [rsp-8+arg_0], rbx
0x180029f01  push    rbp
0x180029f02  mov     rbp, rsp
0x180029f05  sub     rsp, 80h
0x180029f0c  mov     rax, cs:__security_cookie
0x180029f13  xor     rax, rsp
0x180029f16  mov     [rbp+var_8], rax
0x180029f1a  xor     ebx, ebx
0x180029f1c  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x180029f22  lea     rax, [rbp+SidToCheck]
0x180029f26  mov     dword ptr [rbp+pIdentifierAuthority.Value], ebx
0x180029f29  mov     [rsp+80h+pSid], rax; pSid
0x180029f2e  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180029f32  mov     [rsp+80h+nSubAuthority7], ebx; nSubAuthority7
0x180029f36  mov     r9d, 220h; nSubAuthority1
0x180029f3c  mov     [rsp+80h+nSubAuthority6], ebx; nSubAuthority6
0x180029f40  lea     r8d, [rbx+20h]; nSubAuthority0
0x180029f44  mov     [rsp+80h+nSubAuthority5], ebx; nSubAuthority5
0x180029f48  mov     dl, 2; nSubAuthorityCount
0x180029f4a  mov     [rsp+80h+nSubAuthority4], ebx; nSubAuthority4
0x180029f4e  mov     [rsp+80h+nSubAuthority3], ebx; nSubAuthority3
0x180029f52  mov     [rsp+80h+nSubAuthority2], ebx; nSubAuthority2
0x180029f56  mov     [rbp+SidToCheck], rbx
0x180029f5a  mov     [rbp+IsMember], ebx
0x180029f5d  call    cs:__imp_AllocateAndInitializeSid
0x180029f63  test    eax, eax
0x180029f65  jz      short loc_180029F88
0x180029f67  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x180029f6b  lea     r8, [rbp+IsMember]; IsMember
0x180029f6f  xor     ecx, ecx; TokenHandle
0x180029f71  call    cs:__imp_CheckTokenMembership
0x180029f77  test    eax, eax
0x180029f79  jnz     short loc_180029F7E
0x180029f7b  mov     [rbp+IsMember], ebx
0x180029f7e  mov     rcx, [rbp+SidToCheck]; pSid
0x180029f82  call    cs:__imp_FreeSid
0x180029f88  mov     eax, [rbp+IsMember]
0x180029f8b  mov     rcx, [rbp+var_8]
0x180029f8f  xor     rcx, rsp; StackCookie
0x180029f92  call    __security_check_cookie
0x180029f97  mov     rbx, [rsp+80h+arg_0]
0x180029f9f  add     rsp, 80h
0x180029fa6  pop     rbp
0x180029fa7  retn
```
