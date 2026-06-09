# IsWcmsvc(void)

- ea: `0x180029fb0`
- end: `0x18002a074`
- name: `?IsWcmsvc@@YAHXZ`
- size: `196`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a898`

## callees

- `0x180029fb0`
- `0x18002d200`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002a031`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002a031`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002a045`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002a045`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002a056`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002a056`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 IsWcmsvc(void)
{
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  SidToCheck = 0;
  IsMember = 0;
  if ( AllocateAndInitializeSid(
         &pIdentifierAuthority,
         6u,
         0x50u,
         0xF7B3FCBA,
         0xE6ED954E,
         0xE28CE7BD,
         0x7F0237E4u,
         0x2B5317E0u,
         0,
         0,
         &SidToCheck) )
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
0x180029fb0  push    rbp
0x180029fb2  mov     rbp, rsp
0x180029fb5  sub     rsp, 80h
0x180029fbc  mov     rax, cs:__security_cookie
0x180029fc3  xor     rax, rsp
0x180029fc6  mov     [rbp+var_8], rax
0x180029fca  lea     rax, [rbp+SidToCheck]
0x180029fce  mov     dword ptr [rbp+pIdentifierAuthority.Value], 0
0x180029fd5  mov     [rsp+80h+pSid], rax; pSid
0x180029fda  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180029fde  mov     [rsp+80h+nSubAuthority7], 0; nSubAuthority7
0x180029fe6  mov     r9d, 0F7B3FCBAh; nSubAuthority1
0x180029fec  mov     [rsp+80h+nSubAuthority6], 0; nSubAuthority6
0x180029ff4  mov     r8d, 50h ; 'P'; nSubAuthority0
0x180029ffa  mov     [rsp+80h+nSubAuthority5], 2B5317E0h; nSubAuthority5
0x18002a002  mov     dl, 6; nSubAuthorityCount
0x18002a004  mov     [rsp+80h+nSubAuthority4], 7F0237E4h; nSubAuthority4
0x18002a00c  mov     [rsp+80h+nSubAuthority3], 0E28CE7BDh; nSubAuthority3
0x18002a014  mov     [rsp+80h+nSubAuthority2], 0E6ED954Eh; nSubAuthority2
0x18002a01c  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x18002a022  mov     [rbp+SidToCheck], 0
0x18002a02a  mov     [rbp+IsMember], 0
0x18002a031  call    cs:__imp_AllocateAndInitializeSid
0x18002a037  test    eax, eax
0x18002a039  jz      short loc_18002A05C
0x18002a03b  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x18002a03f  lea     r8, [rbp+IsMember]; IsMember
0x18002a043  xor     ecx, ecx; TokenHandle
0x18002a045  call    cs:__imp_CheckTokenMembership
0x18002a04b  test    eax, eax
0x18002a04d  jnz     short loc_18002A052
0x18002a04f  mov     [rbp+IsMember], eax
0x18002a052  mov     rcx, [rbp+SidToCheck]; pSid
0x18002a056  call    cs:__imp_FreeSid
0x18002a05c  mov     eax, [rbp+IsMember]
0x18002a05f  mov     rcx, [rbp+var_8]
0x18002a063  xor     rcx, rsp; StackCookie
0x18002a066  call    __security_check_cookie
0x18002a06b  add     rsp, 80h
0x18002a072  pop     rbp
0x18002a073  retn
```
