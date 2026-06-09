# CUstComputer::_SearchAD(ldap *,ushort *,ushort * * *,ulong &)

- ea: `0x18001c284`
- end: `0x18001c416`
- name: `?_SearchAD@CUstComputer@@KAJPEAUldap@@PEAGPEAPEAPEAGAEAK@Z`
- size: `402`
- prototype: `__int64 __fastcall(struct ldap *, PWSTR base, unsigned __int16 ***, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001b8a0`

## callees

- `0x18000a520`
- `0x18000a8f0`
- `0x18001afa0`
- `0x18001afc8`
- `0x18001bb38`
- `0x18001bf44`
- `0x18001c284`

## import_xrefs

- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001c386`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001c386`
- `WLDAP32!__imp_ldap_msgfree` at `0x18001c3e1`
- `WLDAP32!__imp_ldap_msgfree` at `0x18001c3e1`
- `WLDAP32!__imp_ldap_search_sW` at `0x18001c321`
- `WLDAP32!__imp_ldap_search_sW` at `0x18001c321`

## string_xrefs

- `0x18001c2ea`: `msDS-IsPrimaryComputerFor`

## pseudocode

```c
__int64 __fastcall CUstComputer::_SearchAD(struct ldap *a1, PWSTR base, unsigned __int16 ***a3, unsigned int *a4)
{
  unsigned __int64 v8; // rdx
  signed int v9; // ebx
  ULONG v10; // ebx
  __int64 v11; // r9
  UstCommon::CImpersonator *v12; // rcx
  signed int v13; // eax
  __int64 v14; // r9
  PWSTR filter; // [rsp+40h] [rbp-68h] BYREF
  LDAPMessage *res; // [rsp+48h] [rbp-60h] BYREF
  PWSTR attrs[3]; // [rsp+50h] [rbp-58h] BYREF

  res = 0;
  filter = 0;
  v9 = CUstComputer::_ConstructFilterString(&filter);
  if ( v9 >= 0 )
  {
    attrs[0] = (PWSTR)L"cn";
    attrs[2] = 0;
    attrs[1] = (PWSTR)L"msDS-IsPrimaryComputerFor";
    v10 = ldap_search_sW(a1, base, 2u, filter, attrs, 0, &res);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_ab0185983553356c12180ac14bccd298_Traceguids, v11);
      v12 = WPP_GLOBAL_Control;
    }
    if ( !v10 )
      goto LABEL_12;
    if ( v12 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)v12 + 2), 28, WPP_ab0185983553356c12180ac14bccd298_Traceguids, v10);
    v13 = LdapMapErrorToWin32(v10);
    v9 = v13;
    if ( v13 > 0 )
      v9 = (unsigned __int16)v13 | 0x80070000;
    if ( v9 >= 0 )
LABEL_12:
      v9 = CUstComputer::_ProcessEntries(a1, res, a3, a4);
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_ab0185983553356c12180ac14bccd298_Traceguids, v14);
    }
    if ( res )
      ldap_msgfree(res);
  }
  if ( filter )
    operator delete(filter, v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001c284  push    rbx
0x18001c286  push    rbp
0x18001c287  push    rsi
0x18001c288  push    r13
0x18001c28a  push    r14
0x18001c28c  push    r15
0x18001c28e  sub     rsp, 78h
0x18001c292  mov     rax, cs:__security_cookie
0x18001c299  xor     rax, rsp
0x18001c29c  mov     [rsp+0A8h+var_40], rax
0x18001c2a1  mov     rbp, rcx
0x18001c2a4  mov     [rsp+0A8h+var_60], 0
0x18001c2ad  lea     rcx, [rsp+0A8h+filter]; unsigned __int16 **
0x18001c2b2  mov     [rsp+0A8h+filter], 0
0x18001c2bb  mov     r15, r9
0x18001c2be  mov     r14, r8
0x18001c2c1  mov     rsi, rdx
0x18001c2c4  call    ?_ConstructFilterString@CUstComputer@@KAJPEAPEAG@Z; CUstComputer::_ConstructFilterString(ushort * *)
0x18001c2c9  mov     ebx, eax
0x18001c2cb  test    eax, eax
0x18001c2cd  js      loc_18001C3E7
0x18001c2d3  mov     r9, [rsp+0A8h+filter]; filter
0x18001c2d8  lea     rax, aCn; "cn"
0x18001c2df  mov     [rsp+0A8h+var_58], rax
0x18001c2e4  mov     r8d, 2; scope
0x18001c2ea  lea     rax, aMsdsIsprimaryc; "msDS-IsPrimaryComputerFor"
0x18001c2f1  mov     [rsp+0A8h+var_48], 0
0x18001c2fa  mov     [rsp+0A8h+var_50], rax
0x18001c2ff  mov     rdx, rsi; base
0x18001c302  lea     rax, [rsp+0A8h+var_60]
0x18001c307  mov     rcx, rbp; ld
0x18001c30a  mov     [rsp+0A8h+res], rax; res
0x18001c30f  lea     rax, [rsp+0A8h+var_58]
0x18001c314  mov     [rsp+0A8h+attrsonly], 0; attrsonly
0x18001c31c  mov     [rsp+0A8h+attrs], rax; attrs
0x18001c321  call    cs:__imp_ldap_search_sW
0x18001c327  mov     ebx, eax
0x18001c329  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c330  lea     r13, WPP_GLOBAL_Control
0x18001c337  lea     rsi, WPP_ab0185983553356c12180ac14bccd298_Traceguids
0x18001c33e  cmp     rcx, r13
0x18001c341  jz      short loc_18001C361
0x18001c343  test    byte ptr [rcx+1Ch], 8
0x18001c347  jz      short loc_18001C361
0x18001c349  mov     rcx, [rcx+10h]
0x18001c34d  mov     edx, 1Bh
0x18001c352  mov     r8, rsi
0x18001c355  call    WPP_SF_
0x18001c35a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c361  test    ebx, ebx
0x18001c363  jz      short loc_18001C39F
0x18001c365  cmp     rcx, r13
0x18001c368  jz      short loc_18001C384
0x18001c36a  test    byte ptr [rcx+1Ch], 1
0x18001c36e  jz      short loc_18001C384
0x18001c370  mov     rcx, [rcx+10h]
0x18001c374  mov     edx, 1Ch
0x18001c379  mov     r9d, ebx
0x18001c37c  mov     r8, rsi
0x18001c37f  call    WPP_SF_d
0x18001c384  mov     ecx, ebx; LdapError
0x18001c386  call    cs:__imp_LdapMapErrorToWin32
0x18001c38c  mov     ebx, eax
0x18001c38e  test    eax, eax
0x18001c390  jle     short loc_18001C39B
0x18001c392  movzx   ebx, ax
0x18001c395  or      ebx, 80070000h
0x18001c39b  test    ebx, ebx
0x18001c39d  js      short loc_18001C3B4
0x18001c39f  mov     rdx, [rsp+0A8h+var_60]; res
0x18001c3a4  mov     r9, r15; unsigned int *
0x18001c3a7  mov     r8, r14; unsigned __int16 ***
0x18001c3aa  mov     rcx, rbp; struct ldap *
0x18001c3ad  call    ?_ProcessEntries@CUstComputer@@KAJPEAUldap@@PEAUldapmsg@@PEAPEAPEAGAEAK@Z; CUstComputer::_ProcessEntries(ldap *,ldapmsg *,ushort * * *,ulong &)
0x18001c3b2  mov     ebx, eax
0x18001c3b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c3bb  cmp     rcx, r13
0x18001c3be  jz      short loc_18001C3D7
0x18001c3c0  test    byte ptr [rcx+1Ch], 8
0x18001c3c4  jz      short loc_18001C3D7
0x18001c3c6  mov     rcx, [rcx+10h]
0x18001c3ca  mov     edx, 1Dh
0x18001c3cf  mov     r8, rsi
0x18001c3d2  call    WPP_SF_
0x18001c3d7  mov     rcx, [rsp+0A8h+var_60]; res
0x18001c3dc  test    rcx, rcx
0x18001c3df  jz      short loc_18001C3E7
0x18001c3e1  call    cs:__imp_ldap_msgfree
0x18001c3e7  cmp     [rsp+0A8h+filter], 0
0x18001c3ed  jz      short loc_18001C3F9
0x18001c3ef  mov     rcx, [rsp+0A8h+filter]; void *
0x18001c3f4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c3f9  mov     eax, ebx
0x18001c3fb  mov     rcx, [rsp+0A8h+var_40]
0x18001c400  xor     rcx, rsp; StackCookie
0x18001c403  call    __security_check_cookie
0x18001c408  add     rsp, 78h
0x18001c40c  pop     r15
0x18001c40e  pop     r14
0x18001c410  pop     r13
0x18001c412  pop     rsi
0x18001c413  pop     rbp
0x18001c414  pop     rbx
0x18001c415  retn
```
