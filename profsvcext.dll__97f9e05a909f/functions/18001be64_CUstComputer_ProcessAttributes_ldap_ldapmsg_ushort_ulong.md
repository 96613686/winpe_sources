# CUstComputer::_ProcessAttributes(ldap *,ldapmsg *,ushort * * *,ulong &)

- ea: `0x18001be64`
- end: `0x18001bf3b`
- name: `?_ProcessAttributes@CUstComputer@@KAJPEAUldap@@PEAUldapmsg@@PEAPEAPEAGAEAK@Z`
- size: `215`
- prototype: `__int64 __fastcall(struct ldap *, struct ldapmsg *, unsigned __int16 ***, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001bf44`

## callees

- `0x18001afc8`
- `0x18001be64`
- `0x18001c058`

## import_xrefs

- `WLDAP32!__imp_LdapGetLastError` at `0x18001becb`
- `WLDAP32!__imp_LdapGetLastError` at `0x18001becb`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001bf0a`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001bf0a`
- `WLDAP32!__imp_ldap_first_attributeW` at `0x18001be89`
- `WLDAP32!__imp_ldap_first_attributeW` at `0x18001be89`
- `WLDAP32!__imp_ldap_memfreeW` at `0x18001beac`
- `WLDAP32!__imp_ldap_memfreeW` at `0x18001beac`
- `WLDAP32!__imp_ldap_next_attributeW` at `0x18001bebd`
- `WLDAP32!__imp_ldap_next_attributeW` at `0x18001bebd`
- `WLDAP32!__imp_ber_free` at `0x18001bf26`
- `WLDAP32!__imp_ber_free` at `0x18001bf26`

## pseudocode

```c
__int64 __fastcall CUstComputer::_ProcessAttributes(
        struct ldap *a1,
        struct ldapmsg *a2,
        unsigned __int16 ***a3,
        unsigned int *a4)
{
  unsigned int v5; // ebx
  unsigned __int16 *i; // rax
  WCHAR *v10; // rdi
  ULONG LastError; // edi
  signed int v12; // eax
  BerElement *ptr; // [rsp+30h] [rbp-48h] BYREF

  v5 = 0;
  ptr = 0;
  for ( i = ldap_first_attributeW(a1, a2, &ptr); ; i = ldap_next_attributeW(a1, a2, ptr) )
  {
    v10 = i;
    if ( !i )
      break;
    v5 = CUstComputer::_ProcessValues(a1, i, a2, a3, a4);
    ldap_memfreeW(v10);
  }
  LastError = LdapGetLastError();
  if ( LastError )
  {
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_ab0185983553356c12180ac14bccd298_Traceguids, LastError);
    }
    v12 = LdapMapErrorToWin32(LastError);
    v5 = v12;
    if ( v12 > 0 )
      v5 = (unsigned __int16)v12 | 0x80070000;
  }
  ber_free(ptr, 0);
  return v5;
}

```

## disassembly

```asm
0x18001be64  push    rbx
0x18001be66  push    rbp
0x18001be67  push    rsi
0x18001be68  push    rdi
0x18001be69  push    r14
0x18001be6b  push    r15
0x18001be6d  sub     rsp, 48h
0x18001be71  mov     r15, r8
0x18001be74  xor     ebx, ebx
0x18001be76  lea     r8, [rsp+78h+ptr]; ptr
0x18001be7b  mov     [rsp+78h+ptr], rbx
0x18001be80  mov     r14, r9
0x18001be83  mov     rsi, rdx
0x18001be86  mov     rbp, rcx
0x18001be89  call    cs:__imp_ldap_first_attributeW
0x18001be8f  jmp     short loc_18001BEC3
0x18001be91  mov     r9, r15; unsigned __int16 ***
0x18001be94  mov     [rsp+78h+var_58], r14; unsigned int *
0x18001be99  mov     r8, rsi; struct ldapmsg *
0x18001be9c  mov     rdx, rdi; unsigned __int16 *
0x18001be9f  mov     rcx, rbp; struct ldap *
0x18001bea2  call    ?_ProcessValues@CUstComputer@@KAJPEAUldap@@PEAGPEAUldapmsg@@PEAPEAPEAGAEAK@Z; CUstComputer::_ProcessValues(ldap *,ushort *,ldapmsg *,ushort * * *,ulong &)
0x18001bea7  mov     rcx, rdi; Block
0x18001beaa  mov     ebx, eax
0x18001beac  call    cs:__imp_ldap_memfreeW
0x18001beb2  mov     r8, [rsp+78h+ptr]; ptr
0x18001beb7  mov     rdx, rsi; entry
0x18001beba  mov     rcx, rbp; ld
0x18001bebd  call    cs:__imp_ldap_next_attributeW
0x18001bec3  mov     rdi, rax
0x18001bec6  test    rax, rax
0x18001bec9  jnz     short loc_18001BE91
0x18001becb  call    cs:__imp_LdapGetLastError
0x18001bed1  mov     edi, eax
0x18001bed3  test    eax, eax
0x18001bed5  jz      short loc_18001BF1F
0x18001bed7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bede  lea     rax, WPP_GLOBAL_Control
0x18001bee5  cmp     rcx, rax
0x18001bee8  jz      short loc_18001BF08
0x18001beea  test    byte ptr [rcx+1Ch], 1
0x18001beee  jz      short loc_18001BF08
0x18001bef0  mov     rcx, [rcx+10h]
0x18001bef4  lea     r8, WPP_ab0185983553356c12180ac14bccd298_Traceguids
0x18001befb  mov     edx, 19h
0x18001bf00  mov     r9d, edi
0x18001bf03  call    WPP_SF_d
0x18001bf08  mov     ecx, edi; LdapError
0x18001bf0a  call    cs:__imp_LdapMapErrorToWin32
0x18001bf10  mov     ebx, eax
0x18001bf12  test    eax, eax
0x18001bf14  jle     short loc_18001BF1F
0x18001bf16  movzx   ebx, ax
0x18001bf19  or      ebx, 80070000h
0x18001bf1f  mov     rcx, [rsp+78h+ptr]
0x18001bf24  xor     edx, edx
0x18001bf26  call    cs:__imp_ber_free
0x18001bf2c  mov     eax, ebx
0x18001bf2e  add     rsp, 48h
0x18001bf32  pop     r15
0x18001bf34  pop     r14
0x18001bf36  pop     rdi
0x18001bf37  pop     rsi
0x18001bf38  pop     rbp
0x18001bf39  pop     rbx
0x18001bf3a  retn
```
