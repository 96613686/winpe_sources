# SearchDSObject(ushort const *,ulong,void *,_GROUP_POLICY_OBJECTW * *,_GROUP_POLICY_OBJECTW * *,_SCOPEOFMGMT * *,_GPCONTAINER * *,int,_GPO_LINK,ldap *,ldapmsg *,int *,void *,_GPOINFO *,int)

- ea: `0x18003e060`
- end: `0x18003ee24`
- name: `?SearchDSObject@@YAHPEBGKPEAXPEAPEAU_GROUP_POLICY_OBJECTW@@2PEAPEAU_SCOPEOFMGMT@@PEAPEAU_GPCONTAINER@@HW4_GPO_LINK@@PEAUldap@@PEAUldapmsg@@PEAH1PEAU_GPOINFO@@H@Z`
- size: `3524`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, unsigned int@<edx>, void *@<r8>, struct _GROUP_POLICY_OBJECTW **@<r9>, struct _GROUP_POLICY_OBJECTW **, struct _SCOPEOFMGMT **, struct _GPCONTAINER **, int, enum _GPO_LINK, struct ldap *, struct ldapmsg *, int *, void *, struct _GPOINFO *, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800147b0`
- `0x18002d188`

## callees

- `0x180018ed4`
- `0x180030bcc`
- `0x18003a810`
- `0x18003cfa0`
- `0x18003d8d0`
- `0x18003e060`
- `0x18003ee2c`
- `0x180058cf8`
- `0x18006f894`
- `0x180073984`
- `0x180075ec0`
- `0x18007d320`
- `0x180095314`
- `0x1800ba1ec`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003edf9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003edf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e1fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e298`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e67a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e7fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e81a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e84d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eb83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ebee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e1fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e298`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e67a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e7fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e81a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e84d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eb83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ebee`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18003e53c`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18003e53c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003e7e8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003e7e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003eddd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003eddd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003e4e4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003e4e4`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003e45a`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003e5c5`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003e45a`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003e5c5`
- `WLDAP32!__imp_ldap_msgfree` at `0x18003e6f6`
- `WLDAP32!__imp_ldap_msgfree` at `0x18003edf0`
- `WLDAP32!__imp_ldap_msgfree` at `0x18003e6f6`
- `WLDAP32!__imp_ldap_msgfree` at `0x18003edf0`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18003e71b`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18003e750`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18003e71b`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18003e750`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x18003e377`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x18003e377`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003e73c`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003e86a`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003e90a`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003ec4a`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003e73c`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003e86a`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003e90a`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003ec4a`

## string_xrefs

