# basessp::BaseSSP::WSTInitGlobalVariables(void)

- ea: `0x1800435e0`
- end: `0x1800436a9`
- name: `?WSTInitGlobalVariables@BaseSSP@basessp@@AEAAJXZ`
- size: `201`
- prototype: `__int64 __fastcall(basessp::BaseSSP *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800434dc`

## callees

- `0x1800210f0`
- `0x1800435e0`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x180043642`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180043688`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180043642`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180043688`

## pseudocode

```c
int __fastcall basessp::BaseSSP::WSTInitGlobalVariables(PSID *this)
{
  PSID *Sid; // rcx
  int result; // eax
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+60h] [rbp-18h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  Sid = this + 28;
  result = 0;
  if ( *Sid
    || (result = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, Sid), result >= 0) )
  {
    if ( !this[29] )
      return RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, this + 29);
  }
  return result;
}

```

## disassembly

```asm
0x1800435e0  mov     [rsp+arg_8], rbx
0x1800435e5  push    rdi
0x1800435e6  sub     rsp, 70h
0x1800435ea  mov     rax, cs:__security_cookie
0x1800435f1  xor     rax, rsp
0x1800435f4  mov     [rsp+78h+var_10], rax
0x1800435f9  xor     edi, edi
0x1800435fb  mov     word ptr [rsp+78h+IdentifierAuthority.Value+4], 500h
0x180043602  mov     rbx, rcx
0x180043605  mov     dword ptr [rsp+78h+IdentifierAuthority.Value], edi
0x180043609  add     rcx, 0E0h
0x180043610  mov     eax, edi
0x180043612  cmp     [rcx], rdi
0x180043615  jnz     short loc_18004364C
0x180043617  mov     [rsp+78h+Sid], rcx; Sid
0x18004361c  lea     r8d, [rdi+12h]; SubAuthority0
0x180043620  mov     [rsp+78h+SubAuthority7], edi; SubAuthority7
0x180043624  lea     rcx, [rsp+78h+IdentifierAuthority]; IdentifierAuthority
0x180043629  mov     [rsp+78h+SubAuthority6], edi; SubAuthority6
0x18004362d  xor     r9d, r9d; SubAuthority1
0x180043630  mov     [rsp+78h+SubAuthority5], edi; SubAuthority5
0x180043634  mov     dl, 1; SubAuthorityCount
0x180043636  mov     [rsp+78h+SubAuthority4], edi; SubAuthority4
0x18004363a  mov     [rsp+78h+SubAuthority3], edi; SubAuthority3
0x18004363e  mov     [rsp+78h+SubAuthority2], edi; SubAuthority2
0x180043642  call    cs:__imp_RtlAllocateAndInitializeSid
0x180043648  test    eax, eax
0x18004364a  js      short loc_18004368E
0x18004364c  lea     rcx, [rbx+0E8h]
0x180043653  cmp     [rcx], rdi
0x180043656  jnz     short loc_18004368E
0x180043658  mov     [rsp+78h+Sid], rcx; Sid
0x18004365d  mov     r9d, 220h; SubAuthority1
0x180043663  mov     [rsp+78h+SubAuthority7], edi; SubAuthority7
0x180043667  lea     rcx, [rsp+78h+IdentifierAuthority]; IdentifierAuthority
0x18004366c  mov     [rsp+78h+SubAuthority6], edi; SubAuthority6
0x180043670  mov     r8d, 20h ; ' '; SubAuthority0
0x180043676  mov     [rsp+78h+SubAuthority5], edi; SubAuthority5
0x18004367a  mov     dl, 2; SubAuthorityCount
0x18004367c  mov     [rsp+78h+SubAuthority4], edi; SubAuthority4
0x180043680  mov     [rsp+78h+SubAuthority3], edi; SubAuthority3
0x180043684  mov     [rsp+78h+SubAuthority2], edi; SubAuthority2
0x180043688  call    cs:__imp_RtlAllocateAndInitializeSid
0x18004368e  mov     rcx, [rsp+78h+var_10]
0x180043693  xor     rcx, rsp; StackCookie
0x180043696  call    __security_check_cookie
0x18004369b  mov     rbx, [rsp+78h+arg_8]
0x1800436a3  add     rsp, 70h
0x1800436a7  pop     rdi
0x1800436a8  retn
```
