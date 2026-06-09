# CAOIDRetrieveEnterpriseRootWithConfig(ldap *,ushort *,ulong,ushort * *)

- ea: `0x18002ab94`
- end: `0x18002b26d`
- name: `?CAOIDRetrieveEnterpriseRootWithConfig@@YAJPEAUldap@@PEAGKPEAPEAG@Z`
- size: `1753`
- prototype: `__int64 __fastcall(LDAP *ld, unsigned __int16 *, __int64, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002a668`
- `0x18002bd08`

## callees

- `0x180005944`
- `0x180005f00`
- `0x180008400`
- `0x180008420`
- `0x18000e130`
- `0x180011158`
- `0x180011600`
- `0x18002a5d0`
- `0x18002aa7c`
- `0x18002ab94`
- `0x1800382c0`

## import_xrefs

- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002acc6`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002acec`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002ad3f`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002ad7b`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002ae16`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002af72`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002afd2`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002b029`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002b181`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002b1af`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002b1dd`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002acc6`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002acec`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002ad3f`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002ad7b`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002ae16`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002af72`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002afd2`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002b029`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002b181`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002b1af`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002b1dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002aef9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b0fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002aef9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b0fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002af68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b172`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002af68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b172`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002af41`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b001`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b14b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002af41`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b001`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b14b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b1ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b1ff`
- `WLDAP32!__imp_ldap_first_entry` at `0x18002ae3e`
- `WLDAP32!__imp_ldap_first_entry` at `0x18002ae3e`
- `WLDAP32!__imp_ldap_count_entries` at `0x18002ae27`
- `WLDAP32!__imp_ldap_count_entries` at `0x18002ae27`
- `WLDAP32!__imp_ldap_msgfree` at `0x18002b235`
- `WLDAP32!__imp_ldap_msgfree` at `0x18002b235`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18002b212`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18002b212`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18002ae5d`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18002ae5d`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x18002af8b`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x18002af8b`
- `WLDAP32!__imp_ldap_modify_ext_sW` at `0x18002b0e2`
- `WLDAP32!__imp_ldap_modify_ext_sW` at `0x18002b0e2`
- `WLDAP32!__imp_ldap_search_stW` at `0x18002ade9`
- `WLDAP32!__imp_ldap_search_stW` at `0x18002ade9`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18002b220`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18002b220`

## string_xrefs

- `0x18002ae50`: `msPKI-Cert-Template-OID`
- `0x18002b08e`: `msPKI-Cert-Template-OID`
- `0x18002ad87`: `CN=OID,CN=Public Key Services,CN=Services,`

## pseudocode

