# I_CAOIDGetProperty(ushort const *,ulong,void *,ldap *)

- ea: `0x18002c24c`
- end: `0x18002c69e`
- name: `?I_CAOIDGetProperty@@YAJPEBGKPEAXPEAUldap@@@Z`
- size: `1106`
- prototype: `__int64 __fastcall(unsigned __int16 *, int, unsigned __int16 **, struct ldap *)`
- caller_count: `2`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x180001bf0`
- `0x18002cd30`

## callees

- `0x180005944`
- `0x180005f00`
- `0x180008400`
- `0x180008420`
- `0x180008610`
- `0x18000e130`
- `0x18000e52c`
- `0x180011600`
- `0x180012680`
- `0x18002a5d0`
- `0x18002bb4c`
- `0x18002c24c`
- `0x18002c830`
- `0x1800382c0`

## import_xrefs

- `msvcrt!_wtol` at `0x18002c548`
- `msvcrt!_wtol` at `0x18002c548`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c62a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c647`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c62a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c647`
- `WLDAP32!__imp_ldap_unbind` at `0x18002c66f`
- `WLDAP32!__imp_ldap_unbind` at `0x18002c66f`
- `WLDAP32!__imp_ldap_first_entry` at `0x18002c4ef`
- `WLDAP32!__imp_ldap_first_entry` at `0x18002c4ef`
- `WLDAP32!__imp_ldap_count_entries` at `0x18002c4d9`
- `WLDAP32!__imp_ldap_count_entries` at `0x18002c4d9`
- `WLDAP32!__imp_ldap_msgfree` at `0x18002c639`
- `WLDAP32!__imp_ldap_msgfree` at `0x18002c639`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18002c532`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18002c571`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18002c532`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18002c571`
- `WLDAP32!__imp_ldap_search_stW` at `0x18002c49f`
- `WLDAP32!__imp_ldap_search_stW` at `0x18002c49f`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18002c5ee`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18002c5ee`

## string_xrefs

- `0x18002c420`: `msPKI-Cert-Template-OID`
- `0x18002c3f1`: `CN=OID,CN=Public Key Services,CN=Services,`

## pseudocode

```c
__int64 __fastcall I_CAOIDGetProperty(unsigned __int16 *a1, int a2, unsigned __int16 **a3, struct ldap *a4)
{
  struct ldap *v5; // rdi
  LDAP *v6; // r13
  unsigned __int16 *v7; // r15
  unsigned __int16 *v8; // r14
  unsigned __int16 *v9; // r12
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // eax
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rcx
  unsigned __int64 v16; // rbx
  unsigned int v17; // ecx
  unsigned __int16 *v18; // rax
  int v19; // eax
  int v20; // edx
  ULONG v21; // eax
  unsigned int v22; // r9d
  unsigned int v23; // r9d
  LDAPMessage *entry; // rax
  int v25; // esi
  int v26; // esi
  PWCHAR *v27; // rsi
  unsigned __int16 *v28; // rax
  const wchar_t **valuesW; // rax
  unsigned int v30; // r9d
  int v31; // eax
  WCHAR *v32; // r8
  PWCHAR *v33; // rax
  unsigned int v34; // eax
  unsigned __int16 **attrs; // [rsp+20h] [rbp-69h]
  unsigned __int16 *v37; // [rsp+40h] [rbp-49h] BYREF
  unsigned __int16 *v38; // [rsp+48h] [rbp-41h] BYREF
  PWSTR filter; // [rsp+50h] [rbp-39h] BYREF
  PLDAPMessage res; // [rsp+58h] [rbp-31h] BYREF
  LDAP *ld; // [rsp+60h] [rbp-29h] BYREF
  struct l_timeval timeout; // [rsp+68h] [rbp-21h] BYREF
  unsigned __int16 **v43; // [rsp+70h] [rbp-19h]
  unsigned __int16 *v44; // [rsp+78h] [rbp-11h]
  PWSTR v45[2]; // [rsp+80h] [rbp-9h] BYREF
  __int128 v46; // [rsp+90h] [rbp+7h]

  v44 = a1;
  v43 = a3;
  timeout = 0;
  v5 = a4;
  filter = 0;
  v6 = 0;
  res = 0;
  v7 = 0;
  ld = 0;
  v8 = 0;
  v38 = 0;
  v9 = 0;
  v37 = 0;
  *(_OWORD *)v45 = 0;
  v46 = 0;
  if ( !a1 || !a3 )
  {
    v11 = -2147024809;
    v17 = 119079734;
    goto LABEL_45;
  }
  if ( !a4 )
  {
    v10 = myTimeOutRobustLdapBind(&ld);
    v11 = v10;
    if ( v10 )
    {
      CSPrintErrorLineFile(0x9E0336u, v10);
      CSPrintErrorLineFile(0x71D0336u, v11);
      v6 = ld;
      goto LABEL_47;
    }
    v6 = ld;
    v5 = ld;
  }
  v12 = CAGetAuthoritativeDomainDn(v5, 0, &v38);
  v11 = v12;
  if ( v12 )
  {
    CSPrintErrorLineFile(0x7220336u, v12);
    v7 = v38;
    goto LABEL_47;
  }
  v13 = myOIDHashOIDToString(v44, &v37);
  v11 = v13;
  if ( v13 )
  {
    CSPrintErrorLineFile(0x7270336u, v13);
    v7 = v38;
    v9 = v37;
    goto LABEL_47;
  }
  v7 = v38;
  v14 = -1;
  v15 = -1;
  do
    ++v15;
  while ( v38[v15] );
  v9 = v37;
  do
    ++v14;
  while ( v37[v14] );
  v16 = v14 + v15 + 47;
  if ( v16 > 0x10000 )
  {
    v11 = -2147024362;
    v17 = 120390454;
LABEL_45:
    v20 = v11;
    goto LABEL_46;
  }
  v18 = CertAllocStringLen(0, (int)v16 - 1);
  v8 = v18;
  if ( !v18 )
  {
    v11 = -2147024882;
    v17 = 120783670;
    goto LABEL_45;
  }
  StringCchCopyW(v18, v16, L"CN=");
  StringCchCatW(v8, v16, v9);
  StringCchCatW(v8, v16, L",");
  StringCchCatW(v8, v16, L"CN=OID,CN=Public Key Services,CN=Services,");
  StringCchCatW(v8, v16, v7);
  v37 = L"flags";
  v45[0] = (PWSTR)L"flags";
  timeout = (struct l_timeval)120LL;
  *((_QWORD *)&v46 + 1) = 0;
  v45[1] = (PWSTR)L"displayName";
  *(_QWORD *)&v46 = L"msPKI-OID-CPS";
  v19 = FormatMessageUnicode(&filter, L"(%1!s!=%2!s!)", L"msPKI-Cert-Template-OID", v44);
  v11 = v19;
  if ( v19 )
  {
    v20 = v19;
    v17 = 122028854;
LABEL_46:
    CSPrintErrorLineFile(v17, v20);
    goto LABEL_47;
  }
  v11 = 0;
  v21 = ldap_search_stW(v5, v8, 0, filter, v45, 0, &timeout, &res);
  if ( v21 )
  {
    v11 = myHLdapError3(v5, v21, 0x20u, v22, attrs);
    CSPrintErrorLineFileData2(filter, 0x75A0336u, v11, -2147016563);
    goto LABEL_47;
  }
  if ( ldap_count_entries(v5, res) != 1 || (entry = ldap_first_entry(v5, res)) == 0 )
  {
    v11 = myHLdapError3(v5, 0x20u, 0, v23, attrs);
    v20 = v11;
    v17 = 123994934;
    goto LABEL_46;
  }
  v25 = a2 - 1;
  if ( v25 )
  {
    v26 = v25 - 1;
    if ( v26 )
    {
      if ( v26 != 1 )
      {
        v27 = 0;
        v28 = L"Unknown";
        v11 = -2147024809;
        goto LABEL_40;
      }
      valuesW = (const wchar_t **)ldap_get_valuesW(v5, entry, (const PWSTR)L"flags");
      v27 = (PWCHAR *)valuesW;
      if ( valuesW && *valuesW )
      {
        v31 = _wtol(*valuesW);
        *(_DWORD *)v43 = v31;
        goto LABEL_41;
      }
      goto LABEL_37;
    }
    v37 = L"msPKI-OID-CPS";
    v32 = (WCHAR *)L"msPKI-OID-CPS";
  }
  else
  {
    v37 = L"displayName";
    v32 = (WCHAR *)L"displayName";
  }
  v33 = ldap_get_valuesW(v5, entry, v32);
  v27 = v33;
  if ( !v33 || !*v33 )
  {
LABEL_37:
    v34 = myHLdapError3(v5, 0x10u, 0, v30, attrs);
    goto LABEL_38;
  }
  v34 = CAOIDAllocAndCopy(*v33, v43);
LABEL_38:
  v11 = v34;
  if ( !v34 )
    goto LABEL_41;
  v28 = v37;
LABEL_40:
  CSPrintErrorLineFileData2(v28, 0x7940336u, v11, 0);
  CSPrintErrorLineFileData2(v44, 0x7950336u, v11, 0);
LABEL_41:
  if ( v27 )
    ldap_value_freeW(v27);
LABEL_47:
  if ( filter )
    LocalFree(filter);
  if ( res )
    ldap_msgfree(res);
  if ( v9 )
    LocalFree(v9);
  if ( v8 )
    CertFreeString(v8);
  if ( v7 )
    CertFreeString(v7);
  if ( v6 )
    ldap_unbind(v6);
  return v11;
}