- `0x18003e183`: `nTSecurityDescriptor`
- `0x18003e13f`: `gPLink`
- `0x18003e47a`: `SearchDSObject:  Too many linked GPOs in search.`
- `0x18003e49f`: `SearchDSObject:  Too many linked GPOs in search.`
- `0x18003e6a5`: `SearchDSObject: Access denied in planning mode to SOM <%s>`
- `0x18003e6cd`: `SearchDSObject: Access denied in planning mode to SOM <%s>`
- `0x18003e823`: `SearchDSObject:  Failed to allocate memory for full DS Object path name with %d`
- `0x18003e856`: `SearchDSObject:  Failed to allocate memory for full DS Object path name with %d`
- `0x18003eba3`: `SearchDSObject:  Unable to allocate memory for GpLink object.  Leaving. `
- `0x18003ebd4`: `SearchDSObject:  Unable to allocate memory for GpLink object.  Leaving. `
- `0x18003ea21`: `SearchDSObject:  The link to GPO %s is disabled.  It will be skipped for processing.`
- `0x18003ea4f`: `SearchDSObject:  The link to GPO %s is disabled.  It will be skipped for processing.`
- `0x18003ea8c`: `SearchDSObject:  The link to GPO %s is disabled. GPO is still being queried. Planning mode.`
- `0x18003eab8`: `SearchDSObject:  The link to GPO %s is disabled. GPO is still being queried. Planning mode.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SearchDSObject(
        unsigned __int16 *a1,
        signed int a2,
        void *a3,
        struct _GROUP_POLICY_OBJECTW **a4,
        struct _GROUP_POLICY_OBJECTW **a5,
        struct _SCOPEOFMGMT **a6,
        struct _GPCONTAINER **a7,
        int a8,
        enum _GPO_LINK a9,
        struct ldap *a10,
        struct ldapmsg *a11,
        int *a12,
        void *a13,
        struct _GPOINFO *a14,
        int a15)
{
  struct _SCOPEOFMGMT **v16; // rsi
  unsigned int v17; // edi
  struct _SCOPEOFMGMT *v18; // r14
  int v19; // r13d
  DWORD LastError; // ebx
  struct _SCOPEOFMGMT *v21; // rax
  int v22; // esi
  unsigned __int16 *v23; // r15
  LDAPMessage *v24; // rdx
  ULONG v25; // eax
  ULONG v26; // edi
  struct _GPOINFO *v27; // rsi
  int v28; // edi
  int v29; // r15d
  int v30; // r13d
  unsigned int i; // edi
  unsigned int v32; // esi
  int *v33; // r8
  LDAP *v34; // rdi
  const unsigned __int16 **valuesW; // rax
  PWCHAR *v36; // r10
  PWCHAR *v37; // rax
  PWCHAR *v38; // r13
  PWCHAR v39; // rdi
  unsigned __int64 v40; // rsi
  __int64 v41; // rsi
  unsigned __int16 *v42; // rax
  void (*v43)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v44; // eax
  DWORD v45; // eax
  __int64 v46; // rdx
  const wchar_t *v47; // r8
  unsigned __int64 v48; // r9
  unsigned __int16 *v49; // rcx
  wchar_t v50; // ax
  WCHAR v51; // ax
  unsigned __int16 *v52; // rcx
  int v53; // edx
  unsigned __int16 *v54; // rdi
  unsigned __int16 v55; // ax
  unsigned __int16 *v56; // rdi
  unsigned __int16 *v57; // rcx
  int v58; // edx
  unsigned __int16 v59; // ax
  unsigned int v60; // eax
  unsigned int v61; // r15d
  unsigned __int16 **v62; // rcx
  __int64 v63; // rax
  unsigned __int16 ***v64; // rdx
  int v65; // r14d
  struct _GROUP_POLICY_OBJECTW **v66; // r9
  struct _GROUP_POLICY_OBJECTW *v67; // rcx
  struct _GROUP_POLICY_OBJECTW **v68; // rdx
  struct _GROUP_POLICY_OBJECTW *v69; // rcx
  int v71; // [rsp+A0h] [rbp-80h]
  int v72; // [rsp+ACh] [rbp-74h] BYREF
  unsigned __int16 *v73; // [rsp+B0h] [rbp-70h]
  PLDAPMessage entry; // [rsp+B8h] [rbp-68h] BYREF
  LDAP *ld; // [rsp+C0h] [rbp-60h]
  int v76; // [rsp+C8h] [rbp-58h]
  unsigned int v77; // [rsp+CCh] [rbp-54h]
  struct _SCOPEOFMGMT *v78; // [rsp+D0h] [rbp-50h]
  struct _GPOINFO *v79; // [rsp+D8h] [rbp-48h]
  int *v80; // [rsp+E0h] [rbp-40h]
  struct _GROUP_POLICY_OBJECTW *v81; // [rsp+E8h] [rbp-38h] BYREF
  struct _GROUP_POLICY_OBJECTW *v82; // [rsp+F0h] [rbp-30h] BYREF
  void *v83; // [rsp+F8h] [rbp-28h]
  PWCHAR *vals; // [rsp+100h] [rbp-20h]
  struct _SCOPEOFMGMT **v85; // [rsp+108h] [rbp-18h]
  _QWORD v86[3]; // [rsp+110h] [rbp-10h] BYREF
  char v87; // [rsp+128h] [rbp+8h]
  int v88; // [rsp+129h] [rbp+9h]
  __int16 v89; // [rsp+12Dh] [rbp+Dh]
  char v90; // [rsp+12Fh] [rbp+Fh]
  struct _GPCONTAINER **v91; // [rsp+130h] [rbp+10h]
  void *v92; // [rsp+138h] [rbp+18h]
  struct _GROUP_POLICY_OBJECTW **v93; // [rsp+140h] [rbp+20h]
  struct _GROUP_POLICY_OBJECTW **v94; // [rsp+148h] [rbp+28h]
  PLDAPControlW ServerControls[2]; // [rsp+150h] [rbp+30h] BYREF
  _QWORD v96[12]; // [rsp+160h] [rbp+40h] BYREF
  PWSTR attrs[2]; // [rsp+1C0h] [rbp+A0h] BYREF
  __int128 *v98; // [rsp+1D0h] [rbp+B0h]
  __int64 v99; // [rsp+1D8h] [rbp+B8h]
  int v100; // [rsp+1E0h] [rbp+C0h] BYREF
  char v101; // [rsp+1E4h] [rbp+C4h]
  WCHAR v102[8]; // [rsp+1E8h] [rbp+C8h] BYREF
  WCHAR attr[12]; // [rsp+1F8h] [rbp+D8h] BYREF
  unsigned __int16 v104[12]; // [rsp+210h] [rbp+F0h] BYREF
  __int128 v105; // [rsp+228h] [rbp+108h] BYREF
  _OWORD v106[2]; // [rsp+238h] [rbp+118h]
  unsigned __int16 v107[512]; // [rsp+260h] [rbp+140h] BYREF

  v94 = a4;
  v92 = a3;
  v77 = a2;
  v16 = a6;
  v85 = a6;
  v93 = a5;
  v91 = a7;
  ld = a10;
  entry = a11;
  v80 = a12;
  v83 = a13;
  v79 = a14;
  v82 = 0;
  v81 = 0;
  v17 = 0;
  v71 = 0;
  v86[0] = L"1.2.840.113556.1.4.801";
  v86[1] = 5;
  v86[2] = &v100;
  v87 = 1;
  v88 = 0;
  v89 = 0;
  v90 = 0;
  ServerControls[0] = (PLDAPControlW)v86;
  ServerControls[1] = 0;
  wcscpy(v102, L"gPLink");
  wcscpy(attr, L"gPOptions");
  v105 = *(_OWORD *)L"nTSecurityDescriptor";
  v106[0] = *(_OWORD *)L"tyDescriptor";
  *(_OWORD *)((char *)v106 + 10) = *(_OWORD *)L"criptor";
  attrs[0] = v102;
  attrs[1] = attr;
  v98 = &v105;
  v99 = 0;
  v18 = 0;
  v78 = 0;
  if ( a2 >= 0 || (v19 = 1, (a2 & 0x800000) == 0) )
    v19 = 0;
  v76 = v19;
  LastError = GetLastError();
  v100 = 16909104;
  v101 = 7;
  if ( !a13 )
  {
    v98 = 0;
    ServerControls[0] = 0;
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"SearchDSObject:  Searching <%s>", a1);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"SearchDSObject:  Searching <%s>", a1);
    }
  }
  if ( !a6 )
    goto LABEL_22;
  v21 = AllocSOM(a1);
  v18 = v21;
  v78 = v21;
  if ( v21 )
  {
    *((_DWORD *)v21 + 2) = a9;
    *((_DWORD *)v21 + 4) = *v80;
LABEL_22:
    v23 = 0;
    v73 = 0;
    v24 = entry;
    if ( !entry )
    {
      v71 = 1;
      v25 = ldap_search_ext_sW(ld, a1, 0, szDSClassAny, attrs, 0, ServerControls, 0, &MAX_LDAP_SEARCH_TIME, 0, &entry);
      v26 = v25;
      if ( v25 )
      {
        if ( v25 == 16 )
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(4u, L"SearchDSObject:  No GPO(s) for this object.");
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(4u, L"SearchDSObject:  No GPO(s) for this object.");
            }
          }
        }
        else
        {
          if ( v25 != 32 )
          {
            if ( v25 == 4 )
            {
              LastError = LdapMapErrorToWin32(4u);
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                if ( g_lpDebugMsg )
                {
                  g_lpDebugMsg(2u, L"SearchDSObject:  Too many linked GPOs in search.");
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  RedirectDebugMsg(2u, L"SearchDSObject:  Too many linked GPOs in search.");
                }
              }
              LogLdapServerError(ld, entry);
              if ( a15 && (v27 = v79) != 0 )
              {
                v28 = *((_DWORD *)v79 + 64);
                v29 = GetTickCount() - v28;
                v30 = *((_DWORD *)v27 + 70);
                for ( i = 0; i < 6; ++i )
                {
                  if ( FindNLSString(
                         0x7Fu,
                         0x200001u,
                         L"ds\\grouppolicy\\client\\gpsvc\\engine\\gpqry.cpp",
                         -1,
                         (LPCWSTR)*(&GPSourceFileNameIdTable + 2 * i),
                         -1,
                         0) != -1 )
                  {
                    v32 = *((_DWORD *)&GPSourceFileNameIdTable + 4 * i + 2);
                    goto LABEL_53;
                  }
                }
                v32 = -1;
LABEL_53:
                CGPAdminEventLdapFailure::CGPAdminEventLdapFailure(
                  (CGPAdminEventGenericFailure *)v96,
                  (__int64)gpEvent_TOO_MANY_GPOS,
                  v32,
                  0x550u,
                  v30,
                  v29,
                  4u);
                CGPPolicyEventReporting::Report(
                  *((CGPPolicyEventReporting **)v79 + 34),
                  (struct CGPEventInfo *)v96,
                  v33);
                v96[0] = &CGPAdminEventLdapFailure::`vftable';
                CGPAdminEventInitFailure::~CGPAdminEventInitFailure((CGPAdminEventInitFailure *)v96);
                v23 = v73;
                v17 = (unsigned int)v73;
