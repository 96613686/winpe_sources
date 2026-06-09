# GmsapGetSingleBinaryAttribute

- ea: `0x180007064`
- end: `0x180007372`
- name: `GmsapGetSingleBinaryAttribute`
- size: `782`
- prototype: `__int64 __usercall@<rax>(LDAP *ld@<rcx>, PWSTR base@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180006084`

## callees

- `0x180006280`
- `0x1800062b0`
- `0x18000634c`
- `0x1800063cc`
- `0x18000686c`
- `0x180007064`
- `0x180007bcd`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800071d6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800071d6`
- `WLDAP32!__imp_ldap_first_entry` at `0x180007188`
- `WLDAP32!__imp_ldap_first_entry` at `0x180007188`
- `WLDAP32!__imp_ldap_count_entries` at `0x180007169`
- `WLDAP32!__imp_ldap_count_entries` at `0x180007169`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800072ec`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800072ec`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18000732c`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18000732c`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x18000719f`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x18000719f`
- `WLDAP32!__imp_ldap_search_sW` at `0x180007107`
- `WLDAP32!__imp_ldap_search_sW` at `0x180007107`

## pseudocode

```c
__int64 __fastcall GmsapGetSingleBinaryAttribute(LDAP *ld, PWSTR base, __int64 a3, ULONG *a4, _QWORD *a5)
{
  struct berval **v8; // rdi
  _QWORD *v9; // r14
  ULONG v10; // eax
  int v11; // eax
  unsigned int v12; // ebx
  _UNKNOWN **v13; // rcx
  LDAPMessage *entry; // rax
  struct berval **values_lenW; // rax
  struct berval *v16; // rax
  HLOCAL v17; // rax
  struct berval *v18; // rax
  ULONG bv_len; // ecx
  PCHAR bv_val; // rax
  __int64 v21; // rdx
  __int128 attr; // [rsp+40h] [rbp-48h] BYREF
  LDAPMessage *res; // [rsp+A0h] [rbp+18h] BYREF

  res = 0;
  attr = 0;
  v8 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x15u, &WPP_664bdc16998933377d7f42e86ad1a4df_Traceguids);
  v9 = a5;
  *(_QWORD *)&attr = L"msDS-ManagedPassword";
  *a4 = 0;
  *v9 = 0;
  *((_QWORD *)&attr + 1) = 0;
  v10 = ldap_search_sW(ld, base, 0, (const PWSTR)L"(objectClass=*)", (PZPWSTR)&attr, 0, &res);
  v11 = GmsapMapLdapErrorToNtStatusEx(ld, v10);
  v12 = v11;
  if ( v11 >= 0 )
  {
    if ( res && ldap_count_entries(ld, res) )
    {
      entry = ldap_first_entry(ld, res);
      values_lenW = ldap_get_values_lenW(ld, entry, (const PWSTR)attr);
      v8 = values_lenW;
      if ( values_lenW && (v16 = *values_lenW) != 0 )
      {
        if ( v16->bv_len && v16->bv_val )
        {
          v17 = LocalAlloc(0x40u, v16->bv_len);
          *v9 = v17;
          if ( v17 )
          {
            memcpy_0(v17, (*v8)->bv_val, (*v8)->bv_len);
            v12 = 0;
            *a4 = (*v8)->bv_len;
          }
          else
          {
            v12 = -1073741801;
          }
          goto LABEL_28;
        }
        v12 = -1073741151;
        v13 = (_UNKNOWN **)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_SSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            (unsigned int)&WPP_664bdc16998933377d7f42e86ad1a4df_Traceguids,
            (unsigned int)L"msDS-ManagedPassword",
            (__int64)base,
            161);
          goto LABEL_28;
        }
      }
      else
      {
        v12 = -1073741790;
        v13 = (_UNKNOWN **)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_SSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            24,
            (unsigned int)&WPP_664bdc16998933377d7f42e86ad1a4df_Traceguids,
            (unsigned int)L"msDS-ManagedPassword",
            (__int64)base,
            34);
          goto LABEL_28;
        }
      }
    }
    else
    {
      v12 = -1073741151;
      v13 = (_UNKNOWN **)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          (unsigned int)&WPP_664bdc16998933377d7f42e86ad1a4df_Traceguids,
          (_DWORD)base,
          161);
        goto LABEL_28;
      }
    }
  }
  else
  {
    v13 = (_UNKNOWN **)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        (unsigned int)&WPP_664bdc16998933377d7f42e86ad1a4df_Traceguids,
        (_DWORD)base,
        v11);