```c
__int64 __fastcall CAOIDRetrieveEnterpriseRootWithConfig(
        LDAP *ld,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 **a4)
{
  unsigned int v6; // esi
  unsigned __int16 *v7; // r12
  void (*v8)(unsigned int, struct _EXCEPTION_POINTERS *); // rbx
  unsigned __int64 v9; // r14
  __int64 v10; // rax
  unsigned __int64 v11; // rsi
  WCHAR *v12; // rax
  ULONG v13; // eax
  unsigned int v14; // r9d
  unsigned int v15; // r9d
  LDAPMessage *entry; // rax
  LDAPMessage *v17; // rsi
  PWCHAR *valuesW; // rax
  unsigned __int16 **v19; // r12
  PWCHAR v20; // rax
  int v21; // ecx
  const unsigned __int16 *v22; // r13
  HLOCAL v23; // rax
  struct berval **values_lenW; // rax
  unsigned int v25; // r9d
  int v26; // eax
  __int64 v27; // rax
  const unsigned __int16 *v28; // rsi
  unsigned __int16 *v29; // rax
  const unsigned __int16 *v30; // r15
  HLOCAL v31; // rax
  unsigned __int16 **attrs; // [rsp+20h] [rbp-168h]
  SIZE_T uBytes; // [rsp+48h] [rbp-140h] BYREF
  PWSTR dn; // [rsp+50h] [rbp-138h]
  PLDAPMessage res; // [rsp+58h] [rbp-130h] BYREF
  int v37; // [rsp+60h] [rbp-128h]
  BOOL v38; // [rsp+64h] [rbp-124h]
  struct l_timeval timeout; // [rsp+68h] [rbp-120h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-118h] BYREF
  PWCHAR v41; // [rsp+78h] [rbp-110h]
  SIZE_T v42; // [rsp+80h] [rbp-108h] BYREF
  PWCHAR *v43; // [rsp+88h] [rbp-100h]
  struct berval **vals; // [rsp+90h] [rbp-F8h]
  _QWORD v45[3]; // [rsp+98h] [rbp-F0h] BYREF
  char v46; // [rsp+B0h] [rbp-D8h]
  int v47; // [rsp+B1h] [rbp-D7h]
  __int16 v48; // [rsp+B5h] [rbp-D3h]
  char v49; // [rsp+B7h] [rbp-D1h]
  _QWORD v50[3]; // [rsp+B8h] [rbp-D0h] BYREF
  char v51; // [rsp+D0h] [rbp-B8h]
  int v52; // [rsp+D1h] [rbp-B7h]
  __int16 v53; // [rsp+D5h] [rbp-B3h]
  char v54; // [rsp+D7h] [rbp-B1h]
  __int128 v55; // [rsp+D8h] [rbp-B0h] BYREF
  LDAPModW *mods[2]; // [rsp+E8h] [rbp-A0h] BYREF
  __int128 v57; // [rsp+F8h] [rbp-90h] BYREF
  __int128 *v58; // [rsp+108h] [rbp-80h]
  void (*v59)(unsigned int, struct _EXCEPTION_POINTERS *); // [rsp+110h] [rbp-78h]
  __int64 v60; // [rsp+118h] [rbp-70h]
  PLDAPControlW ServerControls[3]; // [rsp+128h] [rbp-60h] BYREF
  int v62; // [rsp+140h] [rbp-48h] BYREF
  char v63; // [rsp+144h] [rbp-44h]

  uBytes = (SIZE_T)a2;
  v6 = -2147024809;
  timeout = 0;
  *(_OWORD *)mods = 0;
  v57 = 0;
  v58 = 0;
  v55 = 0;
  v62 = 16909104;
  v63 = 4;
  v45[0] = L"1.2.840.113556.1.4.801";
  v45[1] = 5;
  v45[2] = &v62;
  v46 = 1;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50[0] = L"1.2.840.113556.1.4.1413";
  v50[1] = 0;
  v50[2] = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  ServerControls[0] = (PLDAPControlW)v45;
  ServerControls[1] = (PLDAPControlW)v50;
  ServerControls[2] = 0;
  v7 = 0;
  dn = 0;
  res = 0;
  v43 = 0;
  vals = 0;
  hMem = 0;
  v8 = _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))SeTranslator);
  v59 = v8;
  if ( a4 )
  {
    *a4 = 0;
    v9 = -1;
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)(uBytes + 2 * v10) );
    v11 = v10 + 43;
    v60 = v10 + 43;
    if ( (unsigned __int64)(v10 + 43) <= 0x10000 )
    {
      v12 = CertAllocStringLen(0, (int)v10 + 42);
      v7 = v12;
      dn = v12;
      if ( v12 )
      {
        StringCchCopyW(v12, v11, L"CN=OID,CN=Public Key Services,CN=Services,");
        StringCchCatW(v7, v11, (const unsigned __int16 *)uBytes);
        timeout.tv_sec = 120;
        timeout.tv_usec = 0;
        v13 = ldap_search_stW(
                ld,
                v7,
                0,
                (const PWSTR)L"(&(CN=OID)(objectCategory=msPKI-Enterprise-Oid))",
                &g_awszOIDContainerAttrs,
                0,
                &timeout,
                &res);
        if ( v13 )
        {
          v6 = myHLdapError3(ld, v13, 0, v14, attrs);
          CSPrintErrorLineFile(0x3420336u, v6);
          _set_se_translator(v8);
        }
        else if ( ldap_count_entries(ld, res) == 1 && (entry = ldap_first_entry(ld, res), (v17 = entry) != 0) )
        {
          valuesW = ldap_get_valuesW(ld, entry, (const PWSTR)L"msPKI-Cert-Template-OID");
          v19 = valuesW;
          v43 = valuesW;
          if ( !valuesW )
            goto LABEL_32;
          v20 = *valuesW;
          if ( !v20 )
            goto LABEL_32;
          v38 = 0;
          v21 = 0;
          v37 = 0;
          v41 = v20;
          while ( *v20 )
          {
            if ( *v20 == 46 )
              v37 = ++v21;
            v41 = ++v20;
          }
          v38 = v21 == 14;
          if ( v21 == 14 )
          {
            v6 = CAOIDAllocAndCopy(*v19, a4);
            if ( !v6 && g_fOidURL )
            {
              EnterCriticalSection(&g_csOidURL);
              v22 = *a4;
              if ( v22 )
              {
                uBytes = 0;
                do
                  ++v9;
                while ( v22[v9] );
                if ( v9 + 1 >= v9 && (int)ULongLongMult(v9 + 1, 2u, &uBytes) >= 0 )
                {
                  v23 = LocalAlloc(0x40u, uBytes);
                  g_pwszEnterpriseRootOID = v23;
                  if ( v23 )
                    StringCchCopyW((unsigned __int16 *)v23, v9 + 1, v22);
                }
              }
              LeaveCriticalSection(&g_csOidURL);
            }
            _set_se_translator(v8);
          }
          else
          {
LABEL_32:
            values_lenW = ldap_get_values_lenW(ld, v17, (const PWSTR)L"objectGUID");
            vals = values_lenW;
            if ( values_lenW && *values_lenW )
            {
              v26 = CAOIDMapGUIDToOID(*values_lenW, (unsigned __int16 **)&hMem);
              v6 = v26;
              if ( v26 )
              {
                CSPrintErrorLineFile(0x3710336u, v26);
                _set_se_translator(v8);
              }
              else
              {
                v27 = -1;
                v28 = (const unsigned __int16 *)hMem;
                do
                  ++v27;
                while ( *((_WORD *)hMem + v27) );
                uBytes = v27 + 22;
                v29 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * (v27 + 22));
                *a4 = v29;
                if ( v29 )
                {
                  StringCchCopyW(v29, uBytes, L"1.3.6.1.4.1.311.21.8");
                  StringCchCatW(*a4, uBytes, L".");
                  StringCchCatW(*a4, uBytes, v28);
                  v55 = (unsigned __int64)*a4;
                  LODWORD(v57) = 2;
                  *((_QWORD *)&v57 + 1) = L"msPKI-Cert-Template-OID";
                  v58 = &v55;
                  mods[0] = (LDAPModW *)&v57;
                  mods[1] = 0;
                  ldap_modify_ext_sW(ld, dn, mods, ServerControls, 0);
                  if ( g_fOidURL )
                  {
                    EnterCriticalSection(&g_csOidURL);
                    v30 = *a4;
                    if ( *a4 )
                    {
                      v42 = 0;
                      do
                        ++v9;
                      while ( v30[v9] );
                      if ( v9 + 1 >= v9 && (int)ULongLongMult(v9 + 1, 2u, &v42) >= 0 )
                      {
                        v31 = LocalAlloc(0x40u, v42);
                        g_pwszEnterpriseRootOID = v31;
                        if ( v31 )
                          StringCchCopyW((unsigned __int16 *)v31, v9 + 1, v30);
                      }
                    }
                    LeaveCriticalSection(&g_csOidURL);
                  }
                  v6 = 0;
                  _set_se_translator(v8);
                }
                else
                {
                  v6 = -2147024882;
                  CSPrintErrorLineFile(0x37A0336u, -2147024882);
                  _set_se_translator(v8);
                }
              }
            }
            else
            {
              v6 = myHLdapError3(ld, 0x10u, 0, v25, attrs);
              CSPrintErrorLineFile(0x36D0336u, v6);
              _set_se_translator(v8);
            }
          }
          if ( hMem )
            LocalFree(hMem);
          if ( vals )
            ldap_value_free_len(vals);
          if ( v19 )
            ldap_value_freeW(v19);
          v7 = dn;
        }
        else
        {
          v6 = myHLdapError3(ld, 0x20u, 0, v15, attrs);
          CSPrintErrorLineFile(0x34C0336u, v6);
          _set_se_translator(v8);
        }
      }
      else
      {
        v6 = -2147024882;
        CSPrintErrorLineFile(0x32C0336u, -2147024882);
        _set_se_translator(v8);
      }
    }
    else
    {
      v6 = -2147024362;
      CSPrintErrorLineFile(0x3260336u, -2147024362);
      _set_se_translator(v8);
    }
  }
  else
  {
    CSPrintErrorLineFile(0x31D0336u, -2147024809);
    _set_se_translator(v8);
  }
  if ( res )
    ldap_msgfree(res);
  if ( v7 )
    CertFreeString(v7);
  return v6;
}

```

