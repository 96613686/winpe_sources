# GmsapGetAccountObject

- ea: `0x180006a38`
- end: `0x180006f60`
- name: `GmsapGetAccountObject`
- size: `1320`
- prototype: `__int64 __fastcall(LDAP *ld)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x1800025b0`
- `0x180006084`

## callees

- `0x180001400`
- `0x180006280`
- `0x1800066ac`
- `0x180006a38`
- `0x18000764c`
- `0x1800078fc`
- `0x180007bcd`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006e29`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006e29`
- `WLDAP32!__imp_ldap_first_entry` at `0x180006b72`
- `WLDAP32!__imp_ldap_first_entry` at `0x180006d88`
- `WLDAP32!__imp_ldap_first_entry` at `0x180006b72`
- `WLDAP32!__imp_ldap_first_entry` at `0x180006d88`
- `WLDAP32!__imp_ldap_count_entries` at `0x180006c15`
- `WLDAP32!__imp_ldap_count_entries` at `0x180006c15`
- `WLDAP32!__imp_ldap_msgfree` at `0x180006b9f`
- `WLDAP32!__imp_ldap_msgfree` at `0x180006c48`
- `WLDAP32!__imp_ldap_msgfree` at `0x180006dae`
- `WLDAP32!__imp_ldap_msgfree` at `0x180006b9f`
- `WLDAP32!__imp_ldap_msgfree` at `0x180006c48`
- `WLDAP32!__imp_ldap_msgfree` at `0x180006dae`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180006b88`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180006df7`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180006e9d`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180006b88`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180006df7`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180006e9d`
- `WLDAP32!__imp_ldap_search_sW` at `0x180006b14`
- `WLDAP32!__imp_ldap_search_sW` at `0x180006d00`
- `WLDAP32!__imp_ldap_search_sW` at `0x180006b14`
- `WLDAP32!__imp_ldap_search_sW` at `0x180006d00`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180006dd6`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180006e73`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180006e87`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180006dd6`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180006e73`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180006e87`
- `netutils!NetApiBufferFree` at `0x180006c60`
- `netutils!NetApiBufferFree` at `0x180006dc2`
- `netutils!NetApiBufferFree` at `0x180006c60`
- `netutils!NetApiBufferFree` at `0x180006dc2`
- `netutils!NetApiBufferAllocate` at `0x180006ee9`
- `netutils!NetApiBufferAllocate` at `0x180006ee9`

## string_xrefs

- `0x180006e1e`: `msDS-GroupManagedServiceAccount`
- `0x180006e5f`: `msDS-GroupManagedServiceAccount`

## pseudocode

