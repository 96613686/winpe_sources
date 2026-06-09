# AEGetConfigDN

- ea: `0x180004270`
- end: `0x1800043fe`
- name: `AEGetConfigDN`
- size: `398`
- prototype: `__int64 __fastcall(LDAP *ld, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180003d10`

## callees

- `0x180004270`
- `0x180004630`
- `0x180007d20`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004382`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004382`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180004313`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180004313`
- `WLDAP32!__imp_ldap_first_entry` at `0x180004338`
- `WLDAP32!__imp_ldap_first_entry` at `0x180004338`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800043d3`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800043d3`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000434c`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000434c`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x18000430b`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x18000430b`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800043aa`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800043aa`

## string_xrefs

- `0x1800042bd`: `configurationNamingContext`

## pseudocode

```c
__int64 __fastcall AEGetConfigDN(LDAP *ld, unsigned __int16 **a2)
{
  ULONG v4; // eax
  signed int v5; // eax
  unsigned int v6; // ebx
  LDAPMessage *entry; // rax
  PWCHAR *valuesW; // rax
  unsigned __int16 **v9; // rsi
  PWCHAR v10; // rax
  __int64 v11; // rcx
  unsigned __int64 v13; // rbx
  unsigned __int16 *v14; // rax
  PLDAPMessage res; // [rsp+60h] [rbp-48h] BYREF
  struct l_timeval timeout; // [rsp+68h] [rbp-40h] BYREF
  PWSTR attrs[3]; // [rsp+70h] [rbp-38h] BYREF

  res = 0;
  attrs[2] = 0;
  if ( a2 )
    *a2 = 0;
  attrs[1] = 0;
  timeout = (struct l_timeval)300LL;
  attrs[0] = (PWSTR)L"configurationNamingContext";
  v4 = ldap_search_ext_sW(ld, 0, 0, (const PWSTR)L"objectCategory=*", attrs, 0, 0, 0, &timeout, 0x2710u, &res);
  v5 = LdapMapErrorToWin32(v4);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( !v6 )
  {
    entry = ldap_first_entry(ld, res);
    if ( entry )
    {
      valuesW = ldap_get_valuesW(ld, entry, (const PWSTR)L"configurationNamingContext");
      v9 = valuesW;
      if ( valuesW )
      {
        v10 = *valuesW;
        if ( v10 )
        {
          v11 = -1;
          while ( v10[++v11] != 0 )
            ;
          v13 = v11 + 1;
          v14 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * (v11 + 1));
          *a2 = v14;
          if ( v14 )
            v6 = StringCchCopyW(v14, v13, *v9);
          else
            v6 = -2147024882;
        }
      }
      ldap_value_freeW(v9);
    }
    if ( a2 && !*a2 && v6 != -2147024882 )
      v6 = -2147023545;
    if ( res )
      ldap_msgfree(res);
  }
  return v6;
}

```

## disassembly