## disassembly

```asm
0x18002ab94  mov     r11, rsp
0x18002ab97  push    rbx
0x18002ab98  push    rsi
0x18002ab99  push    rdi
0x18002ab9a  push    r12
0x18002ab9c  push    r13
0x18002ab9e  push    r14
0x18002aba0  push    r15
0x18002aba2  sub     rsp, 150h
0x18002aba9  mov     rax, cs:__security_cookie
0x18002abb0  xor     rax, rsp
0x18002abb3  mov     [rsp+188h+var_40], rax
0x18002abbb  mov     r13, r9
0x18002abbe  mov     [rsp+188h+uBytes], rdx
0x18002abc3  mov     r15, rcx
0x18002abc6  mov     esi, 80070057h
0x18002abcb  xor     edi, edi
0x18002abcd  mov     qword ptr [rsp+188h+var_120.tv_sec], rdi
0x18002abd2  xorps   xmm0, xmm0
0x18002abd5  movups  xmmword ptr [rsp+188h+mods], xmm0
0x18002abdd  xorps   xmm1, xmm1
0x18002abe0  xor     eax, eax
0x18002abe2  movups  [rsp+188h+var_90], xmm1
0x18002abea  mov     [r11-80h], rax
0x18002abee  movups  [rsp+188h+var_B0], xmm0
0x18002abf6  mov     dword ptr [r11-48h], 1020330h
0x18002abfe  lea     ecx, [rdi+1]
0x18002ac01  mov     byte ptr [r11-44h], 4
0x18002ac06  lea     rax, a12840113556148; "1.2.840.113556.1.4.801"
0x18002ac0d  mov     [r11-0F0h], rax
0x18002ac14  mov     qword ptr [r11-0E8h], 5
0x18002ac1f  lea     rax, [r11-48h]
0x18002ac23  mov     [r11-0E0h], rax
0x18002ac2a  mov     [rsp+188h+var_D8], cl
0x18002ac31  xor     eax, eax
0x18002ac33  mov     [rsp+188h+var_D7], eax
0x18002ac3a  mov     [rsp+188h+var_D3], ax
0x18002ac42  mov     [rsp+188h+var_D1], al
0x18002ac49  lea     rax, a12840113556141; "1.2.840.113556.1.4.1413"
0x18002ac50  mov     [r11-0D0h], rax
0x18002ac57  mov     [r11-0C8h], rdi
0x18002ac5e  mov     [r11-0C0h], rdi
0x18002ac65  mov     [rsp+188h+var_B8], dil
0x18002ac6d  xor     eax, eax
0x18002ac6f  mov     [rsp+188h+var_B7], eax
0x18002ac76  mov     [rsp+188h+var_B3], ax
0x18002ac7e  mov     [rsp+188h+var_B1], al
0x18002ac85  lea     rax, [r11-0F0h]
0x18002ac8c  mov     [r11-60h], rax
0x18002ac90  lea     rax, [r11-0D0h]
0x18002ac97  mov     [r11-58h], rax
0x18002ac9b  mov     [r11-50h], rdi
0x18002ac9f  mov     r12d, edi
0x18002aca2  mov     [rsp+188h+dn], rdi
0x18002aca7  mov     [rsp+188h+var_130], rdi
0x18002acac  mov     [r11-100h], rdi
0x18002acb3  mov     [r11-0F8h], rdi
0x18002acba  mov     [rsp+188h+hMem], rdi
0x18002acbf  lea     rcx, ?SeTranslator@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTranslator(uint,_EXCEPTION_POINTERS *)
0x18002acc6  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18002accc  mov     rbx, rax
0x18002accf  mov     [rsp+188h+var_78], rax
0x18002acd7  test    r13, r13
0x18002acda  jnz     short loc_18002ACF8
0x18002acdc  mov     edx, esi; int
0x18002acde  mov     ecx, 31D0336h; unsigned int
0x18002ace3  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002ace8  nop
0x18002ace9  mov     rcx, rbx
0x18002acec  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18002acf2  nop
0x18002acf3  jmp     loc_18002B22B
0x18002acf8  mov     [r13+0], rdi
0x18002acfc  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002ad00  mov     rax, r14
0x18002ad03  mov     rcx, [rsp+188h+uBytes]
0x18002ad08  inc     rax
0x18002ad0b  cmp     [rcx+rax*2], di
0x18002ad0f  jnz     short loc_18002AD08
0x18002ad11  lea     rsi, [rax+2Bh]
0x18002ad15  mov     [rsp+188h+var_70], rsi
0x18002ad1d  cmp     rsi, 10000h
0x18002ad24  jbe     short loc_18002AD4B
0x18002ad26  mov     esi, 80070216h
0x18002ad2b  mov     [rsp+188h+var_148], esi
0x18002ad2f  mov     edx, esi; int
0x18002ad31  mov     ecx, 3260336h; unsigned int
0x18002ad36  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002ad3b  nop
0x18002ad3c  mov     rcx, rbx
0x18002ad3f  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18002ad45  nop
0x18002ad46  jmp     loc_18002B22B
0x18002ad4b  lea     edx, [rsi-1]; unsigned int
0x18002ad4e  xor     ecx, ecx; Src
0x18002ad50  call    ?CertAllocStringLen@@YAPEAGPEBGI@Z; CertAllocStringLen(ushort const *,uint)
0x18002ad55  mov     r12, rax
0x18002ad58  mov     [rsp+188h+dn], rax
0x18002ad5d  test    rax, rax
0x18002ad60  jnz     short loc_18002AD87
0x18002ad62  mov     edx, 8007000Eh; int
0x18002ad67  mov     esi, edx
0x18002ad69  mov     [rsp+188h+var_148], edx
0x18002ad6d  mov     ecx, 32C0336h; unsigned int
0x18002ad72  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002ad77  nop
0x18002ad78  mov     rcx, rbx
0x18002ad7b  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18002ad81  nop
0x18002ad82  jmp     loc_18002B22B
0x18002ad87  lea     r8, aCnOidCnPublicK; "CN=OID,CN=Public Key Services,CN=Servic"...
0x18002ad8e  mov     rdx, rsi; unsigned __int64
0x18002ad91  mov     rcx, r12; unsigned __int16 *
0x18002ad94  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002ad99  mov     r8, [rsp+188h+uBytes]; unsigned __int16 *
0x18002ad9e  mov     rdx, rsi; unsigned __int64
0x18002ada1  mov     rcx, r12; unsigned __int16 *
0x18002ada4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002ada9  mov     [rsp+188h+var_120.tv_sec], 78h ; 'x'
0x18002adb1  mov     [rsp+188h+var_120.tv_usec], edi
0x18002adb5  lea     rax, [rsp+188h+var_130]
0x18002adba  mov     [rsp+188h+res], rax; res
0x18002adbf  lea     rax, [rsp+188h+var_120]
0x18002adc4  mov     [rsp+188h+timeout], rax; timeout
0x18002adc9  mov     [rsp+188h+attrsonly], edi; attrsonly
0x18002adcd  lea     rax, ?g_awszOIDContainerAttrs@@3PAPEAGA; ushort * near * g_awszOIDContainerAttrs
0x18002add4  mov     [rsp+188h+attrs], rax; unsigned __int16 **
0x18002add9  lea     r9, aCnOidObjectcat; "(&(CN=OID)(objectCategory=msPKI-Enterpr"...
0x18002ade0  xor     r8d, r8d; scope
0x18002ade3  mov     rdx, r12; base
0x18002ade6  mov     rcx, r15; ld
0x18002ade9  call    cs:__imp_ldap_search_stW
0x18002adef  mov     rcx, r15; ld
0x18002adf2  test    eax, eax
0x18002adf4  jz      short loc_18002AE22
0x18002adf6  xor     r8d, r8d; unsigned int
0x18002adf9  mov     edx, eax; unsigned int
0x18002adfb  call    ?myHLdapError3@@YAJPEAUldap@@KKKPEAPEAG@Z; myHLdapError3(ldap *,ulong,ulong,ulong,ushort * *)
0x18002ae00  mov     esi, eax
0x18002ae02  mov     [rsp+188h+var_148], eax
0x18002ae06  mov     edx, eax; int
0x18002ae08  mov     ecx, 3420336h; unsigned int
0x18002ae0d  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002ae12  nop
0x18002ae13  mov     rcx, rbx
0x18002ae16  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18002ae1c  nop
0x18002ae1d  jmp     loc_18002B22B
0x18002ae22  mov     rdx, [rsp+188h+var_130]; res
0x18002ae27  call    cs:__imp_ldap_count_entries
0x18002ae2d  cmp     eax, 1
0x18002ae30  jnz     loc_18002B1B8
0x18002ae36  mov     rdx, [rsp+188h+var_130]; res
0x18002ae3b  mov     rcx, r15; ld
0x18002ae3e  call    cs:__imp_ldap_first_entry
0x18002ae44  mov     rsi, rax
0x18002ae47  test    rax, rax
0x18002ae4a  jz      loc_18002B1B8
0x18002ae50  lea     r8, aMspkiCertTempl; "msPKI-Cert-Template-OID"
0x18002ae57  mov     rdx, rax; entry
0x18002ae5a  mov     rcx, r15; ld
0x18002ae5d  call    cs:__imp_ldap_get_valuesW
0x18002ae63  mov     r12, rax
0x18002ae66  mov     [rsp+188h+var_100], rax
0x18002ae6e  test    rax, rax
0x18002ae71  jz      loc_18002AF7E
0x18002ae77  mov     rax, [rax]
0x18002ae7a  test    rax, rax
0x18002ae7d  jz      loc_18002AF7E
0x18002ae83  mov     [rsp+188h+var_124], edi
0x18002ae87  mov     [rsp+188h+var_110], rdi
0x18002ae8c  mov     ecx, edi
0x18002ae8e  mov     [rsp+188h+var_128], ecx
0x18002ae92  mov     [rsp+188h+var_110], rax
0x18002ae97  cmp     di, [rax]
0x18002ae9a  jz      short loc_18002AEB7
0x18002ae9c  mov     edx, 2Eh ; '.'
0x18002aea1  cmp     dx, [rax]
0x18002aea4  jnz     short loc_18002AEAC
0x18002aea6  inc     ecx
0x18002aea8  mov     [rsp+188h+var_128], ecx
0x18002aeac  add     rax, 2
0x18002aeb0  mov     [rsp+188h+var_110], rax
0x18002aeb5  jmp     short loc_18002AE97
0x18002aeb7  mov     eax, edi
0x18002aeb9  cmp     ecx, 0Eh
0x18002aebc  mov     ecx, 1
0x18002aec1  cmovz   eax, ecx
0x18002aec4  mov     [rsp+188h+var_124], eax
0x18002aec8  test    eax, eax
0x18002aeca  jz      loc_18002AF7E
0x18002aed0  mov     rdx, r13; unsigned __int16 **
0x18002aed3  mov     rcx, [r12]; unsigned __int16 *
0x18002aed7  call    ?CAOIDAllocAndCopy@@YAJPEAGPEAPEAG@Z; CAOIDAllocAndCopy(ushort *,ushort * *)
0x18002aedc  mov     esi, eax
0x18002aede  mov     [rsp+188h+var_148], eax
0x18002aee2  test    eax, eax
0x18002aee4  jnz     loc_18002AF6F
0x18002aeea  cmp     cs:?g_fOidURL@@3HA, edi; int g_fOidURL
0x18002aef0  jz      short loc_18002AF6F
0x18002aef2  lea     rcx, ?g_csOidURL@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002aef9  call    cs:__imp_EnterCriticalSection
0x18002aeff  mov     r13, [r13+0]
0x18002af03  test    r13, r13
0x18002af06  jz      short loc_18002AF61
0x18002af08  mov     [rsp+188h+uBytes], rdi
0x18002af0d  inc     r14
0x18002af10  cmp     [r13+r14*2+0], di
0x18002af16  jnz     short loc_18002AF0D
0x18002af18  lea     r15, [r14+1]
0x18002af1c  cmp     r15, r14
0x18002af1f  jb      short loc_18002AF61
0x18002af21  lea     r8, [rsp+188h+uBytes]; unsigned __int64 *
0x18002af26  mov     edx, 2; unsigned __int64
0x18002af2b  mov     rcx, r15; unsigned __int64
0x18002af2e  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18002af33  test    eax, eax
0x18002af35  js      short loc_18002AF61
0x18002af37  mov     rdx, [rsp+188h+uBytes]; uBytes
0x18002af3c  mov     ecx, 40h ; '@'; uFlags
0x18002af41  call    cs:__imp_LocalAlloc
0x18002af47  mov     cs:?g_pwszEnterpriseRootOID@@3PEAGEA, rax; ushort * g_pwszEnterpriseRootOID
0x18002af4e  test    rax, rax
0x18002af51  jz      short loc_18002AF61
0x18002af53  mov     r8, r13; unsigned __int16 *
0x18002af56  mov     rdx, r15; unsigned __int64
0x18002af59  mov     rcx, rax; unsigned __int16 *
0x18002af5c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002af61  lea     rcx, ?g_csOidURL@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002af68  call    cs:__imp_LeaveCriticalSection
0x18002af6e  nop
0x18002af6f  mov     rcx, rbx
0x18002af72  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18002af78  nop
0x18002af79  jmp     loc_18002B1F2
0x18002af7e  lea     r8, aObjectguid; "objectGUID"
0x18002af85  mov     rdx, rsi; Message
0x18002af88  mov     rcx, r15; ExternalHandle
0x18002af8b  call    cs:__imp_ldap_get_values_lenW
0x18002af91  mov     [rsp+188h+vals], rax
0x18002af99  test    rax, rax
0x18002af9c  jz      loc_18002B18A
0x18002afa2  cmp     [rax], rdi
0x18002afa5  jz      loc_18002B18A
0x18002afab  lea     rdx, [rsp+188h+hMem]; unsigned __int16 **
0x18002afb0  mov     rcx, [rax]; struct berval *
0x18002afb3  call    ?CAOIDMapGUIDToOID@@YAJPEAUberval@@PEAPEAG@Z; CAOIDMapGUIDToOID(berval *,ushort * *)
0x18002afb8  mov     esi, eax
0x18002afba  mov     [rsp+188h+var_148], eax
0x18002afbe  test    eax, eax
0x18002afc0  jz      short loc_18002AFDE
0x18002afc2  mov     edx, eax; int
0x18002afc4  mov     ecx, 3710336h; unsigned int
0x18002afc9  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002afce  nop
0x18002afcf  mov     rcx, rbx
0x18002afd2  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18002afd8  nop
0x18002afd9  jmp     loc_18002B1F2
0x18002afde  mov     rax, r14
0x18002afe1  mov     rsi, [rsp+188h+hMem]
0x18002afe6  inc     rax
0x18002afe9  cmp     [rsi+rax*2], di
0x18002afed  jnz     short loc_18002AFE6
0x18002afef  add     rax, 16h
0x18002aff3  mov     [rsp+188h+uBytes], rax
0x18002aff8  lea     rdx, [rax+rax]; uBytes
0x18002affc  mov     ecx, 40h ; '@'; uFlags
0x18002b001  call    cs:__imp_LocalAlloc
0x18002b007  mov     [r13+0], rax
0x18002b00b  test    rax, rax
0x18002b00e  jnz     short loc_18002B035
0x18002b010  mov     edx, 8007000Eh; int
0x18002b015  mov     esi, edx
0x18002b017  mov     [rsp+188h+var_148], edx
0x18002b01b  mov     ecx, 37A0336h; unsigned int
0x18002b020  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002b025  nop
0x18002b026  mov     rcx, rbx
0x18002b029  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18002b02f  nop
0x18002b030  jmp     loc_18002B1F2
0x18002b035  lea     r8, a136141311218; "1.3.6.1.4.1.311.21.8"
0x18002b03c  mov     rdx, [rsp+188h+uBytes]; unsigned __int64
0x18002b041  mov     rcx, rax; unsigned __int16 *
0x18002b044  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002b049  lea     r8, asc_180063614; "."
0x18002b050  mov     rdx, [rsp+188h+uBytes]; unsigned __int64
0x18002b055  mov     rcx, [r13+0]; unsigned __int16 *
0x18002b059  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002b05e  mov     r8, rsi; unsigned __int16 *
0x18002b061  mov     rdx, [rsp+188h+uBytes]; unsigned __int64
0x18002b066  mov     rcx, [r13+0]; unsigned __int16 *
0x18002b06a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002b06f  mov     rax, [r13+0]
0x18002b073  mov     qword ptr [rsp+188h+var_B0], rax
0x18002b07b  mov     qword ptr [rsp+188h+var_B0+8], rdi
0x18002b083  mov     dword ptr [rsp+188h+var_90], 2
0x18002b08e  lea     rax, aMspkiCertTempl; "msPKI-Cert-Template-OID"
0x18002b095  mov     qword ptr [rsp+188h+var_90+8], rax
  ... truncated ...
```
