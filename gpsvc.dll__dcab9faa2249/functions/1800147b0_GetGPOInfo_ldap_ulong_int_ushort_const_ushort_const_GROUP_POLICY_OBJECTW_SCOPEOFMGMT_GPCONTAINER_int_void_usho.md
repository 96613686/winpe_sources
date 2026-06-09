# GetGPOInfo(ldap *,ulong,int,ushort const *,ushort const *,_GROUP_POLICY_OBJECTW * *,_SCOPEOFMGMT * *,_GPCONTAINER * *,int,void *,ushort const *,CGpoFilter *,CLocator *,_GPOINFO *,int,_BANDWIDTHESTIMATE *,int)

- ea: `0x1800147b0`
- end: `0x180016631`
- name: `?GetGPOInfo@@YAHPEAUldap@@KHPEBG1PEAPEAU_GROUP_POLICY_OBJECTW@@PEAPEAU_SCOPEOFMGMT@@PEAPEAU_GPCONTAINER@@HPEAX1PEAVCGpoFilter@@PEAVCLocator@@PEAU_GPOINFO@@HPEAU_BANDWIDTHESTIMATE@@H@Z`
- size: `7809`
- prototype: `__int64 __fastcall(struct ldap *, unsigned int, unsigned int, unsigned __int16 *, const unsigned __int16 *, struct _GROUP_POLICY_OBJECTW **, struct _SCOPEOFMGMT **, struct _GPCONTAINER **, int, void *, const unsigned __int16 *, struct CGpoFilter *, struct CLocator *, struct _GPOINFO *, int, struct _BANDWIDTHESTIMATE *, int)`
- caller_count: `3`
- callee_count: `39`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005ce5c`
- `0x180095704`
- `0x18009cc38`

## callees

- `0x180003770`
- `0x180014080`
- `0x1800147b0`
- `0x180016640`
- `0x180016728`
- `0x1800167b0`
- `0x1800183d4`
- `0x18001dd14`
- `0x1800246a8`
- `0x18002ba60`
- `0x18002c70c`
- `0x18002ce24`
- `0x18002d188`
- `0x180030944`
- `0x180030bcc`
- `0x180039364`
- `0x18003e060`
- `0x18003ee2c`
- `0x18004f57c`
- `0x180058d90`
- `0x18005c020`
- `0x1800672b0`
- `0x18006f894`
- `0x18006fb68`
- `0x180073984`
- `0x180075ec0`
- `0x180075fb8`
- `0x18007c910`
- `0x18007d320`
- `0x18009cab4`
- `0x18009e540`
- `0x18009e5a4`
- `0x1800a445c`
- `0x1800a45d8`
- `0x1800a4950`
- `0x1800a4a78`
- `0x1800a7604`
- `0x1800b9d0c`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800165ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800165ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001492c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ae6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014db9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014dd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014eb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001500f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001508f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001534a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800155bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800156d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001571e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015acd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ecb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015f8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016325`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001492c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ae6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014db9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014dd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014eb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001500f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001508f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001534a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800155bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800156d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001571e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015acd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ecb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015f8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016325`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014d9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015a4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014d9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015a4b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014d70`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180015a2c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014d70`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180015a2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180014d58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180015a14`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180014d58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180015a14`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180014daf`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180015a5d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180014daf`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180015a5d`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x180014ca3`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x180015d0c`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x180014ca3`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x180015d0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014ed2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014ee3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800165e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014ed2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014ee3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800165e7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180014f70`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180014fba`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180014f70`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180014fba`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015295`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015295`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014f2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800153a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800156e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015e7b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015e8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001638c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016470`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800164f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016517`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800165f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014f2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800153a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800156e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015e7b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015e8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001638c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016470`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800164f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016517`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800165f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800157e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015846`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800157e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015846`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800157a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015807`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800157a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015807`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800157d7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001583c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800157d7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001583c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180014aec`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180014c4a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180014f02`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800154db`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800155e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180015cb3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180016339`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180016426`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180014aec`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180014c4a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180014f02`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800154db`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800155e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180015cb3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180016339`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180016426`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180014e5a`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180014e5a`
- `ntdll!EtwEventWrite` at `0x180014adc`
- `ntdll!EtwEventWrite` at `0x1800156ce`
- `ntdll!EtwEventWrite` at `0x180014adc`
- `ntdll!EtwEventWrite` at `0x1800156ce`
- `ntdll!EtwEventActivityIdControl` at `0x180014a6c`
- `ntdll!EtwEventActivityIdControl` at `0x18001565e`
- `ntdll!EtwEventActivityIdControl` at `0x180014a6c`
- `ntdll!EtwEventActivityIdControl` at `0x18001565e`
- `ntdll!RtlFreeUnicodeString` at `0x180015c08`
- `ntdll!RtlFreeUnicodeString` at `0x180015c08`
- `ntdll!RtlInitUnicodeString` at `0x180015bfe`
- `ntdll!RtlInitUnicodeString` at `0x180015bfe`
- `WLDAP32!__imp_ldap_unbind` at `0x180016534`
- `WLDAP32!__imp_ldap_unbind` at `0x180016534`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180015553`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180015553`
- `WLDAP32!__imp_ldap_msgfree` at `0x180015433`
- `WLDAP32!__imp_ldap_msgfree` at `0x180015433`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180015204`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180015204`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x1800151dc`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x1800151dc`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800153bf`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800153bf`

## string_xrefs

- `0x180014884`: `configurationNamingContext`
- `0x1800148be`: `nTSecurityDescriptor`
- `0x180014be1`: `GetGPOInfo:  Failed to get the machine token with  %d`
- `0x180014c12`: `GetGPOInfo:  Failed to get the machine token with  %d`
- `0x180014de1`: `GetGPOInfo:  Failed to get a token with %d`
- `0x180014e1f`: `GetGPOInfo:  Failed to get a token with %d`
- `0x180014e8c`: `GetGPOInfo:  Failed to duplicate the token with %d`
- `0x180014ebd`: `GetGPOInfo:  Failed to duplicate the token with %d`
- `0x180015740`: `GetGPOInfo:  Unable to detect computer's role due to error=%d`
- `0x180015768`: `GetGPOInfo:  Unable to detect computer's role due to error=%d`
- `0x180015a98`: `GetGPOInfo:  Failed to get a token with  %d`
- `0x180015ad6`: `GetGPOInfo:  Failed to get a token with  %d`
- `0x180015bb3`: `GetGPOInfo:  ProcessLocalGPO failed to process user LGPO for SID=%ls. Exiting`
- `0x180015bde`: `GetGPOInfo:  ProcessLocalGPO failed to process user LGPO for SID=%ls. Exiting`
- `0x180015c52`: `GetGPOInfo:  GetSidString failed with %d`
- `0x180015c85`: `GetGPOInfo:  GetSidString failed with %d`
- `0x180015e3b`: `GetGPOInfo:  ProcessLocalGPO failed to process group LGPO for group SID=%ls. Exiting`
- `0x180015e66`: `GetGPOInfo:  ProcessLocalGPO failed to process group LGPO for group SID=%ls. Exiting`
- `0x1800161ef`: `GetGPOInfo: SaveGPOsToLocalCache failed.`
- `0x180016216`: `GetGPOInfo: SaveGPOsToLocalCache failed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall GetGPOInfo(
        struct ldap *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned __int16 *a4,
        const unsigned __int16 *a5,
        struct _GROUP_POLICY_OBJECTW **a6,
        struct _SCOPEOFMGMT **a7,
        struct _GPCONTAINER **a8,
        int a9,
        void *a10,
        const unsigned __int16 *a11,
        struct CGpoFilter *a12,
        struct CLocator *a13,
        struct _GPOINFO *a14,
        int a15,
        struct _BANDWIDTHESTIMATE *a16,
        int a17)
{
  char v17; // di
  struct ldap *v18; // r15
  unsigned int LastError; // ebx
  void (*v20)(unsigned int, const unsigned __int16 *, ...); // rax
  int v21; // r14d
  unsigned int EventDataDescriptorStorage; // eax
  _QWORD *v23; // r12
  unsigned int v24; // edi
  __int64 v25; // rax
  unsigned __int64 v26; // rsi
  _BYTE *v27; // rax
  unsigned int v28; // eax
  unsigned int v29; // esi
  DWORD v30; // edi
  void (*v31)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v32; // eax
  DWORD v33; // eax
  int v34; // edi
  unsigned int k; // edi
  __int64 v36; // r8
  __int64 *v37; // rdx
  int *v38; // r8
  unsigned int WMIRules; // edi
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  void (*v42)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v43; // eax
  DWORD v44; // eax
  void (*v45)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v46; // eax
  DWORD v47; // eax
  const unsigned __int16 *v48; // rsi
  const struct _EVENT_DESCRIPTOR *v49; // rdx
  unsigned __int16 i; // ax
  PWCHAR *v51; // r15
  void *v52; // rsi
  BOOL v53; // ecx
  LDAP *MachineDomainDS; // rax
  ULONG v55; // eax
  void (*v56)(void *, unsigned int, const unsigned __int16 *, char **); // rsi
  PWCHAR *valuesW; // rdx
  __int64 v58; // r8
  __int64 v59; // rax
  PWCHAR v60; // rdx
  __int64 v61; // rcx
  unsigned __int64 v62; // rsi
  unsigned __int16 *v63; // rax
  unsigned __int16 *v64; // r15
  int v65; // edx
  __int64 v66; // rcx
  _QWORD *v67; // rax
  unsigned int v68; // eax
  _QWORD *v69; // rsi
  unsigned int v70; // edi
  __int64 v71; // rax
  unsigned __int64 v72; // r15
  unsigned int v73; // eax
  int v74; // edx
  struct _SCOPEOFMGMT *v75; // rdi
  unsigned int v76; // r15d
  struct _SCOPEOFMGMT **v77; // rsi
  struct _SCOPEOFMGMT *v78; // rax
  HANDLE v79; // rax
  HANDLE v80; // rax
  void (*v81)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v82; // eax
  DWORD v83; // eax
  const WCHAR *SidString; // rax
  int v85; // esi
  void (*v86)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v87; // eax
  DWORD v88; // eax
  int v89; // edi
  unsigned int j; // edi
  __int64 v91; // r8
  int *v92; // r8
  struct _GROUP_POLICY_OBJECTW *v93; // rax
  struct _GROUP_POLICY_OBJECTW *v94; // rcx
  BYTE **v95; // rsi
  unsigned int GPOCount; // ecx
  int v97; // edi
  struct _GPWMIINFO *v98; // rcx
  unsigned int v99; // ecx
  DWORD v100; // eax
  const struct _EVENT_DESCRIPTOR *v101; // rdx
  void *v102; // rcx
  void *v103; // rcx
  PWCHAR *v104; // rdi
  _QWORD *v105; // rcx
  _QWORD *v106; // rdi
  _QWORD *v107; // rcx
  _QWORD *v108; // rdi
  void (*v109)(unsigned int, const unsigned __int16 *, ...); // rax
  ULONG v111; // [rsp+84h] [rbp-7Ch]
  PWCHAR *v112; // [rsp+88h] [rbp-78h]
  PCNZWCH lpString1; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v114; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v115; // [rsp+A8h] [rbp-58h] BYREF
  int v116; // [rsp+B0h] [rbp-50h]
  unsigned int v117; // [rsp+B8h] [rbp-48h] BYREF
  PWCHAR *vals; // [rsp+C0h] [rbp-40h] BYREF
  BYTE Data[4]; // [rsp+C8h] [rbp-38h] BYREF
  void *phNewToken; // [rsp+D0h] [rbp-30h] BYREF
  HLOCAL v121; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v122; // [rsp+E0h] [rbp-20h]
  DWORD cbData; // [rsp+E8h] [rbp-18h] BYREF
  DWORD TickCount; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int v125; // [rsp+F8h] [rbp-8h] BYREF
  struct _GROUP_POLICY_OBJECTW *v126; // [rsp+100h] [rbp+0h] BYREF
  unsigned int v127[2]; // [rsp+108h] [rbp+8h] BYREF
  struct _GPCONTAINER **v128; // [rsp+110h] [rbp+10h]
  PLDAPMessage entry; // [rsp+118h] [rbp+18h] BYREF
  HKEY phkResult; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 *v131; // [rsp+128h] [rbp+28h]
  HLOCAL v132; // [rsp+130h] [rbp+30h] BYREF
  __int64 v133; // [rsp+138h] [rbp+38h]
  ULONG attrsonly[2]; // [rsp+140h] [rbp+40h]
  struct _GROUP_POLICY_OBJECTW **v135; // [rsp+148h] [rbp+48h]
  int v136; // [rsp+150h] [rbp+50h] BYREF
  DWORD Type; // [rsp+154h] [rbp+54h] BYREF
  void *TokenHandle; // [rsp+158h] [rbp+58h] BYREF
  HLOCAL hMem[2]; // [rsp+160h] [rbp+60h] BYREF
  HLOCAL v140; // [rsp+170h] [rbp+70h] BYREF
  HLOCAL v141; // [rsp+178h] [rbp+78h] BYREF
  LDAP *ld; // [rsp+180h] [rbp+80h]
  struct _SCOPEOFMGMT **v143; // [rsp+188h] [rbp+88h]
  struct _GROUP_POLICY_OBJECTW *v144; // [rsp+190h] [rbp+90h] BYREF
  HLOCAL v145; // [rsp+198h] [rbp+98h] BYREF
  __int64 v146; // [rsp+1A0h] [rbp+A0h]
  _QWORD v147[3]; // [rsp+1A8h] [rbp+A8h] BYREF
  char v148; // [rsp+1C0h] [rbp+C0h]
  int v149; // [rsp+1C1h] [rbp+C1h]
  __int16 v150; // [rsp+1C5h] [rbp+C5h]
  char v151; // [rsp+1C7h] [rbp+C7h]
  struct ldap *v152; // [rsp+1C8h] [rbp+C8h]
  struct _BANDWIDTHESTIMATE *v153; // [rsp+1D0h] [rbp+D0h]
  struct CLocator *v154; // [rsp+1D8h] [rbp+D8h]
  _QWORD v155[12]; // [rsp+1E0h] [rbp+E0h] BYREF
  PWSTR attrs[3]; // [rsp+240h] [rbp+140h] BYREF
  unsigned __int16 v157[8]; // [rsp+258h] [rbp+158h] BYREF
  __int128 v158; // [rsp+268h] [rbp+168h]
  int v159; // [rsp+278h] [rbp+178h]
  WCHAR attr[28]; // [rsp+280h] [rbp+180h] BYREF
  __int128 v161; // [rsp+2B8h] [rbp+1B8h] BYREF
  _OWORD v162[2]; // [rsp+2C8h] [rbp+1C8h]

  v131 = a4;
  v115 = a3;
  v17 = a2;
  v114 = a2;
  v18 = a1;
  v152 = a1;
  v143 = a7;
  *(_QWORD *)attrsonly = a10;
  lpString1 = a5;
  v135 = a6;
  v128 = a8;
  *(_QWORD *)v127 = a11;
  v132 = a12;
  v154 = a13;
  v153 = a16;
  v144 = 0;
  v126 = 0;
  v111 = 0;
  v136 = 0;
  entry = 0;
  wcscpy(attr, L"configurationNamingConext");
  v161 = *(_OWORD *)L"nTSecurityDescriptor";
  v162[0] = *(_OWORD *)L"tyDescriptor";
  *(_OWORD *)((char *)v162 + 10) = *(_OWORD *)L"criptor";
  attrs[0] = attr;
  attrs[1] = (PWSTR)&v161;
  attrs[2] = 0;
  phNewToken = 0;
  TokenHandle = 0;
  v140 = 0;
  v141 = 0;
  v112 = 0;
  vals = 0;
  ld = 0;
  LastError = GetLastError();
  v117 = 0;
  v125 = 0;
  if ( !*(_DWORD *)&g_dwDebugLevel )
    goto LABEL_14;
  v20 = g_lpDebugMsg;
  if ( g_lpDebugMsg )
  {
    g_lpDebugMsg(4u, L"GetGPOInfo:  ********************************");
LABEL_7:
    v20 = g_lpDebugMsg;
    goto LABEL_8;
  }
  if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
  {
    RedirectDebugMsg(4u, L"GetGPOInfo:  ********************************");
    goto LABEL_7;
  }
LABEL_8:
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( v20 )
    {
      v20(4u, L"GetGPOInfo:  Entering...");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"GetGPOInfo:  Entering...");
    }
  }
LABEL_14:
  v145 = 0;
  v146 = 0;
  v21 = v17 & 1;
  TickCount = v21;
  EventDataDescriptorStorage = COperationalBaseEvent::VerifyAndAllocateEventDataDescriptorStorage((COperationalBaseEvent *)&v145);
  v23 = v145;
  v24 = HIDWORD(v146);
  if ( !EventDataDescriptorStorage )
  {
    v25 = 2LL * HIDWORD(v146);
    *((_QWORD *)v145 + v25) = &TickCount;
    v23[v25 + 1] = 4;
    HIDWORD(v146) = ++v24;
  }
  v26 = CGPServiceEventReporting::s_pEventProviderHandle;
  v27 = (_BYTE *)*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  v121 = v27;
  if ( v27[8] == 1 )
  {
    v28 = EtwEventActivityIdControl(2, v27 + 16);
    if ( v28 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(
            2u,
            L"COperationalBaseEvent::ReportOperationalEvent: Failed to set the activity id with error 0x%x",
            v28);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(
            2u,
            L"COperationalBaseEvent::ReportOperationalEvent: Failed to set the activity id with error 0x%x",
            v28);
        }
      }
    }
  }
  if ( (unsigned int)EtwEventWrite(v26, GET_APPLICABLE_GPOS_START, v24, v23) )
    GetLastError();
  TickCount = GetTickCount();
  v29 = 0;
  *v135 = 0;
  if ( v143 )
    *v143 = 0;
  if ( v128 )
    *v128 = 0;
  v116 = CheckForVerbosePolicy();
  if ( v115 )
  {
    v30 = 0;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"GetGPOInfo:  It is for Local User.  Skipping DS stuff.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"GetGPOInfo:  It is for Local User.  Skipping DS stuff.");
      }
    }
    goto LABEL_142;
  }
  if ( !a9 || !v21 )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0x2000Eu, 1, &TokenHandle) )
    {
      if ( GetLastError() != 1008 )
      {
        LastError = GetLastError();
        WMIRules = 0;
        goto LABEL_157;
      }
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 0x2000Eu, &TokenHandle) )
      {
        LastError = GetLastError();
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v42 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            v43 = GetLastError();
            v42(2u, L"GetGPOInfo:  Failed to get a token with %d", v43);
            WMIRules = 0;
            goto LABEL_157;
          }
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            v44 = GetLastError();
            RedirectDebugMsg(2u, L"GetGPOInfo:  Failed to get a token with %d", v44);
            WMIRules = 0;
            goto LABEL_157;
          }
        }
        goto LABEL_61;
      }
    }
    if ( !DuplicateTokenEx(TokenHandle, 8u, 0, SecurityImpersonation, TokenImpersonation, &phNewToken) )
    {
      LastError = GetLastError();
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v45 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v46 = GetLastError();
          v45(2u, L"GetGPOInfo:  Failed to duplicate the token with %d", v46);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v47 = GetLastError();
          RedirectDebugMsg(2u, L"GetGPOInfo:  Failed to duplicate the token with %d", v47);
        }
      }
      CloseHandle(TokenHandle);
      WMIRules = 0;
      goto LABEL_157;
    }
    CloseHandle(TokenHandle);
LABEL_81:
    if ( *v131 == 92 && v131[1] == 92 )
      v131 += 2;
    v30 = GetTickCount();
    hMem[0] = 0;
    hMem[1] = 0;
    v48 = lpString1;
    CGPOperationalEvent::ReportEventW((CGPOperationalEvent *)hMem, v49, v21, lpString1);
    if ( hMem[0] )
      LocalFree(hMem[0]);
    if ( (v114 & 2) != 0 )
    {
      v52 = *(void **)attrsonly;
    }
    else
    {
      while ( *v48 )
      {
        if ( CompareStringW(0x7Fu, 1u, v48, 3, L"OU=", 3) == 2 )
        {
          if ( !AddOU((struct _DNENTRY **)&vals, v48, GPLinkOrganizationalUnit) )
            goto LABEL_98;
        }
        else if ( CompareStringW(0x7Fu, 1u, v48, 3, L"DC=", 3) == 2 )
        {
          if ( !AddOU((struct _DNENTRY **)&vals, v48, GPLinkDomain) )
          {
LABEL_98:
            LastError = GetLastError();
            v51 = vals;
            v29 = 0;
            WMIRules = 0;
            goto LABEL_158;
          }
          break;
        }
        for ( i = *v48; *v48; i = *v48 )
        {
          if ( i == 44 )
            break;
          ++v48;
        }
        if ( *v48 == 44 )
          ++v48;
      }
      v52 = *(void **)attrsonly;
      v112 = vals;
      if ( !(unsigned int)EvaluateDeferredOUs(
                            (struct _DNENTRY *)vals,
                            v114,
                            phNewToken,
                            (struct _GROUP_POLICY_OBJECTW **)&v140,
                            (struct _GROUP_POLICY_OBJECTW **)&v141,
                            v143,
                            v128,
                            v116,
                            v18,
                            &v136,
                            *(void **)attrsonly,
                            a14,
                            a15) )
      {
        LastError = GetLastError();
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"GetGPOInfo:  EvaluateDeferredOUs failed. Exiting");
            v29 = 0;
            WMIRules = 0;
            goto LABEL_157;
          }
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"GetGPOInfo:  EvaluateDeferredOUs failed. Exiting");
            v29 = 0;
            WMIRules = 0;
            goto LABEL_157;
          }
        }
        goto LABEL_60;
      }
    }
    if ( *(_QWORD *)v127 )
    {
      v53 = !v52 && v21;
      MachineDomainDS = GetMachineDomainDS(v53);
      ld = MachineDomainDS;
      if ( !MachineDomainDS )
        goto LABEL_154;
      entry = 0;
      v147[0] = L"1.2.840.113556.1.4.1339";
      v147[1] = 0;
      v147[2] = 0;
      v148 = 1;
      v149 = 0;
      v150 = 0;
      v151 = 0;
      hMem[0] = v147;
      hMem[1] = 0;
      v55 = ldap_search_ext_sW(
              MachineDomainDS,
              (const PWSTR)&DomainName,
              0,
              (const PWSTR)L"(objectClass=*)",
              attrs,
              0,
              (PLDAPControlW *)hMem,
              0,
              &MAX_LDAP_SEARCH_TIME,
              1u,
              &entry);
      v56 = (void (*)(void *, unsigned int, const unsigned __int16 *, char **))v55;
      v111 = v55;
      if ( v55 )
      {
        LdapMapErrorToWin32(v55);
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"GetGPOInfo:  ldap_search_ext_s failed with = <%d>", (unsigned int)v56);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"GetGPOInfo:  ldap_search_ext_s failed with = <%d>", (unsigned int)v56);
          }
        }
        LogLdapServerError(v18, entry);
        goto LABEL_154;
      }
      LODWORD(lpString1) = 0;
      valuesW = ldap_get_valuesW(ld, entry, attr);
      vals = valuesW;
      if ( valuesW )
      {
        *(_OWORD *)v157 = *(_OWORD *)L"CN=%s,CN=Sites,%s";
        v158 = *(_OWORD *)L"=Sites,%s";
        v159 = *(_DWORD *)L"s";
        v58 = -1;
        do
          ++v58;
        while ( v157[v58] != (_WORD)v56 );
        v59 = -1;
        do
          ++v59;
        while ( *(_WORD *)(*(_QWORD *)v127 + 2 * v59) != (_WORD)v56 );
        v60 = *valuesW;
        v61 = -1;
        do
          ++v61;
        while ( v60[v61] != (_WORD)v56 );
        v62 = v61 + v58 + v59 + 1;
        v63 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v62);
        v64 = v63;
        if ( v63 )
        {
          StringCchPrintfW(v63, v62, v157, *(_QWORD *)v127, *vals);
          if ( (unsigned int)SearchDSObject(
                               v64,
                               v114,
                               phNewToken,
                               (struct _GROUP_POLICY_OBJECTW **)&v140,
                               (struct _GROUP_POLICY_OBJECTW **)&v141,
                               v143,
                               v128,
                               v116,
                               GPLinkSite,
                               ld,
                               0,
                               &v136,
                               *(void **)attrsonly,
                               a14,
                               a15) )
          {
            LODWORD(v56) = 1;
          }
          else
          {
            LastError = GetLastError();
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(2u, L"GetGPOInfo:  SearchDSObject failed.  Exiting.");
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(2u, L"GetGPOInfo:  SearchDSObject failed.  Exiting.");
              }
            }
            LODWORD(v56) = (_DWORD)lpString1;
          }
          LocalFree(v64);
        }
        else
        {
          LastError = 14;
          LODWORD(v56) = (_DWORD)lpString1;
        }
        ldap_value_freeW(vals);
        v18 = v152;
      }
      else
      {
        LastError = GetLastError();
        if ( *(_DWORD *)&g_dwDebugLevel != (_DWORD)v56 )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"GetGPOInfo:  Failed to get values.");
          }
          else if ( g_lpDebugMsgContextInstance != v56 && g_lpDebugMsgContext != v56 )
          {
            RedirectDebugMsg(2u, L"GetGPOInfo:  Failed to get values.");
          }
        }
        LogLdapServerError(v18, entry);
      }
      ldap_msgfree(entry);
      if ( !(_DWORD)v56 )
      {
LABEL_154:
        LastError = GetLastError();
LABEL_155:
        WMIRules = v111;
LABEL_156:
        v29 = 0;
        goto LABEL_157;
      }
    }
LABEL_142:
    if ( !(unsigned int)EvaluateDeferredGPOs(
                          v18,
                          v131,
                          v114,
                          phNewToken,
                          v116,
                          (struct _GROUP_POLICY_OBJECTW *)v140,
                          (struct _GROUP_POLICY_OBJECTW *)v141,
                          &v144,
                          &v126,
                          v128,
                          *(void **)attrsonly,
                          (struct CGpoFilter *)v132,
                          v154,
                          a14,
                          a15,
                          v153) )
    {
      LastError = GetLastError();
      v121 = 0;
      v122 = 0;
      v115 = GetTickCount() - v30;
      v127[0] = LastError;
      LODWORD(vals) = v21;
      COperationalBaseEvent::AddArg((COperationalBaseEvent *)&v121, (unsigned int *)&vals);
      COperationalBaseEvent::AddArg((COperationalBaseEvent *)&v121, v127);
      COperationalBaseEvent::AddArg((COperationalBaseEvent *)&v121, &v115);
      COperationalBaseEvent::ReportOperationalEvent((COperationalBaseEvent *)&v121, &gpEvent_GP_POLICY_DOWNLOAD_ERROR);
      if ( v121 )
        LocalFree(v121);
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"GetGPOInfo:  EvaluateDeferredGPOs failed. Exiting");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"GetGPOInfo:  EvaluateDeferredGPOs failed. Exiting");
        }
      }
      goto LABEL_155;
    }
    v132 = 0;
    v133 = 0;
    LODWORD(vals) = GetTickCount() - v30;
    v127[0] = v21;
    if ( !COperationalBaseEvent::VerifyAndAllocateEventDataDescriptorStorage((COperationalBaseEvent *)&v132) )
    {
      v65 = HIDWORD(v133);
      v66 = 2LL * HIDWORD(v133);
      v67 = v132;
      *((_QWORD *)v132 + v66) = v127;
      v67[v66 + 1] = 4;
      HIDWORD(v133) = v65 + 1;
    }
    v68 = COperationalBaseEvent::VerifyAndAllocateEventDataDescriptorStorage((COperationalBaseEvent *)&v132);
    v69 = v132;
    v70 = HIDWORD(v133);
    if ( !v68 )
    {
      v71 = 2LL * HIDWORD(v133);
      *((_QWORD *)v132 + v71) = &vals;
      v69[v71 + 1] = 4;
      HIDWORD(v133) = ++v70;
    }
    v72 = CGPServiceEventReporting::s_pEventProviderHandle;
    if ( *((_BYTE *)v121 + 8) == 1 )
    {
      v73 = EtwEventActivityIdControl(2, (char *)v121 + 16);
      if ( v73 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(
              2u,
              L"COperationalBaseEvent::ReportOperationalEvent: Failed to set the activity id with error 0x%x",
              v73);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(
              2u,
              L"COperationalBaseEvent::ReportOperationalEvent: Failed to set the activity id with error 0x%x",
              v73);
          }
        }
      }
    }
    if ( (unsigned int)EtwEventWrite(v72, gpEvent_GP_POLICY_DOWNLOAD_END, v70, v69) )
      GetLastError();
    if ( v69 )
      LocalFree(v69);
    v75 = 0;
    *(_DWORD *)Data = 0;
    phkResult = 0;
    Type = 0;
    cbData = 0;
    LODWORD(lpString1) = 1;
    if ( a14 )
    {
      LODWORD(lpString1) = *((_DWORD *)a14 + 1);
    }
    else if ( !(unsigned int)GetMachineRole((int *)&lpString1, v74) )
    {
      LastError = GetLastError();
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"GetGPOInfo:  Unable to detect computer's role due to error=%d", LastError);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"GetGPOInfo:  Unable to detect computer's role due to error=%d", LastError);
        }
      }
    }
    if ( (_DWORD)lpString1 )
    {
      if ( !RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
              0,
              0x20019u,
              &phkResult) )
      {
        cbData = 4;
        RegQueryValueExW(phkResult, L"DisableLGPOProcessing", 0, &Type, Data, &cbData);
        RegCloseKey(phkResult);
      }
      if ( !RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Policies\\Microsoft\\Windows\\System",
              0,
              0x20019u,
              &phkResult) )
      {
        cbData = 4;
        RegQueryValueExW(phkResult, L"DisableLGPOProcessing", 0, &Type, Data, &cbData);
        RegCloseKey(phkResult);
      }
    }
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"GetGPOInfo:  dwDisableLGPOProcessing =  %d", *(unsigned int *)Data);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"GetGPOInfo:  dwDisableLGPOProcessing =  %d", *(unsigned int *)Data);
      }
    }
    if ( *(_DWORD *)Data )
      goto LABEL_297;
    if ( *(_QWORD *)attrsonly )
      goto LABEL_297;
    v76 = v114;
    if ( (v114 & 2) != 0 )
      goto LABEL_297;
    v77 = v143;
    if ( v143 )
    {
      v78 = AllocSOM(L"Local");
      v75 = v78;
      if ( !v78 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"GetGPOInfo: Unable to allocate memory for SOM object");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"GetGPOInfo: Unable to allocate memory for SOM object");
          }
        }
        goto LABEL_155;
      }
      *((_DWORD *)v78 + 2) = 1;
      *((_QWORD *)v78 + 4) = *v77;
      *v77 = v78;
    }
    if ( v21 )
      goto LABEL_278;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"GetGPOInfo:  Processing LGP with no machine settings.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"GetGPOInfo:  Processing LGP with no machine settings.");
      }
    }
    if ( (_DWORD)lpString1 == 3 )
    {
LABEL_278:
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"GetGPOInfo:  Processing default LGP.");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"GetGPOInfo:  Processing default LGP.");
        }
      }
      if ( !(unsigned int)ProcessLocalGPO(v116, v76, 0, L"Local", v75, &v126, v128) )
      {
        LastError = GetLastError();
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"GetGPOInfo:  ProcessLocalGPO failed to process default LGPO. Exiting");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"GetGPOInfo:  ProcessLocalGPO failed to process default LGPO. Exiting");
          }
        }
        goto LABEL_155;
      }
LABEL_297:
      v93 = v144;
      if ( v144 )
      {
        v94 = v126;
        if ( v126 )
        {
          if ( v126->pNext )
          {
            do
              v94 = v94->pNext;
            while ( v94->pNext );
          }
          v94->pNext = v144;
          v144->pPrev = v94;
          v93 = v126;
          v95 = (BYTE **)v135;
        }
        else
        {
          v95 = (BYTE **)v135;
        }
      }
      else
      {
        v93 = v126;
        v95 = (BYTE **)v135;
        if ( !v126 )
          goto LABEL_305;
      }
      *v95 = (BYTE *)v93;
LABEL_305:
      if ( a14 )
      {
        GPOCount = GetGPOCount(*((struct _GROUP_POLICY_OBJECTW **)a14 + 8));
        v117 = GPOCount;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"GetGPOInfo: Get %ld GPOs to before filtering.", GPOCount);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"GetGPOInfo: Get %ld GPOs to before filtering.", GPOCount);
          }
        }
        DebugPrintGPOList2(a14);
        if ( *((_QWORD *)a14 + 38) )
        {
          v97 = *(_DWORD *)a14 & 1;
          if ( !v97 && !(unsigned int)IsValuesOverridenUsingRegkey(L"ForceKerberosOverride") )
          {
            v97 = 1;
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(4u, L"GetLdapHandle:  Will force the Kerbeors as this is not overriden in regkey");
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(4u, L"GetLdapHandle:  Will force the Kerbeors as this is not overriden in regkey");
              }
            }
          }
          WMIRules = CGPWMI::GetWMIRules(*((struct _WMIDomain **)a14 + 37), v97);
          if ( WMIRules && *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(2u, L"GetGPOInfo: GetWMIRules failed with error: %d.", WMIRules);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(2u, L"GetGPOInfo: GetWMIRules failed with error: %d.", WMIRules);
            }
          }
          CGPWMI::PrintGPWMIInfo(*((struct _GPWMIINFO **)a14 + 38));
        }
        else
        {
          WMIRules = 0;
        }
        if ( a17 && !(unsigned int)SaveGPOsToLocalCache(a14, *v95, v131) && *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"GetGPOInfo: SaveGPOsToLocalCache failed.");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"GetGPOInfo: SaveGPOsToLocalCache failed.");
          }
        }
        v98 = (struct _GPWMIINFO *)*((_QWORD *)a14 + 38);
        if ( v98 )
        {
          WMIRules = FilterOutNotAllowedGPO(
                       v98,
                       (struct _GROUP_POLICY_OBJECTW *)*v95,
                       (struct _GROUP_POLICY_OBJECTW **)v95);
          v99 = GetGPOCount(*((struct _GROUP_POLICY_OBJECTW **)a14 + 8));
          v125 = v99;
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(4u, L"GetGPOInfo: Get %ld GPOs to after filtering.", v99);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(4u, L"GetGPOInfo: Get %ld GPOs to after filtering.", v99);
            }
          }
          DebugPrintGPOList2(a14);
          if ( WMIRules )
          {
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(2u, L"GetGPOInfo: FilterOutNotAllowedGPO failed with error: %d.", WMIRules);
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(2u, L"GetGPOInfo: FilterOutNotAllowedGPO failed with error: %d.", WMIRules);
              }
            }
            goto LABEL_156;
          }
        }
      }
      else
      {
        WMIRules = 0;
      }
      v29 = 1;
      goto LABEL_157;
    }
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"GetGPOInfo:  Processing LGP with no machine settings. Not a DC.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"GetGPOInfo:  Processing LGP with no machine settings. Not a DC.");
      }
    }
    lpString1 = 0;
    if ( phNewToken || (v79 = GetCurrentThread(), OpenThreadToken(v79, 8u, 1, &phNewToken)) )
    {
LABEL_228:
      if ( v115 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"GetGPOInfo:  Processing LGP with no machine settings. Local User.");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"GetGPOInfo:  Processing LGP with no machine settings. Local User.");
          }
        }
        SidString = GetSidString(phNewToken);
        lpString1 = SidString;
        if ( !SidString )
        {
          LastError = GetLastError();
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            v86 = g_lpDebugMsg;
            if ( g_lpDebugMsg )
            {
              v87 = GetLastError();
              v86(2u, L"GetGPOInfo:  GetSidString failed with %d", v87);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              v88 = GetLastError();
              RedirectDebugMsg(2u, L"GetGPOInfo:  GetSidString failed with %d", v88);
            }
          }
          if ( a14 && a15 )
          {
            v89 = *((_DWORD *)a14 + 64);
            v115 = GetTickCount() - v89;
            v114 = *((_DWORD *)a14 + 70);
            for ( j = 0; j < 6; ++j )
            {
              if ( FindNLSString(
                     0x7Fu,
                     0x200001u,
                     L"ds\\grouppolicy\\client\\gpsvc\\engine\\gplist.cpp",
                     -1,
                     (LPCWSTR)*(&GPSourceFileNameIdTable + 2 * j),
                     -1,
                     0) != -1 )
              {
                v91 = *((unsigned int *)&GPSourceFileNameIdTable + 4 * j + 2);
                goto LABEL_259;
              }
            }
            v91 = 0xFFFFFFFFLL;
LABEL_259:
            CGPAdminEventInitFailure::CGPAdminEventInitFailure(
              v155,
              &gpEvent_INTERNAL_SYSTEM_ERROR,
              v91,
              801,
              v114,
              v115,
              LastError);
            CGPPolicyEventReporting::Report(*((CGPPolicyEventReporting **)a14 + 34), (struct CGPEventInfo *)v155, v92);
            CGPAdminEventInitFailure::~CGPAdminEventInitFailure((CGPAdminEventInitFailure *)v155);
          }
          goto LABEL_155;
        }
        v85 = v116;
        if ( !(unsigned int)ProcessLocalGPO(v116, v76, SidString, L"Local", v75, &v126, v128) )
        {
          LastError = GetLastError();
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(
                2u,
                L"GetGPOInfo:  ProcessLocalGPO failed to process user LGPO for SID=%ls. Exiting",
                lpString1);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(
                2u,
                L"GetGPOInfo:  ProcessLocalGPO failed to process user LGPO for SID=%ls. Exiting",
                lpString1);
            }
          }
          *(_OWORD *)hMem = 0;
          RtlInitUnicodeString((PUNICODE_STRING)hMem, lpString1);
          RtlFreeUnicodeString((PUNICODE_STRING)hMem);
          goto LABEL_155;
        }
        DeleteSidString(lpString1);
        lpString1 = 0;
      }
      else
      {
        v85 = v116;
      }
      if ( !(unsigned int)SelectGroupLGPOToApply(phNewToken, (LPWSTR *)&lpString1) )
      {
        LastError = GetLastError();
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"GetGPOInfo:  SelectGroupLGPOToApply failed.");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"GetGPOInfo:  SelectGroupLGPOToApply failed.");
          }
        }
        goto LABEL_155;
      }
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"GetGPOInfo:  Processing LGP with no machine settings. Local Group.");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"GetGPOInfo:  Processing LGP with no machine settings. Local Group.");
        }
      }
      if ( lpString1 )
      {
        if ( !(unsigned int)ProcessLocalGPO(v85, v76, lpString1, L"Local", v75, &v126, v128) )
        {
          LastError = GetLastError();
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(
                2u,
                L"GetGPOInfo:  ProcessLocalGPO failed to process group LGPO for group SID=%ls. Exiting",
                lpString1);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(
                2u,
                L"GetGPOInfo:  ProcessLocalGPO failed to process group LGPO for group SID=%ls. Exiting",
                lpString1);
            }
          }
          LocalFree((HLOCAL)lpString1);
          goto LABEL_155;
        }
        LocalFree((HLOCAL)lpString1);
        lpString1 = 0;
      }
      goto LABEL_278;
    }
    if ( GetLastError() == 1008 )
    {
      v80 = GetCurrentProcess();
      if ( !OpenProcessToken(v80, 8u, &phNewToken) )
      {
        LastError = GetLastError();
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v81 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            v82 = GetLastError();
            v81(2u, L"GetGPOInfo:  Failed to get a token with  %d", v82);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            v83 = GetLastError();
            RedirectDebugMsg(2u, L"GetGPOInfo:  Failed to get a token with  %d", v83);
          }
        }
        goto LABEL_155;
      }
      goto LABEL_228;
    }
    goto LABEL_154;
  }
  phNewToken = GetMachineToken();
  if ( phNewToken && (*(_WORD *)&CGPServiceEventReporting::s_dwTestFlags & 0xC00) == 0 )
    goto LABEL_81;
  LastError = GetLastError();
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    v31 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      v32 = GetLastError();
      v31(2u, L"GetGPOInfo:  Failed to get the machine token with  %d", v32);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      v33 = GetLastError();
      RedirectDebugMsg(2u, L"GetGPOInfo:  Failed to get the machine token with  %d", v33);
    }
  }
  if ( !a14 || !a15 )
    goto LABEL_61;
  v131 = (unsigned __int16 *)*((_QWORD *)a14 + 33);
  v34 = *((_DWORD *)a14 + 64);
  v115 = GetTickCount() - v34;
  v114 = *((_DWORD *)a14 + 70);
  for ( k = 0; k < 6; ++k )
  {
    if ( FindNLSString(
           0x7Fu,
           0x200001u,
           L"ds\\grouppolicy\\client\\gpsvc\\engine\\gplist.cpp",
           -1,
           (LPCWSTR)*(&GPSourceFileNameIdTable + 2 * k),
           -1,
           0) != -1 )
    {
      v36 = *((unsigned int *)&GPSourceFileNameIdTable + 4 * k + 2);
      goto LABEL_55;
    }
  }
  v36 = 0xFFFFFFFFLL;
LABEL_55:
  if ( LastError == -2146893020
    || LastError == 1398
    || (v37 = gpEvent_FAILED_MACHINE_TOKEN, (*(_WORD *)&CGPServiceEventReporting::s_dwTestFlags & 0x400) != 0) )
  {
    v37 = gpEvent_TIME_SKEW;
  }
  CGPAdminEventGenericFailure::CGPAdminEventGenericFailure(v155, v37, v36, 347, v114, v115, LastError, v131, 0);
  CGPPolicyEventReporting::Report(*((CGPPolicyEventReporting **)a14 + 34), (struct CGPEventInfo *)v155, v38);
  v155[0] = &CGPAdminEventLdapFailure::`vftable';
  CGPAdminEventInitFailure::~CGPAdminEventInitFailure((CGPAdminEventInitFailure *)v155);
