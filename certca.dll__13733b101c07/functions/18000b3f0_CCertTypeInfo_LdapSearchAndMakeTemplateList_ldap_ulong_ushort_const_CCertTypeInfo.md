# CCertTypeInfo::_LdapSearchAndMakeTemplateList(ldap *,ulong,ushort const *,CCertTypeInfo * *)

- ea: `0x18000b3f0`
- end: `0x18000b7f6`
- name: `?_LdapSearchAndMakeTemplateList@CCertTypeInfo@@KAJPEAUldap@@KPEBGPEAPEAV1@@Z`
- size: `1030`
- prototype: `__int64 __fastcall(LDAP *ld, char, WCHAR *, struct CCertTypeInfo **)`
- caller_count: `3`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a630`
- `0x18000a920`
- `0x180032724`

## callees

- `0x180008400`
- `0x18000b3f0`
- `0x18000c160`
- `0x18000e500`
- `0x18000fb00`
- `0x180011600`
- `0x180012450`
- `0x180014fac`
- `0x18002a470`
- `0x18002cddc`
- `0x18002fa14`
- `0x18002fa3c`
- `0x1800382c0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b517`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b552`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b7ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b517`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b552`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b7ab`
- `WLDAP32!__imp_ldap_first_entry` at `0x18000b61f`
- `WLDAP32!__imp_ldap_first_entry` at `0x18000b61f`
- `WLDAP32!__imp_ldap_next_entry` at `0x18000b774`
- `WLDAP32!__imp_ldap_next_entry` at `0x18000b774`
- `WLDAP32!__imp_ldap_count_entries` at `0x18000b5ff`
- `WLDAP32!__imp_ldap_count_entries` at `0x18000b5ff`
- `WLDAP32!__imp_ldap_msgfree` at `0x18000b7c7`
- `WLDAP32!__imp_ldap_msgfree` at `0x18000b7c7`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x18000b5c2`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x18000b5c2`

## string_xrefs

- `0x18000b5af`: `(objectCategory=pKICertificateTemplate)`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::_LdapSearchAndMakeTemplateList(
        LDAP *ld,
        char a2,
        WCHAR *a3,
        struct CCertTypeInfo **a4)
{
  unsigned int v8; // ebx
  CCertTypeInfo *v9; // rdi
  AUTHZ_CLIENT_CONTEXT_HANDLE v10; // rsi
  int v11; // eax
  unsigned int v12; // ecx
  int v13; // edx
  unsigned int v14; // ecx
  unsigned int v15; // edx
  ULONG v16; // eax
  unsigned int v17; // r9d
  LDAPMessage *i; // rax
  struct ldapmsg *v19; // rdi
  CCertTypeInfo *v20; // rax
  CCertTypeInfo *v21; // rbx
  unsigned int v22; // edx
  unsigned __int16 **attrs; // [rsp+20h] [rbp-A9h]
  HANDLE hObject; // [rsp+60h] [rbp-69h] BYREF
  WINBOOL IsMember; // [rsp+68h] [rbp-61h] BYREF
  PLDAPMessage res; // [rsp+70h] [rbp-59h] BYREF
  l_timeval timeout; // [rsp+78h] [rbp-51h] BYREF
  struct CCertTypeInfo *v29; // [rsp+80h] [rbp-49h] BYREF
  _QWORD v30[3]; // [rsp+88h] [rbp-41h] BYREF
  char v31; // [rsp+A0h] [rbp-29h]
  int v32; // [rsp+A1h] [rbp-28h]
  __int16 v33; // [rsp+A5h] [rbp-24h]
  char v34; // [rsp+A7h] [rbp-22h]
  _QWORD v35[3]; // [rsp+A8h] [rbp-21h] BYREF
  char v36; // [rsp+C0h] [rbp-9h]
  int v37; // [rsp+C1h] [rbp-8h]
  __int16 v38; // [rsp+C5h] [rbp-4h]
  char v39; // [rsp+C7h] [rbp-2h]
  PLDAPControlW ServerControls[3]; // [rsp+C8h] [rbp-1h] BYREF
  int v41; // [rsp+E0h] [rbp+17h] BYREF
  char v42; // [rsp+E4h] [rbp+1Bh]

  v41 = 16909104;
  v42 = 7;
  v30[0] = L"1.2.840.113556.1.4.801";
  v30[1] = 5;
  v30[2] = &v41;
  v31 = 1;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35[0] = L"1.2.840.113556.1.4.1413";
  v8 = 0;
  v35[1] = 0;
  v35[2] = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  ServerControls[0] = (PLDAPControlW)v30;
  ServerControls[1] = (PLDAPControlW)v35;
  ServerControls[2] = 0;
  res = 0;
  timeout = 0;
  v9 = 0;
  v29 = 0;
  if ( !a4 )
  {
    v8 = -2147467261;
    CSPrintErrorLineFile(0x9AD0328u, -2147467261);
    goto LABEL_48;
  }
  v10 = 0;
  *a4 = 0;
  IsMember = 0;
  hObject = 0;
  if ( !CertTypeRetrieveClientToken(&hObject) )
  {
    v11 = myHLastError();
    v12 = 73270054;
LABEL_5:
    v8 = v11;
    CSPrintErrorLineFile(v12, v11);
    goto LABEL_14;
  }
  if ( !(unsigned int)myIsLocalSystem(hObject, &IsMember) )
  {
    v11 = myHLastError();
    v12 = 73728806;
    goto LABEL_5;
  }
  if ( IsMember )
  {
    if ( hObject )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    if ( !(unsigned int)myNetLogonUser(0, 0, 0, &hObject) )
    {
      v11 = myHLastError();
      v12 = 74646310;
      goto LABEL_5;
    }
  }
  v10 = (AUTHZ_CLIENT_CONTEXT_HANDLE)hObject;
  hObject = 0;
LABEL_14:
  if ( hObject )
    CloseHandle(hObject);
  if ( v8 )
  {
    v13 = v8;
    v14 = 162726696;
  }
  else
  {
    timeout = (l_timeval)120LL;
    v16 = ldap_search_ext_sW(
            ld,
            a3,
            2u,
            (const PWSTR)L"(objectCategory=pKICertificateTemplate)",
            &g_awszCTAttrs,
            0,
            ServerControls,
            0,
            &timeout,
            0x2710u,
            &res);
    if ( v16 == 32 )
    {
      v8 = 0;
      v13 = 0;
      v14 = 164234024;
    }
    else if ( v16 )
    {
      v8 = myHLdapError3(ld, v16, 0, v17, attrs);
      v13 = v8;
      v14 = 164561704;
    }
    else
    {
      if ( ldap_count_entries(ld, res) )
      {
        for ( i = ldap_first_entry(ld, res); ; i = ldap_next_entry(ld, v19) )
        {
          v19 = i;
          if ( !i )
            break;
          v20 = (CCertTypeInfo *)operator new(0xC0u, (const struct std::nothrow_t *)&std::nothrow);
          v21 = v20;
          hObject = v20;
          if ( v20 )
          {
            *(_DWORD *)v20 = 1;
            *((_QWORD *)v20 + 19) = 0;
            *((_QWORD *)v20 + 20) = 0;
            *((_DWORD *)v20 + 14) = 0;
            *((_QWORD *)v20 + 12) = 0;
            *((_QWORD *)v20 + 2) = 0;
            *((_DWORD *)v20 + 6) = 0;
            *((_QWORD *)v20 + 5) = 0;
            *((_DWORD *)v20 + 8) = 0;
            *((_QWORD *)v20 + 8) = 0;
            *((_QWORD *)v20 + 9) = 0;
            *((_QWORD *)v20 + 10) = 0;
            *((_DWORD *)v20 + 22) = 0;
            *((_QWORD *)v20 + 1) = 0;
            *((_QWORD *)v20 + 17) = 0;
            *((_QWORD *)v20 + 15) = 1;
            *((_DWORD *)v20 + 36) = 0;
            *((_DWORD *)v20 + 32) = 0;
            *((_QWORD *)v20 + 13) = 315360000000000LL;
            *((_QWORD *)v20 + 14) = 12096000000000LL;
            *((_QWORD *)v20 + 21) = 1;
            *((_QWORD *)v20 + 22) = 1;
            *((_QWORD *)v20 + 23) = 0;
          }
          else
          {
            v21 = 0;
          }
          if ( !v21 )
          {
            v8 = -2147024882;
            CSPrintErrorLineFile(0x9E20328u, -2147024882);
            v9 = v29;
            goto LABEL_44;
          }
          if ( CCertTypeInfo::_LoadFromDSEntry(v21, ld, v19) || *((_DWORD *)v21 + 22) > 4u )
          {
            CCertTypeInfo::`scalar deleting destructor'(v21, v22);
          }
          else
          {
            if ( (a2 & 0x20) != 0 )
              *((_DWORD *)v21 + 31) = 1;
            *((_DWORD *)v21 + 44) = 1;
            if ( !(unsigned int)CCertTypeInfo::AccessCheck((PSECURITY_DESCRIPTOR *)v21, v10, 1, 0) )
              *((_DWORD *)v21 + 44) |= 2u;
            if ( !(unsigned int)CCertTypeInfo::AccessCheck((PSECURITY_DESCRIPTOR *)v21, v10, 2, 0) )
              *((_DWORD *)v21 + 44) |= 4u;
            CCertTypeInfo::_Append(&v29, v21);
          }
        }
        *a4 = v29;
        v9 = 0;
        v8 = 0;
        goto LABEL_44;
      }
      v8 = 0;
      v13 = 0;
      v14 = 165020456;
    }
  }
  CSPrintErrorLineFile(v14, v13);
