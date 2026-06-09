# Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)

- ea: `0x18003d6cc`
- end: `0x18003d782`
- name: `?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z`
- size: `182`
- prototype: `void __fastcall(Vml::VmAcl *__hidden this, void *, unsigned int, unsigned int, enum _ACCESS_MODE)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003d788`

## callees

- `0x1800067c0`
- `0x180027380`
- `0x18003d6cc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d74c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d74c`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18003d733`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18003d733`

## string_xrefs

- `0x18003d76d`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
void __fastcall Vml::VmAcl::UpdateAccess(struct _ACL **this, WCHAR *a2, DWORD a3, DWORD a4, enum _ACCESS_MODE a5)
{
  struct _ACL *v6; // r8
  DWORD v7; // eax
  struct _ACL *v8; // rcx
  PACL NewAcl; // [rsp+20h] [rbp-40h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+28h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  pListOfExplicitEntries.grfAccessPermissions = a3;
  v6 = *this;
  pListOfExplicitEntries.grfInheritance = a4;
  pListOfExplicitEntries.Trustee.ptstrName = a2;
  memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 28);
  pListOfExplicitEntries.grfAccessMode = a5;
  NewAcl = 0;
  v7 = SetEntriesInAclW(1u, &pListOfExplicitEntries, v6, &NewAcl);
  if ( v7 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x1713,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      (const char *)v7,
      (unsigned int)NewAcl);
  v8 = *this;
  *this = NewAcl;
  if ( v8 )
    LocalFree(v8);
}

```

## disassembly

```asm
0x18003d6cc  mov     [rsp-8+arg_8], rbx
0x18003d6d1  push    rbp
0x18003d6d2  mov     rbp, rsp
0x18003d6d5  sub     rsp, 60h
0x18003d6d9  mov     rax, cs:__security_cookie
0x18003d6e0  xor     rax, rsp
0x18003d6e3  mov     [rbp+var_8], rax
0x18003d6e7  mov     eax, [rbp+arg_20]
0x18003d6ea  mov     rbx, rcx
0x18003d6ed  mov     [rbp+pListOfExplicitEntries.grfAccessPermissions], r8d
0x18003d6f1  mov     r8, [rcx]; OldAcl
0x18003d6f4  mov     ecx, 1; cCountOfExplicitEntries
0x18003d6f9  mov     [rbp+pListOfExplicitEntries.grfInheritance], r9d
0x18003d6fd  lea     r9, [rbp+NewAcl]; NewAcl
0x18003d701  mov     [rbp+pListOfExplicitEntries.Trustee.ptstrName], rdx
0x18003d705  lea     rdx, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x18003d709  mov     dword ptr [rbp+pListOfExplicitEntries+0Ch], 0
0x18003d710  mov     qword ptr [rbp+pListOfExplicitEntries.Trustee.TrusteeType], 0
0x18003d718  mov     [rbp+pListOfExplicitEntries.grfAccessMode], eax
0x18003d71b  mov     [rbp+pListOfExplicitEntries.Trustee.pMultipleTrustee], 0
0x18003d723  mov     qword ptr [rbp+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], 0
0x18003d72b  mov     [rbp+NewAcl], 0
0x18003d733  call    cs:__imp_SetEntriesInAclW
0x18003d739  test    eax, eax
0x18003d73b  jnz     short loc_18003D769
0x18003d73d  mov     rcx, [rbx]; hMem
0x18003d740  mov     rax, [rbp+NewAcl]
0x18003d744  mov     [rbx], rax
0x18003d747  test    rcx, rcx
0x18003d74a  jz      short loc_18003D752
0x18003d74c  call    cs:__imp_LocalFree
0x18003d752  mov     rcx, [rbp+var_8]
0x18003d756  xor     rcx, rsp; StackCookie
0x18003d759  call    __security_check_cookie
0x18003d75e  mov     rbx, [rsp+60h+arg_8]
0x18003d763  add     rsp, 60h
0x18003d767  pop     rbp
0x18003d768  retn
0x18003d769  mov     rcx, [rbp+8]; this
0x18003d76d  lea     r8, aOnecoreVmCommo_31; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x18003d774  mov     r9d, eax; char *
0x18003d777  mov     edx, 1713h; void *
0x18003d77c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