LABEL_60:
  v29 = 0;
LABEL_61:
  WMIRules = 0;
LABEL_157:
  v51 = v112;
LABEL_158:
  v121 = 0;
  v122 = 0;
  if ( WMIRules )
  {
    v114 = GetTickCount() - TickCount;
    v125 = WMIRules;
    v117 = v21;
    HIDWORD(v122) = 0;
    COperationalBaseEvent::AddArg((COperationalBaseEvent *)&v121, &v117);
    COperationalBaseEvent::AddArg((COperationalBaseEvent *)&v121, &v125);
    COperationalBaseEvent::AddArg((COperationalBaseEvent *)&v121, &v114);
    COperationalBaseEvent::ReportOperationalEvent((COperationalBaseEvent *)&v121, &GET_APPLICABLE_GPOS_END_FAILURE);
  }
  else if ( a14 )
  {
    v100 = GetTickCount();
    CGPOperationalEvent::ReportEventW(
      (CGPOperationalEvent *)&v121,
      v101,
      a9,
      *(_DWORD *)a14 & 0x10000,
      *(_DWORD *)a14 & 8,
      v117,
      v125,
      v100 - TickCount);
  }
  else
  {
    v117 = a9;
    HIDWORD(v122) = 0;
    COperationalBaseEvent::AddArg((COperationalBaseEvent *)&v121, &v117);
    COperationalBaseEvent::ReportOperationalEvent((COperationalBaseEvent *)&v121, &GET_APPLICABLE_GPOS_END_SUCCESS);
  }
  if ( v121 )
    LocalFree(v121);
  if ( a14 )
  {
    v102 = (void *)*((_QWORD *)a14 + 37);
    if ( v102 )
    {
      CGPWMI::WMIDomainFree(v102);
      *((_QWORD *)a14 + 37) = 0;
    }
    v103 = (void *)*((_QWORD *)a14 + 38);
    if ( v103 )
    {
      CGPWMI::FreeGPWMIInfo(v103);
      *((_QWORD *)a14 + 38) = 0;
    }
  }
  if ( !v29 )
  {
    FreeGPOListImpl(v144);
    FreeGPOListImpl(v126);
  }
  if ( v51 )
  {
    do
    {
      v104 = (PWCHAR *)v51[4];
      FreeDnEntry(v51);
      v51 = v104;
    }
    while ( v104 );
  }
  v105 = v140;
  if ( v140 )
  {
    do
    {
      v106 = (_QWORD *)v105[18];
      LocalFree(v105);
      v105 = v106;
    }
    while ( v106 );
  }
  v107 = v141;
  if ( v141 )
  {
    do
    {
      v108 = (_QWORD *)v107[18];
      LocalFree(v107);
      v107 = v108;
    }
    while ( v108 );
  }
  if ( ld )
    ldap_unbind(ld);
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    v109 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"GetGPOInfo:  Leaving with %d", v29);
    }
    else
    {
      if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
      {
LABEL_389:
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( v109 )
          {
            v109(4u, L"GetGPOInfo:  ********************************");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"GetGPOInfo:  ********************************");
          }
        }
        goto LABEL_395;
      }
      RedirectDebugMsg(4u, L"GetGPOInfo:  Leaving with %d", v29);
    }
    v109 = g_lpDebugMsg;
    goto LABEL_389;
  }