```c
__int64 __fastcall GmsapGetAccountObject(LDAP *ld, __int64 a2, LPVOID *a3, int *a4)
{
  int v4; // r15d
  void *v9; // rsi
  ULONG v10; // eax
  int v11; // ebx
  PWCHAR *valuesW; // r12
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  LDAPMessage *entry; // rax
  ULONG v16; // eax
  __int64 v17; // r8
  ULONG v18; // eax
  LDAPMessage *v19; // rax
  LDAPMessage *v20; // r12
  WCHAR *v22; // r8
  PWCHAR *v23; // rax
  __int64 v24; // r8
  PWCHAR *v25; // rdi
  __int64 v26; // r15
  PWCHAR *v27; // rax
  PWCHAR v28; // rbx
  __int64 v29; // rax
  void **v30; // r15
  DWORD v31; // r14d
  LDAPMessage *res; // [rsp+40h] [rbp-29h] BYREF
  LPVOID Buffer; // [rsp+48h] [rbp-21h] BYREF
  PWCHAR *v34; // [rsp+50h] [rbp-19h]
  LPVOID *v35; // [rsp+58h] [rbp-11h]
  PWSTR attr[2]; // [rsp+60h] [rbp-9h] BYREF
  __int64 v37; // [rsp+70h] [rbp+7h]

  v4 = 0;
  Buffer = 0;
  v35 = a3;
  v37 = 0;
  res = 0;
  v9 = 0;
  *(_OWORD *)attr = 0;
  if ( !a3 || !a2 || !ld || !a4 )
    return 3221225485LL;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, a3, a2);
  *a3 = 0;
  attr[0] = L"defaultNamingContext";
  attr[1] = 0;
  v10 = ldap_search_sW(ld, (const PWSTR)&base, 0, (const PWSTR)L"(objectClass=*)", attr, 0, &res);
  v11 = GmsapMapLdapErrorToNtStatus(v10);
  if ( v11 >= 0 )
  {
    entry = ldap_first_entry(ld, res);
    valuesW = ldap_get_valuesW(ld, entry, attr[0]);
    v34 = valuesW;
    ldap_msgfree(res);
    res = 0;
    v11 = GmsapConcatenate(0, (unsigned __int16 **)&Buffer, 3u, L"(sAMAccountName=", a2, L"$)");
    if ( v11 < 0 )
    {
LABEL_66:
      v9 = Buffer;
      goto LABEL_39;
    }
    v37 = 0;
    attr[0] = L"distinguishedName";
    attr[1] = L"objectClass";
    while ( 1 )
    {
      v9 = Buffer;
      v18 = ldap_search_sW(ld, *valuesW, 2u, (const PWSTR)Buffer, attr, 0, &res);
      v11 = GmsapMapLdapErrorToNtStatus(v18);
      if ( v11 < 0 )
        break;
      v16 = ldap_count_entries(ld, res);
      if ( v16 )
      {
        if ( v16 > 1 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_664bdc16998933377d7f42e86ad1a4df_Traceguids);
          v11 = -1073740796;
          goto LABEL_39;
        }
        v19 = ldap_first_entry(ld, res);
        v20 = v19;
        if ( v19 )
        {
          v22 = attr[1];
          *a4 = v4;
          v23 = ldap_get_valuesW(ld, v19, v22);
          v11 = -1073741788;
          v25 = v23;
          if ( v23 )
          {
            LODWORD(v26) = 0;
            if ( *v23 )
            {
              while ( (unsigned int)_o__wcsicmp(L"msDS-GroupManagedServiceAccount", v25[(unsigned int)v26]) )
              {
                v26 = (unsigned int)(v26 + 1);
                if ( !v25[v26] )
                  goto LABEL_50;
              }
              ldap_value_freeW(v25);
              v27 = ldap_get_valuesW(ld, v20, attr[0]);
              v25 = v27;
              if ( v27 && (v28 = *v27) != 0 )
              {
                if ( v27[1] )
                {
                  v11 = -1073740796;
                }
                else
                {
                  v29 = -1;
                  do
                    ++v29;
                  while ( v28[v29] );
                  v30 = v35;
                  v31 = 2 * v29 + 2;
                  if ( NetApiBufferAllocate(v31, v35) || !*v30 )
                  {
                    v11 = -1073741801;
                  }
                  else
                  {
                    memcpy_0(*v30, v28, v31);
                    v11 = 0;
                  }
                }
              }
              else
              {
                v11 = -1073741275;
                if ( !v27 )
                  goto LABEL_38;
              }
            }
            else
            {
LABEL_50:
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, v24, L"msDS-GroupManagedServiceAccount");
              }
            }
            ldap_value_freeW(v25);
          }
        }
        else
        {
          v11 = -1073741275;
        }
LABEL_38:
        valuesW = v34;
        goto LABEL_39;
      }
      if ( v4 || !*a4 )
      {
        v11 = -1073741275;
        goto LABEL_39;
      }
      if ( res )
      {
        ldap_msgfree(res);
        res = 0;
      }
      if ( v9 )
      {
        NetApiBufferFree(v9);
        Buffer = 0;
      }
      v11 = GmsapConcatenate(0, (unsigned __int16 **)&Buffer, 3u, L"(sAMAccountName=", a2, L")");
      if ( v11 < 0 )
        goto LABEL_66;
      v4 = 1;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, v17, a2);
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v14 = 29;
      goto LABEL_12;
    }
  }
  else
  {
    valuesW = 0;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v14 = 28;
LABEL_12:
      WPP_SF_(v13[2], v14, &WPP_664bdc16998933377d7f42e86ad1a4df_Traceguids);
    }
  }
LABEL_39:
  if ( res )
    ldap_msgfree(res);
  if ( v9 )
    NetApiBufferFree(v9);
  if ( valuesW )
    ldap_value_freeW(valuesW);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180006a38  push    rbp
0x180006a3a  push    rbx
0x180006a3b  push    rsi
0x180006a3c  push    rdi
0x180006a3d  push    r12
0x180006a3f  push    r13
0x180006a41  push    r14
0x180006a43  push    r15
0x180006a45  lea     rbp, [rsp-1Fh]
0x180006a4a  sub     rsp, 88h
0x180006a51  mov     rax, cs:__security_cookie
0x180006a58  xor     rax, rsp
0x180006a5b  mov     [rbp+57h+var_48], rax
0x180006a5f  xor     r15d, r15d
0x180006a62  xor     eax, eax
0x180006a64  mov     [rbp+57h+Buffer], r15
0x180006a68  mov     rbx, r8
0x180006a6b  mov     [rbp+57h+var_68], rbx
0x180006a6f  xorps   xmm0, xmm0
0x180006a72  mov     [rbp+57h+var_50], rax
0x180006a76  mov     r13, r9
0x180006a79  mov     [rbp+57h+var_80], r15
0x180006a7d  mov     rdi, rdx
0x180006a80  mov     r14, rcx
0x180006a83  mov     esi, r15d
0x180006a86  movups  xmmword ptr [rbp+57h+attr], xmm0
0x180006a8a  test    r8, r8
0x180006a8d  jz      loc_180006F3A
0x180006a93  test    rdx, rdx
0x180006a96  jz      loc_180006F3A
0x180006a9c  test    rcx, rcx
0x180006a9f  jz      loc_180006F3A
0x180006aa5  test    r9, r9
0x180006aa8  jz      loc_180006F3A
0x180006aae  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ab5  lea     rax, WPP_GLOBAL_Control
0x180006abc  cmp     rcx, rax
0x180006abf  jz      short loc_180006AD7
0x180006ac1  test    byte ptr [rcx+1Ch], 4
0x180006ac5  jz      short loc_180006AD7
0x180006ac7  mov     rcx, [rcx+10h]
0x180006acb  lea     edx, [r15+1Bh]
0x180006acf  mov     r9, rdi
0x180006ad2  call    WPP_SF_S
0x180006ad7  lea     rax, aDefaultnamingc; "defaultNamingContext"
0x180006ade  mov     [rbx], r15
0x180006ae1  mov     [rbp+57h+attr], rax
0x180006ae5  lea     r9, filter; "(objectClass=*)"
0x180006aec  lea     rax, [rbp+57h+var_80]
0x180006af0  mov     [rbp+57h+attr+8], r15
0x180006af4  mov     [rsp+0C0h+res], rax; res
0x180006af9  lea     rdx, base; base
0x180006b00  lea     rax, [rbp+57h+attr]
0x180006b04  mov     [rsp+0C0h+attrsonly], r15d; attrsonly
0x180006b09  xor     r8d, r8d; scope
0x180006b0c  mov     [rsp+0C0h+attrs], rax; attrs
0x180006b11  mov     rcx, r14; ld
0x180006b14  call    cs:__imp_ldap_search_sW
0x180006b1b  nop     dword ptr [rax+rax+00h]
0x180006b20  mov     ecx, eax
0x180006b22  call    GmsapMapLdapErrorToNtStatus
0x180006b27  mov     ebx, eax
0x180006b29  test    eax, eax
0x180006b2b  jns     short loc_180006B6B
0x180006b2d  mov     r12, r15
0x180006b30  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b37  lea     rax, WPP_GLOBAL_Control
0x180006b3e  cmp     rcx, rax
0x180006b41  jz      loc_180006DA5
0x180006b47  test    byte ptr [rcx+1Ch], 4
0x180006b4b  jz      loc_180006DA5
0x180006b51  mov     edx, 1Ch
0x180006b56  mov     rcx, [rcx+10h]
0x180006b5a  lea     r8, WPP_664bdc16998933377d7f42e86ad1a4df_Traceguids
0x180006b61  call    WPP_SF_
0x180006b66  jmp     loc_180006DA5
0x180006b6b  mov     rdx, [rbp+57h+var_80]; res
0x180006b6f  mov     rcx, r14; ld
0x180006b72  call    cs:__imp_ldap_first_entry
0x180006b79  nop     dword ptr [rax+rax+00h]
0x180006b7e  mov     r8, [rbp+57h+attr]; attr
0x180006b82  mov     rcx, r14; ld
0x180006b85  mov     rdx, rax; entry
0x180006b88  call    cs:__imp_ldap_get_valuesW
0x180006b8f  nop     dword ptr [rax+rax+00h]
0x180006b94  mov     rcx, [rbp+57h+var_80]; res
0x180006b98  mov     r12, rax
0x180006b9b  mov     [rbp+57h+var_70], rax
0x180006b9f  call    cs:__imp_ldap_msgfree
0x180006ba6  nop     dword ptr [rax+rax+00h]
0x180006bab  lea     rax, asc_1800095AC; "$)"
0x180006bb2  mov     [rbp+57h+var_80], r15
0x180006bb6  mov     qword ptr [rsp+0C0h+attrsonly], rax
0x180006bbb  lea     r9, aSamaccountname; "(sAMAccountName="
0x180006bc2  mov     r8d, 3; unsigned __int16
0x180006bc8  mov     [rsp+0C0h+attrs], rdi
0x180006bcd  lea     rdx, [rbp+57h+Buffer]; unsigned __int16 **
0x180006bd1  xor     ecx, ecx; int
0x180006bd3  call    ?GmsapConcatenate@@YAJHPEAPEAGGZZ; GmsapConcatenate(int,ushort * *,ushort,...)
0x180006bd8  mov     ebx, eax
0x180006bda  test    eax, eax
0x180006bdc  js      loc_180006F31
0x180006be2  lea     rax, aDistinguishedn; "distinguishedName"
0x180006be9  mov     [rbp+57h+var_50], rsi
0x180006bed  mov     [rbp+57h+attr], rax
0x180006bf1  lea     rax, aObjectclass_0; "objectClass"
0x180006bf8  mov     [rbp+57h+attr+8], rax
0x180006bfc  lea     rax, [rbp+57h+var_80]
0x180006c00  mov     [rsp+0C0h+res], rax
0x180006c05  mov     [rsp+0C0h+attrsonly], esi
0x180006c09  jmp     loc_180006CE3
0x180006c0e  mov     rdx, [rbp+57h+var_80]; res
0x180006c12  mov     rcx, r14; ld
0x180006c15  call    cs:__imp_ldap_count_entries
0x180006c1c  nop     dword ptr [rax+rax+00h]
0x180006c21  test    eax, eax
0x180006c23  jnz     loc_180006D47
0x180006c29  test    r15d, r15d
0x180006c2c  jnz     loc_180006D40
0x180006c32  xor     r15d, r15d
0x180006c35  cmp     [r13+0], r15d
0x180006c39  jz      loc_180006D40
0x180006c3f  mov     rcx, [rbp+57h+var_80]; res
0x180006c43  test    rcx, rcx
0x180006c46  jz      short loc_180006C58
0x180006c48  call    cs:__imp_ldap_msgfree
0x180006c4f  nop     dword ptr [rax+rax+00h]
0x180006c54  mov     [rbp+57h+var_80], r15
0x180006c58  test    rsi, rsi
0x180006c5b  jz      short loc_180006C70
0x180006c5d  mov     rcx, rsi; Buffer
0x180006c60  call    cs:__imp_NetApiBufferFree
0x180006c67  nop     dword ptr [rax+rax+00h]
0x180006c6c  mov     [rbp+57h+Buffer], r15
0x180006c70  lea     rax, asc_180009620; ")"
0x180006c77  mov     r8d, 3; unsigned __int16
0x180006c7d  mov     qword ptr [rsp+0C0h+attrsonly], rax
0x180006c82  lea     r9, aSamaccountname; "(sAMAccountName="
0x180006c89  lea     rdx, [rbp+57h+Buffer]; unsigned __int16 **
0x180006c8d  mov     [rsp+0C0h+attrs], rdi
0x180006c92  xor     ecx, ecx; int
0x180006c94  call    ?GmsapConcatenate@@YAJHPEAPEAGGZZ; GmsapConcatenate(int,ushort * *,ushort,...)
0x180006c99  mov     ebx, eax
0x180006c9b  test    eax, eax
0x180006c9d  js      loc_180006F31
0x180006ca3  mov     r15d, 1
0x180006ca9  mov     rcx, cs:WPP_GLOBAL_Control
0x180006cb0  lea     rax, WPP_GLOBAL_Control
0x180006cb7  cmp     rcx, rax
0x180006cba  jz      short loc_180006CD2
0x180006cbc  test    byte ptr [rcx+1Ch], 4
0x180006cc0  jz      short loc_180006CD2
0x180006cc2  mov     rcx, [rcx+10h]
0x180006cc6  lea     edx, [r15+1Dh]
0x180006cca  mov     r9, rdi
0x180006ccd  call    WPP_SF_S
0x180006cd2  lea     rax, [rbp+57h+var_80]
0x180006cd6  mov     [rsp+0C0h+res], rax; res
0x180006cdb  mov     [rsp+0C0h+attrsonly], 0; attrsonly
0x180006ce3  mov     rsi, [rbp+57h+Buffer]
0x180006ce7  lea     rax, [rbp+57h+attr]
0x180006ceb  mov     rdx, [r12]; base
0x180006cef  mov     r9, rsi; filter
0x180006cf2  mov     r8d, 2; scope
0x180006cf8  mov     [rsp+0C0h+attrs], rax; attrs
0x180006cfd  mov     rcx, r14; ld
0x180006d00  call    cs:__imp_ldap_search_sW
0x180006d07  nop     dword ptr [rax+rax+00h]
0x180006d0c  mov     ecx, eax
0x180006d0e  call    GmsapMapLdapErrorToNtStatus
0x180006d13  mov     ebx, eax
0x180006d15  test    eax, eax
0x180006d17  jns     loc_180006C0E
0x180006d1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d24  lea     rax, WPP_GLOBAL_Control
0x180006d2b  cmp     rcx, rax
0x180006d2e  jz      short loc_180006DA5
0x180006d30  test    byte ptr [rcx+1Ch], 4
0x180006d34  jz      short loc_180006DA5
0x180006d36  mov     edx, 1Dh
0x180006d3b  jmp     loc_180006B56
0x180006d40  mov     ebx, 0C0000225h
0x180006d45  jmp     short loc_180006DA5
0x180006d47  cmp     eax, 1
0x180006d4a  jbe     short loc_180006D81
0x180006d4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d53  lea     rax, WPP_GLOBAL_Control
0x180006d5a  cmp     rcx, rax
0x180006d5d  jz      short loc_180006D7A
0x180006d5f  test    byte ptr [rcx+1Ch], 4
0x180006d63  jz      short loc_180006D7A
0x180006d65  mov     rcx, [rcx+10h]
0x180006d69  lea     r8, WPP_664bdc16998933377d7f42e86ad1a4df_Traceguids
0x180006d70  mov     edx, 1Fh
0x180006d75  call    WPP_SF_
0x180006d7a  mov     ebx, 0C0000404h
0x180006d7f  jmp     short loc_180006DA5
0x180006d81  mov     rdx, [rbp+57h+var_80]; res
0x180006d85  mov     rcx, r14; ld
0x180006d88  call    cs:__imp_ldap_first_entry
0x180006d8f  nop     dword ptr [rax+rax+00h]
0x180006d94  mov     r12, rax
0x180006d97  test    rax, rax
0x180006d9a  jnz     short loc_180006DE9
0x180006d9c  mov     ebx, 0C0000225h
0x180006da1  mov     r12, [rbp+57h+var_70]
0x180006da5  mov     rcx, [rbp+57h+var_80]; res
0x180006da9  test    rcx, rcx
0x180006dac  jz      short loc_180006DBA
0x180006dae  call    cs:__imp_ldap_msgfree
0x180006db5  nop     dword ptr [rax+rax+00h]
0x180006dba  test    rsi, rsi
0x180006dbd  jz      short loc_180006DCE
0x180006dbf  mov     rcx, rsi; Buffer
0x180006dc2  call    cs:__imp_NetApiBufferFree
0x180006dc9  nop     dword ptr [rax+rax+00h]
0x180006dce  test    r12, r12
0x180006dd1  jz      short loc_180006DE2
0x180006dd3  mov     rcx, r12; vals
0x180006dd6  call    cs:__imp_ldap_value_freeW
0x180006ddd  nop     dword ptr [rax+rax+00h]
0x180006de2  mov     eax, ebx
0x180006de4  jmp     loc_180006F3F
0x180006de9  mov     r8, [rbp+57h+attr+8]; attr
0x180006ded  mov     rdx, r12; entry
0x180006df0  mov     rcx, r14; ld
0x180006df3  mov     [r13+0], r15d
0x180006df7  call    cs:__imp_ldap_get_valuesW
0x180006dfe  nop     dword ptr [rax+rax+00h]
0x180006e03  xor     r13d, r13d
0x180006e06  mov     ebx, 0C0000024h
0x180006e0b  mov     rdi, rax
0x180006e0e  test    rax, rax
0x180006e11  jz      short loc_180006DA1
0x180006e13  mov     r15d, r13d
0x180006e16  cmp     [rax], r13
0x180006e19  jz      short loc_180006E42
0x180006e1b  mov     edx, r15d
0x180006e1e  lea     rcx, aMsdsGroupmanag; "msDS-GroupManagedServiceAccount"
0x180006e25  mov     rdx, [rdi+rdx*8]
0x180006e29  call    cs:__imp__o__wcsicmp
0x180006e30  nop     dword ptr [rax+rax+00h]
0x180006e35  test    eax, eax
0x180006e37  jz      short loc_180006E84
0x180006e39  inc     r15d
0x180006e3c  cmp     [rdi+r15*8], r13
0x180006e40  jnz     short loc_180006E1B
0x180006e42  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e49  lea     rax, WPP_GLOBAL_Control
0x180006e50  cmp     rcx, rax
0x180006e53  jz      short loc_180006E70
0x180006e55  test    byte ptr [rcx+1Ch], 4
0x180006e59  jz      short loc_180006E70
0x180006e5b  mov     rcx, [rcx+10h]
0x180006e5f  lea     r9, aMsdsGroupmanag; "msDS-GroupManagedServiceAccount"
0x180006e66  mov     edx, 20h ; ' '
0x180006e6b  call    WPP_SF_S
0x180006e70  mov     rcx, rdi; vals
0x180006e73  call    cs:__imp_ldap_value_freeW
0x180006e7a  nop     dword ptr [rax+rax+00h]
0x180006e7f  jmp     loc_180006DA1
0x180006e84  mov     rcx, rdi; vals
0x180006e87  call    cs:__imp_ldap_value_freeW
0x180006e8e  nop     dword ptr [rax+rax+00h]
0x180006e93  mov     r8, [rbp+57h+attr]; attr
0x180006e97  mov     rdx, r12; entry
0x180006e9a  mov     rcx, r14; ld
0x180006e9d  call    cs:__imp_ldap_get_valuesW
0x180006ea4  nop     dword ptr [rax+rax+00h]
0x180006ea9  xor     r12d, r12d
0x180006eac  mov     rdi, rax
0x180006eaf  test    rax, rax
0x180006eb2  jz      short loc_180006F1E
0x180006eb4  mov     rbx, [rax]
0x180006eb7  test    rbx, rbx
0x180006eba  jz      short loc_180006F1E
0x180006ebc  cmp     [rax+8], r12
0x180006ec0  jz      short loc_180006EC9
0x180006ec2  mov     ebx, 0C0000404h
0x180006ec7  jmp     short loc_180006E70
0x180006ec9  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006ecd  inc     rax
0x180006ed0  cmp     [rbx+rax*2], r12w
0x180006ed5  jnz     short loc_180006ECD
0x180006ed7  mov     r15, [rbp+57h+var_68]
0x180006edb  lea     r14d, ds:2[rax*2]
0x180006ee3  mov     rdx, r15; Buffer
0x180006ee6  mov     ecx, r14d; ByteCount
0x180006ee9  call    cs:__imp_NetApiBufferAllocate
0x180006ef0  nop     dword ptr [rax+rax+00h]
0x180006ef5  test    eax, eax
0x180006ef7  jnz     short loc_180006F14
0x180006ef9  mov     rcx, [r15]; void *
0x180006efc  test    rcx, rcx
0x180006eff  jz      short loc_180006F14
0x180006f01  mov     r8d, r14d; Size
0x180006f04  mov     rdx, rbx; Src
0x180006f07  call    memcpy_0
0x180006f0c  mov     ebx, r12d
0x180006f0f  jmp     loc_180006E70
  ... truncated ...
```
