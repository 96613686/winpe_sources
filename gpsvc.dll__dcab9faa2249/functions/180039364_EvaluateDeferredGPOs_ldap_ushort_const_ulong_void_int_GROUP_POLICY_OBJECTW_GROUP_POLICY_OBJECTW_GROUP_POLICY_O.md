# EvaluateDeferredGPOs(ldap *,ushort const *,ulong,void *,int,_GROUP_POLICY_OBJECTW *,_GROUP_POLICY_OBJECTW *,_GROUP_POLICY_OBJECTW * *,_GROUP_POLICY_OBJECTW * *,_GPCONTAINER * *,void *,CGpoFilter *,CLocator *,_GPOINFO *,int,_BANDWIDTHESTIMATE *)

- ea: `0x180039364`
- end: `0x18003a802`
- name: `?EvaluateDeferredGPOs@@YAHPEAUldap@@PEBGKPEAXHPEAU_GROUP_POLICY_OBJECTW@@3PEAPEAU2@4PEAPEAU_GPCONTAINER@@2PEAVCGpoFilter@@PEAVCLocator@@PEAU_GPOINFO@@HPEAU_BANDWIDTHESTIMATE@@@Z`
- size: `5278`
- prototype: `__int64 __fastcall(struct ldap *, const unsigned __int16 *, unsigned int, void *, int, struct _GROUP_POLICY_OBJECTW *, struct _GROUP_POLICY_OBJECTW *, struct _GROUP_POLICY_OBJECTW **, struct _GROUP_POLICY_OBJECTW **, struct _GPCONTAINER **, void *, struct CGpoFilter *, struct CLocator *, struct _GPOINFO *, int, struct _BANDWIDTHESTIMATE *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800147b0`

## callees

