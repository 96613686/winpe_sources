# DfsStampSD

- ea: `0x14005a780`
- end: `0x14005a86a`
- name: `DfsStampSD`
- size: `234`
- prototype: `__int64 __usercall@<rax>(PWSTR dn@<rcx>, LDAP *ld)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140059f80`
- `0x14005a3c0`

## callees

- `0x14005ce70`

## import_xrefs

- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x14005a848`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x14005a848`
- `WLDAP32!__imp_ldap_modify_ext_sW` at `0x14005a83a`
- `WLDAP32!__imp_ldap_modify_ext_sW` at `0x14005a83a`

## string_xrefs

- `0x14005a7b8`: `nTSecurityDescriptor`

## pseudocode

```c
ULONG __fastcall DfsStampSD(PWSTR dn, int a2, __int64 a3, __int64 a4, LDAP *ld)
{
  ULONG v5; // eax
  _DWORD v7[2]; // [rsp+30h] [rbp-41h] BYREF
  __int64 v8; // [rsp+38h] [rbp-39h]
  _QWORD v9[3]; // [rsp+40h] [rbp-31h] BYREF
  char v10; // [rsp+58h] [rbp-19h]
  int v11; // [rsp+59h] [rbp-18h]
  __int16 v12; // [rsp+5Dh] [rbp-14h]
  char v13; // [rsp+5Fh] [rbp-12h]
  _QWORD v14[3]; // [rsp+60h] [rbp-11h] BYREF
  _QWORD v15[2]; // [rsp+78h] [rbp+7h] BYREF
  PLDAPControlW ServerControls[2]; // [rsp+88h] [rbp+17h] BYREF
  LDAPModW *mods[2]; // [rsp+98h] [rbp+27h] BYREF
  int v18; // [rsp+A8h] [rbp+37h] BYREF
  char v19; // [rsp+ACh] [rbp+3Bh]

  v7[0] = a2;
  v8 = a4;
  v9[0] = L"1.2.840.113556.1.4.801";
  v14[1] = L"nTSecurityDescriptor";
  v9[2] = &v18;
  v14[2] = v15;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  ServerControls[0] = (PLDAPControlW)v9;
  mods[0] = (LDAPModW *)v14;
  v15[0] = v7;
  v14[0] = 130;
  v7[1] = 0;
  v9[1] = 5;
  v10 = 1;
  ServerControls[1] = 0;
  v18 = 16909104;
  v19 = 4;
  mods[1] = 0;
  v15[1] = 0;
  v5 = ldap_modify_ext_sW(ld, dn, mods, ServerControls, 0);
  return LdapMapErrorToWin32(v5);
}

```

## disassembly

```asm
0x14005a780  push    rbp
0x14005a782  lea     rbp, [rsp-4Fh]
0x14005a787  sub     rsp, 0C0h
0x14005a78e  mov     rax, cs:__security_cookie
0x14005a795  xor     rax, rsp
0x14005a798  mov     [rbp+4Fh+var_10], rax
0x14005a79c  xor     r10d, r10d
0x14005a79f  mov     [rbp+4Fh+var_90], edx
0x14005a7a2  mov     rax, rcx
0x14005a7a5  mov     [rbp+4Fh+var_88], r9
0x14005a7a9  mov     rcx, [rbp+4Fh+ld]; ld
0x14005a7ad  lea     r8, a12840113556148_0; "1.2.840.113556.1.4.801"
0x14005a7b4  mov     [rbp+4Fh+var_80], r8
0x14005a7b8  lea     rdx, aNtsecuritydesc; "nTSecurityDescriptor"
0x14005a7bf  mov     [rbp+4Fh+var_58], rdx
0x14005a7c3  lea     r8, [rbp+4Fh+var_18]
0x14005a7c7  mov     [rbp+4Fh+var_70], r8
0x14005a7cb  lea     rdx, [rbp+4Fh+var_48]
0x14005a7cf  xor     r8d, r8d
0x14005a7d2  mov     [rbp+4Fh+var_50], rdx
0x14005a7d6  mov     [rbp+4Fh+var_67], r8d
0x14005a7da  lea     r9, [rbp+4Fh+ServerControls]; ServerControls
0x14005a7de  mov     [rbp+4Fh+var_63], r8w
0x14005a7e3  mov     rdx, rax; dn
0x14005a7e6  mov     [rbp+4Fh+var_61], r8b
0x14005a7ea  lea     r8, [rbp+4Fh+var_80]
0x14005a7ee  mov     [rbp+4Fh+ServerControls], r8
0x14005a7f2  lea     r8, [rbp+4Fh+var_60]
0x14005a7f6  mov     [rbp+4Fh+mods], r8
0x14005a7fa  lea     r8, [rbp+4Fh+var_90]
0x14005a7fe  mov     [rbp+4Fh+var_48], r8
0x14005a802  lea     r8, [rbp+4Fh+mods]; mods
0x14005a806  mov     [rbp+4Fh+var_60], 82h
0x14005a80e  mov     [rbp+4Fh+var_8C], r10d
0x14005a812  mov     [rbp+4Fh+var_78], 5
0x14005a81a  mov     [rbp+4Fh+var_68], 1
0x14005a81e  mov     [rbp+4Fh+var_30], r10
0x14005a822  mov     [rbp+4Fh+var_18], 1020330h
0x14005a829  mov     [rbp+4Fh+var_14], 4
0x14005a82d  mov     [rbp+4Fh+var_20], r10
0x14005a831  mov     [rbp+4Fh+var_40], r10
0x14005a835  mov     [rsp+0C0h+ClientControls], r10; ClientControls
0x14005a83a  call    cs:__imp_ldap_modify_ext_sW
0x14005a841  nop     dword ptr [rax+rax+00h]
0x14005a846  mov     ecx, eax; LdapError
0x14005a848  call    cs:__imp_LdapMapErrorToWin32
0x14005a84f  nop     dword ptr [rax+rax+00h]
0x14005a854  mov     rcx, [rbp+4Fh+var_10]
0x14005a858  xor     rcx, rsp; StackCookie
0x14005a85b  call    __security_check_cookie
0x14005a860  add     rsp, 0C0h
0x14005a867  pop     rbp
0x14005a868  retn
```