LABEL_166:
                v18 = v78;
              }
              else
              {
LABEL_155:
                v17 = 0;
              }
            }
            else
            {
              LastError = LdapMapErrorToWin32(v25);
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                if ( g_lpDebugMsg )
                {
                  g_lpDebugMsg(4u, L"SearchDSObject:  Failed to find DS object <%s> due to error %d.", a1, v26);
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  RedirectDebugMsg(4u, L"SearchDSObject:  Failed to find DS object <%s> due to error %d.", a1, v26);
                }
              }
              LogLdapServerError(ld, entry);
              v17 = 0;
            }
            goto LABEL_167;
          }
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(4u, L"SearchDSObject:  Object not found in DS (this is ok).  Leaving. ");
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(4u, L"SearchDSObject:  Object not found in DS (this is ok).  Leaving. ");
            }
          }
        }
        goto LABEL_197;
      }
      v24 = entry;
      v17 = 0;
    }
    if ( a6 && v83 && !v19 )
    {
      v72 = 0;
      if ( !(unsigned int)CheckOUAccess(ld, v24, v83, &v72) )
      {
        LastError = GetLastError();
        goto LABEL_167;
      }
      if ( !v72 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"SearchDSObject: Access denied in planning mode to SOM <%s>", a1);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"SearchDSObject: Access denied in planning mode to SOM <%s>", a1);
          }
        }
        if ( !entry )
          goto LABEL_167;
        v22 = v71;
        if ( v71 )
        {
          ldap_msgfree(entry);
          entry = 0;
        }
        goto LABEL_168;
      }
      v24 = entry;
    }
    v72 = 0;
    v34 = ld;
    valuesW = (const unsigned __int16 **)ldap_get_valuesW(ld, v24, attr);
    if ( valuesW && *valuesW )
    {
      v72 = StringToInt(*valuesW);
      ldap_value_freeW(v36);
    }
    v37 = ldap_get_valuesW(v34, entry, v102);
    v38 = v37;
    vals = v37;
    if ( !v37 || (v39 = *v37) == 0 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"SearchDSObject:  No GPO(s) for this object.");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"SearchDSObject:  No GPO(s) for this object.");
        }
      }