- `0x180003770`
- `0x18000a504`
- `0x18001dcf0`
- `0x18002c740`
- `0x180030bcc`
- `0x180039184`
- `0x180039364`
- `0x18003a810`
- `0x180067d58`
- `0x1800684c0`
- `0x18006f894`
- `0x18007060c`
- `0x180073984`
- `0x180075ec0`
- `0x18007d320`
- `0x180098c40`
- `0x1800ba1ec`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039df0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039df0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039691`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039bea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039c1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039d9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a048`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a09c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a0d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a41b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a442`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a47d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a799`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039691`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039bea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039c1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039d9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a048`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a09c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a0d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a41b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a442`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a47d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a799`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003970b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800397f5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800398c6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180039d1a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003970b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800397f5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800398c6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180039d1a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039ae7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039ae7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039d83`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039d8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039d83`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039d8e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180039ecf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003a2ae`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003a3a2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180039ecf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003a2ae`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003a3a2`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x18003985d`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x18003985d`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180039a91`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180039f41`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180039fbd`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180039a91`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180039f41`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180039fbd`
- `WLDAP32!__imp_ldap_unbind` at `0x180039fc6`
- `WLDAP32!__imp_ldap_unbind` at `0x180039fc6`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180039965`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180039aa8`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180039965`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180039aa8`
- `WLDAP32!__imp_LdapGetLastError` at `0x18003a01c`
- `WLDAP32!__imp_LdapGetLastError` at `0x18003a050`
- `WLDAP32!__imp_LdapGetLastError` at `0x18003a0a4`
- `WLDAP32!__imp_LdapGetLastError` at `0x18003a01c`
- `WLDAP32!__imp_LdapGetLastError` at `0x18003a050`
- `WLDAP32!__imp_LdapGetLastError` at `0x18003a0a4`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180039e4b`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180039f52`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180039fd4`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003a024`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003a0f6`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003a225`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003a327`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003a4a6`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180039e4b`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180039f52`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180039fd4`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003a024`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003a0f6`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003a225`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003a327`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003a4a6`
- `WLDAP32!__imp_ldap_first_entry` at `0x180039cc3`
- `WLDAP32!__imp_ldap_first_entry` at `0x180039cc3`
- `WLDAP32!__imp_ldap_next_entry` at `0x180039d69`
- `WLDAP32!__imp_ldap_next_entry` at `0x180039d69`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180039a2f`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180039a2f`
- `WLDAP32!__imp_ldap_connect` at `0x180039980`
- `WLDAP32!__imp_ldap_connect` at `0x180039980`
- `WLDAP32!__imp_ldap_get_dnW` at `0x180039cdc`
- `WLDAP32!__imp_ldap_get_dnW` at `0x180039cdc`
- `WLDAP32!__imp_ldap_initW` at `0x180039943`
- `WLDAP32!__imp_ldap_initW` at `0x180039943`
- `WLDAP32!__imp_ldap_memfreeW` at `0x180039d5c`
- `WLDAP32!__imp_ldap_memfreeW` at `0x180039d5c`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x180039c86`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x180039c86`

## string_xrefs

- `0x180039499`: `nTSecurityDescriptor`
- `0x180039605`: `gPCUserExtensionNames`
- `0x1800395f7`: `gPCMachineExtensionNames`
- `0x1800396f2`: `cn=configuration`
- `0x1800394fb`: `gPCFileSysPath`
- `0x18003a652`: `EvalList: Object <%s> cannot be accessed/is disabled/or has no extensions`
- `0x18003a683`: `EvalList: Object <%s> cannot be accessed/is disabled/or has no extensions`
- `0x18003972e`: `EvaluateDeferredGPOs: DN %s is under cn=configuration container`
- `0x180039753`: `EvaluateDeferredGPOs: DN %s is under cn=configuration container`
- `0x180039796`: `EvaluateDeferredGPOs: The GPO is under the config container. Querying seperately\n`
- `0x1800397b8`: `EvaluateDeferredGPOs: The GPO is under the config container. Querying seperately\n`
- `0x18003a18e`: `EvaluateDeferredGPOs:  All objects can not be accessed.`
- `0x18003a1a9`: `EvaluateDeferredGPOs:  All objects can not be accessed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall EvaluateDeferredGPOs(
        struct ldap *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        void *a4,
        int a5,
        struct _GROUP_POLICY_OBJECTW *a6,
        struct _GROUP_POLICY_OBJECTW *a7,
        struct _GROUP_POLICY_OBJECTW **a8,
        struct _GROUP_POLICY_OBJECTW **a9,
        struct _GPCONTAINER **a10,
        void *a11,
        struct CGpoFilter *a12,
        struct CLocator *a13,
        struct _GPOINFO *a14,
        int a15,
        struct _BANDWIDTHESTIMATE *a16)
{
  char v16; // r12
  unsigned int v17; // r14d
  DWORD LastError; // ebx
  int v19; // esi
  struct _GROUP_POLICY_OBJECTW *i; // rdi
  struct _GROUP_POLICY_OBJECTW *j; // rdi
  _QWORD *v22; // rsi
  int v23; // eax
  const WCHAR *v24; // rdi
  DWORD v25; // eax
  PDS_NAME_RESULT_ITEMW rItems; // rdx
  LDAP *v27; // rax
  struct ldap *v28; // rdi
  ULONG v29; // eax
  ULONG v30; // r15d
  ULONG v31; // eax
  unsigned __int64 v32; // rcx
  WCHAR *v33; // r8
  ULONG v34; // eax
  ULONG v35; // r15d
  ULONG v36; // eax
  ULONG v37; // edi
  __int64 v38; // rax
  unsigned __int64 v39; // rdi
  WCHAR *v40; // rax
  WCHAR *v41; // r15
  unsigned __int16 *v42; // r12
  WCHAR *v43; // r9
  void (*v44)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v45; // eax
  DWORD v46; // eax
  LDAPMessage **v47; // rdi
  ULONG v48; // r15d
  LDAP *v49; // rcx
  LDAPMessage *k; // rax
  LDAPMessage *v51; // r15
  WCHAR *dnW; // rax
  __int64 v53; // rdi
  const WCHAR *v54; // rbx
  int v55; // eax
  __int64 v56; // rax
  __int64 v57; // rcx
  _QWORD *v58; // rcx
  _QWORD *v59; // rdi
  int v61; // edi
  int v62; // esi
  int v63; // edi
  unsigned int GPSourceFileId; // eax
  int *v65; // r8
  void (*v66)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v67; // rdx
  ULONG v68; // eax
  void (*v69)(unsigned int, const unsigned __int16 *, ...); // rsi
  DWORD v70; // edi
  ULONG v71; // eax
  DWORD v72; // edi
  ULONG v73; // eax
  void (*v74)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v75; // rdx
  int v76; // edi
  int v77; // esi
  int v78; // edi
  unsigned int v79; // eax
  int *v80; // r8
  int v81; // edi
  int v82; // esi
  int v83; // edi
  unsigned int v84; // eax
  int *v85; // r8
  void (*v86)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v87; // eax
  DWORD v88; // eax
  struct _GROUP_POLICY_OBJECTW *v89; // r15
  unsigned int v90; // r12d
  struct ldapmsg *lParam; // rdx
  LPARAM lParam2; // rcx
  PCNZWCH lpString2; // [rsp+20h] [rbp-100h]
  HLOCAL v94; // [rsp+A8h] [rbp-78h] BYREF
  int v95; // [rsp+B0h] [rbp-70h]
  PDS_NAME_RESULTW pResult; // [rsp+B8h] [rbp-68h] BYREF
  HLOCAL hMem; // [rsp+C0h] [rbp-60h] BYREF
  unsigned __int16 *v98; // [rsp+C8h] [rbp-58h] BYREF
  unsigned int v99; // [rsp+D0h] [rbp-50h]
  LPCWSTR rpNames; // [rsp+D8h] [rbp-48h] BYREF
  __int64 invalue; // [rsp+E0h] [rbp-40h] BYREF
  DWORD v102; // [rsp+E8h] [rbp-38h]
  void *v103; // [rsp+F0h] [rbp-30h]
  struct _GROUP_POLICY_OBJECTW *v104; // [rsp+F8h] [rbp-28h]
  struct _GPCONTAINER **v105; // [rsp+100h] [rbp-20h]
  void *v106; // [rsp+108h] [rbp-18h]
  WCHAR *v107; // [rsp+110h] [rbp-10h]
  struct CLocator *v108; // [rsp+118h] [rbp-8h]
  struct CGpoFilter *v109; // [rsp+120h] [rbp+0h]
  _QWORD v110[3]; // [rsp+128h] [rbp+8h] BYREF
  char v111; // [rsp+140h] [rbp+20h]
  int v112; // [rsp+141h] [rbp+21h]
  __int16 v113; // [rsp+145h] [rbp+25h]
  char v114; // [rsp+147h] [rbp+27h]
  _QWORD v115[3]; // [rsp+148h] [rbp+28h] BYREF
  char v116; // [rsp+160h] [rbp+40h]
  int v117; // [rsp+161h] [rbp+41h]
  __int16 v118; // [rsp+165h] [rbp+45h]
  char v119; // [rsp+167h] [rbp+47h]
  _QWORD v120[6]; // [rsp+170h] [rbp+50h] BYREF
  int v121; // [rsp+1A0h] [rbp+80h]
  int v122; // [rsp+1A4h] [rbp+84h]
  unsigned __int16 near **v123; // [rsp+1A8h] [rbp+88h]
  __int64 v124; // [rsp+1B0h] [rbp+90h]
  struct ldap *v125; // [rsp+1D0h] [rbp+B0h]
  PCNZWCH lpString1; // [rsp+1D8h] [rbp+B8h]
  struct _BANDWIDTHESTIMATE *v127; // [rsp+1E0h] [rbp+C0h]
  struct _GROUP_POLICY_OBJECTW *v128; // [rsp+1E8h] [rbp+C8h]
  struct _GROUP_POLICY_OBJECTW **v129; // [rsp+1F0h] [rbp+D0h]
  struct _GROUP_POLICY_OBJECTW **v130; // [rsp+1F8h] [rbp+D8h]
  PLDAPControlW ServerControls[4]; // [rsp+200h] [rbp+E0h] BYREF
  PWSTR attrs[12]; // [rsp+220h] [rbp+100h] BYREF
  int v133; // [rsp+280h] [rbp+160h] BYREF
  char v134; // [rsp+284h] [rbp+164h]
  int v135; // [rsp+288h] [rbp+168h] BYREF
  wchar_t v136; // [rsp+28Ch] [rbp+16Ch]
  __int64 v137; // [rsp+290h] [rbp+170h] BYREF
  int v138; // [rsp+298h] [rbp+178h]
  wchar_t v139[12]; // [rsp+2A0h] [rbp+180h] BYREF
  _OWORD v140[2]; // [rsp+2B8h] [rbp+198h] BYREF
  _OWORD v141[2]; // [rsp+2D8h] [rbp+1B8h] BYREF
  _OWORD v142[2]; // [rsp+2F8h] [rbp+1D8h] BYREF
  __int128 v143; // [rsp+318h] [rbp+1F8h] BYREF
  _OWORD v144[2]; // [rsp+328h] [rbp+208h]
  _OWORD v145[3]; // [rsp+348h] [rbp+228h] BYREF

