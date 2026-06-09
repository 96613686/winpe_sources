# ProcessGPO(ushort const *,ulong,void *,_GROUP_POLICY_OBJECTW * *,_GPCONTAINER * *,ulong,int,int,_GPO_LINK,ushort const *,ldap *,ldapmsg *,int,void *,CGpoFilter *,CLocator *,int,_GPOINFO *,int)

- ea: `0x18003a810`
- end: `0x18003cf99`
- name: `?ProcessGPO@@YAHPEBGKPEAXPEAPEAU_GROUP_POLICY_OBJECTW@@PEAPEAU_GPCONTAINER@@KHHW4_GPO_LINK@@0PEAUldap@@PEAUldapmsg@@H1PEAVCGpoFilter@@PEAVCLocator@@HPEAU_GPOINFO@@H@Z`
- size: `10121`
- prototype: `int(const unsigned __int16 *, unsigned int, void *, struct _GROUP_POLICY_OBJECTW **, struct _GPCONTAINER **, unsigned int, int, int, enum _GPO_LINK, const unsigned __int16 *, struct ldap *, struct ldapmsg *, int, void *, struct CGpoFilter *, struct CLocator *, int, struct _GPOINFO *, int)`
- caller_count: `3`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180039184`
- `0x180039364`
- `0x18003e060`

## callees

- `0x1800184b4`
- `0x18001d6e8`
- `0x18002a5a0`
- `0x180030bcc`
- `0x18003a810`
- `0x18003cfa0`
- `0x18003d000`
- `0x18003d580`
- `0x18003d630`
- `0x18003d670`
- `0x18003d8d0`
- `0x180063ce4`
- `0x180067c90`
- `0x18006f470`
- `0x18006f894`
- `0x180073984`
- `0x180074ddc`
- `0x180075ec0`
- `0x18007d320`
- `0x18009c63c`
- `0x18009e9b4`
- `0x1800a445c`
- `0x1800a751c`
- `0x1800ba2f8`
- `0x1800ba464`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003aad5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003acbc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ca07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ca45`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003cf6d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003aad5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003acbc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ca07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ca45`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003cf6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a9d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ae22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b193`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b59a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b8f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bbd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bc25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bc80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003beef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c0a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c44e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c78e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c7b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c7fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c90b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c9ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ca10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cb38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a9d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ae22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b193`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b59a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b8f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bbd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bc25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bc80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003beef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c0a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c44e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c78e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c7b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c7fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c90b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c9ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ca10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cb38`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18003b684`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18003bceb`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18003b684`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18003bceb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003ab53`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003ab53`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b229`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b8e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003bed9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003c08f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003c43c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003c778`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b229`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b8e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003bed9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003c08f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003c43c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003c778`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bb80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bd85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bd98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ca1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003cbad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ced5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003cee3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003cef1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ceff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003cf0e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bb80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bd85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bd98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ca1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003cbad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ced5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003cee3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003cef1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ceff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003cf0e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003b629`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003bc90`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003b629`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003bc90`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18003b756`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18003b756`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003c339`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003c339`
- `WLDAP32!__imp_LdapGetLastError` at `0x18003cbb8`
- `WLDAP32!__imp_LdapGetLastError` at `0x18003cc50`
- `WLDAP32!__imp_LdapGetLastError` at `0x18003cd98`
- `WLDAP32!__imp_LdapGetLastError` at `0x18003ce37`
- `WLDAP32!__imp_LdapGetLastError` at `0x18003cbb8`
- `WLDAP32!__imp_LdapGetLastError` at `0x18003cc50`
- `WLDAP32!__imp_LdapGetLastError` at `0x18003cd98`
- `WLDAP32!__imp_LdapGetLastError` at `0x18003ce37`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003cbc0`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003cd2e`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003cdab`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003ce3f`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003cbc0`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003cd2e`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003cdab`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003ce3f`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18003b02a`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18003b732`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18003b77e`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18003b8a9`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18003beab`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18003c14b`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18003c27b`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18003c31d`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18003b02a`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18003b732`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18003b77e`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18003b8a9`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18003beab`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18003c14b`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18003c27b`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18003c31d`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003b111`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003b767`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003b7da`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003b896`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003b95e`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003ba32`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003bf54`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003c025`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003c268`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003c2f6`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003c4b3`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003c581`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003b111`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003b767`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003b7da`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003b896`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003b95e`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003ba32`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003bf54`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003c025`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003c268`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003c2f6`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003c4b3`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003c581`

## string_xrefs

- `0x18003a8c9`: `nTSecurityDescriptor`
- `0x18003c300`: `gPCUserExtensionNames`
- `0x18003c307`: `gPCMachineExtensionNames`
- `0x18003a92b`: `gPCFileSysPath`
- `0x18003ad59`: `ProcessGPO(%s): ProcessGPO called with GPO_LIST_FLAG_NO_SECURITYFILTERS, Security filters will be skipped`
- `0x18003adca`: `ProcessGPO(%s): ProcessGPO called with GPO_LIST_FLAG_NO_SECURITYFILTERS, Security filters will be skipped`
- `0x18003ae4d`: `ProcessGPO(%s):  CheckGPOAccess failed for <%s>`
- `0x18003ae92`: `ProcessGPO(%s):  CheckGPOAccess failed for <%s>`
- `0x18003aef6`: `ProcessGPO(%s):  Machine does not have access to the GPO and so will not be applied.`
- `0x18003af20`: `ProcessGPO(%s):  Machine does not have access to the GPO and so will not be applied.`
- `0x18003af42`: `ProcessGPO(%s):  User does not have access to the GPO and so will not be applied.`
- `0x18003af6c`: `ProcessGPO(%s):  User does not have access to the GPO and so will not be applied.`
- `0x18003ad9d`: `ProcessGPO(%s):  Machine has access to this GPO.`
- `0x18003afc6`: `ProcessGPO(%s):  Machine has access to this GPO.`
- `0x18003afe1`: `ProcessGPO(%s):  User has access to this GPO.`
- `0x18003b008`: `ProcessGPO(%s):  User has access to this GPO.`
- `0x18003b0cb`: `ProcessGPO(%s):  Found common name of:  <%s>`
- `0x18003b0fd`: `ProcessGPO(%s):  Found common name of:  <%s>`
- `0x18003ce6a`: `ProcessGPO(%s):  GPO %s does not have a common name (a GUID).`
- `0x18003ce9c`: `ProcessGPO(%s):  GPO %s does not have a common name (a GUID).`
- `0x18003b2d2`: `ProcessGPO(%s):  StringClone failed to copy GPOName.`
- `0x18003b2fd`: `ProcessGPO(%s):  StringClone failed to copy GPOName.`
- `0x18003cc86`: `ProcessGPO(%s):  Machine does not have access to <%s>`
- `0x18003ccb0`: `ProcessGPO(%s):  Machine does not have access to <%s>`
- `0x18003ccd5`: `ProcessGPO(%s):  User does not have access to <%s>`
- `0x18003ccff`: `ProcessGPO(%s):  User does not have access to <%s>`
- `0x18003b9f0`: `ProcessGPO(%s):  Found file system path of:  <%s>`
- `0x18003ba1e`: `ProcessGPO(%s):  Found file system path of:  <%s>`
- `0x18003bbed`: `ProcessGPO(%s):  Couldn't find the group policy template file <%s>, error = 0x%x. DC: %ls`
- `0x18003bc3b`: `ProcessGPO(%s):  Couldn't find the group policy template file <%s>, error = 0x%x. DC: %ls`
- `0x18003bdc3`: `ProcessGPO(%s):  Sysvol access skipped because GPO is not getting applied or is not needed.`
- `0x18003bdee`: `ProcessGPO(%s):  Sysvol access skipped because GPO is not getting applied or is not needed.`
- `0x18003cd5d`: `ProcessGPO(%s):  GPO %s does not have a file system path, error = 0x%x.`
- `0x18003cd8f`: `ProcessGPO(%s):  GPO %s does not have a file system path, error = 0x%x.`
- `0x18003c366`: `ProcessGPO(%s):  No client-side extensions for this object.`
- `0x18003c403`: `ProcessGPO(%s):  No client-side extensions for this object.`
- `0x18003c5a1`: `ProcessGPO(%s):  No client-side extensions for this object.`
- `0x18003c5cb`: `ProcessGPO(%s):  No client-side extensions for this object.`
- `0x18003c53f`: `ProcessGPO(%s):  Found extensions:  %s`
- `0x18003c56d`: `ProcessGPO(%s):  Found extensions:  %s`
- `0x18003c613`: `ProcessGPO(%s):  GPO %s was created by an old version of the Group Policy Editor.  It will be skipped.`
- `0x18003c63e`: `ProcessGPO(%s):  GPO %s was created by an old version of the Group Policy Editor.  It will be skipped.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ProcessGPO(
        WCHAR *a1,
        int a2,
        void *a3,
        struct _GROUP_POLICY_OBJECTW **a4,
        struct _GPCONTAINER **a5,
        unsigned int a6,
        int a7,
        int a8,
        enum _GPO_LINK a9,
        const unsigned __int16 *a10,
        struct ldap *a11,
        struct ldapmsg *a12,
        int a13,
        void *a14,
        struct CGpoFilter *a15,
        struct CLocator *a16,
        int a17,
        struct _GPOINFO *a18,
        int a19)
{
  char v20; // r14
  __int64 cchCount2; // rbx
  unsigned int LastError; // edi
  const wchar_t *v23; // r8
  int v24; // ecx
  void (*v25)(unsigned int, const unsigned __int16 *, ...); // rax
  int v27; // r14d
  int v28; // r8d
  int v29; // r9d
  unsigned __int16 *v30; // rdx
  unsigned int v31; // ebx
  void (*v32)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v33; // rsi
  void (*v34)(unsigned int, const unsigned __int16 *, ...); // rax
  struct ldap *v35; // rsi
  LDAPMessage *v36; // rbx
  void *v37; // rdx
  const wchar_t *v38; // r13
  WCHAR *v39; // rbx
  unsigned __int16 *v40; // r14
  unsigned __int16 *v41; // r15
  unsigned int v42; // r12d
  const unsigned __int16 **valuesW; // rax
  PWCHAR *v44; // rbx
  unsigned __int16 *v45; // r11
  __int64 v46; // rcx
  __int64 v47; // rdx
  unsigned __int16 *v48; // r8
  unsigned __int16 v49; // ax
  LDAPMessage *v50; // r15
  struct _GPWMIINFO *v51; // r14
  HLOCAL v52; // rsi
  void *v53; // rbx
  int v54; // eax
  __int64 v55; // rax
  int v56; // r12d
  int v57; // edx
  void (*v58)(unsigned int, const unsigned __int16 *, ...); // rax
  void *v59; // rcx
  unsigned __int16 *v60; // r13
  int v61; // ebx
  __int64 v62; // rdx
  __int64 v63; // r9
  int v64; // r12d
  unsigned int k; // ebx
  unsigned int v66; // ecx
  int *v67; // r8
  PWCHAR *v68; // rbx
  __int64 i; // rsi
  const WCHAR *v70; // rcx
  const unsigned __int16 **v71; // rax
  PWCHAR *v72; // rbx
  unsigned int v73; // r14d
  PWCHAR *v74; // rax
  PWCHAR *v75; // rbx
  __int64 v76; // rsi
  unsigned __int64 v77; // rsi
  unsigned __int16 *v78; // rax
  unsigned __int16 *v79; // r13
  __int64 v80; // rcx
  PWCHAR v81; // rdx
  unsigned __int64 v82; // r8
  unsigned __int16 *v83; // r9
  WCHAR v84; // ax
  unsigned __int16 *v85; // rax
  const char *v86; // rdx
  unsigned __int64 v87; // r8
  unsigned __int16 *v88; // r9
  unsigned __int16 *v89; // rbx
  unsigned __int64 v90; // rsi
  __int64 v91; // rcx
  unsigned __int16 v92; // ax
  unsigned int ValueFromAnsiTextFile; // eax
  unsigned int v94; // r15d
  unsigned int v95; // r13d
  unsigned __int16 *DCNameFromGPTPath; // rax
  unsigned __int16 *v97; // rbx
  void (*v98)(unsigned int, const unsigned __int16 *, ...); // rsi
  const wchar_t *v99; // r12
  const wchar_t *v100; // r12
  struct _GPWMIINFO *v101; // r14
  unsigned __int16 *v102; // r13
  int v103; // esi
  int v104; // r12d
  unsigned int j; // esi
  unsigned int v106; // ecx
  int *v107; // r8
  __int64 v108; // rcx
  wchar_t v109; // ax
  __int64 v110; // rcx
  unsigned __int16 v111; // ax
  PWCHAR *v112; // rax
  PWCHAR *v113; // rsi
  __int64 v114; // rbx
  unsigned __int64 v115; // rbx
  WCHAR *v116; // r8
  __int64 v117; // rcx
  PWCHAR v118; // rdx
  WCHAR v119; // ax
  LDAPMessage *v120; // r12
  const unsigned __int16 **v121; // rax
  PWCHAR *v122; // rbx
  unsigned int v123; // eax
  unsigned int v124; // r13d
  const unsigned __int16 *v125; // rdx
  const unsigned __int16 **v126; // rax
  PWCHAR *v127; // rbx
  unsigned int v128; // r12d
  const wchar_t *v129; // rbx
  WCHAR *v130; // r8
  LPCWSTR *v131; // rax
  PWCHAR *v132; // rsi
  __int64 v133; // rbx
  unsigned __int64 v134; // rbx
  unsigned __int16 *v135; // rax
  __int64 v136; // rcx
  PWCHAR v137; // rdx
  WCHAR *v138; // r8
  WCHAR v139; // ax
  int v140; // r15d
  int v141; // r14d
  __int64 v142; // rax
  unsigned __int64 v143; // rbx
  unsigned __int16 *v144; // rax
  unsigned __int16 *v145; // rsi
  void (*v146)(unsigned int, const unsigned __int16 *, ...); // rsi
  DWORD v147; // eax
  DWORD v148; // eax
  const wchar_t *v149; // rcx
  unsigned __int64 v150; // r8
  unsigned __int16 *v151; // rdx
  __int64 v152; // r9
  wchar_t v153; // ax
  const wchar_t *v154; // rcx
  unsigned __int64 v155; // r8
  __int64 v156; // r9
  wchar_t v157; // ax
  int v158; // r8d
  int v159; // r9d
  HLOCAL v160; // rsi
  int v161; // r14d
  unsigned int v162; // r15d
  struct _GPOINFO *v163; // r12
  DWORD v164; // ebx
  int v165; // r13d
  int v166; // r12d
  __int64 v167; // rcx
  _QWORD *v168; // rdx
  ULONG v169; // eax
  ULONG v170; // eax
  ULONG v171; // ebx
  const unsigned __int16 *v172; // rdx
  ULONG v173; // eax
  LDAPMessage *v174; // rdx
  ULONG v175; // eax
  PCNZWCH lpString2; // [rsp+20h] [rbp-110h]
  struct _GPOINFO *v177; // [rsp+48h] [rbp-E8h]
  int v178; // [rsp+58h] [rbp-D8h]
  __int64 v179; // [rsp+60h] [rbp-D0h]
  __int64 v180; // [rsp+60h] [rbp-D0h]
  int v181; // [rsp+68h] [rbp-C8h]
  int v182; // [rsp+98h] [rbp-98h]
  const wchar_t *v183; // [rsp+B0h] [rbp-80h]
  int v184; // [rsp+B8h] [rbp-78h]
  WCHAR *v185; // [rsp+C0h] [rbp-70h]
  unsigned __int16 *v186; // [rsp+C8h] [rbp-68h]
  unsigned __int16 *v187; // [rsp+D0h] [rbp-60h]
  int ld; // [rsp+E8h] [rbp-48h]
  DWORD lda; // [rsp+E8h] [rbp-48h]
  int ldb; // [rsp+E8h] [rbp-48h]
  int v192; // [rsp+F0h] [rbp-40h] BYREF
  int v193; // [rsp+F4h] [rbp-3Ch]
  LDAPMessage *entry; // [rsp+F8h] [rbp-38h]
  unsigned int v195; // [rsp+100h] [rbp-30h] BYREF
  int v196; // [rsp+104h] [rbp-2Ch]
  int v197; // [rsp+108h] [rbp-28h]
  int v198[2]; // [rsp+110h] [rbp-20h] BYREF
  unsigned int v199; // [rsp+118h] [rbp-18h] BYREF
  struct _GPWMIINFO *v200; // [rsp+120h] [rbp-10h]
  HLOCAL v201; // [rsp+128h] [rbp-8h]
  unsigned __int16 *v202; // [rsp+130h] [rbp+0h]
  struct _GPCONTAINER **v203; // [rsp+138h] [rbp+8h]
  HLOCAL v204; // [rsp+140h] [rbp+10h] BYREF
  HLOCAL v205; // [rsp+148h] [rbp+18h] BYREF
  __int64 v206; // [rsp+150h] [rbp+20h]
  int v207[2]; // [rsp+158h] [rbp+28h]
  const wchar_t *v208; // [rsp+160h] [rbp+30h]
  _QWORD v209[14]; // [rsp+170h] [rbp+40h] BYREF
  void **v210; // [rsp+1E0h] [rbp+B0h] BYREF
  HLOCAL hMem; // [rsp+1E8h] [rbp+B8h]
  __int64 v212; // [rsp+1F0h] [rbp+C0h]
  __int64 *v213; // [rsp+1F8h] [rbp+C8h]
  __int64 v214; // [rsp+200h] [rbp+D0h]
  const char *v215; // [rsp+208h] [rbp+D8h]
  int v216; // [rsp+214h] [rbp+E4h]
  int v217; // [rsp+218h] [rbp+E8h]
  int v218; // [rsp+238h] [rbp+108h]
  unsigned __int16 *v219; // [rsp+258h] [rbp+128h]
  WCHAR attr[4]; // [rsp+260h] [rbp+130h] BYREF
  WCHAR v221[8]; // [rsp+268h] [rbp+138h] BYREF
  WCHAR String2[8]; // [rsp+278h] [rbp+148h] BYREF
  unsigned __int16 v223[16]; // [rsp+288h] [rbp+158h] BYREF
  WCHAR v224[12]; // [rsp+2A8h] [rbp+178h] BYREF
  wchar_t v225[16]; // [rsp+2C0h] [rbp+190h] BYREF
  wchar_t v226[16]; // [rsp+2E0h] [rbp+1B0h] BYREF
  unsigned __int16 v227[8]; // [rsp+300h] [rbp+1D0h] BYREF
  _OWORD v228[2]; // [rsp+310h] [rbp+1E0h]
  WCHAR v229[24]; // [rsp+330h] [rbp+200h] BYREF
  unsigned __int16 v230[80]; // [rsp+360h] [rbp+230h] BYREF

  *(_QWORD *)v207 = a4;
  v20 = a2;
  v196 = a2;
  v203 = a5;
  v206 = (__int64)a10;
  entry = a12;
  v200 = a18;
  v198[0] = 0;
  v195 = 0;
  wcscpy(String2, L"LDAP://");
  cchCount2 = -1;
  do
    ++cchCount2;
  while ( String2[cchCount2] );
  *(_OWORD *)v227 = *(_OWORD *)L"nTSecurityDescriptor";
  v228[0] = *(_OWORD *)L"tyDescriptor";
  *(_OWORD *)((char *)v228 + 10) = *(_OWORD *)L"criptor";
  wcscpy(attr, L"cn");
  wcscpy(v224, L"displayName");
  wcscpy(v226, L"gPCFilSysPath");
  wcscpy(v225, L"versnNumber");
  wcscpy(v229, L"gPCFunctionalityVersion");
  wcscpy(v221, L"flags");
  *(_OWORD *)v223 = *(_OWORD *)L"gPCWQLFilter";
  *(_OWORD *)&v223[5] = *(_OWORD *)L"LFilter";
  v205 = 0;
  v199 = 0;
  v192 = 0;
  v204 = 0;
  LastError = GetLastError();
  v193 = v20 & 1;
  v201 = (HLOCAL)L"User";
  v208 = L"Machine";
  v23 = L"Machine";
  if ( (v20 & 1) == 0 )
    v23 = L"User";
  v183 = v23;
  v24 = *(_DWORD *)&g_dwDebugLevel;
  v25 = g_lpDebugMsg;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"ProcessGPO(%s):  ==============================");
LABEL_11:
      v25 = g_lpDebugMsg;
      v24 = *(_DWORD *)&g_dwDebugLevel;
      goto LABEL_12;
    }
    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"ProcessGPO(%s):  ==============================");
      goto LABEL_11;
    }
  }
LABEL_12:
  if ( v200 && *((_DWORD *)v200 + 60) )
  {
    if ( v24 )
    {
      if ( v25 )
      {
        v25(2u, L"ProcessGPO(%s): Aborting GetGPOs processing due to machine shutdown or user logoff.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"ProcessGPO(%s): Aborting GetGPOs processing due to machine shutdown or user logoff.");
      }
    }
    if ( (unsigned int)CGPTestOperationalTraceEvent::IsEnabled() )
      CGPOperationalTraceEvent::ReportOperationalEvent(0x1052u, 0x1Fu);
    SetLastError(LastError);
    return 0;
  }
  v27 = 0;
  if ( (v196 & 4) != 0 )
  {
    v27 = 1;
    if ( v24 )
    {
      if ( v25 )
      {
        v25(4u, L"ProcessGPO(%s): ProcessGPO called with GPO_LIST_FLAG_NO_WMIFILTERS, WMI filters will be skipped");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(
          4u,
          L"ProcessGPO(%s): ProcessGPO called with GPO_LIST_FLAG_NO_WMIFILTERS, WMI filters will be skipped");
      }
    }
  }
  if ( CompareStringW(0x7Fu, 1u, a1, cchCount2, String2, cchCount2) == 2 )
    v30 = &a1[(int)cchCount2];
  else
    v30 = a1;
  v202 = v30;
  if ( a7 )
  {
    v31 = AddGPO(
            v207[0],
            v196,
            v28,
            v29,
            (int)lpString2,
            a6,
            0,
            v30,
            0,
            0,
            0,
            0,
            v179,
            v181,
            a9,
            v206,
            0,
            0,
            a13,
            v182,
            a17);
    if ( v31 )
    {
      v33 = v183;
    }
    else
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
      {
LABEL_49:
        SetLastError(LastError);
        return v31;
      }
      v32 = g_lpDebugMsg;
      v33 = v183;
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"ProcessGPO(%s):  Failed to add GPO <%s> to the list.", v183, v202);
      }
      else
      {
        if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
        {
LABEL_43:
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( v32 )
            {
              v32(4u, L"ProcessGPO(%s):  Deferring search for <%s>", v33, a1);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(4u, L"ProcessGPO(%s):  Deferring search for <%s>", v33, a1);
            }
          }
          goto LABEL_49;
        }
        RedirectDebugMsg(2u, L"ProcessGPO(%s):  Failed to add GPO <%s> to the list.", v183, v202);
      }
    }
    v32 = g_lpDebugMsg;
    goto LABEL_43;
  }
  v184 = 0;
  v187 = 0;
  v34 = g_lpDebugMsg;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"ProcessGPO(%s):  Searching <%s>", v183, a1);
LABEL_56:
      v34 = g_lpDebugMsg;
      goto LABEL_57;
    }
    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"ProcessGPO(%s):  Searching <%s>", v183, a1);
      goto LABEL_56;
    }
  }
LABEL_57:
  if ( (v196 & 8) != 0 )
  {
    v197 = 1;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( v34 )
      {
        v34(
          4u,
          L"ProcessGPO(%s): ProcessGPO called with GPO_LIST_FLAG_NO_SECURITYFILTERS, Security filters will be skipped",
          v183);
      }
      else
      {
        if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
          goto LABEL_62;
        RedirectDebugMsg(
          4u,
          L"ProcessGPO(%s): ProcessGPO called with GPO_LIST_FLAG_NO_SECURITYFILTERS, Security filters will be skipped",
          v183);
      }
      v34 = g_lpDebugMsg;
    }
LABEL_62:
    v35 = a11;
    v36 = entry;
    goto LABEL_63;
  }
  v36 = entry;
  v37 = a3;
  v35 = a11;
  if ( (unsigned int)CheckGPOAccess(a11, v37, entry, v227, (unsigned int)lpString2, &v205, &v199, v198, a14) )
  {
    v197 = v198[0];
    if ( v198[0] )
    {
      v34 = g_lpDebugMsg;
LABEL_63:
      if ( v193 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( v34 )
          {
            v34(4u, L"ProcessGPO(%s):  Machine has access to this GPO.", v183);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"ProcessGPO(%s):  Machine has access to this GPO.", v183);
          }
        }
      }
      else if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( v34 )
        {
          v34(4u, L"ProcessGPO(%s):  User has access to this GPO.", v183);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"ProcessGPO(%s):  User has access to this GPO.", v183);
        }
      }
      goto LABEL_106;
    }
    if ( v193 )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_94;
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"ProcessGPO(%s):  Machine does not have access to the GPO and so will not be applied.", v183);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(
          4u,
          L"ProcessGPO(%s):  Machine does not have access to the GPO and so will not be applied.",
          v183);
      }
    }
    else
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_94;
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"ProcessGPO(%s):  User does not have access to the GPO and so will not be applied.", v183);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"ProcessGPO(%s):  User does not have access to the GPO and so will not be applied.", v183);
      }
    }
    v35 = a11;
LABEL_94:
    v184 = 1;
    if ( !v203 )
      goto LABEL_95;
LABEL_106:
    valuesW = (const unsigned __int16 **)ldap_get_valuesW(v35, v36, attr);
    v44 = (PWCHAR *)valuesW;
    if ( valuesW && (unsigned int)ValidateGuid(*valuesW) )
    {
      v46 = 2147483646;
      v47 = 80;
      v48 = v230;
      while ( v46 )
      {
        v49 = *v45;
        if ( !*v45 )
          break;
        ++v45;
        *v48++ = v49;
        --v46;
        if ( !--v47 )
        {
          *(v48 - 1) = 0;
          LastError = 122;
          v39 = 0;
          v40 = 0;
          v41 = 0;
          goto LABEL_581;
        }
      }
      *v48 = 0;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"ProcessGPO(%s):  Found common name of:  <%s>", v183, v230);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"ProcessGPO(%s):  Found common name of:  <%s>", v183, v230);
        }
      }
      ldap_value_freeW(v44);
      if ( !v197 )
      {
        v192 = 0;
        v50 = entry;
        v56 = v193;
        goto LABEL_208;
      }
      if ( v27 )
      {
        v192 = 1;
        v50 = entry;
        goto LABEL_156;
      }
      v51 = v200;
      if ( !v200 )
      {
        v50 = entry;
        if ( !(unsigned int)FilterCheck(v35, entry, a14, v223, a15, a16, &v192, (unsigned __int16 **)&v204, 0, 0)
          || (CGPServiceEventReporting::s_dwTestFlags & 0x20) != 0 )
        {
          LastError = GetLastError();
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              v38 = v183;
              g_lpDebugMsg(2u, L"ProcessGPO(%s):  CheckFilterAcess failed for <%s>", v183, a1);
              goto LABEL_131;
            }
            if ( g_lpDebugMsgContextInstance )
            {
              v38 = v183;
              if ( g_lpDebugMsgContext )
                RedirectDebugMsg(2u, L"ProcessGPO(%s):  CheckFilterAcess failed for <%s>", v183, a1);
              goto LABEL_131;
            }
          }
LABEL_95:
          v39 = 0;
          v40 = 0;
          v41 = 0;
LABEL_581:
          v42 = v184;
          goto LABEL_582;
        }
LABEL_156:
        v56 = v193;
        if ( (v196 & 0x800000) != 0 )
        {
          if ( v193 )
          {
            if ( (v196 & 0x2000000) != 0 )
            {
              v192 = 1;
              v57 = *(_DWORD *)&g_dwDebugLevel;
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                v58 = g_lpDebugMsg;
                if ( g_lpDebugMsg )
                {
                  v38 = v183;
                  g_lpDebugMsg(4u, L"ProcessGPO(%s):  Machine WQL filter is assumed to be true.", v183);
LABEL_174:
                  if ( !v192 )
                  {
                    if ( *(_DWORD *)&g_dwDebugLevel )
                    {
                      if ( g_lpDebugMsg )
                      {
                        g_lpDebugMsg(
                          4u,
                          L"ProcessGPO(%s):  The GPO does not pass the filter check and so will not be applied.",
                          v38);
                      }
                      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                      {
                        RedirectDebugMsg(
                          4u,
                          L"ProcessGPO(%s):  The GPO does not pass the filter check and so will not be applied.",
                          v38);
                      }
                      v35 = a11;
                    }
                    v184 = 1;
                    if ( v203 )
                      goto LABEL_209;
LABEL_131:
                    v39 = 0;
                    v40 = 0;
                    v41 = 0;
LABEL_132:
                    v42 = v184;
                    goto LABEL_583;
                  }
                  v57 = *(_DWORD *)&g_dwDebugLevel;
                  v58 = g_lpDebugMsg;
                  v59 = g_lpDebugMsgContextInstance;
LABEL_185:
                  if ( v57 )
                  {
                    if ( v58 )
                    {
                      v58(4u, L"ProcessGPO(%s):  GPO passes the filter check.", v38);
                    }
                    else if ( v59 && g_lpDebugMsgContext )
                    {
                      RedirectDebugMsg(4u, L"ProcessGPO(%s):  GPO passes the filter check.", v38);
                    }
                  }
LABEL_209:
                  v68 = ldap_get_valuesW(v35, v50, szObjectClass);
                  if ( v68 )
                  {
                    for ( i = 0; ; i = (unsigned int)(i + 1) )
                    {
                      v70 = v68[i];
                      if ( !v70 )
                        break;
                      if ( !lstrcmpW(v70, szDSClassGPO) )
                      {
                        ldap_value_freeW(v68);
                        v35 = a11;
                        goto LABEL_215;
                      }
                    }
                    ldap_value_freeW(v68);
                    LastError = 8316;
                    if ( *(_DWORD *)&g_dwDebugLevel )
                    {
                      if ( g_lpDebugMsg )
                      {
                        g_lpDebugMsg(2u, L"ProcessGPO(%s):  Object <%s> is not a GPO", v38, a1);
                      }
                      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                      {
                        RedirectDebugMsg(2u, L"ProcessGPO(%s):  Object <%s> is not a GPO", v38, a1);
                        v39 = 0;
                        v40 = 0;
                        v41 = 0;
                        v42 = v184;
                        goto LABEL_583;
                      }
                    }
                    goto LABEL_131;
                  }
LABEL_215:
                  v71 = (const unsigned __int16 **)ldap_get_valuesW(v35, v50, v229);
                  v72 = (PWCHAR *)v71;
                  if ( v71 )
                  {
                    v73 = StringToInt(*v71);
                    v198[0] = v73;
                    if ( *(_DWORD *)&g_dwDebugLevel )
                    {
                      if ( g_lpDebugMsg )
                      {
                        g_lpDebugMsg(4u, L"ProcessGPO(%s):  Found functionality version of:  %d", v38, v73);
                      }
                      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                      {
                        RedirectDebugMsg(4u, L"ProcessGPO(%s):  Found functionality version of:  %d", v38, v73);
                      }
                    }
                    ldap_value_freeW(v72);
                    v74 = ldap_get_valuesW(v35, v50, v226);
                    v75 = v74;
                    if ( v74 )
                    {
                      v76 = -1;
                      do
                        ++v76;
                      while ( (*v74)[v76] );
                      v77 = v76 + 9;
                      v78 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v77);
                      v79 = v78;
                      v186 = v78;
                      if ( !v78 )
                      {
                        LastError = GetLastError();
                        v38 = v183;
                        if ( *(_DWORD *)&g_dwDebugLevel )
                        {
                          if ( g_lpDebugMsg )
                          {
                            g_lpDebugMsg(2u, L"ProcessGPO(%s):  Unable to allocate memory", v183);
                          }
                          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                          {
                            RedirectDebugMsg(2u, L"ProcessGPO(%s):  Unable to allocate memory", v183);
                          }
                        }
                        ldap_value_freeW(v75);
                        v39 = 0;
                        v40 = 0;
                        v41 = 0;
                        v42 = v184;
                        goto LABEL_583;
                      }
                      if ( v77 )
                      {
                        if ( v77 <= 0x7FFFFFFF )
                        {
                          v80 = 2147483646;
                          v81 = *v75;
                          v82 = v77;
                          v83 = v78;
                          while ( v80 )
                          {
                            v84 = *v81;
                            if ( !*v81 )
                              break;
                            ++v81;
                            *v83++ = v84;
                            --v80;
                            if ( !--v82 )
                            {
                              --v83;
                              break;
                            }
                          }
                          *v83 = 0;
                        }
                        else
                        {
                          *v78 = 0;
                        }
                      }
                      if ( *(_DWORD *)&g_dwDebugLevel )
                      {
                        if ( g_lpDebugMsg )
                        {
                          g_lpDebugMsg(4u, L"ProcessGPO(%s):  Found file system path of:  <%s>", v183, v79);
                        }
                        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                        {
                          RedirectDebugMsg(4u, L"ProcessGPO(%s):  Found file system path of:  <%s>", v183, v79);
                        }
                      }
                      ldap_value_freeW(v75);
                      v85 = CheckSlash(v79);
                      v89 = v85;
                      v90 = v77 - (v85 - v79);
                      if ( v90 )
                      {
                        if ( v90 <= 0x7FFFFFFF )
                        {
                          v91 = 2147483646;
                          v86 = (const char *)L"gpt.ini";
                          v87 = v90;
                          v88 = v85;
                          while ( v91 )
                          {
                            v92 = *(_WORD *)v86;
                            if ( !*(_WORD *)v86 )
                              break;
                            v86 += 2;
                            *v88++ = v92;
                            --v91;
                            if ( !--v87 )
                            {
                              --v88;
                              break;
                            }
                          }
                          *v88 = 0;
                        }
                        else
                        {
                          *v85 = 0;
                        }
                      }
                      if ( v197 && (v200 || v192) )
                      {
                        hMem = 0;
                        v212 = 0;
                        v213 = API_CALL_TRACING_END_SUCCESS;
                        v214 = 0;
                        v215 = "i\x1B";
                        v210 = &CAPICallScenarioEvent::`vftable';
                        v216 = 0;
                        v217 = 4131;
                        v218 = 4132;
                        v219 = v79;
                        if ( a19 )
                          CAPICallScenarioEvent::ReportStartEvent((CAPICallScenarioEvent *)&v210);
                        ValueFromAnsiTextFile = GetValueFromAnsiTextFile(v79, v86, v87, (unsigned int)v88, &v195);
                        v94 = ValueFromAnsiTextFile;
                        if ( ValueFromAnsiTextFile || (CGPServiceEventReporting::s_dwTestFlags & 0x40) != 0 )
                        {
                          LastError = ValueFromAnsiTextFile;
                          DCNameFromGPTPath = GetDCNameFromGPTPath(v79);
                          v97 = DCNameFromGPTPath;
                          *(_QWORD *)v207 = DCNameFromGPTPath;
                          if ( *(_DWORD *)&g_dwDebugLevel )
                          {
                            v98 = g_lpDebugMsg;
                            if ( g_lpDebugMsg )
                            {
                              v99 = L"<null>";
                              if ( DCNameFromGPTPath )
                                v99 = DCNameFromGPTPath;
                              LODWORD(lpString2) = GetLastError();
                              v98(
                                2u,
                                L"ProcessGPO(%s):  Couldn't find the group policy template file <%s>, error = 0x%x. DC: %ls",
                                v183,
                                v79,
                                lpString2,
                                v99);
                            }
                            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                            {
                              v100 = L"<null>";
                              if ( DCNameFromGPTPath )
                                v100 = DCNameFromGPTPath;
                              LODWORD(lpString2) = GetLastError();
                              RedirectDebugMsg(
                                2u,
                                L"ProcessGPO(%s):  Couldn't find the group policy template file <%s>, error = 0x%x. DC: %ls",
                                v183,
                                v79,
                                lpString2,
                                v100);
                            }
                          }
                          if ( a19 )
                          {
                            CGPPolicyApplicationScenarioEvent::ReportEndEvent(
                              (CGPPolicyApplicationScenarioEvent *)&v210,
                              v94);
                            v101 = v200;
                            if ( v200 )
                            {
                              v102 = v97;
                              if ( !v97 )
                                v102 = (unsigned __int16 *)*((_QWORD *)v200 + 33);
                              lda = GetLastError();
                              v103 = *((_DWORD *)v101 + 64);
                              v104 = GetTickCount() - v103;
                              LODWORD(entry) = *((_DWORD *)v101 + 70);
                              for ( j = 0; j < 6; ++j )
                              {
                                if ( FindNLSString(
                                       0x7Fu,
                                       0x200001u,
                                       L"ds\\grouppolicy\\client\\gpsvc\\engine\\gpqry.cpp",
                                       -1,
                                       (LPCWSTR)*(&GPSourceFileNameIdTable + 2 * j),
                                       -1,
                                       0) != -1 )
                                {
                                  v106 = *((_DWORD *)&GPSourceFileNameIdTable + 4 * j + 2);
                                  goto LABEL_295;
                                }
                              }
                              v106 = -1;
LABEL_295:
                              CGPAdminEventGPOFileFailure::CGPAdminEventGPOFileFailure(
                                (CGPAdminEventGenericFailure *)v209,
                                (__int64)gpEvent_GPT_NOTACCESSIBLE,
                                v106,
                                921,
                                (int)entry,
                                v104,
                                lda,
                                v102,
                                a1,
                                v186);
                              CGPPolicyEventReporting::Report(
                                *((CGPPolicyEventReporting **)v200 + 34),
                                (struct CGPEventInfo *)v209,
                                v107);
                              v209[0] = &CGPAdminEventLdapFailure::`vftable';
                              CGPAdminEventInitFailure::~CGPAdminEventInitFailure((CGPAdminEventInitFailure *)v209);
                            }
                          }
                          if ( v97 )
                            LocalFree(v97);
                          if ( hMem )
                            LocalFree(hMem);
                          v39 = 0;
                          v41 = 0;
LABEL_580:
                          v40 = v186;
                          goto LABEL_581;
                        }
                        if ( a19 )
                          CGPPolicyApplicationScenarioEvent::ReportEndEvent(
                            (CGPPolicyApplicationScenarioEvent *)&v210,
                            0);
                        if ( hMem )
                          LocalFree(hMem);
                        v95 = v195;
                        v73 = v198[0];
                      }
                      else
                      {
                        if ( *(_DWORD *)&g_dwDebugLevel )
                        {
                          if ( g_lpDebugMsg )
                          {
                            g_lpDebugMsg(
                              4u,
                              L"ProcessGPO(%s):  Sysvol access skipped because GPO is not getting applied or is not needed.",
                              v183);
                          }
                          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                          {
                            RedirectDebugMsg(
                              4u,
                              L"ProcessGPO(%s):  Sysvol access skipped because GPO is not getting applied or is not needed.",
                              v183);
                          }
                        }
                        v95 = -1;
                      }
                      if ( v193 )
                      {
                        if ( v90 )
                        {
                          if ( v90 <= 0x7FFFFFFF )
                          {
                            v108 = 2147483646;
                            while ( v108 )
                            {
                              v109 = *v208;
                              if ( !*v208 )
                                break;
                              ++v208;
                              *v89++ = v109;
                              --v108;
                              if ( !--v90 )
                                goto LABEL_325;
                            }
                          }
LABEL_326:
                          *v89 = 0;
                        }
                      }
                      else if ( v90 )
                      {
                        if ( v90 <= 0x7FFFFFFF )
                        {
                          v110 = 2147483646;
                          while ( v110 )
                          {
                            v111 = *(_WORD *)v201;
                            if ( !*(_WORD *)v201 )
                              break;
                            v201 = (char *)v201 + 2;
                            *v89++ = v111;
                            --v110;
                            if ( !--v90 )
                            {
LABEL_325:
                              --v89;
                              goto LABEL_326;
                            }
                          }
                        }
                        goto LABEL_326;
                      }
                      v112 = ldap_get_valuesW(a11, entry, v224);
                      v113 = v112;
                      if ( v112 )
                      {
                        v114 = -1;
                        do
                          ++v114;
                        while ( (*v112)[v114] );
                        v115 = v114 + 1;
                        v116 = (WCHAR *)LocalAlloc(0x40u, 2 * v115);
                        v185 = v116;
                        if ( !v116 )
                        {
                          LastError = GetLastError();
                          v38 = v183;
                          if ( *(_DWORD *)&g_dwDebugLevel )
                          {
                            if ( g_lpDebugMsg )
                            {
                              g_lpDebugMsg(2u, L"ProcessGPO(%s):  Unable to allocate memory", v183);
                            }
                            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                            {
                              RedirectDebugMsg(2u, L"ProcessGPO(%s):  Unable to allocate memory", v183);
                            }
                          }
                          ldap_value_freeW(v113);
                          goto LABEL_338;
                        }
                        if ( v115 )
                        {
                          if ( v115 <= 0x7FFFFFFF )
                          {
                            v117 = 2147483646;
                            v118 = *v113;
                            while ( v117 )
                            {
                              v119 = *v118;
                              if ( !*v118 )
                                break;
                              ++v118;
                              *v116++ = v119;
                              --v117;
                              if ( !--v115 )
                              {
                                --v116;
                                break;
                              }
                            }
                            *v116 = 0;
                            v116 = v185;
                          }
                          else
                          {
                            *v116 = 0;
                          }
                        }
                        if ( *(_DWORD *)&g_dwDebugLevel )
                        {
                          if ( g_lpDebugMsg )
                          {
                            g_lpDebugMsg(4u, L"ProcessGPO(%s):  Found display name of:  <%s>", v183, v116);
                          }
                          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                          {
                            RedirectDebugMsg(4u, L"ProcessGPO(%s):  Found display name of:  <%s>", v183, v116);
                          }
                        }
                        ldap_value_freeW(v113);
LABEL_369:
                        v120 = entry;
                        v121 = (const unsigned __int16 **)ldap_get_valuesW(a11, entry, v225);
                        v122 = (PWCHAR *)v121;
                        if ( v121 )
                        {
                          v123 = StringToInt(*v121);
                          if ( v193 )
                          {
                            v124 = (unsigned __int16)v123 | ((unsigned __int16)v95 << 16);
                            v198[0] = v124;
                            if ( !*(_DWORD *)&g_dwDebugLevel )
                              goto LABEL_384;
                            if ( g_lpDebugMsg )
                            {
                              LODWORD(lpString2) = HIWORD(v124);
                              g_lpDebugMsg(
                                4u,
                                L"ProcessGPO(%s):  Found machine version of:  GPC is %d, GPT is %d",
                                v183,
                                (unsigned __int16)v124);
                              goto LABEL_384;
                            }
                            if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                            {
                              v125 = L"ProcessGPO(%s):  Found machine version of:  GPC is %d, GPT is %d";
LABEL_383:
                              LODWORD(lpString2) = HIWORD(v124);
                              RedirectDebugMsg(4u, v125, v183, (unsigned __int16)v124, lpString2);
                            }
                          }
                          else
                          {
                            v124 = HIWORD(v123) | v95 & 0xFFFF0000;
                            v198[0] = v124;
                            if ( !*(_DWORD *)&g_dwDebugLevel )
                              goto LABEL_384;
                            if ( g_lpDebugMsg )
                            {
                              LODWORD(lpString2) = HIWORD(v124);
                              g_lpDebugMsg(
                                4u,
                                L"ProcessGPO(%s):  Found user version of:  GPC is %d, GPT is %d",
                                v183,
                                (unsigned __int16)v124);
                              goto LABEL_384;
                            }
                            if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                            {
                              v125 = L"ProcessGPO(%s):  Found user version of:  GPC is %d, GPT is %d";
                              goto LABEL_383;
                            }
                          }
LABEL_384:
                          ldap_value_freeW(v122);
                          v126 = (const unsigned __int16 **)ldap_get_valuesW(a11, v120, v221);
                          v127 = (PWCHAR *)v126;
                          if ( v126 )
                          {
                            v128 = StringToInt(*v126);
                            if ( *(_DWORD *)&g_dwDebugLevel )
                            {
                              if ( g_lpDebugMsg )
                              {
                                g_lpDebugMsg(4u, L"ProcessGPO(%s):  Found flags of:  %d", v183, v128);
                              }
                              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                              {
                                RedirectDebugMsg(4u, L"ProcessGPO(%s):  Found flags of:  %d", v183, v128);
                              }
                            }
                            ldap_value_freeW(v127);
                            goto LABEL_392;
                          }
                          LOBYTE(v128) = 0;
                          if ( *(_DWORD *)&g_dwDebugLevel )
                          {
                            if ( g_lpDebugMsg )
                            {
                              v129 = v183;
                              g_lpDebugMsg(4u, L"ProcessGPO(%s):  No flags for this object.", v183);
                              goto LABEL_393;
                            }
                            if ( g_lpDebugMsgContextInstance )
                            {
                              v129 = v183;
                              if ( g_lpDebugMsgContext )
                                RedirectDebugMsg(4u, L"ProcessGPO(%s):  No flags for this object.", v183);
LABEL_393:
                              v130 = L"gPCMachineExtensionNames";
                              if ( !v193 )
                                v130 = (WCHAR *)L"gPCUserExtensionNames";
                              v131 = (LPCWSTR *)ldap_get_valuesW(a11, entry, v130);
                              v132 = (PWCHAR *)v131;
                              if ( v131 )
                              {
                                if ( lstrcmpiW(*v131, L" ") )
                                {
                                  v133 = -1;
                                  do
                                    ++v133;
                                  while ( (*v132)[v133] );
                                  v134 = v133 + 1;
                                  v135 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v134);
                                  v41 = v135;
                                  v187 = v135;
                                  if ( !v135 )
                                  {
                                    LastError = GetLastError();
                                    v38 = v183;
                                    if ( *(_DWORD *)&g_dwDebugLevel )
                                    {
                                      if ( g_lpDebugMsg )
                                      {
                                        g_lpDebugMsg(2u, L"ProcessGPO(%s):  Unable to allocate memory", v183);
                                      }
                                      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                                      {
                                        RedirectDebugMsg(2u, L"ProcessGPO(%s):  Unable to allocate memory", v183);
                                      }
                                    }
                                    ldap_value_freeW(v132);
                                    v39 = v185;
                                    v40 = v186;
                                    goto LABEL_132;
                                  }
                                  v195 = 0;
                                  if ( v134 )
                                  {
                                    if ( v134 <= 0x7FFFFFFF )
                                    {
                                      v136 = 2147483646;
                                      v137 = *v132;
                                      v138 = v135;
                                      while ( v136 )
                                      {
                                        v139 = *v137;
                                        if ( !*v137 )
                                          break;
                                        ++v137;
                                        *v138++ = v139;
                                        --v136;
                                        if ( !--v134 )
                                        {
                                          --v138;
                                          break;
                                        }
                                      }
                                      *v138 = 0;
                                    }
                                    else
                                    {
                                      *v135 = 0;
                                    }
                                  }
                                  if ( *(_DWORD *)&g_dwDebugLevel )
                                  {
                                    if ( g_lpDebugMsg )
                                    {
                                      g_lpDebugMsg(4u, L"ProcessGPO(%s):  Found extensions:  %s", v183, v41);
                                    }
                                    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                                    {
                                      RedirectDebugMsg(4u, L"ProcessGPO(%s):  Found extensions:  %s", v183, v41);
                                    }
                                  }
                                }
                                else
                                {
                                  if ( *(_DWORD *)&g_dwDebugLevel )
                                  {
                                    if ( g_lpDebugMsg )
                                    {
                                      g_lpDebugMsg(
                                        4u,
                                        L"ProcessGPO(%s):  No client-side extensions for this object.",
                                        v129);
                                    }
                                    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                                    {
                                      RedirectDebugMsg(
                                        4u,
                                        L"ProcessGPO(%s):  No client-side extensions for this object.",
                                        v129);
                                    }
                                  }
                                  v195 = 1;
                                }
                                ldap_value_freeW(v132);
                              }
                              else
                              {
                                if ( *(_DWORD *)&g_dwDebugLevel )
                                {
                                  if ( g_lpDebugMsg )
                                  {
                                    g_lpDebugMsg(
                                      4u,
                                      L"ProcessGPO(%s):  No client-side extensions for this object.",
                                      v129);
                                  }
                                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                                  {
                                    RedirectDebugMsg(
                                      4u,
                                      L"ProcessGPO(%s):  No client-side extensions for this object.",
                                      v129);
                                  }
                                }
                                v195 = 1;
                              }
                              v140 = 0;
                              ldb = 0;
                              if ( v73 < 2 )
                              {
                                if ( *(_DWORD *)&g_dwDebugLevel )
                                {
                                  if ( g_lpDebugMsg )
                                  {
                                    g_lpDebugMsg(
                                      4u,
                                      L"ProcessGPO(%s):  GPO %s was created by an old version of the Group Policy Editor. "
                                       " It will be skipped.",
                                      v183,
                                      v185);
                                  }
                                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                                  {
                                    RedirectDebugMsg(
                                      4u,
                                      L"ProcessGPO(%s):  GPO %s was created by an old version of the Group Policy Editor. "
                                       " It will be skipped.",
                                      v183,
                                      v185);
                                  }
                                }
                                v140 = 1;
                                ldb = 1;
                              }
                              if ( v193 && (v128 & 2) != 0 || (v141 = 0, LODWORD(entry) = 0, !v193) && (v128 & 1) != 0 )
                              {
                                if ( *(_DWORD *)&g_dwDebugLevel )
                                {
                                  if ( g_lpDebugMsg )
                                  {
                                    g_lpDebugMsg(
                                      4u,
                                      L"ProcessGPO(%s):  GPO %s is disabled.  It will be skipped.",
                                      v183,
                                      v185);
                                  }
                                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                                  {
                                    RedirectDebugMsg(
                                      4u,
                                      L"ProcessGPO(%s):  GPO %s is disabled.  It will be skipped.",
                                      v183,
                                      v185);
                                  }
                                }
                                v141 = 1;
                                LODWORD(entry) = 1;
                              }
                              if ( v124 )
                              {
                                v38 = v183;
                                goto LABEL_472;
                              }
                              if ( *(_DWORD *)&g_dwDebugLevel )
                              {
                                if ( g_lpDebugMsg )
                                {
                                  v38 = v183;
                                  g_lpDebugMsg(
                                    4u,
                                    L"ProcessGPO(%s):  GPO %s doesn't contain any data since the version number is 0.  It "
                                     "will be skipped.",
                                    v183,
                                    v185);
LABEL_470:
                                  v195 = 1;
LABEL_472:
                                  v142 = -1;
                                  do
                                    ++v142;
                                  while ( a1[v142] );
                                  v143 = v142 + 20;
                                  v144 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * (v142 + 20));
                                  v145 = v144;
                                  v201 = v144;
                                  if ( !v144 )
                                  {
                                    LastError = GetLastError();
                                    if ( *(_DWORD *)&g_dwDebugLevel )
                                    {
                                      v146 = g_lpDebugMsg;
                                      if ( g_lpDebugMsg )
                                      {
                                        v147 = GetLastError();
                                        v146(2u, L"ProcessGPO(%s):  Failed to allocate memory with %d", v38, v147);
                                        v39 = v185;
                                        v40 = v186;
                                        v41 = v187;
                                        goto LABEL_132;
                                      }
                                      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                                      {
                                        v148 = GetLastError();
                                        RedirectDebugMsg(
                                          2u,
                                          L"ProcessGPO(%s):  Failed to allocate memory with %d",
                                          v38,
                                          v148);
                                        v39 = v185;
                                        v40 = v186;
                                        v41 = v187;
                                        goto LABEL_132;
                                      }
                                    }
LABEL_338:
                                    v39 = v185;
                                    v40 = v186;
                                    v41 = v187;
                                    v42 = v184;
                                    goto LABEL_583;
                                  }
                                  if ( v193 )
                                  {
                                    if ( !v143 )
                                      goto LABEL_501;
                                    if ( v143 <= 0x7FFFFFFF )
                                    {
                                      v149 = L"LDAP://CN=Machine,";
                                      v150 = v143;
                                      v151 = v144;
                                      v152 = 2147483646;
                                      while ( v152 )
                                      {
                                        v153 = *v149;
                                        if ( !*v149 )
                                          break;
                                        ++v149;
                                        *v151++ = v153;
                                        --v152;
                                        if ( !--v150 )
                                          goto LABEL_499;
                                      }
LABEL_500:
                                      *v151 = 0;
LABEL_501:
                                      StringCchCatW(v145, v143, v202);
                                      if ( v203 )
                                      {
                                        v160 = v204;
                                        v161 = v192;
                                        v162 = v199;
                                        v163 = (struct _GPOINFO *)v205;
                                        v164 = GetLastError();
                                        v199 = v164;
                                        v165 = a6;
                                        v180 = (__int64)v160;
                                        v178 = v161;
                                        v177 = v163;
                                        v145 = (unsigned __int16 *)v201;
                                        v166 = v198[0];
                                        v141 = (int)entry;
                                        v167 = AllocGpContainer(
                                                 v196,
                                                 1,
                                                 v197,
                                                 (int)entry,
                                                 v198[0],
                                                 (PCNZWCH)v201,
                                                 (__int64)v186,
                                                 (__int64)v185,
                                                 (__int64)v230,
                                                 (__int64)v177,
                                                 v162,
                                                 v178,
                                                 v180,
                                                 v206,
                                                 a6,
                                                 (__int64)v187);
                                        if ( !v167 )
                                        {
                                          if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GpupdateCrash_gptmodify>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_GpupdateCrash_gptmodify>::GetImpl'::`2'::impl) )
                                          {
                                            v164 = GetLastError();
                                            v199 = v164;
                                          }
                                          if ( *(_DWORD *)&g_dwDebugLevel )
                                          {
                                            if ( g_lpDebugMsg )
                                            {
                                              g_lpDebugMsg(4u, L"AddGPO: Failed to allocate memory for Gp Container.");
                                            }
                                            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                                            {
                                              RedirectDebugMsg(
                                                4u,
                                                L"AddGPO: Failed to allocate memory for Gp Container.");
                                            }
                                          }
                                          SetLastError(v164);
                                          v42 = 0;
                                          LastError = GetLastError();
                                          LocalFree(v145);
                                          v39 = v185;
                                          v40 = v186;
                                          v41 = v187;
                                          goto LABEL_582;
                                        }
                                        v168 = v203;
                                        *(_QWORD *)(v167 + 112) = *v203;
                                        *v168 = v167;
                                        SetLastError(v164);
                                        v184 = 1;
                                        v140 = ldb;
                                      }
                                      else
                                      {
                                        v165 = a6;
                                        v166 = v198[0];
                                      }
                                      if ( a17 && v197 && !v140 && !v141 && !v195 && (v200 || v192) )
                                      {
                                        v41 = v187;
                                        v39 = v185;
                                        v40 = v186;
                                        v42 = AddGPO(
                                                v207[0],
                                                v196,
                                                v158,
                                                v159,
                                                (int)lpString2,
                                                v165,
                                                v166,
                                                v145,
                                                (__int64)v186,
                                                (__int64)v185,
                                                (__int64)v230,
                                                v187,
                                                v179,
                                                v181,
                                                a9,
                                                v206,
                                                0,
                                                0,
                                                a13,
                                                v182,
                                                a17);
                                      }
                                      else
                                      {
                                        v42 = v184;
                                        v41 = v187;
                                        v40 = v186;
                                        v39 = v185;
                                      }
                                      if ( !v42 )
                                      {
                                        LastError = GetLastError();
                                        if ( *(_DWORD *)&g_dwDebugLevel )
                                        {
                                          if ( g_lpDebugMsg )
                                          {
                                            v38 = v183;
                                            g_lpDebugMsg(
                                              2u,
                                              L"ProcessGPO(%s):  Failed to add GPO <%s> to the list.",
                                              v183,
                                              v39);
LABEL_531:
                                            LocalFree(v145);
                                            goto LABEL_583;
                                          }
                                          if ( g_lpDebugMsgContextInstance )
                                          {
                                            v38 = v183;
                                            if ( g_lpDebugMsgContext )
                                              RedirectDebugMsg(
                                                2u,
                                                L"ProcessGPO(%s):  Failed to add GPO <%s> to the list.",
                                                v183,
                                                v39);
                                            goto LABEL_531;
                                          }
                                        }
                                      }
                                      v38 = v183;
                                      goto LABEL_531;
                                    }
                                  }
                                  else
                                  {
                                    if ( !v143 )
                                      goto LABEL_501;
                                    if ( v143 <= 0x7FFFFFFF )
                                    {
                                      v154 = L"LDAP://CN=User,";
                                      v155 = v143;
                                      v151 = v144;
                                      v156 = 2147483646;
                                      while ( v156 )
                                      {
                                        v157 = *v154;
                                        if ( !*v154 )
                                          break;
                                        ++v154;
                                        *v151++ = v157;
                                        --v156;
                                        if ( !--v155 )
                                        {
LABEL_499:
                                          --v151;
                                          goto LABEL_500;
                                        }
                                      }
                                      goto LABEL_500;
                                    }
                                  }
                                  *v144 = 0;
                                  goto LABEL_501;
                                }
                                if ( g_lpDebugMsgContextInstance )
                                {
                                  v38 = v183;
                                  if ( g_lpDebugMsgContext )
                                    RedirectDebugMsg(
                                      4u,
                                      L"ProcessGPO(%s):  GPO %s doesn't contain any data since the version number is 0.  I"
                                       "t will be skipped.",
                                      v183,
                                      v185);
                                  goto LABEL_470;
                                }
                              }
                              v38 = v183;
                              goto LABEL_470;
                            }
                          }
