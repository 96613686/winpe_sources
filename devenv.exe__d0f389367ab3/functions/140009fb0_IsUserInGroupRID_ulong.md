# IsUserInGroupRID(ulong)

- ea: `0x140009fb0`
- end: `0x14000a058`
- name: `?IsUserInGroupRID@@YAHK@Z`
- size: `168`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000a060`
- `0x140024c30`

## callees

- `0x140001020`
- `0x140009fb0`

## import_xrefs

- `ADVAPI32!AllocateAndInitializeSid` at `0x14000a00a`
- `ADVAPI32!AllocateAndInitializeSid` at `0x14000a00a`
- `ADVAPI32!CheckTokenMembership` at `0x14000a021`
- `ADVAPI32!CheckTokenMembership` at `0x14000a021`
- `ADVAPI32!FreeSid` at `0x14000a032`
- `ADVAPI32!FreeSid` at `0x14000a032`

## pseudocode

```c
BOOL __fastcall IsUserInGroupRID()
{
  BOOL result; // eax
  PSID SidToCheck; // [rsp+60h] [rbp-20h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp-18h] BYREF
  BOOL IsMember; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  result = AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck);
  IsMember = result;
  if ( result )
  {
    if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
      IsMember = 0;
    FreeSid(SidToCheck);
    return IsMember;
  }
  return result;
}

```

## disassembly

```asm
0x140009fb0  mov     [rsp-8+arg_0], rbx
0x140009fb5  push    rbp
0x140009fb6  mov     rbp, rsp
0x140009fb9  sub     rsp, 80h
0x140009fc0  mov     rax, cs:__security_cookie
0x140009fc7  xor     rax, rsp
0x140009fca  mov     [rbp+var_8], rax
0x140009fce  xor     ebx, ebx
0x140009fd0  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x140009fd6  lea     rax, [rbp+SidToCheck]
0x140009fda  mov     dword ptr [rbp+pIdentifierAuthority.Value], ebx
0x140009fdd  mov     [rsp+80h+pSid], rax; pSid
0x140009fe2  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x140009fe6  mov     [rsp+80h+nSubAuthority7], ebx; nSubAuthority7
0x140009fea  mov     r9d, 220h; nSubAuthority1
0x140009ff0  mov     [rsp+80h+nSubAuthority6], ebx; nSubAuthority6
0x140009ff4  lea     r8d, [rbx+20h]; nSubAuthority0
0x140009ff8  mov     [rsp+80h+nSubAuthority5], ebx; nSubAuthority5
0x140009ffc  mov     dl, 2; nSubAuthorityCount
0x140009ffe  mov     [rsp+80h+nSubAuthority4], ebx; nSubAuthority4
0x14000a002  mov     [rsp+80h+nSubAuthority3], ebx; nSubAuthority3
0x14000a006  mov     [rsp+80h+nSubAuthority2], ebx; nSubAuthority2
0x14000a00a  call    cs:__imp_AllocateAndInitializeSid
0x14000a010  mov     [rbp+IsMember], eax
0x14000a013  test    eax, eax
0x14000a015  jz      short loc_14000A03B
0x14000a017  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x14000a01b  lea     r8, [rbp+IsMember]; IsMember
0x14000a01f  xor     ecx, ecx; TokenHandle
0x14000a021  call    cs:__imp_CheckTokenMembership
0x14000a027  test    eax, eax
0x14000a029  jnz     short loc_14000A02E
0x14000a02b  mov     [rbp+IsMember], ebx
0x14000a02e  mov     rcx, [rbp+SidToCheck]; pSid
0x14000a032  call    cs:__imp_FreeSid
0x14000a038  mov     eax, [rbp+IsMember]
0x14000a03b  mov     rcx, [rbp+var_8]
0x14000a03f  xor     rcx, rsp; StackCookie
0x14000a042  call    __security_check_cookie
0x14000a047  mov     rbx, [rsp+80h+arg_0]
0x14000a04f  add     rsp, 80h
0x14000a056  pop     rbp
0x14000a057  retn
```