```

## disassembly

```asm
0x18002c24c  mov     [rsp-8+arg_8], rbx
0x18002c251  push    rbp
0x18002c252  push    rsi
0x18002c253  push    rdi
0x18002c254  push    r12
0x18002c256  push    r13
0x18002c258  push    r14
0x18002c25a  push    r15
0x18002c25c  lea     rbp, [rsp-27h]
0x18002c261  sub     rsp, 0B0h
0x18002c268  mov     rax, cs:__security_cookie
0x18002c26f  xor     rax, rsp
0x18002c272  mov     [rbp+57h+var_40], rax
0x18002c276  xorps   xmm0, xmm0
0x18002c279  mov     [rbp+57h+var_68], rcx
0x18002c27d  mov     esi, edx
0x18002c27f  mov     rax, r8
0x18002c282  xor     edx, edx
0x18002c284  mov     [rbp+57h+var_70], rax
0x18002c288  mov     qword ptr [rbp+57h+var_78.tv_sec], rdx
0x18002c28c  mov     rdi, r9
0x18002c28f  mov     [rbp+57h+filter], rdx
0x18002c293  mov     r13d, edx
0x18002c296  mov     [rbp+57h+var_88], rdx
0x18002c29a  mov     r15d, edx
0x18002c29d  mov     [rbp+57h+ld], rdx
0x18002c2a1  mov     r14d, edx
0x18002c2a4  mov     [rbp+57h+var_98], rdx
0x18002c2a8  mov     r12d, edx
0x18002c2ab  mov     [rbp+57h+var_A0], rdx
0x18002c2af  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x18002c2b3  movups  [rbp+57h+var_50], xmm0
0x18002c2b7  test    rcx, rcx
0x18002c2ba  jz      loc_18002C610
0x18002c2c0  test    rax, rax
0x18002c2c3  jz      loc_18002C610
0x18002c2c9  test    r9, r9
0x18002c2cc  jnz     short loc_18002C305
0x18002c2ce  lea     rcx, [rbp+57h+ld]; struct ldap **
0x18002c2d2  call    ?myTimeOutRobustLdapBind@@YAJPEAPEAUldap@@@Z; myTimeOutRobustLdapBind(ldap * *)
0x18002c2d7  mov     ebx, eax
0x18002c2d9  test    eax, eax
0x18002c2db  jz      short loc_18002C2FE
0x18002c2dd  mov     edx, eax; int
0x18002c2df  mov     ecx, 9E0336h; unsigned int
0x18002c2e4  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002c2e9  mov     edx, ebx; int
0x18002c2eb  mov     ecx, 71D0336h; unsigned int
0x18002c2f0  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002c2f5  mov     r13, [rbp+57h+ld]
0x18002c2f9  jmp     loc_18002C621
0x18002c2fe  mov     r13, [rbp+57h+ld]
0x18002c302  mov     rdi, r13
0x18002c305  lea     r8, [rbp+57h+var_98]; unsigned __int16 **
0x18002c309  xor     edx, edx; unsigned __int16 **
0x18002c30b  mov     rcx, rdi; struct ldap *
0x18002c30e  call    ?CAGetAuthoritativeDomainDn@@YAJPEAUldap@@PEAPEAG1@Z; CAGetAuthoritativeDomainDn(ldap *,ushort * *,ushort * *)
0x18002c313  mov     ebx, eax
0x18002c315  test    eax, eax
0x18002c317  jz      short loc_18002C32E
0x18002c319  mov     edx, eax; int
0x18002c31b  mov     ecx, 7220336h; unsigned int
0x18002c320  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002c325  mov     r15, [rbp+57h+var_98]
0x18002c329  jmp     loc_18002C621
0x18002c32e  mov     rcx, [rbp+57h+var_68]; unsigned __int16 *
0x18002c332  lea     rdx, [rbp+57h+var_A0]; unsigned __int16 **
0x18002c336  call    ?myOIDHashOIDToString@@YAJPEBGPEAPEAG@Z; myOIDHashOIDToString(ushort const *,ushort * *)
0x18002c33b  xor     edx, edx
0x18002c33d  mov     ebx, eax
0x18002c33f  test    eax, eax
0x18002c341  jz      short loc_18002C35C
0x18002c343  mov     edx, eax; int
0x18002c345  mov     ecx, 7270336h; unsigned int
0x18002c34a  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002c34f  mov     r15, [rbp+57h+var_98]
0x18002c353  mov     r12, [rbp+57h+var_A0]
0x18002c357  jmp     loc_18002C621
0x18002c35c  mov     r15, [rbp+57h+var_98]
0x18002c360  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002c364  mov     rcx, rax
0x18002c367  inc     rcx
0x18002c36a  cmp     [r15+rcx*2], dx
0x18002c36f  jnz     short loc_18002C367
0x18002c371  mov     r12, [rbp+57h+var_A0]
0x18002c375  inc     rax
0x18002c378  cmp     [r12+rax*2], dx
0x18002c37d  jnz     short loc_18002C375
0x18002c37f  lea     rbx, [rcx+2Fh]
0x18002c383  add     rbx, rax
0x18002c386  cmp     rbx, 10000h
0x18002c38d  jbe     short loc_18002C39E
0x18002c38f  mov     ebx, 80070216h
0x18002c394  mov     ecx, 72D0336h
0x18002c399  jmp     loc_18002C61A
0x18002c39e  lea     edx, [rbx-1]; unsigned int
0x18002c3a1  xor     ecx, ecx; Src
0x18002c3a3  call    ?CertAllocStringLen@@YAPEAGPEBGI@Z; CertAllocStringLen(ushort const *,uint)
0x18002c3a8  mov     r14, rax
0x18002c3ab  test    rax, rax
0x18002c3ae  jnz     short loc_18002C3BF
0x18002c3b0  mov     ebx, 8007000Eh
0x18002c3b5  mov     ecx, 7330336h
0x18002c3ba  jmp     loc_18002C61A
0x18002c3bf  lea     r8, aCn_2; "CN="
0x18002c3c6  mov     rdx, rbx; unsigned __int64
0x18002c3c9  mov     rcx, r14; unsigned __int16 *
0x18002c3cc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002c3d1  mov     r8, r12; unsigned __int16 *
0x18002c3d4  mov     rdx, rbx; unsigned __int64
0x18002c3d7  mov     rcx, r14; unsigned __int16 *
0x18002c3da  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002c3df  lea     r8, asc_180063424; ","
0x18002c3e6  mov     rdx, rbx; unsigned __int64
0x18002c3e9  mov     rcx, r14; unsigned __int16 *
0x18002c3ec  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002c3f1  lea     r8, aCnOidCnPublicK; "CN=OID,CN=Public Key Services,CN=Servic"...
0x18002c3f8  mov     rdx, rbx; unsigned __int64
0x18002c3fb  mov     rcx, r14; unsigned __int16 *
0x18002c3fe  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002c403  mov     r8, r15; unsigned __int16 *
0x18002c406  mov     rdx, rbx; unsigned __int64
0x18002c409  mov     rcx, r14; unsigned __int16 *
0x18002c40c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002c411  mov     r9, [rbp+57h+var_68]
0x18002c415  lea     rax, attr; "flags"
0x18002c41c  mov     [rbp+57h+var_A0], rax
0x18002c420  lea     r8, aMspkiCertTempl; "msPKI-Cert-Template-OID"
0x18002c427  mov     [rbp+57h+var_60], rax
0x18002c42b  lea     rdx, a1S2S; "(%1!s!=%2!s!)"
0x18002c432  xor     ecx, ecx
0x18002c434  mov     qword ptr [rbp+57h+var_78.tv_sec], 78h ; 'x'
0x18002c43c  lea     rax, aDisplayname_0; "displayName"
0x18002c443  mov     qword ptr [rbp+57h+var_50+8], rcx
0x18002c447  mov     [rbp+57h+var_60+8], rax
0x18002c44b  lea     rcx, [rbp+57h+filter]; unsigned __int16 **
0x18002c44f  lea     rax, aMspkiOidCps; "msPKI-OID-CPS"
0x18002c456  mov     qword ptr [rbp+57h+var_50], rax
0x18002c45a  call    ?FormatMessageUnicode@@YAJPEAPEAGPEAGZZ; FormatMessageUnicode(ushort * *,ushort *,...)
0x18002c45f  mov     ebx, eax
0x18002c461  test    eax, eax
0x18002c463  jz      short loc_18002C471
0x18002c465  mov     edx, eax
0x18002c467  mov     ecx, 7460336h
0x18002c46c  jmp     loc_18002C61C
0x18002c471  mov     r9, [rbp+57h+filter]; filter
0x18002c475  lea     rax, [rbp+57h+var_88]
0x18002c479  mov     [rsp+0E0h+res], rax; res
0x18002c47e  xor     ebx, ebx
0x18002c480  lea     rax, [rbp+57h+var_78]
0x18002c484  xor     r8d, r8d; scope
0x18002c487  mov     [rsp+0E0h+timeout], rax; timeout
0x18002c48c  mov     rdx, r14; base
0x18002c48f  lea     rax, [rbp+57h+var_60]
0x18002c493  mov     [rsp+0E0h+attrsonly], ebx; attrsonly
0x18002c497  mov     rcx, rdi; ld
0x18002c49a  mov     [rsp+0E0h+attrs], rax; unsigned __int16 **
0x18002c49f  call    cs:__imp_ldap_search_stW
0x18002c4a5  mov     rcx, rdi; ld
0x18002c4a8  test    eax, eax
0x18002c4aa  jz      short loc_18002C4D5
0x18002c4ac  lea     r8d, [rbx+20h]; unsigned int
0x18002c4b0  mov     edx, eax; unsigned int
0x18002c4b2  call    ?myHLdapError3@@YAJPEAUldap@@KKKPEAPEAG@Z; myHLdapError3(ldap *,ulong,ulong,ulong,ushort * *)
0x18002c4b7  mov     rcx, [rbp+57h+filter]; unsigned __int16 *
0x18002c4bb  mov     r9d, 8007208Dh; int
0x18002c4c1  mov     r8d, eax; int
0x18002c4c4  mov     edx, 75A0336h; unsigned int
0x18002c4c9  mov     ebx, eax
0x18002c4cb  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18002c4d0  jmp     loc_18002C621
0x18002c4d5  mov     rdx, [rbp+57h+var_88]; res
0x18002c4d9  call    cs:__imp_ldap_count_entries
0x18002c4df  cmp     eax, 1
0x18002c4e2  jnz     loc_18002C5F6
0x18002c4e8  mov     rdx, [rbp+57h+var_88]; res
0x18002c4ec  mov     rcx, rdi; ld
0x18002c4ef  call    cs:__imp_ldap_first_entry
0x18002c4f5  test    rax, rax
0x18002c4f8  jz      loc_18002C5F6
0x18002c4fe  sub     esi, 1
0x18002c501  jz      loc_18002C592
0x18002c507  sub     esi, 1
0x18002c50a  jz      short loc_18002C559
0x18002c50c  cmp     esi, 1
0x18002c50f  jz      short loc_18002C525
0x18002c511  mov     rsi, rbx
0x18002c514  lea     rax, aUnknown; "Unknown"
0x18002c51b  mov     ebx, 80070057h
0x18002c520  jmp     loc_18002C5BF
0x18002c525  lea     r8, attr; "flags"
0x18002c52c  mov     rdx, rax; entry
0x18002c52f  mov     rcx, rdi; ld
0x18002c532  call    cs:__imp_ldap_get_valuesW
0x18002c538  mov     rsi, rax
0x18002c53b  test    rax, rax
0x18002c53e  jz      short loc_18002C5A6
0x18002c540  mov     rcx, [rax]; String
0x18002c543  test    rcx, rcx
0x18002c546  jz      short loc_18002C5A6
0x18002c548  call    cs:__imp__wtol
0x18002c54e  mov     rdx, [rbp+57h+var_70]
0x18002c552  mov     [rdx], eax
0x18002c554  jmp     loc_18002C5E6
0x18002c559  lea     r8, aMspkiOidCps; "msPKI-OID-CPS"
0x18002c560  mov     [rbp+57h+var_A0], r8
0x18002c564  lea     r8, aMspkiOidCps; "msPKI-OID-CPS"
0x18002c56b  mov     rdx, rax; entry
0x18002c56e  mov     rcx, rdi; ld
0x18002c571  call    cs:__imp_ldap_get_valuesW
0x18002c577  mov     rsi, rax
0x18002c57a  test    rax, rax
0x18002c57d  jz      short loc_18002C5A6
0x18002c57f  mov     rcx, [rax]; unsigned __int16 *
0x18002c582  test    rcx, rcx
0x18002c585  jz      short loc_18002C5A6
0x18002c587  mov     rdx, [rbp+57h+var_70]; unsigned __int16 **
0x18002c58b  call    ?CAOIDAllocAndCopy@@YAJPEAGPEAPEAG@Z; CAOIDAllocAndCopy(ushort *,ushort * *)
0x18002c590  jmp     short loc_18002C5B5
0x18002c592  lea     r8, aDisplayname_0; "displayName"
0x18002c599  mov     [rbp+57h+var_A0], r8
0x18002c59d  lea     r8, aDisplayname_0; "displayName"
0x18002c5a4  jmp     short loc_18002C56B
0x18002c5a6  xor     r8d, r8d; unsigned int
0x18002c5a9  mov     rcx, rdi; ld
0x18002c5ac  lea     edx, [r8+10h]; unsigned int
0x18002c5b0  call    ?myHLdapError3@@YAJPEAUldap@@KKKPEAPEAG@Z; myHLdapError3(ldap *,ulong,ulong,ulong,ushort * *)
0x18002c5b5  mov     ebx, eax
0x18002c5b7  test    eax, eax
0x18002c5b9  jz      short loc_18002C5E6
0x18002c5bb  mov     rax, [rbp+57h+var_A0]
0x18002c5bf  xor     r9d, r9d; int
0x18002c5c2  mov     r8d, ebx; int
0x18002c5c5  mov     edx, 7940336h; unsigned int
0x18002c5ca  mov     rcx, rax; unsigned __int16 *
0x18002c5cd  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18002c5d2  mov     rcx, [rbp+57h+var_68]; unsigned __int16 *
0x18002c5d6  xor     r9d, r9d; int
0x18002c5d9  mov     r8d, ebx; int
0x18002c5dc  mov     edx, 7950336h; unsigned int
0x18002c5e1  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18002c5e6  test    rsi, rsi
0x18002c5e9  jz      short loc_18002C621
0x18002c5eb  mov     rcx, rsi; vals
0x18002c5ee  call    cs:__imp_ldap_value_freeW
0x18002c5f4  jmp     short loc_18002C621
0x18002c5f6  xor     r8d, r8d; unsigned int
0x18002c5f9  mov     rcx, rdi; ld
0x18002c5fc  lea     edx, [r8+20h]; unsigned int
0x18002c600  call    ?myHLdapError3@@YAJPEAUldap@@KKKPEAPEAG@Z; myHLdapError3(ldap *,ulong,ulong,ulong,ushort * *)
0x18002c605  mov     ebx, eax
0x18002c607  mov     edx, eax
0x18002c609  mov     ecx, 7640336h
0x18002c60e  jmp     short loc_18002C61C
0x18002c610  mov     ebx, 80070057h
0x18002c615  mov     ecx, 7190336h; unsigned int
0x18002c61a  mov     edx, ebx; int
0x18002c61c  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002c621  mov     rcx, [rbp+57h+filter]; hMem
0x18002c625  test    rcx, rcx
0x18002c628  jz      short loc_18002C630
0x18002c62a  call    cs:__imp_LocalFree
0x18002c630  mov     rcx, [rbp+57h+var_88]; res
0x18002c634  test    rcx, rcx
0x18002c637  jz      short loc_18002C63F
0x18002c639  call    cs:__imp_ldap_msgfree
0x18002c63f  test    r12, r12
0x18002c642  jz      short loc_18002C64D
0x18002c644  mov     rcx, r12; hMem
0x18002c647  call    cs:__imp_LocalFree
0x18002c64d  test    r14, r14
0x18002c650  jz      short loc_18002C65A
0x18002c652  mov     rcx, r14; unsigned __int16 *
0x18002c655  call    ?CertFreeString@@YAJPEAG@Z; CertFreeString(ushort *)
0x18002c65a  test    r15, r15
0x18002c65d  jz      short loc_18002C667
0x18002c65f  mov     rcx, r15; unsigned __int16 *
0x18002c662  call    ?CertFreeString@@YAJPEAG@Z; CertFreeString(ushort *)
0x18002c667  test    r13, r13
0x18002c66a  jz      short loc_18002C675
0x18002c66c  mov     rcx, r13; ld
0x18002c66f  call    cs:__imp_ldap_unbind
0x18002c675  mov     eax, ebx
0x18002c677  mov     rcx, [rbp+57h+var_40]
0x18002c67b  xor     rcx, rsp; StackCookie
0x18002c67e  call    __security_check_cookie
0x18002c683  mov     rbx, [rsp+0E0h+arg_8]
0x18002c68b  add     rsp, 0B0h
0x18002c692  pop     r15
0x18002c694  pop     r14
0x18002c696  pop     r13
0x18002c698  pop     r12
0x18002c69a  pop     rdi
0x18002c69b  pop     rsi
0x18002c69c  pop     rbp
0x18002c69d  retn
```