```asm
0x180004270  mov     [rsp+arg_10], rbx
0x180004275  push    rbp
0x180004276  push    rsi
0x180004277  push    rdi
0x180004278  sub     rsp, 90h
0x18000427f  mov     rax, cs:__security_cookie
0x180004286  xor     rax, rsp
0x180004289  mov     [rsp+0A8h+var_20], rax
0x180004291  mov     rsi, rcx
0x180004294  mov     rdi, rdx
0x180004297  xor     ecx, ecx
0x180004299  mov     [rsp+0A8h+var_48], rcx
0x18000429e  mov     [rsp+0A8h+var_28], rcx
0x1800042a6  test    rdx, rdx
0x1800042a9  jz      short loc_1800042AE
0x1800042ab  mov     [rdx], rcx
0x1800042ae  lea     rax, [rsp+0A8h+var_48]
0x1800042b3  mov     [rsp+0A8h+var_30], rcx
0x1800042b8  mov     [rsp+0A8h+res], rax; res
0x1800042bd  lea     rbp, aConfigurationn; "configurationNamingContext"
0x1800042c4  mov     [rsp+0A8h+SizeLimit], 2710h; SizeLimit
0x1800042cc  lea     rax, [rsp+0A8h+var_40]
0x1800042d1  mov     [rsp+0A8h+timeout], rax; timeout
0x1800042d6  lea     r9, aObjectcategory_0; "objectCategory=*"
0x1800042dd  mov     [rsp+0A8h+ClientControls], rcx; ClientControls
0x1800042e2  lea     rax, [rsp+0A8h+var_38]
0x1800042e7  mov     [rsp+0A8h+ServerControls], rcx; ServerControls
0x1800042ec  xor     r8d, r8d; scope
0x1800042ef  mov     [rsp+0A8h+attrsonly], ecx; attrsonly
0x1800042f3  xor     edx, edx; base
0x1800042f5  mov     rcx, rsi; ld
0x1800042f8  mov     qword ptr [rsp+0A8h+var_40.tv_sec], 12Ch
0x180004301  mov     [rsp+0A8h+var_38], rbp
0x180004306  mov     [rsp+0A8h+attrs], rax; attrs
0x18000430b  call    cs:__imp_ldap_search_ext_sW
0x180004311  mov     ecx, eax; LdapError
0x180004313  call    cs:__imp_LdapMapErrorToWin32
0x180004319  mov     ebx, eax
0x18000431b  test    eax, eax
0x18000431d  jle     short loc_180004328
0x18000431f  movzx   ebx, ax
0x180004322  or      ebx, 80070000h
0x180004328  test    ebx, ebx
0x18000432a  jnz     loc_1800043D9
0x180004330  mov     rdx, [rsp+0A8h+var_48]; res
0x180004335  mov     rcx, rsi; ld
0x180004338  call    cs:__imp_ldap_first_entry
0x18000433e  test    rax, rax
0x180004341  jz      short loc_1800043B0
0x180004343  mov     r8, rbp; attr
0x180004346  mov     rdx, rax; entry
0x180004349  mov     rcx, rsi; ld
0x18000434c  call    cs:__imp_ldap_get_valuesW
0x180004352  mov     rsi, rax
0x180004355  test    rax, rax
0x180004358  jz      short loc_1800043A7
0x18000435a  mov     rax, [rax]
0x18000435d  test    rax, rax
0x180004360  jz      short loc_1800043A7
0x180004362  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180004369  cmp     word ptr [rax+rcx*2+2], 0
0x18000436f  lea     rcx, [rcx+1]
0x180004373  jnz     short loc_180004369
0x180004375  lea     rbx, [rcx+1]
0x180004379  mov     ecx, 40h ; '@'; uFlags
0x18000437e  lea     rdx, [rbx+rbx]; uBytes
0x180004382  call    cs:__imp_LocalAlloc
0x180004388  mov     [rdi], rax
0x18000438b  test    rax, rax
0x18000438e  jnz     short loc_180004397
0x180004390  mov     ebx, 8007000Eh
0x180004395  jmp     short loc_1800043A7
0x180004397  mov     r8, [rsi]; unsigned __int16 *
0x18000439a  mov     rdx, rbx; unsigned __int64
0x18000439d  mov     rcx, rax; unsigned __int16 *
0x1800043a0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800043a5  mov     ebx, eax
0x1800043a7  mov     rcx, rsi; vals
0x1800043aa  call    cs:__imp_ldap_value_freeW
0x1800043b0  test    rdi, rdi
0x1800043b3  jz      short loc_1800043C9
0x1800043b5  cmp     qword ptr [rdi], 0
0x1800043b9  jnz     short loc_1800043C9
0x1800043bb  cmp     ebx, 8007000Eh
0x1800043c1  mov     eax, 80070547h
0x1800043c6  cmovnz  ebx, eax
0x1800043c9  mov     rcx, [rsp+0A8h+var_48]; res
0x1800043ce  test    rcx, rcx
0x1800043d1  jz      short loc_1800043D9
0x1800043d3  call    cs:__imp_ldap_msgfree
0x1800043d9  mov     eax, ebx
0x1800043db  mov     rcx, [rsp+0A8h+var_20]
0x1800043e3  xor     rcx, rsp; StackCookie
0x1800043e6  call    __security_check_cookie
0x1800043eb  mov     rbx, [rsp+0A8h+arg_10]
0x1800043f3  add     rsp, 90h
0x1800043fa  pop     rdi
0x1800043fb  pop     rsi
0x1800043fc  pop     rbp
0x1800043fd  retn
```