LABEL_176:
      if ( (v72 & 1) != 0 )
      {
        *v80 = 1;
        if ( v16 )
          *((_DWORD *)v18 + 3) = 1;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"SearchDSObject:  <%s> has the Block From Above attribute set", a1);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"SearchDSObject:  <%s> has the Block From Above attribute set", a1);
          }
        }
      }
      v67 = v81;
      if ( v81 )
      {
        if ( v81->pNext )
        {
          do
            v67 = v67->pNext;
          while ( v67->pNext );
        }
        v68 = v93;
        v67->pNext = *v93;
        if ( *v68 )
          (*v68)->pPrev = v67;
        *v68 = v81;
      }
      if ( v82 )
      {
        v69 = *v94;
        if ( *v94 )
        {
          for ( ; v69->pNext; v69 = v69->pNext )
            ;
          v69->pNext = v82;
          v82->pPrev = v69;
        }
        else
        {
          *v94 = v82;
        }
      }
LABEL_197:
      v17 = 1;
      if ( v16 )
      {
        *((_QWORD *)v18 + 4) = *v16;
        *v16 = v18;
      }
      v22 = v71;
      goto LABEL_200;
    }
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"SearchDSObject:  Found GPO(s):  <%s>", v39);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"SearchDSObject:  Found GPO(s):  <%s>", v39);
      }
    }
    v40 = 0;
    if ( a1 )
    {
      v41 = -1;
      do
        ++v41;
      while ( a1[v41] );
      v40 = v41 + 8;
    }
    v42 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v40);
    v23 = v42;
    v73 = v42;
    if ( !v42 )
    {
      LastError = GetLastError();
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v43 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v44 = GetLastError();
          v43(2u, L"SearchDSObject:  Failed to allocate memory for full DS Object path name with %d", v44);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v45 = GetLastError();
          RedirectDebugMsg(2u, L"SearchDSObject:  Failed to allocate memory for full DS Object path name with %d", v45);
        }
      }
      ldap_value_freeW(v38);
      v17 = 0;
      goto LABEL_167;
    }
    if ( v40 )
    {
      if ( v40 <= 0x7FFFFFFF )
      {
        v46 = 2147483646;
        v47 = L"LDAP://";
        v48 = v40;
        v49 = v42;
        do
        {
          if ( !v46 )
            goto LABEL_109;
          v50 = *v47;
          if ( !*v47 )
            goto LABEL_109;
          ++v47;
          *v49++ = v50;
          --v46;
          --v48;
        }
        while ( v48 );
        --v49;
LABEL_109:
        *v49 = 0;
      }
      else
      {
        *v42 = 0;
      }
    }
    StringCchCatW(v23, v40, a1);
    while ( 1 )
    {
      v51 = *v39;
      if ( !*v39 )
        goto LABEL_114;
      while ( v51 != 91 )
      {
        v51 = *++v39;
        if ( !*v39 )
          goto LABEL_114;
      }
      if ( !*v39 )
        goto LABEL_114;
      v52 = v107;
      v53 = 511;
      v54 = v39 + 1;
      do
      {
        v55 = *v54;
        if ( !*v54 )
          break;
        if ( v55 == 59 )
          break;
        ++v54;
        *v52++ = v55;
        --v53;
      }
      while ( v53 );
      if ( *v54 != 59 )
        goto LABEL_114;
      *v52 = 0;
      v56 = v54 + 1;
      v57 = v104;
      v58 = 11;
      v104[0] = 0;
      do
      {
        v59 = *v56;
        if ( !*v56 )
          break;
        if ( v59 == 93 )
          break;
        ++v56;
        *v57++ = v59;
        --v58;
      }
      while ( v58 );
      if ( *v56 != 93 )
      {
LABEL_114:
        ldap_value_freeW(vals);
        v16 = v85;
        v23 = v73;
        goto LABEL_176;
      }
      *v57 = 0;
      v60 = StringToInt(v104);
      v61 = v60;
      if ( v85 )
      {
        v62 = AllocGpLink(v107, v60);
        if ( !v62 )
        {
          LastError = GetLastError();
          if ( !*(_DWORD *)&g_dwDebugLevel )
          {
LABEL_154:
            v23 = v73;
            goto LABEL_155;
          }
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"SearchDSObject:  Unable to allocate memory for GpLink object.  Leaving. ");
            goto LABEL_154;
          }
          if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
            goto LABEL_154;
          RedirectDebugMsg(2u, L"SearchDSObject:  Unable to allocate memory for GpLink object.  Leaving. ");
          v23 = v73;
          v17 = 0;
LABEL_167:
          v22 = v71;
LABEL_168:
          if ( v18 )
            FreeSOM(v18);
LABEL_200:
          if ( v23 )
            LocalFree(v23);
          goto LABEL_202;
        }
        v63 = *((_QWORD *)v18 + 3);
        if ( v63 )
        {
          do
          {
            v64 = (unsigned __int16 ***)(v63 + 16);
            v63 = *(_QWORD *)(v63 + 16);
          }
          while ( v63 );
          *v64 = v62;
        }
        else
        {
          *((_QWORD *)v18 + 3) = v62;
        }
      }
      v65 = 1;
      if ( (v61 & 1) != 0 && !v76 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(
              4u,
              L"SearchDSObject:  The link to GPO %s is disabled.  It will be skipped for processing.",
              v107);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(
              4u,
              L"SearchDSObject:  The link to GPO %s is disabled.  It will be skipped for processing.",
              v107);
          }
        }
        if ( (v77 & 0x800000) == 0 )
          goto LABEL_150;
        v65 = 0;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(
              4u,
              L"SearchDSObject:  The link to GPO %s is disabled. GPO is still being queried. Planning mode.",
              v107);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(
              4u,
              L"SearchDSObject:  The link to GPO %s is disabled. GPO is still being queried. Planning mode.",
              v107);
          }
        }
      }
      v66 = &v81;
      if ( (v61 & 2) != 0 )
        v66 = &v82;
      if ( !(unsigned int)ProcessGPO(
                            v107,
                            v77,
                            v92,
                            v66,
                            v91,
                            v61,
                            1,
                            a8,
                            a9,
                            v73,
                            ld,
                            0,
                            *v80,
                            v83,
                            0,
                            0,
                            v65,
                            v79,
                            a15) )
      {
        LastError = GetLastError();
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"SearchDSObject:  ProcessGPO failed.");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"SearchDSObject:  ProcessGPO failed.");
          }
        }
        ldap_value_freeW(vals);
        v23 = v73;
        v17 = 0;
        goto LABEL_166;
      }