LABEL_28:
      v13 = (_UNKNOWN **)WPP_GLOBAL_Control;
    }
  }
  if ( res )
  {
    ldap_msgfree(res);
    v13 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( v8 )
  {
    v18 = *v8;
    if ( *v8 )
    {
      bv_len = v18->bv_len;
      if ( v18->bv_len )
      {
        bv_val = v18->bv_val;
        if ( bv_val )
        {
          v21 = bv_len;
          do
          {
            *bv_val++ = 0;
            --v21;
          }
          while ( v21 );
        }
      }
    }
    ldap_value_free_len(v8);
    v13 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 4) != 0 )
    WPP_SF_D((TRACEHANDLE)v13[2], 0x1Au, &WPP_664bdc16998933377d7f42e86ad1a4df_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x180007064  mov     rax, rsp
0x180007067  mov     [rax+18h], r8
0x18000706b  push    rbx
0x18000706c  push    rbp
0x18000706d  push    rsi
0x18000706e  push    rdi
0x18000706f  push    r14
0x180007071  push    r15
0x180007073  sub     rsp, 58h
0x180007077  xorps   xmm0, xmm0
0x18000707a  mov     qword ptr [rax+18h], 0
0x180007082  movups  xmmword ptr [rax-48h], xmm0
0x180007086  mov     r15, r9
0x180007089  mov     rbp, rdx
0x18000708c  mov     rsi, rcx
0x18000708f  xor     edi, edi
0x180007091  mov     rcx, cs:WPP_GLOBAL_Control
0x180007098  lea     rax, WPP_GLOBAL_Control
0x18000709f  cmp     rcx, rax
0x1800070a2  jz      short loc_1800070BD
0x1800070a4  test    byte ptr [rcx+1Ch], 4
0x1800070a8  jz      short loc_1800070BD
0x1800070aa  mov     rcx, [rcx+10h]
0x1800070ae  lea     edx, [rdi+15h]
0x1800070b1  lea     r8, WPP_664bdc16998933377d7f42e86ad1a4df_Traceguids
0x1800070b8  call    WPP_SF_
0x1800070bd  mov     r14, [rsp+88h+arg_20]
0x1800070c5  lea     rax, aMsdsManagedpas; "msDS-ManagedPassword"
0x1800070cc  mov     [rsp+88h+attr], rax
0x1800070d1  lea     r9, filter; "(objectClass=*)"
0x1800070d8  lea     rax, [rsp+88h+arg_10]
0x1800070e0  mov     [r15], edi
0x1800070e3  mov     [rsp+88h+res], rax; res
0x1800070e8  xor     r8d, r8d; scope
0x1800070eb  lea     rax, [rsp+88h+attr]
0x1800070f0  mov     [rsp+88h+attrsonly], edi; attrsonly
0x1800070f4  mov     rdx, rbp; base
0x1800070f7  mov     [rsp+88h+attrs], rax; attrs
0x1800070fc  mov     rcx, rsi; ld
0x1800070ff  mov     [r14], rdi
0x180007102  mov     [rsp+88h+var_40], rdi
0x180007107  call    cs:__imp_ldap_search_sW
0x18000710e  nop     dword ptr [rax+rax+00h]
0x180007113  mov     edx, eax; LdapError
0x180007115  mov     rcx, rsi; ld
0x180007118  call    ?GmsapMapLdapErrorToNtStatusEx@@YAJPEAUldap@@K@Z; GmsapMapLdapErrorToNtStatusEx(ldap *,ulong)
0x18000711d  mov     ebx, eax
0x18000711f  test    eax, eax
0x180007121  jns     short loc_180007152
0x180007123  mov     rcx, cs:WPP_GLOBAL_Control
0x18000712a  lea     rsi, WPP_GLOBAL_Control
0x180007131  cmp     rcx, rsi
0x180007134  jz      loc_1800072DC
0x18000713a  test    byte ptr [rcx+1Ch], 4
0x18000713e  jz      loc_1800072DC
0x180007144  mov     edx, 16h
0x180007149  mov     dword ptr [rsp+88h+attrs], eax
0x18000714d  jmp     loc_1800072C2
0x180007152  mov     rax, [rsp+88h+arg_10]
0x18000715a  test    rax, rax
0x18000715d  jz      loc_180007297
0x180007163  mov     rdx, rax; res
0x180007166  mov     rcx, rsi; ld
0x180007169  call    cs:__imp_ldap_count_entries
0x180007170  nop     dword ptr [rax+rax+00h]
0x180007175  test    eax, eax
0x180007177  jz      loc_180007297
0x18000717d  mov     rdx, [rsp+88h+arg_10]; res
0x180007185  mov     rcx, rsi; ld
0x180007188  call    cs:__imp_ldap_first_entry
0x18000718f  nop     dword ptr [rax+rax+00h]
0x180007194  mov     r8, [rsp+88h+attr]; attr
0x180007199  mov     rcx, rsi; ExternalHandle
0x18000719c  mov     rdx, rax; Message
0x18000719f  call    cs:__imp_ldap_get_values_lenW
0x1800071a6  nop     dword ptr [rax+rax+00h]
0x1800071ab  mov     rdi, rax
0x1800071ae  test    rax, rax
0x1800071b1  jz      loc_18000726A
0x1800071b7  mov     rax, [rax]
0x1800071ba  test    rax, rax
0x1800071bd  jz      loc_18000726A
0x1800071c3  cmp     dword ptr [rax], 0
0x1800071c6  jz      short loc_180007219
0x1800071c8  cmp     qword ptr [rax+8], 0
0x1800071cd  jz      short loc_180007219
0x1800071cf  mov     edx, [rax]; uBytes
0x1800071d1  mov     ecx, 40h ; '@'; uFlags
0x1800071d6  call    cs:__imp_LocalAlloc
0x1800071dd  nop     dword ptr [rax+rax+00h]
0x1800071e2  mov     [r14], rax
0x1800071e5  test    rax, rax
0x1800071e8  jnz     short loc_1800071FB
0x1800071ea  mov     ebx, 0C0000017h
0x1800071ef  lea     rsi, WPP_GLOBAL_Control
0x1800071f6  jmp     loc_1800072D5
0x1800071fb  mov     rdx, [rdi]
0x1800071fe  mov     rcx, rax; void *
0x180007201  mov     r8d, [rdx]; Size
0x180007204  mov     rdx, [rdx+8]; Src
0x180007208  call    memcpy_0
0x18000720d  mov     rax, [rdi]
0x180007210  xor     ebx, ebx
0x180007212  mov     ecx, [rax]
0x180007214  mov     [r15], ecx
0x180007217  jmp     short loc_1800071EF
0x180007219  mov     ebx, 0C00002A1h
0x18000721e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007225  lea     rsi, WPP_GLOBAL_Control
0x18000722c  cmp     rcx, rsi
0x18000722f  jz      loc_1800072DC
0x180007235  test    byte ptr [rcx+1Ch], 4
0x180007239  jz      loc_1800072DC
0x18000723f  mov     edx, 19h
0x180007244  mov     [rsp+88h+attrsonly], 0C00002A1h
0x18000724c  mov     rcx, [rcx+10h]
0x180007250  lea     r9, aMsdsManagedpas; "msDS-ManagedPassword"
0x180007257  lea     r8, WPP_664bdc16998933377d7f42e86ad1a4df_Traceguids
0x18000725e  mov     [rsp+88h+attrs], rbp
0x180007263  call    WPP_SF_SSD
0x180007268  jmp     short loc_1800072D5
0x18000726a  mov     ebx, 0C0000022h
0x18000726f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007276  lea     rsi, WPP_GLOBAL_Control
0x18000727d  cmp     rcx, rsi
0x180007280  jz      short loc_1800072DC
0x180007282  test    byte ptr [rcx+1Ch], 4
0x180007286  jz      short loc_1800072DC
0x180007288  mov     edx, 18h
0x18000728d  mov     [rsp+88h+attrsonly], 0C0000022h
0x180007295  jmp     short loc_18000724C
0x180007297  mov     ebx, 0C00002A1h
0x18000729c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800072a3  lea     rsi, WPP_GLOBAL_Control
0x1800072aa  cmp     rcx, rsi
0x1800072ad  jz      short loc_1800072DC
0x1800072af  test    byte ptr [rcx+1Ch], 4
0x1800072b3  jz      short loc_1800072DC
0x1800072b5  mov     edx, 17h
0x1800072ba  mov     dword ptr [rsp+88h+attrs], 0C00002A1h
0x1800072c2  mov     rcx, [rcx+10h]
0x1800072c6  lea     r8, WPP_664bdc16998933377d7f42e86ad1a4df_Traceguids
0x1800072cd  mov     r9, rbp
0x1800072d0  call    WPP_SF_SD
0x1800072d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800072dc  mov     rax, [rsp+88h+arg_10]
0x1800072e4  test    rax, rax
0x1800072e7  jz      short loc_1800072FF
0x1800072e9  mov     rcx, rax; res
0x1800072ec  call    cs:__imp_ldap_msgfree
0x1800072f3  nop     dword ptr [rax+rax+00h]
0x1800072f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800072ff  test    rdi, rdi
0x180007302  jz      short loc_18000733F
0x180007304  mov     rax, [rdi]
0x180007307  test    rax, rax
0x18000730a  jz      short loc_180007329
0x18000730c  mov     ecx, [rax]
0x18000730e  test    ecx, ecx
0x180007310  jz      short loc_180007329
0x180007312  mov     rax, [rax+8]
0x180007316  test    rax, rax
0x180007319  jz      short loc_180007329
0x18000731b  mov     edx, ecx
0x18000731d  mov     byte ptr [rax], 0
0x180007320  inc     rax
0x180007323  sub     rdx, 1
0x180007327  jnz     short loc_18000731D
0x180007329  mov     rcx, rdi; vals
0x18000732c  call    cs:__imp_ldap_value_free_len
0x180007333  nop     dword ptr [rax+rax+00h]
0x180007338  mov     rcx, cs:WPP_GLOBAL_Control
0x18000733f  cmp     rcx, rsi
0x180007342  jz      short loc_180007362
0x180007344  test    byte ptr [rcx+1Ch], 4
0x180007348  jz      short loc_180007362
0x18000734a  mov     rcx, [rcx+10h]
0x18000734e  lea     r8, WPP_664bdc16998933377d7f42e86ad1a4df_Traceguids
0x180007355  mov     edx, 1Ah
0x18000735a  mov     r9d, ebx
0x18000735d  call    WPP_SF_D
0x180007362  mov     eax, ebx
0x180007364  add     rsp, 58h
0x180007368  pop     r15
0x18000736a  pop     r14
0x18000736c  pop     rdi
0x18000736d  pop     rsi
0x18000736e  pop     rbp
0x18000736f  pop     rbx
0x180007370  retn
```