LABEL_392:
                          v129 = v183;
                          goto LABEL_393;
                        }
                        v169 = LdapGetLastError();
                        LastError = LdapMapErrorToWin32(v169);
                        if ( *(_DWORD *)&g_dwDebugLevel )
                        {
                          if ( g_lpDebugMsg )
                          {
                            v38 = v183;
                            g_lpDebugMsg(2u, L"ProcessGPO(%s):  GPO %s does not have a version number.", v183, a1);
LABEL_539:
                            LogLdapServerError(a11, v120);
                            v39 = v185;
                            v40 = v186;
                            v41 = 0;
                            goto LABEL_132;
                          }
                          if ( g_lpDebugMsgContextInstance )
                          {
                            v38 = v183;
                            if ( g_lpDebugMsgContext )
                              RedirectDebugMsg(2u, L"ProcessGPO(%s):  GPO %s does not have a version number.", v183, a1);
                            goto LABEL_539;
                          }
                        }
                        v38 = v183;
                        goto LABEL_539;
                      }
                      if ( *(_DWORD *)&g_dwDebugLevel )
                      {
                        if ( g_lpDebugMsg )
                        {
                          g_lpDebugMsg(4u, L"ProcessGPO(%s):  No display name for this object.", v183);
                        }
                        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                        {
                          RedirectDebugMsg(4u, L"ProcessGPO(%s):  No display name for this object.", v183);
                        }
                      }
                      v39 = (WCHAR *)LocalAlloc(0x40u, 4u);
                      v185 = v39;
                      if ( v39 )
                      {
                        *v39 = 0;
                        goto LABEL_369;
                      }
                      LastError = GetLastError();
                      if ( *(_DWORD *)&g_dwDebugLevel )
                      {
                        if ( g_lpDebugMsg )
                        {
                          v38 = v183;
                          g_lpDebugMsg(2u, L"ProcessGPO(%s):  Unable to allocate memory", v183);
                          v40 = v186;
                          v41 = 0;
                          goto LABEL_132;
                        }
                        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                        {
                          v38 = v183;
                          RedirectDebugMsg(2u, L"ProcessGPO(%s):  Unable to allocate memory", v183);
                          v40 = v186;
                          v41 = 0;
                          goto LABEL_132;
                        }
                      }
                      v41 = 0;
                      goto LABEL_580;
                    }
                    v170 = LdapGetLastError();
                    v171 = v170;
                    if ( v170 == 16 )
                    {
LABEL_541:
                      if ( v56 )
                      {
                        if ( *(_DWORD *)&g_dwDebugLevel )
                        {
                          if ( g_lpDebugMsg )
                          {
                            g_lpDebugMsg(4u, L"ProcessGPO(%s):  Machine does not have access to <%s>", v38, a1);
                          }
                          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                          {
                            RedirectDebugMsg(4u, L"ProcessGPO(%s):  Machine does not have access to <%s>", v38, a1);
                          }
                        }
                      }
                      else if ( *(_DWORD *)&g_dwDebugLevel )
                      {
                        if ( g_lpDebugMsg )
                        {
                          g_lpDebugMsg(4u, L"ProcessGPO(%s):  User does not have access to <%s>", v38, a1);
                        }
                        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                        {
                          RedirectDebugMsg(4u, L"ProcessGPO(%s):  User does not have access to <%s>", v38, a1);
                        }
                      }
                      v42 = 1;
                      v39 = 0;
                      v40 = 0;
                      v41 = 0;
                      goto LABEL_583;
                    }
                    LastError = LdapMapErrorToWin32(v170);
                    if ( !*(_DWORD *)&g_dwDebugLevel )
                      goto LABEL_569;
                    if ( g_lpDebugMsg )
                    {
                      LODWORD(lpString2) = v171;
                      g_lpDebugMsg(
                        2u,
                        L"ProcessGPO(%s):  GPO %s does not have a file system path, error = 0x%x.",
                        v38,
                        a1,
                        lpString2);
LABEL_569:
                      v174 = v50;
LABEL_570:
                      LogLdapServerError(v35, v174);
                      v39 = 0;
                      v40 = 0;
                      v41 = 0;
                      v42 = v184;
                      goto LABEL_583;
                    }
                    if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
                      goto LABEL_569;
                    v172 = L"ProcessGPO(%s):  GPO %s does not have a file system path, error = 0x%x.";
                  }
                  else
                  {
                    v173 = LdapGetLastError();
                    v171 = v173;
                    if ( v173 == 16 )
                      goto LABEL_541;
                    LastError = LdapMapErrorToWin32(v173);
                    if ( !*(_DWORD *)&g_dwDebugLevel )
                      goto LABEL_569;
                    if ( g_lpDebugMsg )
                    {
                      LODWORD(lpString2) = v171;
                      g_lpDebugMsg(
                        2u,
                        L"ProcessGPO(%s):  GPO %s does not have a functionality version number, error = 0x%x.",
                        v38,
                        a1,
                        lpString2);
                      goto LABEL_569;
                    }
                    if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
                      goto LABEL_569;
                    v172 = L"ProcessGPO(%s):  GPO %s does not have a functionality version number, error = 0x%x.";
                  }
                  LODWORD(lpString2) = v171;
                  RedirectDebugMsg(2u, v172, v38, a1, lpString2);
                  goto LABEL_569;
                }
                v59 = g_lpDebugMsgContextInstance;
                if ( g_lpDebugMsgContextInstance )
                {
                  v38 = v183;
                  if ( !g_lpDebugMsgContext )
                    goto LABEL_185;
                  RedirectDebugMsg(4u, L"ProcessGPO(%s):  Machine WQL filter is assumed to be true.", v183);
                  goto LABEL_174;
                }
                goto LABEL_172;
              }
              goto LABEL_208;
            }
          }
          else if ( (v196 & 0x4000000) != 0 )
          {
            v192 = 1;
            v57 = *(_DWORD *)&g_dwDebugLevel;
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              v58 = g_lpDebugMsg;
              if ( g_lpDebugMsg )
              {
                v38 = v183;
                g_lpDebugMsg(4u, L"ProcessGPO(%s):  User WQL filter is assumed to be true.", v183);
                goto LABEL_174;
              }
              v59 = g_lpDebugMsgContextInstance;
              if ( g_lpDebugMsgContextInstance )
              {
                v38 = v183;
                if ( !g_lpDebugMsgContext )
                  goto LABEL_185;
                RedirectDebugMsg(4u, L"ProcessGPO(%s):  User WQL filter is assumed to be true.", v183);
                goto LABEL_174;
              }
LABEL_172:
              v38 = v183;
              goto LABEL_185;
            }