LABEL_150:
      v39 = v56 + 1;
      v18 = v78;
    }
  }
  LastError = GetLastError();
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"SearchDSObject:  Unable to allocate memory for SOM object.  Leaving. ");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(2u, L"SearchDSObject:  Unable to allocate memory for SOM object.  Leaving. ");
      v22 = 0;
      goto LABEL_202;
    }
  }
  v22 = 0;
LABEL_202:
  if ( entry && v22 )
    ldap_msgfree(entry);
  SetLastError(LastError);
  return v17;
}

```

## disassembly

```asm
0x18003e060  push    rbp
0x18003e062  push    rbx
0x18003e063  push    rsi
0x18003e064  push    rdi
0x18003e065  push    r12
0x18003e067  push    r13
0x18003e069  push    r14
0x18003e06b  push    r15
0x18003e06d  lea     rbp, [rsp-558h]
0x18003e075  sub     rsp, 678h
0x18003e07c  mov     rax, cs:__security_cookie
0x18003e083  xor     rax, rsp
0x18003e086  mov     [rbp+590h+var_50], rax
0x18003e08d  mov     [rbp+590h+var_568], r9
0x18003e091  mov     [rbp+590h+var_578], r8
0x18003e095  mov     [rbp+590h+var_5E4], edx
0x18003e098  mov     r12, rcx
0x18003e09b  mov     rsi, [rbp+590h+arg_28]
0x18003e0a2  mov     [rbp+590h+var_5A8], rsi
0x18003e0a6  mov     rax, [rbp+590h+arg_20]
0x18003e0ad  mov     [rbp+590h+var_570], rax
0x18003e0b1  mov     rax, [rbp+590h+arg_30]
0x18003e0b8  mov     [rbp+590h+var_580], rax
0x18003e0bc  mov     rax, [rbp+590h+arg_48]
0x18003e0c3  mov     [rbp+590h+ld], rax
0x18003e0c7  mov     rax, [rbp+590h+arg_50]
0x18003e0ce  mov     [rbp+590h+entry], rax
0x18003e0d2  mov     rax, [rbp+590h+arg_58]
0x18003e0d9  mov     [rbp+590h+var_5D0], rax
0x18003e0dd  mov     r15, [rbp+590h+arg_60]
0x18003e0e4  mov     [rbp+590h+var_5B8], r15
0x18003e0e8  mov     rax, [rbp+590h+arg_68]
0x18003e0ef  mov     [rbp+590h+var_5D8], rax
0x18003e0f3  xor     ecx, ecx
0x18003e0f5  mov     [rbp+590h+var_5C0], rcx
0x18003e0f9  mov     [rbp+590h+var_5C8], rcx
0x18003e0fd  mov     edi, ecx
0x18003e0ff  mov     [rbp+590h+var_60C], ecx
0x18003e102  mov     [rbp+590h+var_610], ecx
0x18003e105  lea     rax, a12840113556148; "1.2.840.113556.1.4.801"
0x18003e10c  mov     [rbp+590h+var_5A0], rax
0x18003e110  mov     [rbp+590h+var_598], 5
0x18003e118  lea     rax, [rbp+590h+var_4D0]
0x18003e11f  mov     [rbp+590h+var_590], rax
0x18003e123  mov     [rbp+590h+var_588], 1
0x18003e127  xor     eax, eax
0x18003e129  mov     [rbp+590h+var_587], eax
0x18003e12c  mov     [rbp+590h+var_583], ax
0x18003e130  mov     [rbp+590h+var_581], al
0x18003e133  lea     rax, [rbp+590h+var_5A0]
0x18003e137  mov     [rbp+590h+var_560], rax
0x18003e13b  mov     [rbp+590h+var_558], rcx
0x18003e13f  movsd   xmm0, qword ptr cs:aGplink; "gPLink"
0x18003e147  movsd   qword ptr [rbp+590h+var_4C8], xmm0
0x18003e14f  mov     eax, dword ptr cs:aGplink+8; "nk"
0x18003e155  mov     [rbp+590h+var_4C0], eax
0x18003e15b  movzx   eax, word ptr cs:aGplink+0Ch; ""
0x18003e162  mov     [rbp+590h+var_4BC], ax
0x18003e169  movups  xmm0, xmmword ptr cs:aGpoptions; "gPOptions"
0x18003e170  movups  xmmword ptr [rbp+590h+attr], xmm0
0x18003e177  mov     eax, dword ptr cs:aGpoptions+10h; "s"
0x18003e17d  mov     [rbp+590h+var_4A8], eax
0x18003e183  movups  xmm0, xmmword ptr cs:aNtsecuritydesc; "nTSecurityDescriptor"
0x18003e18a  movups  [rbp+590h+var_488], xmm0
0x18003e191  movups  xmm1, xmmword ptr cs:aNtsecuritydesc+10h; "tyDescriptor"
0x18003e198  movups  xmmword ptr [rbp+590h+var_478], xmm1
0x18003e19f  movups  xmm0, xmmword ptr cs:aNtsecuritydesc+1Ah; "criptor"
0x18003e1a6  movups  xmmword ptr [rbp+590h+var_478+0Ah], xmm0
0x18003e1ad  lea     rax, [rbp+590h+var_4C8]
0x18003e1b4  mov     [rbp+590h+var_4F0], rax
0x18003e1bb  lea     rax, [rbp+590h+attr]
0x18003e1c2  mov     [rbp+590h+var_4E8], rax
0x18003e1c9  lea     rax, [rbp+590h+var_488]
0x18003e1d0  mov     [rbp+590h+var_4E0], rax
0x18003e1d7  mov     [rbp+590h+var_4D8], rcx
0x18003e1de  mov     r14d, ecx
0x18003e1e1  mov     [rbp+590h+var_5E0], rcx
0x18003e1e5  test    edx, edx
0x18003e1e7  jns     short loc_18003E1F5
0x18003e1e9  bt      edx, 17h
0x18003e1ed  mov     r13d, 1
0x18003e1f3  jb      short loc_18003E1F8
0x18003e1f5  mov     r13d, ecx
0x18003e1f8  mov     [rbp+590h+var_5E8], r13d
0x18003e1fc  call    cs:__imp_GetLastError
0x18003e202  mov     ebx, eax
0x18003e204  mov     [rbp+590h+var_608], eax
0x18003e207  mov     [rbp+590h+var_4D0], 1020330h
0x18003e211  mov     [rbp+590h+var_4CC], 7
0x18003e218  test    r15, r15
0x18003e21b  jnz     short loc_18003E228
0x18003e21d  mov     [rbp+590h+var_4E0], r15
0x18003e224  mov     [rbp+590h+var_560], r15
0x18003e228  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18003e22f  jz      short loc_18003E27B
0x18003e231  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003e238  test    rax, rax
0x18003e23b  jz      short loc_18003E253
0x18003e23d  mov     r8, r12
0x18003e240  lea     rdx, aSearchdsobject; "SearchDSObject:  Searching <%s>"
0x18003e247  mov     ecx, 4
0x18003e24c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e251  jmp     short loc_18003E27B
0x18003e253  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x18003e25b  jz      short loc_18003E27B
0x18003e25d  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18003e265  jz      short loc_18003E27B
0x18003e267  mov     r8, r12
0x18003e26a  lea     rdx, aSearchdsobject; "SearchDSObject:  Searching <%s>"
0x18003e271  mov     ecx, 4; unsigned int
0x18003e276  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18003e27b  test    rsi, rsi
0x18003e27e  jz      loc_18003E312
0x18003e284  mov     rcx, r12; unsigned __int16 *
0x18003e287  call    ?AllocSOM@@YAPEAU_SCOPEOFMGMT@@PEBG@Z; AllocSOM(ushort const *)
0x18003e28c  mov     r14, rax
0x18003e28f  mov     [rbp+590h+var_5E0], rax
0x18003e293  test    rax, rax
0x18003e296  jnz     short loc_18003E2FE
0x18003e298  call    cs:__imp_GetLastError
0x18003e29e  mov     ebx, eax
0x18003e2a0  mov     [rbp+590h+var_608], eax
0x18003e2a3  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18003e2aa  jz      short loc_18003E2C9
0x18003e2ac  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003e2b3  test    rax, rax
0x18003e2b6  jz      short loc_18003E2D1
0x18003e2b8  lea     rdx, aSearchdsobject_4; "SearchDSObject:  Unable to allocate mem"...
0x18003e2bf  mov     ecx, 2
0x18003e2c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e2c9  mov     esi, [rbp+590h+var_610]
0x18003e2cc  jmp     loc_18003EDE3
0x18003e2d1  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x18003e2d9  jz      short loc_18003E2C9
0x18003e2db  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18003e2e3  jz      short loc_18003E2C9
0x18003e2e5  lea     rdx, aSearchdsobject_4; "SearchDSObject:  Unable to allocate mem"...
0x18003e2ec  mov     ecx, 2; unsigned int
0x18003e2f1  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18003e2f6  mov     esi, [rbp+590h+var_610]
0x18003e2f9  jmp     loc_18003EDE3
0x18003e2fe  mov     eax, [rbp+590h+arg_40]
0x18003e304  mov     [r14+8], eax
0x18003e308  mov     rax, [rbp+590h+var_5D0]
0x18003e30c  mov     eax, [rax]
0x18003e30e  mov     [r14+10h], eax
0x18003e312  xor     r15d, r15d
0x18003e315  mov     [rbp+590h+var_600], r15
0x18003e319  mov     rdx, [rbp+590h+entry]
0x18003e31d  test    rdx, rdx
0x18003e320  jnz     loc_18003E643
0x18003e326  mov     [rbp+590h+var_610], 1
0x18003e32d  lea     rax, [rbp+590h+entry]
0x18003e331  mov     [rsp+6B0h+res], rax; res
0x18003e336  mov     [rsp+6B0h+SizeLimit], r15d; SizeLimit
0x18003e33b  lea     rax, ?MAX_LDAP_SEARCH_TIME@@3Ul_timeval@@A; l_timeval MAX_LDAP_SEARCH_TIME
0x18003e342  mov     [rsp+6B0h+timeout], rax; timeout
0x18003e347  mov     [rsp+6B0h+ClientControls], r15; ClientControls
0x18003e34c  lea     rax, [rbp+590h+var_560]
0x18003e350  mov     [rsp+6B0h+ServerControls], rax; ServerControls
0x18003e355  mov     [rsp+6B0h+attrsonly], r15d; attrsonly
0x18003e35a  lea     rax, [rbp+590h+var_4F0]
0x18003e361  mov     [rsp+6B0h+attrs], rax; attrs
0x18003e366  lea     r9, ?szDSClassAny@@3PAGA; "(objectClass=*)"
0x18003e36d  xor     r8d, r8d; scope
0x18003e370  mov     rdx, r12; base
0x18003e373  mov     rcx, [rbp+590h+ld]; ld
0x18003e377  call    cs:__imp_ldap_search_ext_sW
0x18003e37d  mov     edi, eax
0x18003e37f  test    eax, eax
0x18003e381  jz      loc_18003E63C
0x18003e387  cmp     eax, 10h
0x18003e38a  jnz     short loc_18003E3EB
0x18003e38c  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x18003e393  jz      loc_18003EDBE
0x18003e399  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003e3a0  test    rax, rax
0x18003e3a3  jz      short loc_18003E3BB
0x18003e3a5  lea     rdx, aSearchdsobject_3; "SearchDSObject:  No GPO(s) for this obj"...
0x18003e3ac  mov     ecx, 4
0x18003e3b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e3b6  jmp     loc_18003EDBE
0x18003e3bb  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x18003e3c2  jz      loc_18003EDBE
0x18003e3c8  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18003e3cf  jz      loc_18003EDBE
0x18003e3d5  lea     rdx, aSearchdsobject_3; "SearchDSObject:  No GPO(s) for this obj"...
0x18003e3dc  mov     ecx, 4; unsigned int
0x18003e3e1  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18003e3e6  jmp     loc_18003EDBE
0x18003e3eb  cmp     edi, 20h ; ' '
0x18003e3ee  jnz     short loc_18003E44F
0x18003e3f0  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x18003e3f7  jz      loc_18003EDBE
0x18003e3fd  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003e404  test    rax, rax
0x18003e407  jz      short loc_18003E41F
0x18003e409  lea     rdx, aSearchdsobject_7; "SearchDSObject:  Object not found in DS"...
0x18003e410  mov     ecx, 4
0x18003e415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e41a  jmp     loc_18003EDBE
0x18003e41f  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x18003e426  jz      loc_18003EDBE
0x18003e42c  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18003e433  jz      loc_18003EDBE
0x18003e439  lea     rdx, aSearchdsobject_7; "SearchDSObject:  Object not found in DS"...
0x18003e440  mov     ecx, 4; unsigned int
0x18003e445  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18003e44a  jmp     loc_18003EDBE
0x18003e44f  cmp     edi, 4
0x18003e452  jnz     loc_18003E5C3
0x18003e458  mov     ecx, edi; LdapError
0x18003e45a  call    cs:__imp_LdapMapErrorToWin32
0x18003e460  mov     ebx, eax
0x18003e462  mov     [rbp+590h+var_608], eax
0x18003e465  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x18003e46c  jz      short loc_18003E4B0
0x18003e46e  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003e475  test    rax, rax
0x18003e478  jz      short loc_18003E48D
0x18003e47a  lea     rdx, aSearchdsobject_9; "SearchDSObject:  Too many linked GPOs i"...
0x18003e481  mov     ecx, 2
0x18003e486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e48b  jmp     short loc_18003E4B0
0x18003e48d  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x18003e494  jz      short loc_18003E4B0
0x18003e496  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18003e49d  jz      short loc_18003E4B0
0x18003e49f  lea     rdx, aSearchdsobject_9; "SearchDSObject:  Too many linked GPOs i"...
0x18003e4a6  mov     ecx, 2; unsigned int
0x18003e4ab  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18003e4b0  mov     rdx, [rbp+590h+entry]; struct ldapmsg *
0x18003e4b4  mov     rcx, [rbp+590h+ld]; struct ldap *
0x18003e4b8  call    ?LogLdapServerError@@YAXPEAUldap@@PEAUldapmsg@@@Z; LogLdapServerError(ldap *,ldapmsg *)
0x18003e4bd  cmp     [rbp+590h+arg_70], r15d
0x18003e4c4  jz      loc_18003EBB8
0x18003e4ca  mov     rsi, [rbp+590h+var_5D8]
0x18003e4ce  test    rsi, rsi
0x18003e4d1  jz      loc_18003EBB8
0x18003e4d7  mov     r12, [rsi+108h]
0x18003e4de  mov     edi, [rsi+100h]
0x18003e4e4  call    cs:__imp_GetTickCount
0x18003e4ea  mov     r15d, eax
0x18003e4ed  sub     r15d, edi
0x18003e4f0  mov     r13d, [rsi+118h]
0x18003e4f7  xor     edi, edi
0x18003e4f9  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18003e500  lea     rax, ?GPSourceFileNameIdTable@@3PAU_GP_SOURCE_FILE_NAME_ID_ENTRY@@A; _GP_SOURCE_FILE_NAME_ID_ENTRY near * GPSourceFileNameIdTable
0x18003e507  cmp     edi, 6
0x18003e50a  jnb     short loc_18003E558
0x18003e50c  mov     r14d, edi
0x18003e50f  add     r14, r14
0x18003e512  mov     [rsp+6B0h+ServerControls], 0; pcchFound
0x18003e51b  mov     [rsp+6B0h+attrsonly], esi; cchValue
0x18003e51f  mov     rax, [rax+r14*8]
0x18003e523  mov     [rsp+6B0h+attrs], rax; lpStringValue
0x18003e528  mov     r9d, esi; cchSource
0x18003e52b  lea     r8, aDsGrouppolicyC_7; "ds\\grouppolicy\\client\\gpsvc\\engine"...
0x18003e532  mov     edx, 200001h; dwFindNLSStringFlags
0x18003e537  mov     ecx, 7Fh; Locale
0x18003e53c  call    cs:__imp_FindNLSString
0x18003e542  cmp     eax, esi
0x18003e544  jnz     short loc_18003E54A
0x18003e546  inc     edi
0x18003e548  jmp     short loc_18003E500
0x18003e54a  lea     rsi, ?GPSourceFileNameIdTable@@3PAU_GP_SOURCE_FILE_NAME_ID_ENTRY@@A; _GP_SOURCE_FILE_NAME_ID_ENTRY near * GPSourceFileNameIdTable
0x18003e551  mov     esi, [rsi+r14*8+8]
0x18003e556  jmp     short loc_18003E55D
0x18003e558  mov     esi, 0FFFFFFFFh
0x18003e55d  mov     [rsp+6B0h+ClientControls], r12
0x18003e562  mov     dword ptr [rsp+6B0h+ServerControls], 4
0x18003e56a  mov     [rsp+6B0h+attrsonly], r15d
0x18003e56f  mov     dword ptr [rsp+6B0h+attrs], r13d
0x18003e574  mov     r9d, 550h
0x18003e57a  mov     r8d, esi
0x18003e57d  lea     rdx, gpEvent_TOO_MANY_GPOS
0x18003e584  lea     rcx, [rbp+590h+var_550]
0x18003e588  call    ??0CGPAdminEventLdapFailure@@QEAA@PEBU_EVENT_DESCRIPTOR@@KKW4ProcessingModeEnum@@KKPEBG@Z; CGPAdminEventLdapFailure::CGPAdminEventLdapFailure(_EVENT_DESCRIPTOR const *,ulong,ulong,ProcessingModeEnum,ulong,ulong,ushort const *)
0x18003e58d  nop
0x18003e58e  lea     rdx, [rbp+590h+var_550]; struct CGPEventInfo *
0x18003e592  mov     rcx, [rbp+590h+var_5D8]
0x18003e596  mov     rcx, [rcx+110h]; this
0x18003e59d  call    ?Report@CGPPolicyEventReporting@@QEAAKPEAVCGPEventInfo@@PEAH@Z; CGPPolicyEventReporting::Report(CGPEventInfo *,int *)
0x18003e5a2  nop
0x18003e5a3  lea     rax, ??_7CGPAdminEventLdapFailure@@6B@; const CGPAdminEventLdapFailure::`vftable'
0x18003e5aa  mov     [rbp+590h+var_550], rax
0x18003e5ae  lea     rcx, [rbp+590h+var_550]; this
0x18003e5b2  call    ??1CGPAdminEventInitFailure@@UEAA@XZ; CGPAdminEventInitFailure::~CGPAdminEventInitFailure(void)
0x18003e5b7  mov     r15, [rbp+590h+var_600]
0x18003e5bb  mov     edi, r15d
0x18003e5be  jmp     loc_18003EC57
0x18003e5c3  mov     ecx, edi; LdapError
0x18003e5c5  call    cs:__imp_LdapMapErrorToWin32
0x18003e5cb  mov     ebx, eax
0x18003e5cd  mov     [rbp+590h+var_608], eax
0x18003e5d0  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x18003e5d7  jz      short loc_18003E627
0x18003e5d9  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003e5e0  test    rax, rax
0x18003e5e3  jz      short loc_18003E5FE
  ... truncated ...
```