  v106 = a4;
  v16 = a3;
  v99 = a3;
  lpString1 = a2;
  v125 = a1;
  v103 = a11;
  v127 = a16;
  v128 = a6;
  v104 = a7;
  v129 = a8;
  v130 = a9;
  v105 = a10;
  v109 = a12;
  v108 = a13;
  v110[0] = L"1.2.840.113556.1.4.801";
  v110[1] = 5;
  v110[2] = &v133;
  v17 = 1;
  v111 = 1;
  v112 = 0;
  v113 = 0;
  v114 = 0;
  v115[0] = L"1.2.840.113556.1.4.1339";
  v115[1] = 0;
  v115[2] = 0;
  v116 = 1;
  v117 = 0;
  v118 = 0;
  v119 = 0;
  ServerControls[0] = (PLDAPControlW)v110;
  ServerControls[1] = (PLDAPControlW)v115;
  ServerControls[2] = 0;
  v143 = *(_OWORD *)L"nTSecurityDescriptor";
  v144[0] = *(_OWORD *)L"tyDescriptor";
  *(_OWORD *)((char *)v144 + 10) = *(_OWORD *)L"criptor";
  v135 = *(_DWORD *)L"cn";
  v136 = aCn_0[2];
  wcscpy(v139, L"displayName");
  v142[0] = *(_OWORD *)L"gPCFileSysPath";
  *(_OWORD *)((char *)v142 + 14) = *(_OWORD *)L"SysPath";
  v141[0] = *(_OWORD *)L"versionNumber";
  *(_OWORD *)((char *)v141 + 12) = *(_OWORD *)L"nNumber";
  wcscpy((wchar_t *)v145, L"gPCFunctionalityVersion");
  v137 = *(_QWORD *)L"flags";
  v138 = *(_DWORD *)L"s";
  v140[0] = *(_OWORD *)L"gPCWQLFilter";
  *(_OWORD *)((char *)v140 + 10) = *(_OWORD *)L"LFilter";
  attrs[0] = (PWSTR)&v143;
  attrs[1] = (PWSTR)v142;
  attrs[2] = (PWSTR)&v135;
  attrs[3] = v139;
  attrs[4] = (PWSTR)v141;
  attrs[5] = (PWSTR)v145;
  attrs[6] = (PWSTR)&v137;
  attrs[7] = L"gPCMachineExtensionNames";
  attrs[8] = (PWSTR)L"gPCUserExtensionNames";
  attrs[9] = szObjectClass;
  attrs[10] = (PWSTR)v140;
  attrs[11] = 0;
  v94 = 0;
  invalue = 0;
  *a8 = 0;
  *a9 = 0;
  LastError = GetLastError();
  v102 = LastError;
  v95 = LastError;
  if ( !a6 && !v104 )
    goto LABEL_121;
  v19 = 0;
  for ( i = a6; i; i = i->pNext )
  {
    if ( !(unsigned int)AddDN((struct _LDAPQUERY **)&v94, i->lpDSPath, 0, i) )
    {
LABEL_7:
      LastError = GetLastError();
      goto LABEL_118;
    }
  }
  for ( j = v104; j; j = j->pNext )
  {
    if ( !(unsigned int)AddDN((struct _LDAPQUERY **)&v94, j->lpDSPath, 0, j) )
      goto LABEL_7;
  }
  v133 = 16909104;
  v134 = 7;
  v22 = v94;
  while ( 1 )
  {
    if ( !v22 )
    {
      if ( v127 )
        DetermineLinkStatus(a14, *(struct IConnectivityInfo **)v127, *((_DWORD *)v127 + 2), (int *)v127 + 3);
      v89 = v128;
      v90 = v99;
      while ( v89 )
      {
        lParam = (struct ldapmsg *)v89->lParam;
        if ( lParam )
        {
          lParam2 = v89->lParam2;
          if ( lParam2
            && !(unsigned int)ProcessGPO(
                                v89->lpDSPath,
                                v90,
                                v106,
                                v129,
                                v105,
                                v89->dwOptions,
                                0,
                                a5,
                                v89->GPOLink,
                                v89->lpLink,
                                *(struct ldap **)(lParam2 + 8),
                                lParam,
                                0,
                                v103,
                                v109,
                                v108,
                                *(_DWORD *)lParam2,
                                a14,
                                a15) )
          {
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(2u, L"EvalList:  ProcessGPO failed", 0);
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(2u, L"EvalList:  ProcessGPO failed", 0);
              }
            }
            goto LABEL_250;
          }
        }
        else if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(
              4u,
              L"EvalList: Object <%s> cannot be accessed/is disabled/or has no extensions",
              v89->lpDSPath);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(
              4u,
              L"EvalList: Object <%s> cannot be accessed/is disabled/or has no extensions",
              v89->lpDSPath);
          }
        }
        v89 = v89->pNext;
      }
      if ( !(unsigned int)EvalList(v90, v106, a5, v104, v130, v105, v103, v109, v108, a14, a15) )
      {
LABEL_250:
        LastError = GetLastError();
        goto LABEL_117;
      }
      v19 = 1;
      goto LABEL_118;
    }
    if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)*v22, 16, L"cn=configuration", 16) == 2 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"EvaluateDeferredGPOs: DN %s is under cn=configuration container", *v22);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"EvaluateDeferredGPOs: DN %s is under cn=configuration container", *v22);
        }
      }
      v23 = 1;
    }
    else
    {
      v23 = 0;
    }
    rpNames = 0;
    pResult = 0;
    if ( v23 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"EvaluateDeferredGPOs: The GPO is under the config container. Querying seperately\n");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"EvaluateDeferredGPOs: The GPO is under the config container. Querying seperately\n");
        }
      }
      v24 = (const WCHAR *)*v22;
      rpNames = 0;
      while ( *v24 )
      {
        if ( CompareStringW(0x7Fu, 1u, v24, 3, L"DC=", 3) == 2 )
        {
          rpNames = v24;
          goto LABEL_41;
        }
        while ( *v24 && *v24 != 44 )
          ++v24;
        if ( *v24 == 44 )
          ++v24;
      }
      v24 = rpNames;