LABEL_208:
            v38 = v183;
            goto LABEL_209;
          }
        }
        v38 = v183;
        goto LABEL_174;
      }
      v52 = LocalAlloc(0x40u, 0x28u);
      v53 = v52;
      *(_QWORD *)v198 = v52;
      if ( !v52 && *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"ProcessGPO(%s):  cannot allocate memory for xpWMIInfo", v183);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"ProcessGPO(%s):  cannot allocate memory for xpWMIInfo", v183);
        }
      }
      *((_QWORD *)v52 + 3) = 0;
      LastError = StringClone(v230, (unsigned __int16 **)v52);
      if ( LastError && *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"ProcessGPO(%s):  StringClone failed to copy GPOName.", v183);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"ProcessGPO(%s):  StringClone failed to copy GPOName.", v183);
        }
      }
      v50 = entry;
      v54 = FilterCheck(
              a11,
              entry,
              a14,
              v223,
              a15,
              a16,
              &v192,
              (unsigned __int16 **)&v204,
              (struct _GPWMIINFO *)v52,
              v51);
      *((_DWORD *)v52 + 2) = v192;
      if ( v54 && (CGPServiceEventReporting::s_dwTestFlags & 0x20) == 0 )
      {
        if ( *((_QWORD *)v52 + 3) )
        {
          v55 = *((_QWORD *)v51 + 38);
          v53 = 0;
          if ( v55 )
            *((_QWORD *)v52 + 4) = v55;
          *((_QWORD *)v51 + 38) = v52;
        }
        if ( v53 )
          CGPWMI::FreeGPWMIInfo(v53);
        v35 = a11;
        goto LABEL_156;
      }
      LastError = GetLastError();
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          v38 = v183;
          g_lpDebugMsg(2u, L"ProcessGPO(%s):  CheckFilterAcess failed for <%s>", v183, a1);