LABEL_44:
  if ( v10 )
    CloseHandle(v10);
  if ( v9 )
    CCertTypeInfo::`scalar deleting destructor'(v9, v15);
LABEL_48:
  if ( res )
    ldap_msgfree(res);
  return v8;
}

```

## disassembly

```asm
0x18000b3f0  mov     [rsp-8+arg_8], rbx
0x18000b3f5  push    rbp
0x18000b3f6  push    rsi
0x18000b3f7  push    rdi
0x18000b3f8  push    r12
0x18000b3fa  push    r13
0x18000b3fc  push    r14
0x18000b3fe  push    r15
0x18000b400  lea     rbp, [rsp-27h]
0x18000b405  sub     rsp, 0F0h
0x18000b40c  mov     rax, cs:__security_cookie
0x18000b413  xor     rax, rsp
0x18000b416  mov     [rbp+57h+var_38], rax
0x18000b41a  mov     r15, r9
0x18000b41d  mov     r12, r8
0x18000b420  mov     r13d, edx
0x18000b423  mov     r14, rcx
0x18000b426  mov     [rbp+57h+var_40], 1020330h
0x18000b42d  mov     [rbp+57h+var_3C], 7
0x18000b431  lea     rax, a12840113556148; "1.2.840.113556.1.4.801"
0x18000b438  mov     [rbp+57h+var_98], rax
0x18000b43c  mov     [rbp+57h+var_90], 5
0x18000b444  lea     rax, [rbp+57h+var_40]
0x18000b448  mov     [rbp+57h+var_88], rax
0x18000b44c  mov     [rbp+57h+var_80], 1
0x18000b450  xor     eax, eax
0x18000b452  mov     [rbp+57h+var_7F], eax
0x18000b455  mov     [rbp+57h+var_7B], ax
0x18000b459  mov     [rbp+57h+var_79], al
0x18000b45c  lea     rax, a12840113556141; "1.2.840.113556.1.4.1413"
0x18000b463  mov     [rbp+57h+var_78], rax
0x18000b467  xor     ebx, ebx
0x18000b469  mov     [rbp+57h+var_70], rbx
0x18000b46d  mov     [rbp+57h+var_68], rbx
0x18000b471  mov     [rbp+57h+var_60], bl
0x18000b474  xor     eax, eax
0x18000b476  mov     [rbp+57h+var_5F], eax
0x18000b479  mov     [rbp+57h+var_5B], ax
0x18000b47d  mov     [rbp+57h+var_59], al
0x18000b480  lea     rax, [rbp+57h+var_98]
0x18000b484  mov     [rbp+57h+var_58], rax
0x18000b488  lea     rax, [rbp+57h+var_78]
0x18000b48c  mov     [rbp+57h+var_50], rax
0x18000b490  mov     [rbp+57h+var_48], rbx
0x18000b494  mov     [rbp+57h+var_B0], rbx
0x18000b498  mov     qword ptr [rbp+57h+var_A8.tv_sec], rbx
0x18000b49c  mov     edi, ebx
0x18000b49e  mov     [rbp+57h+var_A0], rbx
0x18000b4a2  test    r9, r9
0x18000b4a5  jnz     short loc_18000B4BD
0x18000b4a7  mov     ebx, 80004003h
0x18000b4ac  mov     edx, ebx; int
0x18000b4ae  mov     ecx, 9AD0328h; unsigned int
0x18000b4b3  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000b4b8  jmp     loc_18000B7BE
0x18000b4bd  mov     rsi, rbx
0x18000b4c0  mov     [r9], rbx
0x18000b4c3  mov     [rbp+57h+IsMember], ebx
0x18000b4c6  mov     [rbp+57h+hObject], rbx
0x18000b4ca  lea     rcx, [rbp+57h+hObject]; void **
0x18000b4ce  call    ?CertTypeRetrieveClientToken@@YAHPEAPEAX@Z; CertTypeRetrieveClientToken(void * *)
0x18000b4d3  test    eax, eax
0x18000b4d5  jnz     short loc_18000B4EC
0x18000b4d7  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18000b4dc  mov     ecx, 45E0326h; unsigned int
0x18000b4e1  mov     ebx, eax
0x18000b4e3  mov     edx, eax; int
0x18000b4e5  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000b4ea  jmp     short loc_18000B549
0x18000b4ec  lea     rdx, [rbp+57h+IsMember]; IsMember
0x18000b4f0  mov     rcx, [rbp+57h+hObject]; TokenHandle
0x18000b4f4  call    ?myIsLocalSystem@@YAHPEAXPEAH@Z; myIsLocalSystem(void *,int *)
0x18000b4f9  test    eax, eax
0x18000b4fb  jnz     short loc_18000B509
0x18000b4fd  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18000b502  mov     ecx, 4650326h
0x18000b507  jmp     short loc_18000B4E1
0x18000b509  cmp     [rbp+57h+IsMember], ebx
0x18000b50c  jz      short loc_18000B541
0x18000b50e  mov     rcx, [rbp+57h+hObject]; hObject
0x18000b512  test    rcx, rcx
0x18000b515  jz      short loc_18000B521
0x18000b517  call    cs:__imp_CloseHandle
0x18000b51d  mov     [rbp+57h+hObject], rbx
0x18000b521  lea     r9, [rbp+57h+hObject]
0x18000b525  xor     r8d, r8d; LPCWSTR
0x18000b528  xor     edx, edx; LPCWSTR
0x18000b52a  xor     ecx, ecx; lpString
0x18000b52c  call    myNetLogonUser
0x18000b531  test    eax, eax
0x18000b533  jnz     short loc_18000B541
0x18000b535  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18000b53a  mov     ecx, 4730326h
0x18000b53f  jmp     short loc_18000B4E1
0x18000b541  mov     rsi, [rbp+57h+hObject]
0x18000b545  mov     [rbp+57h+hObject], rbx
0x18000b549  mov     rcx, [rbp+57h+hObject]; hObject
0x18000b54d  test    rcx, rcx
0x18000b550  jz      short loc_18000B558
0x18000b552  call    cs:__imp_CloseHandle
0x18000b558  xor     ecx, ecx
0x18000b55a  test    ebx, ebx
0x18000b55c  jz      short loc_18000B56F
0x18000b55e  mov     edx, ebx; int
0x18000b560  mov     ecx, 9B30328h; unsigned int
0x18000b565  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000b56a  jmp     loc_18000B7A3
0x18000b56f  mov     qword ptr [rbp+57h+var_A8.tv_sec], 78h ; 'x'
0x18000b577  lea     rax, [rbp+57h+var_B0]
0x18000b57b  mov     [rsp+120h+res], rax; res
0x18000b580  mov     [rsp+120h+SizeLimit], 2710h; SizeLimit
0x18000b588  lea     rax, [rbp+57h+var_A8]
0x18000b58c  mov     [rsp+120h+timeout], rax; timeout
0x18000b591  mov     [rsp+120h+ClientControls], rcx; ClientControls
0x18000b596  lea     rax, [rbp+57h+var_58]
0x18000b59a  mov     [rsp+120h+ServerControls], rax; ServerControls
0x18000b59f  mov     [rsp+120h+attrsonly], ecx; attrsonly
0x18000b5a3  lea     rax, ?g_awszCTAttrs@@3PAPEAGA; ushort * near * g_awszCTAttrs
0x18000b5aa  mov     [rsp+120h+attrs], rax; unsigned __int16 **
0x18000b5af  lea     r9, filter; "(objectCategory=pKICertificateTemplate)"
0x18000b5b6  mov     r8d, 2; scope
0x18000b5bc  mov     rdx, r12; base
0x18000b5bf  mov     rcx, r14; ld
0x18000b5c2  call    cs:__imp_ldap_search_ext_sW
0x18000b5c8  xor     r12d, r12d
0x18000b5cb  cmp     eax, 20h ; ' '
0x18000b5ce  jnz     short loc_18000B5DC
0x18000b5d0  mov     ebx, r12d
0x18000b5d3  xor     edx, edx
0x18000b5d5  mov     ecx, 9CA0328h
0x18000b5da  jmp     short loc_18000B565
0x18000b5dc  mov     rcx, r14; ld
0x18000b5df  test    eax, eax
0x18000b5e1  jz      short loc_18000B5FB
0x18000b5e3  xor     r8d, r8d; unsigned int
0x18000b5e6  mov     edx, eax; unsigned int
0x18000b5e8  call    ?myHLdapError3@@YAJPEAUldap@@KKKPEAPEAG@Z; myHLdapError3(ldap *,ulong,ulong,ulong,ushort * *)
0x18000b5ed  mov     ebx, eax
0x18000b5ef  mov     edx, eax
0x18000b5f1  mov     ecx, 9CF0328h
0x18000b5f6  jmp     loc_18000B565
0x18000b5fb  mov     rdx, [rbp+57h+var_B0]; res
0x18000b5ff  call    cs:__imp_ldap_count_entries
0x18000b605  test    eax, eax
0x18000b607  jnz     short loc_18000B618
0x18000b609  mov     ebx, r12d
0x18000b60c  xor     edx, edx
0x18000b60e  mov     ecx, 9D60328h
0x18000b613  jmp     loc_18000B565
0x18000b618  mov     rdx, [rbp+57h+var_B0]; res
0x18000b61c  mov     rcx, r14; ld
0x18000b61f  call    cs:__imp_ldap_first_entry
0x18000b625  mov     rdi, rax
0x18000b628  test    rax, rax
0x18000b62b  jz      loc_18000B796
0x18000b631  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b638  mov     ecx, 0C0h; unsigned __int64
0x18000b63d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b642  mov     rbx, rax
0x18000b645  mov     [rbp+57h+hObject], rax
0x18000b649  test    rax, rax
0x18000b64c  jz      loc_18000B6DF
0x18000b652  mov     ecx, 1
0x18000b657  mov     [rax], ecx
0x18000b659  mov     [rax+98h], r12
0x18000b660  mov     [rax+0A0h], r12
0x18000b667  mov     [rax+38h], r12d
0x18000b66b  mov     [rax+60h], r12
0x18000b66f  mov     [rax+10h], r12
0x18000b673  mov     [rax+18h], r12d
0x18000b677  mov     [rax+28h], r12
0x18000b67b  mov     [rax+20h], r12d
0x18000b67f  mov     [rax+40h], r12
0x18000b683  mov     [rax+48h], r12
0x18000b687  mov     [rax+50h], r12
0x18000b68b  mov     [rax+58h], r12d
0x18000b68f  mov     [rax+8], r12
0x18000b693  mov     [rax+88h], r12
0x18000b69a  mov     [rax+78h], rcx
0x18000b69e  mov     [rax+90h], r12d
0x18000b6a5  mov     [rax+80h], r12d
0x18000b6ac  mov     rax, 11ED178C6C000h
0x18000b6b6  mov     [rbx+68h], rax
0x18000b6ba  mov     rax, 0B0051C88000h
0x18000b6c4  mov     [rbx+70h], rax
0x18000b6c8  mov     [rbx+0A8h], rcx
0x18000b6cf  mov     [rbx+0B0h], rcx
0x18000b6d6  mov     [rbx+0B8h], r12
0x18000b6dd  jmp     short loc_18000B6E2
0x18000b6df  mov     rbx, r12
0x18000b6e2  test    rbx, rbx
0x18000b6e5  jz      loc_18000B77F
0x18000b6eb  mov     r8, rdi; struct ldapmsg *
0x18000b6ee  mov     rdx, r14; struct ldap *
0x18000b6f1  mov     rcx, rbx; this
0x18000b6f4  call    ?_LoadFromDSEntry@CCertTypeInfo@@IEAAJPEAUldap@@PEAUldapmsg@@@Z; CCertTypeInfo::_LoadFromDSEntry(ldap *,ldapmsg *)
0x18000b6f9  test    eax, eax
0x18000b6fb  jnz     short loc_18000B766
0x18000b6fd  cmp     dword ptr [rbx+58h], 4
0x18000b701  ja      short loc_18000B766
0x18000b703  test    r13b, 20h
0x18000b707  jz      short loc_18000B710
0x18000b709  mov     dword ptr [rbx+7Ch], 1
0x18000b710  mov     dword ptr [rbx+0B0h], 1
0x18000b71a  xor     r9d, r9d; int
0x18000b71d  mov     r8d, 10001h; unsigned int
0x18000b723  mov     rdx, rsi; void *
0x18000b726  mov     rcx, rbx; this
0x18000b729  call    ?AccessCheck@CCertTypeInfo@@QEAAJPEAXKH@Z; CCertTypeInfo::AccessCheck(void *,ulong,int)
0x18000b72e  test    eax, eax
0x18000b730  jnz     short loc_18000B739
0x18000b732  or      dword ptr [rbx+0B0h], 2
0x18000b739  xor     r9d, r9d; int
0x18000b73c  mov     r8d, 10002h; unsigned int
0x18000b742  mov     rdx, rsi; void *
0x18000b745  mov     rcx, rbx; this
0x18000b748  call    ?AccessCheck@CCertTypeInfo@@QEAAJPEAXKH@Z; CCertTypeInfo::AccessCheck(void *,ulong,int)
0x18000b74d  test    eax, eax
0x18000b74f  jnz     short loc_18000B758
0x18000b751  or      dword ptr [rbx+0B0h], 4
0x18000b758  mov     rdx, rbx; struct CCertTypeInfo *
0x18000b75b  lea     rcx, [rbp+57h+var_A0]; struct CCertTypeInfo **
0x18000b75f  call    ?_Append@CCertTypeInfo@@SAPEAV1@PEAPEAV1@PEAV1@@Z; CCertTypeInfo::_Append(CCertTypeInfo * *,CCertTypeInfo *)
0x18000b764  jmp     short loc_18000B76E
0x18000b766  mov     rcx, rbx; this
0x18000b769  call    ??_GCCertTypeInfo@@QEAAPEAXI@Z; CCertTypeInfo::`scalar deleting destructor'(uint)
0x18000b76e  mov     rdx, rdi; entry
0x18000b771  mov     rcx, r14; ld
0x18000b774  call    cs:__imp_ldap_next_entry
0x18000b77a  jmp     loc_18000B625
0x18000b77f  mov     ebx, 8007000Eh
0x18000b784  mov     edx, ebx; int
0x18000b786  mov     ecx, 9E20328h; unsigned int
0x18000b78b  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000b790  mov     rdi, [rbp+57h+var_A0]
0x18000b794  jmp     short loc_18000B7A3
0x18000b796  mov     rax, [rbp+57h+var_A0]
0x18000b79a  mov     [r15], rax
0x18000b79d  mov     rdi, r12
0x18000b7a0  mov     ebx, r12d
0x18000b7a3  test    rsi, rsi
0x18000b7a6  jz      short loc_18000B7B1
0x18000b7a8  mov     rcx, rsi; hObject
0x18000b7ab  call    cs:__imp_CloseHandle
0x18000b7b1  test    rdi, rdi
0x18000b7b4  jz      short loc_18000B7BE
0x18000b7b6  mov     rcx, rdi; this
0x18000b7b9  call    ??_GCCertTypeInfo@@QEAAPEAXI@Z; CCertTypeInfo::`scalar deleting destructor'(uint)
0x18000b7be  mov     rcx, [rbp+57h+var_B0]; res
0x18000b7c2  test    rcx, rcx
0x18000b7c5  jz      short loc_18000B7CD
0x18000b7c7  call    cs:__imp_ldap_msgfree
0x18000b7cd  mov     eax, ebx
0x18000b7cf  mov     rcx, [rbp+57h+var_38]
0x18000b7d3  xor     rcx, rsp; StackCookie
0x18000b7d6  call    __security_check_cookie
0x18000b7db  mov     rbx, [rsp+120h+arg_8]
0x18000b7e3  add     rsp, 0F0h
0x18000b7ea  pop     r15
0x18000b7ec  pop     r14
0x18000b7ee  pop     r13
0x18000b7f0  pop     r12
0x18000b7f2  pop     rdi
0x18000b7f3  pop     rsi
0x18000b7f4  pop     rbp
0x18000b7f5  retn
```