LABEL_395:
  if ( phNewToken )
    CloseHandle(phNewToken);
  if ( v23 )
    LocalFree(v23);
  SetLastError(LastError);
  return v29;
}

```

## disassembly

```asm
0x1800147b0  mov     [rsp-8+arg_10], rbx
0x1800147b5  push    rbp
0x1800147b6  push    rsi
0x1800147b7  push    rdi
0x1800147b8  push    r12
0x1800147ba  push    r13
0x1800147bc  push    r14
0x1800147be  push    r15
0x1800147c0  lea     rbp, [rsp-1F0h]
0x1800147c8  sub     rsp, 2F0h
0x1800147cf  mov     rax, cs:__security_cookie
0x1800147d6  xor     rax, rsp
0x1800147d9  mov     [rbp+220h+var_38], rax
0x1800147e0  mov     [rbp+220h+var_1F8], r9
0x1800147e4  mov     [rbp+220h+var_278], r8d
0x1800147e8  mov     edi, edx
0x1800147ea  mov     [rbp+220h+var_280], edx
0x1800147ed  mov     r15, rcx
0x1800147f0  mov     [rbp+220h+var_158], rcx
0x1800147f7  mov     rax, [rbp+220h+arg_30]
0x1800147fe  mov     [rbp+220h+var_198], rax
0x180014805  mov     rax, [rbp+220h+arg_48]
0x18001480c  mov     qword ptr [rbp+220h+attrsonly], rax
0x180014810  mov     r13, [rbp+220h+arg_68]
0x180014817  mov     rax, [rbp+220h+arg_20]
0x18001481e  mov     [rbp+220h+lpString1], rax
0x180014822  mov     rax, [rbp+220h+arg_28]
0x180014829  mov     [rbp+220h+var_1D8], rax
0x18001482d  mov     rax, [rbp+220h+arg_38]
0x180014834  mov     [rbp+220h+var_210], rax
0x180014838  mov     rax, [rbp+220h+arg_50]
0x18001483f  mov     qword ptr [rbp+220h+var_218], rax
0x180014843  mov     rax, [rbp+220h+arg_58]
0x18001484a  mov     [rbp+220h+var_1F0], rax
0x18001484e  mov     rax, [rbp+220h+arg_60]
0x180014855  mov     [rbp+220h+var_148], rax
0x18001485c  mov     rax, [rbp+220h+arg_78]
0x180014863  mov     [rbp+220h+var_150], rax
0x18001486a  xor     esi, esi
0x18001486c  mov     [rbp+220h+var_190], rsi
0x180014873  mov     [rbp+220h+var_220], rsi
0x180014877  mov     [rbp+220h+var_29C], esi
0x18001487a  mov     [rbp+220h+var_2A0], esi
0x18001487d  mov     [rbp+220h+var_1D0], esi
0x180014880  mov     [rbp+220h+entry], rsi
0x180014884  movups  xmm0, xmmword ptr cs:aConfigurationn; "configurationNamingContext"
0x18001488b  movups  xmmword ptr [rbp+220h+attr], xmm0
0x180014892  movups  xmm1, xmmword ptr cs:aConfigurationn+10h; "ationNamingContext"
0x180014899  movups  [rbp+220h+var_90], xmm1
0x1800148a0  movups  xmm0, xmmword ptr cs:aConfigurationn+20h; "ingContext"
0x1800148a7  movups  [rbp+220h+var_80], xmm0
0x1800148ae  movsd   xmm1, qword ptr cs:aConfigurationn+2Eh; "ext"
0x1800148b6  movsd   qword ptr [rbp+220h+var_80+0Eh], xmm1
0x1800148be  movups  xmm0, xmmword ptr cs:aNtsecuritydesc; "nTSecurityDescriptor"
0x1800148c5  movups  [rbp+220h+var_68], xmm0
0x1800148cc  movups  xmm1, xmmword ptr cs:aNtsecuritydesc+10h; "tyDescriptor"
0x1800148d3  movups  xmmword ptr [rbp+220h+var_58], xmm1
0x1800148da  movups  xmm0, xmmword ptr cs:aNtsecuritydesc+1Ah; "criptor"
0x1800148e1  movups  xmmword ptr [rbp+220h+var_58+0Ah], xmm0
0x1800148e8  lea     rax, [rbp+220h+attr]
0x1800148ef  mov     [rbp+220h+attrs], rax
0x1800148f6  lea     rax, [rbp+220h+var_68]
0x1800148fd  mov     [rbp+220h+var_D8], rax
0x180014904  mov     [rbp+220h+var_D0], rsi
0x18001490b  mov     [rbp+220h+phNewToken], rsi
0x18001490f  mov     [rbp+220h+TokenHandle], rsi
0x180014913  mov     [rbp+220h+var_1B0], rsi
0x180014917  mov     [rbp+220h+var_1A8], rsi
0x18001491b  mov     eax, esi
0x18001491d  mov     [rbp+220h+var_298], rax
0x180014921  mov     [rbp+220h+vals], rax
0x180014925  mov     [rbp+220h+ld], rsi
0x18001492c  call    cs:__imp_GetLastError
0x180014932  mov     ebx, eax
0x180014934  mov     [rbp+220h+var_290], eax
0x180014937  mov     [rbp+220h+var_268], esi
0x18001493a  mov     [rbp+220h+var_228], esi
0x18001493d  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x180014943  jz      loc_1800149DA
0x180014949  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180014950  test    rax, rax
0x180014953  jz      short loc_180014968
0x180014955  lea     rdx, aGetgpoinfo; "GetGPOInfo:  **************************"...
0x18001495c  mov     ecx, 4
0x180014961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014966  jmp     short loc_18001498D
0x180014968  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x180014970  jz      short loc_180014994
0x180014972  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18001497a  jz      short loc_180014994
0x18001497c  lea     rdx, aGetgpoinfo; "GetGPOInfo:  **************************"...
0x180014983  mov     ecx, 4; unsigned int
0x180014988  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18001498d  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180014994  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18001499b  jz      short loc_1800149DA
0x18001499d  test    rax, rax
0x1800149a0  jz      short loc_1800149B5
0x1800149a2  lea     rdx, aGetgpoinfoEnte; "GetGPOInfo:  Entering..."
0x1800149a9  mov     ecx, 4
0x1800149ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149b3  jmp     short loc_1800149DA
0x1800149b5  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x1800149bd  jz      short loc_1800149DA
0x1800149bf  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800149c7  jz      short loc_1800149DA
0x1800149c9  lea     rdx, aGetgpoinfoEnte; "GetGPOInfo:  Entering..."
0x1800149d0  mov     ecx, 4; unsigned int
0x1800149d5  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800149da  mov     [rbp+220h+var_188], rsi
0x1800149e1  mov     [rbp+220h+var_180], rsi
0x1800149e8  mov     r14d, edi
0x1800149eb  and     r14d, 1
0x1800149ef  mov     [rbp+220h+var_230], r14d
0x1800149f3  lea     rcx, [rbp+220h+var_188]; this
0x1800149fa  call    ?VerifyAndAllocateEventDataDescriptorStorage@COperationalBaseEvent@@AEAAKXZ; COperationalBaseEvent::VerifyAndAllocateEventDataDescriptorStorage(void)
0x1800149ff  mov     r12, [rbp+220h+var_188]
0x180014a06  test    eax, eax
0x180014a08  jnz     short loc_180014A30
0x180014a0a  mov     edi, dword ptr [rbp+220h+var_180+4]
0x180014a10  mov     eax, edi
0x180014a12  add     rax, rax
0x180014a15  lea     rcx, [rbp+220h+var_230]
0x180014a19  mov     [r12+rax*8], rcx
0x180014a1d  mov     qword ptr [r12+rax*8+8], 4
0x180014a26  inc     edi
0x180014a28  mov     dword ptr [rbp+220h+var_180+4], edi
0x180014a2e  jmp     short loc_180014A36
0x180014a30  mov     edi, dword ptr [rbp+220h+var_180+4]
0x180014a36  mov     rsi, cs:?s_pEventProviderHandle@CGPServiceEventReporting@@0_KA; unsigned __int64 CGPServiceEventReporting::s_pEventProviderHandle
0x180014a3d  mov     ecx, cs:_tls_index
0x180014a43  mov     rax, gs:58h
0x180014a4c  mov     rax, [rax+rcx*8]
0x180014a50  mov     [rbp+220h+var_248], rax
0x180014a54  mov     ecx, 8
0x180014a59  mov     edx, 10h
0x180014a5e  cmp     byte ptr [rcx+rax], 1
0x180014a62  jnz     short loc_180014ACC
0x180014a64  add     rdx, rax
0x180014a67  mov     ecx, 2
0x180014a6c  call    cs:__imp_EtwEventActivityIdControl
0x180014a72  test    eax, eax
0x180014a74  jz      short loc_180014ACC
0x180014a76  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180014a7d  jz      short loc_180014ACC
0x180014a7f  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180014a86  test    r9, r9
0x180014a89  jz      short loc_180014AA4
0x180014a8b  mov     r8d, eax
0x180014a8e  lea     rdx, aCoperationalba; "COperationalBaseEvent::ReportOperationa"...
0x180014a95  mov     ecx, 2
0x180014a9a  mov     rax, r9
0x180014a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014aa2  jmp     short loc_180014ACC
0x180014aa4  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x180014aac  jz      short loc_180014ACC
0x180014aae  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180014ab6  jz      short loc_180014ACC
0x180014ab8  mov     r8d, eax
0x180014abb  lea     rdx, aCoperationalba; "COperationalBaseEvent::ReportOperationa"...
0x180014ac2  mov     ecx, 2; unsigned int
0x180014ac7  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180014acc  mov     r9, r12
0x180014acf  mov     r8d, edi
0x180014ad2  lea     rdx, GET_APPLICABLE_GPOS_START
0x180014ad9  mov     rcx, rsi
0x180014adc  call    cs:__imp_EtwEventWrite
0x180014ae2  test    eax, eax
0x180014ae4  jz      short loc_180014AEC
0x180014ae6  call    cs:__imp_GetLastError
0x180014aec  call    cs:__imp_GetTickCount
0x180014af2  mov     [rbp+220h+var_230], eax
0x180014af5  mov     rax, [rbp+220h+var_1D8]
0x180014af9  xor     esi, esi
0x180014afb  mov     [rax], rsi
0x180014afe  mov     rax, [rbp+220h+var_198]
0x180014b05  test    rax, rax
0x180014b08  jz      short loc_180014B0D
0x180014b0a  mov     [rax], rsi
0x180014b0d  mov     rax, [rbp+220h+var_210]
0x180014b11  test    rax, rax
0x180014b14  jz      short loc_180014B19
0x180014b16  mov     [rax], rsi
0x180014b19  call    ?CheckForVerbosePolicy@@YAHXZ; CheckForVerbosePolicy(void)
0x180014b1e  mov     [rbp+220h+var_270], eax
0x180014b21  cmp     [rbp+220h+var_278], esi
0x180014b24  jz      short loc_180014B86
0x180014b26  mov     edi, esi
0x180014b28  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x180014b2e  jz      loc_180015443
0x180014b34  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180014b3b  test    rax, rax
0x180014b3e  jz      short loc_180014B56
0x180014b40  lea     rdx, aGetgpoinfoItIs; "GetGPOInfo:  It is for Local User.  Ski"...
0x180014b47  mov     ecx, 4
0x180014b4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b51  jmp     loc_180015443
0x180014b56  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x180014b5d  jz      loc_180015443
0x180014b63  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180014b6a  jz      loc_180015443
0x180014b70  lea     rdx, aGetgpoinfoItIs; "GetGPOInfo:  It is for Local User.  Ski"...
0x180014b77  mov     ecx, 4; unsigned int
0x180014b7c  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180014b81  jmp     loc_180015443
0x180014b86  cmp     [rbp+220h+arg_40], esi
0x180014b8c  jz      loc_180014D58
0x180014b92  test    r14d, r14d
0x180014b95  jz      loc_180014D58
0x180014b9b  call    ?GetMachineToken@@YAPEAXXZ; GetMachineToken(void)
0x180014ba0  mov     [rbp+220h+phNewToken], rax
0x180014ba4  test    rax, rax
0x180014ba7  jz      short loc_180014BB9
0x180014ba9  test    cs:?s_dwTestFlags@CGPServiceEventReporting@@0KA, 0C00h; ulong CGPServiceEventReporting::s_dwTestFlags
0x180014bb3  jz      loc_180014EE9
0x180014bb9  call    cs:__imp_GetLastError
0x180014bbf  mov     ebx, eax
0x180014bc1  mov     [rbp+220h+var_290], eax
0x180014bc4  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x180014bca  jz      short loc_180014C23
0x180014bcc  mov     rdi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180014bd3  test    rdi, rdi
0x180014bd6  jz      short loc_180014BF7
0x180014bd8  call    cs:__imp_GetLastError
0x180014bde  mov     r8d, eax
0x180014be1  lea     rdx, aGetgpoinfoFail_0; "GetGPOInfo:  Failed to get the machine "...
0x180014be8  mov     ecx, 2
0x180014bed  mov     rax, rdi
0x180014bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bf5  jmp     short loc_180014C23
0x180014bf7  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x180014bfe  jz      short loc_180014C23
0x180014c00  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180014c07  jz      short loc_180014C23
0x180014c09  call    cs:__imp_GetLastError
0x180014c0f  mov     r8d, eax
0x180014c12  lea     rdx, aGetgpoinfoFail_0; "GetGPOInfo:  Failed to get the machine "...
0x180014c19  mov     ecx, 2; unsigned int
0x180014c1e  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180014c23  test    r13, r13
0x180014c26  jz      loc_180014D51
0x180014c2c  cmp     [rbp+220h+arg_70], esi
0x180014c32  jz      loc_180014D51
0x180014c38  mov     rsi, [r13+108h]
0x180014c3f  mov     [rbp+220h+var_1F8], rsi
0x180014c43  mov     edi, [r13+100h]
0x180014c4a  call    cs:__imp_GetTickCount
0x180014c50  sub     eax, edi
0x180014c52  mov     [rbp+220h+var_278], eax
0x180014c55  mov     ecx, [r13+118h]
0x180014c5c  mov     [rbp+220h+var_280], ecx
0x180014c5f  xor     edi, edi
0x180014c61  lea     r15, ?GPSourceFileNameIdTable@@3PAU_GP_SOURCE_FILE_NAME_ID_ENTRY@@A; _GP_SOURCE_FILE_NAME_ID_ENTRY near * GPSourceFileNameIdTable
0x180014c68  cmp     edi, 6
0x180014c6b  jnb     short loc_180014CB9
0x180014c6d  mov     esi, edi
0x180014c6f  add     rsi, rsi
0x180014c72  mov     [rsp+320h+pcchFound], 0; pcchFound
0x180014c7b  mov     [rsp+320h+cchValue], 0FFFFFFFFh; cchValue
0x180014c83  mov     rax, [r15+rsi*8]
0x180014c87  mov     [rsp+320h+lpStringValue], rax; lpStringValue
0x180014c8c  mov     r9d, 0FFFFFFFFh; cchSource
0x180014c92  lea     r8, StringSource; "ds\\grouppolicy\\client\\gpsvc\\engine"...
0x180014c99  mov     edx, 200001h; dwFindNLSStringFlags
0x180014c9e  mov     ecx, 7Fh; Locale
0x180014ca3  call    cs:__imp_FindNLSString
0x180014ca9  cmp     eax, 0FFFFFFFFh
0x180014cac  jnz     short loc_180014CB2
0x180014cae  inc     edi
0x180014cb0  jmp     short loc_180014C68
0x180014cb2  mov     r8d, [r15+rsi*8+8]
0x180014cb7  jmp     short loc_180014CBF
0x180014cb9  mov     r8d, 0FFFFFFFFh
0x180014cbf  cmp     ebx, 80090324h
0x180014cc5  jz      short loc_180014CE2
0x180014cc7  cmp     ebx, 576h
0x180014ccd  jz      short loc_180014CE2
0x180014ccf  test    cs:?s_dwTestFlags@CGPServiceEventReporting@@0KA, 400h; ulong CGPServiceEventReporting::s_dwTestFlags
0x180014cd9  lea     rdx, gpEvent_FAILED_MACHINE_TOKEN
0x180014ce0  jz      short loc_180014CE9
0x180014ce2  lea     rdx, gpEvent_TIME_SKEW
0x180014ce9  mov     [rsp+320h+timeout], 0
0x180014cf2  mov     rax, [rbp+220h+var_1F8]
0x180014cf6  mov     [rsp+320h+ClientControls], rax
0x180014cfb  mov     dword ptr [rsp+320h+pcchFound], ebx
0x180014cff  mov     eax, [rbp+220h+var_278]
0x180014d02  mov     [rsp+320h+cchValue], eax
0x180014d06  mov     eax, [rbp+220h+var_280]
0x180014d09  mov     dword ptr [rsp+320h+lpStringValue], eax
0x180014d0d  mov     r9d, 15Bh
0x180014d13  lea     rcx, [rbp+220h+var_140]
0x180014d1a  call    ??0CGPAdminEventGenericFailure@@QEAA@PEBU_EVENT_DESCRIPTOR@@KKW4ProcessingModeEnum@@KKPEBG2@Z; CGPAdminEventGenericFailure::CGPAdminEventGenericFailure(_EVENT_DESCRIPTOR const *,ulong,ulong,ProcessingModeEnum,ulong,ulong,ushort const *,ushort const *)
0x180014d1f  nop
0x180014d20  lea     rdx, [rbp+220h+var_140]; struct CGPEventInfo *
0x180014d27  mov     rcx, [r13+110h]; this
0x180014d2e  call    ?Report@CGPPolicyEventReporting@@QEAAKPEAVCGPEventInfo@@PEAH@Z; CGPPolicyEventReporting::Report(CGPEventInfo *,int *)
0x180014d33  nop
0x180014d34  lea     rax, ??_7CGPAdminEventLdapFailure@@6B@; const CGPAdminEventLdapFailure::`vftable'
0x180014d3b  mov     [rbp+220h+var_140], rax
0x180014d42  lea     rcx, [rbp+220h+var_140]; this
  ... truncated ...
```