LABEL_198:
          if ( a19 )
          {
            v60 = (unsigned __int16 *)*((_QWORD *)v51 + 33);
            v61 = *((_DWORD *)v51 + 64);
            v64 = GetTickCount() - v61;
            ld = *((_DWORD *)v51 + 70);
            for ( k = 0; k < 6; ++k )
            {
              if ( FindNLSString(
                     0x7Fu,
                     0x200001u,
                     L"ds\\grouppolicy\\client\\gpsvc\\engine\\gpqry.cpp",
                     -1,
                     (LPCWSTR)*(&GPSourceFileNameIdTable + 2 * k),
                     -1,
                     0) != -1 )
              {
                v66 = *((_DWORD *)&GPSourceFileNameIdTable + 4 * k + 2);
                goto LABEL_205;
              }
            }
            v66 = -1;
LABEL_205:
            CGPAdminEventGPOFailure::CGPAdminEventGPOFailure(
              (CGPAdminEventGenericFailure *)v209,
              v62,
              v66,
              v63,
              ld,
              v64,
              LastError,
              v60,
              a1);
            CGPPolicyEventReporting::Report(*((CGPPolicyEventReporting **)v200 + 34), (struct CGPEventInfo *)v209, v67);
            v209[0] = &CGPAdminEventLdapFailure::`vftable';
            CGPAdminEventInitFailure::~CGPAdminEventInitFailure((CGPAdminEventInitFailure *)v209);
            v38 = v183;
          }
          CGPWMI::FreeGPWMIInfo(v52);
          v39 = 0;
          v40 = 0;
          v41 = 0;
          v42 = v184;
          goto LABEL_583;
        }
        if ( g_lpDebugMsgContextInstance )
        {
          v38 = v183;
          if ( g_lpDebugMsgContext )
            RedirectDebugMsg(2u, L"ProcessGPO(%s):  CheckFilterAcess failed for <%s>", v183, a1);
          goto LABEL_198;
        }
      }
      v38 = v183;
      goto LABEL_198;
    }
    v175 = LdapGetLastError();
    LastError = LdapMapErrorToWin32(v175);
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        v38 = v183;
        g_lpDebugMsg(2u, L"ProcessGPO(%s):  GPO %s does not have a common name (a GUID).", v183, a1);
LABEL_578:
        v174 = entry;
        goto LABEL_570;
      }
      if ( g_lpDebugMsgContextInstance )
      {
        v38 = v183;
        if ( g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"ProcessGPO(%s):  GPO %s does not have a common name (a GUID).", v183, a1);
        goto LABEL_578;
      }
    }
    v38 = v183;
    goto LABEL_578;
  }
  LastError = GetLastError();
  if ( !*(_DWORD *)&g_dwDebugLevel )
  {
LABEL_78:
    v39 = 0;
    v40 = 0;
    v41 = 0;
    v42 = 0;
LABEL_582:
    v38 = v183;
    goto LABEL_583;
  }
  if ( !g_lpDebugMsg )
  {
    if ( g_lpDebugMsgContextInstance )
    {
      v38 = v183;
      if ( g_lpDebugMsgContext )
        RedirectDebugMsg(2u, L"ProcessGPO(%s):  CheckGPOAccess failed for <%s>", v183, a1);
      v39 = 0;
      v40 = 0;
      v41 = 0;
      v42 = 0;
      goto LABEL_583;
    }
    goto LABEL_78;
  }
  v38 = v183;
  g_lpDebugMsg(2u, L"ProcessGPO(%s):  CheckGPOAccess failed for <%s>", v183, a1);
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
LABEL_583:
  if ( v205 )
    LocalFree(v205);
  if ( v40 )
    LocalFree(v40);
  if ( v39 )
    LocalFree(v39);
  if ( v41 )
    LocalFree(v41);
  if ( v204 )
    LocalFree(v204);
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"ProcessGPO(%s):  ==============================", v38);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"ProcessGPO(%s):  ==============================", v38);
    }
  }
  SetLastError(LastError);
  return v42;
}

```

## disassembly

```asm
0x18003a810  push    rbp
0x18003a812  push    rbx
0x18003a813  push    rsi
0x18003a814  push    rdi
0x18003a815  push    r12
0x18003a817  push    r13
0x18003a819  push    r14
0x18003a81b  push    r15
0x18003a81d  lea     rbp, [rsp-2E8h]
0x18003a825  sub     rsp, 418h
0x18003a82c  mov     rax, cs:__security_cookie
0x18003a833  xor     rax, rsp
0x18003a836  mov     [rbp+320h+var_50], rax
0x18003a83d  mov     qword ptr [rbp+320h+var_2F8], r9
0x18003a841  mov     rsi, r8
0x18003a844  mov     r14d, edx
0x18003a847  mov     [rbp+320h+var_34C], edx
0x18003a84a  mov     [rbp+320h+lpString1], rcx
0x18003a84e  mov     rax, [rbp+320h+arg_20]
0x18003a855  mov     [rbp+320h+var_318], rax
0x18003a859  mov     rax, [rbp+320h+arg_48]
0x18003a860  mov     [rbp+320h+var_300], rax
0x18003a864  mov     rcx, [rbp+320h+arg_50]
0x18003a86b  mov     [rbp+320h+ld], rcx
0x18003a86f  mov     rax, [rbp+320h+arg_58]
0x18003a876  mov     [rbp+320h+entry], rax
0x18003a87a  mov     r15, [rbp+320h+arg_68]
0x18003a881  mov     r12, [rbp+320h+arg_70]
0x18003a888  mov     r13, [rbp+320h+arg_78]
0x18003a88f  mov     rax, [rbp+320h+arg_88]
0x18003a896  mov     [rbp+320h+var_330], rax
0x18003a89a  xor     ecx, ecx
0x18003a89c  mov     [rbp+320h+var_340], ecx
0x18003a89f  mov     [rbp+320h+var_350], ecx
0x18003a8a2  movups  xmm0, xmmword ptr cs:aLdap; "LDAP://"
0x18003a8a9  movups  xmmword ptr [rbp+320h+String2], xmm0
0x18003a8b0  lea     rax, [rbp+320h+String2]
0x18003a8b7  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18003a8be  xchg    ax, ax
0x18003a8c0  inc     rbx
0x18003a8c3  cmp     [rax+rbx*2], cx
0x18003a8c7  jnz     short loc_18003A8C0
0x18003a8c9  movups  xmm0, xmmword ptr cs:aNtsecuritydesc; "nTSecurityDescriptor"
0x18003a8d0  movups  xmmword ptr [rbp+320h+var_150], xmm0
0x18003a8d7  movups  xmm1, xmmword ptr cs:aNtsecuritydesc+10h; "tyDescriptor"
0x18003a8de  movups  xmmword ptr [rbp+320h+var_140], xmm1
0x18003a8e5  movups  xmm0, xmmword ptr cs:aNtsecuritydesc+1Ah; "criptor"
0x18003a8ec  movups  xmmword ptr [rbp+320h+var_140+0Ah], xmm0
0x18003a8f3  mov     eax, dword ptr cs:aCn_0; "cn"
0x18003a8f9  mov     dword ptr [rbp+320h+attr], eax
0x18003a8ff  movzx   eax, word ptr cs:aCn_0+4; ""
0x18003a906  mov     [rbp+320h+var_1EC], ax
0x18003a90d  movups  xmm0, xmmword ptr cs:aDisplayname_0; "displayName"
0x18003a914  movups  xmmword ptr [rbp+320h+var_1A8], xmm0
0x18003a91b  movsd   xmm1, qword ptr cs:aDisplayname_0+10h; "ame"
0x18003a923  movsd   [rbp+320h+var_198], xmm1
0x18003a92b  movups  xmm0, xmmword ptr cs:aGpcfilesyspath; "gPCFileSysPath"
0x18003a932  movups  xmmword ptr [rbp+320h+var_170], xmm0
0x18003a939  movups  xmm1, xmmword ptr cs:aGpcfilesyspath+0Eh; "SysPath"
0x18003a940  movups  xmmword ptr [rbp+320h+var_170+0Eh], xmm1
0x18003a947  movups  xmm0, xmmword ptr cs:aVersionnumber; "versionNumber"
0x18003a94e  movups  xmmword ptr [rbp+320h+var_190], xmm0
0x18003a955  movups  xmm1, xmmword ptr cs:aVersionnumber+0Ch; "nNumber"
0x18003a95c  movups  xmmword ptr [rbp+320h+var_190+0Ch], xmm1
0x18003a963  movups  xmm0, xmmword ptr cs:aGpcfunctionali; "gPCFunctionalityVersion"
0x18003a96a  movups  xmmword ptr [rbp+320h+var_120], xmm0
0x18003a971  movups  xmm1, xmmword ptr cs:aGpcfunctionali+10h; "ionalityVersion"
0x18003a978  movups  [rbp+320h+var_110], xmm1
0x18003a97f  movups  xmm0, xmmword ptr cs:aGpcfunctionali+20h; "Version"
0x18003a986  movups  [rbp+320h+var_100], xmm0
0x18003a98d  movsd   xmm1, qword ptr cs:aFlags; "flags"
0x18003a995  movsd   qword ptr [rbp+320h+var_1E8], xmm1
0x18003a99d  mov     eax, dword ptr cs:aFlags+8; "s"
0x18003a9a3  mov     [rbp+320h+var_1E0], eax
0x18003a9a9  movups  xmm0, xmmword ptr cs:aGpcwqlfilter; "gPCWQLFilter"
0x18003a9b0  movups  xmmword ptr [rbp+320h+var_1C8], xmm0
0x18003a9b7  movups  xmm1, xmmword ptr cs:aGpcwqlfilter+0Ah; "LFilter"
0x18003a9be  movups  xmmword ptr [rbp+320h+var_1C8+0Ah], xmm1
0x18003a9c5  mov     [rbp+320h+var_308], rcx
0x18003a9c9  mov     [rbp+320h+var_338], ecx
0x18003a9cc  mov     [rbp+320h+var_360], ecx
0x18003a9cf  mov     [rbp+320h+var_310], rcx
0x18003a9d3  call    cs:__imp_GetLastError
0x18003a9d9  mov     edi, eax
0x18003a9db  mov     [rbp+320h+var_378], eax
0x18003a9de  mov     edx, r14d
0x18003a9e1  and     edx, 1
0x18003a9e4  mov     [rbp+320h+var_35C], edx
0x18003a9e7  lea     rcx, aUser; "User"
0x18003a9ee  mov     [rbp+320h+var_328], rcx
0x18003a9f2  lea     rax, aMachine; "Machine"
0x18003a9f9  mov     [rbp+320h+var_2F0], rax
0x18003a9fd  mov     r8, rax
0x18003aa00  cmovz   r8, rcx
0x18003aa04  mov     [rbp+320h+var_3A0], r8
0x18003aa08  mov     ecx, cs:?g_dwDebugLevel@@3KA; ulong g_dwDebugLevel
0x18003aa0e  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003aa15  test    ecx, ecx
0x18003aa17  jz      short loc_18003AA67
0x18003aa19  test    rax, rax
0x18003aa1c  jz      short loc_18003AA31
0x18003aa1e  lea     rdx, aProcessgpoS; "ProcessGPO(%s):  ======================"...
0x18003aa25  mov     ecx, 4
0x18003aa2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa2f  jmp     short loc_18003AA56
0x18003aa31  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x18003aa39  jz      short loc_18003AA67
0x18003aa3b  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18003aa43  jz      short loc_18003AA67
0x18003aa45  lea     rdx, aProcessgpoS; "ProcessGPO(%s):  ======================"...
0x18003aa4c  mov     ecx, 4; unsigned int
0x18003aa51  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18003aa56  mov     r8, [rbp+320h+var_3A0]
0x18003aa5a  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003aa61  mov     ecx, cs:?g_dwDebugLevel@@3KA; ulong g_dwDebugLevel
0x18003aa67  mov     rdx, [rbp+320h+var_330]
0x18003aa6b  test    rdx, rdx
0x18003aa6e  jz      short loc_18003AAE2
0x18003aa70  cmp     dword ptr [rdx+0F0h], 0
0x18003aa77  jz      short loc_18003AAE2
0x18003aa79  test    ecx, ecx
0x18003aa7b  jz      short loc_18003AABA
0x18003aa7d  test    rax, rax
0x18003aa80  jz      short loc_18003AA95
0x18003aa82  lea     rdx, aProcessgpoSAbo; "ProcessGPO(%s): Aborting GetGPOs proces"...
0x18003aa89  mov     ecx, 2
0x18003aa8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa93  jmp     short loc_18003AABA
0x18003aa95  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x18003aa9d  jz      short loc_18003AABA
0x18003aa9f  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18003aaa7  jz      short loc_18003AABA
0x18003aaa9  lea     rdx, aProcessgpoSAbo; "ProcessGPO(%s): Aborting GetGPOs proces"...
0x18003aab0  mov     ecx, 2; unsigned int
0x18003aab5  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18003aaba  call    ?IsEnabled@CGPTestOperationalTraceEvent@@CAHXZ; CGPTestOperationalTraceEvent::IsEnabled(void)
0x18003aabf  test    eax, eax
0x18003aac1  jz      short loc_18003AAD3
0x18003aac3  mov     edx, 1Fh; unsigned int
0x18003aac8  mov     ecx, 1052h; unsigned int
0x18003aacd  call    ?ReportOperationalEvent@CGPOperationalTraceEvent@@SAKKK@Z; CGPOperationalTraceEvent::ReportOperationalEvent(ulong,ulong)
0x18003aad2  nop
0x18003aad3  mov     ecx, edi; dwErrCode
0x18003aad5  call    cs:__imp_SetLastError
0x18003aadb  xor     eax, eax
0x18003aadd  jmp     loc_18003CF76
0x18003aae2  xor     r14d, r14d
0x18003aae5  test    byte ptr [rbp+320h+var_34C], 4
0x18003aae9  jz      short loc_18003AB32
0x18003aaeb  mov     r14d, 1
0x18003aaf1  test    ecx, ecx
0x18003aaf3  jz      short loc_18003AB32
0x18003aaf5  test    rax, rax
0x18003aaf8  jz      short loc_18003AB0D
0x18003aafa  lea     rdx, aProcessgpoSPro_0; "ProcessGPO(%s): ProcessGPO called with "...
0x18003ab01  mov     ecx, 4
0x18003ab06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab0b  jmp     short loc_18003AB32
0x18003ab0d  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x18003ab15  jz      short loc_18003AB32
0x18003ab17  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18003ab1f  jz      short loc_18003AB32
0x18003ab21  lea     rdx, aProcessgpoSPro_0; "ProcessGPO(%s): ProcessGPO called with "...
0x18003ab28  mov     ecx, 4; unsigned int
0x18003ab2d  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18003ab32  mov     [rsp+450h+cchCount2], ebx; cchCount2
0x18003ab36  lea     rax, [rbp+320h+String2]
0x18003ab3d  mov     [rsp+450h+lpString2], rax; unsigned int
0x18003ab42  mov     r9d, ebx; cchCount1
0x18003ab45  mov     r8, [rbp+320h+lpString1]; lpString1
0x18003ab49  mov     edx, 1; dwCmpFlags
0x18003ab4e  mov     ecx, 7Fh; Locale
0x18003ab53  call    cs:__imp_CompareStringW
0x18003ab59  mov     rcx, [rbp+320h+lpString1]
0x18003ab5d  cmp     eax, 2
0x18003ab60  jnz     short loc_18003AB6B
0x18003ab62  movsxd  rax, ebx
0x18003ab65  lea     rdx, [rcx+rax*2]
0x18003ab69  jmp     short loc_18003AB6E
0x18003ab6b  mov     rdx, rcx
0x18003ab6e  mov     [rbp+320h+var_320], rdx
0x18003ab72  cmp     [rbp+320h+arg_30], 0
0x18003ab79  jz      loc_18003ACC9
0x18003ab7f  mov     eax, [rbp+320h+arg_80]
0x18003ab85  mov     [rsp+450h+var_3B0], eax; int
0x18003ab8c  mov     eax, [rbp+320h+arg_60]
0x18003ab92  mov     [rsp+450h+var_3C0], eax; int
0x18003ab99  xor     ecx, ecx
0x18003ab9b  mov     [rsp+450h+var_3C8], ecx; int
0x18003aba2  mov     [rsp+450h+var_3D0], rcx; __int64
0x18003abaa  mov     rax, [rbp+320h+var_300]
0x18003abae  mov     [rsp+450h+var_3D8], rax; __int64
0x18003abb3  mov     eax, [rbp+320h+arg_40]
0x18003abb9  mov     [rsp+450h+var_3E0], eax; int
0x18003abbd  mov     [rsp+450h+var_3F8], rcx; unsigned __int16 *
0x18003abc2  mov     [rsp+450h+var_400], rcx; __int64
0x18003abc7  mov     [rsp+450h+var_408], rcx; __int64
0x18003abcc  mov     [rsp+450h+var_410], rcx; __int64
0x18003abd1  mov     [rsp+450h+var_418], rdx; unsigned __int16 *
0x18003abd6  mov     dword ptr [rsp+450h+pcchFound], ecx; int
0x18003abda  mov     eax, [rbp+320h+arg_28]
0x18003abe0  mov     [rsp+450h+cchCount2], eax; int
0x18003abe4  mov     edx, [rbp+320h+var_34C]; int
0x18003abe7  mov     rcx, qword ptr [rbp+320h+var_2F8]; int
0x18003abeb  call    AddGPO
0x18003abf0  mov     ebx, eax
0x18003abf2  test    eax, eax
0x18003abf4  jnz     short loc_18003AC5A
0x18003abf6  cmp     cs:?g_dwDebugLevel@@3KA, eax; ulong g_dwDebugLevel
0x18003abfc  jz      loc_18003ACBA
0x18003ac02  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003ac09  mov     rsi, [rbp+320h+var_3A0]
0x18003ac0d  test    rax, rax
0x18003ac10  jz      short loc_18003AC2C
0x18003ac12  mov     r9, [rbp+320h+var_320]
0x18003ac16  mov     r8, rsi
0x18003ac19  lea     rdx, aProcessgpoSFai; "ProcessGPO(%s):  Failed to add GPO <%s>"...
0x18003ac20  mov     ecx, 2
0x18003ac25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac2a  jmp     short loc_18003AC5E
0x18003ac2c  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x18003ac34  jz      short loc_18003AC65
0x18003ac36  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18003ac3e  jz      short loc_18003AC65
0x18003ac40  mov     r9, [rbp+320h+var_320]
0x18003ac44  mov     r8, rsi
0x18003ac47  lea     rdx, aProcessgpoSFai; "ProcessGPO(%s):  Failed to add GPO <%s>"...
0x18003ac4e  mov     ecx, 2; unsigned int
0x18003ac53  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18003ac58  jmp     short loc_18003AC5E
0x18003ac5a  mov     rsi, [rbp+320h+var_3A0]
0x18003ac5e  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003ac65  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18003ac6c  jz      short loc_18003ACBA
0x18003ac6e  test    rax, rax
0x18003ac71  jz      short loc_18003AC8D
0x18003ac73  mov     r9, [rbp+320h+lpString1]
0x18003ac77  mov     r8, rsi
0x18003ac7a  lea     rdx, aProcessgpoSDef; "ProcessGPO(%s):  Deferring search for <"...
0x18003ac81  mov     ecx, 4
0x18003ac86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac8b  jmp     short loc_18003ACBA
0x18003ac8d  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x18003ac95  jz      short loc_18003ACBA
0x18003ac97  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18003ac9f  jz      short loc_18003ACBA
0x18003aca1  mov     r9, [rbp+320h+lpString1]
0x18003aca5  mov     r8, rsi
0x18003aca8  lea     rdx, aProcessgpoSDef; "ProcessGPO(%s):  Deferring search for <"...
0x18003acaf  mov     ecx, 4; unsigned int
0x18003acb4  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18003acb9  nop
0x18003acba  mov     ecx, edi; dwErrCode
0x18003acbc  call    cs:__imp_SetLastError
0x18003acc2  mov     eax, ebx
0x18003acc4  jmp     loc_18003CF76
0x18003acc9  xor     edx, edx
0x18003accb  mov     [rbp+320h+var_398], edx
0x18003acce  mov     [rbp+320h+var_390], rdx
0x18003acd2  mov     [rbp+320h+var_380], rdx
0x18003acd6  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003acdd  mov     rbx, [rbp+320h+var_3A0]
0x18003ace1  cmp     cs:?g_dwDebugLevel@@3KA, edx; ulong g_dwDebugLevel
0x18003ace7  jz      short loc_18003AD37
0x18003ace9  test    rax, rax
0x18003acec  jz      short loc_18003AD07
0x18003acee  mov     r9, rcx
0x18003acf1  mov     r8, rbx
0x18003acf4  lea     rdx, aProcessgpoSSea; "ProcessGPO(%s):  Searching <%s>"
0x18003acfb  mov     ecx, 4
0x18003ad00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad05  jmp     short loc_18003AD30
0x18003ad07  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rdx; void * g_lpDebugMsgContextInstance
0x18003ad0e  jz      short loc_18003AD37
0x18003ad10  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rdx; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18003ad17  jz      short loc_18003AD37
0x18003ad19  mov     r9, rcx
0x18003ad1c  mov     r8, rbx
0x18003ad1f  lea     rdx, aProcessgpoSSea; "ProcessGPO(%s):  Searching <%s>"
0x18003ad26  mov     ecx, 4; unsigned int
0x18003ad2b  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18003ad30  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003ad37  test    byte ptr [rbp+320h+var_34C], 8
0x18003ad3b  jz      loc_18003ADDD
0x18003ad41  mov     [rbp+320h+var_348], 1
0x18003ad48  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18003ad4f  jz      short loc_18003AD71
0x18003ad51  test    rax, rax
0x18003ad54  jz      short loc_18003ADB3
0x18003ad56  mov     r8, rbx
0x18003ad59  lea     rdx, aProcessgpoSPro; "ProcessGPO(%s): ProcessGPO called with "...
0x18003ad60  mov     ecx, 4
0x18003ad65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad6a  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003ad71  mov     rsi, [rbp+320h+ld]
0x18003ad75  mov     rbx, [rbp+320h+entry]
0x18003ad79  cmp     [rbp+320h+var_35C], 0
0x18003ad7d  jz      loc_18003AFCF
0x18003ad83  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18003ad8a  jz      loc_18003B01D
  ... truncated ...
```
