# IsProcessDWM(void)

- ea: `0x18004d4a4`
- end: `0x18004d546`
- name: `?IsProcessDWM@@YAHXZ`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005be40`

## callees

- `0x18004d4a4`
- `0x180075fa0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18004d520`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18004d520`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18004d516`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18004d516`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18004d502`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18004d502`

## pseudocode

```c
__int64 IsProcessDWM(void)
{
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  IsMember = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x5Au, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    CheckTokenMembership(0, SidToCheck, &IsMember);
    FreeSid(SidToCheck);
  }
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x18004d4a4  mov     [rsp-8+arg_0], rbx
0x18004d4a9  push    rbp
0x18004d4aa  mov     rbp, rsp
0x18004d4ad  sub     rsp, 80h
0x18004d4b4  mov     rax, cs:__security_cookie
0x18004d4bb  xor     rax, rsp
0x18004d4be  mov     [rbp+var_8], rax
0x18004d4c2  xor     ebx, ebx
0x18004d4c4  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x18004d4ca  lea     rax, [rbp+SidToCheck]
0x18004d4ce  mov     dword ptr [rbp+pIdentifierAuthority.Value], ebx
0x18004d4d1  mov     [rsp+80h+pSid], rax; pSid
0x18004d4d6  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18004d4da  mov     [rsp+80h+nSubAuthority7], ebx; nSubAuthority7
0x18004d4de  xor     r9d, r9d; nSubAuthority1
0x18004d4e1  mov     [rsp+80h+nSubAuthority6], ebx; nSubAuthority6
0x18004d4e5  lea     r8d, [rbx+5Ah]; nSubAuthority0
0x18004d4e9  mov     [rsp+80h+nSubAuthority5], ebx; nSubAuthority5
0x18004d4ed  mov     dl, 2; nSubAuthorityCount
0x18004d4ef  mov     [rsp+80h+nSubAuthority4], ebx; nSubAuthority4
0x18004d4f3  mov     [rsp+80h+nSubAuthority3], ebx; nSubAuthority3
0x18004d4f7  mov     [rsp+80h+nSubAuthority2], ebx; nSubAuthority2
0x18004d4fb  mov     [rbp+SidToCheck], rbx
0x18004d4ff  mov     [rbp+IsMember], ebx
0x18004d502  call    cs:__imp_AllocateAndInitializeSid
0x18004d508  test    eax, eax
0x18004d50a  jz      short loc_18004D526
0x18004d50c  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x18004d510  lea     r8, [rbp+IsMember]; IsMember
0x18004d514  xor     ecx, ecx; TokenHandle
0x18004d516  call    cs:__imp_CheckTokenMembership
0x18004d51c  mov     rcx, [rbp+SidToCheck]; pSid
0x18004d520  call    cs:__imp_FreeSid
0x18004d526  mov     eax, [rbp+IsMember]
0x18004d529  mov     rcx, [rbp+var_8]
0x18004d52d  xor     rcx, rsp; StackCookie
0x18004d530  call    __security_check_cookie
0x18004d535  mov     rbx, [rsp+80h+arg_0]
0x18004d53d  add     rsp, 80h
0x18004d544  pop     rbp
0x18004d545  retn
```
