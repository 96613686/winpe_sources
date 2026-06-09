# CUstComputer::_ProcessEntries(ldap *,ldapmsg *,ushort * * *,ulong &)

- ea: `0x18001bf44`
- end: `0x18001c050`
- name: `?_ProcessEntries@CUstComputer@@KAJPEAUldap@@PEAUldapmsg@@PEAPEAPEAGAEAK@Z`
- size: `268`
- prototype: `__int64 __fastcall(struct ldap *, LDAPMessage *res, unsigned __int16 ***, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001c284`

## callees

- `0x18001afa0`
- `0x18001afc8`
- `0x18001be64`
- `0x18001bf44`

## import_xrefs

- `WLDAP32!__imp_LdapGetLastError` at `0x18001bf7a`
- `WLDAP32!__imp_LdapGetLastError` at `0x18001bf7a`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001bfac`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001bfac`
- `WLDAP32!__imp_ldap_first_entry` at `0x18001bfd6`
- `WLDAP32!__imp_ldap_first_entry` at `0x18001bfd6`
- `WLDAP32!__imp_ldap_next_entry` at `0x18001bfe1`
- `WLDAP32!__imp_ldap_next_entry` at `0x18001bfe1`
- `WLDAP32!__imp_ldap_count_entries` at `0x18001bf65`
- `WLDAP32!__imp_ldap_count_entries` at `0x18001bf65`

## pseudocode

```c
__int64 __fastcall CUstComputer::_ProcessEntries(
        struct ldap *a1,
        LDAPMessage *res,
        unsigned __int16 ***a3,
        unsigned int *a4)
{
  LDAPMessage *v8; // rsi
  signed int v9; // ebx
  ULONG v10; // r14d
  ULONG LastError; // eax
  ULONG v12; // ebx
  signed int v13; // eax
  ULONG v14; // edi
  LDAPMessage *entry; // rax
  __int64 v16; // r9

  v8 = 0;
  v9 = 0;
  v10 = ldap_count_entries(a1, res);
  if ( v10 == -1 )
  {
    LastError = LdapGetLastError();
    v12 = LastError;
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_ab0185983553356c12180ac14bccd298_Traceguids, LastError);
    }
    v13 = LdapMapErrorToWin32(v12);
    v9 = v13;
    if ( v13 > 0 )
      v9 = (unsigned __int16)v13 | 0x80070000;
  }
  v14 = 0;
  if ( v9 >= 0 )
  {
    while ( v14 < v10 )
    {
      if ( v14 )
        entry = ldap_next_entry(a1, v8);
      else
        entry = ldap_first_entry(a1, res);
      v8 = entry;
      if ( !entry )
      {
        if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_ab0185983553356c12180ac14bccd298_Traceguids, v16);
        }
        return (unsigned int)-2147418113;
      }
      ++v14;
      v9 = CUstComputer::_ProcessAttributes(a1, entry, a3, a4);
      if ( v9 < 0 )
        return (unsigned int)v9;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001bf44  push    rbx
0x18001bf46  push    rbp
0x18001bf47  push    rsi
0x18001bf48  push    rdi
0x18001bf49  push    r12
0x18001bf4b  push    r13
0x18001bf4d  push    r14
0x18001bf4f  push    r15
0x18001bf51  sub     rsp, 28h
0x18001bf55  mov     r12, r9
0x18001bf58  mov     r13, r8
0x18001bf5b  mov     r15, rdx
0x18001bf5e  mov     rbp, rcx
0x18001bf61  xor     esi, esi
0x18001bf63  xor     ebx, ebx
0x18001bf65  call    cs:__imp_ldap_count_entries
0x18001bf6b  lea     rdi, WPP_GLOBAL_Control
0x18001bf72  mov     r14d, eax
0x18001bf75  cmp     eax, 0FFFFFFFFh
0x18001bf78  jnz     short loc_18001BFC1
0x18001bf7a  call    cs:__imp_LdapGetLastError
0x18001bf80  mov     ebx, eax
0x18001bf82  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf89  cmp     rcx, rdi
0x18001bf8c  jz      short loc_18001BFAA
0x18001bf8e  test    byte ptr [rcx+1Ch], 1
0x18001bf92  jz      short loc_18001BFAA
0x18001bf94  mov     rcx, [rcx+10h]
0x18001bf98  lea     edx, [rsi+11h]
0x18001bf9b  mov     r9d, eax
0x18001bf9e  lea     r8, WPP_ab0185983553356c12180ac14bccd298_Traceguids
0x18001bfa5  call    WPP_SF_d
0x18001bfaa  mov     ecx, ebx; LdapError
0x18001bfac  call    cs:__imp_LdapMapErrorToWin32
0x18001bfb2  mov     ebx, eax
0x18001bfb4  test    eax, eax
0x18001bfb6  jle     short loc_18001BFC1
0x18001bfb8  movzx   ebx, ax
0x18001bfbb  or      ebx, 80070000h
0x18001bfc1  xor     edi, edi
0x18001bfc3  test    ebx, ebx
0x18001bfc5  js      short loc_18001C03D
0x18001bfc7  cmp     edi, r14d
0x18001bfca  jnb     short loc_18001C03D
0x18001bfcc  mov     rcx, rbp; ld
0x18001bfcf  test    edi, edi
0x18001bfd1  jnz     short loc_18001BFDE
0x18001bfd3  mov     rdx, r15; res
0x18001bfd6  call    cs:__imp_ldap_first_entry
0x18001bfdc  jmp     short loc_18001BFE7
0x18001bfde  mov     rdx, rsi; entry
0x18001bfe1  call    cs:__imp_ldap_next_entry
0x18001bfe7  mov     rsi, rax
0x18001bfea  test    rax, rax
0x18001bfed  jz      short loc_18001C00A
0x18001bfef  mov     r9, r12; unsigned int *
0x18001bff2  mov     r8, r13; unsigned __int16 ***
0x18001bff5  mov     rdx, rax; struct ldapmsg *
0x18001bff8  mov     rcx, rbp; struct ldap *
0x18001bffb  call    ?_ProcessAttributes@CUstComputer@@KAJPEAUldap@@PEAUldapmsg@@PEAPEAPEAGAEAK@Z; CUstComputer::_ProcessAttributes(ldap *,ldapmsg *,ushort * * *,ulong &)
0x18001c000  inc     edi
0x18001c002  mov     ebx, eax
0x18001c004  test    eax, eax
0x18001c006  jns     short loc_18001BFC7
0x18001c008  jmp     short loc_18001C03D
0x18001c00a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c011  lea     rax, WPP_GLOBAL_Control
0x18001c018  cmp     rcx, rax
0x18001c01b  jz      short loc_18001C038
0x18001c01d  test    byte ptr [rcx+1Ch], 1
0x18001c021  jz      short loc_18001C038
0x18001c023  mov     rcx, [rcx+10h]
0x18001c027  lea     r8, WPP_ab0185983553356c12180ac14bccd298_Traceguids
0x18001c02e  mov     edx, 12h
0x18001c033  call    WPP_SF_
0x18001c038  mov     ebx, 8000FFFFh
0x18001c03d  mov     eax, ebx
0x18001c03f  add     rsp, 28h
0x18001c043  pop     r15
0x18001c045  pop     r14
0x18001c047  pop     r13
0x18001c049  pop     r12
0x18001c04b  pop     rdi
0x18001c04c  pop     rsi
0x18001c04d  pop     rbp
0x18001c04e  pop     rbx
0x18001c04f  retn
```
