# CCertTypeInfo::_LoadFromDSEntry(ldap *,ldapmsg *)

- ea: `0x18000c160`
- end: `0x18000ce7e`
- name: `?_LoadFromDSEntry@CCertTypeInfo@@IEAAJPEAUldap@@PEAUldapmsg@@@Z`
- size: `3358`
- prototype: `__int64 __fastcall(struct CCAProperty **this, struct ldap *, struct ldapmsg *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b3f0`

## callees

- `0x180008610`
- `0x18000c160`
- `0x18000ce90`
- `0x18000cfc0`
- `0x18000fac0`
- `0x1800113e0`
- `0x180011600`
- `0x180013a86`
- `0x180014fac`
- `0x180038262`
- `0x180038286`

## import_xrefs

- `msvcrt!_wtoi` at `0x18000c92b`
- `msvcrt!_wtoi` at `0x18000c92b`
- `msvcrt!_wtol` at `0x18000c7e5`
- `msvcrt!_wtol` at `0x18000c826`
- `msvcrt!_wtol` at `0x18000c867`
- `msvcrt!_wtol` at `0x18000cc68`
- `msvcrt!_wtol` at `0x18000c7e5`
- `msvcrt!_wtol` at `0x18000c826`
- `msvcrt!_wtol` at `0x18000c867`
- `msvcrt!_wtol` at `0x18000cc68`
- `msvcrt!wcstol` at `0x18000c4e7`
- `msvcrt!wcstol` at `0x18000c4e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c301`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c4a0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c5ef`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c775`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c8a8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cb20`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c301`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c4a0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c5ef`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c775`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c8a8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cb20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c297`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c582`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c6d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cabb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ce27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c297`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c582`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c6d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cabb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ce27`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18000c760`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18000c78f`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18000c7b4`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18000c8bf`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18000c8e4`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18000c99c`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18000c9e1`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18000c760`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18000c78f`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18000c7b4`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18000c8bf`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18000c8e4`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18000c99c`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18000c9e1`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000c18f`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000c286`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000c468`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000c7cf`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000c810`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000c851`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000c915`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000c9fe`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000caaa`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000cc4a`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000c18f`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000c286`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000c468`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000c7cf`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000c810`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000c851`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000c915`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000c9fe`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000caaa`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000cc4a`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x18000c73d`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x18000c887`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x18000c96a`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x18000c9b5`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x18000c73d`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x18000c887`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x18000c96a`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x18000c9b5`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000c211`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000c3c3`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000c406`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000c4b1`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000c6e3`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000c7f2`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000c836`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000c874`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000c951`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000ca19`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000cbe4`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000cc73`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000cd99`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000cdf9`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000ce0b`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000ce35`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000c211`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000c3c3`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000c406`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000c4b1`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000c6e3`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000c7f2`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000c836`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000c874`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000c951`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000ca19`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000cbe4`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000cc73`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000cd99`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000cdf9`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000ce0b`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000ce35`

## string_xrefs

- `0x18000c9f1`: `msPKI-Template-Schema-Version`
- `0x18000cd60`: `msPKI-Template-Schema-Version`
- `0x18000cc7e`: `msPKI-Template-Minor-Revision`
- `0x18000c728`: `NTSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::_LoadFromDSEntry(struct CCAProperty **this, struct ldap *a2, struct ldapmsg *a3)
{
  LDAPMessage *v3; // rbp
  PWCHAR *valuesW; // rax
  unsigned int v7; // r9d
  const unsigned __int16 **v8; // rbx
  unsigned int v9; // ebp
  int v10; // r8d
  unsigned int v11; // edx
  unsigned __int16 *v12; // rax
  const PWSTR *i; // rsi
  struct CCAProperty *v14; // rax
  struct CCAProperty *v15; // rdi
  const unsigned __int16 *v16; // rcx
  PWCHAR *v17; // r14
  unsigned __int64 v18; // rbp
  unsigned int v19; // r8d
  PWCHAR v20; // rcx
  PWCHAR *v21; // rdx
  __int64 v22; // rax
  __int64 v23; // rbx
  char *v24; // rax
  char *v25; // r10
  unsigned int v26; // r11d
  unsigned __int64 v27; // rbp
  PWCHAR *j; // rbx
  __int64 v29; // rcx
  PWCHAR v30; // rdx
  unsigned __int64 v31; // r9
  char *v32; // r8
  WCHAR v33; // ax
  char *v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rax
  int v37; // eax
  __int64 *v38; // r14
  PWCHAR *v39; // rax
  PWCHAR *v40; // r15
  unsigned int v41; // edi
  PWCHAR *k; // rcx
  __int64 *v43; // rax
  const wchar_t *v44; // rax
  const wchar_t **v45; // rbx
  unsigned int v46; // eax
  wchar_t *v47; // rdx
  struct CCAProperty *v48; // rax
  struct CCAProperty *v49; // rbx
  unsigned __int64 v50; // rsi
  unsigned int v51; // edx
  __int64 v52; // rcx
  __int64 *v53; // r8
  __int64 v54; // rax
  __int64 v55; // rdi
  char *v56; // rax
  char *v57; // r10
  __int64 v58; // rdi
  unsigned __int64 v59; // rsi
  __int16 **v60; // r11
  __int64 v61; // rax
  __int16 *v62; // rcx
  unsigned __int64 v63; // r9
  char *v64; // r8
  __int16 v65; // dx
  char *v66; // rcx
  __int64 v67; // rax
  __int64 v68; // rax
  int v69; // eax
  LDAPMessage *v70; // r14
  struct berval **values_lenW; // rax
  struct berval **v72; // rbx
  SIZE_T bv_len; // rax
  struct CCAProperty *v74; // rax
  const wchar_t **v75; // rax
  PWCHAR *v76; // rbx
  const wchar_t **v77; // rax
  PWCHAR *v78; // rbx
  const wchar_t **v79; // rax
  PWCHAR *v80; // rbx
  struct berval **v81; // rax
  struct berval **v82; // rbx
  SIZE_T v83; // rdx
  struct CCAProperty *v84; // rax
  const wchar_t **v85; // rax
  PWCHAR *v86; // rbx
  int v87; // eax
  BOOL v88; // eax
  struct berval **v89; // rax
  struct berval **v90; // rbx
  size_t v91; // rsi
  const void **v92; // rdx
  unsigned int v93; // eax
  size_t v94; // r8
  struct berval **v95; // rax
  struct berval **v96; // rbx
  const void **v97; // rdx
  unsigned int v98; // eax
  PWCHAR *v99; // rax
  unsigned int v100; // r15d
  struct _CERT_TYPE_PROP_INFO near **v101; // rdi
  struct CCAProperty *v102; // rax
  struct CCAProperty *v103; // rsi
  const unsigned __int16 *v104; // rcx
  PWCHAR *v105; // r14
  unsigned __int64 v106; // rdi
  unsigned int v107; // r8d
  PWCHAR v108; // rcx
  PWCHAR *v109; // rdx
  __int64 v110; // rax
  __int64 v111; // rbx
  char *v112; // rax
  char *v113; // r10
  __int64 v114; // r11
  unsigned __int64 v115; // rdi
  PWCHAR *m; // rbx
  __int64 v117; // rcx
  PWCHAR v118; // rdx
  unsigned __int64 v119; // r9
  char *v120; // r8
  WCHAR v121; // ax
  char *v122; // rcx
  __int64 v123; // rax
  __int64 v124; // rax
  struct CCAProperty **v125; // rcx
  struct CCAProperty *v126; // rax
  const wchar_t **v127; // rax
  PWCHAR *v128; // rbx
  int v129; // esi
  const wchar_t *v130; // rbx
  __int64 n; // rcx
  int v132; // r8d
  unsigned __int16 **v134; // [rsp+20h] [rbp-58h]
  wchar_t *EndPtr; // [rsp+30h] [rbp-48h] BYREF
  struct CCAProperty *v137; // [rsp+98h] [rbp+20h] BYREF

  v3 = a3;
  valuesW = ldap_get_valuesW(a2, a3, (const PWSTR)L"cn");
  v8 = (const unsigned __int16 **)valuesW;
  if ( !valuesW )
  {
    v9 = myHLdapError3(a2, 0x10u, 0, v7, v134);
    v10 = v9;
    v11 = 97387304;
    goto LABEL_213;
  }
  if ( !*valuesW )
  {
    v9 = myHLdapError3(a2, 0x10u, 0, v7, v134);
    v10 = v9;
    v11 = 97780520;
    goto LABEL_213;
  }
  CCertTypeInfo::SetProperty((CCertTypeInfo *)this, L"distinguishedName", valuesW);
  v12 = CertAllocString(*v8);
  this[1] = (struct CCAProperty *)v12;
  if ( !v12 )
  {
    v11 = 98370344;
LABEL_211:
    v9 = -2147024882;
    goto LABEL_212;
  }
  ldap_value_freeW((PWCHAR *)v8);
  for ( i = (const PWSTR *)&g_awszCTNamedProps; *i; ++i )
  {
    v14 = (struct CCAProperty *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v15 = v14;
    EndPtr = (wchar_t *)v14;
    if ( v14 )
    {
      v16 = *i;
      *(_QWORD *)v14 = 0;
      *((_QWORD *)v14 + 2) = 0;
      *((_QWORD *)v14 + 1) = CertAllocString(v16);
    }
    else
    {
      v15 = 0;
    }
    v137 = v15;
    if ( !v15 )
    {
      v11 = 99287848;
      goto LABEL_211;
    }
    if ( !*((_QWORD *)v15 + 1) )
    {
      CCAProperty::DeleteChain(&v137);
      v11 = 99746600;
      goto LABEL_211;
    }
    v17 = ldap_get_valuesW(a2, v3, *i);
    if ( *(_QWORD *)v15 )
    {
      LocalFree(*(HLOCAL *)v15);
      *(_QWORD *)v15 = 0;
    }
    if ( v17 )
    {
      v18 = 0;
      v19 = 1;
      v20 = *v17;
      if ( *v17 )
      {
        v21 = v17;
        do
        {
          ++v19;
          v22 = -1;
          do
            ++v22;
          while ( v20[v22] );
          v18 += 2 * v22 + 2;
          v20 = *++v21;
        }
        while ( *v21 );
      }
      v23 = 8LL * v19;
      v24 = (char *)LocalAlloc(0, v23 + v18);
      *(_QWORD *)v15 = v24;
      if ( !v24 )
      {
        v9 = -2147024882;
        CSPrintErrorLineFileData2(0, 0x5F70328u, -2147024882, 0);
        ldap_value_freeW(v17);
LABEL_42:
        CCAProperty::DeleteChain(&v137);
        v11 = 101057320;
        goto LABEL_212;
      }
      v25 = &v24[v23];
      v26 = 0;
      v27 = v18 >> 1;
      for ( j = v17; *j; ++j )
      {
        *(_QWORD *)(*(_QWORD *)v15 + 8LL * v26) = v25;
        if ( v27 )
        {
          if ( v27 <= 0x7FFFFFFF )
          {
            v29 = 2147483646;
            v30 = *j;
            v31 = v27;
            v32 = v25;
            do
            {
              if ( !v29 )
                break;
              v33 = *v30;
              if ( !*v30 )
                break;
              ++v30;
              *(_WORD *)v32 = v33;
              v32 += 2;
              --v29;
              --v31;
            }
            while ( v31 );
            v34 = v32 - 2;
            if ( v31 )
              v34 = v32;
            *(_WORD *)v34 = 0;
          }
          else
          {
            *(_WORD *)v25 = 0;
          }
        }
        v35 = -1;
        do
          ++v35;
        while ( *(_WORD *)&v25[2 * v35] );
        v36 = v35 + 1;
        v25 += 2 * v36;
        v27 -= v36;
        ++v26;
      }
      *(_QWORD *)(*(_QWORD *)v15 + 8LL * v26) = 0;
      ldap_value_freeW(v17);
    }
    v37 = CCAProperty::Append(this + 12, v15);
    v9 = v37;
    if ( v37 )
    {
      CSPrintErrorLineFileData2(0, 0x6000328u, v37, 0);
      goto LABEL_42;
    }
    v3 = a3;
  }
  v38 = 0;
  v39 = ldap_get_valuesW(a2, v3, (const PWSTR)L"pKIDefaultCSPs");
  v40 = v39;
  if ( v39 )
  {
    EndPtr = 0;
    v41 = 0;
    for ( k = v39; *k; ++k )
      ++v41;
    v43 = (__int64 *)LocalAlloc(0, 8LL * (v41 + 1));
    v38 = v43;
    if ( !v43 )
    {
      ldap_value_freeW(v40);
      v11 = 103023400;
      goto LABEL_211;
    }
    memset_0(v43, 0, 8LL * (v41 + 1));
    v44 = *v40;
    if ( *v40 )
    {
      v45 = (const wchar_t **)v40;
      do
      {
        v46 = wcstol(v44, &EndPtr, 10);
        v47 = EndPtr;
        if ( EndPtr )
          v47 = ++EndPtr;
        if ( v46 && v46 <= v41 )
          v38[v46 - 1] = (__int64)v47;
        v44 = *++v45;
      }
      while ( *v45 );
    }
  }
  v48 = (struct CCAProperty *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v49 = v48;
  v137 = v48;
  if ( v48 )
  {
    *(_QWORD *)v48 = 0;
    *((_QWORD *)v48 + 2) = 0;
    *((_QWORD *)v48 + 1) = CertAllocString(L"pKIDefaultCSPs");
  }
  else
  {
    v49 = 0;
  }
  v137 = v49;
  if ( !v49 || !*((_QWORD *)v49 + 1) )
  {
    if ( v38 )
      LocalFree(v38);
    if ( v40 )
      ldap_value_freeW(v40);
    if ( v49 )
      CCAProperty::DeleteChain(&v137);
    v11 = 105382696;
    goto LABEL_211;
  }
  if ( *(_QWORD *)v49 )
  {
    LocalFree(*(HLOCAL *)v49);
    *(_QWORD *)v49 = 0;
  }
  if ( v38 )
  {
    v50 = 0;
    v51 = 1;
    v52 = *v38;
    if ( *v38 )
    {
      v53 = v38;
      do
      {
        ++v51;
        v54 = -1;
        do
          ++v54;
        while ( *(_WORD *)(v52 + 2 * v54) );
        v50 += 2 * v54 + 2;
        v52 = *++v53;
      }
      while ( *v53 );
    }
    v55 = 8LL * v51;
    v56 = (char *)LocalAlloc(0, v55 + v50);
    *(_QWORD *)v49 = v56;
    if ( v56 )
    {
      v57 = &v56[v55];
      v58 = 0;
      v59 = v50 >> 1;
      v60 = (__int16 **)v38;
      if ( *v38 )
      {
        do
        {
          *(_QWORD *)(*(_QWORD *)v49 + 8 * v58) = v57;
          if ( v59 )
          {
            if ( v59 <= 0x7FFFFFFF )
            {
              v61 = 2147483646;
              v62 = *v60;
              v63 = v59;
              v64 = v57;
              do
              {
                if ( !v61 )
                  break;
                v65 = *v62;
                if ( !*v62 )
                  break;
                ++v62;
                *(_WORD *)v64 = v65;
                v64 += 2;
                --v61;
                --v63;
              }
              while ( v63 );
              v66 = v64 - 2;
              if ( v63 )
                v66 = v64;
              *(_WORD *)v66 = 0;
            }
            else
            {
              *(_WORD *)v57 = 0;
            }
          }
          v67 = -1;
          do
            ++v67;
          while ( *(_WORD *)&v57[2 * v67] );
          v68 = v67 + 1;
          v57 += 2 * v68;
          v59 -= v68;
          v58 = (unsigned int)(v58 + 1);
          ++v60;
        }
        while ( *v60 );
      }
      *(_QWORD *)(*(_QWORD *)v49 + 8 * v58) = 0;
      v9 = 0;
    }
    else
    {
      v9 = -2147024882;
      CSPrintErrorLineFileData2(0, 0x64B0328u, -2147024882, 0);
    }
    LocalFree(v38);
  }
  else
  {
    v9 = 0;
  }
  if ( v40 )
    ldap_value_freeW(v40);
  if ( v9 )
  {
LABEL_95:
    CCAProperty::DeleteChain(&v137);
    v11 = 106890024;
    goto LABEL_212;
  }
  v69 = CCAProperty::Append(this + 12, v49);
  v9 = v69;
  if ( v69 )
  {
    CSPrintErrorLineFileData2(0, 0x6590328u, v69, 0);
    goto LABEL_95;
  }
  v70 = a3;
  values_lenW = ldap_get_values_lenW(a2, a3, (const PWSTR)L"NTSecurityDescriptor");
  v72 = values_lenW;
  if ( !values_lenW )
  {
    v9 = -2147024883;
    v11 = 108987176;
    goto LABEL_212;
  }
  bv_len = (*values_lenW)->bv_len;
  if ( !(_DWORD)bv_len )
  {
    v9 = -2147024883;
    ldap_value_free_len(v72);
    v11 = 107873064;
    goto LABEL_212;
  }
  v74 = (struct CCAProperty *)LocalAlloc(0, bv_len);
  this[17] = v74;
  if ( !v74 )
  {
    v9 = -2147024882;
    ldap_value_free_len(v72);
    v11 = 108397352;
    goto LABEL_212;
  }
  memcpy_0(v74, (*v72)->bv_val, (*v72)->bv_len);
  ldap_value_free_len(v72);
  *((_DWORD *)this + 14) = 0;
  v75 = (const wchar_t **)ldap_get_valuesW(a2, a3, (const PWSTR)L"flags");
  v76 = (PWCHAR *)v75;
  if ( v75 )
  {
    if ( *v75 )
      *((_DWORD *)this + 14) = _wtol(*v75);
    ldap_value_freeW(v76);
  }
  *((_DWORD *)this + 36) = 0;
  v77 = (const wchar_t **)ldap_get_valuesW(a2, a3, (const PWSTR)L"revision");
  v78 = (PWCHAR *)v77;
  if ( v77 )
  {
    if ( *v77 )
      *((_DWORD *)this + 36) = _wtol(*v77);
    ldap_value_freeW(v78);
  }
  *((_DWORD *)this + 15) = 0;
  v79 = (const wchar_t **)ldap_get_valuesW(a2, a3, (const PWSTR)L"pKIDefaultKeySpec");
  v80 = (PWCHAR *)v79;
  if ( v79 )
  {
    if ( *v79 )
      *((_DWORD *)this + 15) = _wtol(*v79);
    ldap_value_freeW(v80);
  }
  v81 = ldap_get_values_lenW(a2, a3, (const PWSTR)L"pKIKeyUsage");
  v82 = v81;
  if ( v81 )
  {
    v83 = (*v81)->bv_len;
    *((_DWORD *)this + 8) = v83;
    *((_DWORD *)this + 12) = 0;
    v84 = (struct CCAProperty *)LocalAlloc(0, v83);
    this[5] = v84;
    if ( !v84 )
    {
      v9 = -2147024882;
      ldap_value_free_len(v82);
      v11 = 112001832;
      goto LABEL_212;
    }
    memcpy_0(v84, (*v82)->bv_val, (*v82)->bv_len);
    ldap_value_free_len(v82);
  }
  *((_DWORD *)this + 6) = 0;
  *((_DWORD *)this + 4) = ((_DWORD)this[7] & 0x880) != 0;
  v85 = (const wchar_t **)ldap_get_valuesW(a2, a3, (const PWSTR)L"pKIMaxIssuingDepth");
  v86 = (PWCHAR *)v85;
  if ( v85 )
  {
    if ( *v85 )
    {
      v87 = _wtoi(*v85);
      *((_DWORD *)this + 6) = v87;
      v88 = v87 != -1 && *((_DWORD *)this + 4);
      *((_DWORD *)this + 5) = v88;
    }
    ldap_value_freeW(v86);
  }
  this[13] = 0;
  v89 = ldap_get_values_lenW(a2, a3, (const PWSTR)L"pKIExpirationPeriod");
  v90 = v89;
  v91 = 8;
  if ( v89 )
  {
    v92 = (const void **)*v89;
    v93 = (*v89)->bv_len;
    v94 = v93;
    if ( v93 >= 8 )
      v94 = 8;
    memcpy_0(this + 13, v92[1], v94);
    ldap_value_free_len(v90);
  }
  this[14] = 0;
  v95 = ldap_get_values_lenW(a2, a3, (const PWSTR)L"pKIOverlapPeriod");
  v96 = v95;
  if ( v95 )
  {
    v97 = (const void **)*v95;
    v98 = (*v95)->bv_len;
    if ( v98 < 8 )
      v91 = v98;
    memcpy_0(this + 14, v97[1], v91);
    ldap_value_free_len(v96);
  }
  *((_DWORD *)this + 30) = 0;
  v9 = 0;
  v99 = ldap_get_valuesW(a2, a3, (const PWSTR)L"msPKI-Template-Schema-Version");
  if ( !v99 )
    return v9;
  if ( !*v99 )
  {
    ldap_value_freeW(v99);
    return v9;
  }
  ldap_value_freeW(v99);
  v100 = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      if ( v100 >= 0xD )
        return v9;
      v101 = &g_CTV2Properties + 2 * v100;
      if ( !*((_DWORD *)v101 + 2) )
        break;
      v102 = (struct CCAProperty *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
      v103 = v102;
      EndPtr = (wchar_t *)v102;
      if ( v102 )
      {
        v104 = (const unsigned __int16 *)*v101;
        *(_QWORD *)v102 = 0;
        *((_QWORD *)v102 + 2) = 0;
        *((_QWORD *)v102 + 1) = CertAllocString(v104);
      }
      else
      {
        v103 = 0;
      }
      v137 = v103;
      if ( !v103 )
      {
        v11 = 116392744;
        goto LABEL_211;
      }
      if ( !*((_QWORD *)v103 + 1) )
      {
        CCAProperty::DeleteChain(&v137);
        v11 = 116917032;
        goto LABEL_211;
      }
      v105 = ldap_get_valuesW(a2, v70, (const PWSTR)*v101);
      if ( *(_QWORD *)v103 )
      {
        LocalFree(*(HLOCAL *)v103);
        *(_QWORD *)v103 = 0;
      }
      if ( v105 )
      {
        v106 = 0;
        v107 = 1;
        v108 = *v105;
        if ( *v105 )
        {
          v109 = v105;
          do
          {
            ++v107;
            v110 = -1;
            do
              ++v110;
            while ( v108[v110] );
            v106 += 2 * v110 + 2;
            v108 = *++v109;
          }
          while ( *v109 );
        }
        v111 = 8LL * v107;
        v112 = (char *)LocalAlloc(0, v111 + v106);
        *(_QWORD *)v103 = v112;
        if ( !v112 )
        {
          v9 = -2147024882;
          CSPrintErrorLineFileData2(0, 0x6FD0328u, -2147024882, 0);
          ldap_value_freeW(v105);
LABEL_196:
          CCAProperty::DeleteChain(&v137);
          v11 = 118358824;
          goto LABEL_212;
        }
        v113 = &v112[v111];
        v114 = 0;
        v115 = v106 >> 1;
        for ( m = v105; *m; ++m )
        {
          *(_QWORD *)(*(_QWORD *)v103 + 8 * v114) = v113;
          if ( v115 )
          {
            if ( v115 <= 0x7FFFFFFF )
            {
              v117 = 2147483646;
              v118 = *m;
              v119 = v115;
              v120 = v113;
              do
              {
                if ( !v117 )
                  break;
                v121 = *v118;
                if ( !*v118 )
                  break;
                ++v118;
                *(_WORD *)v120 = v121;
                v120 += 2;
                --v117;
                --v119;
              }
              while ( v119 );
              v122 = v120 - 2;
              if ( v119 )
                v122 = v120;
              *(_WORD *)v122 = 0;
            }
            else
            {
              *(_WORD *)v113 = 0;
            }
          }
          v123 = -1;
          do
            ++v123;
          while ( *(_WORD *)&v113[2 * v123] );
          v124 = v123 + 1;
          v113 += 2 * v124;
          v115 -= v124;
          v114 = (unsigned int)(v114 + 1);
        }
        *(_QWORD *)(*(_QWORD *)v103 + 8 * v114) = 0;
        ldap_value_freeW(v105);
      }
      v125 = this + 12;
      if ( this == (struct CCAProperty **)-96LL )
      {
        v9 = -2147467261;
        CSPrintErrorLineFileData2(0, 0x7080328u, -2147467261, 0);
        goto LABEL_196;
      }
      v126 = *v125;
      if ( !*v125 )
      {
        *v125 = v103;
        v9 = 0;
        v70 = a3;
        goto LABEL_193;
      }
      for ( ; *((_QWORD *)v126 + 2); v126 = (struct CCAProperty *)*((_QWORD *)v126 + 2) )
        ;
      *((_QWORD *)v126 + 2) = v103;
      v9 = 0;
      v70 = a3;
      ++v100;
    }
    v127 = (const wchar_t **)ldap_get_valuesW(a2, v70, (const PWSTR)*v101);
    v128 = (PWCHAR *)v127;
    if ( !v127 )
      goto LABEL_201;
    if ( !*v127 )
      break;
    v129 = _wtol(*v127);
    ldap_value_freeW(v128);
    v130 = (const wchar_t *)*v101;
    for ( n = 0; n != 30; n += 2 )
    {
      v132 = v130[n] - aMspkiTemplateM[n];
      if ( v132 )
        break;
      v132 = v130[n + 1] - aMspkiTemplateM[n + 1];
      if ( v132 )
        break;
    }
    if ( v132 )
    {
      if ( !wcscmp_0((const wchar_t *)*v101, L"msPKI-RA-Signature") )
      {
        *((_DWORD *)this + 21) = v129;
        ++v100;
      }
      else if ( !wcscmp_0(v130, L"msPKI-Enrollment-Flag") )
      {
        *((_DWORD *)this + 17) = v129;
        ++v100;
      }
      else
      {
        if ( !wcscmp_0(v130, L"msPKI-Private-Key-Flag") )
        {
          *((_DWORD *)this + 18) = v129;
          goto LABEL_193;
        }
        if ( !wcscmp_0(v130, L"msPKI-Certificate-Name-Flag") )
        {
          *((_DWORD *)this + 19) = v129;
          ++v100;
        }
        else if ( !wcscmp_0(v130, L"msPKI-Minimal-Key-Size") )
        {
          *((_DWORD *)this + 20) = v129;
          ++v100;
        }
        else
        {
          if ( wcscmp_0(v130, L"msPKI-Template-Schema-Version") )
          {
            v9 = -2147418113;
            v11 = 121307944;
            goto LABEL_212;
          }
          *((_DWORD *)this + 22) = v129;
LABEL_193:
          ++v100;
        }
      }
    }
    else
    {
      *((_DWORD *)this + 16) = v129;
      ++v100;
    }
  }
  ldap_value_freeW((PWCHAR *)v127);
LABEL_201:
  v9 = -2147418113;
  v11 = 119931688;
LABEL_212:
  v10 = v9;
LABEL_213:
  CSPrintErrorLineFileData2(0, v11, v10, 0);
  return v9;
}

```

## disassembly

```asm
0x18000c160  mov     [rsp+arg_0], rbx
0x18000c165  mov     [rsp+Message], r8
0x18000c16a  push    rbp
0x18000c16b  push    rsi
0x18000c16c  push    rdi
0x18000c16d  push    r12
0x18000c16f  push    r13
0x18000c171  push    r14
0x18000c173  push    r15
0x18000c175  sub     rsp, 40h
0x18000c179  mov     rbp, r8
0x18000c17c  mov     r12, rdx
0x18000c17f  mov     r13, rcx
0x18000c182  lea     r8, aCn_1; "cn"
0x18000c189  mov     rdx, rbp; entry
0x18000c18c  mov     rcx, r12; ld
0x18000c18f  call    cs:__imp_ldap_get_valuesW
0x18000c195  mov     rbx, rax
0x18000c198  test    rax, rax
0x18000c19b  jnz     short loc_18000C1BC
0x18000c19d  xor     r8d, r8d; unsigned int
0x18000c1a0  mov     edx, 10h; unsigned int
0x18000c1a5  mov     rcx, r12; ld
0x18000c1a8  call    ?myHLdapError3@@YAJPEAUldap@@KKKPEAPEAG@Z; myHLdapError3(ldap *,ulong,ulong,ulong,ushort * *)
0x18000c1ad  mov     ebp, eax
0x18000c1af  mov     r8d, eax
0x18000c1b2  mov     edx, 5CE0328h
0x18000c1b7  jmp     loc_18000CE5A
0x18000c1bc  cmp     qword ptr [rax], 0
0x18000c1c0  jnz     short loc_18000C1E1
0x18000c1c2  xor     r8d, r8d; unsigned int
0x18000c1c5  mov     edx, 10h; unsigned int
0x18000c1ca  mov     rcx, r12; ld
0x18000c1cd  call    ?myHLdapError3@@YAJPEAUldap@@KKKPEAPEAG@Z; myHLdapError3(ldap *,ulong,ulong,ulong,ushort * *)
0x18000c1d2  mov     ebp, eax
0x18000c1d4  mov     r8d, eax
0x18000c1d7  mov     edx, 5D40328h
0x18000c1dc  jmp     loc_18000CE5A
0x18000c1e1  mov     r8, rbx; unsigned __int16 **
0x18000c1e4  lea     rdx, aDistinguishedn; "distinguishedName"
0x18000c1eb  mov     rcx, r13; this
0x18000c1ee  call    ?SetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAG@Z; CCertTypeInfo::SetProperty(ushort const *,ushort * *)
0x18000c1f3  mov     rcx, [rbx]; Src
0x18000c1f6  call    ?CertAllocString@@YAPEAGPEBG@Z; CertAllocString(ushort const *)
0x18000c1fb  mov     [r13+8], rax
0x18000c1ff  test    rax, rax
0x18000c202  jnz     short loc_18000C20E
0x18000c204  mov     edx, 5DD0328h
0x18000c209  jmp     loc_18000CE52
0x18000c20e  mov     rcx, rbx; vals
0x18000c211  call    cs:__imp_ldap_value_freeW
0x18000c217  lea     rsi, ?g_awszCTNamedProps@@3PAPEAGA; ushort * near * g_awszCTNamedProps
0x18000c21e  xor     r15d, r15d
0x18000c221  cmp     qword ptr [rsi], 0
0x18000c225  jz      loc_18000C458
0x18000c22b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c232  mov     ecx, 18h; unsigned __int64
0x18000c237  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c23c  mov     rdi, rax
0x18000c23f  mov     [rsp+78h+EndPtr], rax
0x18000c244  test    rax, rax
0x18000c247  jz      short loc_18000C25E
0x18000c249  mov     rcx, [rsi]; Src
0x18000c24c  mov     [rax], r15
0x18000c24f  mov     [rax+10h], r15
0x18000c253  call    ?CertAllocString@@YAPEAGPEBG@Z; CertAllocString(ushort const *)
0x18000c258  mov     [rdi+8], rax
0x18000c25c  jmp     short loc_18000C261
0x18000c25e  mov     rdi, r15
0x18000c261  mov     [rsp+78h+arg_18], rdi
0x18000c269  test    rdi, rdi
0x18000c26c  jz      loc_18000C44E
0x18000c272  cmp     qword ptr [rdi+8], 0
0x18000c277  jz      loc_18000C437
0x18000c27d  mov     r8, [rsi]; attr
0x18000c280  mov     rdx, rbp; entry
0x18000c283  mov     rcx, r12; ld
0x18000c286  call    cs:__imp_ldap_get_valuesW
0x18000c28c  mov     r14, rax
0x18000c28f  mov     rcx, [rdi]; hMem
0x18000c292  test    rcx, rcx
0x18000c295  jz      short loc_18000C2A0
0x18000c297  call    cs:__imp_LocalFree
0x18000c29d  mov     [rdi], r15
0x18000c2a0  test    r14, r14
0x18000c2a3  jz      loc_18000C3C9
0x18000c2a9  mov     rbp, r15
0x18000c2ac  mov     r8d, 1
0x18000c2b2  mov     rcx, [r14]
0x18000c2b5  test    rcx, rcx
0x18000c2b8  jz      short loc_18000C2F0
0x18000c2ba  mov     rdx, r14
0x18000c2bd  inc     r8d
0x18000c2c0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000c2c7  nop     word ptr [rax+rax+00000000h]
0x18000c2d0  lea     rax, [rax+1]
0x18000c2d4  cmp     word ptr [rcx+rax*2], 0
0x18000c2d9  jnz     short loc_18000C2D0
0x18000c2db  lea     rbp, [rbp+rax*2+0]
0x18000c2e0  add     rbp, 2
0x18000c2e4  add     rdx, 8
0x18000c2e8  mov     rcx, [rdx]
0x18000c2eb  test    rcx, rcx
0x18000c2ee  jnz     short loc_18000C2BD
0x18000c2f0  mov     eax, r8d
0x18000c2f3  lea     rbx, ds:0[rax*8]
0x18000c2fb  lea     rdx, [rbx+rbp]; uBytes
0x18000c2ff  xor     ecx, ecx; uFlags
0x18000c301  call    cs:__imp_LocalAlloc
0x18000c307  mov     [rdi], rax
0x18000c30a  test    rax, rax
0x18000c30d  jz      loc_18000C3EC
0x18000c313  lea     r10, [rax+rbx]
0x18000c317  mov     r11d, r15d
0x18000c31a  shr     rbp, 1
0x18000c31d  mov     rbx, r14
0x18000c320  cmp     [r14], r11
0x18000c323  jz      loc_18000C3B6
0x18000c329  mov     ecx, r11d
0x18000c32c  mov     rax, [rdi]
0x18000c32f  mov     [rax+rcx*8], r10
0x18000c333  test    rbp, rbp
0x18000c336  jz      short loc_18000C386
0x18000c338  cmp     rbp, 7FFFFFFFh
0x18000c33f  jbe     short loc_18000C347
0x18000c341  mov     [r10], r15w
0x18000c345  jmp     short loc_18000C386
0x18000c347  mov     ecx, 7FFFFFFEh
0x18000c34c  mov     rdx, [rbx]
0x18000c34f  mov     r9, rbp
0x18000c352  mov     r8, r10
0x18000c355  test    rcx, rcx
0x18000c358  jz      short loc_18000C377
0x18000c35a  movzx   eax, word ptr [rdx]
0x18000c35d  test    ax, ax
0x18000c360  jz      short loc_18000C377
0x18000c362  add     rdx, 2
0x18000c366  mov     [r8], ax
0x18000c36a  add     r8, 2
0x18000c36e  dec     rcx
0x18000c371  sub     r9, 1
0x18000c375  jnz     short loc_18000C355
0x18000c377  lea     rcx, [r8-2]
0x18000c37b  test    r9, r9
0x18000c37e  cmovnz  rcx, r8
0x18000c382  mov     [rcx], r15w
0x18000c386  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000c38d  nop     dword ptr [rax]
0x18000c390  inc     rax
0x18000c393  cmp     word ptr [r10+rax*2], 0
0x18000c399  jnz     short loc_18000C390
0x18000c39b  inc     rax
0x18000c39e  lea     r10, [r10+rax*2]
0x18000c3a2  sub     rbp, rax
0x18000c3a5  inc     r11d
0x18000c3a8  add     rbx, 8
0x18000c3ac  cmp     qword ptr [rbx], 0
0x18000c3b0  jnz     loc_18000C329
0x18000c3b6  mov     ecx, r11d
0x18000c3b9  mov     rax, [rdi]
0x18000c3bc  mov     [rax+rcx*8], r15
0x18000c3c0  mov     rcx, r14; vals
0x18000c3c3  call    cs:__imp_ldap_value_freeW
0x18000c3c9  lea     rcx, [r13+60h]; struct CCAProperty **
0x18000c3cd  mov     rdx, rdi; struct CCAProperty *
0x18000c3d0  call    ?Append@CCAProperty@@SAJPEAPEAV1@PEAV1@@Z; CCAProperty::Append(CCAProperty * *,CCAProperty *)
0x18000c3d5  mov     ebp, eax
0x18000c3d7  test    eax, eax
0x18000c3d9  jnz     short loc_18000C40E
0x18000c3db  add     rsi, 8
0x18000c3df  mov     rbp, [rsp+78h+Message]
0x18000c3e7  jmp     loc_18000C221
0x18000c3ec  mov     ebp, 8007000Eh
0x18000c3f1  xor     r9d, r9d; int
0x18000c3f4  mov     edx, 5F70328h; unsigned int
0x18000c3f9  xor     ecx, ecx; unsigned __int16 *
0x18000c3fb  mov     r8d, ebp; int
0x18000c3fe  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000c403  mov     rcx, r14; vals
0x18000c406  call    cs:__imp_ldap_value_freeW
0x18000c40c  jmp     short loc_18000C420
0x18000c40e  xor     r9d, r9d; int
0x18000c411  mov     r8d, eax; int
0x18000c414  mov     edx, 6000328h; unsigned int
0x18000c419  xor     ecx, ecx; unsigned __int16 *
0x18000c41b  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000c420  lea     rcx, [rsp+78h+arg_18]; struct CCAProperty **
0x18000c428  call    ?DeleteChain@CCAProperty@@SAJPEAPEAV1@@Z; CCAProperty::DeleteChain(CCAProperty * *)
0x18000c42d  mov     edx, 6060328h
0x18000c432  jmp     loc_18000CE57
0x18000c437  lea     rcx, [rsp+78h+arg_18]; struct CCAProperty **
0x18000c43f  call    ?DeleteChain@CCAProperty@@SAJPEAPEAV1@@Z; CCAProperty::DeleteChain(CCAProperty * *)
0x18000c444  mov     edx, 5F20328h
0x18000c449  jmp     loc_18000CE52
0x18000c44e  mov     edx, 5EB0328h
0x18000c453  jmp     loc_18000CE52
0x18000c458  xor     r14d, r14d
0x18000c45b  lea     r8, aPkidefaultcsps; "pKIDefaultCSPs"
0x18000c462  mov     rdx, rbp; entry
0x18000c465  mov     rcx, r12; ld
0x18000c468  call    cs:__imp_ldap_get_valuesW
0x18000c46e  mov     r15, rax
0x18000c471  test    rax, rax
0x18000c474  jz      loc_18000C51A
0x18000c47a  mov     [rsp+78h+EndPtr], r14
0x18000c47f  xor     edi, edi
0x18000c481  mov     rcx, rax
0x18000c484  cmp     [rax], rdi
0x18000c487  jz      short loc_18000C494
0x18000c489  inc     edi
0x18000c48b  lea     rcx, [rcx+8]
0x18000c48f  cmp     [rcx], r14
0x18000c492  jnz     short loc_18000C489
0x18000c494  lea     ebx, [rdi+1]
0x18000c497  shl     rbx, 3
0x18000c49b  mov     rdx, rbx; uBytes
0x18000c49e  xor     ecx, ecx; uFlags
0x18000c4a0  call    cs:__imp_LocalAlloc
0x18000c4a6  mov     r14, rax
0x18000c4a9  test    rax, rax
0x18000c4ac  jnz     short loc_18000C4C1
0x18000c4ae  mov     rcx, r15; vals
0x18000c4b1  call    cs:__imp_ldap_value_freeW
0x18000c4b7  mov     edx, 6240328h
0x18000c4bc  jmp     loc_18000CE52
0x18000c4c1  mov     r8, rbx; Size
0x18000c4c4  xor     edx, edx; Val
0x18000c4c6  mov     rcx, r14; void *
0x18000c4c9  call    memset_0
0x18000c4ce  mov     rax, [r15]
0x18000c4d1  test    rax, rax
0x18000c4d4  jz      short loc_18000C51A
0x18000c4d6  mov     rbx, r15
0x18000c4d9  mov     r8d, 0Ah; Radix
0x18000c4df  lea     rdx, [rsp+78h+EndPtr]; EndPtr
0x18000c4e4  mov     rcx, rax; String
0x18000c4e7  call    cs:__imp_wcstol
0x18000c4ed  mov     rdx, [rsp+78h+EndPtr]
0x18000c4f2  test    rdx, rdx
0x18000c4f5  jz      short loc_18000C500
0x18000c4f7  add     rdx, 2
0x18000c4fb  mov     [rsp+78h+EndPtr], rdx
0x18000c500  test    eax, eax
0x18000c502  jz      short loc_18000C50E
0x18000c504  cmp     eax, edi
0x18000c506  ja      short loc_18000C50E
0x18000c508  dec     eax
0x18000c50a  mov     [r14+rax*8], rdx
0x18000c50e  add     rbx, 8
0x18000c512  mov     rax, [rbx]
0x18000c515  test    rax, rax
0x18000c518  jnz     short loc_18000C4D9
0x18000c51a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c521  mov     ecx, 18h; unsigned __int64
0x18000c526  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c52b  mov     rbx, rax
0x18000c52e  mov     [rsp+78h+arg_18], rax
0x18000c536  test    rax, rax
0x18000c539  jz      short loc_18000C55C
0x18000c53b  mov     qword ptr [rax], 0
0x18000c542  mov     qword ptr [rax+10h], 0
0x18000c54a  lea     rcx, aPkidefaultcsps; "pKIDefaultCSPs"
0x18000c551  call    ?CertAllocString@@YAPEAGPEBG@Z; CertAllocString(ushort const *)
0x18000c556  mov     [rbx+8], rax
0x18000c55a  jmp     short loc_18000C55E
0x18000c55c  xor     ebx, ebx
0x18000c55e  mov     [rsp+78h+arg_18], rbx
0x18000c566  test    rbx, rbx
0x18000c569  jz      loc_18000CE1F
0x18000c56f  cmp     qword ptr [rbx+8], 0
0x18000c574  jz      loc_18000CE1F
0x18000c57a  mov     rcx, [rbx]; hMem
0x18000c57d  test    rcx, rcx
0x18000c580  jz      short loc_18000C58F
0x18000c582  call    cs:__imp_LocalFree
0x18000c588  mov     qword ptr [rbx], 0
0x18000c58f  test    r14, r14
0x18000c592  jnz     short loc_18000C59B
0x18000c594  xor     ebp, ebp
0x18000c596  jmp     loc_18000C6DB
0x18000c59b  xor     esi, esi
0x18000c59d  mov     edx, 1
0x18000c5a2  mov     rcx, [r14]
0x18000c5a5  test    rcx, rcx
0x18000c5a8  jz      short loc_18000C5DF
0x18000c5aa  mov     r8, r14
0x18000c5ad  inc     edx
0x18000c5af  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000c5b6  nop     word ptr [rax+rax+00000000h]
0x18000c5c0  lea     rax, [rax+1]
0x18000c5c4  cmp     word ptr [rcx+rax*2], 0
0x18000c5c9  jnz     short loc_18000C5C0
0x18000c5cb  lea     rsi, [rsi+rax*2]
0x18000c5cf  add     rsi, 2
0x18000c5d3  add     r8, 8
0x18000c5d7  mov     rcx, [r8]
0x18000c5da  test    rcx, rcx
0x18000c5dd  jnz     short loc_18000C5AD
0x18000c5df  mov     eax, edx
0x18000c5e1  lea     rdi, ds:0[rax*8]
  ... truncated ...
```