LABEL_41:
      if ( !v24 )
      {
        LastError = 13;
        v95 = 13;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"EvaluateDeferredGPOs: Domain not found for <%s>. Exiting.", *v22);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"EvaluateDeferredGPOs: Domain not found for <%s>. Exiting.", *v22);
          }
        }
        goto LABEL_135;
      }
    }
    else
    {
      rpNames = (LPCWSTR)*v22;
    }
    v25 = DsCrackNamesW(
            (HANDLE)0xFFFFFFFFFFFFFFFFLL,
            DS_NAME_FLAG_SYNTACTICAL_ONLY,
            DS_FQDN_1779_NAME,
            DS_CANONICAL_NAME,
            1u,
            &rpNames,
            &pResult);
    if ( v25 || !pResult->cItems || (rItems = pResult->rItems, rItems->status) || !rItems->pDomain )
    {
      LastError = v25;
      v95 = v25;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"EvaluateDeferredGPOs:  DsCrackNames failed with 0x%x.", v25);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"EvaluateDeferredGPOs:  DsCrackNames failed with 0x%x.", v25);
        }
      }
      goto LABEL_135;
    }
    v22[3] = v125;
    if ( CompareStringW(0x7Fu, 1u, lpString1, -1, pResult->rItems->pDomain, -1) != 2 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"EvaluateDeferredGPOs: Doing an ldap bind to cross-domain <%s>", pResult->rItems->pDomain);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(
            4u,
            L"EvaluateDeferredGPOs: Doing an ldap bind to cross-domain <%s>",
            pResult->rItems->pDomain);
        }
      }
      v27 = ldap_initW(pResult->rItems->pDomain, 0x185u);
      v28 = v27;
      if ( !v27 )
      {
        v68 = LdapGetLastError();
        LastError = LdapMapErrorToWin32(v68);
        v95 = LastError;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v69 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            v70 = GetLastError();
            v71 = LdapGetLastError();
            LODWORD(lpString2) = v70;
            v69(
              2u,
              L"EvaluateDeferredGPOs:  ldap_init for <%s> failed with = 0x%x or %d",
              pResult->rItems->pDomain,
              v71,
              lpString2);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            v72 = GetLastError();
            v73 = LdapGetLastError();
            LODWORD(lpString2) = v72;
            RedirectDebugMsg(
              2u,
              L"EvaluateDeferredGPOs:  ldap_init for <%s> failed with = 0x%x or %d",
              pResult->rItems->pDomain,
              v73,
              lpString2);
          }
        }
LABEL_134:
        DsFreeNameResultW(pResult);
LABEL_135:
        v19 = 0;
        goto LABEL_118;
      }
      invalue = 1;
      v29 = ldap_set_optionW(v27, 149, &invalue);
      v30 = v29;
      if ( v29 )
      {
        LastError = LdapMapErrorToWin32(v29);
        v95 = LastError;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v66 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            v67 = L"EvaluateDeferredGPOs:  Failed to turn on LDAP_OPT_SIGN with %d";
LABEL_139:
            v66(2u, v67, v30);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"EvaluateDeferredGPOs:  Failed to turn on LDAP_OPT_SIGN with %d", v30);
          }
        }
LABEL_143:
        LogLdapServerError(v28, 0);
        DsFreeNameResultW(pResult);
        ldap_unbind(v28);
        goto LABEL_135;
      }
      v31 = ldap_connect(v28, &MAX_LDAP_SERVER_CONNECT_TIME);
      v30 = v31;
      if ( v31 )
      {
        LastError = LdapMapErrorToWin32(v31);
        v95 = LastError;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v66 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            v67 = L"EvaluateDeferredGPOs:  Failed to connect with %d";
            goto LABEL_139;
          }
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            RedirectDebugMsg(2u, L"EvaluateDeferredGPOs:  Failed to connect with %d", v30);
        }
        goto LABEL_143;
      }
      v22[3] = v28;
      *((_DWORD *)v22 + 8) = 1;
      if ( v103 || (v16 & 1) == 0 )
      {
        v33 = 0;
      }
      else
      {
        v124 = 0;
        v120[0] = 0x4800000200LL;
        memset(&v120[1], 0, 40);
        v121 = 0;
        v122 = 2;
        v123 = &wszKerberos;
        LODWORD(hMem) = 0;
        v32 = -1;
        do
          ++v32;
        while ( *((_WORD *)&wszKerberos + v32) );
        if ( (int)ULongLongToULong(v32, (unsigned int *)&hMem) < 0 )
        {
          LastError = GetLastError();
          v95 = LastError;
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(2u, L"SizeTToDWord() Failed to convert wszKerberos length to DWORD");
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(2u, L"SizeTToDWord() Failed to convert wszKerberos length to DWORD");
            }
          }
