# IsSystem(void)

- ea: `0x140003bf8`
- end: `0x140003cbd`
- name: `?IsSystem@@YAHXZ`
- size: `197`
- prototype: `int(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140004108`
- `0x14000ba88`

## callees

- `0x140003bf8`
- `0x1400109c0`

## import_xrefs

- `ADVAPI32!CheckTokenMembership` at `0x140003c77`
- `ADVAPI32!CheckTokenMembership` at `0x140003c77`
- `ADVAPI32!FreeSid` at `0x140003c96`
- `ADVAPI32!FreeSid` at `0x140003c96`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140003c5d`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140003c5d`

## pseudocode

```c
_BOOL8 IsSystem(void)
{
  BOOL v0; // ebx
  WINBOOL IsMember; // [rsp+60h] [rbp+17h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp+1Fh] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  IsMember = 0;
  v0 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck)
    && CheckTokenMembership(0, SidToCheck, &IsMember) )
  {
    v0 = IsMember != 0;
  }
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return v0;
}

```

## disassembly

```asm
0x140003bf8  push    rbp
0x140003bfa  push    rbx
0x140003bfb  push    rsi
0x140003bfc  push    rdi
0x140003bfd  lea     rbp, [rsp-3Fh]
0x140003c02  sub     rsp, 88h
0x140003c09  mov     rax, cs:__security_cookie
0x140003c10  xor     rax, rsp
0x140003c13  mov     [rbp+57h+var_28], rax
0x140003c17  xor     edi, edi
0x140003c19  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x140003c1f  lea     rax, [rbp+57h+SidToCheck]
0x140003c23  mov     [rbp+57h+IsMember], edi
0x140003c26  mov     [rsp+0A0h+pSid], rax; pSid
0x140003c2b  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x140003c2f  mov     [rsp+0A0h+nSubAuthority7], edi; nSubAuthority7
0x140003c33  xor     r9d, r9d; nSubAuthority1
0x140003c36  mov     [rsp+0A0h+nSubAuthority6], edi; nSubAuthority6
0x140003c3a  lea     esi, [rdi+1]
0x140003c3d  mov     [rsp+0A0h+nSubAuthority5], edi; nSubAuthority5
0x140003c41  lea     r8d, [rdi+12h]; nSubAuthority0
0x140003c45  mov     [rsp+0A0h+nSubAuthority4], edi; nSubAuthority4
0x140003c49  mov     dl, sil; nSubAuthorityCount
0x140003c4c  mov     [rsp+0A0h+nSubAuthority3], edi; nSubAuthority3
0x140003c50  mov     ebx, edi
0x140003c52  mov     [rsp+0A0h+nSubAuthority2], edi; nSubAuthority2
0x140003c56  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x140003c59  mov     [rbp+57h+SidToCheck], rdi
0x140003c5d  call    cs:__imp_AllocateAndInitializeSid
0x140003c64  nop     dword ptr [rax+rax+00h]
0x140003c69  test    eax, eax
0x140003c6b  jz      short loc_140003C8D
0x140003c6d  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x140003c71  lea     r8, [rbp+57h+IsMember]; IsMember
0x140003c75  xor     ecx, ecx; TokenHandle
0x140003c77  call    cs:__imp_CheckTokenMembership
0x140003c7e  nop     dword ptr [rax+rax+00h]
0x140003c83  test    eax, eax
0x140003c85  jz      short loc_140003C8D
0x140003c87  cmp     [rbp+57h+IsMember], edi
0x140003c8a  cmovnz  ebx, esi
0x140003c8d  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x140003c91  test    rcx, rcx
0x140003c94  jz      short loc_140003CA2
0x140003c96  call    cs:__imp_FreeSid
0x140003c9d  nop     dword ptr [rax+rax+00h]
0x140003ca2  mov     eax, ebx
0x140003ca4  mov     rcx, [rbp+57h+var_28]
0x140003ca8  xor     rcx, rsp; StackCookie
0x140003cab  call    __security_check_cookie
0x140003cb0  add     rsp, 88h
0x140003cb7  pop     rdi
0x140003cb8  pop     rsi
0x140003cb9  pop     rbx
0x140003cba  pop     rbp
0x140003cbb  retn
```
