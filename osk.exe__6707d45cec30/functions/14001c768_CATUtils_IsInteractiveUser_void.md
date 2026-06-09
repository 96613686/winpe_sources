# CATUtils::IsInteractiveUser(void)

- ea: `0x14001c768`
- end: `0x14001c823`
- name: `?IsInteractiveUser@CATUtils@@SAHXZ`
- size: `187`
- prototype: `static int(void)`
- caller_count: `9`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14001b51c`
- `0x14001ec2c`
- `0x14001f728`
- `0x1400205a8`
- `0x140020938`
- `0x140020d24`
- `0x14002491c`
- `0x140024ba4`
- `0x140025184`

## callees

- `0x14001c768`
- `0x140025d70`

## import_xrefs

- `ADVAPI32!CheckTokenMembership` at `0x14001c7ec`
- `ADVAPI32!CheckTokenMembership` at `0x14001c7ec`
- `ADVAPI32!FreeSid` at `0x14001c7f8`
- `ADVAPI32!FreeSid` at `0x14001c7f8`
- `ADVAPI32!AllocateAndInitializeSid` at `0x14001c7cb`
- `ADVAPI32!AllocateAndInitializeSid` at `0x14001c7cb`

## pseudocode

```c
__int64 CATUtils::IsInteractiveUser(void)
{
  unsigned int v0; // edi
  PSID v1; // rdx
  BOOL v2; // ebx
  WINBOOL IsMember; // [rsp+60h] [rbp+17h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp+1Fh] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  IsMember = 0;
  v0 = 1;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 4u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    v1 = SidToCheck;
  }
  else
  {
    v1 = 0;
    SidToCheck = 0;
  }
  if ( !v1 )
    return 0;
  v2 = CheckTokenMembership(0, v1, &IsMember);
  FreeSid(SidToCheck);
  if ( !v2 || !IsMember )
    return 0;
  return v0;
}

```

## disassembly

```asm
0x14001c768  push    rbp
0x14001c76a  push    rbx
0x14001c76b  push    rsi
0x14001c76c  push    rdi
0x14001c76d  lea     rbp, [rsp-3Fh]
0x14001c772  sub     rsp, 88h
0x14001c779  mov     rax, cs:__security_cookie
0x14001c780  xor     rax, rsp
0x14001c783  mov     [rbp+57h+var_28], rax
0x14001c787  xor     esi, esi
0x14001c789  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x14001c78f  lea     rax, [rbp+57h+SidToCheck]
0x14001c793  mov     [rbp+57h+IsMember], esi
0x14001c796  mov     [rsp+0A0h+pSid], rax; pSid
0x14001c79b  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x14001c79f  mov     [rsp+0A0h+nSubAuthority7], esi; nSubAuthority7
0x14001c7a3  xor     r9d, r9d; nSubAuthority1
0x14001c7a6  mov     [rsp+0A0h+nSubAuthority6], esi; nSubAuthority6
0x14001c7aa  lea     edi, [rsi+1]
0x14001c7ad  mov     [rsp+0A0h+nSubAuthority5], esi; nSubAuthority5
0x14001c7b1  lea     r8d, [rsi+4]; nSubAuthority0
0x14001c7b5  mov     [rsp+0A0h+nSubAuthority4], esi; nSubAuthority4
0x14001c7b9  mov     dl, dil; nSubAuthorityCount
0x14001c7bc  mov     [rsp+0A0h+nSubAuthority3], esi; nSubAuthority3
0x14001c7c0  mov     [rsp+0A0h+nSubAuthority2], esi; nSubAuthority2
0x14001c7c4  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x14001c7c7  mov     [rbp+57h+SidToCheck], rsi
0x14001c7cb  call    cs:__imp_AllocateAndInitializeSid
0x14001c7d1  test    eax, eax
0x14001c7d3  jnz     short loc_14001C7DD
0x14001c7d5  mov     edx, esi
0x14001c7d7  mov     [rbp+57h+SidToCheck], rdx
0x14001c7db  jmp     short loc_14001C7E1
0x14001c7dd  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x14001c7e1  test    rdx, rdx
0x14001c7e4  jz      short loc_14001C807
0x14001c7e6  lea     r8, [rbp+57h+IsMember]; IsMember
0x14001c7ea  xor     ecx, ecx; TokenHandle
0x14001c7ec  call    cs:__imp_CheckTokenMembership
0x14001c7f2  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x14001c7f6  mov     ebx, eax
0x14001c7f8  call    cs:__imp_FreeSid
0x14001c7fe  test    ebx, ebx
0x14001c800  jz      short loc_14001C807
0x14001c802  cmp     [rbp+57h+IsMember], esi
0x14001c805  jnz     short loc_14001C809
0x14001c807  mov     edi, esi
0x14001c809  mov     eax, edi
0x14001c80b  mov     rcx, [rbp+57h+var_28]
0x14001c80f  xor     rcx, rsp; StackCookie
0x14001c812  call    __security_check_cookie
0x14001c817  add     rsp, 88h
0x14001c81e  pop     rdi
0x14001c81f  pop     rsi
0x14001c820  pop     rbx
0x14001c821  pop     rbp
0x14001c822  retn
```