LABEL_117:
          v19 = 0;
          goto LABEL_118;
        }
        LODWORD(v124) = (_DWORD)hMem;
        v33 = (WCHAR *)v120;
      }
      v34 = ldap_bind_sW(v28, 0, v33, 0x486u);
      v35 = v34;
      if ( v34 )
      {
        LastError = LdapMapErrorToWin32(v34);
        v95 = LastError;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"EvaluateDeferredGPOs:  ldap_bind_s failed with = <%d>", v35);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"EvaluateDeferredGPOs:  ldap_bind_s failed with = <%d>", v35);
          }
        }
        LogLdapServerError(v28, 0);
        if ( a15 && a14 )
        {
          v61 = *((_DWORD *)a14 + 64);
          v62 = GetTickCount() - v61;
          v63 = *((_DWORD *)a14 + 70);
          GPSourceFileId = GetGPSourceFileId(L"ds\\grouppolicy\\client\\gpsvc\\engine\\gpqry.cpp");
          CGPAdminEventLdapFailure::CGPAdminEventLdapFailure(
            (CGPAdminEventGenericFailure *)v120,
            (__int64)gpEvent_FAILED_DS_BIND,
            GPSourceFileId,
            0xAC8u,
            v63,
            v62,
            v35);
          CGPPolicyEventReporting::Report(*((CGPPolicyEventReporting **)a14 + 34), (struct CGPEventInfo *)v120, v65);
          v120[0] = &CGPAdminEventLdapFailure::`vftable';
          CGPAdminEventInitFailure::~CGPAdminEventInitFailure((CGPAdminEventInitFailure *)v120);
        }
        goto LABEL_134;
      }
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"EvaluateDeferredGPOs: Bind sucessful");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"EvaluateDeferredGPOs: Bind sucessful");
        }
      }
    }
    DsFreeNameResultW(pResult);
    invalue = 0;
    v36 = ldap_set_optionW((LDAP *)v22[3], 8, &invalue);
    v37 = v36;
    if ( v36 )
    {
      LastError = LdapMapErrorToWin32(v36);
      v95 = LastError;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"EvalauteDeferredGPOs:  Failed to turn off referrals with error %d", v37);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"EvalauteDeferredGPOs:  Failed to turn off referrals with error %d", v37);
        }
      }
      LogLdapServerError((struct ldap *)v22[3], 0);
      goto LABEL_135;
    }
    hMem = 0;
    v98 = 0;
    if ( !*v22 )
      break;
    v38 = -1;
    do
      ++v38;
    while ( *(_WORD *)(*v22 + 2 * v38) );
    v39 = v38 + 25;
    v40 = (WCHAR *)LocalAlloc(0x40u, 2 * (v38 + 25));
    v41 = v40;
    hMem = v40;
    if ( !v40 )
    {
      LastError = GetLastError();
      v95 = LastError;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v86 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v87 = GetLastError();
          v86(2u, L"EvalauteDeferredGPOs:  Failed to allocate memory for GPO base search with %d", v87);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v88 = GetLastError();
          RedirectDebugMsg(2u, L"EvalauteDeferredGPOs:  Failed to allocate memory for GPO base search with %d", v88);
        }
      }
LABEL_157:
      XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v98);
      XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&hMem);
      goto LABEL_135;
    }
    StringCchPrintfW(v40, v39, L"cn=policies,cn=system,%s", *v22);
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"EvaluateDeferredGPOs:  Searching for GPOs in %s", v41);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"EvaluateDeferredGPOs:  Searching for GPOs in %s", v41);
      }
    }
    v42 = FormatLDAPToExcludeDisabledGPOs((const unsigned __int16 *)v22[1], v16 & 1);
    v98 = v42;
    if ( v42 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"EvaluateDeferredGPOs:  Adding filters %s", v42);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"EvaluateDeferredGPOs:  Adding filters %s", v42);
        }
      }
      v43 = v42;
    }
    else
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v44 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v45 = GetLastError();
          v44(
            4u,
            L"EvaluateDeferredGPOs:  Adding filters failed with %d. Executing default query without filtering",
            v45);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v46 = GetLastError();
          RedirectDebugMsg(
            4u,
            L"EvaluateDeferredGPOs:  Adding filters failed with %d. Executing default query without filtering",
            v46);
        }
      }
      v43 = (WCHAR *)v22[1];
    }
    v47 = (LDAPMessage **)(v22 + 5);
    v48 = ldap_search_ext_sW(
            (LDAP *)v22[3],
            v41,
            2u,
            v43,
            attrs,
            0,
            ServerControls,
            0,
            &MAX_LDAP_SEARCH_TIME,
            0x10000u,
            (PLDAPMessage *)v22 + 5);
    if ( v48 )
    {
      if ( v48 == 16 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v74 = g_lpDebugMsg;
          if ( !g_lpDebugMsg )
          {
            if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              RedirectDebugMsg(4u, L"EvaluateDeferredGPOs:  All objects can not be accessed.");
            goto LABEL_180;
          }
          v75 = L"EvaluateDeferredGPOs:  All objects can not be accessed.";
          goto LABEL_176;
        }
        goto LABEL_180;
      }
      if ( v48 == 32 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v74 = g_lpDebugMsg;
          if ( !g_lpDebugMsg )
          {
            if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              RedirectDebugMsg(4u, L"EvaluateDeferredGPOs:  Objects do not exist.");
            goto LABEL_180;
          }
          v75 = L"EvaluateDeferredGPOs:  Objects do not exist.";
LABEL_176:
          v74(4u, v75);
        }
LABEL_180:
        v19 = 1;
        goto LABEL_203;
      }
      if ( v48 != 4 )
      {
LABEL_182:
        if ( (*(_WORD *)&CGPServiceEventReporting::s_dwTestFlags & 0x8000) == 0 )
        {
          LastError = LdapMapErrorToWin32(v48);
          v95 = LastError;
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(2u, L"EvaluteDeferredGPOs:  Failed to search with error 0x%x", v48);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(2u, L"EvaluteDeferredGPOs:  Failed to search with error 0x%x", v48);
            }
          }
          LogLdapServerError((struct ldap *)v22[3], 0);
          if ( a15 && a14 )
          {
            v76 = *((_DWORD *)a14 + 64);
            v77 = GetTickCount() - v76;
            v78 = *((_DWORD *)a14 + 70);
            v79 = GetGPSourceFileId(L"ds\\grouppolicy\\client\\gpsvc\\engine\\gpqry.cpp");
            CGPAdminEventLdapFailure::CGPAdminEventLdapFailure(
              (CGPAdminEventGenericFailure *)v120,
              (__int64)gpEvent_FAILED_GPO_SEARCH,
              v79,
              0xB58u,
              v78,
              v77,
              v48);
            CGPPolicyEventReporting::Report(*((CGPPolicyEventReporting **)a14 + 34), (struct CGPEventInfo *)v120, v80);
LABEL_192:
            v120[0] = &CGPAdminEventLdapFailure::`vftable';
            CGPAdminEventInitFailure::~CGPAdminEventInitFailure((CGPAdminEventInitFailure *)v120);
            v19 = 0;
            goto LABEL_203;
          }
          goto LABEL_202;
        }
      }
LABEL_193:
      LastError = LdapMapErrorToWin32(v48);
      v95 = LastError;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"EvalateDeferredGPOs:  Too many GPOs in search.");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"EvalateDeferredGPOs:  Too many GPOs in search.");
        }
      }
      LogLdapServerError((struct ldap *)v22[3], 0);
      if ( a15 && a14 )
      {
        v81 = *((_DWORD *)a14 + 64);
        v82 = GetTickCount() - v81;
        v83 = *((_DWORD *)a14 + 70);
        v84 = GetGPSourceFileId(L"ds\\grouppolicy\\client\\gpsvc\\engine\\gpqry.cpp");
        CGPAdminEventLdapFailure::CGPAdminEventLdapFailure(
          (CGPAdminEventGenericFailure *)v120,
          (__int64)gpEvent_TOO_MANY_GPOS,
          v84,
          0xB48u,
          v83,
          v82,
          v48);
        CGPPolicyEventReporting::Report(*((CGPPolicyEventReporting **)a14 + 34), (struct CGPEventInfo *)v120, v85);
        goto LABEL_192;
      }
LABEL_202:
      v19 = 0;
      goto LABEL_203;
    }
    if ( (CGPServiceEventReporting::s_dwTestFlags & 0x10) != 0 )
      goto LABEL_182;
    if ( (*(_WORD *)&CGPServiceEventReporting::s_dwTestFlags & 0x8000) != 0 )
      goto LABEL_193;
    v49 = (LDAP *)v22[3];
    if ( !*v47 )
    {
      LastError = LdapMapErrorToWin32(v49->ld_errno);
      v95 = LastError;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(
            2u,
            L"EvaluateDeferredGPOs:  Search returned an empty message structure.  Error = 0x%x",
            *(unsigned int *)(v22[3] + 116LL));
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(
            2u,
            L"EvaluateDeferredGPOs:  Search returned an empty message structure.  Error = 0x%x",
            *(unsigned int *)(v22[3] + 116LL));
        }
      }
      LogLdapServerError((struct ldap *)v22[3], 0);
      goto LABEL_157;
    }
    for ( k = ldap_first_entry(v49, *v47); ; k = ldap_next_entry((LDAP *)v22[3], v51) )
    {
      v51 = k;
      if ( !k )
        break;
      dnW = ldap_get_dnW((LDAP *)v22[3], k);
      v107 = dnW;
      if ( !dnW )
      {
        LastError = GetLastError();
        goto LABEL_157;
      }
      v53 = v22[6];
      if ( v53 )
      {
        v54 = dnW;
        do
        {
          v55 = CompareStringW(0x7Fu, 1u, v54, -1, *(PCNZWCH *)v53, -1);
          if ( v55 == 2 )
          {
            v56 = *(_QWORD *)(v53 + 8);
            v57 = *(_QWORD *)(v56 + 168);
            *(_QWORD *)(v56 + 136) = v51;
            *(_QWORD *)(v57 + 8) = v22[3];
          }
          else if ( v55 == 1 )
          {
            break;
          }
          v53 = *(_QWORD *)(v53 + 32);
        }
        while ( v53 );
        LastError = v102;
        dnW = v107;
      }
      ldap_memfreeW(dnW);
    }
    v22 = (_QWORD *)v22[7];
    if ( v42 )
      LocalFree(v42);
    LocalFree(hMem);
    v16 = v99;
  }
  v19 = 0;
