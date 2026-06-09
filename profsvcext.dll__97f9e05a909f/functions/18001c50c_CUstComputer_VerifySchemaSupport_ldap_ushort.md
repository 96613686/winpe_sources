# CUstComputer::_VerifySchemaSupport(ldap *,ushort *)

- ea: `0x18001c50c`
- end: `0x18001c644`
- name: `?_VerifySchemaSupport@CUstComputer@@KAJPEAUldap@@PEAG@Z`
- size: `312`
- prototype: `__int64 __fastcall(LDAP *ld, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001b8a0`

## callees

- `0x18000a8f0`
- `0x18001afc8`
- `0x18001b008`
- `0x18001bc94`
- `0x18001c50c`

## import_xrefs

- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001c5fa`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001c5fa`
- `WLDAP32!__imp_ldap_msgfree` at `0x18001c619`
- `WLDAP32!__imp_ldap_msgfree` at `0x18001c619`
- `WLDAP32!__imp_ldap_search_sW` at `0x18001c5c2`
- `WLDAP32!__imp_ldap_search_sW` at `0x18001c5c2`

## pseudocode

```c
__int64 __fastcall CUstComputer::_VerifySchemaSupport(LDAP *ld, unsigned __int16 *a2)
{
  unsigned __int64 v3; // rdx
  signed int v4; // ebx
  ULONG v5; // eax
  ULONG v6; // esi
  signed int v7; // eax
  PWSTR attrs[3]; // [rsp+40h] [rbp-18h] BYREF
  PWSTR base; // [rsp+70h] [rbp+18h] BYREF
  LDAPMessage *res; // [rsp+78h] [rbp+20h] BYREF

  res = 0;
  base = 0;
  v4 = CUstComputer::_ConstructSchemaBaseString(a2, &base);
  if ( v4 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_ab0185983553356c12180ac14bccd298_Traceguids, base);
    }
    attrs[0] = (PWSTR)L"cn";
    attrs[1] = 0;
    v5 = ldap_search_sW(ld, base, 2u, (const PWSTR)L"(objectClass=*)", attrs, 0, &res);
    v6 = v5;
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_ab0185983553356c12180ac14bccd298_Traceguids, v5);
      }
      v7 = LdapMapErrorToWin32(v6);
      v4 = v7;
      if ( v7 > 0 )
        v4 = (unsigned __int16)v7 | 0x80070000;
    }
  }
  if ( res )
    ldap_msgfree(res);
  if ( base )
    operator delete(base, v3);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001c50c  mov     r11, rsp
0x18001c50f  mov     [r11+8], rbx
0x18001c513  mov     [r11+10h], rsi
0x18001c517  push    r14
0x18001c519  sub     rsp, 50h
0x18001c51d  mov     rax, rdx
0x18001c520  mov     qword ptr [r11+20h], 0
0x18001c528  mov     rsi, rcx
0x18001c52b  mov     qword ptr [r11+18h], 0
0x18001c533  mov     rcx, rax; unsigned __int16 *
0x18001c536  lea     rdx, [r11+18h]; unsigned __int16 **
0x18001c53a  call    ?_ConstructSchemaBaseString@CUstComputer@@KAJPEAGPEAPEAG@Z; CUstComputer::_ConstructSchemaBaseString(ushort *,ushort * *)
0x18001c53f  mov     ebx, eax
0x18001c541  test    eax, eax
0x18001c543  js      loc_18001C60F
0x18001c549  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c550  lea     r14, WPP_GLOBAL_Control
0x18001c557  cmp     rcx, r14
0x18001c55a  jz      short loc_18001C57C
0x18001c55c  test    byte ptr [rcx+1Ch], 2
0x18001c560  jz      short loc_18001C57C
0x18001c562  mov     r9, [rsp+58h+base]
0x18001c567  lea     r8, WPP_ab0185983553356c12180ac14bccd298_Traceguids
0x18001c56e  mov     rcx, [rcx+10h]
0x18001c572  mov     edx, 1Fh
0x18001c577  call    WPP_SF_S
0x18001c57c  mov     rdx, [rsp+58h+base]; base
0x18001c581  lea     rax, aCn; "cn"
0x18001c588  mov     [rsp+58h+var_18], rax
0x18001c58d  lea     r9, filter; "(objectClass=*)"
0x18001c594  lea     rax, [rsp+58h+arg_18]
0x18001c599  mov     [rsp+58h+var_10], 0
0x18001c5a2  mov     [rsp+58h+res], rax; res
0x18001c5a7  mov     r8d, 2; scope
0x18001c5ad  lea     rax, [rsp+58h+var_18]
0x18001c5b2  mov     [rsp+58h+attrsonly], 0; attrsonly
0x18001c5ba  mov     rcx, rsi; ld
0x18001c5bd  mov     [rsp+58h+attrs], rax; attrs
0x18001c5c2  call    cs:__imp_ldap_search_sW
0x18001c5c8  mov     esi, eax
0x18001c5ca  test    eax, eax
0x18001c5cc  jz      short loc_18001C60F
0x18001c5ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c5d5  cmp     rcx, r14
0x18001c5d8  jz      short loc_18001C5F8
0x18001c5da  test    byte ptr [rcx+1Ch], 1
0x18001c5de  jz      short loc_18001C5F8
0x18001c5e0  mov     rcx, [rcx+10h]
0x18001c5e4  lea     r8, WPP_ab0185983553356c12180ac14bccd298_Traceguids
0x18001c5eb  mov     edx, 20h ; ' '
0x18001c5f0  mov     r9d, eax
0x18001c5f3  call    WPP_SF_d
0x18001c5f8  mov     ecx, esi; LdapError
0x18001c5fa  call    cs:__imp_LdapMapErrorToWin32
0x18001c600  mov     ebx, eax
0x18001c602  test    eax, eax
0x18001c604  jle     short loc_18001C60F
0x18001c606  movzx   ebx, ax
0x18001c609  or      ebx, 80070000h
0x18001c60f  mov     rcx, [rsp+58h+arg_18]; res
0x18001c614  test    rcx, rcx
0x18001c617  jz      short loc_18001C61F
0x18001c619  call    cs:__imp_ldap_msgfree
0x18001c61f  cmp     [rsp+58h+base], 0
0x18001c625  jz      short loc_18001C631
0x18001c627  mov     rcx, [rsp+58h+base]; void *
0x18001c62c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c631  mov     rsi, [rsp+58h+arg_8]
0x18001c636  mov     eax, ebx
0x18001c638  mov     rbx, [rsp+58h+arg_0]
0x18001c63d  add     rsp, 50h
0x18001c641  pop     r14
0x18001c643  retn
```
