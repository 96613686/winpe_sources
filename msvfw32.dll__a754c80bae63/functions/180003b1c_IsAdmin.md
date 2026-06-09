# IsAdmin

- ea: `0x180003b1c`
- end: `0x180003be8`
- name: `IsAdmin`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800043b0`

## callees

- `0x1800014b0`
- `0x180003b1c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180003bae`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180003bbf`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180003bae`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180003bbf`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180003b88`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180003b88`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180003ba0`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180003ba0`

## pseudocode

```c
__int64 IsAdmin()
{
  __int64 result; // rax
  BOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  result = (unsigned int)fIsAdmin;
  IsMember = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  SidToCheck = 0;
  if ( fIsAdmin == 15 )
  {
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
      return 0;
    if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
    {
      FreeSid(SidToCheck);
      return 0;
    }
    fIsAdmin = IsMember;
    FreeSid(SidToCheck);
    return (unsigned int)fIsAdmin;
  }
  return result;
}

```

## disassembly

```asm
0x180003b1c  mov     [rsp-8+arg_0], rbx
0x180003b21  push    rbp
0x180003b22  mov     rbp, rsp
0x180003b25  sub     rsp, 80h
0x180003b2c  mov     rax, cs:__security_cookie
0x180003b33  xor     rax, rsp
0x180003b36  mov     [rbp+var_8], rax
0x180003b3a  mov     eax, cs:fIsAdmin
0x180003b40  xor     ebx, ebx
0x180003b42  mov     [rbp+IsMember], ebx
0x180003b45  mov     dword ptr [rbp+pIdentifierAuthority.Value], ebx
0x180003b48  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x180003b4e  mov     [rbp+SidToCheck], rbx
0x180003b52  cmp     eax, 0Fh
0x180003b55  jnz     short loc_180003BCB
0x180003b57  lea     rax, [rbp+SidToCheck]
0x180003b5b  mov     r9d, 220h; nSubAuthority1
0x180003b61  mov     [rsp+80h+pSid], rax; pSid
0x180003b66  lea     r8d, [rbx+20h]; nSubAuthority0
0x180003b6a  mov     [rsp+80h+nSubAuthority7], ebx; nSubAuthority7
0x180003b6e  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180003b72  mov     [rsp+80h+nSubAuthority6], ebx; nSubAuthority6
0x180003b76  mov     dl, 2; nSubAuthorityCount
0x180003b78  mov     [rsp+80h+nSubAuthority5], ebx; nSubAuthority5
0x180003b7c  mov     [rsp+80h+nSubAuthority4], ebx; nSubAuthority4
0x180003b80  mov     [rsp+80h+nSubAuthority3], ebx; nSubAuthority3
0x180003b84  mov     [rsp+80h+nSubAuthority2], ebx; nSubAuthority2
0x180003b88  call    cs:__imp_AllocateAndInitializeSid
0x180003b8e  test    eax, eax
0x180003b90  jnz     short loc_180003B96
0x180003b92  xor     eax, eax
0x180003b94  jmp     short loc_180003BCB
0x180003b96  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x180003b9a  lea     r8, [rbp+IsMember]; IsMember
0x180003b9e  xor     ecx, ecx; TokenHandle
0x180003ba0  call    cs:__imp_CheckTokenMembership
0x180003ba6  mov     rcx, [rbp+SidToCheck]; pSid
0x180003baa  test    eax, eax
0x180003bac  jnz     short loc_180003BB6
0x180003bae  call    cs:__imp_FreeSid
0x180003bb4  jmp     short loc_180003B92
0x180003bb6  mov     eax, [rbp+IsMember]
0x180003bb9  mov     cs:fIsAdmin, eax
0x180003bbf  call    cs:__imp_FreeSid
0x180003bc5  mov     eax, cs:fIsAdmin
0x180003bcb  mov     rcx, [rbp+var_8]
0x180003bcf  xor     rcx, rsp; StackCookie
0x180003bd2  call    __security_check_cookie
0x180003bd7  mov     rbx, [rsp+80h+arg_0]
0x180003bdf  add     rsp, 80h
0x180003be6  pop     rbp
0x180003be7  retn
```