LABEL_203:
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v98);
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&hMem);
LABEL_118:
  v58 = v94;
  if ( v94 )
  {
    do
    {
      v59 = (_QWORD *)v58[7];
      FreeLdapQuery(v58);
      v58 = v59;
    }
    while ( v59 );
  }
  v17 = v19;
LABEL_121:
  SetLastError(LastError);
  return v17;
}

```

## disassembly

```asm
0x180039364  mov     [rsp-8+arg_0], rbx
0x180039369  push    rbp
0x18003936a  push    rsi
0x18003936b  push    rdi
0x18003936c  push    r12
0x18003936e  push    r13
0x180039370  push    r14
0x180039372  push    r15
0x180039374  lea     rbp, [rsp-260h]
0x18003937c  sub     rsp, 380h
0x180039383  mov     rax, cs:__security_cookie
0x18003938a  xor     rax, rsp
0x18003938d  mov     [rbp+290h+var_38], rax
0x180039394  mov     [rbp+290h+var_2A8], r9
0x180039398  mov     r12d, r8d
0x18003939b  mov     [rbp+290h+var_2E0], r8d
0x18003939f  mov     [rbp+290h+lpString1], rdx
0x1800393a6  mov     [rbp+290h+var_1E0], rcx
0x1800393ad  mov     rax, [rbp+290h+arg_50]
0x1800393b4  mov     [rbp+290h+var_2C0], rax
0x1800393b8  mov     rax, [rbp+290h+arg_78]
0x1800393bf  mov     [rbp+290h+var_1D0], rax
0x1800393c6  mov     r15, [rbp+290h+arg_28]
0x1800393cd  mov     [rbp+290h+var_1C8], r15
0x1800393d4  mov     r9, [rbp+290h+arg_30]
0x1800393db  mov     [rbp+290h+var_2B8], r9
0x1800393df  mov     rdx, [rbp+290h+arg_38]
0x1800393e6  mov     [rbp+290h+var_1C0], rdx
0x1800393ed  mov     rcx, [rbp+290h+arg_40]
0x1800393f4  mov     [rbp+290h+var_1B8], rcx
0x1800393fb  mov     rax, [rbp+290h+arg_48]
0x180039402  mov     [rbp+290h+var_2B0], rax
0x180039406  mov     rax, [rbp+290h+arg_58]
0x18003940d  mov     [rbp+290h+var_290], rax
0x180039411  mov     rax, [rbp+290h+arg_60]
0x180039418  mov     [rbp+290h+var_298], rax
0x18003941c  mov     r13, [rbp+290h+arg_68]
0x180039423  lea     rax, a12840113556148; "1.2.840.113556.1.4.801"
0x18003942a  mov     [rbp+290h+var_288], rax
0x18003942e  mov     [rbp+290h+var_280], 5
0x180039436  lea     rax, [rbp+290h+var_130]
0x18003943d  mov     [rbp+290h+var_278], rax
0x180039441  mov     r14d, 1
0x180039447  mov     [rbp+290h+var_270], r14b
0x18003944b  xor     eax, eax
0x18003944d  mov     [rbp+290h+var_26F], eax
0x180039450  mov     [rbp+290h+var_26B], ax
0x180039454  mov     [rbp+290h+var_269], al
0x180039457  lea     rax, a12840113556141; "1.2.840.113556.1.4.1339"
0x18003945e  mov     [rbp+290h+var_268], rax
0x180039462  xor     edi, edi
0x180039464  mov     [rbp+290h+var_260], rdi
0x180039468  mov     [rbp+290h+var_258], rdi
0x18003946c  mov     [rbp+290h+var_250], r14b
0x180039470  xor     eax, eax
0x180039472  mov     [rbp+290h+var_24F], eax
0x180039475  mov     [rbp+290h+var_24B], ax
0x180039479  mov     [rbp+290h+var_249], al
0x18003947c  lea     rax, [rbp+290h+var_288]
0x180039480  mov     [rbp+290h+ServerControls], rax
0x180039487  lea     rax, [rbp+290h+var_268]
0x18003948b  mov     [rbp+290h+var_1A8], rax
0x180039492  mov     [rbp+290h+var_1A0], rdi
0x180039499  movups  xmm0, xmmword ptr cs:aNtsecuritydesc; "nTSecurityDescriptor"
0x1800394a0  movups  [rbp+290h+var_98], xmm0
0x1800394a7  movups  xmm1, xmmword ptr cs:aNtsecuritydesc+10h; "tyDescriptor"
0x1800394ae  movups  xmmword ptr [rbp+290h+var_88], xmm1
0x1800394b5  movups  xmm0, xmmword ptr cs:aNtsecuritydesc+1Ah; "criptor"
0x1800394bc  movups  xmmword ptr [rbp+290h+var_88+0Ah], xmm0
0x1800394c3  mov     eax, dword ptr cs:aCn_0; "cn"
0x1800394c9  mov     [rbp+290h+var_128], eax
0x1800394cf  movzx   eax, word ptr cs:aCn_0+4; ""
0x1800394d6  mov     [rbp+290h+var_124], ax
0x1800394dd  movups  xmm0, xmmword ptr cs:aDisplayname_0; "displayName"
0x1800394e4  movups  [rbp+290h+var_110], xmm0
0x1800394eb  movsd   xmm1, qword ptr cs:aDisplayname_0+10h; "ame"
0x1800394f3  movsd   [rbp+290h+var_100], xmm1
0x1800394fb  movups  xmm0, xmmword ptr cs:aGpcfilesyspath; "gPCFileSysPath"
0x180039502  movups  xmmword ptr [rbp+290h+var_B8], xmm0
0x180039509  movups  xmm1, xmmword ptr cs:aGpcfilesyspath+0Eh; "SysPath"
0x180039510  movups  xmmword ptr [rbp+290h+var_B8+0Eh], xmm1
0x180039517  movups  xmm0, xmmword ptr cs:aVersionnumber; "versionNumber"
0x18003951e  movups  xmmword ptr [rbp+290h+var_D8], xmm0
0x180039525  movups  xmm1, xmmword ptr cs:aVersionnumber+0Ch; "nNumber"
0x18003952c  movups  xmmword ptr [rbp+290h+var_D8+0Ch], xmm1
0x180039533  movups  xmm0, xmmword ptr cs:aGpcfunctionali; "gPCFunctionalityVersion"
0x18003953a  movups  [rbp+290h+var_68], xmm0
0x180039541  movups  xmm1, xmmword ptr cs:aGpcfunctionali+10h; "ionalityVersion"
0x180039548  movups  [rbp+290h+var_58], xmm1
0x18003954f  movups  xmm0, xmmword ptr cs:aGpcfunctionali+20h; "Version"
0x180039556  movups  [rbp+290h+var_48], xmm0
0x18003955d  movsd   xmm1, qword ptr cs:aFlags; "flags"
0x180039565  movsd   [rbp+290h+var_120], xmm1
0x18003956d  mov     eax, dword ptr cs:aFlags+8; "s"
0x180039573  mov     [rbp+290h+var_118], eax
0x180039579  movups  xmm0, xmmword ptr cs:aGpcwqlfilter; "gPCWQLFilter"
0x180039580  movups  xmmword ptr [rbp+290h+var_F8], xmm0
0x180039587  movups  xmm1, xmmword ptr cs:aGpcwqlfilter+0Ah; "LFilter"
0x18003958e  movups  xmmword ptr [rbp+290h+var_F8+0Ah], xmm1
0x180039595  lea     rax, [rbp+290h+var_98]
0x18003959c  mov     [rbp+290h+attrs], rax
0x1800395a3  lea     rax, [rbp+290h+var_B8]
0x1800395aa  mov     [rbp+290h+var_188], rax
0x1800395b1  lea     rax, [rbp+290h+var_128]
0x1800395b8  mov     [rbp+290h+var_180], rax
0x1800395bf  lea     rax, [rbp+290h+var_110]
0x1800395c6  mov     [rbp+290h+var_178], rax
0x1800395cd  lea     rax, [rbp+290h+var_D8]
0x1800395d4  mov     [rbp+290h+var_170], rax
0x1800395db  lea     rax, [rbp+290h+var_68]
0x1800395e2  mov     [rbp+290h+var_168], rax
0x1800395e9  lea     rax, [rbp+290h+var_120]
0x1800395f0  mov     [rbp+290h+var_160], rax
0x1800395f7  lea     rax, aGpcmachineexte; "gPCMachineExtensionNames"
0x1800395fe  mov     [rbp+290h+var_158], rax
0x180039605  lea     rax, attr; "gPCUserExtensionNames"
0x18003960c  mov     [rbp+290h+var_150], rax
0x180039613  lea     rax, ?szObjectClass@@3PAGA; "objectClass"
0x18003961a  mov     [rbp+290h+var_148], rax
0x180039621  lea     rax, [rbp+290h+var_F8]
0x180039628  mov     [rbp+290h+var_140], rax
0x18003962f  mov     [rbp+290h+var_138], rdi
0x180039636  mov     [rbp+290h+var_308], rdi
0x18003963a  mov     [rbp+290h+invalue], rdi
0x18003963e  mov     [rdx], rdi
0x180039641  mov     [rcx], rdi
0x180039644  call    cs:__imp_GetLastError
0x18003964a  mov     ebx, eax
0x18003964c  mov     [rbp+290h+var_2C8], eax
0x18003964f  mov     [rbp+290h+var_300], eax
0x180039652  test    r15, r15
0x180039655  jnz     short loc_180039661
0x180039657  cmp     [rbp+290h+var_2B8], rdi
0x18003965b  jz      loc_180039DEE
0x180039661  mov     esi, edi
0x180039663  mov     [rbp+290h+var_310], edi
0x180039666  mov     rdi, r15
0x180039669  xor     r15d, r15d
0x18003966c  test    rdi, rdi
0x18003966f  jz      short loc_18003969E
0x180039671  mov     r9, rdi; struct _GROUP_POLICY_OBJECTW *
0x180039674  xor     r8d, r8d; struct _DNENTRY *
0x180039677  mov     rdx, [rdi+8]; unsigned __int16 *
0x18003967b  lea     rcx, [rbp+290h+var_308]; struct _LDAPQUERY **
0x18003967f  call    ?AddDN@@YAHPEAPEAU_LDAPQUERY@@PEBGPEAU_DNENTRY@@PEAU_GROUP_POLICY_OBJECTW@@@Z; AddDN(_LDAPQUERY * *,ushort const *,_DNENTRY *,_GROUP_POLICY_OBJECTW *)
0x180039684  test    eax, eax
0x180039686  jz      short loc_180039691
0x180039688  mov     rdi, [rdi+90h]
0x18003968f  jmp     short loc_18003966C
0x180039691  call    cs:__imp_GetLastError
0x180039697  mov     ebx, eax
0x180039699  jmp     loc_180039DD1
0x18003969e  mov     rdi, [rbp+290h+var_2B8]
0x1800396a2  test    rdi, rdi
0x1800396a5  jz      short loc_1800396C7
0x1800396a7  mov     r9, rdi; struct _GROUP_POLICY_OBJECTW *
0x1800396aa  xor     r8d, r8d; struct _DNENTRY *
0x1800396ad  mov     rdx, [rdi+8]; unsigned __int16 *
0x1800396b1  lea     rcx, [rbp+290h+var_308]; struct _LDAPQUERY **
0x1800396b5  call    ?AddDN@@YAHPEAPEAU_LDAPQUERY@@PEBGPEAU_DNENTRY@@PEAU_GROUP_POLICY_OBJECTW@@@Z; AddDN(_LDAPQUERY * *,ushort const *,_DNENTRY *,_GROUP_POLICY_OBJECTW *)
0x1800396ba  test    eax, eax
0x1800396bc  jz      short loc_180039691
0x1800396be  mov     rdi, [rdi+90h]
0x1800396c5  jmp     short loc_1800396A2
0x1800396c7  mov     [rbp+290h+var_130], 1020330h
0x1800396d1  mov     [rbp+290h+var_12C], 7
0x1800396d8  mov     rsi, [rbp+290h+var_308]
0x1800396dc  mov     edi, 4
0x1800396e1  test    rsi, rsi
0x1800396e4  jz      loc_18003A5E4
0x1800396ea  mov     [rsp+3B0h+cchCount2], 10h; cchCount2
0x1800396f2  lea     rax, aCnConfiguratio; "cn=configuration"
0x1800396f9  mov     [rsp+3B0h+lpString2], rax; lpString2
0x1800396fe  lea     r9d, [rdi+0Ch]; cchCount1
0x180039702  mov     r8, [rsi]; lpString1
0x180039705  mov     edx, r14d; dwCmpFlags
0x180039708  lea     ecx, [rdi+7Bh]; Locale
0x18003970b  call    cs:__imp_CompareStringW
0x180039711  cmp     eax, 2
0x180039714  jnz     short loc_180039766
0x180039716  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x18003971d  jz      short loc_180039761
0x18003971f  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180039726  test    rax, rax
0x180039729  jz      short loc_18003973E
0x18003972b  mov     r8, [rsi]
0x18003972e  lea     rdx, aEvaluatedeferr_12; "EvaluateDeferredGPOs: DN %s is under cn"...
0x180039735  mov     ecx, edi
0x180039737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003973c  jmp     short loc_180039761
0x18003973e  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180039745  jz      short loc_180039761
0x180039747  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18003974e  jz      short loc_180039761
0x180039750  mov     r8, [rsi]
0x180039753  lea     rdx, aEvaluatedeferr_12; "EvaluateDeferredGPOs: DN %s is under cn"...
0x18003975a  mov     ecx, edi; unsigned int
0x18003975c  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180039761  mov     eax, r14d
0x180039764  jmp     short loc_180039769
0x180039766  mov     eax, r15d
0x180039769  mov     [rbp+290h+rpNames], r15
0x18003976d  mov     [rbp+290h+pResult], r15
0x180039771  test    eax, eax
0x180039773  jnz     short loc_180039781
0x180039775  mov     rax, [rsi]
0x180039778  mov     [rbp+290h+rpNames], rax
0x18003977c  jmp     loc_180039836
0x180039781  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180039788  jz      short loc_1800397C6
0x18003978a  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180039791  test    rax, rax
0x180039794  jz      short loc_1800397A6
0x180039796  lea     rdx, aEvaluatedeferr_9; "EvaluateDeferredGPOs: The GPO is under "...
0x18003979d  mov     ecx, edi
0x18003979f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800397a4  jmp     short loc_1800397C6
0x1800397a6  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800397ad  jz      short loc_1800397C6
0x1800397af  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800397b6  jz      short loc_1800397C6
0x1800397b8  lea     rdx, aEvaluatedeferr_9; "EvaluateDeferredGPOs: The GPO is under "...
0x1800397bf  mov     ecx, edi; unsigned int
0x1800397c1  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800397c6  mov     rdi, [rsi]
0x1800397c9  mov     [rbp+290h+rpNames], r15
0x1800397cd  cmp     [rdi], r15w
0x1800397d1  jz      short loc_180039824
0x1800397d3  mov     ecx, 3
0x1800397d8  mov     [rsp+3B0h+cchCount2], ecx; cchCount2
0x1800397dc  lea     rax, aDc; "DC="
0x1800397e3  mov     [rsp+3B0h+lpString2], rax; lpString2
0x1800397e8  mov     r9d, ecx; cchCount1
0x1800397eb  mov     r8, rdi; lpString1
0x1800397ee  mov     edx, r14d; dwCmpFlags
0x1800397f1  lea     ecx, [r9+7Ch]; Locale
0x1800397f5  call    cs:__imp_CompareStringW
0x1800397fb  cmp     eax, 2
0x1800397fe  jnz     short loc_180039810
0x180039800  mov     [rbp+290h+rpNames], rdi
0x180039804  jmp     short loc_180039828
0x180039806  cmp     ax, 2Ch ; ','
0x18003980a  jz      short loc_180039818
0x18003980c  add     rdi, 2
0x180039810  movzx   eax, word ptr [rdi]
0x180039813  test    ax, ax
0x180039816  jnz     short loc_180039806
0x180039818  cmp     word ptr [rdi], 2Ch ; ','
0x18003981c  jnz     short loc_1800397CD
0x18003981e  add     rdi, 2
0x180039822  jmp     short loc_1800397CD
0x180039824  mov     rdi, [rbp+290h+rpNames]
0x180039828  test    rdi, rdi
0x18003982b  jz      loc_18003A579
0x180039831  mov     edi, 4
0x180039836  lea     rax, [rbp+290h+pResult]
0x18003983a  mov     [rsp+3B0h+ppResult], rax; ppResult
0x18003983f  lea     rax, [rbp+290h+rpNames]
0x180039843  mov     qword ptr [rsp+3B0h+cchCount2], rax; rpNames
0x180039848  mov     dword ptr [rsp+3B0h+lpString2], r14d; cNames
0x18003984d  mov     r9d, 7; formatDesired
0x180039853  mov     r8d, r14d; formatOffered
0x180039856  mov     edx, r14d; flags
0x180039859  or      rcx, 0FFFFFFFFFFFFFFFFh; hDS
0x18003985d  call    cs:__imp_DsCrackNamesW
0x180039863  test    eax, eax
0x180039865  jnz     loc_18003A512
0x18003986b  mov     rcx, [rbp+290h+pResult]
0x18003986f  cmp     [rcx], r15d
0x180039872  jz      loc_18003A512
0x180039878  mov     rdx, [rcx+8]
0x18003987c  cmp     [rdx], r15d
0x18003987f  jnz     loc_18003A512
0x180039885  cmp     [rdx+8], r15
0x180039889  jz      loc_18003A512
0x18003988f  mov     rax, [rbp+290h+var_1E0]
0x180039896  mov     [rsi+18h], rax
0x18003989a  mov     rax, [rbp+290h+pResult]
0x18003989e  mov     rax, [rax+8]
0x1800398a2  mov     [rsp+3B0h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800398aa  mov     rax, [rax+8]
0x1800398ae  mov     [rsp+3B0h+lpString2], rax; lpString2
0x1800398b3  or      r9d, 0FFFFFFFFh; cchCount1
0x1800398b7  mov     r8, [rbp+290h+lpString1]; lpString1
0x1800398be  mov     edx, r14d; dwCmpFlags
0x1800398c1  mov     ecx, 7Fh; Locale
0x1800398c6  call    cs:__imp_CompareStringW
0x1800398cc  cmp     eax, 2
0x1800398cf  jz      loc_180039A8D
0x1800398d5  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800398dc  jz      short loc_180039932
0x1800398de  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800398e5  test    rax, rax
0x1800398e8  jz      short loc_180039906
0x1800398ea  mov     rcx, [rbp+290h+pResult]
0x1800398ee  mov     r8, [rcx+8]
0x1800398f2  mov     r8, [r8+8]
0x1800398f6  lea     rdx, aEvaluatedeferr_7; "EvaluateDeferredGPOs: Doing an ldap bin"...
0x1800398fd  mov     ecx, edi
0x1800398ff  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
